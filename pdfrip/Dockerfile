FROM alpine:latest

# install Rust
RUN apk update && apk add curl && \
    apk add libgcc && \
    apk add build-base && \
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
    #when issue with resolve sh.rustup.rs
    #curl --resolve sh.rustup.rs:443:108.138.51.125 --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y

# install pdfrip
RUN . "$HOME/.cargo/env" && \
    cargo install --git https://github.com/mufeedvh/pdfrip.git && \
    ln -s /root/.cargo/bin/pdfrip /bin/pdfrip

# exec pdfrip
#ENTRYPOINT ["pdfrip"]
CMD [ "pdfrip", "--help" ]
