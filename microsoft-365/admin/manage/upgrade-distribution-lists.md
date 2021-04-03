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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 1 つ以上の配布リストを Outlook の Microsoft 365 グループにアップグレードする方法と、PowerShell を使用して複数の配布リストを同時にアップグレードする方法について説明します。
ms.openlocfilehash: ab7c2ff68b1f16915d65fff0d7292e3b3ad72d02
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579244"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook で配布リストを Microsoft 365 グループにアップグレードする

Outlook を使用して配布リストを Microsoft 365 グループにアップグレードできます。 これは、組織の配布リストに Microsoft 365 グループのすべての機能と機能を提供する最適な方法です。 [Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

配布リストは 1 つずつ、または複数を同時にアップグレードできます。

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook で 1 つ以上の配布リストを Microsoft 365 グループにアップグレードする

配布リストをアップグレードするには、グローバル管理者または Exchange 管理者である必要があります。 Microsoft 365 グループにアップグレードするには、配布グループにメールボックスを持つ所有者が必要です。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. Exchange 管理センターで、[受信者グループ] **に移動** \> **します**。<br/>Microsoft 365 グループにアップグレードできる配布リスト (配布 **グループとも呼** ばれる) を持っているという通知が表示されます。<br/> ![[スタート] ボタンを選択する](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. **グループ** ページから 1 つ以上の配布リスト ( **配布グループ** とも呼ばれる) を選びます。<br/>![配布グループを選択する](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. アップグレード アイコンを選択します。<br/>![[Microsoft 365 グループへのアップグレード] アイコン](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 情報ダイアログで、[はい] **を選択して** アップグレードを確認します。 プロセスがすぐに開始されます。 アップグレードする配布リストのサイズや数に応じて、処理には数分または数時間かかることがあります。<br/>配布リストをアップグレードできない場合は、それを示すダイアログが表示されます。 「 [アップグレードできない配布リスト」を参照してください](#which-distribution-lists-cant-be-upgraded)。

6. 複数の配布リストをアップグレードする場合は、ドロップダウン リストを使用して、アップグレードされた配布リストをフィルター処理します。 リストが完了しない場合は、しばらく待ち、次に [更新] を選択して、正常にアップグレードされた項目を確認します。<br/>選択した配布リストのすべてのアップグレード プロセスが完了しても、通知は表示されません。[ **アップグレード可能** ] または [ **アップグレードされた配布リスト** ] に一覧された内容を確認して、これを把握することができます。

7. アップグレードする配布リストを選択しても、ページ上に [アップグレード可能] と表示され続ける場合は、アップグレードに失敗しています。「[アップグレードが機能しない場合の対処方法](#what-to-do-if-the-upgrade-doesnt-work)」を参照してください。

> [!NOTE]
> グループのダイジェスト メールを受け取っている場合は、下部に通知が表示され、所有者になっている対象の配布リストをアップグレードできるように示されることがあります。ダイジェスト メールの詳細については、「[Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)」 (Outlook でグループ会話を使用する) を参照してください。

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>アップグレードが機能しない場合の対処方法

アップグレードに失敗した配布リストは、変更されないまま保持されます。

1 つ以上の **対象** の配布リストがアップグレードに失敗した場合は、 [サポート チケット](../contact-support-for-business-products.md)を開きます。問題を解決するために、この問題をグループ エンジニアリング チームにエスカレーションする必要があります。

サービスが停止しているため、配布リストがアップグレードされなかった可能性もありますが、この可能性は低いです。必要な場合は、しばらく待ってから、もう一度配布リストをアップグレードします。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell を使用して複数の配布リストを同時にアップグレードする方法

PowerShell の使用経験がある場合は、UI ではなく、この手順を使用することをお勧めします。配布リストのアップグレードに役立つ一連のコマンドレットが用意されています。以下を参照してください。

### <a name="upgrade-a-single-dl"></a>1 つの DL をアップグレードする

1 つの DL をアップグレードするには、次のコマンドを実行します。

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

たとえば、SMTP アドレスが dl1@contoso.com の DL をアップグレードする場合は、次のコマンドを実行します。

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell コマンドレットを使用して、1 つの配布リストを Microsoft 365 グループにアップグレードすることもできます。

### <a name="upgrade-multiple-dls-in-a-batch"></a>複数の DL を一括してアップグレードする

複数の DL をバッチとして渡し、まとめてアップグレードすることもできます。

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
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

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook で配布リストを Microsoft 365 グループにアップグレードする方法に関するよく寄せられる質問

### <a name="which-distribution-lists-cant-be-upgraded"></a>アップグレードできない配布リスト

クラウド管理されている、単純で入れ子になっていない配布リストのみをアップグレードできます。 次の表に、アップグレードできない **配布リスト** を示します。

|**プロパティ**|**対象**|
|:-----|:-----|
|オンプレミスで管理される配布リスト  <br/> |いいえ  <br/> |
|入れ子になった配布リスト子グループがあるか、または別のグループのメンバーである配布リスト  <br/> |いいえ  <br/> |
|**UserMailbox**、SharedMailbox **、TeamMailbox** **、MailUser** 以外のメンバー **RecipientTypeDetails** を持つ配布リスト  <br/> |いいえ  <br/> |
|100 人を超える所有者を含む配布リスト  <br/> |いいえ  <br/> |
|メンバーのみで、所有者を含まない配布リスト  <br/> |いいえ  <br/> |
|特殊文字を含むエイリアスがある配布リスト  <br/> |いいえ  <br/> |
|配布リストが共有メールボックスの転送アドレスになるように構成されている場合  <br/> |いいえ  <br/> |
|DL が別の DL の **送信者制限の一** 部である場合。  <br/> |いいえ  <br/> |
|セキュリティ グループ  <br/> |いいえ  <br/> |
|動的配布リスト  <br/> |いいえ  <br/> |
|**RoomLists** に変換された配布リスト  <br/> |いいえ  <br/> |
|**MemberJoinRestriction および/または** **MemberDepartRestriction** が閉じている配布 **リスト**  <br/> |いいえ  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>アップグレードの対象となる DLL を確認する

ある DL がアップグレード対象かどうかを確認するには、次のコマンドを実行します。

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

アップグレード対象の DL を確認する場合は、次のコマンドを実行します。

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>どのユーザーがアップグレード スクリプトを実行できますか?

グローバル管理者または Exchange 管理者権限を持つユーザー。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>連絡先カードに依然として配布リストが表示されるのはなぜでしょうか。 アップグレードした配布リストが自動提案リストに表示されないようにするにはどうすればよいでしょうか。

- Outlook の場合: 移行後に Microsoft 365 グループ名を入力して Outlook で電子メールを送信しようとすると、受信者はグループの代わりに配布リストとして解決されます。 受信者の連絡先カードは配布リストの連絡先カードとなります。 これは Outlook の受信者キャッシュまたはニックネーム キャッシュに起因します。 電子メールはグループに正常に送信されますが、送信者に混乱を招く可能性があります。<br/>「[Outlook のオートコンプリートの一覧についての情報](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list)」というトピックにある手順を実行してキャッシュをリセットすると、この問題は解消されます。

- Outlook on the web: Outlook on the web の場合、配布リストの受信者は引き続きキャッシュに残ります。 「自動完了リストから推奨[](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)される名前または電子メール アドレスを削除する」の手順に従って、キャッシュを更新してグループ連絡先カードを表示できます。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新しいグループのメンバーは、受信トレイでウェルカム メッセージを受け取りますか?

いいえ。ウェルカム メッセージを有効にする設定は、既定で false に設定されています。この設定は、既存のグループ メンバーにも、移行が完了した後に参加する可能性がある新しいグループ メンバーにも影響します。グループの所有者が後でゲスト ユーザーを許可した場合、ゲスト ユーザーは受信トレイでウェルカム メールを受け取ることはありません。ゲスト メンバーはグループで継続して作業を行うことができます。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>1 つまたは一部の DLL がアップグレードされていない場合は、どうしますか。

DL が対象ですが、アップグレードできない場合もあります。 DL はアップグレードされません。DL として残ります。

- 管理者が組織内の **グループ** にグループ メール アドレス ポリシーを適用し、条件を満たしていない DLL のアップグレードを試みた場合、DL はアップグレードされません

- **MemberJoinRestriction** または **MemberDepartRestriction** が **Closed** に設定されている DLL をアップグレードできない

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>EAC からのアップグレードに失敗した場合、配布リストはどうなりますか?

呼び出しがサーバーに送信された場合にのみ、アップグレードが発生します。アップグレードが失敗した場合、配布リストはそのまま保持されます。配布リストは、以前のように動作します。