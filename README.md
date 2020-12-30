# template__docker-laravel
## 概要
dockerを用いてlaravelを動かすための環境リポジトリ
| 項目 | バージョン |
| --- | --- |
| Laravel | 6.20.8 |
| MySQL | 5.7.31 |

## Set Up

### リポジトリをクローンする
```bash
$ git clone git@github.com:ToukaHanetsuki/template__docker-laravel.git
$ cd template__docker-laravel
```

### コンテナの作成・起動
```bash
$ docker-compose up -d --build
```

| オプション | 説明 |
| --- | --- |
| -d | バックグラウンドで実行 |
| --build | 変更点があればビルド、なければキャッシュを利用する |

### コンテナへ入る
```bash
$ docker-compose exec app bash
```

### Laravelのvendorをインストール
```bash
$ composer install # コンテナ内で実施
```

### .envの用意
```bash
$ cp .env.example .env # コンテナ内で実施
$ php artisan key:generate # APP_KEYの作成
```

### migrationの実施
```bash
$ php artisan migrate # コンテナ内で実施
```

## Command
### mysqlへの接続
```bash
$ docker-compose exec db bash -c 'mysql -u${MYSQL_USER} -p${MYSQL_PASSWORD} ${MYSQL_DATABASE}'
```