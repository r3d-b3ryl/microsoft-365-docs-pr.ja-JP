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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: グループ メンバーの削除の追加、電子メール アドレス、グループ名、または説明の編集、グループの動作のカスタマイズなど、Microsoft 365 グループの管理について説明します。
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908712"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでグループを管理する

[Microsoft 365 グループを作成](create-groups.md)し、グループ メンバーを追加したら、グループを構成できます。 グループ名または説明の編集、所有者またはメンバーの管理、外部送信者がグループにメールを送信できるかどうか、およびグループ会話のコピーをメンバーに送信するかどうかを指定できます。

で Microsoft 365 管理センターに移動します [https://admin.microsoft.com](https://admin.microsoft.com) 。

## <a name="edit-the-group-name-or-description"></a>グループ名または説明を編集する

1. 管理センターで、[グループ] を **展開し**、[グループ] を **クリックします**。

2. 編集するグループを選択し、[名前と説明の編集 **] をクリックします**。

3. 名前と説明を更新し、[保存] を **選択します**。

## <a name="manage-group-owners-and-members"></a>グループの所有者とメンバーを管理する

1. 管理センターで、[グループ] を **展開し**、[グループ] を **クリックします**。

2. 管理するグループの名前をクリックして、設定ウィンドウを開きます。

3. [メンバー **] タブ** で、所有者またはメンバーを管理する場合を選択します。

4. [追加 **] を** 選択してユーザーを追加するか **、[X] をクリックして** ユーザーを削除します。

5. **[閉じる]** をクリックします。

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>グループ メンバーの受信トレイに会話のコピーを送信する
  
管理センターを使用してグループを作成する場合、既定では、ユーザーは受信トレイに送信されるグループメールと会議出席依頼のコピーを取得されません。 会話や会議を表示するには、グループに移動する必要があります。 管理センターでこの設定を変更できます。

この設定を有効にすると、グループ メンバーは Outlook 受信トレイに送信されたグループメールと会議出席依頼のコピーを取得します。 各メンバーはメールのコピーを閲覧、削除することができますが、他のメンバーに影響を与えることはありません。 グループの受信トレイに、メールのコピーは引き続き存在します。

グループ メンバーは、Outlook でグループの実行を停止することを選択して、これらのメールの受信をオプトアウトできます。

1. 管理センターで、[グループ] を **展開し**、[グループ] を **クリックします**。

2. 管理するグループの名前をクリックして、設定ウィンドウを開きます。

3. [設定 **] タブ** で、メンバーが自分の受信トレイでグループ メッセージと予定表アイテムのコピーを受信する場合は、[グループ会話とイベントのコピーをグループ メンバーに送信する] を選択します。

4. **[保存]** を選択します。

## <a name="let-people-outside-the-organization-email-the-group"></a>組織外のユーザーがグループにメールを送信する

このオプションは、会社の電子メール アドレス (電子メール アドレスなど) を使用する場合 info@contoso.com。
 
1. 管理センターで、[グループ] を **展開し**、[グループ] を **クリックします**。

2. 管理するグループの名前をクリックして、設定ウィンドウを開きます。

3. 管理センター グループの一覧で、変更するグループの名前を選択し、[設定] タブで、[このグループにメールを送信する外部送信者を許可する]**を選択します**。
    
4. **[保存]** を選択します。

## <a name="permanently-delete-a-microsoft-365-group"></a>Microsoft 365 グループを完全に削除する

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

[Microsoft 365 グループの作成](create-groups.md)

[Microsoft 365 グループへのゲスト アクセスを管理する](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Microsoft 365 グループの作成時に使用するドメインを選択する](../../solutions/choose-domain-to-create-groups.md)

[メンバーが Microsoft 365 グループの代理として送信または送信を許可する](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell を使用して Microsoft 365 グループを管理する](../../enterprise/manage-microsoft-365-groups-with-powershell.md)