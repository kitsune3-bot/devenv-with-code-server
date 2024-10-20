開発環境 with code-server
===

このリポジトリはcode-serverで開発環境を作成するテンプレートです。  
linuxserver.ioをベースに環境を構築します。


## コンテナ構成

- code-server: 開発環境
    - docker in docker環境構築済み
- ollama: LLMを使った支援に使用

## 導入手順

- mkcertで証明書を作成し、下記パスに保存
    - certs/cert.crt
    - cert.key
- 作成した公開鍵をクライアントマシンにインストール
- コンテナ起動
    ```
    docker compose build --no-cache
    docker compose up -d
    ```

## ollamaのイメージ追加
    下記のように実行
    ```
    docker compose exec ollama ollama pull llama3.2-3b
    ```

## TODO
- nvidia toolkitへの対応