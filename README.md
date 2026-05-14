# カレー厨房 スパイスガーデン — Git 入門ハンズオンプロジェクト

このリポジトリは、**Git の使い方を実例を通して学ぶ**ためのハンズオン用サンプルプロジェクトです。

架空のカレー屋さん「スパイスガーデン」のホームページを実際に操作しながら、  
「ファイルを変更する → 変更を記録する → 共有する」という **Git の基本的なワークフロー** を体験できます。  
コマンドの意味を理解しながら手を動かすことで、実務でも通用する Git の感覚を身につけることを目的としています。

---

## 目次

1. [事前に必要なもの](#1-事前に必要なもの)
2. [Git のインストール確認](#2-git-のインストール確認)
3. [GitHub アカウントの作成](#3-github-アカウントの作成)
4. [リポジトリをクローンする](#4-リポジトリをクローンする)
5. [依存パッケージのインストール](#5-依存パッケージのインストール)
6. [開発サーバーの起動](#6-開発サーバーの起動)
7. [基本的な Git の流れ](#7-基本的な-git-の流れ)

---

## 1. 事前に必要なもの

| ツール | 説明 |
|--------|------|
| **Git** | バージョン管理システム |
| **Node.js** (v18 以上) | JavaScript の実行環境 |
| **VS Code** (推奨) | コードエディター |

### Node.js のインストール

[https://nodejs.org/](https://nodejs.org/) にアクセスし、**LTS 版**をダウンロード・インストールしてください。

---

## 2. Git のインストール確認

ターミナル（Mac: Terminal、Windows: Git Bash）を開き、以下を入力してください。

```bash
git --version
```

`git version 2.x.x` のように表示されれば OK です。

表示されない場合は [https://git-scm.com/](https://git-scm.com/) からインストールしてください。

### Git の初期設定（初回のみ）

Git を初めて使う場合は、自分の名前とメールアドレスを登録します。

```bash
git config --global user.name "あなたの名前"
git config --global user.email "you@example.com"
```

---

## 3. GitHub アカウントの作成

[https://github.com/](https://github.com/) にアクセスし、アカウントを作成してください（無料）。

---

## 4. リポジトリをクローンする

「クローン」とは、GitHub 上のリポジトリを自分のパソコンにコピーすることです。

```bash
git clone https://github.com/Gifted-People-Support-Association/git-basic-example.git
```

クローンが完了したら、プロジェクトのフォルダーに移動します。

```bash
cd git-basic-example
```

---

## 5. 依存パッケージのインストール

このプロジェクトは Vite を使っています。必要なパッケージをインストールします。

```bash
npm install
```

`node_modules` フォルダーが作成されれば成功です。

---

## 6. 開発サーバーの起動

以下のコマンドを実行すると、ブラウザでホームページを確認できます。

```bash
npm run dev
```

ターミナルに表示される URL（例: `http://localhost:5173`）をブラウザで開いてください。  
ファイルを変更すると、ブラウザが自動で更新されます。

サーバーを止めるときは `Ctrl + C` を押します。

---

## 7. 基本的な Git の流れ

ファイルを変更して Git で管理するまでの基本的な手順です。

### ① 変更状態を確認する

```bash
git status
```

変更・追加されたファイルが一覧表示されます。

### ② 変更をステージに追加する

特定のファイルを追加する場合：

```bash
git add index.html
```

すべての変更をまとめて追加する場合：

```bash
git add .
```

### ③ コミットする

「コミット」とは、ステージに追加した変更を記録することです。  
`-m` の後にどんな変更をしたかメッセージを書きます。

```bash
git commit -m "トップページのデザインを修正"
```

### ④ GitHub に反映する（プッシュ）

```bash
git push origin main
```

これで GitHub のリポジトリに変更が反映されます。

### ⑤ GitHub から最新の変更を取得する（プル）

他の人が変更を加えた場合は、以下で最新の状態を取得できます。

```bash
git pull origin main
```

---

## よく使う Git コマンド一覧

| コマンド | 内容 |
|----------|------|
| `git status` | 変更状態を確認 |
| `git add .` | すべての変更をステージに追加 |
| `git commit -m "メッセージ"` | 変更をコミット |
| `git push origin main` | GitHub に反映 |
| `git pull origin main` | GitHub から最新を取得 |
| `git log --oneline` | コミット履歴を確認 |
| `git diff` | 変更箇所の差分を表示 |

---

## プロジェクト構成

```
git-basic-example/
├── index.html        # メインの HTML ファイル
├── package.json      # プロジェクト設定・スクリプト
├── pnpm-lock.yaml    # パッケージのバージョン固定ファイル
└── src/
    ├── main.js       # JavaScript エントリーポイント
    ├── style.css     # スタイルシート
    └── assets/       # 画像などのアセット
```
