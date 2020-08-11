---
title: 二重キー暗号化 (DKE)
description: DKE を使用すると、キーのフルコントロールを維持しながら、機密性の高いデータを保護することができます。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 0c66afa22c8712455a875bc8ca4ddcad1678e2e7
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602000"
---
# <a name="double-key-encryption-dke"></a>二重キー暗号化 (DKE)

> *適用対象: Microsoft 365 パブリックプレビュー、 [microsoft 365 コンプライアンス](https://www.microsoft.com/microsoft-365/business/compliance-management)、 [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)の二重キー暗号化*
>
> *手順: [Azure Information Protection を使用した Windows 用の統一されたラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *サービスの説明: [Microsoft 365 コンプライアンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

二重キー暗号化 (DKE) は、2つのキーを一緒に使用して、保護されたコンテンツにアクセスします。 Microsoft Azure には1つのキーを保存し、もう一方のキーは保持します。 Azure Information Protection の統合されたラベルクライアントは、キーの1つのフルコントロールを維持しながら、機密性の高いコンテンツを保護します。

二重キー暗号化は、クラウドとオンプレミスの両方の展開をサポートしています。 これらの展開は、保護されたデータを格納する際に、暗号化されたデータが透過的であるようにするのに役立ちます。

既定のクラウドベースのテナントルートキーの詳細については、「 [Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)する」を参照してください。

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

組織に次の要件がある場合は、DKE を使用してコンテンツをセキュリティで保護できます。

- すべての状況で保護されたコンテンツの暗号化を*解除できるよう*にする必要があります。
- 保護されたデータへのアクセス権を Microsoft に付与しないようにします。
- 地理的な境界内にキーを保持する規制要件があります。 データの暗号化と復号化に使用するすべてのキーは、データセンターに保持されます。

## <a name="system-and-licensing-requirements-for-dke"></a>DKE のシステムおよびライセンスの要件

Microsoft 365 の二重キー暗号化には、Microsoft 365 E5 および Office 365 E5 が付属しています。 Microsoft 365 E5 ライセンスを持っていない場合は、[試用版](https://aka.ms/M365E5ComplianceTrial)にサインアップできます。 これらのライセンスの詳細については、「 [Microsoft 365 licensing ガイダンス for security & 法令遵守](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。

**Office Insider**パブリックプレビューを使用するには、Office Insider プログラムのメンバーである必要があります。 Office Insider に参加するには、にアクセス [https://insider.office.com](https://insider.office.com) してください。 メンバーになったら、組織に適した展開方法を選択して、Office Insider ビルドを展開するための環境を準備します。 手順については、「 [Office Insider ビルドの展開の](https://insider.office.com/business/deploy)概要」を参照してください。

**Azure Information Protection**。 DKE は機密ラベルを使用し、Azure Information Protection を必要とします。

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>DKE で保護されたコンテンツを保存および表示するためにサポートされている環境

**サポートされるアプリケーション**。 Word、Excel、PowerPoint など、Windows の[エンタープライズクライアント用の Microsoft 365 アプリ](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)。

**オンラインコンテンツのサポート**。 Microsoft SharePoint と OneDrive for business の両方でオンラインで格納されたドキュメントやファイルはサポートされています。 暗号化されたコンテンツを電子メールで共有することはできますが、暗号化されたドキュメントやファイルをオンラインで表示することはできません。 代わりに、ローカルコンピューターのデスクトップアプリを使用して、保護されたコンテンツを表示する必要があります。

## <a name="about-this-public-preview-article"></a>このパブリックプレビューの記事について

二重キー暗号化を展開するための手順のいくつかを実行するには、いくつかの方法があります。 この記事では、より熟練していない管理者がサービスを正常に展開するための詳細な手順について説明します。 使いやすい場合は、独自のメソッドを使用することを選択できます。

この記事では、2重のキー暗号化サービスを Azure に展開する方法について手順を追って説明します。 このシナリオは、運用環境での可能性があるものではありません。 パブリックプレビューの場合、Azure を使用することで DKE を簡単に展開できます。 Azure に展開すると、すぐに二重キー暗号化を使い始めることができます。

ネットワーク上または別のプロバイダーを使用して、サービスをローカルに展開することができます。 キーストアは、その場所に適したメソッドを使用して公開する必要があります。

## <a name="deploy-double-key-encryption"></a>二重キー暗号化の展開

この記事と展開ビデオでは、DKE サービスの展開先として Azure を使用します。 別の場所に展開している場合は、独自の値を指定する必要があります。

この記事で説明する概念の詳細な手順については、「[二重キー暗号化展開ビデオ](https://youtu.be/vDWfHN_kygg)」をご覧ください。 ビデオの完了に約18分かかります。

次の一般的な手順に従って、組織のために二重キー暗号化を設定します。

1. [必要なソフトウェアをインストールする](#install-software-prerequisites)
1. [二重キー暗号化 GitHub リポジトリのクローンを作成する](#clone-the-dke-github-repository)
1. [アプリケーションの設定を変更する](#modify-application-settings)
1. [テストキーを生成する](#generate-test-keys)
1. [プロジェクトをビルドする](#build-the-project)
1. [キーストアを発行する](#publish-the-key-store)
1. [展開を検証する](#validate-your-deployment)
1. [キーストアを登録する](#register-your-key-store)
1. [秘密度ラベルを作成する](#create-labels-using-dke)

完了すると、DKE を使用してドキュメントやファイルを暗号化できます。 詳細については、「 [Office のファイルと電子メールに機密ラベルを適用する](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)」を参照してください。

### <a name="install-software-prerequisites"></a>必要なソフトウェアをインストールする

二重キー暗号化の前提条件となるソフトウェアは2種類あります。

- [二重キー暗号化サービスの前提条件](#double-key-encryption-service-prerequisites)
- [クライアントコンピューターの二重キー暗号化の前提条件](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a>二重キー暗号化サービスの前提条件

これらの必須コンポーネントを、DKE サービスをインストールするコンピューターにインストールします。

**.Net Core 3.1 SDK**。 SDK をダウンロードしてインストールします。 [.Net Core 3.1 をダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)します。

**Visual Studio Code**。 から Visual Studio コードをダウンロード [https://code.visualstudio.com/](https://code.visualstudio.com) します。 インストールされたら、Visual Studio Code を実行し、[**ビュー**拡張] を選択し \> **Extensions**ます。 これらの拡張機能をインストールします。

- Visual Studio Code の C#

- NuGet パッケージマネージャー

**Microsoft Office Insider**。 少なくとも1つの[展開方法](https://insider.office.com/business/deploy)を設定します。

**Git リソース**。 次のいずれかをダウンロードしてインストールします。

- [Git](https://git-scm.com/downloads)

- [GitHub デスクトップ](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL**DKE の展開後に[テストキーを生成](#generate-test-keys)するには、 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)がインストールされている必要があります。 環境変数のパスから適切に呼び出していることを確認してください。 たとえば、詳細については、「」の「インストールディレクトリをパスに追加する」を参照してください https://www.osradar.com/install-openssl-windows/ 。

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a>クライアントコンピューターの二重キー暗号化の前提条件

保護されたドキュメントを保護して使用する各クライアントコンピューターにこれらの必須コンポーネントをインストールします。

**Microsoft Office**バージョン * 12711 以降。

**Azure Information Protection クライアント**バージョン2.7.93.0 またはそれ以降のラベルを統合しています。 [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)から統合ラベルクライアントをダウンロードしてインストールします。

### <a name="clone-the-dke-github-repository"></a>DKE GitHub リポジトリのクローンを作成する

Microsoft は、GitHub リポジトリに DKE ソースファイルを提供しています。 リポジトリを複製して、組織の使用に合わせてプロジェクトをローカルに構築します。 DKE GitHub リポジトリは、にあり [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) ます。

次の手順は、経験のない git または Visual Studio Code ユーザーを対象としています。

1. ブラウザーで、次のように移動します。[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)

1. 画面の右側にある [**コード**] を選択します。 使用しているバージョンの UI には、[**クローン] または [ダウンロード**] ボタンが表示される場合があります。 次に、表示されたドロップダウンで、[コピー] アイコンを選択して、URL をクリップボードにコピーします。

    次に例を示します。

   ![GitHub から二重キー暗号化サービスリポジトリを複製する](../media/dke-clone.png)

3. Visual Studio Code で、[ **View** \> **Command Palette** ] を選択し、[ **Git: Clone**] を選択します。 一覧のオプションに移動するには、入力を開始して `git: clone` エントリをフィルター処理し、ドロップダウンから選択します。 次に例を示します。

   ![Visual Studio Code GIT: Clone オプション](../media/dke-vscode-clone.png)

4. テキストボックスに、Git からコピーした URL を貼り付けて、[ **GitHub から複製**] を選択します。

5. 表示される **[フォルダーの選択**] ダイアログで、リポジトリを格納する場所を参照して選択します。 プロンプトで、[**開く**] を選択します。

    リポジトリは Visual Studio Code で開かれ、左下に現在の Git ブランチが表示されます。 ブランチは**master**である必要があります。

    次に例を示します。

   ![Visual Studio Code master 分岐](../media/dke-vscode-master.png)

6. [単語**マスター** ] を選択し、分岐の一覧から [ **public_preview** ] を選択します。

   > [!IMPORTANT]
   > Public_preview ブランチを選択すると、プロジェクトをビルドするための適切なファイルがあることが確認されます。 適切なブランチを選択しない場合、展開は失敗します。

これで、DKE ソースリポジトリがローカルに設定されました。 次に、組織の[アプリケーション設定を変更](#modify-application-settings)します。

### <a name="modify-application-settings"></a>アプリケーションの設定を変更する

DKE サービスを展開するには、次の種類のアプリケーション設定を変更する必要があります。

- [キーアクセス設定](#key-access-settings)
- [テナントとキーの設定](#tenant-and-key-settings)

[ファイル] の appsettings.jsで、アプリケーションの設定を変更します。 このファイルは、DoubleKeyEncryptionService\src\customer-key-store. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。 たとえば、次の図に示すように、Visual Studio Code でファイルを参照できます。

![DKE のファイルの appsettings.jsを検索します。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>キーアクセス設定

メールまたはロールの承認を使用するかどうかを選択します。 DKE は、一度に1つの認証方法のみをサポートします。

- **電子メールの承認**。 組織は、電子メールアドレスのみに基づいてキーへのアクセスを承認できます。

- **役割の承認**。 組織は、Active Directory グループに基づいてキーへのアクセスを承認でき、web サービスが LDAP を照会できるようにする必要があります。

**電子メール認証を使用して DKE のキーアクセス設定を設定するには**

1. ファイル**でappsettings.js**を開き、設定を探し `AuthorizedEmailAddress` ます。

2. 承認するメールアドレスを追加します。 複数の電子メールアドレスは、二重引用符とコンマで区切ります。 次に例を示します。

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. 設定を検索 `LDAPPath` し、 `If role authorization is used then this is the LDAP path` 二重引用符の間のテキストを削除します。 二重引用符はそのままにします。 完了すると、設定は次のようになります。

   ```json
   "LDAPPath": ""
   ```

4. 設定を検索 `AuthorizedRoles` し、行全体を削除します。

このイメージは、電子メールの承認用に正しく書式設定されたファイル**のappsettings.js**を示しています。

   ![電子メール認証方法が表示されているファイルの appsettings.js](../media/dke-email-accesssetting.png)

**ロール認証を使用して DKE のキーアクセス設定を設定するには**

1. ファイル**でappsettings.js**を開き、設定を探し `AuthorizedRoles` ます。

2. 承認する Active Directory グループ名を追加します。 複数のグループ名は、二重引用符とコンマで区切ります。 次に例を示します。

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. `LDAPPath`設定を見つけて、Active Directory ドメインを追加します。 次に例を示します。

   ```json
   "LDAPPath": "contoso.com"
   ```

4. 設定を検索 `AuthorizedEmailAddress` し、行全体を削除します。

このイメージは、役割承認用に正しく書式設定されたファイル**のappsettings.js**を示しています。

   ![ロール認証方法が表示されているファイルの appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>テナントとキーの設定

DKE テナントとキー設定は、ファイルの**appsettings.js**にあります。

**DKE のテナントとキー設定を構成するには**

1. ファイル**でappsettings.js**を開きます。

2. `ValidIssuers`設定を見つけて、 `<tenantid>` テナント ID に置き換えます。 Azure ポータルに移動して、[テナントのプロパティ](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)を表示することによって、テナント ID を見つけることができます。 次に例を示します。

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

を探し `JwtAudience` ます。 を、 `<yourhostname>` DKE サービスが実行されるコンピューターのホスト名に置き換えます。 次に例を示します。



  > [!IMPORTANT]
  > の値は、 `JwtAudience` ホストの名前と*正確*に一致している必要があります。 デバッグ中に**localhost: 5001**を使用することができます。 ただし、デバッグを完了したら、この値をサーバーのホスト名に更新するようにしてください。

- `TestKeys:Name`. キーの名前を入力します。 例: `TestKey1`
- `TestKeys:Id`. GUID を作成し、値として入力し `TestKeys:ID` ます。 たとえば、`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE` などです。 [ONLINE Guid ジェネレーター](https://guidgenerator.com/)のようなサイトを使用して、guid をランダムに生成することができます。

この画像**にはappsettings.js**のテナントとキーの設定の正しい形式が表示されます。 `LDAPPath`は、ロールの承認のために構成されています。

![ファイルの appsettings.jsの DKE の正しいテナントとキー設定を示します。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>テストキーを生成する

アプリケーション設定を定義したら、パブリックおよびプライベートのテストキーを生成する準備ができています。

キーを生成するには

1. Windows の [スタート] メニューから、OpenSSL コマンドプロンプトを実行します。

1. テストキーを保存するフォルダーに移動します。 このタスクの手順を完了することによって作成したファイルは、同じフォルダーに格納されます。

1. 新しいテストキーを生成します。

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. 秘密キーを生成します。

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. 公開キーを生成します。

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. テキストエディターで、 **pubkeyonly**を開きます。 最初と最後の行を除く、 **pubkeyonly**のすべてのコンテンツを `PublicPem` ファイルの**appsettings.js**のセクションにコピーします。

1. テキストエディターで、 **privkeynopass pem**を開きます。 最初の行と最後の行を除いて、 **privkeynopass**のすべてのコンテンツを `PrivatePem` ファイルの**appsettings.js**のセクションにコピーします。

1. セクションとセクションの両方で空白スペースと改行を削除し `PublicPem` `PrivatePem` ます。

    > [!IMPORTANT]
    > このコンテンツをコピーする場合は、PEM データを削除しないでください。

1. Visual Studio Code で、 **Startup.cs**ファイルを参照します。 このファイルは、DoubleKeyEncryptionService\src\customer-key-store\. でローカルに複製した DoubleKeyEncryptionService リポジトリにあります。

2. 次の行を見つけます。

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. これらの行を次のテキストに置き換えます。

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   最終結果は次のようになります。

   ![パブリックプレビュー用の startup.cs ファイル](../media/dke-startupcs-usetestkeys.png)

これで[、DKE プロジェクトを構築](#build-the-project)する準備ができました。

### <a name="build-the-project"></a>プロジェクトをビルドする

次の手順を使用して、ローカルに DKE プロジェクトをビルドします。

1. Visual Studio Code の dke サービスリポジトリで、[コマンドパレットの**表示**] を選択し、 \> **Command Palette**プロンプトで「 **build** 」と入力します。

1. リストから、[**タスク: ビルドタスクの実行**] を選択します。

   ビルドタスクが見つからない場合は、[**ビルドタスクの構成**] を選択し、次のように .net コア用のタスクを作成します。

   ![.NET の不明なビルドタスクを構成する](../media/dke-configurebuildtask.png)

   1. [**テンプレートから tasks.jsを作成**] を選択します。

   ![DKE テンプレートからファイルに tasks.jsを作成する](../media/dke-createtasksjsonfromtemplate.png)

   2. テンプレートの種類の一覧から [ **.Net Core**] を選択します。

   ![DKE テンプレートからファイルに tasks.jsを作成する](../media/dke-tasksjsontemplate.png)

   3. [ビルド] セクションで、**顧客キーストア**ファイルへのパスを見つけます。 存在しない場合は、次の行を追加します。

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. ビルドを再度実行します。

1. 出力ウィンドウに赤のエラーが表示されないことを確認します。

   赤のエラーがある場合は、コンソール出力を確認します。 上記の手順がすべて正常に完了し、適切なビルドバージョンが存在することを確認してください。

2. [**実行** \> **開始デバッグ**] を選択してプロセスをデバッグします。 環境を選択するように求めるメッセージが表示されたら、[ **.net core**] を選択します。

通常、.net コアデバッガーは ' ' ' に起動 https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 し、スラッシュ (/) とキーの名前を追加します。 次に例を示します。

```https
https://localhost:5001/TestKey1
```

キーは JSON 形式で表示されます。

セットアップが完了しました。 キーストアを発行する前に、JwtAudience の設定 appsettings.jsで、[] 設定で、[ホスト名] の値が App Service ホスト名と正確に一致していることを確認してください。 ビルドのトラブルシューティングを行うために、localhost に変更した可能性があります。

### <a name="publish-the-key-store"></a>キーストアを発行する

キーストアを発行するには、DKE 展開をホストする Azure App Service インスタンスを作成します。 次に、生成されたキーを Azure に発行します。

**DKE 展開をホストするための Azure Web App インスタンスを作成するには**

1. ブラウザーで、 [Microsoft Azure ポータル](https://ms.portal.azure.com)にサインインし、[ **App Services**追加] に移動し  >  **Add**ます。

1. サブスクリプションとリソースグループを選択し、インスタンスの詳細を定義します。

    - DKE サービスをインストールするコンピューターのホスト名を入力します。 [ファイルのappsettings.js] の[**[**](#tenant-and-key-settings) JwtAudience] 設定に定義されている名前と同じ名前であることを確認してください。 名前に指定する値は WebAppInstanceName でもあります。

    - [**発行**] で、[**コード**] を選択し、[**ランタイムスタック**] で [ **.net Core 3.1**] を選択します。

    次に例を示します。

   ![アプリサービスを追加する](../media/dke-azure-add-app-service.png)

1. ページの下部にある [**レビュー + 作成**] を選択し、[**追加**] を選択します。

1. 生成されたキーを Azure に公開するには、次のいずれかの操作を行います。

    - [ZipDeployUI を使用して発行する](#publish-via-zipdeployui)
    - [FTP を使用した発行](#publish-via-ftp)
    - [Visual Studio 2019 以降での発行](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [オンプレミスのシステムに発行する](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > 他の方法でキーを展開することもできます。 組織に最も適した方法を選択します。

    > [!TIP]
    > [Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/)と[オンプレミスシステム](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)への発行については、 [ASP .net ドキュメント](https://docs.microsoft.com/aspnet/core/)を参照してください。 これらの方法のいずれかを使用する場合は、操作が完了したら簡単に戻ることができるように、別のタブで手順を開きます。

#### <a name="publish-via-zipdeployui"></a>ZipDeployUI を使用して発行する

1. `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI` に移動します。

    例: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

1. キーストアのコードベースで、 **customer-key-store\src\customer-key-store**フォルダーに移動し、このフォルダーに**顧客キーストア**ファイルが含まれていることを確認します。

1. 実行: **dotnet publish**

     [出力] ウィンドウには、発行が展開されたディレクトリが表示されます。

    例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. Publish ディレクトリ内のすべてのファイルを .zip ファイルに送信します。 .Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。

1. 先ほど開いた ZipDeployUI サイトに、作成した .zip ファイルをドラッグアンドドロップします。 例: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

DKE が展開されており、作成したテストキーを参照することができます。 引き続き「[展開を検証](#validate-your-deployment)する」を参照してください。

#### <a name="publish-via-ftp"></a>FTP を使用した発行

1. [上記の手順](#publish-the-key-store)で作成した App Service に接続します。

    ブラウザーで、「 **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**」に移動します。

1. ローカルファイルに表示される接続文字列をコピーします。 これらの文字列を使用して Web App サービスに接続し、FTP を使用してファイルをアップロードします。

    次に例を示します。

   ![FTP ダッシュボードから接続文字列をコピーする](../media/dke-ftp-dashboard.png)

1. キーの格納用のコードベースで、 **customer-key-store\src\customer-key-store ディレクトリ**に移動します。

1. このディレクトリに、**顧客キーストアの .csproj**ファイルが含まれていることを確認します。

1. 実行: **dotnet publish**

    この出力には、発行が展開されたディレクトリが含まれています。

    例: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. 発行ディレクトリ内のすべてのファイルを zip ファイルに送信します。 .Zip ファイルを作成するときは、ディレクトリ内のすべてのファイルが .zip ファイルのルートレベルにあることを確認してください。

1. FTP クライアントから、コピーした接続情報を使用して App Service に接続します。 前の手順で作成した .zip ファイルを Web アプリのルートディレクトリにアップロードします。

DKE が展開されており、作成したテストキーを参照することができます。 次に、[展開を検証](#validate-your-deployment)します。

### <a name="validate-your-deployment"></a>展開を検証する

前述の方法のいずれかを使用して DKE を展開した後、展開とキーストアの設定を検証します。

次を実行します:  

src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey

次に例を示します。

key_store_tester.ps1https://mycustomerkeystore.com/mykey

出力にエラーが表示されないことを確認します。 準備が整ったら、[キーストアを登録](#register-your-key-store)します。

## <a name="register-your-key-store"></a>キーストアを登録する

次の手順を実行すると、キーストアを登録できるようになります。 ラベルの作成を開始する前に、DKE を展開するための最後の手順として、キーストアの登録が必要になります。

キーストアを登録するには、次のようにします。

1. ブラウザーで、 [Microsoft Azure portal](https://ms.portal.azure.com/)を開き、[**すべてのサービス** \> **id** \> **アプリの登録**] に移動します。

2. [**新しい登録**] を選択し、わかりやすい名前を入力します。

3. 表示されているオプションから、アカウントの種類を選択します。

    **Onmicrosoft.com**などの非ユーザー設定ドメインを使用して Microsoft Azure を使用している場合は、[**この組織ディレクトリ内のアカウントのみ (microsoft のみ)** ] を選択します。

    次に例を示します。

   ![新しいアプリの登録](../media/dke-app-registration.png)

4. ページの下部にある [**登録**] を選択して、新しいアプリの登録を作成します。

5. 新しいアプリの登録で、左側のウィンドウの [**管理**] で [**認証**] を選択します。

6. [**プラットフォームの追加**] を選択します。
 
7. [**プラットフォームの構成**] ポップアップで、[ **Web**] を選択します。
 
8. [**リダイレクト uri**] で、二重キー暗号化サービスの URI を入力します。 ホスト名とドメインの両方を含む、App Service の URL を入力します。

    例: https://mycustomerkeystoretest.com

    - 入力する URL は、キーストアが展開されているホスト名と一致している必要があります。
    - Visual Studio を使用してローカルでテストしている場合は、を使用 **https://localhost:5001** します。
    - すべての場合において、スキームは**https**である必要があります。

    ホスト名が App Service ホスト名と正確に一致していることを確認してください。 ビルドをトラブルシューティングするために、に変更した可能性があり `localhost` ます。 **appsettings.js**の場合、この値は、に設定したホスト名です `JwtAudience` 。

6. [**暗黙的な付与**] で、[ **ID トークン**] チェックボックスをオンにします。

1. **[保存]** を選択し、変更内容を保存します。

7. 左側のウィンドウで、[ **API の公開**] を選択し、[アプリケーション ID URI] の横にある [**設定**] を選択します。

9. 引き続き [ **api の公開**] ページで、[**この api によって定義されるスコープ**] 領域の [**範囲の追加**] を選択します。 新しい範囲の場合:

    1. スコープ名を**user_impersonation**として定義します。

    2. 同意できる管理者とユーザーを選択します。

    3. 残りの必要な値を定義します。

    4. [**スコープの追加**] を選択します。

    上部にある [**保存**] を選択して変更を保存します。

10. 引き続き [ **API の公開**] ページの [承認された**クライアントアプリケーション**] 領域で、[**クライアントアプリケーションの追加**] を選択します。

    新しいクライアントアプリケーションの場合:

    1. クライアント ID を**d3590ed6-52b3-4102-aeff-aad2292ab01c**として定義します。 この値は Microsoft Office クライアント ID であり、Office はキーストアのアクセストークンを取得することができます。

    2. [**承認**されたスコープ] で、 **user_impersonation**スコープを選択します。

    3. **[アプリケーションの追加]** を選択します。

    4. 上部にある [**保存**] を選択して変更を保存します。

これで、DKE キーストアが登録されました。 引き続き、 [DKE を使用してラベルを作成](#create-labels-using-dke)します。

## <a name="create-labels-using-dke"></a>DKE を使用してラベルを作成する

Microsoft 365 コンプライアンスセンターで、別の方法として、新しい機密ラベルを作成し、暗号化を適用します。 [ **2 重のキー暗号化を使用する**] を選択し、キーのエンドポイント URL を入力します。

次に例を示します。

![Microsoft 365 コンプライアンスセンターで [二重のキー暗号化を使用する] を選択します。](../media/dke-use-dke.png)

追加した DKE ラベルは、Microsoft 365 Apps for enterprise の最新バージョンのユーザーに対して表示され始めます。

> [!NOTE]
> クライアントが新しいラベルで更新されるまで、最大24時間かかる場合があります。

### <a name="enable-dke-in-your-client"></a>クライアントで DKE を有効にする

次のレジストリキーを追加して、クライアントに対して DKE を有効にします。

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
