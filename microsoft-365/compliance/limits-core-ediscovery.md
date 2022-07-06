---
title: 電子情報開示 (Standard) ケースの制限
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: この記事では、Microsoft 365 の電子情報開示 (Standard) ケースの制限について説明します。
ms.openlocfilehash: fe564bfb26bf586ba6ff6567dae057ecb1065296
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634139"
---
# <a name="limits-in-ediscovery-standard"></a>電子情報開示の制限 (Standard)

次の表に、電子情報開示 (Standard) ケースの制限と、電子情報開示 (Standard) ケースに関連付けられている保留の一覧を示します。 Microsoft Purview eDiscovery (Standard) の詳細については、「[電子情報開示の概要 (Standard)](./get-started-core-ediscovery.md)」を参照してください。
    
  | 制限の説明 | 極限 |
  |:-----|:-----|
  |組織のケースの最大数。  <br/> |制限なし  <br/> |
  |組織のケース保留の最大数。  <br/> |10,000  <br/> |
  |1 つのケース保留のメールボックスの最大数。 この制限には、ユーザー メールボックスと、Microsoft 365 グループ、Microsoft Teams、Yammer グループに関連付けられているメールボックスの合計が含まれます。  <br/> |1,000 人  <br/> |
  |1 つのケースホールド内のサイトの最大数。 この制限には、OneDrive for Business サイト、SharePoint サイト、およびMicrosoft 365 グループ、Microsoft Teams、Yammer グループに関連付けられているサイトの合計が含まれます。  <br/> |100  <br/> |
  |電子情報開示 (Standard) ホーム ページに表示されるケースの最大数と、ケース内の [保留]、[検索]、[エクスポート] タブに表示されるアイテムの最大数。 <sup>1</sup> |1,000 人|

   > [!NOTE]
   > <sup>1</sup> 1,000 件を超えるケース、保留、検索、またはエクスポートの一覧を表示するには、対応するOffice 365 Security & Compliance PowerShell コマンドレットを使用できます。
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

電子情報開示 (Standard) ケースに関連付けられた検索とエクスポートに関連する制限の詳細については、「 [コンテンツ検索と電子情報開示 (Standard) の制限」](limits-for-content-search.md)を参照してください。