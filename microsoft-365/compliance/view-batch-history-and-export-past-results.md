---
title: 詳細な電子情報開示でバッチ履歴を表示し過去の結果をエクスポートする
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
ms.assetid: 35d52b41-75ab-4144-9edf-31e11453bd5d
description: 選択したエクスポートバッチセッションの詳細情報を表示する方法と、Advanced 電子情報開示の最後のエクスポートセッションを取り消す方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b142c5d582b9a7bb84dd518325369e4b1adccf69
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936190"
---
# <a name="view-batch-history-and-export-past-results-in-advanced-ediscovery-classic"></a>詳細な電子情報開示でのバッチ履歴の表示と過去の結果のエクスポート (クラシック)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
次のセクションでは、高度な電子情報開示でのデータの一括表示およびエクスポートの追加オプションについて説明します。 
  
## <a name="viewing-export-batch-history-and-exporting-previous-batches"></a>バッチのエクスポート履歴を表示し、以前のバッチをエクスポートする

[エクスポート履歴] ダイアログは、選択したエクスポートバッチセッションの詳細情報を提供します。また、最後のセッションを取り消すこともできます。
  
1. [**エクスポートの \> 設定**] で、[バッチの**エクスポート**] ドロップダウンリストからバッチ名を選択します。 
    
2. [バッチ名のエクスポート] の右にある [**バッチ履歴**] アイコンを選択します。 
    
    ![[バッチ履歴のエクスポート] アイコン](../media/a14f6ef9-0c3c-4851-b65d-9380f2d8a38a.gif)
  
    [バッチ履歴] ダイアログが表示されます。
    
    ![バッチ履歴のエクスポート](../media/04c5b75c-348c-491d-b4fe-716659333890.png)
  
3. 前のセッションをロールバックする必要がある場合は、[**前回のセッションを元に戻す**] をクリックします。 Rollback を複数回実行して、最後のセッションを取り消すことができます。
    
4. 以前に実行したエクスポートバッチセッションからいつでもデータをダウンロードする場合は、 **Download**エクスポートする ![ 必要のある ](../media/de69b920-a6ac-4ddb-b93e-e1cc5888e6c4.gif) エクスポートバッチの横にある [ダウンロード] アイコンエクスポートバッチ履歴のダウンロードアイコンをクリックします。 
    
5. [**共有アクセス署名**] ダイアログボックスが表示されたら、[**クリップボードにコピー** ] をクリックして、エクスポートセッションデータをローカルコンピューターにコピーし、[**閉じる**] をクリックします。 [セキュリティ &amp; コンプライアンスセンターの**電子情報開示エクスポートツール**] ダイアログが表示されます。 
    
    ![[電子情報開示のエクスポート] ダイアログボックス](../media/01f79d2d-6da0-45e6-9c6f-ab12347572cb.gif)
  
6. [**電子情報開示エクスポートツール**] ダイアログボックスで、次のようになります。 
    
1. [**貼り付け元への接続に使用される共有アクセス署名**] に、以前にクリップボードにコピーした**共有アクセス署名**の値を貼り付けます。 
    
2. [**参照**] をクリックして、ダウンロードしたエクスポートファイルをローカルコンピューターに保存するためのターゲットの場所を選択します。 
    
3. **[開始]** をクリックします。 エクスポートファイルがローカルコンピューターにダウンロードされます。 
    
## <a name="related-topics"></a>関連トピック

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[結果のエクスポート](export-results-in-advanced-ediscovery.md)

[レポート フィールドのエクスポート](export-report-fields-in-advanced-ediscovery.md)

