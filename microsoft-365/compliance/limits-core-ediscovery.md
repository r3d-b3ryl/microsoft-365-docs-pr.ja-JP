---
title: コア電子情報開示ケースの制限
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: この記事では、Microsoft 365 のコア電子情報開示ケースの制限について説明します。
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905889"
---
# <a name="limits-in-core-ediscovery"></a>コア電子情報開示の制限

次の表に、コアの電子情報開示ケースと、コア電子情報開示ケースに関連付けられているホールドの制限を示します。 Core eDiscovery の詳細については、「Overview [of Core eDiscovery」を参照してください](./get-started-core-ediscovery.md)。
    
  | 制限の説明 | 制限 |
  |:-----|:-----|
  |組織のケースの最大数。  <br/> |制限なし  <br/> |
  |組織のケースホールドの最大数。  <br/> |10,000  <br/> |
  |1 つのケースホールド内のメールボックスの最大数。 この制限には、ユーザー メールボックスの合計と、Microsoft 365 グループ、Microsoft Teams、およびグループグループに関連付けられたメールボックスYammer含まれます。  <br/> |1,000  <br/> |
  |1 つのケースホールド内のサイトの最大数。 この制限には、OneDrive for Business サイト、SharePoint サイト、および Microsoft 365 グループ、Microsoft Teams、および Yammer グループに関連付けられたサイトの合計が含まれます。  <br/> |100  <br/> |
  |コアの電子情報開示ホーム ページに表示されるケースの最大数と、ケース内の [保持] タブ、[検索] タブ、および [エクスポート] タブに表示されるアイテムの最大数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 1,000 を超えるケース、ホールド、検索、またはエクスポートのリストを表示するには、対応する Office 365 Security & Compliance PowerShell コマンドレットを使用できます。
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Core eDiscovery ケースに関連付けられたコンテンツ検索とエクスポートに関連する制限の詳細については、「Limits for Content [Search and Core eDiscovery」を参照してください](limits-for-content-search.md)。