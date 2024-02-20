# Créer un Dockerfile pour cette application en mode production
FROM debian:latest

ENV ROCKET_ADDRESS=http://127.0.0.1:8000
ENV DATABASE_URL=postgres://steven:admin@db:5432/blog
EXPOSE 8000

WORKDIR /blog
COPY . .

RUN apt update && apt upgrade -y && apt install -y libpq-dev curl

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --default-toolchain nightly -y

RUN cargo install --path . && \
    cp usr/local/cargo/bin/blog . && \
    cargo install diesel_cli --no-default-features --features postgres
