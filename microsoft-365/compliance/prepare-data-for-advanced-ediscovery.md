---
title: Advanced eDiscovery 用のデータを作成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: セキュリティ コンプライアンス センターを使用して、Advanced eDiscovery を使用して分析 &amp; 用のデータを準備する方法について説明します。
ms.openlocfilehash: 43253a3908925bc188568f020f48c62a94552403
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662882"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) のデータを準備する

このトピックでは、Advanced eDiscovery (クラシック) のケースにコンテンツ検索の結果を読み込む方法について説明します。 
  
> [!IMPORTANT]
> 新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。 まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション* とも呼ばれる) に移行してください。 Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。 Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a>手順 1: Advanced eDiscovery のデータを準備する

Advanced eDiscovery を使用してデータを分析するには、Microsoft 365 セキュリティ コンプライアンス センターで実行したコンテンツ検索の結果 &amp; (Microsoft  365 セキュリティ コンプライアンス センターの [コンテンツ検索] ページに表示される) または電子情報開示ケースに関連付けられた検索 &amp; (セキュリティ コンプライアンス センターの [電子情報開示] ページに一覧表示) を使用できます。 &amp; 
  
Advanced eDiscovery での分析用に検索結果を準備する詳細な手順については [、「Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md)の検索結果を準備する」を参照してください。
  
> [!NOTE]
> Microsoft 365 の外部にあるデータを Microsoft 365 にインポートして Advanced eDiscovery で準備および分析する場合は[、「Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)への PST ファイルの[](https://www.microsoft.com/?ref=go)インポートとサード パーティデータのアーカイブの概要」を参照してください。 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a>手順 2: Advanced eDiscovery のケースに検索結果データを読み込む

分析のためにセキュリティ コンプライアンス センターで検索結果を準備した後、次の手順では、検索結果を Advanced eDiscovery のケースに &amp; 読み込みます。 詳細については、「プロセス モジュールを実行 [する」を参照してください](run-the-process-module-in-advanced-ediscovery.md)。
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 職場または学校のアカウントを使用してサインインします。
    
3. セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。 
    
4. Advanced  eDiscovery でデータを読み込むケースの横にある [開く] をクリックします。 
    
5. ケースの [**ホーム**] ページで、[**Advanced eDiscovery に切り替え**] をクリックします。 
    
    ![[Advanced eDiscovery に切り替える] をクリックして Advanced eDiscovery でケースを開く](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Advanced **eDiscovery への接続の進行状況** バーが表示されます。 Advanced eDiscovery に接続すると、ケースのセットアップ ページにコンテナーの一覧が表示されます。 
    
    ![ケースが Advanced eDiscovery に表示される](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     これらのコンテナーは、手順 1 で Advanced eDiscovery で分析を準備した検索結果を表します。 コンテナーの名前は、セキュリティ コンプライアンス センターの場合はコンテンツ検索と同じ名前です &amp; 。 リスト内のコンテナーは、準備したコンテナーです。 別のユーザーが Advanced eDiscovery の検索結果を準備した場合、対応するコンテナーはリストに含まれません。 
    
6. コンテナーから Advanced eDiscovery のケースに検索結果データを読み込むには、コンテナーを選択し、[プロセス] をクリック **します**。
    
セキュリティ コンプライアンス センターからの検索結果が Advanced eDiscovery のケースに追加された後、次の手順では、Advanced eDiscovery のツールを使用して、ケースに関連するデータを分析し、収集します。 &amp; 
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ユーザーとケースをセットアップする](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[ケース データの分析](analyze-case-data-with-advanced-ediscovery.md)
  
[関連性のセットアップの管理](manage-relevance-setup-in-advanced-ediscovery.md)
  
[関連度モジュールの使用](use-relevance-in-advanced-ediscovery.md)
  
[ケース データのエクスポート](export-case-data-in-advanced-ediscovery.md)

