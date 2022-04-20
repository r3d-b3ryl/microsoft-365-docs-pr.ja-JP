---
title: 電子情報開示 (Standard) ケースの制限
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: この記事では、Microsoft 365の電子情報開示 (Standard) ケースの制限について説明します。
ms.openlocfilehash: 29d1ef4d017ebf26a0c5ed1cc03fcf4361266e94
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64994108"
---
# <a name="limits-in-ediscovery-standard"></a>電子情報開示の制限 (Standard)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

次の表に、電子情報開示 (Standard) ケースの制限と、電子情報開示 (Standard) ケースに関連付けられている保留の一覧を示します。 Microsoft Purview 電子情報開示 (Standard) の詳細については、「 [電子情報開示の概要 (Standard)](./get-started-core-ediscovery.md)」を参照してください。
    
  | 制限の説明 | 極限 |
  |:-----|:-----|
  |組織のケースの最大数。  <br/> |無制限  <br/> |
  |組織のケースホールドの最大数。  <br/> |10,000  <br/> |
  |1 つのケースホールド内のメールボックスの最大数。 この制限には、ユーザー メールボックスの合計と、Microsoft 365 グループ、Microsoft Teams、Yammer グループに関連付けられているメールボックスの合計が含まれます。  <br/> |1,000  <br/> |
  |1 つのケースホールド内のサイトの最大数。 この制限には、OneDrive for Business サイト、SharePoint サイト、Microsoft 365 グループ、Microsoft Teams、Yammer グループに関連付けられているサイトの合計が含まれます。  <br/> |100  <br/> |
  |電子情報開示 (Standard) ホーム ページに表示されるケースの最大数と、ケース内の [保留]、[検索]、[エクスポート] タブに表示されるアイテムの最大数。 <sup>1</sup> |1,000|

   > [!NOTE]
   > <sup>1</sup> 1,000 件を超えるケース、保留、検索、またはエクスポートの一覧を表示するには、対応するOffice 365 Security & Compliance PowerShell コマンドレットを使用できます。
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

電子情報開示 (Standard) ケースに関連付けられた検索とエクスポートに関連する制限の詳細については、「 [コンテンツ検索と電子情報開示 (Standard) の制限」](limits-for-content-search.md)を参照してください。