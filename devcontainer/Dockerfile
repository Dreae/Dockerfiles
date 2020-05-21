FROM fedora

RUN dnf -y update
RUN dnf -y install fish rust cargo pkg-config openssl-devel

RUN adduser -m -s /usr/bin/fish -G wheel dev
RUN echo "dev:dev" | chpasswd
USER dev
RUN cargo install starship
ENV PATH="/home/dev/.cargo/bin:${PATH}"
COPY --chown=dev:dev devcontainer/config.fish /home/dev/.config/fish/config.fish
WORKDIR /home/dev

CMD fish