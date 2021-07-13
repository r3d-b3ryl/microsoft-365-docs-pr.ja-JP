---
title: 削除された Microsoft 365 グループを復元する
ms.reviewer: arvaradh
f1.keywords: CSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 削除されたグループは 30 日間保持され、グループを復元できます。 30 日後、グループとそのコンテンツは完全に削除されます。
ms.openlocfilehash: ddc3da57c05b7c5f54c10a0cc429c9a3f24b859c
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394053"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>削除された Microsoft 365 グループを復元する

グループを削除した場合、既定では 30 日間保持されます。 この 30 日間の期間は、グループを復元することができますので、"soft-delete" と見なされます。 30 日後、グループとその関連コンテンツは完全に削除され、復元できません。

グループを復元すると、次のコンテンツが復元されます。
  
- Azure Active Directory (AD) Microsoft 365 Groups オブジェクト、プロパティ、およびメンバーを指定します。
    
- グループの電子メール アドレス。
    
- Exchange Online受信トレイと予定表を共有します。
    
- SharePointオンライン チーム サイトとファイル。
    
- OneNote ノートブック
    
- Planner
    
- Teams

- Yammerグループとグループ のコンテンツ (Microsoft 365グループがグループから作成されたYammer)

> [!NOTE]
> この記事では、グループの復元Microsoft 365説明します。 他のすべてのグループは、一度削除すると復元できません。

## <a name="restore-a-group"></a>グループの復元

# <a name="outlook"></a>[Outlook](#tab/outlook)

グループの所有者である場合は、Microsoft 365手順に従って、Outlook on the webを復元できます。

1. [削除された [グループ] ページで、[](https://outlook.office.com/people/group/deleted)グループ] ノードの **[** グループの管理] オプションを選択し、[削除済み]**を選択します**。

2. 復元するグループ **の** 横にある [復元] タブをクリックします。

削除されたグループがここに表示されない場合は、管理者に問い合わせてください。

# <a name="admin-center"></a>[管理センター](#tab/admin-center)

グローバル管理者またはグループ管理者の場合は、次の操作を実行して削除したグループを復元Microsoft 365 管理センター。

1. [管理センター](https://admin.microsoft.com)にアクセスします。
2. [グループ **] を展開** し、[削除済 **みグループ] をクリックします**。
3. 復元するグループを選択し、[グループの復元] **をクリックします**。

> [!NOTE]
> 場合によっては、グループとそのすべてのデータが復元に 24 時間かかる場合があります。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>グループに関する質問Microsoft 365しましたか?

質問を[投稿し、Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)グループに関する会話に参加するには、Microsoft Tech Microsoft 365をご覧ください。 
  
## <a name="related-content"></a>関連コンテンツ

[PowerShell Microsoft 365グループの管理](../../enterprise/manage-microsoft-365-groups-with-powershell.md)(記事)\
[Remove-UnifiedGroupコマンドレットを使用してグループを](/powershell/module/exchange/remove-unifiedgroup) 削除する (記事)\
[グループに接続されたチーム サイトの設定を管理](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) する (記事)\
[グループを削除する (Outlook)](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)