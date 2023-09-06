FROM alpine:latest

ARG PB_VERSION=latest

RUN apk add --no-cache \
    unzip \
    # this is needed only if you want to use scp to copy later your pb_data locally
    openssh

# copy PocketBase
COPY ./pocketbase .

# set executable permissions for pocketbase
RUN chmod +x /pocketbase

EXPOSE 8080

ENV PORT 8080

# start PocketBase
CMD ["/pocketbase", "serve", "--http=0.0.0.0:8080"]
