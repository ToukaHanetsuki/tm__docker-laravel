# template__docker-laravel

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

### Laravelのvendorをインストール
```
$ docker-compose exec app composer install
```

### .envの用意
```bash
$ cp .env.example .env
$ php artisan key:generate # APP_KEY=の作成
```

### migrationの実施
```bash
$ php artisan migrate
```