# texlive-ja devcontainer

texlive-jaをdevcontainerで使うためのDockerイメージのビルドファイルです。

## devcontainer用のimageについて

- [paperist/texlive-ja](https://hub.docker.com/r/paperist/texlive-ja)をベースにしています。
- github actionsを利用し、月に1回ビルドするようにしています。

## 利用可能なタグ

### `minimal`

- `paperist/texlive-ja`のdebianイメージをベースに、latexindentのみを追加しています

### `latest`, `extended`

- `minimal`に加えて、複数種類のパッケージを追加しています

## このimageを利用したdevcontainerのテンプレートについて

[so298/texlive-ja-devcontainer-template](https://github.com/so298/texlive-ja-devcontainer-template)を利用してください
