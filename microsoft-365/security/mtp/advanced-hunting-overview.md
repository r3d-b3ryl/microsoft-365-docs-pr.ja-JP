---
title: Microsoft Threat Protection の高度な捜索の概要
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234756"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="3e832-104">Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する</span><span class="sxs-lookup"><span data-stu-id="3e832-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="3e832-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3e832-105">**Applies to:**</span></span>
- <span data-ttu-id="3e832-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3e832-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="3e832-107">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="3e832-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="3e832-108">ネットワーク内のイベントを事前に検査して、興味深いインジケーターとエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3e832-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="3e832-109">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対して、無制限な捜索が容易になります。</span><span class="sxs-lookup"><span data-stu-id="3e832-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="3e832-110">Microsoft 365 セキュリティセンターでは、高度な検索では、Microsoft Defender ATP、利用デバイスからのデータ、および Office 365 ATP のデータを参照するクエリをサポートしており、電子メールからのデータが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3e832-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="3e832-111">高度な捜索を使用するには、[Microsoft Threat Protection を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="3e832-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="3e832-112">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="3e832-112">Get started with advanced hunting</span></span>

<span data-ttu-id="3e832-113">高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3e832-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="3e832-114">学習目標</span><span class="sxs-lookup"><span data-stu-id="3e832-114">Learning goal</span></span> | <span data-ttu-id="3e832-115">説明</span><span class="sxs-lookup"><span data-stu-id="3e832-115">Description</span></span> | <span data-ttu-id="3e832-116">リソース</span><span class="sxs-lookup"><span data-stu-id="3e832-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="3e832-117">**言語に慣れる**</span><span class="sxs-lookup"><span data-stu-id="3e832-117">**Get a feel for the language**</span></span> | <span data-ttu-id="3e832-118">高度な捜索は、同じ構文および演算子をサポートする [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3e832-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="3e832-119">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="3e832-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="3e832-120">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="3e832-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="3e832-121">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="3e832-121">**Understand the schema**</span></span> | <span data-ttu-id="3e832-122">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="3e832-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="3e832-123">これにより、データを検索する場所およびクエリの作成方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="3e832-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="3e832-124">スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="3e832-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="3e832-125">**定義済みクエリを使用する**</span><span class="sxs-lookup"><span data-stu-id="3e832-125">**Use predefined queries**</span></span> | <span data-ttu-id="3e832-126">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="3e832-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="3e832-127">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3e832-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="3e832-128">**クエリを最適化する**</span><span class="sxs-lookup"><span data-stu-id="3e832-128">**Optimize queries**</span></span> | <span data-ttu-id="3e832-129">効率的なクエリおよびメールとデバイスからのデータを結合するクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="3e832-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="3e832-130">[クエリのベストプラクティス](advanced-hunting-shared-queries.md)、[デバイスやメール全体の捜索](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="3e832-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="3e832-131">クエリを記述するときにヘルプを参照する</span><span class="sxs-lookup"><span data-stu-id="3e832-131">Get help as you write queries</span></span>
<span data-ttu-id="3e832-132">次の機能を利用して、クエリをより速く記述します。</span><span class="sxs-lookup"><span data-stu-id="3e832-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="3e832-133">**自動補完候補** — クエリを記述するときに、高度な捜索が提案を提供します。</span><span class="sxs-lookup"><span data-stu-id="3e832-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="3e832-134">**スキーマ リファレンス** — テーブルとその列のリストを含むスキーマ リファレンスが作業領域の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e832-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="3e832-135">詳細については、アイテムにカーソルを合わせてください。</span><span class="sxs-lookup"><span data-stu-id="3e832-135">For more information, hover over an item.</span></span> <span data-ttu-id="3e832-136">アイテムをダブルクリックして、クエリ エディターに挿入します。</span><span class="sxs-lookup"><span data-stu-id="3e832-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="3e832-137">クエリ結果からドリルダウンする</span><span class="sxs-lookup"><span data-stu-id="3e832-137">Drilldown from query results</span></span>
<span data-ttu-id="3e832-138">クエリ結果でマシン、ファイル、ユーザー、IP アドレス、URL などのエンティティに関する詳細情報を表示するには、エンティティ識別子をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e832-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="3e832-139">これにより、Microsoft Defender セキュリティ センターで選択したエンティティの詳細なプロファイル ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="3e832-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="3e832-140">結果からクエリを絞り込む</span><span class="sxs-lookup"><span data-stu-id="3e832-140">Tweak your queries from the results</span></span>
<span data-ttu-id="3e832-141">結果セットの値を右クリックすると、クエリがすばやく強化されます。</span><span class="sxs-lookup"><span data-stu-id="3e832-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="3e832-142">次のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e832-142">You can use the options to:</span></span>

- <span data-ttu-id="3e832-143">選択した値 (`==`) を明示的に検索する</span><span class="sxs-lookup"><span data-stu-id="3e832-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="3e832-144">選択した値をクエリ (`!=`) から除外する </span><span class="sxs-lookup"><span data-stu-id="3e832-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="3e832-145">クエリに値を追加するためのより高度な演算子 `contains`、`starts with`、および `ends with` を取得する</span><span class="sxs-lookup"><span data-stu-id="3e832-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Microsoft Defender ATP の高度な捜索結果セットの画像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="3e832-147">クエリ結果をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="3e832-147">Filter the query results</span></span>
<span data-ttu-id="3e832-148">右に表示されるフィルターは、結果セットの要約を提供します。</span><span class="sxs-lookup"><span data-stu-id="3e832-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="3e832-149">各列には、その列で見つかった個別の値とインスタンスの数を一覧表示する独自のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="3e832-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="3e832-150">含めるまたは除外する値の [+] または [-] ボタンを選択し、[**クエリの実行**] を選択して、クエリを絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="3e832-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![高度な捜索フィルターの画像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="3e832-152">フィルターを適用してクエリを変更し、クエリを実行すると、結果がそれに応じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="3e832-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3e832-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e832-153">Related topics</span></span>
- [<span data-ttu-id="3e832-154">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="3e832-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3e832-155">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="3e832-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3e832-156">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="3e832-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3e832-157">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="3e832-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3e832-158">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="3e832-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
