---
title: 管理センターでグループを管理する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: グループ メンバーの削除の追加、メール アドレス、グループ名、説明の編集、グループの動作のカスタマイズなど、Microsoft 365 グループを管理する方法について説明します。
ms.openlocfilehash: 7dd17072beab3c8b1cf09f6a6263cf6eb9fa089c
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084237"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでグループを管理する

[Microsoft 365 グループを作成](create-groups.md)し、グループ メンバーを追加したら、グループを構成できます。 グループ名または説明の編集、所有者またはメンバーの管理が行えます。さらに、外部送信者がグループにメールを送信できるかどうか指定したり、グループ会話のコピーをメンバーに送信するかどうかを指定できます。

[https://admin.microsoft.com](https://admin.microsoft.com) の Microsoft 365 管理センターに移動します。

## <a name="edit-the-group-name-or-description"></a>グループ名または説明を編集する

1. 管理センターで [ **グループ**] を展開し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**グループ**</a>] をクリックします。

2. 編集するグループを選択してから **[名前と説明の編集]** をクリックします。

3. 名前と説明を更新してから **[保存]** を選択します。

## <a name="manage-group-owners-and-members"></a>グループの所有者とメンバーを管理する

1. 管理センターで [ **グループ**] を展開し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**グループ**</a>] をクリックします。

2. 管理するグループの名前をクリックし、[設定] ウィンドウを開きます。

3. **[メンバー]** タブで、所有者またはメンバーを管理する場合を選択します。

4. [ **追加]** を選択してユーザーを追加するか、[ **X** ] をクリックしてユーザーを削除します。

5. [閉じる] をクリックします。

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>グループ メンバーの受信トレイに会話のコピーを送信する
  
管理センターを使用してグループを作成する場合、既定では、ユーザーは受信トレイに送信されたグループ会議出席依頼のコピーを受信トレイに届けますが、グループメールのコピーは取得されません。 会話を表示するには、グループに移動する必要があります。 この設定は、管理センターで変更できます。

この設定をオンにすると、グループ メンバーは Outlook 受信トレイに送信されたグループメールと会議出席依頼のコピーを取得します。 各メンバーはメールのコピーを閲覧、削除することができますが、他のメンバーに影響を与えることはありません。 グループの受信トレイに、メールのコピーは引き続き存在します。

グループ メンバーは、Outlook でグループのフォローを停止することで、これらのメールの受信をオプトアウトできます。

1. 管理センターで [ **グループ**] を展開し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**グループ**</a>] をクリックします。

2. 管理するグループの名前をクリックし、[設定] ウィンドウを開きます。

3. メンバーが自分の受信トレイでグループ メッセージと予定表アイテムのコピーを受信する場合は、[ **設定]** タブで、[ **グループの会話とイベント** のコピーをグループ メンバーに送信する] を選択します。

4. **[保存]** を選択します。

## <a name="let-people-outside-the-organization-email-the-group"></a>組織外のユーザーがグループにメールを送信できるようにする

このオプションは、info@contoso.com などの会社の電子メール アドレスを設定する場合に適しています。
 
1. 管理センターで [ **グループ**] を展開し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**グループ**</a>] をクリックします。

2. 管理するグループの名前をクリックし、[設定] ウィンドウを開きます。

3. 管理センター グループの一覧で、変更するグループの名前を選択し、[ **設定]** タブで[ **外部送信者にこのグループへのメール送信を許可** する] を選択します。
    
4. **[保存]** を選択します。

> [!NOTE]
> 組織外のユーザーがグループにメールを送信するには、最大で 30 分かかる場合があります。

## <a name="permanently-delete-a-microsoft-365-group"></a>Microsoft 365 グループを完全に削除する

30 日間の論理的な削除期間の有効期限が切れるのを待たずに、グループを完全に消去したい場合があります。 それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。
 
 ```powershell
Get-AzureADMSDeletedGroup
```

完全に削除するグループのオブジェクト ID をメモしておきます。
  
> [!CAUTION]
> グループを削除すると、グループとそのデータが永久に削除されます。 
  
グループを削除するには、PowerShell で次のコマンドを実行します。

```powershell
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。 
  
## <a name="related-articles"></a>関連資料

[Microsoft 365 グループを作成する](create-groups.md)

[Microsoft 365 グループへのゲスト アクセスを管理する](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Microsoft 365 グループを作成するときに使用するドメインを選択する](../../solutions/choose-domain-to-create-groups.md)

[メンバーが Microsoft 365 グループに代わって送信または送信できるようにする](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[配布リストをMicrosoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell でMicrosoft 365 グループを管理する](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
