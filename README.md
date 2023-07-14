# Azure App Service (Python) Practice

## Setup
- 作業端末に Azure CLI をインストールしてログインする
  - `az login`
- Azure Container Registry でレジストリを作成する
  - 「アクセスキー」で「管理者ユーザー」を有効にする (しないと App Service からデプロイ出来ない)
- App Service を作成する
  - ACR からデプロイするように設定しつつ作成する
  - リポジトリを作成しておく (下記 Deploy セクションの 1. を参照)

## Deploy (with Azure CLI)

### 1. イメージをビルドして ACR にプッシュ
``` console
$ az acr build --registry ${ACR_REGISTRY_NAME} --image ${ACR_IMAGE_NAME} .
```

### 2. デプロイ
App Service の設定が正しくできていれば、push した時点で自動でデプロイされるっぽい...？