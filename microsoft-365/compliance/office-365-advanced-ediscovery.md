---
title: Office 365 Advanced eDiscovery
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
description: Office 365 Advanced eDiscovery を使用して Office 365 内のデータを分析し、ドキュメントレビューを合理化し、効率的な電子情報開示に関する決定を行う方法について説明します。
ms.openlocfilehash: a3a6291459005d60defe61a8bca40ce382b6d052
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597894"
---
# <a name="office-365-advanced-ediscovery"></a><span data-ttu-id="b58da-103">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b58da-103">Office 365 Advanced eDiscovery</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b58da-104">高度な電子情報開示の新バージョンへの投資を継続するうちに、microsoft は Office 365 Advanced eDiscovery ( *Advanced ediscovery*v2.0 とも呼ばれます) の廃止を発表しています。</span><span class="sxs-lookup"><span data-stu-id="b58da-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="b58da-105">まだ Advanced eDiscovery v2.0 を使用している場合は、できるだけ早く、advanced [ediscovery](overview-ediscovery-20.md) V2.0 ( *Microsoft 365 では高度な電子情報開示ソリューション*とも呼ばれます) に移行してください。</span><span class="sxs-lookup"><span data-stu-id="b58da-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="b58da-106">上級電子情報開示2.0 には、Advanced eDiscovery v2.0 のような機能がありますが、保管担当者管理、コミュニケーション管理、およびレビューセットなどの多くの新機能も提供しています。</span><span class="sxs-lookup"><span data-stu-id="b58da-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="b58da-107">Advanced eDiscovery v2.0 の廃止の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b58da-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
<span data-ttu-id="b58da-108">高度な電子情報開示を使用すると、Office 365 データをよりよく理解し、電子情報開示コストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="b58da-108">With Advanced eDiscovery, you can better understand your Office 365 data and reduce your eDiscovery costs.</span></span> <span data-ttu-id="b58da-109">高度な電子情報開示を使用すると、Office 365 内の非構造化データの分析、ドキュメントレビューの効率化、電子情報開示のためのデータの削減を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-109">Advanced eDiscovery helps you analyze unstructured data within Office 365, perform more efficient document review, and make decisions to reduce data for eDiscovery.</span></span> <span data-ttu-id="b58da-110">Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Office 365 グループ、および Microsoft Teams に格納されているデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="b58da-110">You can work with data stored in Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Office 365 Groups, and Microsoft Teams.</span></span> <span data-ttu-id="b58da-111">セキュリティ/コンプライアンスセンターで電子情報開示検索を実行して、グループ、個々のメールボックス、サイト内のコンテンツを検索し、高度な電子情報開示を使用して検索結果を分析することができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-111">You can perform an eDiscovery search in the security and compliance center to search for content in groups, individual mailboxes and sites, and then analyze the search results with Advanced eDiscovery.</span></span> <span data-ttu-id="b58da-112">高度な電子情報開示で分析のために検索結果を準備する場合、光学式文字認識で画像からテキストを抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-112">When you prepare search results for analysis in Advanced eDiscovery, Optical Character Recognition enables the extraction of text from images.</span></span> <span data-ttu-id="b58da-113">この機能により、高度な電子情報開示の強力なテキスト分析機能を画像ファイルに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-113">This feature allows the powerful text analytic capabilities of Advanced eDiscovery to be applied to image files.</span></span>
  
<span data-ttu-id="b58da-114">高度な電子情報開示では、同一の重複を検出し、電子メールスレッド分析などの機能を使用して、重複する情報を特定することで、ドキュメントのレビュープロセスを効率化し、スピードアップします</span><span class="sxs-lookup"><span data-stu-id="b58da-114">Advanced eDiscovery streamlines and speeds up the document review process by identifying redundant information with features like Near-duplicates detection and Email Thread analysis.</span></span> <span data-ttu-id="b58da-115">関連性機能は、予測コーディングテクノロジを適用して、関連するドキュメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="b58da-115">The Relevance feature applies predictive coding technology to identify relevant documents.</span></span> <span data-ttu-id="b58da-116">高度な電子情報開示は、サンプルドキュメントでのタグ付けの決定から学んで、統計情報と自己学習技術を適用して、データセット内の各ドキュメントの関連性を計算します。</span><span class="sxs-lookup"><span data-stu-id="b58da-116">Advanced eDiscovery learns from your tagging decisions on sample documents and applies statistical and self-learning techniques to calculate the relevance of each document in the data set.</span></span> <span data-ttu-id="b58da-117">これにより、主要なドキュメントに集中して、必要な場合について迅速に判断し、データをカリングし、レビューの優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-117">This enables you to focus on key documents, make quick yet informed decisions on case strategy, cull data, and prioritize review.</span></span>
  
 <span data-ttu-id="b58da-118">**高度な電子情報開示が理由**</span><span class="sxs-lookup"><span data-stu-id="b58da-118">**Why advanced eDiscovery?**</span></span> <span data-ttu-id="b58da-119">Office 365 の高度な電子情報開示は、Office 365 の既存の電子情報開示機能のセットに基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="b58da-119">Office 365 Advanced eDiscovery builds on the existing set of eDiscovery capabilities in Office 365.</span></span> <span data-ttu-id="b58da-120">たとえば、Office 365 セキュリティ&amp;コンプライアンスセンターの検索機能を使用して、組織内のすべてのコンテンツソースの最初の検索を実行し、特定の訴訟に関連する可能性があるデータを特定して収集することができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-120">For example, you can use the Search feature in the Office 365 Security &amp; Compliance Center to perform an initial search of all the content sources in your organization to identify and collect the data that may be relevant to a specific legal case.</span></span> <span data-ttu-id="b58da-121">その後、高度な電子情報開示のためのテキスト分析、マシン学習、および関連性/予測のコーディング機能を適用することによって、そのデータに対する分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b58da-121">Then you can perform analysis on that data by applying the text analytics, machine learning, and the Relevance/predictive coding capabilities of Advanced eDiscovery.</span></span> <span data-ttu-id="b58da-122">これにより、組織は、多数の電子メールメッセージ、ドキュメント、およびその他の種類のデータをすばやく処理して、特定のアイテムに関連している可能性の高いものを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-122">This can help your organization quickly process thousands of email messages, documents, and other kinds of data to find those items that are most likely relevant to a specific</span></span> 
 
> [!NOTE]
> <span data-ttu-id="b58da-123">高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b58da-123">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="b58da-124">その計画がなく、高度な電子情報開示を試行する必要がある場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-124">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> <span data-ttu-id="b58da-125">当て.</span><span class="sxs-lookup"><span data-stu-id="b58da-125">case.</span></span> <span data-ttu-id="b58da-126">その後、削減されたデータセットは、さらなるレビューのために Office 365 からエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-126">The reduced data set can then be exported out of Office 365 for further review.</span></span> 
  
## <a name="get-started"></a><span data-ttu-id="b58da-127">はじめに</span><span class="sxs-lookup"><span data-stu-id="b58da-127">Get started</span></span>

<span data-ttu-id="b58da-128">高度な電子情報開示を開始する最も簡単な方法は、ケースを作成して、セキュリティ & コンプライアンスセンターで検索結果を準備し、それらの結果を高度な電子情報開示にロードして、そのケースデータを分析してから、外部レビューの結果をエクスポートするためのエクスプレス分析を実行することです。</span><span class="sxs-lookup"><span data-stu-id="b58da-128">The quickest way to get started with Advanced eDiscovery is to create a case and prepare search results in Security & Compliance Center, load those results in Advanced eDiscovery, and then run Express analysis to analyze that case data and then export the results for external review.</span></span>
  
- <span data-ttu-id="b58da-129">高度な電子情報開示ワークフローの[簡単な概要を取得する](quick-setup-for-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b58da-129">[Get a quick overview](quick-setup-for-advanced-ediscovery.md) of the Advanced eDiscovery workflow</span></span> 
    
- <span data-ttu-id="b58da-130">セキュリティ & コンプライアンスセンターを使用して、ケースの作成、電子情報開示のアクセス許可の割り当て、ケースメンバーの追加を行うことで、高度な電子情報開示の[ユーザーおよびケースをセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)する</span><span class="sxs-lookup"><span data-stu-id="b58da-130">[Set up users and cases](set-up-users-and-cases-in-advanced-ediscovery.md) for Advanced eDiscovery by creating a case, assigning eDiscovery permissions, and adding case members, all by using the Security & Compliance Center</span></span> 
    
- <span data-ttu-id="b58da-131">高度な電子情報開示のケースへの[検索データの準備と読み込み](prepare-data-for-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b58da-131">[Prepare and load search data](prepare-data-for-advanced-ediscovery.md) in to the case in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="b58da-132">[Office 以外の365データ](import-non-office-365-data-into-advanced-ediscovery.md)をケースに読み込み、高度な電子情報開示で分析する</span><span class="sxs-lookup"><span data-stu-id="b58da-132">[Load non-Office 365 data](import-non-office-365-data-into-advanced-ediscovery.md) in to a case to analyze it in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="b58da-133">[エクスプレス分析を使用](use-express-analysis-in-advanced-ediscovery.md)してデータをケースにすばやく分析し、結果を簡単にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b58da-133">[Use Express analysis](use-express-analysis-in-advanced-ediscovery.md) to quickly analyze the data in a case and then easily export the results</span></span> 
    
## <a name="analyze-data"></a><span data-ttu-id="b58da-134">データを分析する</span><span class="sxs-lookup"><span data-stu-id="b58da-134">Analyze data</span></span>

<span data-ttu-id="b58da-135">高度な電子情報開示のケースに検索データが読み込まれたら、Analyze モジュールを使用して分析を開始します。</span><span class="sxs-lookup"><span data-stu-id="b58da-135">After search data is loaded into the case in Advanced eDiscovery, you'll use the Analyze module to start analyzing it.</span></span> <span data-ttu-id="b58da-136">分析プロセスの最初の部分では、ファイルを一意のファイルのグループに分類し、重複して、重複しないようにします (ドキュメントの類似性とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="b58da-136">The first part of the analysis process consists of organizing files into groups of unique files, duplicates, and near-duplicates (also know as document similarity).</span></span> <span data-ttu-id="b58da-137">その後、データを再編成して、階層構造の電子メールのスレッドとテーマをグループ化し、オプションで、特定のテキストを分析から除外するように無視するテキストフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="b58da-137">Then you organize the data again into hierarchically structured groups of email threads and themes and, optionally, set ignore text filters to exclude certain text from analysis.</span></span> <span data-ttu-id="b58da-138">次に、分析を実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="b58da-138">Then you run the analysis and view the results.</span></span>
  
- <span data-ttu-id="b58da-139">詳細な電子情報開示でのデータの分析を準備するための[ドキュメントの類似](understand-document-similarity-in-advanced-ediscovery.md)点について</span><span class="sxs-lookup"><span data-stu-id="b58da-139">[Learn about document similarity](understand-document-similarity-in-advanced-ediscovery.md) to prepare you for analyzing data in Advanced eDiscovery</span></span> 
    
- <span data-ttu-id="b58da-140">ほぼ重複、テーマ、および電子メールのスレッド処理の[オプションを設定](set-analyze-options-in-advanced-ediscovery.md)してから、Analyze モジュールを実行します。</span><span class="sxs-lookup"><span data-stu-id="b58da-140">[Set up the options](set-analyze-options-in-advanced-ediscovery.md) for near-duplicates, themes, and email threading and then run the Analyze module</span></span> 
    
- <span data-ttu-id="b58da-141">テキストおよびテキスト文字列を分析対象から除外するように、[無視するテキストフィルターを設定](set-ignore-text-in-advanced-ediscovery.md)します。このフィルターでは、関連性分析を実行するときにもテキストは無視されます。</span><span class="sxs-lookup"><span data-stu-id="b58da-141">[Set up Ignore Text filters](set-ignore-text-in-advanced-ediscovery.md) to exclude text and text strings from being analyzed; these filters will also ignore text when you run Relevance analysis</span></span> 
    
- <span data-ttu-id="b58da-142">分析プロセスの[結果を表示する](view-analyze-results-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b58da-142">[View the results](view-analyze-results-in-advanced-ediscovery.md) of the analysis process</span></span> 
    
- <span data-ttu-id="b58da-143">分析プロセスの[詳細設定を構成する](set-analyze-advanced-settings-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="b58da-143">[Configure advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for the analysis process</span></span> 
    
## <a name="set-up-relevance-training"></a><span data-ttu-id="b58da-144">関連トレーニングの設定</span><span class="sxs-lookup"><span data-stu-id="b58da-144">Set up Relevance training</span></span>

<span data-ttu-id="b58da-145">上級電子情報開示の予測コーディング (関連性と呼ばれる) を使用すると、ドキュメントの小さなセットに対して意思決定 (関連性があるかどうかに関する決定) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b58da-145">Predictive coding (called Relevance) in Advanced eDiscovery lets you train the system on what you're looking for by letting you to make decisions (about whether something is relevant or not) on a small set of documents.</span></span>
  
- <span data-ttu-id="b58da-146">関連性トレーニングのセットアップ、ケースに関連するタグ付けファイル、ケース問題の定義[について説明](manage-relevance-setup-in-advanced-ediscovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="b58da-146">[Learn about setting up Relevance training](manage-relevance-setup-in-advanced-ediscovery.md) , tagging files that are relevant to a case, and defining case issues</span></span> 
    
- <span data-ttu-id="b58da-147">[ケースの問題を定義](define-issues-and-assign-users.md)し、各問題をファイルをトレーニングするユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b58da-147">[Define case issues](define-issues-and-assign-users.md) and assign each issue to a user who will train the files</span></span> 
    
- <span data-ttu-id="b58da-148">インポートされたファイルを、関連トレーニングに追加する[現在のまたは新しい負荷に追加](set-up-loads-to-add-imported-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="b58da-148">[Add imported files to current or new load](set-up-loads-to-add-imported-files.md) that will be added to the Relevance training.</span></span> <span data-ttu-id="b58da-149">ロードは、ケースに追加され、関連トレーニングに使用されるファイルの新しいバッチです。</span><span class="sxs-lookup"><span data-stu-id="b58da-149">A load is a new batch of files that are added to a case and then used for Relevance training</span></span> 
    
- <span data-ttu-id="b58da-150">関連性トレーニングに追加できる[強調表示](define-highlighted-keywords-and-advanced-options.md)されたキーワードを定義します。</span><span class="sxs-lookup"><span data-stu-id="b58da-150">[Define highlighted keywords](define-highlighted-keywords-and-advanced-options.md) that can be added to the Relevance training.</span></span> <span data-ttu-id="b58da-151">これにより、ケースに関連するファイルを特定しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b58da-151">This helps you better identify files that are relevant to a case</span></span> 
    
## <a name="run-the-relevance-module"></a><span data-ttu-id="b58da-152">関連性モジュールを実行する</span><span class="sxs-lookup"><span data-stu-id="b58da-152">Run the Relevance module</span></span>

<span data-ttu-id="b58da-153">トレーニングを設定すると、関連性モジュールを実行し、トレーニング設定の有効性を評価できます。</span><span class="sxs-lookup"><span data-stu-id="b58da-153">After set up training, you're ready to run the Relevance module and assess the effectiveness of the training settings.</span></span> <span data-ttu-id="b58da-154">これにより、追加のトレーニングを実行する必要があるかどうかを判断したり、ケースに関連してファイルのタグ付けを開始する準備が整っているかどうかを判断したりするのに役立つ関連性ランキングが得られます。</span><span class="sxs-lookup"><span data-stu-id="b58da-154">This results in a relevance ranking that helps you decide if you need to perform additional training or if you're ready to start tagging files as relevant to your case.</span></span>
  
- <span data-ttu-id="b58da-155">サンプルのファイルセットに基づいた評価、タグ付け、追跡、再トレーニングの関連性プロセスと反復プロセス[について説明](use-relevance-in-advanced-ediscovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="b58da-155">[Learn about the Relevance process](use-relevance-in-advanced-ediscovery.md) and the iterative process of assessment, tagging, tracking, and retraining based on sample set of files</span></span> 
    
- <span data-ttu-id="b58da-156">ケースに精通したエキスパートがケースファイルのセットをレビューし、関連性トレーニングの効果を判断する[評価について説明](assessment-in-relevance-in-advanced-ediscovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="b58da-156">[Learn about assessment](assessment-in-relevance-in-advanced-ediscovery.md) , where an expert familiar with the case reviews a set of case files and determines the effectiveness of the Relevance training</span></span> 
    
- <span data-ttu-id="b58da-157">[ケースファイルを評価](tagging-and-assessment-in-advanced-ediscovery.md)して、トレーニング設定の有効性 (\* 多様性) を計算し、ケースに関連するファイルまたは関連しないファイルにタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="b58da-157">[Assess case files](tagging-and-assessment-in-advanced-ediscovery.md) to calculate the effectiveness (called  \*richness) of training settings, and then tag files as relevant or not relevant to your case.</span></span> <span data-ttu-id="b58da-158">これにより、現在のトレーニングが十分かどうか、またはトレーニングの設定を調整する必要があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="b58da-158">This helps you determine if the current training is sufficient or if you should adjust the training settings.</span></span> 
    
- <span data-ttu-id="b58da-159">評価が完了した後に[関連性トレーニングを実行](tagging-and-relevance-training-in-advanced-ediscovery.md)し、そのケースに対して定義した問題に関連するファイルまたは関連していないファイルに再度タグ付けする</span><span class="sxs-lookup"><span data-stu-id="b58da-159">[Perform the relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md) after assessment is complete, and then once again tag files as relevant or not relevant to the issues you've defined for the case</span></span> 
    
- <span data-ttu-id="b58da-160">関連性[の分析プロセスを追跡して、](track-relevance-analysis-in-advanced-ediscovery.md)関連性トレーニングが評価目標を達成したか (\* stable トレーニング状態)、またはさらにトレーニングが必要かどうかを判断します。各ケースの問題に関する関連性の結果を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="b58da-160">[Track the Relevance analysis](track-relevance-analysis-in-advanced-ediscovery.md) process to determine if Relevance training has achieved your assessment target (known as a  \*stable training status) or whether more training is needed; you can also view the Relevance results for each case issue</span></span> 
    
- <span data-ttu-id="b58da-161">レビュー用にエクスポートできるケースファイルの結果セットのサイズを決定するために、[関連性分析に基づいて決定を行い](decision-based-on-the-results-in-advanced-ediscovery.md)ます。</span><span class="sxs-lookup"><span data-stu-id="b58da-161">[Make decisions based on Relevance analysis](decision-based-on-the-results-in-advanced-ediscovery.md) to determine the size of the resulting set of case files that can be exported for review</span></span> 
    
- <span data-ttu-id="b58da-162">関連性[分析の品質をテスト](test-relevance-analysis-in-advanced-ediscovery.md)して、関連性プロセス中に行われたカリングの決定を検証する</span><span class="sxs-lookup"><span data-stu-id="b58da-162">[Test the quality of the Relevance analysis](test-relevance-analysis-in-advanced-ediscovery.md) to validate the culling decisions made during the Relevance process</span></span> 
    
## <a name="export-results"></a><span data-ttu-id="b58da-163">結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="b58da-163">Export results</span></span>

<span data-ttu-id="b58da-164">Advanced eDiscovery でケースデータを分析する最後の手順は、外部レビューの分析結果をエクスポートすることです。</span><span class="sxs-lookup"><span data-stu-id="b58da-164">The final step in analyzing case data in Advanced eDiscovery is to export results of the analysis for external review.</span></span>
  
- [<span data-ttu-id="b58da-165">ケースデータのエクスポートについて</span><span class="sxs-lookup"><span data-stu-id="b58da-165">Learn about exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="b58da-166">ケース データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b58da-166">Export case data</span></span>](export-results-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="b58da-167">バッチ履歴を表示し、過去の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b58da-167">View batch history and export past results</span></span>](view-batch-history-and-export-past-results.md)
    
- [<span data-ttu-id="b58da-168">レポート フィールドのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b58da-168">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
    
## <a name="other-advanced-ediscovery-tools"></a><span data-ttu-id="b58da-169">その他の高度な電子情報開示ツール</span><span class="sxs-lookup"><span data-stu-id="b58da-169">Other Advanced eDiscovery tools</span></span>

<span data-ttu-id="b58da-170">Advanced eDiscovery は、ケースデータの分析、関連性分析、データのエクスポート以外に、追加のツールと機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b58da-170">Advanced eDiscovery provides additional tools and capabilities beyond analyzing case data, relevance analysis, and exporting data.</span></span>
  
- [<span data-ttu-id="b58da-171">高度な電子情報開示レポートを実行する</span><span class="sxs-lookup"><span data-stu-id="b58da-171">Run Advanced eDiscovery reports</span></span>](run-reports-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="b58da-172">ケースとテナントの設定を定義する</span><span class="sxs-lookup"><span data-stu-id="b58da-172">Define case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [<span data-ttu-id="b58da-173">高度な電子情報開示ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b58da-173">Advanced eDiscovery utilities</span></span>](use-advanced-ediscovery-utilities.md)
