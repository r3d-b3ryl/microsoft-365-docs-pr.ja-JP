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
description: グループメンバーの追加、電子メールアドレス、グループ名、説明の編集、グループの動作のカスタマイズなど、Microsoft 365 グループを管理する方法について説明します。
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753303"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでグループを管理する

[Microsoft 365 グループを作成](create-groups.md)し、グループメンバーを追加したら、グループを構成できます。 グループ名または説明を編集したり、所有者またはメンバーを管理したり、外部の送信者がグループに電子メールを送信できるかどうか、およびグループスレッドのコピーをメンバーに送信するかどうかを指定したりできます。

Microsoft 365 管理センター () に移動 [https://admin.microsoft.com](https://admin.microsoft.com) します。

## <a name="edit-the-group-name-or-description"></a>グループ名または説明を編集する

1. 管理センターで、[ **グループ**] を展開し、[ **グループ**] をクリックします。

2. 編集するグループを選択し、[ **名前と説明の編集**] をクリックします。

3. 名前と説明を更新し、[ **保存**] を選択します。

## <a name="manage-group-owners-and-members"></a>グループの所有者とメンバーを管理する

1. 管理センターで、[ **グループ**] を展開し、[ **グループ**] をクリックします。

2. 管理するグループの名前をクリックして、[設定] ウィンドウを開きます。

3. [ **メンバー** ] タブで、所有者またはメンバーを管理するかどうかを選択します。

4. [ **追加** ] を選択してユーザーを追加するか、[ **X** ] をクリックしてユーザーを削除します。

5. [閉じる] **** をクリックします。

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>会話のコピーをグループメンバーの受信トレイに送信する
  
管理センターを使用してグループを作成する場合、既定では、受信トレイに送信されるグループメールと会議出席依頼のコピーは取得されません。 会話や会議を表示するには、グループに移動する必要があります。 この設定は、管理センターで変更できます。

この設定をオンにすると、グループのメンバーは、Outlook 受信トレイに送信されたグループメールと会議出席依頼のコピーを取得します。 各メンバーはメールのコピーを閲覧、削除することができますが、他のメンバーに影響を与えることはありません。 グループの受信トレイに、メールのコピーは引き続き存在します。

グループメンバーは、Outlook でグループのフォローを停止することを選択することで、これらのメールを受信しないようにすることができます。

1. 管理センターで、[ **グループ**] を展開し、[ **グループ**] をクリックします。

2. 管理するグループの名前をクリックして、[設定] ウィンドウを開きます。

3. [ **設定** ] タブで、メンバーがグループメッセージおよび予定表アイテムのコピーを自分の受信トレイに受信するようにする場合は、[グループ **の会話とイベントのコピーをグループのメンバーに送信** する] を選択します。

4. **[保存]** を選択します。

## <a name="let-people-outside-the-organization-email-the-group"></a>組織外のユーザーがグループに電子メールを送信できるようにする

このオプションは、info@contoso.com のような会社の電子メールアドレスを使用する場合に適しています。
 
1. 管理センターで、[ **グループ**] を展開し、[ **グループ**] をクリックします。

2. 管理するグループの名前をクリックして、[設定] ウィンドウを開きます。

3. [管理センターグループ] リストで、変更するグループの名前を選択し、[ **設定** ] タブで [ **外部の送信者にメールを送信することを許可する**] を選択します。
    
4. **[保存]** を選択します。

## <a name="permanently-delete-a-microsoft-365-group"></a>Microsoft 365 グループを完全に削除する

場合によっては、30日間のソフト削除期間が経過するのを待たずに、グループを完全に削除する必要があります。 それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

完全に削除するグループまたはグループのオブジェクト ID を書き留めておきます。
  
> [!CAUTION]
> グループを削除すると、グループとそのデータが永久に削除されます。 
  
グループを削除するには、PowerShell で次のコマンドを実行します。

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。 
  
## <a name="related-articles"></a>関連記事

[Microsoft 365 グループを作成する](create-groups.md)

[Microsoft 365 グループへのゲストアクセスを管理する](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Microsoft 365 グループを作成するときに使用するドメインを選択する](../../solutions/choose-domain-to-create-groups.md)

[メンバーが Microsoft 365 グループの代理として送信または送信できるようにする](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

[PowerShell を使用して Microsoft 365 グループを管理する](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
