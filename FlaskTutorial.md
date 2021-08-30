# Flaskの開発環境の構築と動作確認
## 開発環境の構築(makeコマンド)
[sakeリポジトリ](https://github.com/zemi-team2/sake)のREADMEと同様の手順です。

### １．リポジトリのクローン
```shell
git clone git@github.com:zemi-team2/sake.git
```

### ２．開発環境の初期化
```shell
make init
```

### ３．開発環境の起動
```shell
make upd
```
### 補足
* makeコマンドが使えない場合は[sakeリポジトリ](https://github.com/zemi-team2/sake)のREADMEを参照して構築してください。
* 2021年8月27日に作成した環境にはFlaskが導入されていないので、Flaskを使用する場合は再度、環境を作り直してください。

## 動作確認
### １．開発コンテナのターミナルに接続
``` shell
make sh
```
or
``` shell
docker exec -it python3 bash
```
### ２．Flaskのサンプルプログラムを起動
``` shell
python /sake/backend/src/sample_flask.py
```

正しく起動すると以下のように表示されます。  

![terminal](https://raw.githubusercontent.com/zemi-team2/docs/images/flask_terminal_output.jpg)

### ３．ブラウザで動作確認
インターネットブラウザで`127.0.0.1:8000`と入力して以下のように表示されれば、正しく動作しています。  

![browser](https://raw.githubusercontent.com/zemi-team2/docs/images/flask_browser_output.jpg)

## 補足
今回、Flaskを起動するために開発環境では8000番ポートを使用しています。  
そのため、すでにjupyterなどでポートを使用している場合、コンテナの開発環境の起動ができないことがあります。  
開発環境を起動した際に以下のエラーが出た場合はポートを変更するので連絡してください。

### エラー
`Error response from daemon: driver failed programming external connectivity on endpoint python3 (df3e45da5df4a8382f4ad5d3493611b98491300e1353f9b690922a162616e8b4): Bind for 0.0.0.0:8000 failed: port is already allocated`