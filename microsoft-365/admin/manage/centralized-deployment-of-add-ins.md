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
description: テナントとユーザーが要件を満たしているかどうかを判断し、一元展開を使用して Office アドインを展開できるようにします。
ms.openlocfilehash: f6dd5972dedebfa21d5770a789ae9477c8263801
ms.sourcegitcommit: 13a1199fbfeb329da77ce87b2781d5cc77e4a201
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67037601"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>アドインの一元展開が組織で機能するかどうかを確認する

一元展開は、ほとんどのお客様が組織内のユーザーとグループに Office アドインを展開するための、推奨される最も機能豊富な方法です。 管理者の場合は、このガイダンスを使用して、組織とユーザーが要件を満たしているかどうかを判断し、一元展開を使用できるようにします。

一元展開には、次のような利点があります。

- 管理者は、アドインをユーザー、グループを介して複数のユーザー、または組織内のすべてのユーザーに直接展開して割り当てることができます (詳細については、「管理要件」セクションを参照)。
- 関連する Office アプリケーションが起動すると、アドインが自動的にダウンロードされます。 アドインがアドイン コマンドをサポートしている場合、アドインは Office アプリケーション内のリボンに自動的に表示されます。
- 管理者がアドインをオフまたは削除した場合、またはユーザーが Azure Active Directory またはアドインが割り当てられているグループから削除された場合、アドインはユーザーに表示されなくなります。

一元展開では、Windows、Mac、Online Office の 3 つのデスクトップ プラットフォームがサポートされています。 一元展開では、iOS と Android もサポートされます (Outlook Mobile アドインのみ)。

アドインがすべてのユーザーのクライアントに表示されるまでには、最大で 24 時間かかる場合があります。

## <a name="before-you-begin"></a>始める前に

アドインを一元的に展開するには、ユーザーが Microsoft 365 Business ライセンス (Business Basic、Business Standard、Business Premium)、Office 365 Enterprise ライセンス (E1/E3/E5/F3)、またはMicrosoft 365 Enterprise ライセンス (E3/E5/F3) (組織 ID を使用して Office にサインイン) を使用している必要があります。Office 365 Education ライセンス (A1/A3/A5)、またはMicrosoft 365 Education ライセンス (A3/A5)、Exchange OnlineおよびアクティブなExchange Online メールボックスがあります。 サブスクリプション ディレクトリは、Azure Active Directory 内にあるか、Azure Active Directory にフェデレーションされている必要があります。
Office と Exchange の特定の要件を以下で確認することも、 [一元展開互換性チェッカー](#centralized-deployment-compatibility-checker)を使用することもできます。

一元展開は、次の機能をサポートしていません。

- Office MSI バージョンを対象とするアドイン (Outlook 2016を除く)
- オンプレミスのディレクトリ サービス
- Exchange On-Prem メールボックスへのアドインの展開
- SharePoint に展開するアドイン
- Teams アプリ
- コンポーネント オブジェクト モデル (COM) または Visual Studio Tools for Office (VSTO) アドインのデプロイ。
- SKU などのExchange Onlineを含まない Microsoft 365 の展開: ビジネス向けのMicrosoft 365 Appsとエンタープライズ向けのMicrosoft 365 Apps。

### <a name="office-requirements"></a>Office の要件

- Word、Excel、PowerPoint アドインの場合、ユーザーは次のいずれかを使用している必要があります。
  - Windows デバイスのバージョン 1704 以降の Microsoft 365 Business ライセンス (Business Basic、Business Standard、Business Premium)、Office 365 Enterprise ライセンス (E1/E3/E5/F3)、またはMicrosoft 365 Enterprise ライセンス (E3/E5/F3)。
  - Mac バージョン 15.34 以降。

- Outlook の場合、ユーザーは次のいずれかを使用している必要があります。
  - バージョン 1701 以降の Microsoft 365 Business ライセンス (Business Basic、Business Standard、Business Premium)、Office 365 Enterprise ライセンス (E1/E3/E5/F3)、またはMicrosoft 365 Enterprise ライセンス (E3/E5/F3)。
  - バージョン 1808 以降のOffice Professional Plus 2019または 2019 Office Standard。
  - Office Professional Plus 2016 (MSI) または Office Standard 2016 (MSI) のバージョン 16.0.4494.1000 以降\*
  - バージョン 15.0.4937.1000 以降の Office Professional Plus 2013 (MSI) または Office Standard 2013 (MSI)\*
  - バージョン 16.0.9318.1000 以降のOffice 2016 for Mac
- バージョン 2.75.0 以降の Outlook Mobile for iOS
- バージョン 2.2.145 以降の Outlook Mobile for Android

    *MSI バージョンの Outlook では、管理者がインストールしたアドインが適切な Outlook リボンに表示され、"マイ アドイン" セクションは表示されません。

### <a name="exchange-online-requirements"></a>Exchange Online要件

Microsoft Exchange は、組織のテナント内にアドイン マニフェストを格納します。 アドインを展開する管理者と、それらのアドインを受け取るユーザーは、OAuth 認証をサポートするバージョンのExchange Online上にある必要があります。

組織の Exchange 管理者に、どの構成を使用できるのかを確認してください。ユーザーごとの OAuth 認証接続は、[Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell コマンドレットを使用して、検証できます。

### <a name="admin-requirements"></a>管理者の要件

一元展開を使用してアドインを展開するには、組織内のグローバル管理者または Exchange 管理者である必要があります。

> [!NOTE]
> 次の図に示すように、 **アプリケーション管理者** ロールが追加された場合、または Azure Active Directory 管理センターで **アプリ登録** プロパティが true に設定されている場合、Exchange 管理者はアドインをデプロイできます。
>
> ![image](https://user-images.githubusercontent.com/89943918/144516704-8874a10d-b540-41f3-ae9d-c07a8d7e143f.png)

### <a name="centralized-deployment-compatibility-checker"></a>一元展開互換性チェッカー

一元展開互換性チェッカーを使用して、テナントのユーザーが Word、Excel、PowerPoint の一元展開を使用するように設定されているかどうかを確認できます。 Outlook のサポートには互換性チェックは必要ありません。 [互換性チェック](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)をダウンロードします。

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
- Office プラン - ライセンスが付与されている Office のプラン
- ライセンス認証された Office - Office をライセンス認証している場合
- サポートされているメールボックス - OAuth 対応メールボックスを使用している場合

Microsoft 365 レポートに実際のユーザー名ではなく匿名ユーザー名が表示される場合は、Microsoft 365 管理センターのレポート設定を変更して、この問題を解決します。 詳細な手順については、「 [Microsoft 365 レポートに実際のユーザー名ではなく匿名ユーザー名が表示](/office365/troubleshoot/miscellaneous/reports-show-anonymous-user-name)されている」を参照してください。

> [!NOTE]
> 中央展開 PowerShell モジュールを使用する場合、多要素認証はサポートされません。 モジュールは基本認証でのみ機能します。

## <a name="user-and-group-assignments"></a>ユーザーとグループの割り当て

一元配置機能は、現在、Microsoft 365 グループ、配布リスト、動的グループ、セキュリティ グループなど、Azure Active Directory でサポートされているグループの大半をサポートしています。

> [!NOTE]
> メールが有効ではないセキュリティ グループは、現段階ではサポートされていません。

一元展開では、テナント内の個々のユーザー、グループ、および全員への割り当てがサポートされます。 一元展開では、最上位のグループまたは親グループのないグループのユーザーがサポートされますが、入れ子になったグループまたは親グループを持つグループのユーザーはサポートされません。

次の例では、Sandra、Sheila、「営業部門」のグループがアドインに割り当てられています。「西海岸営業部門」は入れ子のグループのため、Bert と Fred はアドインに割り当てられていません。

![MicrosoftTeams-image](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>グループにネストされたグループが含まれているかどうかを調べる

グループにネストされたグループが含まれているかどうかを調べる最も簡単な方法は、Outlook 内のグループの連絡先カードを確認することです。 電子メールの **[To** ] フィールドにグループ名を入力し、解決時にグループ名を選択すると、ユーザーまたは入れ子になったグループが含まれているかどうかが表示されます。 次の例では、「テスト グループ」での Outlook 情報先カードの [ **メンバー**] タブには、ユーザーはなく、2 つのサブ グループのみが表示されています。

![Outlook 連絡先カードの [メンバー] タブ。](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

反対のクエリを実行できます。グループを解決して、任意のグループのユーザーがいないかどうかを表示します。次の例では、「サブ グループ 1」が「テスト グループ」のメンバーである Outlook 情報先カードの [ **メンバーシップ**] タブの下に表示されます。

![Outlook 連絡先カードの [メンバーシップ] タブ。](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

または、Azure Active Directory Graph API でクエリを実行して、グループ内でのグループ一覧を見つけます。 詳細については、「[グループに対する操作」を参照してください|Graph APIリファレンス](/previous-versions/azure/ad/graph/api/groups-operations)。

### <a name="contacting-microsoft-for-support"></a>Microsoft に連絡してサポートを受ける

一元的に展開された Office アプリ (Word、Excel など) の使用中にアドインの読み込みに関する問題が発生した場合は、Microsoft サポートに問い合わせる必要があります ([方法を確認してください](../../business-video/get-help-support.md)。 Microsoft 365 環境に関する次の情報をサポート チケットに入力します。

|プラットフォーム|デバッグ情報|
|---|---|
|事業所|Charles/Fiddler ログ <br/> テナント ID ([方法については、こちらを参照](/onedrive/find-your-office-365-tenant-id)してください) <br/> Correlationid。 いずれかの Office ページのソースを表示し、関連付け ID の値を探して、サポートするために送信します。  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">` <br/> `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`|
|リッチ クライアント (Windows、Mac)|Charles/Fiddler ログ <br/> クライアント アプリのビルド番号 (ファイル **/アカウント** のスクリーンショットとして望ましい)|

## <a name="related-content"></a>関連コンテンツ

[管理センターにアドインをデプロイする](../manage/manage-deployment-of-add-ins.md) (記事)\
[管理センターでアドインを管理する](manage-addins-in-the-admin-center.md) (記事)\
[一元展開に関する FAQ](../manage/centralized-deployment-faq.yml) (記事)\
[ビジネス ユーザー向けの Microsoft 365 を最新の Office クライアントにアップグレードする](../setup/upgrade-users-to-latest-office-client.md) (記事)
