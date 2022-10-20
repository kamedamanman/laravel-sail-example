# laravel-sail-example

Laravel開発環境構築

```bash
PHP 8.1.11
Composer version 2.4.3
```

## 新規プロジェクト作成

``` bash
curl -s https://laravel.build/laravel-sail-example | bash

# laravel-sail-exampleの部分は任意のプロジェクト名

# laravel-sail-exampl起動
cd laravel-sail-example && ./vendor/bin/sail up

# laravel-sail-example落とす
./vendor/bin/sail down

```

## エイリアス設定

~/.zshrc や ~/.bashrc へ追加

``` bash
alias sail='[ -f sail ] && sh sail || sh vendor/bin/sail'
```

# Elastic Beanstalkへデプロイ

1. Elastic Beanstalkのコンソールで空のアプリケーションと環境を作成
2. 表示確認 403でOK
3. Elastic BeanstalkのコンソールでRDSを作成(ユーザとパスワードは.envから確認)

## .env.prod を編集

DB_HOSTをで作成したRDSに変更

## .ebextensions

起動時に実行するコマンド

## .platform

サーバ設定ファイル
Naginxの設定ファイルを追加

## Zip化コマンド

よしなに除外ファイルを追加

``` bash
zip -r dest.zip ./ -x '*vendor*' '*node_modules*'
```

## zipファイルをAWSコンソール上でデプロイ