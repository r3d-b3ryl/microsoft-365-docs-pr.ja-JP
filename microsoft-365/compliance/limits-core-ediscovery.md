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
ms.openlocfilehash: 6224ce5ecb8fc0439e43ab5e1362f8a618194202
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358515"
---
# <a name="limits-in-core-ediscovery"></a>コア電子情報開示の制限

次の表に、主要な電子情報開示ケースの制限と、コア電子情報開示ケースに関連付けられている保留リストを示します。 コア電子情報開示の詳細については、「 [コア電子情報開示の概要](ediscovery-cases.md)」を参照してください。
    
  |**制限の説明**|**制限**|
  |:-----|:-----|
  |組織のケースの最大数  <br/> |制限なし  <br/> |
  |組織のケース保留の最大数  <br/> |10,000  <br/> |
  |1 つのケース保留のメールボックスの最大数  <br/> |1,000  <br/> |
  |1 つのケース保留の SharePoint および OneDrive for Business サイトの最大数  <br/> |100  <br/> |
  |コア電子情報開示のホームページに表示されるケースの最大数と、ケース内で保持、検索、およびエクスポートタブに表示されるアイテムの最大数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 1000 ケース、ホールド、検索、またはエクスポートの一覧を表示するには、対応する Office 365 Security & コンプライアンス PowerShell コマンドレットを使用できます。<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [New-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
