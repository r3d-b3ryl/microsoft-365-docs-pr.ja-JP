---
title: Advanced eDiscovery
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
ms.openlocfilehash: 231064266a2498ec2eb8845da325fba6e5cfeb76
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649714"
---
# <a name="advanced-ediscovery-classic"></a><span data-ttu-id="5db1c-103">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="5db1c-103">Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5db1c-104">**上級電子情報開示 (クラシック) は、2020年12月31日に完全に廃止されます。**</span><span class="sxs-lookup"><span data-stu-id="5db1c-104">**Advanced eDiscovery (classic) will be permanently retired on December 31, 2020.**</span></span><br/>
> <span data-ttu-id="5db1c-105">高度な電子情報開示の新しいバージョンへの投資を継続するうちに、microsoft は、高度な電子情報開示 (クラシック) からのケースとケースデータの完全な廃止および削除を発表しています。</span><span class="sxs-lookup"><span data-stu-id="5db1c-105">As we continue to invest in newer versions of Advanced eDiscovery, we're announcing the permanent retirement and removal of cases and case data from Advanced eDiscovery (classic).</span></span>
> <span data-ttu-id="5db1c-106">上級電子情報開示 (クラシック) ( *上級電子*情報開示とも呼ばれる) を引き続き使用している場合は、できるだけ早く、使用状況を [advanced](overview-ediscovery-20.md) ediscovery v2.0 ( *Microsoft 365 の高度な電子情報開示ソリューション*ともいいます) に移行してください。</span><span class="sxs-lookup"><span data-stu-id="5db1c-106">If you're still using Advanced eDiscovery (classic), also known as *Advanced eDiscovery v1.0*, please transition your usage to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span>  <span data-ttu-id="5db1c-107">すべてのケースとケースデータの削除の準備では、ケース [からデータをエクスポート](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide)することによってケースデータをアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-107">In preparation for the removal of all cases and case data, you can archive case data by [exporting data from a case](https://docs.microsoft.com/microsoft-365/compliance/export-results-in-advanced-ediscovery?view=o365-worldwide).</span></span>
> <span data-ttu-id="5db1c-108">上級電子情報開示 v2.0 では、Advanced eDiscovery v2.0 と同様の機能が含まれていますが、保管担当者管理、コミュニケーション管理、およびレビューセットなどの多くの新機能も提供しています。</span><span class="sxs-lookup"><span data-stu-id="5db1c-108">Advanced eDiscovery v2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="5db1c-109">Advanced eDiscovery v2.0 の以前の retirment フェーズの詳細については、「 [従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5db1c-109">To learn more about the previous retirment phases of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>

<span data-ttu-id="5db1c-110">高度な電子情報開示を使用すると、データの理解を深め、電子情報開示コストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-110">With Advanced eDiscovery, you can better understand your data and reduce your eDiscovery costs.</span></span> <span data-ttu-id="5db1c-111">高度な電子情報開示を使用すると、非構造化データの分析、ドキュメントレビューの効率化、電子情報開示のためのデータの削減に関する決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-111">Advanced eDiscovery helps you analyze unstructured data, perform more efficient document review, and make decisions to reduce data for eDiscovery.</span></span> <span data-ttu-id="5db1c-112">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 365 グループ、および Microsoft Teams に格納されているデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-112">You can work with data stored in Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft 365 Groups, and Microsoft Teams.</span></span> <span data-ttu-id="5db1c-113">セキュリティ/コンプライアンスセンターで電子情報開示検索を実行して、グループ、個々のメールボックス、サイト内のコンテンツを検索し、高度な電子情報開示を使用して検索結果を分析することができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-113">You can perform an eDiscovery search in the security and compliance center to search for content in groups, individual mailboxes and sites, and then analyze the search results with Advanced eDiscovery.</span></span> <span data-ttu-id="5db1c-114">高度な電子情報開示で分析のために検索結果を準備する場合、光学式文字認識で画像からテキストを抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-114">When you prepare search results for analysis in Advanced eDiscovery, Optical Character Recognition enables the extraction of text from images.</span></span> <span data-ttu-id="5db1c-115">この機能により、高度な電子情報開示の強力なテキスト分析機能を画像ファイルに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-115">This feature allows the powerful text analytic capabilities of Advanced eDiscovery to be applied to image files.</span></span>
  
<span data-ttu-id="5db1c-116">高度な電子情報開示では、同一の重複を検出し、電子メールスレッド分析などの機能を使用して、重複する情報を特定することで、ドキュメントのレビュープロセスを効率化し、スピードアップします</span><span class="sxs-lookup"><span data-stu-id="5db1c-116">Advanced eDiscovery streamlines and speeds up the document review process by identifying redundant information with features like Near-duplicates detection and Email Thread analysis.</span></span> <span data-ttu-id="5db1c-117">関連性機能は、予測コーディングテクノロジを適用して、関連するドキュメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-117">The Relevance feature applies predictive coding technology to identify relevant documents.</span></span> <span data-ttu-id="5db1c-118">高度な電子情報開示は、サンプルドキュメントでのタグ付けの決定から学んで、統計情報と自己学習技術を適用して、データセット内の各ドキュメントの関連性を計算します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-118">Advanced eDiscovery learns from your tagging decisions on sample documents and applies statistical and self-learning techniques to calculate the relevance of each document in the data set.</span></span> <span data-ttu-id="5db1c-119">これにより、主要なドキュメントに集中して、必要な場合について迅速に判断し、データをカリングし、レビューの優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-119">This enables you to focus on key documents, make quick yet informed decisions on case strategy, cull data, and prioritize review.</span></span>
  
 <span data-ttu-id="5db1c-120">**高度な電子情報開示が理由**</span><span class="sxs-lookup"><span data-stu-id="5db1c-120">**Why advanced eDiscovery?**</span></span> <span data-ttu-id="5db1c-121">高度な電子情報開示は、Office 365 の既存の電子情報開示機能のセットに基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-121">Advanced eDiscovery builds on the existing set of eDiscovery capabilities in Office 365.</span></span> <span data-ttu-id="5db1c-122">たとえば、セキュリティコンプライアンスセンターの検索機能を使用して、 &amp; 組織内のすべてのコンテンツソースの最初の検索を実行し、特定の訴訟に関連する可能性があるデータを識別して収集できます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-122">For example, you can use the Search feature in the Security &amp; Compliance Center to perform an initial search of all the content sources in your organization to identify and collect the data that may be relevant to a specific legal case.</span></span> <span data-ttu-id="5db1c-123">その後、高度な電子情報開示のためのテキスト分析、マシン学習、および関連性/予測のコーディング機能を適用することによって、そのデータに対する分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-123">Then you can perform analysis on that data by applying the text analytics, machine learning, and the Relevance/predictive coding capabilities of Advanced eDiscovery.</span></span> <span data-ttu-id="5db1c-124">これにより、組織は、多数の電子メールメッセージ、ドキュメント、およびその他の種類のデータをすばやく処理して、特定のアイテムに関連している可能性の高いものを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-124">This can help your organization quickly process thousands of email messages, documents, and other kinds of data to find those items that are most likely relevant to a specific</span></span> 
 
> [!NOTE]
> <span data-ttu-id="5db1c-125">高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="5db1c-125">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="5db1c-126">その計画がなく、高度な電子情報開示を試行する必要がある場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-126">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> <span data-ttu-id="5db1c-127">当て.</span><span class="sxs-lookup"><span data-stu-id="5db1c-127">case.</span></span> <span data-ttu-id="5db1c-128">その後、削減されたデータセットは、さらなるレビューのために Office 365 からエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-128">The reduced data set can then be exported out of Office 365 for further review.</span></span> 
  
## <a name="get-started"></a><span data-ttu-id="5db1c-129">作業の開始</span><span class="sxs-lookup"><span data-stu-id="5db1c-129">Get started</span></span>

<span data-ttu-id="5db1c-130">高度な電子情報開示を開始する最も簡単な方法は、ケースを作成して、セキュリティ & コンプライアンスセンターで検索結果を準備し、それらの結果を高度な電子情報開示にロードして、そのケースデータを分析してから、外部レビューの結果をエクスポートするためのエクスプレス分析を実行することです。</span><span class="sxs-lookup"><span data-stu-id="5db1c-130">The quickest way to get started with Advanced eDiscovery is to create a case and prepare search results in Security & Compliance Center, load those results in Advanced eDiscovery, and then run Express analysis to analyze that case data and then export the results for external review.</span></span>
  
- <span data-ttu-id="5db1c-131">高度な電子情報開示ワークフローの[簡単な概要を取得する](quick-setup-for-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5db1c-131">[Get a quick overview](quick-setup-for-advanced-ediscovery.md) of the Advanced eDiscovery workflow</span></span> 
    
- <span data-ttu-id="5db1c-132">セキュリティ & コンプライアンスセンターを使用して、ケースの作成、電子情報開示のアクセス許可の割り当て、ケースメンバーの追加を行うことで、高度な電子情報開示の[ユーザーおよびケースをセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)する</span><span class="sxs-lookup"><span data-stu-id="5db1c-132">[Set up users and cases](set-up-users-and-cases-in-advanced-ediscovery.md) for Advanced eDiscovery by creating a case, assigning eDiscovery permissions, and adding case members, all by using the Security & Compliance Center</span></span> 
    
- <span data-ttu-id="5db1c-133">高度な電子情報開示のケースへの[検索データの準備と読み込み](prepare-data-for-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5db1c-133">[Prepare and load search data](prepare-data-for-advanced-ediscovery.md) in to the case in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="5db1c-134">[Office 以外の365データ](import-non-office-365-data-into-advanced-ediscovery.md) をケースに読み込み、高度な電子情報開示で分析する</span><span class="sxs-lookup"><span data-stu-id="5db1c-134">[Load non-Office 365 data](import-non-office-365-data-into-advanced-ediscovery.md) in to a case to analyze it in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="5db1c-135">[エクスプレス分析を使用](use-express-analysis-in-advanced-ediscovery.md) してデータをケースにすばやく分析し、結果を簡単にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5db1c-135">[Use Express analysis](use-express-analysis-in-advanced-ediscovery.md) to quickly analyze the data in a case and then easily export the results</span></span> 
    
## <a name="analyze-data"></a><span data-ttu-id="5db1c-136">データを分析する</span><span class="sxs-lookup"><span data-stu-id="5db1c-136">Analyze data</span></span>

<span data-ttu-id="5db1c-137">高度な電子情報開示のケースに検索データが読み込まれたら、Analyze モジュールを使用して分析を開始します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-137">After search data is loaded into the case in Advanced eDiscovery, you'll use the Analyze module to start analyzing it.</span></span> <span data-ttu-id="5db1c-138">分析プロセスの最初の部分では、ファイルを一意のファイルのグループに分類し、重複して、重複しないようにします (ドキュメントの類似性とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="5db1c-138">The first part of the analysis process consists of organizing files into groups of unique files, duplicates, and near-duplicates (also know as document similarity).</span></span> <span data-ttu-id="5db1c-139">その後、データを再編成して、階層構造の電子メールのスレッドとテーマをグループ化し、オプションで、特定のテキストを分析から除外するように無視するテキストフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-139">Then you organize the data again into hierarchically structured groups of email threads and themes and, optionally, set ignore text filters to exclude certain text from analysis.</span></span> <span data-ttu-id="5db1c-140">次に、分析を実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-140">Then you run the analysis and view the results.</span></span>
  
- <span data-ttu-id="5db1c-141">詳細な電子情報開示でのデータの分析を準備するための[ドキュメントの類似](understand-document-similarity-in-advanced-ediscovery.md)点について</span><span class="sxs-lookup"><span data-stu-id="5db1c-141">[Learn about document similarity](understand-document-similarity-in-advanced-ediscovery.md) to prepare you for analyzing data in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="5db1c-142">ほぼ重複、テーマ、および電子メールのスレッド処理の[オプションを設定](set-analyze-options-in-advanced-ediscovery.md)してから、Analyze モジュールを実行します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-142">[Set up the options](set-analyze-options-in-advanced-ediscovery.md) for near-duplicates, themes, and email threading and then run the Analyze module</span></span> 
    
- <span data-ttu-id="5db1c-143">テキストおよびテキスト文字列を分析対象から除外するように、[無視するテキストフィルターを設定](set-ignore-text-in-advanced-ediscovery.md)します。このフィルターでは、関連性分析を実行するときにもテキストは無視されます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-143">[Set up Ignore Text filters](set-ignore-text-in-advanced-ediscovery.md) to exclude text and text strings from being analyzed; these filters will also ignore text when you run Relevance analysis</span></span> 
    
- <span data-ttu-id="5db1c-144">分析プロセスの[結果を表示する](view-analyze-results-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5db1c-144">[View the results](view-analyze-results-in-advanced-ediscovery.md) of the analysis process</span></span> 
    
- <span data-ttu-id="5db1c-145">分析プロセスの[詳細設定を構成する](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="5db1c-145">[Configure advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for the analysis process</span></span> 
    
## <a name="set-up-relevance-training"></a><span data-ttu-id="5db1c-146">関連トレーニングの設定</span><span class="sxs-lookup"><span data-stu-id="5db1c-146">Set up Relevance training</span></span>

<span data-ttu-id="5db1c-147">上級電子情報開示の予測コーディング (関連性と呼ばれる) を使用すると、ドキュメントの小さなセットに対して意思決定 (関連性があるかどうかに関する決定) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-147">Predictive coding (called Relevance) in Advanced eDiscovery lets you train the system on what you're looking for by letting you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span>
  
- <span data-ttu-id="5db1c-148">関連性トレーニングのセットアップ、ケースに関連するタグ付けファイル、ケース問題の定義[について説明](manage-relevance-setup-in-advanced-ediscovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-148">[Learn about setting up Relevance training](manage-relevance-setup-in-advanced-ediscovery.md) , tagging files that are relevant to a case, and defining case issues</span></span> 
    
- <span data-ttu-id="5db1c-149">[ケースの問題を定義](define-issues-and-assign-users.md) し、各問題をファイルをトレーニングするユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="5db1c-149">[Define case issues](define-issues-and-assign-users.md) and assign each issue to a user who will train the files</span></span> 
    
- <span data-ttu-id="5db1c-150">インポートされたファイルを、関連トレーニングに追加する[現在のまたは新しい負荷に追加](set-up-loads-to-add-imported-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-150">[Add imported files to current or new load](set-up-loads-to-add-imported-files.md) that will be added to the Relevance training.</span></span> <span data-ttu-id="5db1c-151">ロードは、ケースに追加され、関連トレーニングに使用されるファイルの新しいバッチです。</span><span class="sxs-lookup"><span data-stu-id="5db1c-151">A load is a new batch of files that are added to a case and then used for Relevance training</span></span> 
    
- <span data-ttu-id="5db1c-152">関連性トレーニングに追加できる[強調表示](define-highlighted-keywords-and-advanced-options.md)されたキーワードを定義します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-152">[Define highlighted keywords](define-highlighted-keywords-and-advanced-options.md) that can be added to the Relevance training.</span></span> <span data-ttu-id="5db1c-153">これにより、ケースに関連するファイルを特定しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="5db1c-153">This helps you better identify files that are relevant to a case</span></span> 
    
## <a name="run-the-relevance-module"></a><span data-ttu-id="5db1c-154">関連性モジュールを実行する</span><span class="sxs-lookup"><span data-stu-id="5db1c-154">Run the Relevance module</span></span>

<span data-ttu-id="5db1c-155">トレーニングを設定すると、関連性モジュールを実行し、トレーニング設定の有効性を評価できます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-155">After set up training, you're ready to run the Relevance module and assess the effectiveness of the training settings.</span></span> <span data-ttu-id="5db1c-156">これにより、追加のトレーニングを実行する必要があるかどうかを判断したり、ケースに関連してファイルのタグ付けを開始する準備が整っているかどうかを判断したりするのに役立つ関連性ランキングが得られます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-156">This results in a relevance ranking that helps you decide if you need to perform additional training or if you're ready to start tagging files as relevant to your case.</span></span>
  
- <span data-ttu-id="5db1c-157">サンプルのファイルセットに基づいた評価、タグ付け、追跡、再トレーニングの関連性プロセスと反復プロセス[について説明](use-relevance-in-advanced-ediscovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-157">[Learn about the Relevance process](use-relevance-in-advanced-ediscovery.md) and the iterative process of assessment, tagging, tracking, and retraining based on sample set of files</span></span> 
    
- <span data-ttu-id="5db1c-158">ケースに精通したエキスパートがケースファイルのセットをレビューし、関連性トレーニングの効果を判断する[評価について説明](assessment-in-relevance-in-advanced-ediscovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-158">[Learn about assessment](assessment-in-relevance-in-advanced-ediscovery.md) , where an expert familiar with the case reviews a set of case files and determines the effectiveness of the Relevance training</span></span> 
    
- <span data-ttu-id="5db1c-159">[ケースファイルを評価](tagging-and-assessment-in-advanced-ediscovery.md) して、トレーニング設定の有効性 (\* 多様性) を計算し、ケースに関連するファイルまたは関連しないファイルにタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="5db1c-159">[Assess case files](tagging-and-assessment-in-advanced-ediscovery.md) to calculate the effectiveness (called  \*richness) of training settings, and then tag files as relevant or not relevant to your case.</span></span> <span data-ttu-id="5db1c-160">これにより、現在のトレーニングが十分かどうか、またはトレーニングの設定を調整する必要があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-160">This helps you determine if the current training is sufficient or if you should adjust the training settings.</span></span> 
    
- <span data-ttu-id="5db1c-161">評価が完了した後に[関連性トレーニングを実行](tagging-and-relevance-training-in-advanced-ediscovery.md)し、そのケースに対して定義した問題に関連するファイルまたは関連していないファイルに再度タグ付けする</span><span class="sxs-lookup"><span data-stu-id="5db1c-161">[Perform the relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md) after assessment is complete, and then once again tag files as relevant or not relevant to the issues you've defined for the case</span></span> 
    
- <span data-ttu-id="5db1c-162">関連性[の分析プロセスを追跡して、](track-relevance-analysis-in-advanced-ediscovery.md)関連性トレーニングが評価目標を達成したか (\* stable トレーニング状態)、またはさらにトレーニングが必要かどうかを判断します。各ケースの問題に関する関連性の結果を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-162">[Track the Relevance analysis](track-relevance-analysis-in-advanced-ediscovery.md) process to determine if Relevance training has achieved your assessment target (known as a  \*stable training status) or whether more training is needed; you can also view the Relevance results for each case issue</span></span> 
    
- <span data-ttu-id="5db1c-163">レビュー用にエクスポートできるケースファイルの結果セットのサイズを決定するために、[関連性分析に基づいて決定を行い](decision-based-on-the-results-in-advanced-ediscovery.md)ます。</span><span class="sxs-lookup"><span data-stu-id="5db1c-163">[Make decisions based on Relevance analysis](decision-based-on-the-results-in-advanced-ediscovery.md) to determine the size of the resulting set of case files that can be exported for review</span></span> 
    
- <span data-ttu-id="5db1c-164">関連性[分析の品質をテスト](test-relevance-analysis-in-advanced-ediscovery.md)して、関連性プロセス中に行われたカリングの決定を検証する</span><span class="sxs-lookup"><span data-stu-id="5db1c-164">[Test the quality of the Relevance analysis](test-relevance-analysis-in-advanced-ediscovery.md) to validate the culling decisions made during the Relevance process</span></span> 
    
## <a name="export-results"></a><span data-ttu-id="5db1c-165">結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="5db1c-165">Export results</span></span>

<span data-ttu-id="5db1c-166">Advanced eDiscovery でケースデータを分析する最後の手順は、外部レビューの分析結果をエクスポートすることです。</span><span class="sxs-lookup"><span data-stu-id="5db1c-166">The final step in analyzing case data in Advanced eDiscovery is to export results of the analysis for external review.</span></span>
  
- [<span data-ttu-id="5db1c-167">ケースデータのエクスポートについて</span><span class="sxs-lookup"><span data-stu-id="5db1c-167">Learn about exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="5db1c-168">ケース データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5db1c-168">Export case data</span></span>](export-results-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="5db1c-169">バッチ履歴を表示し、過去の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5db1c-169">View batch history and export past results</span></span>](view-batch-history-and-export-past-results.md)
    
- [<span data-ttu-id="5db1c-170">レポート フィールドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="5db1c-170">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a><span data-ttu-id="5db1c-171">その他の高度な電子情報開示ツール</span><span class="sxs-lookup"><span data-stu-id="5db1c-171">Other Advanced eDiscovery tools</span></span>

<span data-ttu-id="5db1c-172">Advanced eDiscovery は、ケースデータの分析、関連性分析、データのエクスポート以外に、追加のツールと機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5db1c-172">Advanced eDiscovery provides additional tools and capabilities beyond analyzing case data, relevance analysis, and exporting data.</span></span>
  
- [<span data-ttu-id="5db1c-173">高度な電子情報開示レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="5db1c-173">Run Advanced eDiscovery reports</span></span>](run-reports-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="5db1c-174">ケースとテナントの設定を定義する</span><span class="sxs-lookup"><span data-stu-id="5db1c-174">Define case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="5db1c-175">高度な電子情報開示ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="5db1c-175">Advanced eDiscovery utilities</span></span>](use-advanced-ediscovery-utilities.md)
