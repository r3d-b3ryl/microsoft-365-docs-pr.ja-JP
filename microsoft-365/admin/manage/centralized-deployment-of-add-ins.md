---
title: 組織でアドインの集中展開が機能するかどうかを判断する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: テナントとユーザーが要件を満たしているか確認し、集中展開を使用してアドインをOfficeできます。
ms.openlocfilehash: c9f2879e989085042758cc1c5385bea45427e7ff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915460"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>組織でアドインの集中展開が機能するかどうかを判断する

集中展開は、ほとんどのお客様が組織内のユーザーやグループに Officeアドインを展開するための、推奨される機能豊富な方法です。 管理者の場合は、このガイダンスを使用して、組織とユーザーが要件を満たしていることを確認し、集中展開を使用できます。

一元展開には、次のような利点があります。
  
- グローバル管理者は、アドインをユーザーに直接割り当て、グループ経由で複数のユーザーに割り当て、組織内のすべてのユーザーに割り当てできます。
    
- 関連するアプリケーションOfficeすると、アドインが自動的にダウンロードされます。 アドインがアドイン コマンドをサポートしている場合、アドインは自動的にアドイン アプリケーション内のリボンにOfficeされます。
    
- 管理者がアドインをオフまたは削除した場合、またはユーザーが Azure Active Directory またはアドインが割り当てられているグループから削除された場合、ユーザーのアドインは表示されなくなりました。

集中展開では、Windows、Mac、および Online の 3 つのデスクトップ プラットフォームがサポートOfficeされます。 集中展開では、iOS と Android (Outlook Mobile アドインのみ) もサポートされています。

すべてのユーザーのクライアントにアドインが表示されるには、最大 24 時間かかる場合があります。
  
## <a name="requirements"></a>Requirements

アドインの一元展開では、ユーザーが Microsoft 365 Enterprise SKU E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business Premium (および組織 ID を使用して Office にサインイン) を使用し、Exchange Online およびアクティブな Exchange Online メールボックスを使用している必要があります。 サブスクリプション ディレクトリが Azure Active Directory に存在するか、Azure Active Directory にフェデレーションされている必要があります。
以下に示すアプリケーションと Exchange に関するOffice要件を確認したり、集中展開互換性チェッカー [を使用することができます](#centralized-deployment-compatibility-checker)。

一元展開は、次の機能をサポートしていません。
  
- Office 2013 の Word、Excel、または PowerPoint を対象とするアドイン 
- オンプレミスのディレクトリ サービス
- Exchange On-Prem メールボックスへのアドインの展開
- SharePoint に展開するアドイン  
- Teams アプリ
- コンポーネント オブジェクト モデル (COM) または Visual Studio (VSTO) アドインOfficeツールの展開。
- Sku などの Exchange Online を含む Microsoft 365 の展開: Microsoft 365 Apps for Business および Microsoft 365 Apps for Enterprise。

### <a name="office-requirements"></a>Office要件

- Word、Excel、および PowerPoint アドインの場合、ユーザーは次のいずれかを使用している必要があります。
  - Windows デバイスのバージョン 1704 以降の Microsoft 365 Enterprise SKU: E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business Premium。
  - Mac のバージョン 15.34 以降。

- Outlook の場合、ユーザーは次のいずれかを使用している必要があります。 
  - Microsoft 365 Enterprise SKU のバージョン 1701 以降: E3/E5/F3 または Business SKU: Business Basic、Business Standard、Business Premium。
  - バージョン 1808 以降の Office Professional Plus 2019 または Office 2019。
  - Office Professional Plus 2016 (MSI) または Office Standard 2016 (MSI) のバージョン 16.0.4494.1000 以降\*
  - バージョン 15.0.4937.1000 以降の Office Professional Plus 2013 (MSI) または Office Standard 2013 (MSI)\*
  - バージョン 16.0.9318.1000 以降のバージョン Office 2016 for Mac 
- iOS 用 Outlook モバイルのバージョン 2.75.0 以降 
- Android 用 Outlook モバイルのバージョン 2.2.145 以降 
    
    *MSI バージョンの Outlook では、"My アドイン" セクションではなく、適切な Outlook リボンに管理者がインストールしたアドインが表示されます。

### <a name="exchange-online-requirements"></a>Exchange Online の要件

Microsoft Exchange は、アドイン マニフェストを組織のテナント内に格納します。 アドインを展開する管理者と、それらのアドインを受け取るユーザーは、OAuth 認証をサポートするバージョンの Exchange Online 上にある必要があります。
  
組織の Exchange 管理者に、どの構成を使用できるのかを確認してください。ユーザーごとの OAuth 認証接続は、[Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell コマンドレットを使用して、検証できます。 


### <a name="centralized-deployment-compatibility-checker"></a>集中展開の互換性チェック

集中展開互換性チェッカーを使用すると、テナントのユーザーが Word、Excel、PowerPoint 用の集中展開を使用するために設定されているかどうかを確認できます。 Outlook のサポートでは、互換性チェックは必要ありません。 互換性チェックをここからダウンロード [します](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)。
  
#### <a name="run-the-compatibility-checker"></a>互換性チェックを実行する
  
1. 管理者特権のウィンドウPowerShell.exeします。
    
2. 次のコマンドを実行します。

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. **Invoke-CompatabilityCheck コマンドを実行** します。

   ```powershell
   Invoke-CompatibilityCheck
   ```
   このコマンドは *_、TenantDomain_* *(TailspinToysIncorporated.onmicrosoft など) の入力を求めるプロンプトを表示します。 </span>com)**_および TenantAdmin_* 資格情報 (グローバル管理者資格情報を使用)、同意を要求します。
    
   > [!NOTE]
   > テナントのユーザー数によって、チェックが完了するのに数分または数時間かかる場合があります。 
  
ツールの実行が完了すると、コンマ区切り (.csv) 形式で出力ファイルが作成されます。 ファイルは既定で **C:\windows\system32 に** 保存されます。 出力ファイルには、次の情報が含まれます。
  
- ユーザー名
    
- ユーザー ID (ユーザーのメール アドレス)
    
- 一元展開の準備完了 - 残りの項目が TRUE の場合
    
- Office計画 - ライセンスOfficeのプラン
    
- ライセンス認証された Office - Office をライセンス認証している場合
    
- サポートされているメールボックス - OAuth 対応メールボックスを使用している場合

> [!NOTE]
> サーバーの全体展開 PowerShell モジュールを使用する場合、多要素認証はサポートされません。
  
## <a name="user-and-group-assignments"></a>ユーザーとグループの割り当て

集中展開機能は現在、Microsoft 365 グループ、配布リスト、セキュリティ グループなど、Azure Active Directory でサポートされているグループの大部分をサポートしています。
  
> [!NOTE]
> メールが有効ではないセキュリティ グループは、現段階ではサポートされていません。 
  
集中展開は、テナント内の個々のユーザー、グループ、およびすべてのユーザーへの割り当てをサポートします。 集中展開は、上位レベルのグループまたは親グループのないグループのユーザーをサポートしますが、ネストされたグループまたは親グループを持つグループのユーザーはサポートされません。
   
次の例では、Sandra、Sheila、「営業部門」のグループがアドインに割り当てられています。「西海岸営業部門」は入れ子のグループのため、Bert と Fred はアドインに割り当てられていません。
  
![営業部門の図](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>グループにネストされたグループが含まれているかどうかを調べる

グループにネストされたグループが含まれているかどうかを調べる最も簡単な方法は、Outlook 内のグループの連絡先カードを確認することです。 電子メールの **[To]** フィールドにグループ名を入力し、解決時にグループ名を選択すると、グループ名にユーザーまたは入れ子になったグループが含まれているかが表示されます。 次の例では、「テスト グループ」での Outlook 情報先カードの [ **メンバー**] タブには、ユーザーはなく、2 つのサブ グループのみが表示されています。 
  
![Outlook 連絡先カードの [メンバー] タブ](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
反対のクエリを実行できます。グループを解決して、任意のグループのユーザーがいないかどうかを表示します。次の例では、「サブ グループ 1」が「テスト グループ」のメンバーである Outlook 情報先カードの [ **メンバーシップ**] タブの下に表示されます。 
  
![Outlook 連絡先カードの [メンバーシップ] タブ](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
または、Azure Active Directory Graph API でクエリを実行して、グループ内でのグループ一覧を見つけます。詳細については、「[Operations on groups | Graph API reference (グループに対する操作 | Graph API リファレンス)](/previous-versions/azure/ad/graph/api/groups-operations)」を参照してください。
  
### <a name="contacting-microsoft-for-support"></a>Microsoft に連絡してサポートを受ける

web 用の Office アプリ (Word、Excel など) の使用中にアドインの読み込み中に問題が発生した場合は、Microsoft サポートに問い合わせが必要な場合があります (方法をご覧[ください](../contact-support-for-business-products.md))。 サポート チケットに Microsoft 365 環境に関する次の情報を提供します。
  
|**プラットフォーム**|**デバッグ情報**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler ログ  <br/>  テナント ID ( [詳細情報](/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationID。 1 つの Office ページのソースを表示し、相関 ID の値を探してサポートに送信します。  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|リッチ クライアント (Windows、Mac)  <br/> | Charles/Fiddler ログ  <br/>  クライアント アプリのビルド番号 (できれば **File/Account** のスクリーンショットとして)  <br/> |
