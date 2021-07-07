---
title: CPU 回帰分析
description: CPU 消費の回帰結果と指標について
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322992"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="bead6-103">インテリジェント CPU 回帰分析</span><span class="sxs-lookup"><span data-stu-id="bead6-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="bead6-104">CPU 使用率は、アプリケーションがオペレーティング システム更新プログラムの影響を受けるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bead6-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="bead6-105">Test Base for Microsoft 365 は、今後の Windows オペレーティング システム (OS) 更新プログラムの異なるバージョンでアプリケーションが実行されている場合に発生する CPU パフォーマンスの回帰に関する分析情報をソフトウェア開発者に提供します。</span><span class="sxs-lookup"><span data-stu-id="bead6-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="bead6-106">これらの CPU 回帰により、開発者は OS 更新プログラムを広く展開する前にアプリケーションの問題 (および潜在的な障害) を検出して解決し、エンド ユーザーの悪いエクスペリエンスを防ぐことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="bead6-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="bead6-107">CPU 回帰分析のしくみ</span><span class="sxs-lookup"><span data-stu-id="bead6-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="bead6-108">Test Base ユーザーは、アプリケーションのバイナリ (単一の .zip ファイル内) を関連付けられたテスト スクリプトと共にアップロードし、Azure のテスト ベース ポータルでアプリケーションをテストする Windows OS バージョンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bead6-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="bead6-109">次に、テスト ベース サービスはテスト スクリプトを実行し **、CPU 回帰分析を実行します**。</span><span class="sxs-lookup"><span data-stu-id="bead6-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="bead6-110">サービスは、ターゲット OS のプレリリース バージョンの更新プログラム上のアプリケーションの CPU 使用率が、リリースされたバージョンの OS の CPU 使用率と一緒にあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="bead6-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="bead6-111">OS の 2 つのバージョンで実行されているプロセスは、OS のバージョンが異なって完全に一致する場合と一致しない場合があります。ただし、Test Base によって実行される分析では、今後の OS 更新プログラムによってアプリケーションの CPU 使用率が影響を受け、具体的には以前のテスト実行からどのプロセスが後退したのかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bead6-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="bead6-112">以下のスナップショットでは、同じアプリケーションの CPU 使用率を比較する 2 つの OS リリースがあります。</span><span class="sxs-lookup"><span data-stu-id="bead6-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="bead6-113">[CPU 使用率] タブには、それぞれ 90 パーセントと 10 パーセントの両方のリリースの使用率の上限と下限が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bead6-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="bead6-114">グラフは、平均使用率と共に CPU 使用率の時系列を示しています。</span><span class="sxs-lookup"><span data-stu-id="bead6-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="bead6-115">お客様は、この機能を使用して、アプリケーションの CPU 使用率が OS 更新プログラムの影響を受けるかどうかを判断し、具体的には以前の実行からどのプロセスが後退したのか判断できます。</span><span class="sxs-lookup"><span data-stu-id="bead6-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![CPU 回帰分析](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="bead6-117">関連するプロセスの識別</span><span class="sxs-lookup"><span data-stu-id="bead6-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="bead6-118">ここでは、アプリケーション内の回帰プロセスを識別する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bead6-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="bead6-119">パフォーマンス回帰を分析するには、テストの実行中に仮想マシンで実行されるプロセスごとに、さまざまな種類のパフォーマンス カウンターを追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bead6-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="bead6-120">このような分析は、特定のアプリケーションの多くのプロセスに対して多くの変数をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="bead6-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="bead6-121">一部のプロセスが実行またはアプリケーションに関連付けられている場合ではありません。</span><span class="sxs-lookup"><span data-stu-id="bead6-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="bead6-122">この課題を回避するために、確率と情報理論を使用した相互情報ランク付けアルゴリズムを適用して、特定のアプリケーションに最も関連性の高いプロセスを特定します。</span><span class="sxs-lookup"><span data-stu-id="bead6-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="bead6-123">アプリケーションは 1 種類の個別ランダム変数と見なされ、プロセスは別の種類の個別ランダム変数と見なされます。</span><span class="sxs-lookup"><span data-stu-id="bead6-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="bead6-124">2 つのランダム変数の関連付けは、関連性の条件付き確率を使用して測定されます。</span><span class="sxs-lookup"><span data-stu-id="bead6-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="bead6-125">次に、各アプリケーションの関連性の順序でプロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bead6-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="bead6-126">また、CPU 回帰分析に関連するプロセスと共に、既定で監視できるプロセスのサブセットをお気に入りに設定できます。</span><span class="sxs-lookup"><span data-stu-id="bead6-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="bead6-127">回帰が検出されると、パフォーマンス アナライザー ツールキットWindowsダウンロードし、CPU パフォーマンス回帰の理由を分析できます。</span><span class="sxs-lookup"><span data-stu-id="bead6-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="bead6-128">パフォーマンス Windowsは、イベント トレース ログ (ETL) を入力として受け取り、これらの .etl ファイルは、ポータルでテスト実行のためにダウンロード可能なログ ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bead6-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="bead6-129">CPU パフォーマンスのデバッグの詳細については、「パフォーマンス アナライザー」のドキュメントWindows参照してください。</span><span class="sxs-lookup"><span data-stu-id="bead6-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

