---
title: 概要 - 高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、microsoft 365、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 0338e87c103bef0f12a45277a14152ef429d0067
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068308"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="da310-104">Microsoft 365 Defender で高度な狩猟を行って脅威を積極的に探す</span><span class="sxs-lookup"><span data-stu-id="da310-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="da310-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="da310-105">**Applies to:**</span></span>
- <span data-ttu-id="da310-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da310-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="da310-107">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="da310-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="da310-108">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="da310-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="da310-109">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="da310-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="da310-110">ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。</span><span class="sxs-lookup"><span data-stu-id="da310-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="da310-111">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する拘束されていない検出が可能です。</span><span class="sxs-lookup"><span data-stu-id="da310-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="da310-112">同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="da310-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="da310-113">これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の結果を確認し、それに対応します。</span><span class="sxs-lookup"><span data-stu-id="da310-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="da310-114">この機能は [、Microsoft Defender for Endpoint の高度な検索に似ています](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="da310-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="da310-115">Microsoft 365 セキュリティ センターで使用できるこの機能は、以下のより広範なデータ セットをチェックするクエリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="da310-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="da310-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da310-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="da310-117">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="da310-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="da310-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="da310-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="da310-119">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="da310-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="da310-120">高度な検索を使用するには [、Microsoft 365 Defender をオンにしてください](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="da310-120">To use advanced hunting, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="da310-121">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="da310-121">Get started with advanced hunting</span></span>

<span data-ttu-id="da310-122">高度な検索をすぐに開始するには、いくつかの手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da310-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="da310-123">学習目標</span><span class="sxs-lookup"><span data-stu-id="da310-123">Learning goal</span></span> | <span data-ttu-id="da310-124">説明</span><span class="sxs-lookup"><span data-stu-id="da310-124">Description</span></span> | <span data-ttu-id="da310-125">リソース</span><span class="sxs-lookup"><span data-stu-id="da310-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="da310-126">**言語を学ぶ**</span><span class="sxs-lookup"><span data-stu-id="da310-126">**Learn the language**</span></span> | <span data-ttu-id="da310-127">高度な検索は [、同じ構文と](/azure/kusto/query/)演算子をサポートする Kusto クエリ言語に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="da310-127">Advanced hunting is based on [Kusto query language](/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="da310-128">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="da310-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="da310-129">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="da310-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="da310-130">**クエリ結果を使用する方法について**</span><span class="sxs-lookup"><span data-stu-id="da310-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="da310-131">グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="da310-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="da310-132">クエリをすばやく調整し、詳細な情報を取得するためにドリルダウンし、応答アクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da310-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="da310-133">- [クエリ結果の処理](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="da310-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="da310-134">- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="da310-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="da310-135">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="da310-135">**Understand the schema**</span></span> | <span data-ttu-id="da310-136">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="da310-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="da310-137">クエリを作成するときにデータを検索する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="da310-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="da310-138">- [スキーマ参照](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="da310-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="da310-139">- [Microsoft Defender for Endpoint からの移行](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="da310-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)</span></span> |
| <span data-ttu-id="da310-140">**エキスパートのヒントと例を取得する**</span><span class="sxs-lookup"><span data-stu-id="da310-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="da310-141">Microsoft の専門家からのガイドを使用して無料でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="da310-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="da310-142">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="da310-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="da310-143">- [専門家のトレーニングを受け取る](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="da310-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="da310-144">- [共有クエリの使用](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="da310-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="da310-145">- [Go hunt](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="da310-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="da310-146">- [デバイス、電子メール、アプリ、および ID 間の脅威を検出する](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="da310-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="da310-147">**クエリを最適化し、エラーを処理する**</span><span class="sxs-lookup"><span data-stu-id="da310-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="da310-148">効率的でエラーフリーのクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="da310-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="da310-149">- [クエリのベスト プラクティス](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="da310-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="da310-150">- [エラーの処理](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="da310-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="da310-151">**検出ルールの作成**</span><span class="sxs-lookup"><span data-stu-id="da310-151">**Create custom detection rules**</span></span> | <span data-ttu-id="da310-152">高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da310-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="da310-153">- [カスタム検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="da310-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="da310-154">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="da310-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="da310-155">アクセス権の取得</span><span class="sxs-lookup"><span data-stu-id="da310-155">Get access</span></span>
<span data-ttu-id="da310-156">高度なハンティングまたは他の [Microsoft 365 Defender](microsoft-365-defender.md) 機能を使用するには、Azure Active Directory で適切な役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="da310-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-365-defender.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="da310-157">また、エンドポイント データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) 設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="da310-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="da310-158">Microsoft 365 Defender へのアクセスの管理について</span><span class="sxs-lookup"><span data-stu-id="da310-158">Read about managing access to Microsoft 365 Defender</span></span>](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="da310-159">データの鮮度と更新頻度</span><span class="sxs-lookup"><span data-stu-id="da310-159">Data freshness and update frequency</span></span>
<span data-ttu-id="da310-160">高度な狩猟データは、それぞれ異なる方法で統合された 2 つの異なる種類に分類できます。</span><span class="sxs-lookup"><span data-stu-id="da310-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="da310-161">**イベントまたはアクティビティ データ**— アラート、セキュリティ イベント、システム イベント、および定期的な評価に関するテーブルを設定します。</span><span class="sxs-lookup"><span data-stu-id="da310-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="da310-162">高度な検出は、センサーを収集したセンサーが対応するクラウド サービスに正常に送信した直後に、このデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="da310-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="da310-163">たとえば、ワークステーションまたはドメイン コントローラー上の正常なセンサーのイベント データは、Microsoft Defender for Endpoint および Microsoft Defender for Identity で使用できる直後にクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="da310-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="da310-164">**エンティティ データ**— ユーザーとデバイスに関する情報を表に設定します。</span><span class="sxs-lookup"><span data-stu-id="da310-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="da310-165">このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。</span><span class="sxs-lookup"><span data-stu-id="da310-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="da310-166">新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されない可能性のある行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="da310-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="da310-167">24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="da310-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="da310-168">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="da310-168">Time zone</span></span>
<span data-ttu-id="da310-169">高度な検索の時間情報は、UTC タイム ゾーンにあります。</span><span class="sxs-lookup"><span data-stu-id="da310-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da310-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="da310-170">Related topics</span></span>
- [<span data-ttu-id="da310-171">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="da310-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="da310-172">エキスパート トレーニングを受ける</span><span class="sxs-lookup"><span data-stu-id="da310-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="da310-173">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="da310-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="da310-174">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="da310-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="da310-175">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="da310-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="da310-176">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="da310-176">Custom detections overview</span></span>](custom-detections-overview.md)