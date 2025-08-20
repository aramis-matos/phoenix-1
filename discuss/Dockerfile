FROM elixir:1.18.4

WORKDIR /app

COPY . .

COPY ./certs/* /usr/local/share/ca-certificates/

RUN update-ca-certificates && \
    apt update && \
    apt install -y git inotify-tools watchman && \
    mix local.hex --force && \
    mix deps.get

EXPOSE 4000