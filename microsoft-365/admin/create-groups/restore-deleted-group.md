---
title: 削除された Microsoft 365 グループを復元する
ms.reviewer: arvaradh
f1.keywords: CSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 削除されたグループは 30 日間保持され、引き続きグループを復元できます。 30 日後、グループとそのコンテンツは完全に削除されます。
ms.openlocfilehash: f16d8b13ad020aec48d39a61e2429b088cc5f2d1
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084193"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>削除された Microsoft 365 グループを復元する

グループを削除した場合、既定では 30 日間保持されます。 この 30 日間は、グループを復元できるため、"論理的な削除" と見なされます。 30 日後、グループとその関連コンテンツは完全に削除され、復元できません。

グループを復元すると、次のコンテンツが復元されます。
  
- Azure Active Directory (AD) Microsoft 365 グループオブジェクト、プロパティ、およびメンバーです。
    
- グループの電子メール アドレス。
    
- 共有受信トレイと予定表をExchange Onlineします。
    
- SharePoint Online チーム サイトとファイル。
    
- OneNote ノートブック
    
- Planner
    
- Teams

- Yammer グループとグループ のコンテンツ (Microsoft 365 グループが Yammer から作成された場合)

- Power BI [クラシック ワークスペース](/power-bi/collaborate-share/service-create-workspaces)

> [!NOTE]
> この記事では、Microsoft 365 グループのみを復元する方法について説明します。 削除後は、他のすべてのグループを復元できません。

## <a name="restore-a-group"></a>グループを復元する

# <a name="outlook"></a>[Outlook](#tab/outlook)

Microsoft 365 グループの所有者である場合は、次の手順に従って、Outlook on the webでグループを自分で復元できます。

1. [[削除されたグループ] ページ](https://outlook.office.com/people/group/deleted)で、[グループ] ノードの下にある [**グループ** の **管理**] オプションを選択し、[**削除済** み] を選択します。

2. 復元するグループの横にある [ **復元** ] タブをクリックします。

削除されたグループがここに表示されない場合は、管理者に問い合わせてください。

# <a name="admin-center"></a>[管理センター](#tab/admin-center)

グローバル管理者またはグループ管理者の場合は、Microsoft 365 管理センターで削除されたグループを復元できます。

1. [管理センター](https://admin.microsoft.com)にアクセスします。
2. [ **グループ]** を展開し、[ **削除済みグループ**] をクリックします。
3. 復元するグループを選択し、[ **グループの復元**] をクリックします。

> [!NOTE]
> 場合によっては、グループとそのすべてのデータが復元されるまでに 24 時間かかる場合があります。 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Microsoft 365 グループに関する質問はありますか?

[Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)にアクセスして質問を投稿し、Microsoft 365 グループに関する会話に参加します。 
  
## <a name="related-content"></a>関連コンテンツ

[PowerShell を使用してMicrosoft 365 グループを管理](../../enterprise/manage-microsoft-365-groups-with-powershell.md)する (記事)\
[Remove-UnifiedGroup コマンドレットを使用してグループを削除](/powershell/module/exchange/remove-unifiedgroup) する (article)\
[グループに接続されたチーム サイトの設定を管理](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) する (記事)\
[Outlook でグループを削除する](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (記事)
