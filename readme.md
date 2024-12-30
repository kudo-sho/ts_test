## はじめに
これはTypeScriptの練習用プロジェクトです。

## 使い方

### 始め方

#### 1. node.js をインストール

#### 2. プロジェクト作成

  以下コマンド実行
  ```bash
  # package.json を作成
  npm init -y

  # typescript をインストール
  npm install typescript --save-dev

  # node.d.ts をインストール
  npm install @types/node --save-dev

  # tsconfig.json を作成
  npx tsc --init --rootDir src --outDir lib --esModuleInterop --resolveJsonModule --lib es6,dom --module commonjs
  ```

#### 3. 追加設定を行う

  以下コマンド実行
  ```bash
  # TypeScriptをコンパイルし、Node.jsで実行するためにts-nodeをインストールする
  npm install ts-node --save-dev

  # ファイルが変更されるたびにts-nodeを再起動するためにnodemonをインストールする
  npm install nodemon --save-dev
  ```

  package.jsonのスクリプトブロックに以下の記述を追加する
  ```json
    "scripts": {
      "start": "npm run build:live",
      "build": "tsc -p .",
      "build:live": "nodemon --watch 'src/*.ts' --exec \"ts-node\" src/index.ts"
    },
  ```

#### 4. srcとlibフォルダを作成する

#### 5. src/index.ts を作成する