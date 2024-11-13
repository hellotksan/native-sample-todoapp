# プロジェクトにアップロードする方法

`expo publish`は、以前の Expo CLI では使われていましたが、現在は`eas update`に置き換えられています。
これにより、EAS（Expo Application Services）を使用してプロジェクトを更新・デプロイする方法が推奨されています。

## `expo publish`の代わりに`eas update`を使う方法

以下の手順で、EAS Update を使用してプロジェクトをアップロードし、Expo の Web ダッシュボードから確認できるようにします。

1. **EAS CLI のインストール**
   まず、EAS CLI がインストールされていない場合は、インストールします。

   ```bash
   npm install -g eas-cli
   ```

2. **EAS アカウントへのログイン**
   EAS CLI にログインするため、以下のコマンドを実行します。

   ```bash
   eas login
   ```

   ここで、Expo アカウントのユーザー名とパスワードを入力します。

3. **EAS Update の実行**
   プロジェクトをアップロードするために、`eas update`を使います。以下のコマンドを実行します。

   ```bash
   eas update --branch <branch-name>
   ```

   - `<branch-name>`: 任意のブランチ名（例えば、`default`や`production`など）を指定します。

   これで、EAS Update を使用して Expo プロジェクトがアップロードされ、Expo の Web ダッシュボードから確認できるようになります。

## **まとめ**

- `expo publish`の代わりに、`eas update`を使用する必要があります。
- EAS CLI をインストールし、`eas login`でログイン後、`eas update --branch <branch-name>`でプロジェクトをアップロードします。

この方法で、Expo Web ダッシュボードにプロジェクトをアップロードし、ブラウザで確認できるようになります。
