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
ms.openlocfilehash: dc91b97f48d6a5ca76c405e4c1006dceb9dc0b34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929030"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="58dc1-104">Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する</span><span class="sxs-lookup"><span data-stu-id="58dc1-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="58dc1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="58dc1-105">**Applies to:**</span></span>
- <span data-ttu-id="58dc1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="58dc1-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="58dc1-107">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="58dc1-108">ネットワーク内のイベントを事前に検査して、興味深いインジケーターとエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="58dc1-109">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対して、無制限な捜索が容易になります。</span><span class="sxs-lookup"><span data-stu-id="58dc1-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="58dc1-110">同じ脅威を探しているクエリを使用して、カスタムの検出ルールを構築できます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="58dc1-111">これらのルールは自動的に実行され、さまざまなイベントやシステムの状態を確認して応答します。これには、違反の疑いがあるアクティビティや不適切なコンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="58dc1-112">Microsoft 365 セキュリティセンターでは、高度な検索では、さまざまなワークスペースからデータを参照するクエリをサポートしています。これには、Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure からのデバイス、メール、アプリ、id に関するデータが含まれます。ツール.</span><span class="sxs-lookup"><span data-stu-id="58dc1-112">In the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="58dc1-113">高度な捜索を使用するには、[Microsoft Threat Protection を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="58dc1-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="58dc1-114">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="58dc1-114">Get started with advanced hunting</span></span>

<span data-ttu-id="58dc1-115">高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58dc1-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="58dc1-116">学習目標</span><span class="sxs-lookup"><span data-stu-id="58dc1-116">Learning goal</span></span> | <span data-ttu-id="58dc1-117">説明</span><span class="sxs-lookup"><span data-stu-id="58dc1-117">Description</span></span> | <span data-ttu-id="58dc1-118">リソース</span><span class="sxs-lookup"><span data-stu-id="58dc1-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="58dc1-119">**言語に慣れる**</span><span class="sxs-lookup"><span data-stu-id="58dc1-119">**Get a feel for the language**</span></span> | <span data-ttu-id="58dc1-120">高度な捜索は、同じ構文および演算子をサポートする [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="58dc1-120">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="58dc1-121">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="58dc1-122">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="58dc1-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="58dc1-123">**クエリ結果の使用方法について説明します。**</span><span class="sxs-lookup"><span data-stu-id="58dc1-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="58dc1-124">グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="58dc1-125">クエリをすばやく微調整して、より豊富な情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-125">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="58dc1-126">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="58dc1-126">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="58dc1-127">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="58dc1-127">**Understand the schema**</span></span> | <span data-ttu-id="58dc1-128">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="58dc1-128">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="58dc1-129">これにより、データを検索する場所およびクエリの作成方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-129">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="58dc1-130">スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="58dc1-130">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="58dc1-131">**定義済みのクエリを活用する**</span><span class="sxs-lookup"><span data-stu-id="58dc1-131">**Leverage predefined queries**</span></span> | <span data-ttu-id="58dc1-132">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-132">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="58dc1-133">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="58dc1-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="58dc1-134">**クエリを最適化する**</span><span class="sxs-lookup"><span data-stu-id="58dc1-134">**Optimize queries**</span></span> | <span data-ttu-id="58dc1-135">効率的なクエリおよびメールとデバイスからのデータを結合するクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-135">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="58dc1-136">- [クエリのベストプラクティス](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="58dc1-136">- [Query best practices](advanced-hunting-shared-queries.md)</span></span> <br><span data-ttu-id="58dc1-137">- [複数のデバイスとメールを探します。](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="58dc1-137">- [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span> |
| <span data-ttu-id="58dc1-138">**カスタム検出ルールを作成する**</span><span class="sxs-lookup"><span data-stu-id="58dc1-138">**Create custom detection rules**</span></span> | <span data-ttu-id="58dc1-139">高度な検索クエリを使用して、通知をトリガーし、応答アクションを自動的に適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-139">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="58dc1-140">- [ユーザー設定の検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="58dc1-140">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="58dc1-141">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="58dc1-141">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="58dc1-142">クエリを記述するときにヘルプを参照する</span><span class="sxs-lookup"><span data-stu-id="58dc1-142">Get help as you write queries</span></span>
<span data-ttu-id="58dc1-143">次の機能を利用して、クエリをより速く記述します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-143">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="58dc1-144">**Autosuggest** : クエリを作成すると、高度な検索によって IntelliSense から候補が表示されます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-144">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="58dc1-145">**スキーマ リファレンス** — テーブルとその列のリストを含むスキーマ リファレンスが作業領域の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="58dc1-145">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="58dc1-146">詳細については、アイテムにカーソルを合わせてください。</span><span class="sxs-lookup"><span data-stu-id="58dc1-146">For more information, hover over an item.</span></span> <span data-ttu-id="58dc1-147">アイテムをダブルクリックして、クエリ エディターに挿入します。</span><span class="sxs-lookup"><span data-stu-id="58dc1-147">Double-click an item to insert it to the query editor.</span></span>


## <a name="related-topics"></a><span data-ttu-id="58dc1-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="58dc1-148">Related topics</span></span>
- [<span data-ttu-id="58dc1-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="58dc1-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="58dc1-150">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="58dc1-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="58dc1-151">共有クエリを使う</span><span class="sxs-lookup"><span data-stu-id="58dc1-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="58dc1-152">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="58dc1-152">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="58dc1-153">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="58dc1-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="58dc1-154">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="58dc1-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="58dc1-155">ユーザー設定の検出の概要</span><span class="sxs-lookup"><span data-stu-id="58dc1-155">Custom detections overview</span></span>](custom-detections-overview.md)