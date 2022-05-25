---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、機密性の高いデータを保護しながら、キーを完全に制御できます。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 02/28/2022
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 74194d4bca71350c180799e071936b75044a6b4e
ms.sourcegitcommit: 612ce4d15d8a2fdbf7795393b50af477d81b6139
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65663692"
---
# <a name="double-key-encryption"></a>二重キー暗号化

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

> *適用対象: Microsoft Purview ダブル キー暗号化、[Microsoft Purview](https://www.microsoft.com/microsoft-365/business/compliance-management)、[Azure Information Protection](https://azure.microsoft.com/pricing/)*
>
> *手順: [azure Information Protection Windows用の統合ラベル付けクライアント](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*

> *サービスの説明: [Microsoft Purview](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

二重キー暗号化 (DKE) は、保護されたコンテンツにアクセスするために 2 つの鍵を同時に使用します。 Microsoft は一方の鍵を Microsoft Azure に保管し、もう一方の鍵はユーザーが保持します。 Double Key Encryption サービスを使用して、いずれかのキーを完全に制御します。 Azure Information Protection統合ラベル付けクライアントを使用して、機密性の高いコンテンツに保護を適用します。

Double Key Encryption は、クラウドとオンプレミスの両方のデプロイをサポートします。 これらのデプロイは、保護されたデータを格納する場所を問わず、暗号化されたデータが不透明なままになるようにするのに役立ちます。

既定のクラウドベースのテナント ルート キーの詳細については、「[Azure Information Protection テナント キーの計画と実装](/azure/information-protection/plan-implement-tenant-key)」を参照してください。

## <a name="when-your-organization-should-adopt-dke"></a>組織が DKE を採用する必要がある場合

二重キー暗号化は、最も厳しい保護要件の対象となる最も機密性の高いデータを対象としています。 DKE は、すべてのデータを対象としたものではありません。 一般に、Double Key Encryption を使用して、全体的なデータのごく一部のみを保護します。 デプロイする前に、このソリューションでカバーする適切なデータを特定する際には、適切な注意を行う必要があります。 場合によっては、Microsoft マネージド キーや BYOK を使用したMicrosoft Purview 情報保護など、ほとんどのデータに対してスコープを絞り込み、他のソリューションを使用することが必要になる場合があります。 これらのソリューションは、強化された保護と規制要件の対象になっていないドキュメントに対して十分です。 また、これらのソリューションを使用すると、DKE で暗号化されたコンテンツでは使用できない最も強力なOffice 365 サービス、サービスを使用できます。 例として以下のようなものがあります。

- 添付ファイルの可視性を必要とするマルウェア対策やスパムを含むトランスポート ルール
- Microsoft Delve
- 電子情報開示
- コンテンツの検索とインデックス作成
- 共同編集機能を含むOffice Web Apps

Microsoft Information Protection (MIP) SDK を使用して DKE と統合されていない外部アプリケーションまたはサービスは、暗号化されたデータに対してアクションを実行できません。

Microsoft Information Protection SDK 1.7 以降では、ダブル キー暗号化がサポートされています。 SDK と統合するアプリケーションは、十分なアクセス許可と統合を用意して、このデータを推論できます。

Microsoft Purview 情報保護機能 (分類とラベル付け) を使用して機密データのほとんどを保護し、ミッション クリティカルなデータにのみ DKE を使用します。 Double Key Encryption は、金融サービスや医療などの厳しく規制された業界の機密データに関連しています。

組織に次のいずれかの要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。

- すべての状況で、保護されたコンテンツの暗号化 *を解除できるのは自分だけ* であることを確認する必要があります。
- Microsoft が独自に保護されたデータにアクセスできないようにする必要があります。
- 地理的境界内でキーを保持するための規制要件があります。 データの暗号化と暗号化解除のために保持するすべてのキーは、データ センターに保持されます。

## <a name="system-and-licensing-requirements-for-dke"></a>DKE のシステム要件とライセンス要件

**Double Key Encryption** にはMicrosoft 365 E5が付属しています。 Microsoft 365 E5 ライセンスをお持ちでない場合は、[試用版](https://aka.ms/M365E5ComplianceTrial)にサインアップできます。 これらのライセンスの詳細については、[セキュリティ&コンプライアンスに関するMicrosoft 365ライセンスガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)参照してください。

**Azure Information Protection**。 DKE は機密ラベルで動作し、Azure Information Protectionが必要です。

DKE 秘密度ラベルは、Office Desktop Apps の AIP 統合ラベル付けクライアントの [秘密度] ボタンを使用してエンド ユーザーが使用できるようになります。 これらの前提条件は、保護されたドキュメントを保護して使用する各クライアント コンピューターにインストールします。

**Windowsでエンタープライズ** バージョン 2009 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) 用のアプリをMicrosoft Officeします。

**Azure Information Protection 統合ラベル付けクライアント** バージョン 2.7.93.0 以降。 [Microsoft ダウンロード センター](https://www.microsoft.com/download/details.aspx?id=53018)から統合ラベル付けクライアントをダウンロードしてインストールします。

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>DKE で保護されたコンテンツを格納および表示するためのサポートされている環境

**サポートされているアプリケーション**。 [Word、Excel](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)、PowerPointなど、Windows上のクライアントをMicrosoft 365 Apps for enterpriseします。

**オンライン コンテンツのサポート**。 Microsoft SharePointとOneDrive for Businessの両方で、Double Key Encryption で保護されているドキュメントとファイルをオンラインで保存できます。 これらの場所にアップロードする前に、サポートされているアプリケーションによって DKE でドキュメントとファイルにラベルを付けて保護する必要があります。 暗号化されたコンテンツは電子メールで共有できますが、暗号化されたドキュメントやファイルをオンラインで表示することはできません。 代わりに、ローカル コンピューターでサポートされているデスクトップ アプリケーションとクライアントを使用して、保護されたコンテンツを表示する必要があります。

## <a name="overview-of-deploying-dke"></a>DKE のデプロイの概要

これらの一般的な手順に従って DKE を設定します。 これらの手順を完了すると、エンド ユーザーは二重キー暗号化を使用して機密性の高いデータを保護できます。

1. この記事で説明されているように、DKE サービスをデプロイします。

2. 二重キー暗号化を使用してラベルを作成します。 Microsoft Purview コンプライアンス ポータルで、**情報保護** に移動し、二重キー暗号化を使用して新しいラベルを作成します。 [機密ラベルを使用して暗号化を適用することでコンテンツへのアクセスを制限する方法に関するページを](./encryption-sensitivity-labels.md)参照してください。

3. Double Key Encryption ラベルを使用します。 Microsoft Officeの [秘密度] リボンから [Double Key Encrypted] ラベルを選択してデータを保護します。

ダブル キー暗号化を展開する手順の一部を完了するには、いくつかの方法があります。 この記事では、経験の少ない管理者がサービスを正常にデプロイできるように、詳細な手順を説明します。 問題がなければ、独自のメソッドを使用できます。

## <a name="deploy-dke"></a>DKE をデプロイする

この記事とデプロイ ビデオでは、DKE サービスのデプロイ先として Azure を使用します。 別の場所にデプロイする場合は、独自の値を指定する必要があります。

[Double Key Encryption の展開ビデオ](https://youtu.be/vDWfHN_kygg)を見て、この記事の概念の詳細な概要を確認してください。 ビデオの完了には約 18 分かかります。

組織のダブル キー暗号化を設定するには、次の一般的な手順に従います。

1. [DKE サービスのソフトウェア前提条件をインストールする](#install-software-prerequisites-for-the-dke-service)
1. [二重キー暗号化GitHubリポジトリを複製する](#clone-the-dke-github-repository)
1. [アプリケーション設定を変更する](#modify-application-settings)
1. [テスト キーを生成する](#generate-test-keys)
1. [プロジェクトをビルドする](#build-the-project)
1. [DKE サービスをデプロイし、キー ストアを発行する](#deploy-the-dke-service-and-publish-the-key-store)
1. [展開を検証する](#validate-your-deployment)
1. [キー ストアを登録する](#register-your-key-store)
1. [DKE を使用して秘密度ラベルを作成する](#create-sensitivity-labels-using-dke)
1. [クライアントで DKE を有効にする](#enable-dke-in-your-client)
1. [保護されたファイルを HYOK ラベルから DKE ラベルに移行する](#migrate-protected-files-from-hyok-labels-to-dke-labels)

完了したら、DKE を使用してドキュメントとファイルを暗号化できます。 詳細については、「[Officeのファイルと電子メールに機密ラベルを適用する](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)」を参照してください。

### <a name="install-software-prerequisites-for-the-dke-service"></a>DKE サービスのソフトウェア前提条件をインストールする

DKE サービスをインストールするコンピューターにこれらの前提条件をインストールします。

**.NET Core 3.1 SDK**。 [.NET Core 3.1 のダウンロードから SDK をダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)してインストールします。

**Visual Studio コード**。 Visual Studio Code をダウンロードします[https://code.visualstudio.com/](https://code.visualstudio.com)。 インストールしたら、Visual Studio コードを実行し、[**拡張機能** の **表示**\>] を選択します。 これらの拡張機能をインストールします。

- Visual Studio コードの C#

- NuGet パッケージ マネージャー

**Git リソース**。 次のいずれかをダウンロードしてインストールします。

- [Git](https://git-scm.com/downloads)

- [デスクトップのGitHub](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**Openssl** DKE をデプロイした後で [テスト キーを生成](#generate-test-keys)するには [、OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) がインストールされている必要があります。 環境変数パスから正しく呼び出していることを確認します。 たとえば、詳細については、「PATH にインストール ディレクトリを追加する」 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) を参照してください。

### <a name="clone-the-dke-github-repository"></a>DKE GitHub リポジトリを複製する

Microsoft は、GitHub リポジトリに DKE ソース ファイルを提供しています。 リポジトリを複製して、組織で使用するためにプロジェクトをローカルにビルドします。 DKE GitHub リポジトリは [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)、 .

次の手順は、未経験の git または Visual Studio Code ユーザーを対象としています。

1. ブラウザーで、次の手順に進みます [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)。

2. 画面の右側にある [ **コード**] を選択します。 バージョンの UI に **[複製] ボタンまたは [ダウンロード** ] ボタンが表示される場合があります。 次に、表示されるドロップダウンでコピー アイコンを選択し、URL をクリップボードにコピーします。

    例として以下のようなものがあります。

   > [!div class="mx-imgBorder"]
   > ![GitHubから Double Key Encryption サービス リポジトリを複製します。](../media/dke-clone.png)

3. Visual Studio コードで、[コマンド **パレット****の表示**\>] を選択し、[**Git: 複製**] を選択します。 一覧のオプションにジャンプするには、入力 `git: clone` を開始してエントリをフィルター処理し、ドロップダウンから選択します。 例として以下のようなものがあります。

   > [!div class="mx-imgBorder"]
   > ![Visual Studio Code GIT:Clone オプション。](../media/dke-vscode-clone.png)

4. テキスト ボックスに、Git からコピーした URL を貼り付けて、[**GitHubから複製**] を選択します。

5. 表示された **[フォルダーの選択** ] ダイアログで、リポジトリを格納する場所を参照して選択します。 プロンプトで [ **開く**] を選択します。

    リポジトリが Visual Studio Code で開き、左下に現在の Git ブランチが表示されます。 たとえば、ブランチは **メイン** である必要があります。 例として以下のようなものがあります。

   ![メイン ブランチを表示する Visual Studio Code の DKE リポジトリのスクリーンショット。](../media/dke-vscode-main-branch.jpg)

6. メイン ブランチにいない場合は、選択する必要があります。 Visual Studio コードで、ブランチを選択し、表示されるブランチの一覧から **main** を選択します。

   > [!IMPORTANT]
   > メイン ブランチを選択すると、プロジェクトをビルドするための適切なファイルが確保されます。 正しいブランチを選択しないと、デプロイは失敗します。

これで、DKE ソース リポジトリがローカルに設定されました。 次に、組織の [アプリケーション設定を変更](#modify-application-settings) します。

### <a name="modify-application-settings"></a>アプリケーション設定を変更する

DKE サービスをデプロイするには、次の種類のアプリケーション設定を変更する必要があります。

- [キー アクセス設定](#key-access-settings)
- [テナントとキーの設定](#tenant-and-key-settings)

appsettings.json ファイルでアプリケーション設定を変更します。 このファイルは、DoubleKeyEncryptionService\src\customer-key-store の下でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。 たとえば、Visual Studio コードでは、次の図に示すようにファイルを参照できます。

![DKE の appsettings.json ファイルを見つける。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>キー アクセス設定

電子メールまたはロールの承認を使用するかどうかを選択します。 DKE では、一度に 1 つの認証方法のみがサポートされます。

- **電子メール承認**。 組織が電子メール アドレスのみに基づいてキーへのアクセスを承認できるようにします。

- **ロールの承認**。 組織が Active Directory グループに基づいてキーへのアクセスを承認することを許可し、Web サービスが LDAP に対してクエリを実行できるようにする必要があります。

##### <a name="to-set-key-access-settings-for-dke-using-email-authorization"></a>電子メール承認を使用して DKE のキー アクセス設定を設定するには

1. **appsettings.json ファイルを** 開き、設定を`AuthorizedEmailAddress`見つけます。

2. 承認する電子メール アドレスを追加します。 複数の電子メール アドレスを二重引用符とコンマで区切ります。 例として以下のようなものがあります。

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 設定を `LDAPPath` 見つけて、二重引用符の間のテキスト `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` を削除します。 二重引用符はそのままにしておきます。 完了したら、設定は次のようになります。

   ```json
   "LDAPPath": ""
   ```

4. 設定を `AuthorizedRoles` 見つけて、行全体を削除します。

この画像は、電子メール承認用に正しく書式設定された **appsettings.json** ファイルを示しています。

   ![電子メール承認方法を示す appsettings.json ファイル。](../media/dke-email-accesssetting.png)

##### <a name="to-set-key-access-settings-for-dke-using-role-authorization"></a>ロール承認を使用して DKE のキー アクセス設定を設定するには

1. **appsettings.json ファイルを** 開き、設定を`AuthorizedRoles`見つけます。

2. 承認する Active Directory グループ名を追加します。 複数のグループ名を二重引用符とコンマで区切ります。 例として以下のようなものがあります。

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. 設定を `LDAPPath` 見つけて Active Directory ドメインを追加します。 例として以下のようなものがあります。

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 設定を `AuthorizedEmailAddress` 見つけて、行全体を削除します。

この画像は、ロール承認用に正しく書式設定された **appsettings.json** ファイルを示しています。

   ![ロール承認メソッドを示す appsettings.json ファイル。](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>テナントとキーの設定

DKE テナントとキーの設定は、 **appsettings.json** ファイルにあります。

##### <a name="to-configure-tenant-and-key-settings-for-dke"></a>DKE のテナントとキーの設定を構成するには

1. **appsettings.json ファイルを** 開きます。

2. 設定を `ValidIssuers` 見つけて、テナント ID に置き換えます `<tenantid>` 。 テナント ID を見つけるには、Azure portalに移動し、[テナントのプロパティ](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)を表示します。 例として以下のようなものがあります。

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

> [!NOTE]
> キー ストアへの外部 B2B アクセスを有効にする場合は、有効な発行者の一覧の一部としてこれらの外部テナントも含める必要があります。

`JwtAudience`を見つけます。 DKE サービスを実行するマシンのホスト名に置き換えます `<yourhostname>` 。 例として以下のようなものがあります。

  > [!IMPORTANT]
  > の値は、 `JwtAudience` ホストの名前と *正確に* 一致する必要があります。 デバッグ中は **localhost:5001** を使用できます。 ただし、デバッグが完了したら、この値をサーバーのホスト名に更新してください。

- `TestKeys:Name`. キーの名前を入力します。 例: `TestKey1`
- `TestKeys:Id`. GUID を作成し、値として `TestKeys:ID` 入力します。 たとえば、「 `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` 」のように入力します。 [オンライン GUID ジェネレーター](https://guidgenerator.com/)などのサイトを使用して、GUID をランダムに生成できます。

この画像は、 **appsettings.json** のテナントとキーの設定に対する正しい形式を示しています。 `LDAPPath` は、ロール承認用に構成されています。

![appsettings.json ファイルに DKE の正しいテナントとキーの設定を表示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>テスト キーを生成する

アプリケーション設定を定義したら、パブリック テスト キーとプライベート テスト キーを生成する準備が整いました。

キーを生成するには:

1. Windows スタート メニューから OpenSSL コマンド プロンプトを実行します。

1. テスト キーを保存するフォルダーに変更します。 このタスクの手順を実行して作成するファイルは、同じフォルダーに格納されます。

1. 新しいテスト キーを生成します。

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

1. 秘密キーを生成します。

   OpenSSL バージョン 3 以降をインストールした場合は、次のコマンドを実行します。
  
  ```console
  openssl rsa -in key.pem -out privkeynopass.pem -outform PEM -traditional
  ```
  
>  それ以外の場合は、次のコマンドを実行します。
>  ```console
>  openssl rsa -in key.pem -out privkeynopass.pem -outform PEM
>  ```

1. 公開キーを生成します。

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. テキスト エディターで **pubkeyonly.pem を** 開きます。 **pubkeyonly.pem** ファイル内のすべてのコンテンツ (最初の行と最後の行を除く) を **appsettings.json** ファイルのセクションに`PublicPem`コピーします。

1. テキスト エディターで **privkeynopass.pem を** 開きます。 **privkeynopass.pem** ファイル内のすべてのコンテンツ (最初の行と最後の行を除く) を **appsettings.json** ファイルのセクションに`PrivatePem`コピーします。

1. セクションとセクションの両方のすべての空白と改行を`PublicPem``PrivatePem`削除します。

    > [!IMPORTANT]
    > このコンテンツをコピーするときは、PEM データを削除しないでください。

1. Visual Studio コードで、**Startup.cs** ファイルを参照します。 このファイルは、DoubleKeyEncryptionService\src\customer-key-store\の下でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。

1. 次の行を見つけます:

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

1. これらの行を次のテキストに置き換えます。

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    最終的な結果は次のようになります。

    ![パブリック プレビュー用の startup.cs ファイル。](../media/dke-startupcs-usetestkeys.png)

これで [、DKE プロジェクトをビルドする準備ができました](#build-the-project)。

### <a name="build-the-project"></a>プロジェクトをビルドする

次の手順に従って、DKE プロジェクトをローカルにビルドします。

1. Visual Studio Code の DKE サービス リポジトリで、[**コマンド パレット** の **表示**\>] を選択し、プロンプトに「**build**」と入力します。

2. 一覧から [ **タスク: ビルド タスクの実行**] を選択します。

   ビルド タスクが見つからない場合は、[ **ビルド タスクの構成** ] を選択し、次のように .NET core 用に作成します。

   ![.NET 用に不足しているビルド タスクを構成します。](../media/dke-configurebuildtask.png)

   1. **[テンプレートから tasks.json を作成する**] を選択します。

      ![DKE のテンプレートから tasks.json ファイルを作成します。](../media/dke-createtasksjsonfromtemplate.png)

   2. テンプレートの種類の一覧から 、 **.NET Core** を選択します。

      ![DKE の正しいテンプレートを選択します。](../media/dke-tasksjsontemplate.png)

   3. ビルド セクションで、 **customerkeystore.csproj** ファイルへのパスを探します。 存在しない場合は、次の行を追加します。

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. ビルドをもう一度実行します。

3. 出力ウィンドウに赤いエラーがないことを確認します。

   赤いエラーが発生した場合は、コンソールの出力を確認します。 前のすべての手順を正しく完了し、正しいビルド バージョンが存在することを確認します。

4. プロセスをデバッグするには、[**デバッグの開始**] を選択します。 \> 環境を選択するように求められた場合は、 **.NET core** を選択します。

   通常、.NET コア デバッガーは `https://localhost:5001`. テスト キーを表示するには、スラッシュ (/) とキーの名前に移動 `https://localhost:5001` して追加します。 例として以下のようなものがあります。

   ```https
   https://localhost:5001/TestKey1
   ```

   キーは JSON 形式で表示されます。

これでセットアップが完了しました。 キーストアを発行する前に、appsettings.json の JwtAudience 設定で、ホスト名の値がApp Serviceホスト名と正確に一致していることを確認します。 ビルドのトラブルシューティングを行うために、localhost に変更した可能性があります。

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>DKE サービスをデプロイし、キー ストアを発行する

運用環境のデプロイの場合は、サード パーティのクラウドにサービスをデプロイするか、 [オンプレミス システムに発行します](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)。

キーをデプロイするには、他の方法を使用することをお好みの場合があります。 組織に最適な方法を選択します。

パイロット デプロイの場合は、Azure にデプロイしてすぐに開始できます。

#### <a name="to-create-an-azure-web-app-instance-to-host-your-dke-deployment"></a>DKE デプロイをホストする Azure Web App インスタンスを作成するには

キー ストアを発行するには、DKE デプロイをホストするAzure App Service インスタンスを作成します。 次に、生成されたキーを Azure に発行します。

1. ブラウザーで [、Microsoft Azure ポータル](https://ms.portal.azure.com)にサインインし、**App Services** > **の追加** に移動します。

2. サブスクリプションとリソース グループを選択し、インスタンスの詳細を定義します。

   - DKE サービスをインストールするコンピューターのホスト名を入力します。 [**appsettings.json**](#tenant-and-key-settings) ファイルの JwtAudience 設定に定義されているものと同じ名前であることを確認します。 名前に指定する値は、WebAppInstanceName でもあります。

   - **[発行]** で **コード** を選択し、[**ランタイム スタック**] で **[.NET Core 3.1**] を選択します。

   例として以下のようなものがあります。

   > [!div class="mx-imgBorder"]
   > ![App Serviceを追加します。](../media/dke-azure-add-app-service.png)

3. ページの下部にある [ **校閲と作成**] を選択し、[ **追加**] を選択します。

4. 生成されたキーを発行するには、次のいずれかの操作を行います。

   - [ZipDeployUI を使用して発行する](#publish-via-zipdeployui)
   - [FTP 経由で発行する](#publish-via-ftp)
   - [Visual Studio 2019 以降を使用して発行する](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>ZipDeployUI を使用して発行する

1. `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`に移動します。

   例: `https://dkeservice.scm.azurewebsites.net/ZipDeployUI`

2. キー ストアのコードベースで、 **customer-key-store\src\customer-key-store** フォルダーに移動し、このフォルダーに **customerkeystore.csproj** ファイルが含まれていることを確認します。

3. 実行: **dotnet publish**

   出力ウィンドウには、発行がデプロイされたディレクトリが表示されます。

   例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. 発行ディレクトリ内のすべてのファイルを.zip ファイルに送信します。 .zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが.zip ファイルのルート レベルであることを確認します。

5. 作成した.zip ファイルを、上で開いた ZipDeployUI サイトにドラッグ アンド ドロップします。 例: `https://dkeservice.scm.azurewebsites.net/ZipDeployUI`

DKE がデプロイされ、作成したテスト キーを参照できます。 次の手順に進み [、デプロイを検証します](#validate-your-deployment) 。

#### <a name="publish-via-ftp"></a>FTP 経由で発行する

1. [上記](#deploy-the-dke-service-and-publish-the-key-store)で作成したApp ServiceにConnectします。

   ブラウザーで、 **Azure portal** >  **App Service** >  **Deployment Center** > **手動デプロイ** > **FTP** > **ダッシュボード** に移動します。

2. 表示された接続文字列をローカル ファイルにコピーします。 これらの文字列を使用して Web App Serviceに接続し、FTP 経由でファイルをアップロードします。

   例として以下のようなものがあります。

   ![FTP ダッシュボードから接続文字列をコピーします。](../media/dke-ftp-dashboard.png)

3. キー ストレージのコードベースで、 **customer-key-store\src\customer-key-store ディレクトリに** 移動します。

4. このディレクトリに **customerkeystore.csproj** ファイルが含まれていることを確認します。

5. 実行: **dotnet publish**

   出力には、発行がデプロイされたディレクトリが含まれます。

   例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. 発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。 .zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが.zip ファイルのルート レベルであることを確認します。

7. FTP クライアントから、コピーした接続情報を使用して、App Serviceに接続します。 前の手順で作成した.zip ファイルを Web アプリのルート ディレクトリにアップロードします。

DKE がデプロイされ、作成したテスト キーを参照できます。 次に、 [デプロイを検証します](#validate-your-deployment)。

### <a name="validate-your-deployment"></a>展開を検証する

上記のいずれかの方法を使用して DKE をデプロイした後、デプロイとキー ストアの設定を検証します。

次を実行します: 

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

次に例を示します。

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

出力にエラーが表示されないようにします。 準備ができたら、 [キー ストアを登録します](#register-your-key-store)。

キー名は大文字と小文字が区別されます。 appsettings.json ファイルに表示されるキー名を入力します。

## <a name="register-your-key-store"></a>キー ストアを登録する

次の手順では、DKE サービスを登録できます。 DKE サービスを登録することは、ラベルの作成を開始する前に DKE をデプロイする最後の手順です。

DKE サービスを登録するには:

1. ブラウザーで [、Microsoft Azure ポータル](https://ms.portal.azure.com/)を開き、[**すべてのサービス** \> **ID** \> **アプリの登録]** に移動します。

2. [ **新規登録**] を選択し、わかりやすい名前を入力します。

3. 表示されたオプションからアカウントの種類を選択します。

   onmicrosoft.com **などのカスタム** 以外のドメインでMicrosoft Azureを使用している場合は、**この組織のディレクトリ内のアカウントのみを選択します (Microsoft のみ - シングル テナント)。**

   例として以下のようなものがあります。

   > [!div class="mx-imgBorder"]
   > ![新しいアプリの登録。](../media/dke-app-registration.png)

4. ページの下部にある [ **登録** ] を選択して、新しいアプリ登録を作成します。

5. 新しいアプリ登録の左側のウィンドウの [ **管理**] で、[ **認証**] を選択します。

6. **[プラットフォームの追加]** を選択します。

7. [ **プラットフォームの構成] ポップアップで** 、[ **Web**] を選択します。

8. **[リダイレクト URI] に**、ダブル キー暗号化サービスの URI を入力します。 ホスト名とドメインの両方を含む、App Service URL を入力します。

   例: `https://mydkeservicetest.com`

   - 入力する URL は、DKE サービスがデプロイされているホスト名と一致している必要があります。
   - ドメインは [検証済みドメイン](/azure/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains)である必要があります。
   - Visual Studioを使用してローカルでテストする場合は、`https://localhost:5001`.
   - いずれの場合も、スキームは **https** である必要があります。

   ホスト名がApp Serviceホスト名と正確に一致していることを確認します。 ビルドのトラブルシューティングに `localhost` 変更した可能性があります。 **appsettings.json** では、この値は設定した`JwtAudience`ホスト名です。

9. [ **暗黙的な付与**] で、[ **ID トークン** ] チェック ボックスをオンにします。

10. **[保存]** を選択し、変更内容を保存します。

11. 左側のウィンドウで [**API の公開**] を選択し、[アプリケーション ID URI] の横に、ホスト名とドメインの両方を含むApp Service URL を入力し、[**設定**] を選択します。

12. [API の **公開** ] ページの [ **この API で定義されたスコープ]** 領域で、[ **スコープの追加**] を選択します。 新しいスコープでは、次の手順を実行します。

    1. スコープ名を **user_impersonation** として定義します。

    2. 同意できる管理者とユーザーを選択します。

    3. 必要な残りの値を定義します。

    4. **[スコープの追加]** を選択します。

    5. 上部にある **[保存] を** 選択して変更を保存します。

13. [API の **公開]** ページの [ **承認されたクライアント アプリケーション** ] 領域で、[ **クライアント アプリケーションの追加**] を選択します。

    新しいクライアント アプリケーションでは、次の手順を実行します。

    1. クライアント ID を次のように `d3590ed6-52b3-4102-aeff-aad2292ab01c`定義します。 この値はMicrosoft Officeクライアント ID であり、Officeはキー ストアのアクセス トークンを取得できます。

    2. [ **承認されたスコープ**] で、 **user_impersonation** スコープを選択します。

    3. **[アプリケーションの追加]** を選択します。

    4. 上部にある **[保存] を** 選択して変更を保存します。

    5. これらの手順を繰り返しますが、今回はクライアント ID を `c00e9d32-3c8d-4a7d-832b-029040e7db99`. この値は、Azure Information Protection統合ラベル付けクライアント ID です。

これで、DKE サービスが登録されました。 [DKE を使用してラベルを作成](#create-sensitivity-labels-using-dke)し続けます。

## <a name="create-sensitivity-labels-using-dke"></a>DKE を使用して秘密度ラベルを作成する

Microsoft Purview コンプライアンス ポータルで、新しい秘密度ラベルを作成し、それ以外の場合と同様に暗号化を適用します。 [ **二重キー暗号化の使用** ] を選択し、キーのエンドポイント URL を入力します。 URL の appsettings.json ファイルの "TestKeys" セクションに指定したキー名を含める必要があります。

例: `https://testingdke1.azurewebsites.net/KEYNAME`

> [!div class="mx-imgBorder"]
> ![Microsoft Purview コンプライアンス ポータルで [二重キー暗号化の使用] を選択します。](../media/dke-use-dke.png)

追加した DKE ラベルは、最新バージョンのMicrosoft 365 Apps for enterpriseのユーザーに対して表示されます。

> [!NOTE]
> クライアントが新しいラベルで更新されるまでに最大で 24 時間かかる場合があります。

### <a name="enable-dke-in-your-client"></a>クライアントで DKE を有効にする

Office Insider の場合は、DKE が有効になります。 それ以外の場合は、次のレジストリ キーを追加して、クライアントの DKE を有効にします。

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>保護されたファイルを HYOK ラベルから DKE ラベルに移行する

必要に応じて、DKE の設定が完了したら、HYOK ラベルを使用して保護したコンテンツを DKE ラベルに移行できます。 移行するには、AIP スキャナーを使用します。 スキャナーの使用を開始するには、「[Azure Information Protection統合ラベル付けスキャナーとは」](/azure/information-protection/deploy-aip-scanner)を参照してください。

コンテンツを移行しない場合、HYOK で保護されたコンテンツは影響を受けません。

## <a name="other-deployment-options"></a>その他のデプロイ オプション

厳しく規制されている業界の一部のお客様にとって、ソフトウェア ベースのキーを使用したこの標準参照実装では、コンプライアンスの強化された義務とニーズを満たすには十分でない可能性があります。 DKE サービスで強化されたキー管理オプションをサポートするために、サード パーティのハードウェア セキュリティ モジュール (HSM) ベンダーと提携しました。次のような機能が備わっています。

- [Entrust](https://www.entrust.com/digital-security/hsm/services/packaged-services/double-key-encryption-integration#:~:text=Entrust%20Double%20Key%20Encryption%20for%20Microsoft%20AIP%2C%20offered,trust%20for%20the%20protection%20of%20sensitive%20cryptographic%20keys.)

- [タレス](https://cpl.thalesgroup.com/cloud-security/encryption/double-key-encryption)

市場内の DKE HSM ソリューションの詳細とガイダンスについては、これらのベンダーに直接お問い合わせください。
