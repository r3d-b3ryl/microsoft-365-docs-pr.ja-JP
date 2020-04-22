---
title: 高度な電子情報開示
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 高度な電子情報開示を使用してデータを分析し、ドキュメントレビューを合理化し、効率的な電子情報開示に関する決定を行う方法について説明します。
ms.openlocfilehash: 554b8cfc5209ce0764e712c3aff4338347bc2881
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631838"
---
# <a name="advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック)

> [!IMPORTANT]
> 高度な電子情報開示の新バージョンへの投資を継続するうちに、microsoft は advanced ediscovery *(classic)* または*advanced ediscovery v 1.0*とも呼ばれる、高度な電子情報開示の廃止をアナウンスしています。 まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。 Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。 Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。 
  
高度な電子情報開示を使用すると、データの理解を深め、電子情報開示コストを削減できます。 高度な電子情報開示を使用すると、非構造化データの分析、ドキュメントレビューの効率化、電子情報開示のためのデータの削減に関する決定を行うことができます。 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 365 グループ、および Microsoft Teams に格納されているデータを操作できます。 セキュリティ/コンプライアンスセンターで電子情報開示検索を実行して、グループ、個々のメールボックス、サイト内のコンテンツを検索し、高度な電子情報開示を使用して検索結果を分析することができます。 高度な電子情報開示で分析のために検索結果を準備する場合、光学式文字認識で画像からテキストを抽出することができます。 この機能により、高度な電子情報開示の強力なテキスト分析機能を画像ファイルに適用することができます。
  
高度な電子情報開示では、同一の重複を検出し、電子メールスレッド分析などの機能を使用して、重複する情報を特定することで、ドキュメントのレビュープロセスを効率化し、スピードアップします 関連性機能は、予測コーディングテクノロジを適用して、関連するドキュメントを特定します。 高度な電子情報開示は、サンプルドキュメントでのタグ付けの決定から学んで、統計情報と自己学習技術を適用して、データセット内の各ドキュメントの関連性を計算します。 これにより、主要なドキュメントに集中して、必要な場合について迅速に判断し、データをカリングし、レビューの優先順位付けを行うことができます。
  
 **高度な電子情報開示が理由** 高度な電子情報開示は、Office 365 の既存の電子情報開示機能のセットに基づいて構築されます。 たとえば、セキュリティ&amp;コンプライアンスセンターの検索機能を使用して、組織内のすべてのコンテンツソースの最初の検索を実行し、特定の訴訟に関連する可能性があるデータを識別して収集できます。 その後、高度な電子情報開示のためのテキスト分析、マシン学習、および関連性/予測のコーディング機能を適用することによって、そのデータに対する分析を実行できます。 これにより、組織は、多数の電子メールメッセージ、ドキュメント、およびその他の種類のデータをすばやく処理して、特定のアイテムに関連している可能性の高いものを見つけることができます。 
 
> [!NOTE]
> 高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。 その計画がなく、高度な電子情報開示を試行する必要がある場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 当て. その後、削減されたデータセットは、さらなるレビューのために Office 365 からエクスポートすることができます。 
  
## <a name="get-started"></a>概要

高度な電子情報開示を開始する最も簡単な方法は、ケースを作成して、セキュリティ & コンプライアンスセンターで検索結果を準備し、それらの結果を高度な電子情報開示にロードして、そのケースデータを分析してから、外部レビューの結果をエクスポートするためのエクスプレス分析を実行することです。
  
- 高度な電子情報開示ワークフローの[簡単な概要を取得する](quick-setup-for-advanced-ediscovery.md) 
    
- セキュリティ & コンプライアンスセンターを使用して、ケースの作成、電子情報開示のアクセス許可の割り当て、ケースメンバーの追加を行うことで、高度な電子情報開示の[ユーザーおよびケースをセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)する 
    
- 高度な電子情報開示のケースへの[検索データの準備と読み込み](prepare-data-for-advanced-ediscovery.md) 
    
- [Office 以外の365データ](import-non-office-365-data-into-advanced-ediscovery.md)をケースに読み込み、高度な電子情報開示で分析する 
    
- [エクスプレス分析を使用](use-express-analysis-in-advanced-ediscovery.md)してデータをケースにすばやく分析し、結果を簡単にエクスポートする 
    
## <a name="analyze-data"></a>データを分析する

高度な電子情報開示のケースに検索データが読み込まれたら、Analyze モジュールを使用して分析を開始します。 分析プロセスの最初の部分では、ファイルを一意のファイルのグループに分類し、重複して、重複しないようにします (ドキュメントの類似性とも呼ばれます)。 その後、データを再編成して、階層構造の電子メールのスレッドとテーマをグループ化し、オプションで、特定のテキストを分析から除外するように無視するテキストフィルターを設定します。 次に、分析を実行し、結果を表示します。
  
- 詳細な電子情報開示でのデータの分析を準備するための[ドキュメントの類似](understand-document-similarity-in-advanced-ediscovery.md)点について 
    
- ほぼ重複、テーマ、および電子メールのスレッド処理の[オプションを設定](set-analyze-options-in-advanced-ediscovery.md)してから、Analyze モジュールを実行します。 
    
- テキストおよびテキスト文字列を分析対象から除外するように、[無視するテキストフィルターを設定](set-ignore-text-in-advanced-ediscovery.md)します。このフィルターでは、関連性分析を実行するときにもテキストは無視されます。 
    
- 分析プロセスの[結果を表示する](view-analyze-results-in-advanced-ediscovery.md) 
    
- 分析プロセスの[詳細設定を構成する](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
## <a name="set-up-relevance-training"></a>関連トレーニングの設定

上級電子情報開示の予測コーディング (関連性と呼ばれる) を使用すると、ドキュメントの小さなセットに対して意思決定 (関連性があるかどうかに関する決定) を行うことができます。
  
- 関連性トレーニングのセットアップ、ケースに関連するタグ付けファイル、ケース問題の定義[について説明](manage-relevance-setup-in-advanced-ediscovery.md)します。 
    
- [ケースの問題を定義](define-issues-and-assign-users.md)し、各問題をファイルをトレーニングするユーザーに割り当てる 
    
- インポートされたファイルを、関連トレーニングに追加する[現在のまたは新しい負荷に追加](set-up-loads-to-add-imported-files.md)します。 ロードは、ケースに追加され、関連トレーニングに使用されるファイルの新しいバッチです。 
    
- 関連性トレーニングに追加できる[強調表示](define-highlighted-keywords-and-advanced-options.md)されたキーワードを定義します。 これにより、ケースに関連するファイルを特定しやすくなります。 
    
## <a name="run-the-relevance-module"></a>関連性モジュールを実行する

トレーニングを設定すると、関連性モジュールを実行し、トレーニング設定の有効性を評価できます。 これにより、追加のトレーニングを実行する必要があるかどうかを判断したり、ケースに関連してファイルのタグ付けを開始する準備が整っているかどうかを判断したりするのに役立つ関連性ランキングが得られます。
  
- サンプルのファイルセットに基づいた評価、タグ付け、追跡、再トレーニングの関連性プロセスと反復プロセス[について説明](use-relevance-in-advanced-ediscovery.md)します。 
    
- ケースに精通したエキスパートがケースファイルのセットをレビューし、関連性トレーニングの効果を判断する[評価について説明](assessment-in-relevance-in-advanced-ediscovery.md)します。 
    
- [ケースファイルを評価](tagging-and-assessment-in-advanced-ediscovery.md)して、トレーニング設定の有効性 (* 多様性) を計算し、ケースに関連するファイルまたは関連しないファイルにタグ付けします。 これにより、現在のトレーニングが十分かどうか、またはトレーニングの設定を調整する必要があるかどうかを判断できます。 
    
- 評価が完了した後に[関連性トレーニングを実行](tagging-and-relevance-training-in-advanced-ediscovery.md)し、そのケースに対して定義した問題に関連するファイルまたは関連していないファイルに再度タグ付けする 
    
- 関連性[の分析プロセスを追跡して、](track-relevance-analysis-in-advanced-ediscovery.md)関連性トレーニングが評価目標を達成したか (* stable トレーニング状態)、またはさらにトレーニングが必要かどうかを判断します。各ケースの問題に関する関連性の結果を表示することもできます。 
    
- レビュー用にエクスポートできるケースファイルの結果セットのサイズを決定するために、[関連性分析に基づいて決定を行い](decision-based-on-the-results-in-advanced-ediscovery.md)ます。 
    
- 関連性[分析の品質をテスト](test-relevance-analysis-in-advanced-ediscovery.md)して、関連性プロセス中に行われたカリングの決定を検証する 
    
## <a name="export-results"></a>結果のエクスポート

Advanced eDiscovery でケースデータを分析する最後の手順は、外部レビューの分析結果をエクスポートすることです。
  
- [ケースデータのエクスポートについて](export-case-data-in-advanced-ediscovery.md)
    
- [ケース データをエクスポートする](export-results-in-advanced-ediscovery.md)
    
- [バッチ履歴を表示し、過去の結果をエクスポートする](view-batch-history-and-export-past-results.md)
    
- [レポート フィールドのエクスポート](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a>その他の高度な電子情報開示ツール

Advanced eDiscovery は、ケースデータの分析、関連性分析、データのエクスポート以外に、追加のツールと機能を提供します。
  
- [高度な電子情報開示レポートを実行する](run-reports-in-advanced-ediscovery.md)
    
- [ケースとテナントの設定を定義する](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高度な電子情報開示ユーティリティ](use-advanced-ediscovery-utilities.md)
