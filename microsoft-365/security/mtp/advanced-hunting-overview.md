---
title: 概要-高度な検索
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48850c76176d79e4f90581bfbab804f4649998cc
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049634"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="fd061-104">Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する</span><span class="sxs-lookup"><span data-stu-id="fd061-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="fd061-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fd061-105">**Applies to:**</span></span>
- <span data-ttu-id="fd061-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fd061-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fd061-107">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="fd061-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="fd061-108">ネットワーク内のイベントを事前に検査して、興味深いインジケーターとエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="fd061-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="fd061-109">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対して、無制限な捜索が容易になります。</span><span class="sxs-lookup"><span data-stu-id="fd061-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="fd061-110">同じ脅威を探しているクエリを使用して、カスタムの検出ルールを構築できます。</span><span class="sxs-lookup"><span data-stu-id="fd061-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="fd061-111">これらのルールは自動的に実行され、さまざまなイベントやシステムの状態を確認して応答します。これには、違反の疑いがあるアクティビティや不適切なコンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd061-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="fd061-112">Microsoft 365 セキュリティセンターでは、高度な検索はさまざまなワークスペースからのデータになるクエリをサポートしています。これには、Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からのデバイス、メール、アプリ、id に関するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd061-112">In the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="fd061-113">高度な捜索を使用するには、[Microsoft Threat Protection を有効](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="fd061-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="fd061-114">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="fd061-114">Get started with advanced hunting</span></span>

<span data-ttu-id="fd061-115">高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd061-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="fd061-116">学習目標</span><span class="sxs-lookup"><span data-stu-id="fd061-116">Learning goal</span></span> | <span data-ttu-id="fd061-117">説明</span><span class="sxs-lookup"><span data-stu-id="fd061-117">Description</span></span> | <span data-ttu-id="fd061-118">リソース</span><span class="sxs-lookup"><span data-stu-id="fd061-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="fd061-119">**言語に慣れる**</span><span class="sxs-lookup"><span data-stu-id="fd061-119">**Get a feel for the language**</span></span> | <span data-ttu-id="fd061-120">高度な捜索は、同じ構文および演算子をサポートする [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fd061-120">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="fd061-121">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="fd061-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="fd061-122">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="fd061-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="fd061-123">**クエリ結果の使用方法について説明します。**</span><span class="sxs-lookup"><span data-stu-id="fd061-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="fd061-124">グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd061-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="fd061-125">クエリをすばやく微調整して、より豊富な情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd061-125">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="fd061-126">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="fd061-126">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="fd061-127">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="fd061-127">**Understand the schema**</span></span> | <span data-ttu-id="fd061-128">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="fd061-128">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="fd061-129">これにより、データを検索する場所およびクエリの作成方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="fd061-129">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="fd061-130">スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="fd061-130">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="fd061-131">**定義済みのクエリを活用する**</span><span class="sxs-lookup"><span data-stu-id="fd061-131">**Leverage predefined queries**</span></span> | <span data-ttu-id="fd061-132">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="fd061-132">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="fd061-133">- [共有クエリを使用する](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="fd061-133">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="fd061-134">- [ハントに移動](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="fd061-134">- [Go hunt](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="fd061-135">**クエリを最適化する**</span><span class="sxs-lookup"><span data-stu-id="fd061-135">**Optimize queries**</span></span> | <span data-ttu-id="fd061-136">効率的なクエリおよびメールとデバイスからのデータを結合するクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="fd061-136">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="fd061-137">- [クエリのベストプラクティス](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="fd061-137">- [Query best practices](advanced-hunting-shared-queries.md)</span></span> <br><span data-ttu-id="fd061-138">- [複数のデバイスとメールを探します。](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="fd061-138">- [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span> |
| <span data-ttu-id="fd061-139">**カスタム検出ルールを作成する**</span><span class="sxs-lookup"><span data-stu-id="fd061-139">**Create custom detection rules**</span></span> | <span data-ttu-id="fd061-140">高度な検索クエリを使用して、通知をトリガーし、応答アクションを自動的に適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd061-140">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="fd061-141">- [ユーザー設定の検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fd061-141">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="fd061-142">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="fd061-142">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="fd061-143">アクセス権を取得する</span><span class="sxs-lookup"><span data-stu-id="fd061-143">Get access</span></span>
<span data-ttu-id="fd061-144">高度な検索やその他の[Microsoft の脅威保護](microsoft-threat-protection.md)機能を使用するには、Azure AD で適切なロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd061-144">To use advanced hunting or other [Microsoft Threat Protection](microsoft-threat-protection.md) capabilities, you need to be assigned an appropriate role in Azure AD.</span></span> <span data-ttu-id="fd061-145">エンドポイントデータへのアクセスは、Microsoft Defender ATP のロールベースのアクセス制御の設定の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="fd061-145">Note that your access to endpoint data is influenced by role-based access control settings in Microsoft Defender ATP.</span></span> [<span data-ttu-id="fd061-146">Microsoft の脅威保護へのアクセスの管理について確認する</span><span class="sxs-lookup"><span data-stu-id="fd061-146">Read about managing access to Microsoft Threat Protection</span></span>](mtp-permissions.md)


## <a name="related-topics"></a><span data-ttu-id="fd061-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd061-147">Related topics</span></span>
- [<span data-ttu-id="fd061-148">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="fd061-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fd061-149">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="fd061-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="fd061-150">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="fd061-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fd061-151">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="fd061-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fd061-152">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="fd061-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fd061-153">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="fd061-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="fd061-154">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="fd061-154">Custom detections overview</span></span>](custom-detections-overview.md)
