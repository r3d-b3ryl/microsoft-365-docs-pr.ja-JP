---
title: アドインの一元展開が組織で機能するかどうかを確認する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: テナントとユーザーが要件を満たしているかどうかを判断し、一元展開を使用してアドインOffice展開できるようにします。
ms.openlocfilehash: 4d135e76034880e1419e296f2c201536be98b4bc
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093770"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>アドインの一元展開が組織で機能するかどうかを確認する

一元展開は、ほとんどのお客様が組織内のユーザーとグループにOfficeアドインを展開するために推奨され、最も機能が豊富な方法です。 管理者の場合は、このガイダンスを使用して、組織とユーザーが要件を満たしているかどうかを判断し、一元展開を使用できるようにします。

一元展開には、次のような利点があります。

- 管理者は、アドインをユーザー、グループを介して複数のユーザー、または組織内のすべてのユーザーに直接展開して割り当てることができます (詳細については、「管理者要件」セクションを参照してください)。
- 関連するOffice アプリケーションが起動すると、アドインが自動的にダウンロードされます。 アドインがアドイン コマンドをサポートしている場合、アドインはOffice アプリケーション内のリボンに自動的に表示されます。
- 管理者がアドインをオフまたは削除した場合、またはアドインが割り当てられているAzure Active Directoryまたはグループからユーザーが削除された場合、アドインはユーザーに表示されなくなります。

一元展開では、Mac と Online Office アプリWindows 3 つのデスクトップ プラットフォームがサポートされます。 一元展開では、iOS と Android もサポートされます (モバイル アドインのみOutlook)。

アドインがすべてのユーザーのクライアントに表示されるまでには、最大で 24 時間かかる場合があります。

## <a name="before-you-begin"></a>開始する前に

アドインを一元的に展開するには、ユーザーが Microsoft 365 Business ライセンス (Business Basic、Business Standard、Business プレミアム)、Office 365 Enterprise ライセンス (E1/E3/E5/F3)、またはMicrosoft 365 Enterprise ライセンス (E3/E5/F3) を使用している必要があります (Office 組織 ID、Office 365 Education ライセンス (A1/A3/A5)、またはMicrosoft 365 Education ライセンス (A3/A5)、Exchange OnlineおよびアクティブなExchange Online メールボックスを使用します。 サブスクリプション ディレクトリは、Azure Active Directoryに含まれるか、フェデレーションされている必要があります。
以下のOfficeとExchangeに関する特定の要件を確認することも、[一元配置互換性チェッカー](#centralized-deployment-compatibility-checker)を使用することもできます。

一元展開は、次の機能をサポートしていません。

- MSI バージョンをターゲットとするアドインOffice (Outlook 2016を除く)
- オンプレミスのディレクトリ サービス
- Exchange On-Prem メールボックスへのアドインの展開
- SharePoint に展開するアドイン
- Teams アプリ
- コンポーネント オブジェクト モデル (COM) またはVisual Studio Tools for Office (VSTO) アドインのデプロイ。
- SKU などのExchange Onlineを含まないMicrosoft 365のデプロイ: ビジネス向けのMicrosoft 365 AppsとEnterpriseのMicrosoft 365 Apps。

### <a name="office-requirements"></a>Office要件

- Word、Excel、PowerPoint アドインの場合、ユーザーは次のいずれかを使用している必要があります。
  - Windows デバイスのバージョン 1704 以降の Microsoft 365 Business ライセンス (Business Basic、Business Standard、Business プレミアム)、Office 365 Enterprise ライセンス (E1/E3/E5/F3)、またはMicrosoft 365 Enterprise ライセンス (E3/E5/F3)。
  - Mac バージョン 15.34 以降。

- Outlookの場合、ユーザーは次のいずれかを使用している必要があります。
  - バージョン 1701 以降の Microsoft 365 Business ライセンス (Business Basic、Business Standard、Business プレミアム)、Office 365 Enterprise ライセンス (E1/E3/E5/F3)、またはMicrosoft 365 Enterprise ライセンス (E3/E5/F3)。
  - バージョン 1808 以降のOffice Professional Plus 2019または 2019 Office Standard。
  - Office Professional Plus 2016 (MSI) または Office Standard 2016 (MSI) のバージョン 16.0.4494.1000 以降\*
  - バージョン 15.0.4937.1000 以降の Office Professional Plus 2013 (MSI) または Office Standard 2013 (MSI)\*
  - バージョン 16.0.9318.1000 以降のOffice 2016 for Mac
- iOS 用モバイルのバージョン 2.75.0 以降Outlook
- Android 用モバイルのバージョン 2.2.145 以降Outlook

    *MSI バージョンのOutlookでは、管理者がインストールしたアドインが適切なOutlookリボンに表示され、[マイ アドイン] セクションは表示されません。

### <a name="exchange-online-requirements"></a>Exchange Online要件

Microsoft Exchange は、組織のテナント内にアドイン マニフェストを格納します。 アドインを展開する管理者と、それらのアドインを受け取るユーザーは、OAuth 認証をサポートするバージョンのExchange Online上にある必要があります。

組織の Exchange 管理者に、どの構成を使用できるのかを確認してください。ユーザーごとの OAuth 認証接続は、[Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell コマンドレットを使用して、検証できます。

### <a name="admin-requirements"></a>管理者の要件

一元展開を使用してアドインを展開するには、組織内のグローバル管理者またはExchange管理者である必要があります。

> [!NOTE]
> Exchange管理者は、**アプリケーション管理者** ロールが追加された場合、または次の図に示すように、管理センターで **App Registrations** プロパティが true に設定されている場合Azure Active Directoryアドインを展開できます。
>
> ![image](https://user-images.githubusercontent.com/89943918/144516704-8874a10d-b540-41f3-ae9d-c07a8d7e143f.png)

### <a name="centralized-deployment-compatibility-checker"></a>一元展開互換性チェッカー

一元展開互換性チェッカーを使用すると、テナント上のユーザーが Word、Excel、PowerPointの一元展開を使用するように設定されているかどうかを確認できます。 互換性チェックは、Outlookサポートには必要ありません。 [互換性チェック](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)をダウンロードします。

#### <a name="run-the-compatibility-checker"></a>互換性チェックを実行する

1. 管理者特権のPowerShell.exe ウィンドウを開始します。

2. 次のコマンドを実行します。

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. **Invoke-CompatibilityCheck** コマンドを実行します。

   ```powershell
   Invoke-CompatibilityCheck
   ```

   このコマンドを実行すると、 _TenantDomain_ ( _TailspinToysIncorporated.onmicrosoft.com_ など) と _TenantAdmin_ 資格情報 (グローバル管理者資格情報を使用) の入力を求め、同意を要求します。

   > [!NOTE]
   > テナントのユーザー数によって、チェックが完了するのに数分または数時間かかる場合があります。

ツールの実行が完了すると、コンマ区切り (.csv) 形式で出力ファイルが作成されます。 既定では、ファイルは **現在の作業ディレクトリ** に保存されます。 出力ファイルには、次の情報が含まれます。

- ユーザー名
- ユーザー ID (ユーザーのメール アドレス)
- 一元展開の準備完了 - 残りの項目が TRUE の場合
- Officeプラン - ライセンスが付与されているOfficeの計画
- ライセンス認証された Office - Office をライセンス認証している場合
- サポートされているメールボックス - OAuth 対応メールボックスを使用している場合

> [!NOTE]
> 中央展開 PowerShell モジュールを使用する場合、多要素認証はサポートされません。 モジュールは基本認証でのみ機能します。

## <a name="user-and-group-assignments"></a>ユーザーとグループの割り当て

一元展開機能は、現在、Microsoft 365 グループ、配布リスト、セキュリティ グループなど、Azure Active Directoryでサポートされているグループの大半をサポートしています。

> [!NOTE]
> メールが有効ではないセキュリティ グループは、現段階ではサポートされていません。

一元展開では、テナント内の個々のユーザー、グループ、および全員への割り当てがサポートされます。 一元展開では、最上位のグループまたは親グループのないグループのユーザーがサポートされますが、入れ子になったグループまたは親グループを持つグループのユーザーはサポートされません。

次の例では、Sandra、Sheila、「営業部門」のグループがアドインに割り当てられています。「西海岸営業部門」は入れ子のグループのため、Bert と Fred はアドインに割り当てられていません。

![MicrosoftTeams-image](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>グループにネストされたグループが含まれているかどうかを調べる

グループにネストされたグループが含まれているかどうかを調べる最も簡単な方法は、Outlook 内のグループの連絡先カードを確認することです。 電子メールの **[To** ] フィールドにグループ名を入力し、解決時にグループ名を選択すると、ユーザーまたは入れ子になったグループが含まれているかどうかが表示されます。 次の例では、「テスト グループ」での Outlook 情報先カードの [ **メンバー**] タブには、ユーザーはなく、2 つのサブ グループのみが表示されています。

![連絡先カードの [メンバー] タブOutlook表示されます。](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

反対のクエリを実行できます。グループを解決して、任意のグループのユーザーがいないかどうかを表示します。次の例では、「サブ グループ 1」が「テスト グループ」のメンバーである Outlook 情報先カードの [ **メンバーシップ**] タブの下に表示されます。

![Outlook連絡先カードの [メンバーシップ] タブ。](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

または、Azure Active Directory Graph API でクエリを実行して、グループ内でのグループ一覧を見つけます。 詳細については、「[グループに対する操作」を参照してください|Graph APIリファレンス](/previous-versions/azure/ad/graph/api/groups-operations)。

### <a name="contacting-microsoft-for-support"></a>Microsoft に連絡してサポートを受ける

Web 用のOffice アプリ (Word、Excelなど) を一元的に展開しているときにアドインの読み込みに関する問題が発生した場合は、Microsoft サポートに問い合わせる必要があります ([方法について説明](../../business-video/get-help-support.md)します。 サポート チケットでMicrosoft 365環境に関する次の情報を指定します。

|プラットフォーム|デバッグ情報|
|---|---|
|事業所|Charles/Fiddler ログ <br/> テナント ID ([方法については、こちらを参照](/onedrive/find-your-office-365-tenant-id)してください) <br/> Correlationid。 いずれかの Office ページのソースを表示し、関連付け ID の値を探して、サポートするために送信します。  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">` <br/> `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`|
|リッチ クライアント (Windows、Mac)|Charles/Fiddler ログ <br/> クライアント アプリのビルド番号 (ファイル **/アカウント** のスクリーンショットとして望ましい)|

## <a name="related-content"></a>関連コンテンツ

[管理センターにアドインをデプロイする](../manage/manage-deployment-of-add-ins.md) (記事)\
[管理センターでアドインを管理する](manage-addins-in-the-admin-center.md) (記事)\
[一元展開に関する FAQ](../manage/centralized-deployment-faq.yml) (記事)\
[ビジネス ユーザーのMicrosoft 365を最新のOffice クライアントにアップグレードする](../setup/upgrade-users-to-latest-office-client.md) (記事)
