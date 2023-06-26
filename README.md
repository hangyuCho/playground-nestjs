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

## Description

### NestJs とは

### NestJs/cli インストール

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

### NestJs の基本構成

> - eslintrc.js
> - prettierrc
> - nest-cli.json
>   1.  nest プロジェクトを為細かい設定を定義する json ファイル
> - tsconfig.json
>   1.  typescript のコンパイルの設定を定義
> - tsconfig.build.json
>   1.  tsconfig.json の１種類であり、build 時必要な設定を定義
>   2.  "excludes"にはビルド時除外するファイルを指定することができる。
> - package.json

### NestJs のロジックの流れ

module -> xxx-module -> xxx-controller -> xxx-service

### NestJs モジュール

フロンドから request がある時一番早めに辿り着く場所

### Board の Module 生成

nest はコマンドでファイルを自動生成する機能がついている

```shell
nest g module boards
```

### NestJs の Controller とは？

> ブラウザから request がきたら
> http メソッドにより request を分配し処理を返す処理を行う

- @(デコレーター)
- handler(ハンドラー) - メソッド

### Board の Controller 生成

### Nestjs Providers, Service とは

---

---

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
