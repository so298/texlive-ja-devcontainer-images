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

# install dependencies
RUN apt-get install -y --no-install-recommends \
    libfile-homedir-perl \
    libyaml-tiny-perl \
    libfontconfig1

RUN tlmgr update --self
RUN tlmgr init-usertree && \
    tlmgr install \
        latexindent \
        collection-latexrecommended \
        collection-bibtexextra \
        collection-luatex \
        algorithms \
        algorithmicx \
        algorithm2e \
        newtx \
        inconsolata \
        opensans \
        boondox \
        latexmk \
        acmart \
        libertine \
        mweights \
        realscripts && \
    mktexlsr


# change default shell
RUN chsh -s /bin/zsh $USERNAME

USER $USERNAME

ENTRYPOINT [ "/bin/zsh" ]
