---
title: エンドポイント向け Microsoft Defender での高度な検索の概要
description: Microsoft Defender for Endpoint の脅威検出機能を使用して、ネットワーク内の脅威と弱点を検出するクエリを作成する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、エンドポイント用 Microsoft Defender、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、タイム ゾーン、UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 114c0192f77411016fcb13ec2b912f4440ffa6e0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934359"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a><span data-ttu-id="2ea5d-104">高度な狩猟で脅威を積極的に探す</span><span class="sxs-lookup"><span data-stu-id="2ea5d-104">Proactively hunt for threats with advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ea5d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ea5d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ea5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="2ea5d-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="2ea5d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ea5d-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="2ea5d-109">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="2ea5d-110">ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="2ea5d-111">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する拘束されていない検出が可能です。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="2ea5d-112">このビデオでは、高度な狩猟の簡単な概要と、迅速に始める短いチュートリアルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-112">Watch this video for a quick overview of advanced hunting and a short tutorial that will get you started fast.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

<span data-ttu-id="2ea5d-113">同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-113">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="2ea5d-114">これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の結果を確認し、それに対応します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-114">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

>[!TIP]
><span data-ttu-id="2ea5d-115">[Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview)の高度な検索を使用して、Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity のデータを使用して脅威を探します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-115">Use [advanced hunting in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="2ea5d-116">[Microsoft 365 Defender を有効にする](/microsoft-365/security/defender/m365d-enable)。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-116">[Turn on Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).</span></span><br><br>
<span data-ttu-id="2ea5d-117">高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defender に移動する方法については、「Advanced Hunting [queries](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)を Microsoft Defender for Endpoint から移行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-117">Learn more about how to move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="2ea5d-118">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="2ea5d-118">Get started with advanced hunting</span></span>

<span data-ttu-id="2ea5d-119">高度な狩猟の知識を高くするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-119">Go through the following steps to ramp up your advanced hunting knowledge.</span></span>

<span data-ttu-id="2ea5d-120">高度な捜索をすぐに開始して実行するには、いくつかの手順に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-120">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="2ea5d-121">学習目標</span><span class="sxs-lookup"><span data-stu-id="2ea5d-121">Learning goal</span></span> | <span data-ttu-id="2ea5d-122">説明</span><span class="sxs-lookup"><span data-stu-id="2ea5d-122">Description</span></span> | <span data-ttu-id="2ea5d-123">リソース</span><span class="sxs-lookup"><span data-stu-id="2ea5d-123">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="2ea5d-124">**言語を学ぶ**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-124">**Learn the language**</span></span> | <span data-ttu-id="2ea5d-125">高度な検索は [、同じ構文と](https://docs.microsoft.com/azure/kusto/query/)演算子をサポートする Kusto クエリ言語に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-125">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="2ea5d-126">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-126">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="2ea5d-127">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="2ea5d-127">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="2ea5d-128">**クエリ結果を使用する方法について**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-128">**Learn how to use the query results**</span></span> | <span data-ttu-id="2ea5d-129">グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-129">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="2ea5d-130">クエリをすばやく調整し、詳細な情報を取得するためにドリルダウンする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-130">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="2ea5d-131">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="2ea5d-131">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="2ea5d-132">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-132">**Understand the schema**</span></span> | <span data-ttu-id="2ea5d-133">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-133">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="2ea5d-134">クエリを作成するときにデータを検索する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-134">Learn where to look for data when constructing your queries.</span></span> | [<span data-ttu-id="2ea5d-135">スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="2ea5d-135">Schema reference</span></span>](advanced-hunting-schema-reference.md) |
| <span data-ttu-id="2ea5d-136">**定義済みクエリを使用する**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-136">**Use predefined queries**</span></span> | <span data-ttu-id="2ea5d-137">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-137">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="2ea5d-138">共有クエリ</span><span class="sxs-lookup"><span data-stu-id="2ea5d-138">Shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="2ea5d-139">**クエリを最適化し、エラーを処理する**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-139">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="2ea5d-140">効率的でエラーフリーのクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-140">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="2ea5d-141">- [クエリのベスト プラクティス](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-141">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="2ea5d-142">- [エラーの処理](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-142">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="2ea5d-143">**最も完全なカバレッジを取得する**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-143">**Get the most complete coverage**</span></span> | <span data-ttu-id="2ea5d-144">監査設定を使用して、組織のデータ範囲を向上します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-144">Use audit settings to provide better data coverage for your organization.</span></span> | <span data-ttu-id="2ea5d-145">- [高度な狩猟範囲の拡張](advanced-hunting-extend-data.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-145">- [Extend advanced hunting coverage](advanced-hunting-extend-data.md)</span></span> |
| <span data-ttu-id="2ea5d-146">**クイック調査の実行**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-146">**Run a quick investigation**</span></span> | <span data-ttu-id="2ea5d-147">高度な検索クエリをすばやく実行して、疑わしいアクティビティを調査します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-147">Quickly run an advanced hunting query to investigate suspicious activity.</span></span> | <span data-ttu-id="2ea5d-148">- [go hunt を使用してエンティティまたはイベント情報をすばやく *検索する*](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-148">- [Quickly hunt for entity or event information with *go hunt*](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="2ea5d-149">**脅威を含め、侵害に対処する**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-149">**Contain threats and address compromises**</span></span> | <span data-ttu-id="2ea5d-150">ファイルの quarantining、アプリの実行の制限、その他のアクションによる攻撃への対応</span><span class="sxs-lookup"><span data-stu-id="2ea5d-150">Respond to attacks by quarantining files, restricting app execution, and other actions</span></span> | <span data-ttu-id="2ea5d-151">- [高度な検索クエリの結果に対してアクションを実行する](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-151">- [Take action on advanced hunting query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="2ea5d-152">**検出ルールの作成**</span><span class="sxs-lookup"><span data-stu-id="2ea5d-152">**Create custom detection rules**</span></span> | <span data-ttu-id="2ea5d-153">高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-153">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="2ea5d-154">- [カスタム検出の概要](overview-custom-detections.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-154">- [Custom detections overview](overview-custom-detections.md)</span></span><br><span data-ttu-id="2ea5d-155">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="2ea5d-155">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="2ea5d-156">データの鮮度と更新頻度</span><span class="sxs-lookup"><span data-stu-id="2ea5d-156">Data freshness and update frequency</span></span>

<span data-ttu-id="2ea5d-157">高度な狩猟データは、それぞれ異なる方法で統合された 2 つの異なる種類に分類できます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-157">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="2ea5d-158">**イベントまたはアクティビティ データ**— アラート、セキュリティ イベント、システム イベント、および定期的な評価に関するテーブルを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-158">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="2ea5d-159">高度な検出は、センサーを収集したセンサーが Defender for Endpoint に正常に送信した直後に、このデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-159">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to Defender for Endpoint.</span></span>
- <span data-ttu-id="2ea5d-160">**エンティティ データ**— ユーザーとデバイスに関する統合された情報を表に設定します。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-160">**Entity data**—populates tables with consolidated information about users and devices.</span></span> <span data-ttu-id="2ea5d-161">このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-161">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="2ea5d-162">新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されない可能性のある行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-162">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="2ea5d-163">24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-163">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="2ea5d-164">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="2ea5d-164">Time zone</span></span>

<span data-ttu-id="2ea5d-165">高度な検索の時間情報は現在、UTC タイム ゾーンにあります。</span><span class="sxs-lookup"><span data-stu-id="2ea5d-165">Time information in advanced hunting is currently in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ea5d-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ea5d-166">Related topics</span></span>

- [<span data-ttu-id="2ea5d-167">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="2ea5d-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2ea5d-168">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="2ea5d-168">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2ea5d-169">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2ea5d-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2ea5d-170">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2ea5d-170">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="2ea5d-171">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="2ea5d-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2ea5d-172">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="2ea5d-172">Custom detections overview</span></span>](overview-custom-detections.md)
