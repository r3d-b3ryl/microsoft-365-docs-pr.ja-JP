---
title: Advanced eDiscovery で Process モジュールを実行し、データを読み込む
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: セキュリティ &amp; コンプライアンスセンターを使用して高度な電子情報開示にアクセスし、ケースに対して Process モジュールを実行する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 011a8448c36ac9f4726f13471c548b7bb2427000
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936160"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a>Process モジュールを実行し、Advanced eDiscovery でデータを読み込む (クラシック)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
このセクションでは、Advanced eDiscovery プロセスモジュールの機能について説明します。 
  
ファイルデータに加えて、ファイルの種類、拡張子、場所またはパス、作成日時、作成者、保管担当者、および件名などのメタデータは、高度な電子情報開示に読み込んで、各ケースごとに保存することができます。 一部のメタデータは、アドバンスト eDiscovery によって計算されます。たとえば、ネイティブファイルが読み込まれるときなどです。 
  
Advanced eDiscovery は、重複したグループや関連性のスコアなど、システムメタデータの値を提供します。 ファイル注釈などのその他のメタデータは、管理者が追加できます。 
  
## <a name="running-process"></a>実行中のプロセス

> [!NOTE]
> バッチ番号は、プロセス中にファイルの追跡を許可するためにファイルに割り当てられます。 バッチ番号を使用して、再処理オプションのプロセスバッチを識別することもできます。 バッチ番号およびセッションによるフィルター処理には、追加のフィルターを使用できます。 
  
プロセスを実行するには、次の手順を実行します。
  
1. [セキュリティ &amp; を開くコンプライアンスセンター](go-to-the-securitycompliance-center.md) 
    
2. [**検索 &amp; 調査** \> ]**電子情報開示**に移動し、[ **Advanced ediscovery に移動**] をクリックします。
    
3. [高度な電子情報開示] で、[表示される**ケース**] ページで適切なケースを選択し、[**ケースに移動] を**クリックします。
    
4. [ **Prepare** \> **プロセス** \> **セットアップ**の準備] で、使用可能なコンテナーの一覧からコンテナーを選択します。
    
    ![検索結果をケースに追加するには、[処理] をクリックします。](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. [**詳細設定**] をクリックします。コンテナーを seed ファイルとして、またはタグ付け済みファイルとして追加する場合。 
    
    低低解像度 (通常は2% 以下) の問題のトレーニングを高速化するには、シードファイルを使用します。 シードファイルの場合、さまざまな関連性のあるファイルとプロセスを選択することをお勧めします。1つの問題については、20-50 のシードを使用する必要があります (多くのシードファイルが関連性の結果をスキューする可能性があります)。 シードファイルは、問題をトレーニングするのと同じ担当者が見直す必要があります。
    
    事前にタグ付けされたファイルを使用して、関連性トレーニングを自動化します。 少なくとも1500ファイルにタグを付けて、関連性があるコレクションと同じように関連していないファイルに関連する割合を維持する必要があります。 これらのファイルは手動でタグ付けする必要があり、タグの品質に自信を持っている必要があります。
    
    ![バッチファイルを処理するための [詳細設定] ページのスクリーンショット](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - [ **Seed** ] セクションで、次のようにします。 
    
    [ **Seed ファイルとしてマーク**] を選択して、コンテナーをシードファイルとしてマークします。 [**問題**] ドロップダウンから、問題ごとに割り当てるように選択する必要もあります。 [**タグ**] ドロップダウンから **[関連する] または**[**無関係**] を選択します。 
    
    > [!NOTE]
    > ファイルを**Seed**として設定すると、**あらかじめタグ**付けされたマークを付けることはできません。 
  
  - [**プリタグ付け**されたファイル] セクションで、次の手順を実行します。 
    
    [**プリタグ付きファイルとしてマーク**する] を選択して、タグ付きファイルとしてコンテナーをマークします。 [**懸案事項**] ボックスの一覧から、問題ごとに割り当てる必要もあります。 [**タグ**] ドロップダウンから **[関連する] または**[**無関係**] を選択します。 
    
    > [!NOTE]
    > **プリタグ付き**でファイルを設定すると、 **Seed**としてマークすることはできません。 
  
  - [**電子メールのタグ付け**] セクション。 処理された電子メールのどの部分を Seed としてマークするか、事前にタグ付けするかを設定します。 
    
6. 開始するには、[**処理**] をクリックします。 完了すると、プロセスの結果が表示されます。
    
7. オプション特定の保管担当者にデータソースを割り当てる必要がある場合は、**保管担当者**で保管担当者名を追加および編集し、 \> **保管担当者**assign で保管担当者を**管理**して割り当てることができ \> **Assign**ます。 
    
ケースにを追加した場合は、もう一度処理することができます。
  
## <a name="related-topics"></a>関連トピック

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[プロセスモジュールの結果を表示する](view-process-module-results-in-advanced-ediscovery.md)

