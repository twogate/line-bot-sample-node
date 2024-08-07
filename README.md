# LINE Bot開発のためのサンプルコード

# 準備する

`.env.sample` ファイルをコピーして `.env` ファイルにしてください。
`.env` ファイルに、LINE Developer Consoleから取得した、「チャネルシークレット（チャネル基本設定内）」と「チャネルアクセストークン（Messaging API設定内）」を貼り付けます。

## ngrokに無料登録する

ngrokのアカウントを作成してください。

https://dashboard.ngrok.com/signup

## ngrokにログインする

[Authtokenの取得画面](https://dashboard.ngrok.com/get-started/your-authtoken)より、Authtokenをコピーして下記のコマンドを実行する。
これにより、コマンドライン上でもngrokにログインできます。

```
ngrok config add-authtoken コピーしたAuthtoken
```

# 実行する

下記のコマンドでプログラムを実行します。
このコマンドを実行すると、index.mjsのプログラムが起動します。
`Ctrl+C`でサーバを停止できます。

```
npm install
npm run start
```


次に、もう1つターミナルを開いて、下記のコマンドでngrokを起動します。
`Ctrl+C`でサーバを停止できます。

```
ngrok http 8080
```

起動したら、ForwardingにあるhttpsではじまるURLにアクセスすると、「Hello」と表示されたら完了です。
自分のローカルサーバが、インターネットに公開された状態になりました。

このURLに、`/webhook` をつけて、LINE Developer consoleのWebhook URLとして設定してください。
