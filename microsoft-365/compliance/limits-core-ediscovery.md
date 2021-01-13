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
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799664"
---
# <a name="limits-in-core-ediscovery"></a>コア電子情報開示の制限

次の表に、コア電子情報開示ケースと、コア電子情報開示ケースに関連付けられている保留リストの制限を示します。 コア電子情報開示の詳細については、「コア電子情報開示の概要 [」を参照してください](ediscovery-cases.md)。
    
  | 制限の説明 | 極限 |
  |:-----|:-----|
  |組織のケースの最大数  <br/> |制限なし  <br/> |
  |組織のケース保留の最大数  <br/> |10,000  <br/> |
  |1 つのケース保留のメールボックスの最大数  <br/> |1,000  <br/> |
  |1 つのケース保留の SharePoint および OneDrive for Business サイトの最大数  <br/> |100  <br/> |
  |コア電子情報開示ホーム ページに表示されるケースの最大数と、ケース内の [保留リスト]、[検索]、および [エクスポート] タブに表示されるアイテムの最大数。 <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 1,000 件を超えるケース、保留、検索、またはエクスポートの一覧を表示するには、対応する Office 365 Security & Compliance PowerShell コマンドレットを使用できます。
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

コア電子情報開示ケースに関連するコンテンツ検索とエクスポートに関連する制限の詳細については、「コンテンツ検索とコア電子情報開示の制限」を参照 [してください](limits-for-content-search.md)。