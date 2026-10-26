FROM gcc:13-bookworm AS build
WORKDIR /src

COPY include/ include/
COPY lib/ lib/
COPY apps/loadgen/ apps/loadgen/

RUN make -C lib && make -C apps/loadgen

FROM debian:bookworm-slim
WORKDIR /app
COPY --from=build /src/apps/loadgen/loadgen /app/loadgen
ENTRYPOINT ["/app/loadgen"]
