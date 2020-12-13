---
title: Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: fd53438a-a760-45f6-9df4-861b50161ae4
description: Advanced eDiscovery が、データの分析、ドキュメント レビューの合理化、効率的な電子情報開示のための決定を行う上でどのように役立つのかについて説明します。
ms.openlocfilehash: f8ada5d377e72516ea42d8c5dc5680573daec717
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662822"
---
# <a name="advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック)

> [!IMPORTANT]
> **Advanced eDiscovery (クラシック) は、2020 年 12 月 31 日に完全に廃止されます。**<br/>
> 新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (クラシック) からのケースとケース データの完全な削除と削除を発表します。
> Advanced eDiscovery (クラシック) *(Advanced eDiscovery v1.0* とも呼ばれる) をまだ使用している場合は、使用を [Advanced eDiscovery v2.0](overview-ediscovery-20.md) *(Microsoft 365* の Advanced eDiscovery ソリューションとも呼ばれる) にできるだけ早く移行してください。  すべてのケースとケース データを削除する準備として、ケースからデータをエクスポートすることで、ケース [データをアーカイブできます](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide)。
> Advanced eDiscovery v2.0 には、Advanced eDiscovery v1.0 と同様の機能が含まれるだけでなく、保管担当者の管理、通信管理、レビュー セットなどの多くの新機能も提供されます。 Advanced eDiscovery v1.0 の以前の廃止フェーズの詳細については、「従来の電子情報開示ツールの廃止」 [を参照してください](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)。

Advanced eDiscovery を使用すると、データをよりよく理解し、電子情報開示のコストを削減できます。 Advanced eDiscovery は、非構造化データの分析、より効率的なドキュメント レビューの実行、および電子情報開示のデータ削減に関する決定を行うのに役立ちます。 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 365 グループ、および Microsoft Teams に保存されているデータを使用できます。 セキュリティ/コンプライアンス センターで電子情報開示検索を実行して、グループ、個々のメールボックス、サイト内のコンテンツを検索し、Advanced eDiscovery を使用して検索結果を分析できます。 Advanced eDiscovery で分析用に検索結果を準備すると、光学式文字認識によって画像からテキストを抽出できます。 この機能を使用すると、Advanced eDiscovery の強力なテキスト分析機能を画像ファイルに適用できます。
  
Advanced eDiscovery は、近重複データ検出や電子メール スレッド分析のような機能を使用して冗長な情報を識別することで、ドキュメントレビュー プロセスを合理化し、高速化します。 関連性機能は、関連するドキュメントを識別するための予測コーディング テクノロジを適用します。 Advanced eDiscovery は、サンプル ドキュメントに関するタグ付けの決定から学習し、データ セット内の各ドキュメントの関連性を計算するために統計および自己学習の手法を適用します。 これにより、主要なドキュメントに焦点を当てたり、ケース戦略に関する迅速かつ情報に基づいた意思決定を行い、データをカカル処理し、レビューに優先順位を付けすることができます。
  
 **Advanced eDiscovery を使用する理由** Advanced eDiscovery は、Office 365 の既存の一連の電子情報開示機能に基Officeされています。 たとえば、セキュリティ コンプライアンス センターの検索機能を使用して、組織内のすべてのコンテンツ ソースの初期検索を実行し、特定の法的事例に関連する可能性のあるデータを特定して収集できます。 &amp; その後、Advanced eDiscovery のテキスト分析、機械学習、および関連性/予測コーディング機能を適用することで、そのデータに関する分析を実行できます。 これにより、組織は何千もの電子メール メッセージ、ドキュメント、その他の種類のデータを迅速に処理し、特定のアイテムに最も関連する可能性が高いアイテムを見つけるのに役立ちます。 
 
> [!NOTE]
> Advanced eDiscovery には、Advanced Compliance Office付き 365 E3 または組織の E5 サブスクリプションが必要です。 If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 大文字と小文字を区別します。 その後、縮小されたデータ セットを 365 からエクスポートOffice、詳細を確認できます。 
  
## <a name="get-started"></a>概要

Advanced eDiscovery を使い始める最も簡単な方法は、ケースを作成し、セキュリティ & コンプライアンス センターで検索結果を準備し、それらの結果を Advanced eDiscovery に読み込み、高速分析を実行してケース データを分析し、外部レビューの結果をエクスポートすることです。
  
- Advanced eDiscovery[ワークフローの](quick-setup-for-advanced-ediscovery.md)概要を簡単に説明する 
    
- [ケースの作成](set-up-users-and-cases-in-advanced-ediscovery.md) 、電子情報開示のアクセス許可の割り当て、ケース メンバーの追加を行って、Advanced eDiscovery のユーザーとケースをセットアップします。すべては、セキュリティ/コンプライアンス センター&使用します。 
    
- Advanced eDiscovery[のケースに](prepare-data-for-advanced-ediscovery.md)検索データを準備して読み込む 
    
- Advanced eDiscovery[でOffice 365](import-non-office-365-data-into-advanced-ediscovery.md)以外のデータをケースに読み込む 
    
- [高速分析を使用](use-express-analysis-in-advanced-ediscovery.md) してケース内のデータをすばやく分析し、結果を簡単にエクスポートする 
    
## <a name="analyze-data"></a>データを分析する

Advanced eDiscovery のケースに検索データが読み込まれたら、分析モジュールを使用して分析を開始します。 分析プロセスの最初の部分は、ファイルを一意のファイル、重複、および類似度 (ドキュメントの類似性) のグループに整理します。 次に、データを再び電子メール スレッドとテーマの階層構造のグループに整理し、必要に応じて、テキスト フィルターを無視して分析から特定のテキストを除外するように設定します。 次に、分析を実行し、結果を表示します。
  
- Advanced eDiscovery[でデータ](understand-document-similarity-in-advanced-ediscovery.md)を分析するための準備をするためのドキュメントの類似性について説明します 
    
- [ほぼ重複、テーマ](set-analyze-options-in-advanced-ediscovery.md) 、および電子メールスレッドのオプションを設定し、分析モジュールを実行します。 
    
- [[テキストの無視] フィルターを設定](set-ignore-text-in-advanced-ediscovery.md) して、テキスト文字列とテキスト文字列を分析対象から除外します。これらのフィルターは、関連性分析の実行時にもテキストを無視します。 
    
- [分析プロセスの](view-analyze-results-in-advanced-ediscovery.md) 結果を表示する 
    
- [分析プロセスの詳細設定](set-analyze-advanced-settings-in-advanced-ediscovery.md) を構成する 
    
## <a name="set-up-relevance-training"></a>関連トレーニングの設定

Advanced eDiscovery の予測コーディング (関連性と呼ばれる) を使用すると、ドキュメントの小さなセットで (関連性のあるものかどうかに関して) 判断を下せ、探している情報に関するシステムをトレーニングできます。
  
- [関連トレーニングの設定、ケース](manage-relevance-setup-in-advanced-ediscovery.md) に関連するファイルのタグ付け、ケースの問題の定義について説明します。 
    
- [ケースの問題を定義し](define-issues-and-assign-users.md) 、ファイルをトレーニングするユーザーに各問題を割り当てる 
    
- [関連性トレーニングに追加される現在または](set-up-loads-to-add-imported-files.md) 新しい負荷にインポートしたファイルを追加します。 読み込みとは、ケースに追加され、関連性トレーニングに使用されるファイルの新しいバッチです。 
    
- [関連性トレーニングに追加](define-highlighted-keywords-and-advanced-options.md) できる強調表示されたキーワードを定義します。 これにより、ケースに関連するファイルをより適切に識別できます。 
    
## <a name="run-the-relevance-module"></a>関連性モジュールを実行する

トレーニングをセットアップした後、関連性モジュールを実行し、トレーニング設定の有効性を評価する準備が整いました。 これにより、追加のトレーニングを実行する必要がある場合や、ケースに関連するファイルのタグ付けを開始する準備ができているかを判断するのに役立つ関連性ランキングが作成されます。
  
- [ファイルのサンプル セットに基づく](use-relevance-in-advanced-ediscovery.md) 評価、タグ付け、追跡、再トレーニングの関連性プロセスと反復プロセスについて説明します。 
    
- [ケースに精通している](assessment-in-relevance-in-advanced-ediscovery.md) 専門家が一連のケース ファイルをレビューし、関連性トレーニングの有効性を判断する評価について説明します 
    
- [ケース ファイルを評価](tagging-and-assessment-in-advanced-ediscovery.md) してトレーニング設定の有効性 (*リッチと呼ばれる) を計算し、ファイルに関連するタグまたはケースに関連しないタグを付ける。 これにより、現在のトレーニングで十分かどうかを判断したり、トレーニング設定を調整する必要がある場合に役立ちます。 
    
- [評価の完了後に](tagging-and-relevance-training-in-advanced-ediscovery.md) 関連性トレーニングを実行し、もう一度ファイルに関連するタグを付けるか、ケースに対して定義した問題に関連しないかのタグを付ける 
    
- [関連性分析プロセスを](track-relevance-analysis-in-advanced-ediscovery.md) 追跡して、関連性トレーニングが評価目標 (*安定したトレーニング状態と呼ばれる) を達成したかどうか、またはより多くのトレーニングが必要かどうかを判断します。また、各ケースの問題の関連性の結果を表示できます。 
    
- [関連性分析に基づいて](decision-based-on-the-results-in-advanced-ediscovery.md) 決定を行い、レビューのためにエクスポートできるケース ファイルの結果セットのサイズを決定する 
    
- [関連性分析の品質をテストして](test-relevance-analysis-in-advanced-ediscovery.md) 、関連性プロセス中に行われたカリングの決定を検証する 
    
## <a name="export-results"></a>結果をエクスポートする

Advanced eDiscovery でケース データを分析する最後の手順は、外部レビュー用に分析の結果をエクスポートすることです。
  
- [ケース データのエクスポートについて](export-case-data-in-advanced-ediscovery.md)
    
- [ケース データをエクスポートする](export-results-in-advanced-ediscovery.md)
    
- [バッチ履歴を表示し、過去の結果をエクスポートする](view-batch-history-and-export-past-results.md)
    
- [レポート フィールドのエクスポート](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>その他の Advanced eDiscovery ツール

Advanced eDiscovery には、ケース データの分析、関連性分析、およびデータのエクスポート以外にも、追加のツールと機能が用意されています。
  
- [Advanced eDiscovery レポートを実行する](run-reports-in-advanced-ediscovery.md)
    
- [ケースとテナントの設定を定義する](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Advanced eDiscovery ユーティリティ](use-advanced-ediscovery-utilities.md)
