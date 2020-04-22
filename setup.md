# VSCodeでrails環境を作る

## 前提条件
- 以下の基礎知識があること。
  - Docker
  - Docker Compose
  - Remote Containers(VSCode拡張)  
  - Ruby on Rails
- 以下がインストール済であること。
  - Docker Desktop
  - VSCode
  - Remote Containers(VSCode拡張)

## ファイルを書き換える
Containerを作るために必要なファイルを用途に合わせて書き換える。特に以下ファイルの「myapp」と記載された箇所は、作りたいrailsアプリ名に変更すること。
- .devcontainer/devcontainer.json
- .devcontainer/docker-compose.yml

## Containerを作る
railsアプリの開発環境であるContainerを作る。  
VSCodeでアプリのルートディレクトリをContainerにアタッチすることで、WindowsとContainerの双方でファイル操作が可能になる。アタッチ時にContainerが存在しなければ、VSCodeがDocker Composeで自動作成する。
1. VSCode画面左下の「リモートウィンドウを開く」をクリックする。
2. 「Remote-Containers: Reopen in Container」をクリックする。

## railsアプリを作る
```
rails new . --database=postgresql
```

## DBを作る
railsには、config/database.ymlの内容でDBを作成するコマンドがある。それを実行する。
1. database.ymlを編集する。username, password, host, portを書き換える。
2. 以下コマンドを実行する。
```
rails db:create
```