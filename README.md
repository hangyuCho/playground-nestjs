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

```shell
# nest: nestcliを使います
# g : generate(生成)
# controller : controllerを生成
# boards : controllerの名称
# --no-spec : テストコードを生成しない
nest g controller boards --no-spec
```

### Nestjs Providers, Service とは

DB のデータ取得やビジネスロジックを担当

```shell
nest g service boards --no-spec
```

@Injectable：他のコンポーネントからこのサービスを使えるようにしてくれるデコレーター
(DI の概念)

providers とは

- nestjs の基本クラス
  - service
  - repository
  - factory
  - helper
- オブジェクトを自動的に割当可能(DI)
- nestjs runtime に委任できるようです。

- service とは サービスはソフトウエアの開発の中でよく使われる概念である。
- @Injectable デコレーターに囲まれモジュールに提供され、このサービスインスタンスはアプリケーションの全体で使われる。

サービスはコントローラーからデータの検証を行ったり、DB へアイテムを生成するなどの作業を行う部分らしいです。w

contoller から service を呼び出すためには、constructor の変数でサービスオブジェクトをもらえるが、その方法は以下のようになる。

```javascript
boardsService: BoardsService;

constructor(boardsServices: BoardsService) {
  this.boardsService = boardsService;
}
```

↓ に省略もできる

```typescript
constructor(private boardsServices: BoardsService) { }
```

## crud

## Board Service の作成

### すべての投稿を取得するサービスを作成する

### ボードモデルを定義する

投稿作成機能の前処理

- 投稿について必要な物が何かを定義します。
- 例) Id、名称、説明など
  > board Model ファイル生成 -> board.model.ts

モデルを定義するためには
class / interface を利用

> interface -> 変数のタイプのみチェック
> class -> 変数のタイプチェック、インスタンスの生成可能

board の構造を定義

> interface の場合

board.model.ts 生成 -> interface で構造定義

```typescript
export interface Board {
  id: string;
  title: string;
  description: string;
  status: ;
}
```

Board の status とは？

この投稿が公開・非公開を区分できるようになる列挙系の enum(enumeration)を使用。

```typescript
export enum BoardStatus {
  PUBLIC = 'PUBLIC',
  PRIVATE = 'PRIVATE',
}
```

### 投稿を作成する（サービス部）

### 投稿を作成する(Controller 部分)

### Data Transfer Object(DTO)

### 投稿生成のための DTO

### ID で特定の投稿を取得する

### ID で特定の投稿を削除する

### 特定の投稿のステータスを更新

## NestJS Pipes

### パイプによる検証

### 特定の投稿が見つからなかった場合の結果値の処理

### ない投稿を削除しようとした結果の値の処理

### カスタムパイプによる検証

## PostgresSQL のインストール

### DB 関連

### TypeORM の利用

### 投稿用のエンティティを作成する

### リポジトリの作成

## データベースのためのソースコードの整理

### ID を使用して特定の投稿を取得する

### 投稿を作成する

### 投稿を削除する

### 投稿ステータスを更新する

### すべての投稿を取得

## 認証機能実装のための準備

### 会員登録機能の実装

### ユーザーデータの検証

### ユーザー名にユニークな値を与える

### パスワードを暗号化する（説明）

### パスワードを暗号化する（ソースコードの実装）

### ログイン機能の実装

### JWT について

### JWT を使用してトークンを生成する

### Passport、Jwt を使用してトークン認証後にユーザー情報を取得する

### カスタムデコレータを作成する

### 認証されたユーザーだけが投稿を見て書くことができます

## ユーザーと投稿の関係を形成する

### 投稿を作成するときにユーザー情報を入れる

### そのユーザーの投稿のみを取得する

### 自分が作成した投稿を削除する

## ログについて

## 設定(Configuration)とは？

### 設定適用

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
