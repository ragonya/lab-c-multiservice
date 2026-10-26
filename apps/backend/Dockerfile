FROM gcc:13-bookworm AS build
WORKDIR /src

COPY include/ include/
COPY lib/ lib/
COPY apps/backend/ apps/backend/

RUN make -C lib && make -C apps/backend

FROM debian:bookworm-slim
WORKDIR /app
COPY --from=build /src/apps/backend/backend /app/backend
EXPOSE 9000
ENTRYPOINT ["/app/backend"]
