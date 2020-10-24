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
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753245"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>削除された Microsoft 365 グループを復元する

グループを削除した場合、既定では30日間保持されます。 この30日の期間は、引き続きグループを復元できるため、"ソフト削除" と見なされます。 30日後、グループとそれに関連するコンテンツは完全に削除され、復元することはできません。

グループを復元すると、次のコンテンツが復元されます。
  
- Azure Active Directory (AD) Microsoft 365 グループオブジェクト、プロパティ、およびメンバー。
    
- グループの電子メールアドレス。
    
- Exchange Online の共有の受信トレイと予定表。
    
- SharePoint Online チームサイトとファイル。
    
- OneNote ノートブック
    
- Planner
    
- Teams

- Yammer グループとグループのコンテンツ (Yammer から Microsoft 365 グループが作成されている場合)

> [!NOTE]
> この記事では、Microsoft 365 グループのみを復元する方法について説明します。 他のすべてのグループは、削除された後に復元することはできません。

## <a name="restore-a-group"></a>グループを復元する

# <a name="outlook"></a>[Outlook](#tab/outlook)

Microsoft 365 グループの所有者である場合は、次の手順に従って、そのグループを web 上の Outlook で自分で復元することができます。

1. [[削除さ](https://outlook.office.com/people/group/deleted)れたグループ] ページで、[**グループ**] ノードの下の [**グループの管理**] オプションを選択し、[**削除済み**] を選択します。

2. 復元するグループの横にある [ **復元** ] タブをクリックします。

削除されたグループがここに表示されない場合は、管理者に問い合わせてください。

# <a name="admin-center"></a>[管理センター](#tab/admin-center)

グローバル管理者またはグループ管理者の場合は、次のように、削除されたグループを Microsoft 365 管理センターで復元できます。

1. [管理センター](https://admin.microsoft.com)にアクセスします。
2. [ **グループ**] を展開し、[ **削除済みグループ**] をクリックします。
3. 復元するグループを選択し、[ **グループの復元**] をクリックします。

> [!NOTE]
> 場合によっては、グループとそのすべてのデータが復元されるまでに24時間かかることがあります。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Microsoft 365 グループに関する質問

Microsoft [技術コミュニティ](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) にアクセスして、microsoft 365 グループに関する質問を投稿し、会話に参加してください。 
  
## <a name="related-articles"></a>関連記事

[PowerShell を使用して Microsoft 365 グループを管理する](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Remove-UnifiedGroup コマンドレットを使用してグループを削除する](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[グループに接続されたチーム サイトの設定を管理する](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Outlook でグループを削除する](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
