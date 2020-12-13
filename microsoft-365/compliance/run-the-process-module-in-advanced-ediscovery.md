---
title: Advanced eDiscovery でプロセス モジュールを実行する
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: Advanced eDiscovery を使用して分析するデータのケース ファイルを準備するためのガイドラインについて説明します。
ms.openlocfilehash: 3773833d9d0af993b4ccb35bcd18276800c4081f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662812"
---
# <a name="run-the-process-module-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) でプロセス モジュールを実行する

ケース ファイルは、準備プロセス中に Advanced eDiscovery **に読み込** \> **まれます**。 
  
> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>ガイドライン: Advanced eDiscovery 用のデータの準備

- **品質**: ケースに関連するケース ファイルの母集団を明確に識別します。
    
- **読** み込み: Advanced eDiscovery にアクセスできる場所にファイルを読み込む。
    
- **ファイル ID**: Advanced eDiscovery の一意のファイル識別子。 インポートされたファイル識別子がない場合、Advanced eDiscovery は自動的に ID を生成します。 後続のプロセス読み込みで ID をマップし、最初のプロセスの読み込みとは異なるパスをマップする場合、Advanced eDiscovery はパスを置き換える (新しいファイル エントリを追加する代わりに)。 この ID は、エクスポート プロセスの参照として使用できます。 ID 値を "-1" に設定する必要があります。
    
- **MD5**: この署名は、ファイルを区別するために使用されます (同じ MD5 を持たない限り、2 つのファイルは完全に重複すると見なされません)。 既定では、Advanced eDiscovery はファイルの MD5 を計算します。 読み込まれたファイルがテキスト ファイルの場合は、Advanced eDiscovery で計算するのではなく、元の MD5 値を読み込み、マップしてください。
    
- **ファイルの種類と名前**:
    
  - Advanced eDiscovery では、さまざまな形式のファイルを処理し、読み込まれたネイティブ ファイルを標準形式 (次のように) に抽出できます \* 。TXT、HTML、または .XML。 テキスト ファイルの処理は、ネイティブ ファイルよりも高速です。 抽出されたテキスト ファイルは、ケース フォルダーに格納されます。
    
  - 抽出できないファイル (システム ファイルやグラフィック イメージなど) は読み込めない。 これらのファイルは処理を遅らせる可能性があります。
    
  - ファイル名が大幅に名前が付けられているか、パスが正しいか確認します。
    
- **ファイル パス**: Advanced eDiscovery は、パスの長さが最大 400 文字のファイルを読み込めます。
    
- **テキスト** 抽出 : ネイティブ ファイルからテキストを抽出する場合、通常のテキストに加えて、隠しテキスト (Excel および .doc)、非表示列 (Excel)、変更の追跡 (.doc)、スピーカー ノート (.ppt)、埋め込みオブジェクト (.ppt 内の Excel オブジェクトなど) も抽出されます。 これらはテキスト エディターで表示できます。
    
- **テキストを無視**: このオプション機能は、プロセスの実行後および分析前に定義されます。 使用するとファイル分析のパフォーマンスが低下する可能性があります。テキストを無視する場合は注意が必要です。
    
- **多言語テキスト**: Advanced eDiscovery は現在、タグ、カストディアン、および問題の多言語名を処理していない。
    
- **メタデータ**: 将来の参照のためにケース データベースに保存するメタデータ (日付範囲、ファイル サイズ、ファイルの種類、保管担当者、件名など) が含まれるかどうかを決定します。 メタデータは、インベントリを再実行したり、再処理のオーバーヘッドを追加したりすることなく、ファイルが既に読み込まれた後に読み込む可能性があります。 
    
  - ファイルが最初にパスによって読み込まれた場合は、後でメタデータをインポートするときにパス列をマップします。 ファイルを ID で参照し、別のパスをマップすることができます。 これは、ファイル パスが変更される場合に便利なシナリオです。
    
  - ファイルが最初にファイル ID によって読み込まれた場合は、メタデータの読み込み時に ID 列をマップします。 (ID ではなく) パスでファイルを参照すると、ファイルは別の ID で再読み込みされます。 Advanced eDiscovery は、既存のファイルのメタデータを読み込むファイルのコピーを作成します。
    
- **家族**: 親 (家族の親) なしではファミリを読み込めずに済む。 
    
- **ファイル サイズ**: Advanced eDiscovery に読み込まれるファイルのサイズに制限はありません。 分析 (分析、関連性など) の場合、抽出されたテキストの文字数は 5,242,880 文字に制限されます。 大きなファイルは無視されます (たとえば、関連度では、ファイルは関連性トレーニング プロセスに参加し、バッチ計算後に関連性スコアを受け取ります)。
    
- **ファイル数**: 1 つのケースで処理できるファイルの数に対して推奨される制限はありません。 パフォーマンスはシステムのリソースによって異なります。 
    
## <a name="filtering-files"></a>ファイルのフィルター処理

ユーザー定義ラベルを一連のファイルに関連付け、プロセスや他のタスクから除外できます。 各プロセス セッションは、バッチ ID に関連付けられている。 バッチ ID は、関連性の専門家には表示されませんが、現在のバッチのフィルターを追加し、適切なすべてのファイルにユーザー定義ラベルをタグ付けすることで、検索ユーティリティを使用して行うことができます。 
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[プロセス モジュールの実行とデータの読み込み](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[プロセス モジュールの結果の表示](view-process-module-results-in-advanced-ediscovery.md)

