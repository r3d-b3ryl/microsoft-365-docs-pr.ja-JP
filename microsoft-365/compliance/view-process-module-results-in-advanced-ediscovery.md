---
title: アドバンスド電子情報開示でのプロセスモジュールの結果の表示
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: タスクの状態とプロセスの概要を含む、アドバンスト eDiscovery でのプロセスモジュールの実行結果を確認する方法について説明します。
ms.openlocfilehash: 26ef87c762fc5c77f2374978bf4a425940dd5f37
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936170"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a>アドバンスド電子情報開示でのプロセスモジュールの結果の表示 (クラシック)

**準備** \> **プロセス**が開始されると、進行状況と結果を表示できるようになります。 
  
> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>タスクの進捗状況を処理する

[処理の**準備** \> **Process** \> ] で、次の例に示すよう**に、** ページに現在の状態 (プロセスが実行中の場合) または最後のプロセスの状態タスクの状態が表示されます。
  
![プロセス モジュールのタスクの進捗状況](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
表示されるタスクは、選択された [処理] オプションによって異なる場合があります。 
  
- **インベントリ**: Advanced eDiscovery は、プロセスに対して選択されたすべてのファイルを反復処理し、基本的なデータ収集を実行します。
    
- **署名の計算**: MD5 デジタル署名を計算します。
    
- **複合語抽出**: 内部または含まれているファイルを複合ファイル (PST、ZIP、MSG など) から抽出します。 抽出したファイルは、ケースの case フォルダーに格納されます。
    
- **データベースの同期**: 内部データベースプロセス。
    
- **ファイルコピー**: プロセスファイルをコピーします。 [ファイルの詳細コピー] オプションが選択されている場合でも、このタスクは常に表示されます。
    
- **テキストの抽出**: ネイティブファイルがある場合、Advanced EDiscovery は dtsearch を使用してこれらのファイルからテキストを抽出します。 これらのファイルの抽出テキストは、テキストファイルとして case フォルダーに格納されます。
    
- **メタデータの更新**: 読み込まれたメタデータを処理します。 
    
- **最終**処理: 読み込まれたケースファイルのデータを終了する内部処理 (たとえば、エラーおよび成功ファイルを識別する)。 
    
タスクの進捗状況: タスクの完了後に表示されます。 タスクの実行中は、実行期間が表示されます。
  
> [!NOTE]
> 完了したタスクには、処理を完了したファイルやエラーが発生したファイルの合計も含まれることがあります。 
  
> [!TIP]
> [キャンセル] は、プロセスの実行を停止し、前のデータ作成または保存した処理済みデータにロールバックするためのロールバックオプションを提供します。 Rollback は、処理されたすべてのデータを削除します。 処理されたデータが失われることがないようにする場合 (たとえば、これらのファイルの再読み込みを計画している場合) は、このウィンドウで [キャンセル] オプションを選択して、ロールバックしないことを選択します。 
  
## <a name="process-summary"></a>プロセスの概要

[ \> プロセス \> 結果の処理 \> の概要] で、読み込まれたファイルの結果の内訳が、正常なファイル処理とエラー結果に従って表示されます。
  
ペインは、次のように、インポートされたファイル統計をグラフィカルに表示します。
  
- **プロセスの概要**d: すべてのファイル (ケース内) を蓄積します。
    
- **プロセス概要 last**: 最後のセッションまたはアクションから読み込まれたファイル。 
    
- **姓**: 大文字と小文字のファミリ情報 (存在する場合)。
    
- **Seed**ファイルが追加された場合、ファイルに対して定義された問題ごとにシードファイルの数が表示されます。 
    
    **シード**ファイルのマーキングが失敗した場合は、それも記録されます。 
    
- **プリタグ付き**ファイルが追加された場合は、ファイルに対して定義された問題ごとに、タグ付きファイルの数が表示されます。 
    
    **タグ付け**されたファイルのマーキングが失敗した場合は、それも記録されます。 
    
![プロセス モジュールの概要](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>プロセス概要累計および最終グラフ

左側のバーには、ソースと抽出ファイルが含まれています。すべてのファイルが見つかります。 
  
次のものが含まれている右のバー。
  
- 読み込みエラーが発生したファイル
    
- 正常に読み込まれたファイル: 次のものが含まれます。 
    
  - **既存**: 以前に読み込まれ、後で読み込まれたファイル (重複を含む)。
    
  - **テキスト**: テキストを含む一意のファイル。
    
  - **テキスト以外**: 空のテキストファイル、空のネイティブテキストファイル、ネイティブの非テキストファイル。 
    
  - **複製**s: ファイルがテキストと重複しています。
    
## <a name="last-process-errors"></a>最後の処理エラー

[ \> 処理 \> 結果の \> 最終処理] エラーでは、最後に実行されたセッションまたはアクションのエラーの詳細が表示されます。
  
![プロセス モジュールのエラー](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[プロセスモジュールの実行とデータの読み込み](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

