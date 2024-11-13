# ビルド方法

はい、**EAS (Expo Application Services)** を使用することで、**Android** と **iOS** の両方でビルドすることができます。EAS は Expo の公式ツールで、React Native アプリを簡単にビルド、デプロイ、そしてアプリストアに公開するためのサービスです。

以下は、**EAS**を使って、Android と iOS のアプリをビルドするためのステップです。

## 1. **EAS CLI のインストール**

まず、EAS CLI をインストールします。これにより、コマンドラインからビルドやデプロイを簡単に行えます。

```bash
npm install -g eas-cli
```

## 2. **Expo プロジェクトの設定**

`app.json`に、ビルド設定を追加します。特に iOS と Android の設定を確認しましょう。

### `app.json`の設定例

- **`bundleIdentifier`** は iOS のユニークな識別子です。
- **`package`** は Android のユニークな識別子です。

## 3. **EAS ビルドの準備**

EAS でビルドを開始する前に、いくつかの設定を行います。

1. **EAS プロジェクトを作成**:

   初めて EAS を使う場合、Expo のアカウントでログインし、プロジェクト ID を設定します。

   ```bash
   eas login
   ```

2. **EAS のビルド設定を初期化**

   プロジェクトのルートディレクトリで以下のコマンドを実行し、`eas.json`を生成します。

   ```bash
   eas build:configure
   ```

## 4. **ビルドの開始**

iOS と Android のビルドを個別に行うことができます。

### Android のビルド

Android のビルドを開始するには、以下のコマンドを実行します。

```bash
eas build --platform android
```

このコマンドを実行すると、EAS がビルドを開始し、ビルドが完了すると APK または AAB ファイルをダウンロードできます。

### iOS のビルド

iOS のビルドも同様に、以下のコマンドで行います。

```bash
eas build --platform ios
```

このコマンドを実行すると、iOS のビルドが開始され、完了後に`.ipa`ファイルが生成されます。

## 5. **ビルドのステータス確認**

ビルドが完了するまで、進行状況を確認することができます。ビルドが完了すると、ダウンロードリンクが表示されます。

```bash
eas build:list
```

これにより、ビルドの進捗状況や、完了したビルドの一覧を確認できます。

## 6. **ビルド後の処理**

ビルドが完了したら、生成された `.apk` や `.ipa` ファイルを利用して、次のステップに進むことができます。

- **Android**の場合は、Google Play にアップロードできます。
- **iOS**の場合は、Apple の App Store にアップロードするために**Transporter**を使ったり、**App Store Connect**から直接アップロードします。

### 7. **EAS の追加設定**

必要に応じて、ビルド設定を`eas.json`ファイルでカスタマイズすることもできます。例えば、iOS ビルドの署名や Android ビルドの設定などを指定できます。

- **`buildType`**: `release`、`debug`、`simulator`、`app-bundle`などのビルドタイプを指定できます。

---

EAS を使うことで、ビルドの自動化や管理が簡単にでき、特に Expo で React Native アプリを開発している場合には非常に便利です。
