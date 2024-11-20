## Build tex-fmt
FROM rust:1.82-slim AS tex-fmt-builder
WORKDIR /work

# install stable version of tex-fmt
RUN cargo install tex-fmt

## Build main image
FROM paperist/texlive-ja:debian

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    wget \
    git \
    zsh

# Dependencies for latexindent
RUN apt-get install -y --no-install-recommends \
    libfile-homedir-perl \
    libyaml-tiny-perl
RUN tlmgr update --self
RUN tlmgr init-usertree && tlmgr install latexindent

COPY --from=tex-fmt-builder /usr/local/cargo/bin/tex-fmt /usr/local/bin/tex-fmt

# change default shell
RUN chsh -s /bin/zsh $USERNAME

USER $USERNAME

ENTRYPOINT [ "/bin/zsh" ]