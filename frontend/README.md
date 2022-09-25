# frongend

DockerによるReact開発環境の立ち上げ。

## 立ち上げ方法

Dockerfileの10行目<br>

`command: sh -c "cd testapp && npm start"`

のtestappを[作成するプロジェクト名]に変更する。

以下コマンドを打ち、db_data, [作成するプロジェクト名]ディレクトリができていることを確認する。

```bash
docker-compose build
docker-compose run --rm react sh -c "npm install -g create-react-app && create-react-app [作成するプロジェクト名]"
```

typescriptを使用する場合は2つ目のコマンドを以下に変更する。

`docker-compose run --rm react sh -c "npm install -g create-react-app && create-react-app [作成するプロジェクト名] --template typescript"`

docker-composeをバックグラウンドで立ち上げる。(上記はプロジェクト立ち上げの最初だけ行う。立ち上げ後はここより下のコマンドを実行するだけでおけ。)

`docker-compose up -d`

コマンド実行後localhost:3000をブラウザで確認。反映されるまで数十秒かかる場合あり。