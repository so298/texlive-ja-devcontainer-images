# texlive-ja devcontainer

texlive-jaをdevcontainerで使うための`.devcontainer/`のテンプレートとDockerイメージのビルドファイルです。

## devcontainer用のimageについて

- [paperist/texlive-ja](https://hub.docker.com/r/paperist/texlive-ja)をベースにしています。
- github actionsを利用し、月に1回ビルドするようにしています。

## `.devcontainer/` ディレクトリについて

- テンプレートとして利用するときには`.devcontainer/`ディレクトリをコピーして利用します。
