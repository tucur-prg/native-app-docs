Storage
=====

## KeyChain

1. アプリをアンインストールしても消えない

Keychainの情報はアプリをアンインストールしても消えないため、特に何もしない場合は再インストール後も認証状態が引き継がれることになります。  

インストール後に必ず認証が必要な場合は、UserDefaultsにフラグを設けてインストールされてからのログイン実績を管理するなどの実装が必要になります。  

2. iCloudで同期される

Keychainに保存した情報は、iCloud同期により同じAppleIDでログインしている別の端末に同期されます。さらに、iCloud同期のタイミングは不定期のため、いつバックアップ/同期されるか分かりません。  

一台でのみ利用されることが前提の情報を安易にKeychainに保管してしまうと、複数台で同時に利用されて予期しない不整合が発生してしまう可能性があります。例えば、アクセストークンやリフレッシュトークンを一度しか利用できないように制限している場合などが該当します。  

cf. [ログイン資格情報の管理 | Fintan » Mobile App Development](https://fintan-contents.github.io/mobile-app-crib-notes/reference/auth/manage-credentials/)  
