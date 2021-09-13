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
localization_priority: Normal
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
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 1 つ以上の配布リストを Outlook の Microsoft 365 グループにアップグレードする方法と、PowerShell を使用して複数の配布リストを同時にアップグレードする方法について説明します。
ms.openlocfilehash: 298d349fcf0874dd4c2dbd85ff19101e40988aba
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59178871"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook で配布リストを Microsoft 365 グループにアップグレードする

配布リストを、Microsoft 365グループにアップグレードOutlook。 これは、組織の配布リストに、組織のグループのすべての機能と機能を提供Microsoft 365です。 [Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

配布リストは 1 つずつ、または複数を同時にアップグレードできます。

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>1 つ以上の配布リスト グループを、Microsoft 365グループにアップグレードOutlook

配布リスト グループをアップグレードするには、Exchange管理者または管理者である必要があります。 配布リスト グループMicrosoft 365アップグレードするには、メールボックスを持つ所有者が必要です。

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>新しい EAC を使用して、1 つ以上の配布リスト グループを、Microsoft 365グループにアップグレードOutlook

1. 管理センターの新しい [Exchangeに移動し](https://admin.exchange.microsoft.com)、[受信者グループ]**に移動** \> **します**。

2. [グループ] ページから、配布リスト グループ (配布 **グループとも呼** ばれる) を選択して、Microsoft 365グループ **にアップグレード** します。

3. ツール バー **から [アップグレード配布グループ** ] を選択します。

4. [アップグレードの準備完了] ダイアログ ボックス **で、[アップグレード]** を **クリックします**。 プロセスがすぐに開始されます。 アップグレードする配布リスト グループのサイズと数に応じて、プロセスには数分または数時間かかる場合があります。

> [!NOTE]
> 上部のバナーは、アップグレード (配布グループなど) がアップグレード *された状態を示します。変更を反映するには 5 分かかります。アップグレードされたMicrosoft 365グループ* を表示するには、グループでフィルター処理します。

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>クラシック EAC を使用して、1 つ以上の配布リスト グループを、Microsoft 365グループにアップグレードOutlook

1. クラシック 管理センターに<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchangeします</a>。

2. クラシック 管理センターでExchange[受信者グループ **] に移動** \> **します**。<br/>配布リスト (配布グループとも呼 **ばれる)** が存在し、配布グループにアップグレードする資格があるという通知Microsoft 365表示されます。<br/> ![[開始] ボタンを選択します。](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. [グループ] ページから 1 つ以上の配布リスト (配布 **グループ** とも呼ばれる) **を選択** します。<br/>![配布グループを選択します。](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. アップグレード アイコンを選択します。<br/>![[グループ] Microsoft 365にアップグレードします。](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 情報ダイアログで、[はい] **を選択して** アップグレードを確認します。 プロセスがすぐに開始されます。 アップグレードする配布リストのサイズや数に応じて、処理には数分または数時間かかることがあります。<br/>配布リストをアップグレードできない場合は、それを示すダイアログが表示されます。 「 [アップグレードできない配布リスト」を参照してください](#which-distribution-lists-cant-be-upgraded)。

6. 複数の配布リストをアップグレードする場合は、ドロップダウン リストを使用して、アップグレードされた配布リストをフィルター処理します。 リストが完了しない場合は、しばらく待ち、次に [更新] を選択して、正常にアップグレードされた項目を確認します。<br/>選択した配布リストのすべてのアップグレード プロセスが完了しても、通知は表示されません。[ **アップグレード可能** ] または [ **アップグレードされた配布リスト** ] に一覧された内容を確認して、これを把握することができます。

7. アップグレード用に DL を選択したが、アップグレード可能としてページに表示された場合、アップグレードに失敗しました。 「[アップグレードが機能しない場合の対処方法](#what-to-do-if-the-upgrade-doesnt-work)」を参照してください。

> [!NOTE]
> グループのダイジェスト メールを受け取っている場合は、下部に通知が表示され、所有者になっている対象の配布リストをアップグレードできるように示されることがあります。ダイジェスト メールの詳細については、「[Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)」 (Outlook でグループ会話を使用する) を参照してください。

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>アップグレードが機能しない場合の対処方法

アップグレードに失敗した配布リストは、変更されないまま保持されます。

1 つ以上の **対象** の配布リストがアップグレードに失敗した場合は、 [サポート チケット](../../business-video/get-help-support.md)を開きます。問題を解決するために、この問題をグループ エンジニアリング チームにエスカレーションする必要があります。

サービスの停止により配布リストがアップグレードされませんが、可能性は低い可能性があります。 必要な場合は、しばらく待ってから、もう一度配布リストをアップグレードします。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell を使用して複数の配布リストを同時にアップグレードする方法

PowerShell の使用経験がある場合は、UI ではなく、この手順を使用することをお勧めします。配布リストのアップグレードに役立つ一連のコマンドレットが用意されています。以下を参照してください。

### <a name="upgrade-a-single-dl"></a>1 つの DL をアップグレードする

単一の DL をアップグレードするには、次のコマンドを実行します。

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

たとえば、SMTP アドレスを使用して DL をアップグレードする場合は dl1@contoso.com コマンドを実行します。

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell コマンドレットを使用してMicrosoft 365配布リストを 1 つのグループにアップグレードすることもできます。

### <a name="upgrade-multiple-dls-in-a-batch"></a>複数の DL を一括してアップグレードする

複数の DL をバッチとして渡し、まとめてアップグレードすることもできます。

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

たとえば、SMTP アドレスを使用して 5 つの DLL をアップグレードする場合 `dl1@contoso.com` 、および `dl2@contoso.com` `dl3@contoso.com` 、 `dl4@contoso.com` `dl5@contoso.com` 次のコマンドを実行します。

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>対象となるすべての DL をアップグレードする

対象となるすべての DL をアップグレードするには、2 つの方法があります。

> [!NOTE]
> このUpgrade-DistributionGroupコマンドレットはパイプラインからデータを受け取らないので、"foreach-object" 演算子を使用して正常に {} 実行する必要があります。

1. テナント内の適格な DLL を取得し、upgrade コマンドを使用してアップグレードします。

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

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>配布リストのグループへのアップグレードに関する FAQ Microsoft 365のグループOutlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>アップグレードできない配布リスト

クラウド管理されている、単純で入れ子になっていない配布リストのみをアップグレードできます。 次の表に、アップグレードできない **配布リスト** を示します。

|**プロパティ**|**対象**|
|:-----|:-----|
|オンプレミスで管理される配布リスト  <br/> |いいえ  <br/> |
|入れ子になった配布リスト子グループがあるか、または別のグループのメンバーである配布リスト  <br/> |いいえ  <br/> |
|**UserMailbox**、SharedMailbox **、TeamMailbox** **、MailUser** 以外のメンバー **RecipientTypeDetails** を持つ配布リスト  <br/> |いいえ  <br/> |
|所有者が 100 人を超える配布リスト  <br/> |いいえ  <br/> |
|メンバーのみを持ち、所有者がない配布リスト  <br/> |いいえ  <br/> |
|特殊文字を含むエイリアスを含む配布リスト  <br/> |いいえ  <br/> |
|配布リストが共有メールボックスの転送アドレスになるように構成されている場合  <br/> |いいえ  <br/> |
|DL が別の DL の **送信者制限の一** 部である場合。  <br/> |いいえ  <br/> |
|セキュリティ グループ  <br/> |いいえ  <br/> |
|動的配布リスト  <br/> |いいえ  <br/> |
|**RoomLists** に変換された配布リスト  <br/> |いいえ  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>アップグレードの対象となる DLL を確認する

ある DL がアップグレード対象かどうかを確認するには、次のコマンドを実行します。

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

アップグレード対象の DL を確認する場合は、次のコマンドを実行します。

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>どのユーザーがアップグレード スクリプトを実行できますか?

グローバル管理者または管理者権限を持Exchangeユーザー。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>連絡先カードに依然として配布リストが表示されるのはなぜでしょうか。 アップグレードされた配布リストが自動提案リストに表示されるのを防ぐには、どのような操作を行う必要がありますか?

- [Outlook: 移行後に Microsoft 365 グループ名を入力して Outlook で電子メールを送信しようとすると、受信者はグループの代わりに配布リストとして解決されます。 受信者の連絡先カードは配布リストの連絡先カードとなります。 これは Outlook の受信者キャッシュまたはニックネーム キャッシュに起因します。 電子メールはグループに正常に送信されますが、送信者に混乱を招く可能性があります。<br/>この記事の手順を実行[できます。この](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list)問題を解決するキャッシュをリセットOutlookオートコンプリート リストに関する情報を参照してください。

- [Outlook on the web: Outlook on the web場合、配布リストの受信者は引き続きキャッシュに残ります。 「自動完了リストから推奨[](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)される名前または電子メール アドレスを削除する」の手順に従って、キャッシュを更新してグループ連絡先カードを表示できます。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新しいグループのメンバーは、受信トレイでウェルカム メッセージを受け取りますか?

いいえ。ウェルカム メッセージを有効にする設定は、既定で false に設定されています。この設定は、既存のグループ メンバーにも、移行が完了した後に参加する可能性がある新しいグループ メンバーにも影響します。グループの所有者が後でゲスト ユーザーを許可した場合、ゲスト ユーザーは受信トレイでウェルカム メールを受け取ることはありません。ゲスト メンバーはグループで継続して作業を行うことができます。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>1 つまたは一部の DLL がアップグレードされていない場合は、どうしますか。

DL が対象ですが、アップグレードできない場合もあります。 DL はアップグレードされません。DL として残ります。

- 管理者が組織内の **グループ** にグループ メール アドレス ポリシーを適用し、条件を満たしていない DLL をアップグレードしようとする場合、DL はアップグレードされません。

- **MemberJoinRestriction** または **MemberDepartRestriction** が **Closed** に設定されている DLL をアップグレードできない

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>EAC からのアップグレードに失敗した場合、配布リストはどうなりますか?

呼び出しがサーバーに送信された場合にのみ、アップグレードが発生します。アップグレードが失敗した場合、配布リストはそのまま保持されます。配布リストは、以前のように動作します。

## <a name="related-content"></a>関連コンテンツ

[グループの比較](../create-groups/compare-groups.md) (記事)\
[ユーザー Microsoft 365グループの説明](../create-groups/explain-groups-knowledge-worker.md)(記事)\
[管理センターを使用して、Microsoft 365グループのメンバーを追加または削除する](../create-groups/add-or-remove-members-from-groups.md)
