# texlive-ja devcontainer

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/so298/texlive-ja-devcontainer-images/ci.yml)

texlive-ja を devcontainer で使うための Docker イメージのビルドファイルです。

## devcontainer 用の image について

- [paperist/texlive-ja](https://hub.docker.com/r/paperist/texlive-ja)をベースにしています。
- github actions を利用し、月に 1 回ビルドするようにしています。

## 利用可能なタグ

基本的に`latest`の使用を推奨します。

### `minimal`

![Docker Image Size Minimal](https://img.shields.io/docker/image-size/so298go/texlive-ja-devcontainer/minimal)

- `paperist/texlive-ja`の debian イメージをベースに、latexindent のみを追加しています

```bash
# From Docker Hub
docker pull so298go/texlive-ja-devcontainer:minimal

# From GitHub Container Registry (Login required)
docker pull ghcr.io/so298/texlive-ja-devcontainer:minimal
```

### `latest`, `extended`

![Docker Image Size Latest](https://img.shields.io/docker/image-size/so298go/texlive-ja-devcontainer/latest)

- `minimal`に加えて、複数種類のパッケージを追加しています

```bash
# From Docker Hub
docker pull so298go/texlive-ja-devcontainer:latest

# From GitHub Container Registry (Login required)
docker pull ghcr.io/so298/texlive-ja-devcontainer:latest
```

## この image を利用した devcontainer のテンプレートについて

[so298/texlive-ja-devcontainer-template](https://github.com/so298/texlive-ja-devcontainer-template)を利用してください
