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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 削除された Microsoft 365 グループを復元する方法について説明します。
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910548"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>削除された Microsoft 365 グループを復元する

グループを削除した場合、既定では 30 日間保持されます。 この 30 日間の期間は、グループを復元することができますので、"soft-delete" と見なされます。 30 日後、グループとその関連コンテンツは完全に削除され、復元できません。

グループを復元すると、次のコンテンツが復元されます。
  
- Azure Active Directory (AD) Microsoft 365 Groups オブジェクト、プロパティ、およびメンバー。
    
- グループの電子メール アドレス。
    
- Exchange Online 共有受信トレイと予定表。
    
- SharePoint Online チーム サイトとファイル。
    
- OneNote ノートブック
    
- Planner
    
- Teams

- Yammerグループおよびグループ コンテンツ (Microsoft 365 グループがグループから作成されたYammer)

> [!NOTE]
> この記事では、Microsoft 365 グループのみを復元する方法について説明します。 他のすべてのグループは、一度削除すると復元できません。

## <a name="restore-a-group"></a>グループの復元

# <a name="outlook"></a>[Outlook](#tab/outlook)

Microsoft 365 グループの所有者である場合は、次の手順に従って Outlook on the web でグループを自分で復元できます。

1. [削除された [グループ] ページで、[](https://outlook.office.com/people/group/deleted)グループ] ノードの **[** グループの管理] オプションを選択し、[削除済み]**を選択します**。

2. 復元するグループ **の** 横にある [復元] タブをクリックします。

削除されたグループがここに表示されない場合は、管理者に問い合わせてください。

# <a name="admin-center"></a>[管理センター](#tab/admin-center)

グローバル管理者またはグループ管理者の場合は、Microsoft 365 管理センターで削除されたグループを復元できます。

1. [管理センター](https://admin.microsoft.com)にアクセスします。
2. [グループ **] を展開** し、[削除済 **みグループ] をクリックします**。
3. 復元するグループを選択し、[グループの復元] **をクリックします**。

> [!NOTE]
> 場合によっては、グループとそのすべてのデータが復元に 24 時間かかる場合があります。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Microsoft 365 グループについて質問がありますか?

Microsoft Tech [Community にアクセスして質問](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) を投稿し、Microsoft 365 グループに関する会話に参加します。 
  
## <a name="related-articles"></a>関連記事

[PowerShell を使用して Microsoft 365 グループを管理する](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[Remove-UnifiedGroup コマンドレットを使用してグループを削除する](/powershell/module/exchange/remove-unifiedgroup)
  
[グループに接続されたチーム サイトの設定を管理する](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Outlook でグループを削除する](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)