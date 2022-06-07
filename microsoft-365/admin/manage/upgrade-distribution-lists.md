---
title: Exchange Online で配布リストを Microsoft 365 グループにアップグレードする
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
description: 1 つまたは複数の配布リストを Exchange Online の Microsoft 365 グループにアップグレードする方法と、PowerShell を使用して複数の配布リストを同時にアップグレードする方法について説明します。
ms.openlocfilehash: 6f27c4a7df345a25f4b5ca7d2a9f2979a97e7c6a
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65922177"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-exchange-online"></a>Exchange Online で配布リストを Microsoft 365 グループにアップグレードする

配布リストを Microsoft 365 グループにアップグレードすることは、組織内のグループの機能と機能を向上させる優れた方法です。 詳細については、「[Outlook で配布リストをグループにアップグレードする必要がある理由」を参照してください](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)。

配布リストは、一度に 1 つずつ、または複数の配布リストを同時にアップグレードできます。 Exchange 管理センター (EAC) または Exchange Online PowerShell を使用できます。

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups"></a>1 つまたは複数の配布リスト グループを Microsoft 365 グループにアップグレードする

配布リストをアップグレードするには、グローバル管理者または Exchange 管理者である必要があります。 Microsoft 365 グループにアップグレードするには、配布リストに指定された所有者が必要で、その所有者はメールボックスである必要があります。

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>クラシック EAC を使用して、Outlook で 1 つまたは複数の配布リスト グループを Microsoft 365 グループにアップグレードする

> [!NOTE]
> このセクションの手順は、新しい EAC では使用できません。

1. Exchange 管理センター>**受信者グループに**\>移動 <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**します**</a>。

   Microsoft 365 グループにアップグレードできる配布リスト ( **配布グループ** とも呼ばれます) があることを示す通知が表示されます。
   
   ![[作業の開始] ボタンを選択します。](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

1. グループ **ページから** 1 つ以上の配布リスト (**配布グループ** とも呼ばれます) を選択します。

   ![配布グループを選択します。](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

1. アップグレード アイコンを選択します。

   ![Microsoft 365 グループへのアップグレード アイコン。](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

1. 情報ダイアログで、[ **はい** ] を選択してアップグレードを確認します。 プロセスがすぐに開始されます。 アップグレードする配布ライトのサイズと数によっては、プロセスに数分または数時間かかる場合があります。

   配布リストをアップグレードできない場合は、それを示すダイアログが表示されます。 [アップグレードできない配布リスト](#which-distribution-lists-cant-be-upgraded)を確認してください。

1. 複数の配布リストをアップグレードする場合は、ドロップダウン リストを使用して、アップグレードされた配布リストをフィルター処理します。 一覧が完了していない場合は、しばらく待ってから **[更新** ] を選択して、正常にアップグレードされた内容を確認します。

**注**:

- アップグレードが完了しても、通知は表示されません。 代わりに、[ **アップグレード可能]** または [ **アップグレードされた DLs] の** 一覧を参照してください。

- アップグレード用に配布リストを選択したが、[アップグレード可能] としてページに表示されている場合は、 **アップグレード** できませんでした。 「[アップグレードが機能しない場合の対処方法](#what-to-do-if-the-upgrade-doesnt-work)」を参照してください。

- グループのダイジェスト メールでは、自分が所有している対象となる配布リストをアップグレードできる場合があります。 ダイジェスト メールの詳細については、「 [Outlook でグループ会話を行う](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)」を参照してください。

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>アップグレードが機能しない場合の対処方法

アップグレードに失敗した配布リストは、変更されないまま保持されます。

1 つ以上の **対象となる** 配布リストをアップグレードできない場合は、次の手順を実行します。

1. [このスクリプト](https://aka.ms/DLToM365Group)を使用して、考えられる問題をスキャンします。 スクリプトによって報告されたすべての問題を修正し、配布リストをもう一度アップグレードしてみてください。 

2. スクリプトが役に立たない場合は、 [サポート チケット](../../business-video/get-help-support.md)を開きます。 この問題は、Groups Engineering チームにエスカレートする必要があります。

## <a name="how-to-use-exchange-online-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Exchange Online PowerShell を使用して複数の配布リストを同時にアップグレードする方法

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

### <a name="upgrade-a-single-distribution-list"></a>1 つの配布リストをアップグレードする

1 つの配布リストをアップグレードするには、次の構文を使用します。

```PowerShell
Upgrade-DistributionGroup -DLIdentities <EmailAddress>
```

次の使用例は、配布リスト marketing@contoso.com をアップグレードします。

```PowerShell
Upgrade-DistributionGroup -DLIdentities marketing@contoso.com
```

構文とパラメーターの詳細については、「 [Upgrade-DistributionGroup](/powershell/module/exchange/upgrade-distributiongroup)」を参照してください。

> [!NOTE]
> [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) コマンドレットを使用して、1 つの配布リストを Microsoft 365 グループにアップグレードすることもできます。

### <a name="upgrade-multiple-distribution-lists-at-the-same-time"></a>複数の配布リストを同時にアップグレードする

複数の配布リストを同時にアップグレードするには、次の構文を使用します。

```PowerShell
Upgrade-DistributionGroup -DLIdentities <EmailAddress1>,<EmailAddress2>,...
```

この例では、指定した配布リストを Microsoft 365 グループにアップグレードします。

```powershell
Upgrade-DistributionGroup -DLIdentities marketing@contoso.com,finanace@contoso.com,hr@contoso.com
```

構文とパラメーターの詳細については、「 [Upgrade-DistributionGroup](/powershell/module/exchange/upgrade-distributiongroup)」を参照してください。

### <a name="upgrade-all-eligible-distribution-lists"></a>対象となる配布リストをすべてアップグレードする

次のいずれかの方法を使用して、対象となるすべての配布リストを Microsoft 365 グループにアップグレードします。

- 対象となる配布リストをすべてアップグレードします。

   ```PowerShell
   $All = Get-EligibleDistributionGroupForMigration -ResultSize unlimited
   $All | Foreach-Object {Upgrade-DistributionGroup -DLIdentities $_.PrimarySMTPAddress}
   ```

- 対象となるかどうかにかかわらず、すべての配布リストをアップグレードしてみてください。

   ```PowerShell
   $All Get-DistributionGroup -RecipientTypeDetails MailUniversalDistributionGroup -ResultSize unlimited
   $All | Foreach-Object {Upgrade-DistributionGroup -DLIdentities $_.PrimarySMTPAddress}
   ```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Outlook の Microsoft 365 グループへの配布リストのアップグレードに関する FAQ

### <a name="which-distribution-lists-cant-be-upgraded"></a>アップグレードできない配布リストはどれですか?

クラウド管理されている、単純で入れ子になっていない配布リストのみをアップグレードできます。 次の表に、アップグレード **できない** 配布リストを示します。

|プロパティ|対象|
|---|:---:|
|オンプレミスで管理される配布リスト|いいえ|
|入れ子になった配布リスト子グループがあるか、または別のグループのメンバーである配布リスト|いいえ|
|1 つまたは複数のメンバーがユーザー メールボックス、共有メールボックス、チーム メールボックス、またはメール ユーザー以外のメンバーである配布リスト。 つまり、配布リストの任意のメンバーの **RecipientTypeDetails** 値は **、UserMailbox**、 **SharedMailbox**、 **TeamMailbox**、または **MailUser ではありません**。|いいえ|
|100 人以上の所有者がいる配布リスト。|不要|
|メンバーのみが含まれ、所有者は含まれない配布リスト。|いいえ|
|特殊文字を含むエイリアスを持つ配布リスト。|不要|
|配布リストは、共有メールボックスの転送先アドレスとして構成されます。|不要|
|配布リストは、別の配布リストの **送信者制限** の一部です。|いいえ|
|メールが有効なセキュリティ グループ。|不要|
|動的配布グループ。|いいえ|
|**RoomLists** に変換された配布リスト。|不要|

### <a name="check-which-distribution-lists-are-eligible-for-upgrade"></a>アップグレードの対象となる配布リストを確認する

特定の配布リストがアップグレードの対象かどうかを確認するには、次のコマンドを実行します。

```PowerShell
Get-DistributionGroup <EmailAddress> | Get-EligibleDistributionGroupForMigration
```

アップグレードの対象となるすべての配布グループを表示するには、次のコマンドを実行します。

```PowerShell
Get-EligibleDistributionGroupForMigration
```

### <a name="who-can-run-the-upgrade-scripts"></a>どのユーザーがアップグレード スクリプトを実行できますか?

グローバル管理者または Exchange 管理者権限を持つユーザー。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>連絡先カードに依然として配布リストが表示されるのはなぜでしょうか。 アップグレードされた配布リストが自動提案リストに表示されないようにするには、どうすればよいですか?

- **Outlook**: Ditribution リストを Microsoft 365 グループにアップグレードした後、ユーザーのローカル受信者キャッシュ (nick 名キャッシュとも呼ばれます) は変更を認識しません。 ユーザーのローカル受信者キャッシュをリセットするには、次の記事の手順を実行します: [Outlook AutoComplete リストに関する情報](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list)。 

  受信者キャッシュを更新しない場合、Microsoft 365 グループに送信されたメールは正常に配信されますが、次の問題は残ります。
  
  - グループの受信者は、Microsoft 365 グループの代わりに配布リストとして解決されます。
  - 連絡先カードは、Microsoft 365 グループの代わりに配布リストの連絡先になります。

- **Outlook on the web**: Outlook と同様に、配布リストは受信者キャッシュに残ります。 この記事の手順に従ってキャッシュを更新し、グループの連絡先カードを表示します。 [[オートコンプリート リスト] から推奨される名前または電子メール アドレスを削除します](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新しいグループのメンバーは、受信トレイでウェルカム メッセージを受け取りますか?

いいえ。 ウェルカム メッセージを有効にする設定は、既定で false に設定されています。 この設定は、既存のグループ メンバーにも、移行が完了した後に参加する可能性がある新しいグループ メンバーにも影響します。 グループ所有者が後でゲスト ユーザーを許可した場合、ゲスト ユーザーは受信トレイにウェルカム メールを受信しません。 ゲスト メンバーはグループで継続して作業を行うことができます。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>1 つまたは一部の DL がアップグレードされない場合はどうなりますか?

対象となる配布リストをアップグレードできない場合があります。 次に例を示します。

- 管理者が **グループ電子メール アドレス ポリシー** を適用し、配布リストがポリシーの要件を満たしていません。

- 配布リストには、 **MemberJoinRestriction** または **MemberDepartRestriction** が値 Closed に設定 **されています**。

- Microsoft 365 グループの作成は、この記事( [この記事](/microsoft-365/solutions/manage-creation-of-groups))で説明されているように制限されています。

  この特定の問題には、次のいずれかの回避策を使用します。

  - 配布リストのすべての所有者が Microsoft 365 グループの作成を許可されていることを確認します (つまり、所有者は、Microsoft 365 グループの作成が許可されているセキュリティ グループのメンバーです)。

  - 配布リストの所有者を、Microsoft 365 グループの作成を許可されているユーザーに一時的に置き換えます。

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>EAC からのアップグレードに失敗した場合、配布リストはどうなりますか?

呼び出しがサーバーに送信された場合にのみ、アップグレードが発生します。 アップグレードに失敗した場合、配布リストは残り、以前と同じように機能します。

### <a name="what-happens-to-message-approval-moderation-settings-on-distribution-groups-after-upgrading"></a>アップグレード後、配布グループのメッセージ承認 (モデレーション) 設定はどうなりますか?

メッセージ承認 (モデレーション) 設定は保持され、配布グループが Microsoft 365 グループにアップグレードされた後も引き続き正常に動作します。

## <a name="related-content"></a>関連コンテンツ

[グループの比較](../create-groups/compare-groups.md) (記事)\
[ユーザーへの Microsoft 365 グループの説明](../create-groups/explain-groups-knowledge-worker.md) (記事)\
[管理センターを使用して Microsoft 365 グループのメンバーを追加または削除する](../create-groups/add-or-remove-members-from-groups.md)
