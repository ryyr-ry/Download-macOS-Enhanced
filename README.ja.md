<div align="right">

[English](./README.md) | [日本語](./README.ja.md)

</div>

# Download-macOS-Enhanced

Appleのサーバーから直接macOSインストーラーを生成するためのGitHub Actionワークフローです。

このプロジェクトは、[Comp-Labs/Download-macOS](https://github.com/Comp-Labs/Download-macOS) に改変を加えたものです。

## ⚠️ 重要

このワークフローは、実行に多くのリソースを消費します。単一のリポジトリに負荷が集中することを避けるため、**このリポジトリを直接フォークしないでください。** 代わりに、以下の手順に従って、あなた自身のアカウントにテンプレートから新しいリポジトリを作成してください。また、短時間に何度もこのワークフローを実行することは避けてください。

GitHub Actionsの利用料金に関する詳細は、[公式ドキュメント](https://docs.github.com/ja/billing/managing-billing-for-github-actions/about-billing-for-github-actions)をご参照ください。

## 🚀 利用開始までの手順

### ステップ1: このテンプレートからあなたのリポジトリを作成する

1.  ページ上部にある緑色の **`Use this template`** ボタンをクリックし、**`Create a new repository`** を選択します。
2.  新しく作成するリポジトリの名前を決めます（例: `my-macos-factory`）。
3.  **`Create repository`** ボタンをクリックします。これにより、あなたのGitHubアカウントにこのプロジェクトのコピーが作成されます。

### ステップ2: （重要）リポジトリ変数を設定する

ワークフローの実行の前に、まずあなたのリポジトリ名とユーザー名を変数として登録してください。

1.  作成したリポジトリで **`Settings`** タブに移動します。
2.  左側のメニューで **`Secrets and variables`** > **`Actions`** を選択します。
3.  **`Variables`** タブに切り替え、**`New repository variable`** ボタンを押します。
4.  以下の**2つの変数**を正確に作成してください。

    *   **1つ目:**
        *   **Name:** `REPO_OWNER`
        *   **Value:** `あなたのGitHubユーザー名` (例: `your-id`)
    *   **2つ目:**
        *   **Name:** `REPO_NAME`
        *   **Value:** `あなたがステップ1で付けたリポジトリ名` (例: `my-macos-factory`)

### ステップ3: （推奨）選択肢リストの更新機能を有効にする

macOSのダウンロードリストを簡単に更新する機能を使う には、ワークフローがあなたのリポジトリに変更をプッシュ（書き込み）するためのトークン（Personal Access Token）が必要です。

1.  **Personal Access Token (PAT) を作成します。**
    *   [こちらのGitHubガイド](https://docs.github.com/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic)に従い、**Classic**タイプのPATを作成してください。
    *   **`Select scopes`**（権限の選択）では、**`repo`** と **`workflow`** の2つのチェックボックスを必ずオンにしてください。
    *   生成されたトークン（`ghp_...`から始まる文字列）は、**一度しか表示されません。** 必ず安全な場所に保存してください。

2.  **PATをリポジトリのSecretに登録します。**
    *   あなたのリポジトリで `Settings` > `Secrets and variables` > `Actions` に移動します。
    *   **`Secrets`** タブが開いていることを確認し、**`New repository secret`** ボタンをクリックします。
    *   **Name** に `AUTO_COMMIT_TOKEN` と入力します。
    *   **Secret** に、先ほどコピーしたPATの文字列を貼り付けます。
    *   `Add secret` をクリックして保存します。

これで設定は以上です。

## ⚙️ ワークフローの使い方

*   **選択肢リストを更新したい場合:**
    `Actions`タブから `Update macOS Installer Options` ワークフローを手動で実行してください。設定が正しければ、このワークフローが`generate-installer.yml`の選択肢を更新し、自動でコミットを行います。
    
    *(注: `update-options.yml`内の`schedule`設定のコメントアウトを外し、この更新を毎日自動で実行することも可能です。ただし、GitHub Actionsの制限にはお気を付けください。)*

*   **インストーラーを生成したい場合:**
    `Actions`タブから `Generate and Release macOS Installer` ワークフローを、リストからダウンロードするバージョンを選択、または手動で入力し、生成するファイルの種類を選択したうえで実行してください。

## 💡 ダウンロードについて

生成されたファイルをダウンロードする際、ブラウザの標準機能では時間がかかることがあります。より高速で安定したダウンロードのために、[aria2](https://github.com/aria2/aria2)のようなダウンローダーを使い、複数の接続で並列ダウンロードを行うことをお勧めします。

## ⚖️ 免責事項

このプロジェクトは教育的および実験的な目的で提供されており、このワークフローを使用・実行したことによるいかなる結果についても作成者は一切の責任を負いません。ご自身の責任において、過度な使用を避けてご利用ください。