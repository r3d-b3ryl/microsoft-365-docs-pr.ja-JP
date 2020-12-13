---
title: Advanced eDiscovery でバッチ履歴を表示し、過去の結果をエクスポートする
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
ms.assetid: 35d52b41-75ab-4144-9edf-31e11453bd5d
description: 選択したエクスポート バッチ セッションの詳細情報を表示する方法と、Advanced eDiscovery で最後のエクスポート セッションを元に戻す方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 054fa4a88d8c61751b4064b3535de66881655631
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663276"
---
# <a name="view-batch-history-and-export-past-results-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) でバッチ履歴を表示し、過去の結果をエクスポートする

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
次のセクションでは、Advanced eDiscovery でデータをバッチ表示およびエクスポートするための追加オプションについて説明します。 
  
## <a name="viewing-export-batch-history-and-exporting-previous-batches"></a>エクスポート バッチ履歴の表示と以前のバッチのエクスポート

[エクスポート履歴] ダイアログには、選択したエクスポート バッチ セッションの詳細情報が表示され、最後のセッションを元に戻す機能も提供されます。
  
1. [ **エクスポート \> セットアップ]** で、[エクスポート バッチ] ドロップダウン リストから **バッチ名** を選択します。 
    
2. エクスポート バッチ名の右側にある [バッチ履歴] **アイコンを選択** します。 
    
    ![[バッチ履歴のエクスポート] アイコン](../media/a14f6ef9-0c3c-4851-b65d-9380f2d8a38a.gif)
  
    [バッチ履歴] ダイアログが表示されます。
    
    ![バッチ履歴のエクスポート](../media/04c5b75c-348c-491d-b4fe-716659333890.png)
  
3. 前のセッションをロールバックする必要がある場合は、[最後のセッションを元に戻す] **をクリックします**。 ロールバックは複数回実行できます。この場合、最後のセッションが取り消されます。
    
4. 以前に実行したエクスポート バッチ セッションからいつでもデータをダウンロードする場合は、エクスポートするエクスポートバッチの横にある [ダウンロード] アイコン [エクスポート バッチ履歴のダウンロード] アイコンをクリックします ![ ](../media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif) 。 
    
5. When the **Shared access signature dialog** is displayed, click Copy to clipboard to **copy** the export session data to the local machine, and then click **Close**. セキュリティ コンプライアンス &amp; センターの **電子情報開示エクスポート ツール** ダイアログが表示されます。 
    
    ![[電子情報開示のエクスポート] ダイアログボックス](../media/01f79d2d-6da0-45e6-9c6f-ab12347572cb.gif)
  
6. 電子情報開示 **エクスポート ツール ダイアログで、次の操作を** 行います。 
    
1. ソース **への接続に** 使用する共有アクセス署名を貼り付け、以前にクリップボードにコピーした共有アクセス署名の値を貼り付けます。 
    
2. [ **参照]** をクリックして、ダウンロードしたエクスポート ファイルをローカル コンピューターに保存する場所を選択します。 
    
3. **[開始]** をクリックします。 エクスポート ファイルがローカル コンピューターにダウンロードされます。 
    
## <a name="related-topics"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[結果のエクスポート ](export-results-in-advanced-ediscovery.md)

[レポート フィールドのエクスポート](export-report-fields-in-advanced-ediscovery.md)

