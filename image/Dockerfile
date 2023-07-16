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
  git

RUN curl -sL https://raw.githubusercontent.com/microsoft/vscode-dev-containers/main/script-library/common-debian.sh | bash -

# change default shell
RUN chsh -s /bin/zsh $USERNAME

USER $USERNAME

ENTRYPOINT [ "/bin/zsh" ]
