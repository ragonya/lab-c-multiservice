FROM gcc:13-bookworm AS build
WORKDIR /src

COPY include/ include/
COPY lib/ lib/
COPY apps/balancer/ apps/balancer/

RUN make -C lib && make -C apps/balancer

FROM debian:bookworm-slim
WORKDIR /app
COPY --from=build /src/apps/balancer/balancer /app/balancer
EXPOSE 8080
ENTRYPOINT ["/app/balancer"]
