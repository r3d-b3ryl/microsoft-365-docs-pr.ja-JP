---
title: 概要 - 高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: df48ec921dee7d8f3b441ed3f68ed148c5c6c857
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932979"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="0d3be-104">Microsoft 365 Defender で高度な狩猟を行って脅威を積極的に探す</span><span class="sxs-lookup"><span data-stu-id="0d3be-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0d3be-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0d3be-105">**Applies to:**</span></span>
- <span data-ttu-id="0d3be-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d3be-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="0d3be-107">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="0d3be-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="0d3be-108">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="0d3be-109">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="0d3be-110">ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="0d3be-111">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する拘束されていない検出が可能です。</span><span class="sxs-lookup"><span data-stu-id="0d3be-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="0d3be-112">同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="0d3be-113">これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の結果を確認し、それに対応します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="0d3be-114">この機能は [、Microsoft Defender for Endpoint の高度な検索に似ています](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="0d3be-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="0d3be-115">Microsoft 365 セキュリティ センターで使用できるこの機能は、以下のより広範なデータ セットをチェックするクエリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0d3be-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="0d3be-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0d3be-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="0d3be-117">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0d3be-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="0d3be-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0d3be-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="0d3be-119">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0d3be-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="0d3be-120">高度な検索を使用するには [、Microsoft 365 Defender をオンにしてください](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="0d3be-120">To use advanced hunting, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="0d3be-121">開始する前に</span><span class="sxs-lookup"><span data-stu-id="0d3be-121">Before you begin</span></span>

<span data-ttu-id="0d3be-122">ユーザーが Microsoft Defender にアクセスするには、次のいずれかのレベルのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d3be-122">Users need one of the following levels of permissions to access Microsoft Defender:</span></span>

- <span data-ttu-id="0d3be-123">フル アクセス (読み取りおよび書き込み)</span><span class="sxs-lookup"><span data-stu-id="0d3be-123">Full access (read and write)</span></span>
- <span data-ttu-id="0d3be-124">読み取り専用アクセス</span><span class="sxs-lookup"><span data-stu-id="0d3be-124">Read-only access</span></span>

<span data-ttu-id="0d3be-125">**フル アクセス**: フル アクセスを持つユーザーは、クエリを保存、変更、および共有できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-125">**Full access**: Users with full access can save, modify, and share a query.</span></span> <span data-ttu-id="0d3be-126">フル アクセス権を割り当てるには、Azure Active Directory (AAD) の "セキュリティ管理者" または "グローバル管理者" 組み込みの役割にユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d3be-126">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" built-in roles in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="0d3be-127">**読み取り専用アクセス**: 読み取り専用アクセス権を持つユーザーは、ログインしてすべてのアラートと関連情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-127">**Read-only access**: Users with read-only access can log in and view all alerts and related information.</span></span> <span data-ttu-id="0d3be-128">クエリを保存、変更、または共有できない。</span><span class="sxs-lookup"><span data-stu-id="0d3be-128">They will not be able to save, modify, or share a query.</span></span> <span data-ttu-id="0d3be-129">読み取り専用アクセス権を割り当てるには、AAD の "Security Reader" 組み込みロールにユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d3be-129">Assigning read-only access rights requires adding the users to the "Security Reader" built-in role in AAD.</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="0d3be-130">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="0d3be-130">Get started with advanced hunting</span></span>

<span data-ttu-id="0d3be-131">高度な検索をすぐに開始するには、いくつかの手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d3be-131">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="0d3be-132">学習目標</span><span class="sxs-lookup"><span data-stu-id="0d3be-132">Learning goal</span></span> | <span data-ttu-id="0d3be-133">説明</span><span class="sxs-lookup"><span data-stu-id="0d3be-133">Description</span></span> | <span data-ttu-id="0d3be-134">リソース</span><span class="sxs-lookup"><span data-stu-id="0d3be-134">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="0d3be-135">**言語を学ぶ**</span><span class="sxs-lookup"><span data-stu-id="0d3be-135">**Learn the language**</span></span> | <span data-ttu-id="0d3be-136">高度な検索は [、同じ構文と](/azure/kusto/query/)演算子をサポートする Kusto クエリ言語に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="0d3be-136">Advanced hunting is based on [Kusto query language](/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="0d3be-137">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-137">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="0d3be-138">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="0d3be-138">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="0d3be-139">**クエリ結果を使用する方法について**</span><span class="sxs-lookup"><span data-stu-id="0d3be-139">**Learn how to use the query results**</span></span> | <span data-ttu-id="0d3be-140">グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-140">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="0d3be-141">クエリをすばやく調整し、詳細な情報を取得するためにドリルダウンし、応答アクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-141">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="0d3be-142">- [クエリ結果の処理](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-142">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="0d3be-143">- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-143">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="0d3be-144">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="0d3be-144">**Understand the schema**</span></span> | <span data-ttu-id="0d3be-145">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="0d3be-145">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="0d3be-146">クエリを作成するときにデータを検索する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-146">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="0d3be-147">- [スキーマ参照](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-147">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="0d3be-148">- [Microsoft Defender for Endpoint からの移行](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-148">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)</span></span> |
| <span data-ttu-id="0d3be-149">**エキスパートのヒントと例を取得する**</span><span class="sxs-lookup"><span data-stu-id="0d3be-149">**Get expert tips and examples**</span></span> | <span data-ttu-id="0d3be-150">Microsoft の専門家からのガイドを使用して無料でトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="0d3be-150">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="0d3be-151">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-151">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="0d3be-152">- [専門家のトレーニングを受け取る](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-152">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="0d3be-153">- [共有クエリの使用](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-153">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="0d3be-154">- [Go hunt](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-154">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="0d3be-155">- [デバイス、電子メール、アプリ、および ID 間の脅威を検出する](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-155">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="0d3be-156">**クエリを最適化し、エラーを処理する**</span><span class="sxs-lookup"><span data-stu-id="0d3be-156">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="0d3be-157">効率的でエラーフリーのクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-157">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="0d3be-158">- [クエリのベスト プラクティス](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-158">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="0d3be-159">- [エラーの処理](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-159">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="0d3be-160">**検出ルールの作成**</span><span class="sxs-lookup"><span data-stu-id="0d3be-160">**Create custom detection rules**</span></span> | <span data-ttu-id="0d3be-161">高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-161">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="0d3be-162">- [カスタム検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-162">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="0d3be-163">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="0d3be-163">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="0d3be-164">アクセス権の取得</span><span class="sxs-lookup"><span data-stu-id="0d3be-164">Get access</span></span>
<span data-ttu-id="0d3be-165">高度なハンティングまたは他の [Microsoft 365 Defender](microsoft-365-defender.md) 機能を使用するには、Azure Active Directory で適切な役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d3be-165">To use advanced hunting or other [Microsoft 365 Defender](microsoft-365-defender.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="0d3be-166">また、エンドポイント データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) 設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="0d3be-166">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="0d3be-167">Microsoft 365 Defender へのアクセスの管理について</span><span class="sxs-lookup"><span data-stu-id="0d3be-167">Read about managing access to Microsoft 365 Defender</span></span>](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="0d3be-168">データの鮮度と更新頻度</span><span class="sxs-lookup"><span data-stu-id="0d3be-168">Data freshness and update frequency</span></span>
<span data-ttu-id="0d3be-169">高度な狩猟データは、それぞれ異なる方法で統合された 2 つの異なる種類に分類できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-169">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="0d3be-170">**イベントまたはアクティビティ データ**— アラート、セキュリティ イベント、システム イベント、および定期的な評価に関するテーブルを設定します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-170">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="0d3be-171">高度な検出は、センサーを収集したセンサーが対応するクラウド サービスに正常に送信した直後に、このデータを受信します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-171">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="0d3be-172">たとえば、ワークステーションまたはドメイン コントローラー上の正常なセンサーのイベント データは、Microsoft Defender for Endpoint および Microsoft Defender for Identity で使用できる直後にクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-172">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="0d3be-173">**エンティティ データ**— ユーザーとデバイスに関する情報を表に設定します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-173">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="0d3be-174">このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-174">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="0d3be-175">新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されない可能性のある行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-175">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="0d3be-176">24 時間ごとにデータが統合され、各エンティティに関する最新の最も包括的なデータ セットを含むレコードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-176">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="0d3be-177">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="0d3be-177">Time zone</span></span>
<span data-ttu-id="0d3be-178">高度な検索の時間情報は、UTC タイム ゾーンにあります。</span><span class="sxs-lookup"><span data-stu-id="0d3be-178">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d3be-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d3be-179">Related topics</span></span>
- [<span data-ttu-id="0d3be-180">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="0d3be-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0d3be-181">エキスパート トレーニングを受ける</span><span class="sxs-lookup"><span data-stu-id="0d3be-181">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="0d3be-182">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="0d3be-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0d3be-183">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="0d3be-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0d3be-184">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="0d3be-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0d3be-185">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="0d3be-185">Custom detections overview</span></span>](custom-detections-overview.md)
