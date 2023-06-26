# Playground By Nestjs

> nodejs のフレームワークの中で生産性が高い物がある。。らしく。試してみます。

> 最近 node package manager (NPM)の方はコンソールがあまり綺麗じゃないので
> yarn を使ってたんですが、yarn よりも綺麗な物を見つかってしまいました。
> 「pnpm」でございます。

```shell
# pnpmインストール
npm install -g pnpm
# pnpmのセットアップ
pnpm setup
# セットアップの内容をshellに反映
source ~/.zshrc
```

### nest cli のインストール

```shell
pnpm i -g @nestjs/cli
```

> ![](./init1.png)

### nestjs のプロジェクト生成

```shell
# プロジェクトのフォルダを生成
mkdir playground-nestjs

# 生成したフォルダの中へ移動
cd playground-nestjs

# nestjsのプロジェクト生成
nest new .
```

> ![](./init2.png)

```shell

```

## Description

check in my
[Wiki by this project](https://github.com/hangyuCho)

## Installation

```bash
$ pnpm install
```

## Running the app

```bash
# development
$ pnpm run start

# watch mode
$ pnpm run start:dev

# production mode
$ pnpm run start:prod
```

## Test

```bash
# unit tests
$ pnpm run test

# e2e tests
$ pnpm run test:e2e

# test coverage
$ pnpm run test:cov
```

## License

[MIT licensed](LICENSE).
