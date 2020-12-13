---
title: Advanced eDiscovery で分析オプションを設定する
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: Advanced eDiscovery の分析プロセス (ほぼ重複、電子メール スレッド、テーマなど) のオプションを設定する手順を確認します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663502"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) で分析オプションを設定する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
Advanced eDiscovery で、分析を実行する前に分析オプションを設定します。
  
## <a name="set-analyze-options"></a>分析オプションを設定する

Open **Prepare \> Analyze** \> **Setup**. 次のウィンドウが表示されます。
  
![[分析設定] のオプション](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **ほぼ重複しているスレッドと電子メール スレッド** 分析を実行する場合は、このチェック ボックスをオンにします。 既定では選択されています。 
  
 **ドキュメントの類似性** [近重複] しきい値を入力するか、既定値の 65% を受け入れる。 
  
 **テーマ** すべてのファイルを処理し、テーマを割り当てるには、このチェック ボックスをオンにします。 既定では、このチェック ボックスはオンではありません。 テーマ処理を実行する場合は、次のオプションを入力します。
  
- **テーマの最大数** 作成するテーマの数の値を入力または選択します。 既定値は 200 です。 
    
    > [!NOTE]
    > テーマの数を増やすと、パフォーマンスに影響を与えるだけでなく、テーマを一般化する機能にも影響します。 テーマの数が多いほど、細かく設定できます。 たとえば、一連の 50 のテーマに 「バスケス、ボールズ、クリッパー、レイカー」などのテーマが含まれる場合です。300 のテーマには、"1 つのテーマ"、"Clippers"、"Lakers" が含まれる場合があります。 ECA に対してこの機能を使用する場合は、"バスケト" というテーマを認識する必要がない場合に役立つ可能性があります。 ただし、処理のテーマが多すぎる場合は、"バスケ" という単語が表示されない可能性があります。また、ブートしてヘアに使用されるアイテムではなく、スクリッパーとクリッパーがレビューに優れたバスケト テーマであるというのを知らない場合があります。 
  
- **推奨されるテーマ** テーマの処理を制御するテーマの単語を提案できます。 Advanced eDiscovery は、これらの推奨される単語に焦点を当て、"テーマの最大数" 設定に基づいて、1 つ以上の関連するテーマを作成します。 
    
    たとえば、候補の単語が "computer" で、"2" を "最大テーマ数" として指定した場合、Advanced eDiscovery は単語 "computer" に関連する 2 つのテーマの生成を試みる。 たとえば、"コンピューター ソフトウェア" と "コンピューター ハードウェア" という 2 つのテーマがあります。 
    
    ![提示されたテーマの追加](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 推奨されるテーマを表示、追加、または編集するには、[変更] を **クリックします**。
    
2. [推奨 **されるテーマ] パネル** で、[追加] アイコン アイコンをクリックして ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) テーマを追加します。 [推奨 **されるテーマの追加] パネル** で、単語をコンマで区切って追加します。 
    
3. [ **テーマの数**] で値を選択して、Advanced eDiscovery がこれらの単語に対して生成しようとするテーマの数を決定します (既定値は 1 テーマです)。
    
4. [ **保存] を** クリックし、ダイアログを閉じます。 
    
    > [!NOTE]
    > テーマの総数には、推奨されるテーマが含まれます。 推奨されるテーマの合計がテーマの合計を超えすることはできません。 テーマ全体に対して推奨テーマが多数ある場合、そのテーマのほとんどが推奨テーマ専用なので、システムによって検出される "新しい" テーマはわずかです。 
  
- **モード** ドロップダウン リストからテーマ オプションを **選択** します。 
    
  - **モデルの作成と適用**: ファイルのセグメントからモデル別にテーマを計算し、その間でファイルを配布します。
    
  - **モデルの** 作成 : ファイルのセグメントからテーマ モデルを計算します。 ファイルを分割する適用プロセスは、別の時点で個別に実行されます。
    
  - **モデルの** 適用 : このオプションは、モデルが以前に作成され、まだ適用されていない場合にのみ表示されます。 これにより、テーマに基づいてファイルが分割されます。
    
テキストの無視 [を設定し、分析](set-ignore-text-in-advanced-ediscovery.md) の [詳細設定を分析に](set-analyze-advanced-settings-in-advanced-ediscovery.md) 設定することもできます。 
  
これらのオプションを設定した後、[分析] をクリック **して** 実行します。 [分析結果の表示が](view-analyze-results-in-advanced-ediscovery.md) 表示されます。 
  
## <a name="related-topics"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ドキュメントの類似性について](understand-document-similarity-in-advanced-ediscovery.md)
  
[[テキストを無視する] を設定する ](set-ignore-text-in-advanced-ediscovery.md)
  
[分析設定の拡張設定](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[結果の分析を表示する](view-analyze-results-in-advanced-ediscovery.md)

