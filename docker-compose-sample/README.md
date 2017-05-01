# Docker

## Docker-compose.ymlに書かれているimageをpullする
`docker-compose pull`

## コンテナを作成、起動
`docker-compose up -d`

### その他コマンド
#### ダンプ
`docker exec [MySQLコンテナ] sh -c 'exec mysqldump --all-databases -uroot -p"$MYSQL_ROOT_PASSWORD"' > /some/path/on/your/host/all-databases.sql`