---
title: Advanced eDiscovery で分析の詳細設定を設定する
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: Advanced eDiscovery の分析プロセスで、近重複、電子メール スレッド、テーマなどの高度な設定を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac1300eb26338691722d9ccd15269ccf7f964f58
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663492"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a>Advanced eDiscovery で分析の詳細設定を設定する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
Advanced eDiscovery は、分析モジュール設定の既定の高度なパラメーターを提供します。 以下の手順では、指定できる設定について説明します。
  
1. [セットアップ **の \> 分析 \> の** 準備] タブで、[詳細設定] **(ページ** の下部) をクリックします。 次のパネルが表示されます。 
    
    ![分析設定の拡張設定](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. [ **近重複] および [電子メール** スレッド] パラメーターで、必要に応じて次の値を選択します。
    
  - **最小単語数**: 単語の最小数。その下のファイルは、ほぼ重複分析のために送信されません。 
    
  - **単語の最大数**: ほぼ重複分析のためにファイルが送信されない単語の最大数。
    
  - **メールの類似** 性 : 2 つのメールが類似と見なされる最小限のレベルの再送信。 値は常にドキュメントの類似性と等しいか、ドキュメントの類似性よりも大きくなります。 既定値は 90% です。
    
3. **Themes パラメーターで、[** テーマ分析に数値を含める] チェック ボックスをオンにして、分析中のテーマの処理に数値を含める。 
    
4. **[保存]** をクリックします。 
    
## <a name="related-topics"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ドキュメントの類似性について](understand-document-similarity-in-advanced-ediscovery.md)
  
[分析オプションの設定](set-analyze-options-in-advanced-ediscovery.md)
  
[テキストを無視する設定](set-ignore-text-in-advanced-ediscovery.md)
  
[分析結果の表示](view-analyze-results-in-advanced-ediscovery.md)

