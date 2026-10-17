# PR TIMES INTERN Challenge 総括


## 環境構築

dockerを使ったことがあったので特に困らず進めました。

- WSL2 + Docker Desktopで実行
- Docker Composeの`app`をPHP実装へ切り替え
- NginxではRuby用`default.conf`を退避し、PHP用`php.conf`を有効化
- `make init`で初期DB・ベンチマーク用画像を取得

ここでlocalhostを開いてしまうとエラーが出てきました。
localhostに表示されたエラーを見るとMySQLが接続受付を始める前にPHPが起動しているようなので、修正していきます。

## 初期スコア

- pass: true
- score: 0
- success: 321
- fail: 33

PHP版をDocker Composeで起動して計測した。
負荷テストではタイムアウトが発生したため、以降はボトルネックを調査して改善していきます。

C, C++, TSを読むことができる知識から、仮説を立てながらindex.phpを読んでいきます。