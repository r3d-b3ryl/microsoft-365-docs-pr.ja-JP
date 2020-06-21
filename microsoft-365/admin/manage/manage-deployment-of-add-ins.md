---
title: 管理センターでのアドインの展開を管理する
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターで一元展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780123"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでアドインのデプロイを管理する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。 管理者は、組織内のユーザーに対して Office アドインを展開することができます。 この操作は、Microsoft 365 管理センターの一元展開機能を使用して行うことができます。
  
一元展開は、ほとんどの管理者が組織内のユーザーやグループにアドインを展開するために推奨される最も豊富な方法です。 組織が集中展開をサポートできるかどうかを判断する方法の詳細については、「[組織でアドインの一元展開が機能](centralized-deployment-of-add-ins.md)するかどうかを判断する」を参照してください。
  
一元展開には、次のような利点があります。
  
- グローバル管理者は、ユーザー、グループ、またはテナント内のすべてのユーザーに対して、アドインを直接ユーザーに割り当てることができます。
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- 管理者がアドインをオフまたは削除した場合、またはユーザーが Azure Active Directory またはアドインが割り当てられているグループから削除された場合、アドインはユーザーに対して表示されなくなります。
    
> [!NOTE]
>  Word の場合、Excel および PowerPoint では、 [Sharepoint アプリカタログ](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)を使用して、Microsoft 365 に接続していないオンプレミス環境のユーザーにアドインを展開し、必要な sharepoint アドインをサポートします。 Outlook の > は、Exchange コントロールパネルを使用して、Microsoft 365 への接続なしでオンプレミス環境に展開します。 > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Office アドインを展開する際に推奨される方法

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. 対象ユーザーにアドインを完全にロールアウトします。
    
ロールアウトの手順は、対象ユーザーの規模に応じて、追加または削除することもできます。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>管理センターを使用して Office アドインを展開する

作業を開始する前に、「[組織でアドインの一元展開が機能するかどうかを判断](centralized-deployment-of-add-ins.md)する」を参照してください。

  
1. 管理センターで、[**設定**] [アドイン] ページに移動し \> **Add-ins**ます。
    
2. ページの上部にある **[アドインの展開]** を選択します。 [概要] ページで、**[次へ]** を選択します。
    
3. オプションを選択し、指示に従います。
  
4. Office ストアからアドインを追加するオプションを選択した場合は、アドインを選択できるようになります。 [ **あなたへのおすすめ** ]、[ **評価** ]、[ **名前** ] のカテゴリから、利用可能なアドインを表示することができます。 無料のアドインのみを Office ストアから追加できます。 現在、有料アドインはサポートされていません。 アドインを選択した後、次に進むには、追加の使用条件に同意する必要があります。 <br/><br/> 注: Office ストアオプションを使用すると、ユーザーが操作しなくても、アドインの更新と機能拡張が自動的にユーザーに対して利用可能になります。

5. 次のページで、[**すべて**のユーザー]、[**特定のユーザー/グループ**]、または [**自分のみ**] を選択して、アドインの展開先を指定します。 [検索] ボックスを使用して、アドインを展開するユーザーやグループを検索します。 <br/>メモ: アドインに適用されるその他の状態について説明します。 このトピックで後述する「[アドインの状態](#add-in-states)」を参照してください。
  
6. **[展開]** を選択します。
  
7. アドインが展開されると、緑色の目盛りが表示されます。 ページの指示に従って、アドインの展開が正常に行われたことをテストできます。

> [!NOTE]
> アプリのリボンにアドインアイコンが表示されるように、ユーザーが Office を再起動する必要がある場合があります。 Outlook アドインは、ユーザーのリボンに表示されるまでに最大24時間かかる場合があります。
    
8. 完了したら、[**次へ**] を選択します。 自分だけに展開した場合は、他のユーザーに展開するために、[**アドインにアクセスできるユーザーを変更**する] を選択できます。



アドインを自分以外の組織のメンバーに展開した場合は、「アドインの展開を効果的に通知するために表示される指示に従ってください。 <br/>アドインが Microsoft 365 のその他のアプリと共に表示されるようになります。
  
アドインが使用できるようになったことを知ってもらうため、アドインを展開したことをユーザーとグループに伝えることをお勧めします。 アドインの利用できる時期やその利用方法、アドインの使用により、業務がよりはかどることをメールに記載して、ユーザーに送信することを検討してください。 ユーザーがアドインに問題が発生した場合に役立つ可能性がある関連するヘルプコンテンツや Faq を含めるか、リンクします。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>ユーザーやグループにアドインを割り当てる時期を検討する

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- [**自分**のみ]: 自分だけにアドインを割り当てると、そのアドインは自分のアカウントにのみ割り当てられます。 これは、最初にアドインをテストする場合に適しています。
    
組織に適したオプションは、構成によって異なります。 ただし、割り当てはグループ経由で行うことをお勧めします。 管理者として、割り当てるたびにユーザーを変更するよりも、グループを使用してアドインを管理し、グループのメンバーシップを制御する方が簡単なためです。 一方、ごく少数のユーザーにのみアクセス権を付与したい場合は、指定したユーザーにだけ割り当てるようにします。 このような場合は、割り当てられているユーザーを手動で管理する必要があります。
  
### <a name="add-in-states"></a>アドインの状態

アドインは、 **[オン**] または [**オフ**] のどちらかの状態にすることができます。
  
|**状態**|**状態が発生する原因**|**影響**|
|:-----|:-----|:-----|
|**Active**  <br/> |管理者がアドインをアップロードし、ユーザーまたはグループに割り当てました。  <br/> |アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。  <br/> |
|**オフ**  <br/> |管理者がアドインをオフにした。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。  <br/> |
|**Deleted**  <br/> |管理者がアドインを削除した。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> |
   
他のアドインを使用していない場合は、アドインを削除することをお勧めします。 1 年のうち特定期間のみアドインを使用する場合は、オフにするのも一案です。
  
### <a name="security-of-office-add-ins"></a>Office アドインのセキュリティ

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- データを表示する。
    
- ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。
    
- ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。
    
Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](https://go.microsoft.com/fwlink/p/?linkid=846362)」をご覧ください (特に「Office アドインの構造」セクション)。
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
アドインの更新は次のように発生します。
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > 管理者は更新を実行するために LOB アドインを削除する必要はありません。   [アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅の [**更新] ボタン**を選択できます。 更新プログラムは、新しいアドインのバージョンが既存のアドインのバージョンよりも大きい場合にのみ機能します。   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

### <a name="edit-add-in-access"></a>アドインへのアクセスを編集する

展開後、管理者はアドインへのユーザーアクセスを変更することもできます。

1. 管理センターで、[**設定**  >  **サービス & アドイン**] ページに移動します。

2. 展開されたアドインを選択します。

3. [**アクセスできるユーザー**] の [**編集**] をクリックします。
4. 変更を保存します。
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>すべてのクライアント (Outlook を除く) で Office ストアをオフにして、アドインのダウンロードを禁止する

> [!NOTE]
> Outlook アドインのインストールは、[別のプロセス](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)で管理されます。

組織の場合は、Office ストアから新しい Office アドインをダウンロードできないようにする必要があります。 これを一元展開と組み合わせて使用することにより、組織内のユーザーが組織内の承認済みアドインのみを展開するようにすることができます。
  
アドインの取得を無効にするには、以下の操作を行います。
  
1. 管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。
    
3. **[ユーザー所有のアプリとサービス]** を選びます。
    
4. ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。

これにより、すべてのユーザーがストアから次のアドインを取得するのを防ぐことができます。
  
- Word、Excel、PowerPoint 2016 用のアドインは次のとおりです。
    
  - Windows
    
  - Mac
    
  - Office
    
    
- **Appsource**内からの取得
    
- Microsoft 365 内のアドイン
    
ストアにアクセスしようとするユーザーには、次のメッセージが表示されます。**申し訳ございません。 Microsoft 365 は、Office ストアアドインの個別の取得を防止するように構成されています。**
  
Office ストアの無効化のサポートは、次のバージョンで利用できます。
  
- Windows: 16.0.9001-現在使用可能です。
    
- Mac: 16.10.18011401-現在利用可能です。
    
- iOS: 2.9.18010804-現在使用可能です。
    
- Web は現在利用できます。
    
これにより、管理者は一元展開を使用して Office ストアからアドインを割り当てることができます。
  
ユーザーが Microsoft アカウントでサインインできないようにするには、組織のアカウントのみを使用するようにログオンを制限することができます。 詳細については、[こちら](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)を参照してください。
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>未成年者とストアからのアドインの取得

一般的なデータ保護規則 (GDPR) は、2018年5月25日に有効になる欧州連合規制です。 ユーザーがデータを保護するための権限が付与されます。 GDPR の1つの側面は、親またはガーディアンが許可されていない個人データを、未成年者が他者に送信することができないことです。 マイナーとして定義された特定の年齢は、個人が配置されている地域によって異なります。
  
保護者の同意に関する法的な規制がある地域には、米国、南韓国、英国、および欧州連合があります。 これらの地域では、マイナーがブロックされます (Azure Active Directory によって)。新しい Office アドインをストアから取得し、以前に取得したアドインを実行します。 法律上の規定がない国では、ダウンロードの制限はありません。
  
ユーザーは、Azure Active Directory で指定されているデータに基づいて、マイナーであると判断されます。 テナント管理者は、法務年齢グループと、そのユーザーの上位下位の同意を宣言します。
  
親/ガーディアンが特定のアドインを使用して小規模に同意場合は、テナント管理者は一元展開を使用して、同意を得ているすべての未成年者にそのアドインを展開できます。
  
GDPR を未成年者に準拠させるには、次のいずれかの Office ビルドが学校/組織に展開されていることを確認する必要があります。
  
 **Word、Excel、PowerPoint、Project の場合**: 
  
|||
|:-----|:-----|
|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|Microsoft 365 enterprise 用アプリ (現在のチャネル)  <br/> |9001.2138   <br/> |
|Microsoft 365 enterprise 用アプリ (半期エンタープライズチャネル)  <br/> |8431.2159  <br/> |
|Office 2016 for Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 for Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|Web 用 Office  <br/> |該当なし  <br/> |
   
 **Outlook の場合**: 
  
|||
|:-----|:-----|
|**プラットフォーム** <br/> |**ビルド番号** <br/> |
|Outlook 2016 for Windows (MSI)  <br/> |ビルドの未定  <br/> |
|Windows 版 Outlook 2016 (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|IOS 用の Outlook mobile  <br/> |2.75.0  <br/> |
|Outlook mobile for Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |該当なし  <br/> |
   
 **Office 2013 の要件**
  
Windows 版 Word、Excel、PowerPoint 2013 は、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じマイナーチェックをサポートします。 次に説明するように、2つのコンプライアンスオプションがあります。
  
- **ADAL を有効に**します。 この記事では、office[クライアントでの Microsoft 365 モダン認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)2013 の使用方法について説明します。<br/>「 [Windows デバイスで Office 2013 の先進認証を有効](../security-and-compliance/enable-modern-authentication.md)にする」で説明されているように、レジストリキーを設定して ADAL を有効にする必要もあります。<br/>さらに、Office 2013 用の次の4月の更新プログラムをインストールする必要があります。
    
  - [Office 2013 のセキュリティ更新プログラムの説明: 2018 年4月10日](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018年4月3日 Office 2013 の更新プログラム (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL を有効にしない**でください。 Office 2013 で ADAL を有効にできない場合は、グループポリシーを使用して office クライアントのストアをオフにすることをお勧めします。 Office 用アプリの設定を無効にする方法については、[ここ](https://technet.microsoft.com/library/cc178992.aspx)を参照してください。
    
## <a name="end-user-experience-with-add-ins"></a>アドインのエンド ユーザー エクスペリエンス

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). The add-in will appear on all platforms that the add-in supports.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![検索引用を含む Office リボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
展開されたアドインがアドインコマンドをサポートしていない場合や、展開されたすべてのアドインを表示する場合は、 **[マイ**アドイン] で表示できます。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016、Excel 2016、または PowerPoint 2016

1. [ ** \> マイアドインの挿入**] を選択します。 
    
2. Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。 
    
3. 前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。 <br/>![[Office アドイン] ページの [管理者による管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook

1. [**ホーム**] リボンで、[アドインの**取得**] を選択します。<br/>![Outlook の [格納] ボタン](../../media/getaddinsicon.png)
  
2. 左側のナビゲーションで、**[管理者が管理]** を選びます。

## <a name="delete-the-add-in"></a>アドインを削除する

展開されたアドインを削除することもできます。

1. 管理センターで、[**設定**  >  **サービス & アドイン**] ページに移動します。

2. 展開されたアドインを選択します。

3. [**アドインの削除**] をクリックします。 右下隅にある [アドイン] ボタンを削除します。
4. 選択内容を確認し、[**アドインの削除]** を選びます。
  
## <a name="learn-more"></a>詳細情報

[Office アドイン](https://go.microsoft.com/fwlink/p/?linkid=846362)の作成と構築の詳細情報を表示します。
  
[一元展開 PowerShell コマンドレットを使用してアドインを管理](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)します。
  
[トラブルシューティング: ユーザーがアドインを表示していない](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
