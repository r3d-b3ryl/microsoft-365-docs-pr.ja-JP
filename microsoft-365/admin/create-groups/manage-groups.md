---
title: 管理センターでグループを管理する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: グループ メンバーのMicrosoft 365、電子メール アドレス、グループ名、または説明の編集、グループの動作のカスタマイズなど、さまざまなグループを管理する方法について説明します。
ms.openlocfilehash: 12c1b74986429be8c2681725286a3e07b7ae1d86
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58393414"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>グループを管理するMicrosoft 365 管理センター

グループを[作成し、Microsoft 365メンバー](create-groups.md)を追加したら、グループを構成できます。 グループ名または説明の編集、所有者またはメンバーの管理、外部送信者がグループにメールを送信できるかどうか、およびグループ会話のコピーをメンバーに送信するかどうかを指定できます。

で、Microsoft 365 管理センターに移動します [https://admin.microsoft.com](https://admin.microsoft.com) 。

## <a name="edit-the-group-name-or-description"></a>グループ名または説明を編集する

1. 管理センターで、[グループ] を **展開し**、[グループ] を <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**クリックします**</a>。

2. 編集するグループを選択し、[名前と説明の編集 **] をクリックします**。

3. 名前と説明を更新し、[保存] を **選択します**。

## <a name="manage-group-owners-and-members"></a>グループの所有者とメンバーを管理する

1. 管理センターで、[グループ] を **展開し**、[グループ] を <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**クリックします**</a>。

2. 管理するグループの名前をクリックして、設定ウィンドウを開きます。

3. [メンバー **] タブ** で、所有者またはメンバーを管理する場合を選択します。

4. [追加 **] を** 選択してユーザーを追加するか **、[X] をクリックして** ユーザーを削除します。

5. [閉じる] をクリックします。

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>グループ メンバーの受信トレイに会話のコピーを送信する
  
管理センターを使用してグループを作成する場合、既定では、ユーザーは受信トレイに送信されたグループメールのコピーを取得しますが、ユーザーは受信トレイに送信されたグループ会議出席依頼のコピーを取得します。 会話を表示するには、グループに移動する必要があります。 管理センターでこの設定を変更できます。

この設定を有効にすると、グループ メンバーは、グループメールのコピーと、受信トレイに送信された会議出席依頼Outlookされます。 各メンバーはメールのコピーを閲覧、削除することができますが、他のメンバーに影響を与えることはありません。 グループの受信トレイに、メールのコピーは引き続き存在します。

グループ メンバーは、グループ内のグループに従うのを停止することを選択して、これらのメールの受信をOutlook。

1. 管理センターで、[グループ] を **展開し**、[グループ] を <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**クリックします**</a>。

2. 管理するグループの名前をクリックして、設定ウィンドウを開きます。

3. [グループ **メッセージ設定]** タブで、[グループの会話とイベントのコピーをグループ メンバーに送信する] を選択します。メンバーがグループ メッセージと予定表アイテムのコピーを自分の受信トレイで受信する場合。

4. **[保存]** を選択します。

## <a name="let-people-outside-the-organization-email-the-group"></a>組織外のユーザーがグループにメールを送信する

このオプションは、会社の電子メール アドレス (電子メール アドレスなど) を使用する場合 info@contoso.com。
 
1. 管理センターで、[グループ] を **展開し**、[グループ] を <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**クリックします**</a>。

2. 管理するグループの名前をクリックして、設定ウィンドウを開きます。

3. 管理センター グループの一覧で、変更するグループの名前を選択し、[設定] タブ **で、[** このグループにメールを送信する外部送信者を許可する] を **選択します**。
    
4. **[保存]** を選択します。

## <a name="permanently-delete-a-microsoft-365-group"></a>グループを完全Microsoft 365する

30 日間のソフト削除期間の有効期限が切れるのを待たずに、グループを完全に削除する場合があります。 それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

完全に削除するグループまたはグループのオブジェクト ID をメモします。
  
> [!CAUTION]
> グループを削除すると、グループとそのデータが永久に削除されます。 
  
グループを削除するには、PowerShell で次のコマンドを実行します。

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。 
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 グループを作成する](create-groups.md)

[Microsoft 365 グループへのゲスト アクセスの管理](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[グループの作成時に使用するドメインMicrosoft 365する](../../solutions/choose-domain-to-create-groups.md)

[メンバーがグループの代理として送信または送信Microsoft 365する](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[配布リストをグループにMicrosoft 365する](../manage/upgrade-distribution-lists.md)

[PowerShell Microsoft 365グループを管理する](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
