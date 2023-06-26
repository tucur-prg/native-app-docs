Storage
=====

## keyStore

KeyStoreに保存した鍵は、以下のような操作で消えてしまいます。鍵が取得できない場合はユーザに再度ログイン操作を要求する必要があります。  

* アプリのアンインストール
* キー使用を承認するうえでユーザー認証を要求する場合は、承認内容に応じてキーが無効化されるタイミングは異なります。以下に概要を示しますが、詳細についてリンク先のドキュメントを確認してください。
  * ユーザ認証に基づいて、一定期間、キーを使用することを承認する
    * セキュアロック画面が無効化された場合や強制的にリセットされた場合
  * ユーザ認証によって、キーと暗号処理の組み合わせを個別に承認する（指紋認証の場合のみ利用可能）
    * 新しい指紋が登録された場合やすべての指紋の登録が抹消された場合

cf. [ログイン資格情報の管理 | Fintan » Mobile App Development](https://fintan-contents.github.io/mobile-app-crib-notes/reference/auth/manage-credentials/)  

### 暗号化キー

[Android Keystoreの概要 - Qiita](https://qiita.com/masaki_shoji/items/2ada7a182677a98d1cf9)  


## SharedPreferences

どうやらAndroidの設定で「Googleバックアップ」→「自動復元」みたいな設定項目をONにしているとアプリを削除してもSharedPreferencesがGoogleのサーバーに保存（？）されて、同じアプリを再度インストールすると設定が自動復元されてしまうらしいです。  

cf. [AndroidアプリをアンインストールしてもSharedPreferencesが消えない → 自動復元をOFFにすると消える](https://penpen-dev.com/blog/sharedpreferences-backup/)  
