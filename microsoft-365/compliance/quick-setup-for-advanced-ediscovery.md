---
title: Advanced eDiscovery のクイック セットアップ
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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: セキュリティ &amp; コンプライアンス センターから Advanced eDiscovery にアクセスする方法を説明し、Advanced eDiscovery を使用するための一般的なワークフローを確認します。
ms.openlocfilehash: 9aca86d59b3f6b5f77ea5b6eb4c5d0bbe156beb1
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662852"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="2a116-103">Advanced eDiscovery (クラシック) のクイック セットアップ</span><span class="sxs-lookup"><span data-stu-id="2a116-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a116-104">新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。</span><span class="sxs-lookup"><span data-stu-id="2a116-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="2a116-105">まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション* とも呼ばれる) に移行してください。</span><span class="sxs-lookup"><span data-stu-id="2a116-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="2a116-106">Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。</span><span class="sxs-lookup"><span data-stu-id="2a116-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="2a116-107">Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a116-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="2a116-108">このセットアップ セクションでは、Microsoft 365 セキュリティ&amp;コンプライアンス センターの電子情報開示管理者に、Advanced eDiscovery を開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2a116-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="2a116-109">両方に関して、実際上の知識があるものと想定しています。</span><span class="sxs-lookup"><span data-stu-id="2a116-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="2a116-110">Advanced eDiscovery のケースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="2a116-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="2a116-p103">セキュリティ&amp;コンプライアンス センターから Advanced eDiscovery にアクセスします。Advanced eDiscovery のケースにアクセスするには、セキュリティ&amp;コンプライアンス センターの電子情報開示ケースのメンバーである必要があります。電子情報開示ケースのアクセス許可の割り当て方法、電子情報開示ケースへのユーザーの追加方法については、「[Office 365 で電子情報開示ケースを管理する](ediscovery-cases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a116-p103">You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="2a116-114">Advanced eDiscovery のケースに移動するには、以下を実施します:</span><span class="sxs-lookup"><span data-stu-id="2a116-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="2a116-115">[セキュリティ&amp;コンプライアンス センターに移動します](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2a116-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="2a116-116">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="2a116-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="2a116-117">**[電子情報開示]** ページで、Advanced eDiscovery で移動するケースの横にある **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a116-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="2a116-118">ケースの [**ホーム**] ページで、[**Advanced eDiscovery に切り替え**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a116-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="2a116-p104">**[Advanced eDiscovery へ接続しています]** の進行状況バーが表示されます。接続されると、Advanced eDiscovery のケースが開きます。</span><span class="sxs-lookup"><span data-stu-id="2a116-p104">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="2a116-121">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="2a116-121">Workflow</span></span>

<span data-ttu-id="2a116-122">次の図は、セキュリティ&amp;コンプライアンス センターおよび Advanced eDiscovery において、電子情報開示ケースを管理および使用する一般的なワークフローを表したものです。</span><span class="sxs-lookup"><span data-stu-id="2a116-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![図は、Advanced eDiscovery のワークフローを示しています。セットアップには、ユーザー&amp;ケースのセットアップ、ケース データの特定、エクスポート、処理の 4 つのフェーズがあり、その後に分析とローカル コンピューターへのエクスポートのフェーズがあります。](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="2a116-p105">このセットアップ セクションでは、上記ワークフローの最初の 4 つの手順について説明します。ワークフローの他の手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a116-p105">This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="2a116-126">分析</span><span class="sxs-lookup"><span data-stu-id="2a116-126">Analyze</span></span>

<span data-ttu-id="2a116-p106">[ケース データの分析](analyze-case-data-with-advanced-ediscovery.md): さまざまなパラメーターでファイルの識別および整理を行い、テーマの使用を有効にして、結果を表示します。ユーザーは分析機能をカスタマイズして、詳細な結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="2a116-p106">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="2a116-129">関連性のセットアップおよび関連性</span><span class="sxs-lookup"><span data-stu-id="2a116-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="2a116-p107">[関連性のセットアップ](manage-relevance-setup-in-advanced-ediscovery.md)と[関連性モジュールの使用](use-relevance-in-advanced-ediscovery.md): ファイルのランダムなサンプルに基づく評価と関連性トレーニングを有効にし、その評価と関連性トレーニングを使用して、予測されるコーディング プロセスを決定します。プロセスの統計上の妥当性を監視しながら、中間結果を計算して表示します。校閲の意思決定を容易にする結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="2a116-p107">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="2a116-133">エクスポート</span><span class="sxs-lookup"><span data-stu-id="2a116-133">Export</span></span>

<span data-ttu-id="2a116-134">[ケース データのエクスポート](export-case-data-in-advanced-ediscovery.md): 外部で校閲できるように、Advanced eDiscovery のコンテンツと結果のエクスポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a116-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="2a116-135">レポート</span><span class="sxs-lookup"><span data-stu-id="2a116-135">Report</span></span>

<span data-ttu-id="2a116-136">[レポートを実行する](run-reports-in-advanced-ediscovery.md): 選択したレポートで Advanced eDiscovery の処理に関連するものの生成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a116-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2a116-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a116-137">See also</span></span>

[<span data-ttu-id="2a116-138">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="2a116-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2a116-139">ユーザーとケースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2a116-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a116-140">データの準備</span><span class="sxs-lookup"><span data-stu-id="2a116-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

