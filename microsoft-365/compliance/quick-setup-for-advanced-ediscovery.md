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
description: 'セキュリティ &amp; コンプライアンス センターから Advanced eDiscovery にアクセスする方法を説明し、Advanced eDiscovery を使用するための一般的なワークフローを確認します。  '
ms.openlocfilehash: 62c2ef316daafebeba6f91483277ea344039a271
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632172"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) のクイック セットアップ

> [!IMPORTANT]
> 新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。 まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。 Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。 Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。 

このセットアップ セクションでは、Microsoft 365 セキュリティ&amp;コンプライアンス センターの電子情報開示管理者に、Advanced eDiscovery を開始する方法を示します。 両方に関して、実際上の知識があるものと想定しています。
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Advanced eDiscovery のケースへのアクセス


セキュリティ&amp;コンプライアンス センターから Advanced eDiscovery にアクセスします。Advanced eDiscovery のケースにアクセスするには、セキュリティ&amp;コンプライアンス センターの電子情報開示ケースのメンバーである必要があります。電子情報開示ケースのアクセス許可の割り当て方法、電子情報開示ケースへのユーザーの追加方法については、「[Office 365 で電子情報開示ケースを管理する](ediscovery-cases.md)」を参照してください。 
  
Advanced eDiscovery のケースに移動するには、以下を実施します: 
  
1. [セキュリティ&amp;コンプライアンス センターに移動します](go-to-the-securitycompliance-center.md)。 
    
2. セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。 
    
3. **[電子情報開示]** ページで、Advanced eDiscovery で移動するケースの横にある **[開く]** をクリックします。 
    
4. ケースの **[ホーム]** ページで、**[Advanced eDiscovery]** をクリックします。
    
    **[Advanced eDiscovery へ接続しています]** の進行状況バーが表示されます。接続されると、Advanced eDiscovery のケースが開きます。 
    
## <a name="workflow"></a>ワークフロー

次の図は、セキュリティ&amp;コンプライアンス センターおよび Advanced eDiscovery において、電子情報開示ケースを管理および使用する一般的なワークフローを表したものです。 
  
![図は、Advanced eDiscovery のワークフローを示しています。セットアップには、ユーザー&amp;ケースのセットアップ、ケース データの特定、エクスポート、処理の 4 つのフェーズがあり、その後に分析とローカル コンピューターへのエクスポートのフェーズがあります。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
このセットアップ セクションでは、上記ワークフローの最初の 4 つの手順について説明します。ワークフローの他の手順については、以下を参照してください。
  
## <a name="analyze"></a>分析

[ケース データの分析](analyze-case-data-with-advanced-ediscovery.md): さまざまなパラメーターでファイルの識別および整理を行い、テーマの使用を有効にして、結果を表示します。ユーザーは分析機能をカスタマイズして、詳細な結果を得ることができます。 
  
## <a name="relevance-setup-and-relevance"></a>関連性のセットアップおよび関連性

[関連性のセットアップ](manage-relevance-setup-in-advanced-ediscovery.md)と[関連性モジュールの使用](use-relevance-in-advanced-ediscovery.md): ファイルのランダムなサンプルに基づく評価と関連性トレーニングを有効にし、その評価と関連性トレーニングを使用して、予測されるコーディング プロセスを決定します。プロセスの統計上の妥当性を監視しながら、中間結果を計算して表示します。校閲の意思決定を容易にする結果を表示します。 
  
## <a name="export"></a>エクスポート

[ケース データのエクスポート](export-case-data-in-advanced-ediscovery.md): 外部で校閲できるように、Advanced eDiscovery のコンテンツと結果のエクスポートを有効にします。 
  
## <a name="report"></a>レポート

[レポートを実行する](run-reports-in-advanced-ediscovery.md): 選択したレポートで Advanced eDiscovery の処理に関連するものの生成を有効にします。 
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ユーザーとケースのセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[データの準備](prepare-data-for-advanced-ediscovery.md)

