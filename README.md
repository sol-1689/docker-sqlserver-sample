# 起動方法
「start.bat」を実行。
「stop.bat」の実行で停止。


# ファイル説明

・docker-compose.yml
コンテナは１つだが設定項目を見やすくするため、docker-composeにてコンテナを立ち上げている。

・sqlserver/init-data
DDL文やデータのInsert文を記述したsqlファイルの配置場所

・sqlserver/Dockerfile
SQLServerコンテナ。SQLServerの起動と、シェルスクリプトに処理初期データの登録処理を行っている。

・sqlserver/entrypoint.sh
コンテナ起動時に実行されるシェルスクリプト。
DockerfileのCMDにて指定されている。

・sqlserver/start-up.sh
sqlファイルからDDL文の実行と、データのInsert処理を実行するシェルスクリプト。
entrypoint.shから呼び出される。

・sqlserver/wait-for-it.sh
SQLServerが起動し、接続を受け付ける状態になるまでポーリングして待機するためのシェルスクリプト。
以下から拾ってきたもの。
https://github.com/vishnubob/wait-for-it

