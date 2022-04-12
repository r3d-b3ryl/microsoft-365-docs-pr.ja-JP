---
title: Outlook で配布リストを Microsoft 365 グループにアップグレードする
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 1 つまたは複数の配布リストをOutlookのMicrosoft 365 グループにアップグレードする方法と、PowerShell を使用して複数の配布リストを同時にアップグレードする方法について説明します。
ms.openlocfilehash: 832d65854a6a18ad28e3d9fca6d1d11c17146c80
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782261"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook で配布リストを Microsoft 365 グループにアップグレードする

配布リストは、OutlookのMicrosoft 365 グループにアップグレードできます。 これは、組織の配布リストに、Microsoft 365 グループのすべての機能と機能を提供する優れた方法です。 [Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

配布リストは 1 つずつ、または複数を同時にアップグレードできます。

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Outlookで 1 つまたは複数の配布リスト グループをMicrosoft 365 グループにアップグレードする

配布リスト グループをアップグレードするには、グローバル管理者またはExchange管理者である必要があります。 Microsoft 365 グループにアップグレードするには、配布リスト グループにメールボックスを持つ所有者が必要です。

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>新しい EAC を使用して、1 つまたは複数の配布リスト グループをOutlookでMicrosoft 365 グループにアップグレードする

1. 新しいExchange管理センター>**受信者グループに**\>移動 <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">します</a>。

2. [グループ **] ページから**、Microsoft 365 グループにアップグレードする配布リスト グループ (**配布** グループとも呼ばれます) を選択します。

3. ツール バーから **[アップグレード配布グループ** ] を選択します。

4. [ **アップグレードの準備完了]** ダイアログ ボックスで、[ **アップグレード**] をクリックします。 プロセスがすぐに開始されます。 アップグレードする配布リスト グループのサイズと数によっては、プロセスに数分または数時間かかる場合があります。

> [!NOTE]
> 上部のバナーは、アップグレード (*ディストリビューション グループなど) がアップグレードされたことを示します。変更を反映するには 5 分かかります。アップグレードされた配布グループを表示するには、Microsoft 365 グループでフィルター処理* します。

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>クラシック EAC を使用して、1 つまたは複数の配布リスト グループをOutlookでMicrosoft 365 グループにアップグレードする

1. Exchange管理センター>**受信者グループに**\>移動 <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**します**</a>。<br/>Microsoft 365 グループにアップグレードできる配布リスト (**配布グループ** とも呼ばれます) があることを示す通知が表示されます。<br/> ![[概要] ボタンを選択します。](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

1. グループ **ページから** 1 つ以上の配布リスト (**配布グループ** とも呼ばれます) を選択します。<br/>![配布グループを選択します。](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

1. アップグレード アイコンを選択します。<br/>![Microsoft 365 グループ アイコンにアップグレードします。](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

1. 情報ダイアログで、[ **はい** ] を選択してアップグレードを確認します。 プロセスがすぐに開始されます。 アップグレードする配布リストのサイズや数に応じて、処理には数分または数時間かかることがあります。<br/>配布リストをアップグレードできない場合は、それを示すダイアログが表示されます。 [アップグレードできない配布リスト](#which-distribution-lists-cant-be-upgraded)を確認してください。

1. 複数の配布リストをアップグレードする場合は、ドロップダウン リストを使用して、アップグレードされた配布リストをフィルター処理します。 一覧が完了していない場合は、しばらく待ってから **[更新** ] を選択して、正常にアップグレードされた内容を確認します。<br/>選択した配布リストのすべてのアップグレード プロセスが完了しても、通知は表示されません。[ **アップグレード可能** ] または [ **アップグレードされた配布リスト** ] に一覧された内容を確認して、これを把握することができます。

1. アップグレード用に DL を選択したが、[アップグレード可能] としてページに表示されている場合は、アップグレードに失敗しました。 「[アップグレードが機能しない場合の対処方法](#what-to-do-if-the-upgrade-doesnt-work)」を参照してください。

> [!NOTE]
> グループのダイジェスト メールを受け取っている場合は、下部に通知が表示され、所有者になっている対象の配布リストをアップグレードできるように示されることがあります。ダイジェスト メールの詳細については、「[Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)」 (Outlook でグループ会話を使用する) を参照してください。

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>アップグレードが機能しない場合の対処方法

アップグレードに失敗した配布リストは、変更されないまま保持されます。

1 つ以上の **対象となる** 配布リストをアップグレードできない場合は、 

1. [このスクリプト](https://aka.ms/DLToM365Group)を使用して、配布リストをMicrosoft 365 グループにアップグレードできない可能性のある問題をスキャンし、スクリプトによって報告されたすべての問題を修正し、配布リストをもう一度アップグレードしてみてください。 

2. 上記のスクリプトで問題が解決しない場合、または問題が解決しない場合は、 [サポート チケット](../../business-video/get-help-support.md)を開きます。 問題を解決するために、この問題をグループ エンジニアリング チームにエスカレーションする必要があります。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell を使用して複数の配布リストを同時にアップグレードする方法

PowerShell の使用経験がある場合は、UI ではなく、この手順を使用することをお勧めします。配布リストのアップグレードに役立つ一連のコマンドレットが用意されています。以下を参照してください。

### <a name="upgrade-a-single-dl"></a>1 つの DL をアップグレードする

1 つの DL をアップグレードするには、次のコマンドを実行します。

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

たとえば、SMTP アドレス dl1@contoso.com を使用して DL をアップグレードする場合は、次のコマンドを実行します。

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell コマンドレットを使用して、1 つの配布リストをMicrosoft 365 グループにアップグレードすることもできます。

### <a name="upgrade-multiple-dls-in-a-batch"></a>複数の DL を一括してアップグレードする

複数の DL をバッチとして渡し、まとめてアップグレードすることもできます。

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

たとえば、SMTP アドレス`dl1@contoso.com`を使用して 5 つの DL をアップグレードし、 `dl3@contoso.com``dl4@contoso.com` `dl5@contoso.com`次のコマンドを実行します。`dl2@contoso.com`

```powershell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com
```

### <a name="upgrade-all-eligible-dls"></a>対象となるすべての DL をアップグレードする

対象となるすべての DL をアップグレードするには、2 つの方法があります。

> [!NOTE]
> Upgrade-DistributionGroup コマンドレットはパイプラインからデータを受け取りません。このため、"foreach-object{}" 演算子を使用して正常に実行する必要があります。

1. テナントで適格な DL を取得し、upgrade コマンドを使用してアップグレードします。

   ```PowerShell
   Get-EligibleDistributionGroupForMigration | Foreach-Object{
       Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
   }
   ```

2. 2.すべての DL の一覧を取得し、対象となる DL のみをアップグレードします。

   ```PowerShell
   Get-DistributionGroup| Foreach-Object{
       Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
   }
   ```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlookで配布リストをMicrosoft 365 グループにアップグレードする方法に関する FAQ

### <a name="which-distribution-lists-cant-be-upgraded"></a>アップグレードできない配布リストはどれですか?

クラウド管理されている、単純で入れ子になっていない配布リストのみをアップグレードできます。 次の表に、アップグレード **できない** 配布リストを示します。

|プロパティ|対象|
|---|---|
|オンプレミスで管理される配布リスト|いいえ|
|入れ子になった配布リスト子グループがあるか、または別のグループのメンバーである配布リスト|いいえ|
|**UserMailbox、SharedMailbox**、**TeamMailbox**、**MailUser** 以外 **のメンバー RecipientTypeDetails** を含む配布リスト|不要|
|100 を超える所有者を持つ配布リスト|不要|
|メンバーのみが含まれるが所有者がいない配布リスト|不要|
|特殊文字を含むエイリアスを持つ配布リスト|いいえ|
|配布リストが共有メールボックスの転送アドレスになるように構成されている場合|不要|
|DL が別の DL の **送信者制限** の一部である場合。|いいえ|
|セキュリティ グループ|いいえ|
|動的配布リスト|いいえ|
|**RoomLists** に変換された配布リスト|不要|

### <a name="check-which-dls-are-eligible-for-upgrade"></a>アップグレードの対象となる DLs を確認する

ある DL がアップグレード対象かどうかを確認するには、次のコマンドを実行します。

```PowerShell
Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration
```

アップグレード対象の DL を確認する場合は、次のコマンドを実行します。

```PowerShell
Get-EligibleDistributionGroupForMigration
```

### <a name="who-can-run-the-upgrade-scripts"></a>どのユーザーがアップグレード スクリプトを実行できますか?

グローバル管理者またはExchange管理者権限を持つユーザー。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>連絡先カードに依然として配布リストが表示されるのはなぜでしょうか。 アップグレードされた配布リストが自動提案リストに表示されないようにするには、どうすればよいですか?

- Outlook: 移行後にMicrosoft 365グループ名を入力してOutlookで電子メールを送信しようとすると、受信者はグループの代わりに配布リストとして解決されます。 受信者の連絡先カードは配布リストの連絡先カードとなります。 これは Outlook の受信者キャッシュまたはニックネーム キャッシュに起因します。 メールはグループに正常に送信されますが、送信者に混乱が生じる可能性があります。<br/>この記事の「[Outlook AutoComplete リストに関する情報](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list)」の手順を実行してキャッシュをリセットすると、この問題が解決します。

- Outlook on the web: Outlook on the webの場合、配布リストの受信者は引き続きキャッシュに残ります。 「 [オートコンプリート リストから推奨される名前またはメール アドレスを削除する](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) 」の手順に従って、キャッシュを更新してグループの連絡先カードを表示できます。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新しいグループのメンバーは、受信トレイでウェルカム メッセージを受け取りますか?

いいえ。ウェルカム メッセージを有効にする設定は、既定で false に設定されています。この設定は、既存のグループ メンバーにも、移行が完了した後に参加する可能性がある新しいグループ メンバーにも影響します。グループの所有者が後でゲスト ユーザーを許可した場合、ゲスト ユーザーは受信トレイでウェルカム メールを受け取ることはありません。ゲスト メンバーはグループで継続して作業を行うことができます。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>1 つまたは一部の DL がアップグレードされない場合はどうなりますか?

DL は対象ですがアップグレードできない場合があります。 DL はアップグレードされず、DL のままです。

- 管理者が組織内の **グループにグループ電子メール アドレス ポリシー** を適用し、条件を満たしていない DL をアップグレードしようとすると、DL はアップグレードされません

- **MemberJoinRestriction** または **MemberDepartRestriction** が **Closed** に設定されている DLs をアップグレードできませんでした

- Microsoft 365 グループの作成は、[この記事](/microsoft-365/solutions/manage-creation-of-groups)の手順を使用して、少数のユーザーにのみ許可されます。 このシナリオでは、配布リストの所有者が Microsoft 365 グループの作成を許可されていない場合、配布リストは Microsoft 365 グループにアップグレードされません。
回避策: 上記のシナリオでは、次のいずれかの回避策を使用します。

1. DL の所有者として言及されたすべてのユーザーが M365 グループの作成を許可されていることを確認します。つまり、M365 グループに許可されているセキュリティ グループのメンバーであることを確認します。

   または

2. 一時的に、M365 グループの作成が許可されていない DL の所有者を、M365 グループの作成が許可されているユーザーに置き換えます。

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>EAC からのアップグレードに失敗した場合、配布リストはどうなりますか?

呼び出しがサーバーに送信された場合にのみ、アップグレードが発生します。アップグレードが失敗した場合、配布リストはそのまま保持されます。配布リストは、以前のように動作します。

### <a name="what-happens-to-message-approval-moderation-settings-on-distribution-groups-after-upgrading"></a>アップグレード後、配布グループのメッセージ承認 (モデレーション) 設定はどうなりますか?

メッセージ承認 (モデレーション) 設定は保持され、配布グループがMicrosoft 365 グループにアップグレードされた後も引き続き正常に動作します。

## <a name="related-content"></a>関連コンテンツ

[グループの比較](../create-groups/compare-groups.md) (記事)\
[ユーザーへのMicrosoft 365 グループの説明](../create-groups/explain-groups-knowledge-worker.md) (記事)\
[管理センターを使用して、Microsoft 365 グループのメンバーを追加または削除する](../create-groups/add-or-remove-members-from-groups.md)
