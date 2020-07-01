---
title: Advanced eDiscovery のクイック セットアップ
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: セキュリティ &amp; コンプライアンス センターから Advanced eDiscovery にアクセスする方法を説明し、Advanced eDiscovery を使用するための一般的なワークフローを確認します。
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936260"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) のクイック セットアップ

> [!IMPORTANT]
> 新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。 まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。 Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。 Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。 

このセットアップ セクションでは、Microsoft 365 セキュリティ&amp;コンプライアンス センターの電子情報開示管理者に、Advanced eDiscovery を開始する方法を示します。 両方に関して、実際上の知識があるものと想定しています。
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Advanced eDiscovery のケースへのアクセス

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
Advanced eDiscovery のケースに移動するには、以下を実施します: 
  
1. [セキュリティ&amp;コンプライアンス センターに移動します](go-to-the-securitycompliance-center.md)。 
    
2. セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。 
    
3. **[電子情報開示]** ページで、Advanced eDiscovery で移動するケースの横にある **[開く]** をクリックします。
    
4. ケースの [**ホーム**] ページで、[**Advanced eDiscovery に切り替え**] をクリックします。
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>ワークフロー

次の図は、セキュリティ&amp;コンプライアンス センターおよび Advanced eDiscovery において、電子情報開示ケースを管理および使用する一般的なワークフローを表したものです。
  
![図は、Advanced eDiscovery のワークフローを示しています。セットアップには、ユーザー&amp;ケースのセットアップ、ケース データの特定、エクスポート、処理の 4 つのフェーズがあり、その後に分析とローカル コンピューターへのエクスポートのフェーズがあります。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>分析

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>関連性のセットアップおよび関連性

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>エクスポート

[ケース データのエクスポート](export-case-data-in-advanced-ediscovery.md): 外部で校閲できるように、Advanced eDiscovery のコンテンツと結果のエクスポートを有効にします。 
  
## <a name="report"></a>レポート

[レポートを実行する](run-reports-in-advanced-ediscovery.md): 選択したレポートで Advanced eDiscovery の処理に関連するものの生成を有効にします。 
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ユーザーとケースのセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[データの準備](prepare-data-for-advanced-ediscovery.md)

