---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーのフル コントロールを維持しながら、機密性の高いデータを保護できます。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066860"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Microsoft 365 の二重キー暗号化

> *適用対象: Microsoft 365、Microsoft [365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)[、Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)の二重キー暗号化*
>
> *手順: [Windows 用 Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

二重キー暗号化 (DKE) は、2 つのキーを一緒に使用して、保護されたコンテンツにアクセスします。 Microsoft は 1 つのキーを Microsoft Azure に保存し、もう一方のキーを保持します。 Double Key Encryption サービスを使用して、キーの 1 つを完全に制御します。 Azure Information Protection 統合ラベル付けクライアントを使用して、機密性の高いコンテンツに保護を適用します。

二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートします。 これらの展開は、保護されたデータを保存する場所で暗号化されたデータが不透明なままに維持されるのに役立ちます。

既定のクラウドベースのテナント ルート キーの詳細については [、「Azure Information Protection](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)テナント キーの計画と実装」を参照してください。

## <a name="when-your-organization-should-adopt-dke"></a>組織が DKE を採用する必要が生じ

二重キー暗号化は、最も厳しい保護要件の対象となる最も機密性の高いデータを対象とします。 DKE は、すべてのデータを対象としているのではありません。 一般に、Double Key Encryption を使用して、データ全体の一部のみを保護します。 展開する前に、このソリューションでカバーする適切なデータを特定する上で注意が必要です。 場合によっては、Microsoft が管理するキーや BYOK を使用した Microsoft Information Protection など、ほとんどのデータに対して範囲を絞り込み、その他のソリューションを使用する必要があります。 これらのソリューションは、強化された保護と規制要件の対象ではないドキュメントに対して十分です。 また、これらのソリューションを使用すると、最も強力な 365 Office使用できます。DKE で暗号化されたコンテンツでは使用できないサービス。 次に例を示します。

- 添付ファイルの可視性を必要とするマルウェア対策とスパムを含むトランスポート ルール
- Microsoft Delve
- 電子情報開示
- コンテンツ検索とインデックス作成
- Office機能を含む Web アプリの作成

MIP SDK を介して DKE と統合されていない外部アプリケーションまたはサービスは、暗号化されたデータに対してアクションを実行できません。

Microsoft Information Protection SDK 1.7+ は、二重キー暗号化をサポートしています。SDK と統合するアプリケーションは、十分なアクセス許可と統合を適用して、このデータを理由にできます。

組織では、Microsoft 情報保護機能 (分類とラベル付け) を使用して機密データのほとんどを保護し、ミッション クリティカルなデータにのみ DKE を使用することをお勧めします。 二重キー暗号化は、金融サービスや医療などの厳しく規制された業界の機密データに関連します。

組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。

- すべての状況で、 *保護* されたコンテンツの暗号化を解除できるのは自分だけである必要があります。
- Microsoft が独自に保護されたデータにアクセスしたくはない。
- 地理的境界内にキーを保持する規制要件があります。 データの暗号化と暗号化解除のために保持するキーはすべて、データ センターで保持されます。

## <a name="system-and-licensing-requirements-for-dke"></a>DKE のシステム要件とライセンス要件

**Microsoft 365 の二** 重キー暗号化には、Microsoft 365 E5 が付属しています。 Microsoft 365 E5 ライセンスをお持ちない場合は、試用版にサインアップ [できます](https://aka.ms/M365E5ComplianceTrial)。 これらのライセンスの詳細については、セキュリティとコンプライアンスに関する [Microsoft 365 ライセンス ガイダンス&してください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

**Azure Information Protection**。 DKE は、区別ラベルで動作し、Azure Information Protection を必要とします。

DKE の感度ラベルは、デスクトップ アプリの [Office] リボンを通じてエンド ユーザーが使用できます。 保護されたドキュメントを保護して使用する各クライアント コンピューターに、これらの前提条件をインストールします。

**Microsoft Officeのエンタープライズ** バージョン *.12711 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) 用アプリ。

**Azure Information Protection 統合ラベル付けクライアント** バージョン 2.7.93.0 以降。 Microsoft ダウンロード センターから統合ラベル付けクライアントを [ダウンロードしてインストールします](https://www.microsoft.com/download/details.aspx?id=53018)。

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>DKE で保護されたコンテンツを保存および表示するためのサポートされている環境

**サポートされているアプリケーション**。 Word、Excel、PowerPoint を含む、Windows 上の[Microsoft 365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) Apps for enterprise クライアント。

**オンライン コンテンツのサポート**。 Microsoft SharePoint と OneDrive for Business の両方にオンラインで保存されているドキュメントとファイルがサポートされています。 暗号化されたコンテンツは電子メールで共有できますが、暗号化されたドキュメントとファイルをオンラインで表示できません。 代わりに、ローカル コンピューター上のデスクトップ アプリを使用して、保護されたコンテンツを表示する必要があります。

## <a name="overview-of-deploying-dke"></a>DKE の展開の概要

DKE をセットアップするには、次の一般的な手順に従います。 これらの手順を完了すると、エンド ユーザーは、二重キー暗号化を使用して機密性の高いデータを保護できます。

1. この記事の説明に従って DKE サービスを展開します。

2. 二重キー暗号化を使用してラベルを作成します。 [Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターの下の情報保護に移動し、二重キー暗号化を使用して新しいラベルを作成します。 「 [暗号化を適用するために、感度ラベルを使用してコンテンツへのアクセスを制限する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。

3. 二重キー暗号化ラベルを使用します。 データを保護するには、次のページの [Sensitivity] リボンから [Double Key Encrypted] ラベルをMicrosoft Office。

二重キー暗号化を展開するには、いくつかの手順を実行する方法があります。 この記事では、経験の少ない管理者がサービスを正常に展開できるよう、詳細な手順を示します。 この方法に問題が生じない場合は、独自の方法を選択できます。

## <a name="deploy-dke"></a>DKE の展開

この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。 別の場所に展開する場合は、独自の値を指定する必要があります。

二重 [キー暗号化の展開のビデオ](https://youtu.be/vDWfHN_kygg) を見て、この記事の概念の詳しい概要を確認してください。 ビデオが完成するのに約 18 分かかります。

次の一般的な手順に従って、組織の二重キー暗号化を設定します。

1. [DKE サービスの前提条件ソフトウェアをインストールする](#install-software-prerequisites-for-the-dke-service)
1. [二重キー暗号化 GitHub リポジトリを複製する](#clone-the-dke-github-repository)
1. [アプリケーション設定の変更](#modify-application-settings)
1. [テスト キーを生成する](#generate-test-keys)
1. [プロジェクトをビルドする](#build-the-project)
1. [DKE サービスを展開し、キー ストアを発行する](#deploy-the-dke-service-and-publish-the-key-store)
1. [展開を検証する](#validate-your-deployment)
1. [キー ストアを登録する](#register-your-key-store)
1. [DKE を使用して感度ラベルを作成する](#create-sensitivity-labels-using-dke)
1. [クライアントで DKE を有効にする](#enable-dke-in-your-client)
1. [保護されたファイルを HYOK ラベルから DKE ラベルに移行する](#migrate-protected-files-from-hyok-labels-to-dke-labels)

完了したら、DKE を使用してドキュメントとファイルを暗号化できます。 詳細については、「ファイルと [電子メールにラベル](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)を適用する」を参照Office。

### <a name="install-software-prerequisites-for-the-dke-service"></a>DKE サービスの前提条件ソフトウェアをインストールする

これらの前提条件を、DKE サービスをインストールするコンピューターにインストールします。

**.NET Core 3.1 SDK**. [DOWNLOAD .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)から SDK をダウンロードしてインストールします。

**Visual Studio コード**。 コードVisual Studioダウンロードします [https://code.visualstudio.com/](https://code.visualstudio.com) 。 インストールが完了したら、Visual Studioコードを実行し、[拡張機能の **表示]** \> **を選択します**。 これらの拡張機能をインストールします。

- C# for Visual Studio Code

- NuGet パッケージ マネージャー

**Git リソース**。 次のいずれかをダウンロードしてインストールします。

- [Git](https://git-scm.com/downloads)

- [GitHub デスクトップ](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** DKE の展開 [後にテスト キー](https://slproweb.com/products/Win32OpenSSL.html) を [生成するには、OpenSSL](#generate-test-keys) がインストールされている必要があります。 環境変数のパスから正しく呼び出されていることを確認してください。 たとえば、詳細については、「インストール ディレクトリを PATH に追加する」 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) を参照してください。

### <a name="clone-the-dke-github-repository"></a>DKE GitHub リポジトリを複製する

Microsoft は、GitHub リポジトリに DKE ソース ファイルを提供しています。 リポジトリを複製して、組織で使用するためにプロジェクトをローカルにビルドします。 DKE GitHub リポジトリの場所は次の場所にあります [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。

次の手順は、経験の浅い git またはコード Visual Studio向けです。

1. ブラウザーで、次の場所に移動します [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。

2. 画面の右側で、[コード] を選択 **します**。 バージョンの UI に [複製] または [ダウンロード] **ボタンが表示される場合** があります。 次に、表示されるドロップダウンでコピー アイコンを選択し、URL をクリップボードにコピーします。

    次に例を示します。

   > [!div class="mx-imgBorder"]
   > ![GitHub から Double Key Encryption サービス リポジトリを複製する](../media/dke-clone.png)

3. [コードVisual Studioコマンド パレットの **表示]** \> **を** 選択し **、[Git:** Clone] を選択します。 リスト内のオプションに移動するには、入力を開始してエントリをフィルター処理し、ドロップダウン `git: clone` から選択します。 次に例を示します。

   > [!div class="mx-imgBorder"]
   > ![Visual Studio GIT:Clone オプション](../media/dke-vscode-clone.png)

4. テキスト ボックスに、Git からコピーした URL を貼り付け **、GitHub から [Clone] を選択します**。

5. 表示される **[フォルダーの** 選択] ダイアログで、リポジトリを格納する場所を参照して選択します。 プロンプトで、[開く] を **選択します**。

    リポジトリがコードVisual Studio開き、左下に現在の Git 分岐が表示されます。 たとえば、分岐は main である **必要があります**。 次に例を示します。

   ![メイン 分岐を表示している Visual Studioコードの DKE レポのスクリーンショット](../media/dke-vscode-main-branch.jpg)

6. メイン 分岐を使用していない場合は、選択する必要があります。 コードVisual Studio、分岐を選択し、表示される分岐の一覧から main を選択します。

   > [!IMPORTANT]
   > メイン分岐を選択すると、プロジェクトをビルドするための適切なファイルが確保されます。 正しい分岐を選択しない場合、展開は失敗します。

これで、DKE ソース リポジトリがローカルにセットアップされます。 次に [、組織のアプリケーション設定](#modify-application-settings) を変更します。

### <a name="modify-application-settings"></a>アプリケーション設定の変更

DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。

- [キー アクセスの設定](#key-access-settings)
- [テナントとキーの設定](#tenant-and-key-settings)

アプリケーション設定は、on ファイルappsettings.js変更します。 このファイルは、DoubleKeyEncryptionService\src\customer-key-store の下にローカルに複製した DoubleKeyEncryptionService リポジトリにあります。 たとえば、コードVisual Studio、次の図に示すようにファイルを参照できます。

![DKE 用appsettings.jsの場所。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>キー アクセスの設定

電子メールまたは役割の承認を使用するかどうかを選択します。 DKE では、一度にサポートされる認証方法は 1 つのみです。

- **電子メールの承認**。 電子メール アドレスにのみ基づいてキーへのアクセスを組織が承認できます。

- **役割の承認**。 組織が Active Directory グループに基づいてキーへのアクセスを承認し、Web サービスが LDAP を照会できる必要があります。

**電子メールの承認を使用して DKE のキー アクセス設定を設定するには**

1. ファイルの **appsettings.jsを開き** 、設定を探 `AuthorizedEmailAddress` します。

2. 承認するメール アドレスを追加します。 複数の電子メール アドレスは二重引用符とコンマで区切ります。 次に例を示します。

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 設定を `LDAPPath` 見つけて、二重引用符の `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 間のテキストを削除します。 二重引用符はそのまま残します。 完了すると、設定は次のように表示されます。

   ```json
   "LDAPPath": ""
   ```

4. 設定を `AuthorizedRoles` 見つけて、行全体を削除します。

この画像は、電子 **メールのappsettings.js形式の** ファイルに関する情報を示しています。

   ![電子appsettings.js方法を示すファイルの例](../media/dke-email-accesssetting.png)

**役割の承認を使用して DKE のキー アクセス設定を設定するには**

1. ファイルの **appsettings.jsを開き** 、設定を探 `AuthorizedRoles` します。

2. 承認する Active Directory グループ名を追加します。 複数のグループ名を二重引用符とコンマで区切ります。 次に例を示します。

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. 設定を `LDAPPath` 見つけて、Active Directory ドメインを追加します。 次に例を示します。

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 設定を `AuthorizedEmailAddress` 見つけて、行全体を削除します。

この画像は、ロールの **承認appsettings.js形式の** ファイルに関する情報を示しています。

   ![appsettings.jsの承認方法を示すファイルの作成](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>テナントとキーの設定

DKE テナントとキーの設定は、appsettings.js **に表示** されます。

**DKE のテナントとキーの設定を構成するには**

1. ファイルの **appsettings.jsを開** きます。

2. 設定を `ValidIssuers` 見つけて、テナント `<tenantid>` ID に置き換える。 テナント ID を見つけるには、Azure ポータルにアクセスしてテナントのプロパティを [表示します](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。 次に例を示します。

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

を探します `JwtAudience` 。 `<yourhostname>`DKE サービスを実行するコンピューターのホスト名に置き換える。 次に例を示します。

  > [!IMPORTANT]
  > 値は、 `JwtAudience` ホストの名前と正確に一致 *する必要があります*。 デバッグ中に **localhost:5001** を使用できます。 ただし、デバッグが完了したら、この値をサーバーのホスト名に更新してください。

- `TestKeys:Name`. キーの名前を入力します。 例: `TestKey1`
- `TestKeys:Id`. GUID を作成し、値として入力 `TestKeys:ID` します。 たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。 オンライン GUID ジェネレーターのようなサイト [を使用して、GUID](https://guidgenerator.com/) をランダムに生成できます。

この画像は、テナントとキーの設定の正しい形式を示appsettings.js **オンです**。 `LDAPPath` は、役割の承認用に構成されます。

![ファイルに保存されている DKE の適切なテナントとappsettings.js設定を表示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>テスト キーを生成する

アプリケーション設定を定義したら、公開キーとプライベート テスト キーを生成する準備が整います。

キーを生成するには:

1. Windows の [スタート] メニューから、OpenSSL コマンド プロンプトを実行します。

2. テスト キーを保存するフォルダーに移動します。 このタスクの手順を完了して作成するファイルは、同じフォルダーに格納されます。

3. 新しいテスト キーを生成します。

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. プライベート キーを生成します。

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. 公開キーを生成します。

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. テキスト エディターで **、pubkeyonly.pem を開きます**。 **pubkeyonly.pem** ファイルのすべてのコンテンツ (最初の行と最後の行を除く) を、ファイルのappsettings.js`PublicPem` **セクションにコピー** します。

7. テキスト エディターで **、prikeynopass.pem を開きます**。 最初の行と最後の行を除く **、appsettings.js** `PrivatePem` on ファイル内のすべてのコンテンツ **をコピー** します。

8. セクションとセクションの両方のすべての空白と改行 `PublicPem` を `PrivatePem` 削除します。

    > [!IMPORTANT]
    > このコンテンツをコピーする場合は、PEM データを削除してください。

9. [Visual Studioコード] で、次のファイル **Startup.cs** します。 このファイルは、ローカルで DoubleKeyEncryptionService\src\customer-key-store\ の下に複製した DoubleKeyEncryptionService リポジトリにあります。

10. 次の行を検索します。

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. これらの行を次のテキストに置き換します。

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    最後の結果は次のようになります。

    ![startup.csプレビュー用のファイルを作成する](../media/dke-startupcs-usetestkeys.png)

これで [、DKE プロジェクトをビルドする準備ができました](#build-the-project)。

### <a name="build-the-project"></a>プロジェクトをビルドする

DKE プロジェクトをローカルにビルドするには、次の手順を使用します。

1. [Visual Studioコード] の DKE サービス リポジトリで、[コマンド パレットの表示] を選択し、プロンプトで \> **「ビルド**」と入力します。

2. 一覧から、[タスク: ビルド タスク **の実行] を選択します**。

   ビルド タスクが見つからない場合は、[ビルド タスクの構成] を選択し、次のように .NET コア用に作成します。

   ![.NET の不足しているビルド タスクを構成する](../media/dke-configurebuildtask.png)

   1. Choose **Create tasks.json from template**.

      ![DKE tasks.jsテンプレートからファイルに対するデータの作成](../media/dke-createtasksjsonfromtemplate.png)

   2. テンプレートの種類の一覧から **、[.NET Core] を選択します**。

      ![DKE 用の適切なテンプレートを選択する](../media/dke-tasksjsontemplate.png)

   3. ビルド セクションで **、customerkeystore.csproj ファイルへのパスを見** つけます。 表示されない場合は、次の行を追加します。

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. ビルドを再度実行します。

3. 出力ウィンドウに赤いエラーが表示されません。

   赤いエラーがある場合は、コンソールの出力を確認します。 前のすべての手順が正しく完了し、正しいビルド バージョンが存在していることを確認します。

4. [ **デバッグの** \> **開始] を選択して** 、プロセスをデバッグします。 環境を選択するように求めるメッセージが表示されたら **、.NET core を選択します**。

   .NET コア デバッガーは、通常起動します `https://localhost:5001` 。 テスト キーを表示するには、スラッシュ (/) とキーの名前に `https://localhost:5001` 移動して追加します。 次に例を示します。

   ```https
   https://localhost:5001/TestKey1
   ```

   キーは JSON 形式で表示されます。

これでセットアップが完了しました。 jwtAudience 設定の appsettings.jsを公開する前に、ホスト名の値が App Service ホスト名と正確に一致するようにします。 ビルドのトラブルシューティングを行う際に localhost に変更した可能性があります。

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>DKE サービスを展開し、キー ストアを発行する

実稼働展開の場合は、サード パーティ製のクラウドにサービスを展開するか、オンプレミス システム [に発行します](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。

他の方法でキーを展開することもできます。 組織に最適な方法を選択します。

パイロット展開の場合は、Azure に展開して、今すぐ開始できます。

**DKE 展開をホストする Azure Web App インスタンスを作成するには**

キー ストアを公開するには、DKE 展開をホストする Azure App Service インスタンスを作成します。 次に、生成されたキーを Azure に公開します。

1. ブラウザーで Microsoft Azure ポータルにサインインし、[[アプリ](https://ms.portal.azure.com)サービスの追加]**に移動**  >  **します**。

2. サブスクリプションとリソース グループを選択し、インスタンスの詳細を定義します。

   - DKE サービスをインストールするコンピューターのホスト名を入力します。 ファイルに対するファイルの JwtAudience 設定に定義されている名前と同appsettings.js [**してください**](#tenant-and-key-settings) 。 名前に指定する値も WebAppInstanceName です。

   - [**発行]** でコード **を選択し**、ランタイム スタックの場合は **、[.NET Core 3.1] を選択します**。 

   次に例を示します。

   > [!div class="mx-imgBorder"]
   > ![App Service を追加する](../media/dke-azure-add-app-service.png)

3. At the bottom of the page, select **Review + create,** and then select **Add**.

4. 生成されたキーを発行するには、次のいずれかを実行します。

   - [ZipDeployUI を使用して発行する](#publish-via-zipdeployui)
   - [FTP 経由で発行する](#publish-via-ftp)
   - [Visual Studio 2019 以降で発行する](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>ZipDeployUI を使用して発行する

1. `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。

   例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. キー ストアのコードベースで **、customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **customerkeystore.csproj** ファイルが含まれているか確認します。

3. 実行: **dotnet 発行**

   出力ウィンドウには、発行が展開されたディレクトリが表示されます。

   例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. 発行ディレクトリ内のすべてのファイルを .zip ファイルに送信します。 .zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。

5. 作成した .zip ファイルを、上で開いた ZipDeployUI サイトにドラッグ アンド ドロップします。 例: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE が展開され、作成したテスト キーを参照できます。 以下の展開 [の検証に進](#validate-your-deployment) んでください。

#### <a name="publish-via-ftp"></a>FTP 経由で発行する

1. 上で作成したアプリ サービスに接続 [します](#deploy-the-dke-service-and-publish-the-key-store)。

   ブラウザーで **、Azure portal** App Service 展開センターの  >    >  **手動展開** FTP  >  **ダッシュボード** に  >  **移動**  >  **します**。

2. 表示された接続文字列をローカル ファイルにコピーします。 これらの文字列を使用して Web App Service に接続し、FTP 経由でファイルをアップロードします。

   次に例を示します。

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

3. キー ストレージのコードベースで **、customer-key-store\src\customer-key-store ディレクトリに移動します**。

4. このディレクトリに **customerkeystore.csproj ファイルが含まれているか確認** します。

5. 実行: **dotnet 発行**

   出力には、発行が展開されたディレクトリが含まれます。

   例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. 発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。 .zip ファイルを作成する場合は、ディレクトリ内のすべてのファイルが .zip ファイルのルート レベルに存在する必要があります。

7. FTP クライアントから、コピーした接続情報を使用して App Service に接続します。 前の手順で作成した .zip ファイルを Web App のルート ディレクトリにアップロードします。

DKE が展開され、作成したテスト キーを参照できます。 次に、 [展開を検証します](#validate-your-deployment)。

### <a name="validate-your-deployment"></a>展開を検証する

上記のいずれかの方法を使用して DKE を展開した後、展開とキー ストアの設定を検証します。

次のコマンドを実行します。

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

次に例を示します。

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

出力にエラーが表示されないか確認します。 準備ができたら、キー [ストアを登録します](#register-your-key-store)。

キー名では大文字と小文字が区別されます。 ファイルのコピーに表示されるキー名appsettings.js入力します。

## <a name="register-your-key-store"></a>キー ストアを登録する

次の手順を実行すると、DKE サービスを登録できます。 DKE サービスの登録は、ラベルの作成を開始する前に DKE を展開する最後の手順です。

DKE サービスを登録するには:

1. ブラウザーで [、Microsoft Azure ポータルを開](https://ms.portal.azure.com/)き、[すべての **サービス** ID アプリの登録] \>  \> **に移動します**。

2. [ **新規登録] を** 選択し、わかりやすい名前を入力します。

3. 表示されるオプションからアカウントの種類を選択します。

   **onmicrosoft.com** などの非カスタム ドメインで Microsoft Azure を使用している場合は、この組織のディレクトリでのみ [アカウント] を選択します **(Microsoft のみ - シングル テナント)。**

   次に例を示します。

   > [!div class="mx-imgBorder"]
   > ![新しいアプリの登録](../media/dke-app-registration.png)

4. ページの下部にある [登録] **を選択して** 、新しいアプリ登録を作成します。

5. 新しいアプリの登録の左側のウィンドウで、[管理] の下の **[** 認証] を **選択します**。

6. [プラットフォーム **の追加] を選択します**。

7. [プラットフォーム **の構成] ポップアップで****、[Web] を選択します**。

8. [ **リダイレクト URI] で**、二重キー暗号化サービスの URI を入力します。 ホスト名とドメインの両方を含む、アプリ サービスの URL を入力します。

   例: https://mydkeservicetest.com

   - 入力する URL は、DKE サービスが展開されているホスト名と一致している必要があります。
   - If you're testing locally with Visual Studio, use **https://localhost:5001** .
   - すべての場合、スキームは https である **必要があります**。

   ホスト名が App Service のホスト名と正確に一致する必要があります。 ビルドのトラブルシューティングに変更 `localhost` した可能性があります。 In **appsettings.json,** this value is the hostname you set for `JwtAudience` .

9. [**暗黙的な許可] で****、[ID トークン] チェック ボックスをオン** にします。

10. **[保存]** を選択し、変更内容を保存します。

11. 左側のウィンドウで、[API の公開] **を選択** し、[アプリケーション ID URI] の横にある [設定] を選択 **します**。

12. 引き続き **[API の** 公開] ページで、この **API** 領域で定義されているスコープで、[スコープの追加 **] を選択します**。 新しいスコープで、次の条件を実行します。

    1. スコープ名を次のように **定義user_impersonation。**

    2. 同意できる管理者とユーザーを選択します。

    3. 必要な残りの値を定義します。

    4. **[スコープの追加]** を選択します。

    5. 上部 **の [** 保存] を選択して変更を保存します。

13. 引き続き **[API の** 公開] ページの [承認された **クライアント** アプリケーション] 領域で、[クライアント アプリケーションの追加 **] を選択します**。

    新しいクライアント アプリケーションで、次の条件を実行します。

    1. クライアント ID を **d3590ed6-52b3-4102-aeff-aad2292ab01c** として定義します。 この値はクライアント ID Microsoft Officeであり、キー ストアOfficeトークンを取得できます。

    2. [ **承認済みスコープ] で、** 有効なスコープ **user_impersonation** します。

    3. **[アプリケーションの追加]** を選択します。

    4. 上部 **の [** 保存] を選択して変更を保存します。

これで、DKE サービスが登録されました。 [DKE を使用してラベルを作成します](#create-sensitivity-labels-using-dke)。

## <a name="create-sensitivity-labels-using-dke"></a>DKE を使用して感度ラベルを作成する

Microsoft 365 コンプライアンス センターで、新しい区別ラベルを作成し、それ以外の場合と同様に暗号化を適用します。 [Use **Double Key Encryption] を選択** し、キーのエンドポイント URL を入力します。

次に例を示します。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 コンプライアンス センターで [二重キー暗号化を使用する] を選択する](../media/dke-use-dke.png)

追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示されます。

> [!NOTE]
> クライアントが新しいラベルで更新するには、最大 24 時間かかる場合があります。

### <a name="enable-dke-in-your-client"></a>クライアントで DKE を有効にする

Insider を使用している場合Office DKE が有効になります。 それ以外の場合は、次のレジストリ キーを追加して、クライアントの DKE を有効にします。

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>保護されたファイルを HYOK ラベルから DKE ラベルに移行する

必要な場合は、DKE の設定が完了したら、HYOK ラベルを使用して保護したコンテンツを DKE ラベルに移行できます。 移行するには、AIP スキャナーを使用します。 スキャナーの使用を開始するには、「Azure Information Protection 統合ラベル付けスキャナー [とは」を参照してください](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)。

コンテンツを移行しない場合、HYOK で保護されたコンテンツは影響を受けません。
