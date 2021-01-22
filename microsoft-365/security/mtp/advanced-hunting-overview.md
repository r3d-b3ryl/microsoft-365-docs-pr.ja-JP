---
title: 概要 - 高度な検索
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、kusto、Microsoft 365、Microsoft Threat Protection
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932276"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="42cd1-104">Microsoft 365 Defender で高度な検索を使用して脅威を事前に探す</span><span class="sxs-lookup"><span data-stu-id="42cd1-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="42cd1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="42cd1-105">**Applies to:**</span></span>
- <span data-ttu-id="42cd1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42cd1-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="42cd1-107">Microsoft 365 Defender を体験したい場合</span><span class="sxs-lookup"><span data-stu-id="42cd1-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="42cd1-108">ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="42cd1-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="42cd1-109">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="42cd1-110">ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="42cd1-111">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する無条件の検出が可能です。</span><span class="sxs-lookup"><span data-stu-id="42cd1-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="42cd1-112">同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="42cd1-113">これらのルールは自動的に実行され、違反の疑いのあるアクティビティ、正しく構成されていないコンピューター、その他の検出に対応します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="42cd1-114">この機能は、エンドポイント用 [Microsoft Defender の高度な検索に似ています](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="42cd1-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="42cd1-115">Microsoft 365 セキュリティ センターで使用できるこの機能は、次の広範なデータ セットをチェックするクエリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="42cd1-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="42cd1-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42cd1-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="42cd1-117">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="42cd1-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="42cd1-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="42cd1-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="42cd1-119">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="42cd1-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="42cd1-120">高度なハンティングを使用するには [、Microsoft 365 Defender を有効にしてください](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="42cd1-120">To use advanced hunting, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="42cd1-121">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="42cd1-121">Get started with advanced hunting</span></span>

<span data-ttu-id="42cd1-122">高度な検索をすぐに開始するには、いくつかの手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="42cd1-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="42cd1-123">学習目標</span><span class="sxs-lookup"><span data-stu-id="42cd1-123">Learning goal</span></span> | <span data-ttu-id="42cd1-124">説明</span><span class="sxs-lookup"><span data-stu-id="42cd1-124">Description</span></span> | <span data-ttu-id="42cd1-125">リソース</span><span class="sxs-lookup"><span data-stu-id="42cd1-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="42cd1-126">**言語を学ぶ**</span><span class="sxs-lookup"><span data-stu-id="42cd1-126">**Learn the language**</span></span> | <span data-ttu-id="42cd1-127">高度な検索は [Kusto クエリ言語に基づいており](https://docs.microsoft.com/azure/kusto/query/)、同じ構文と演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="42cd1-127">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="42cd1-128">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="42cd1-129">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="42cd1-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="42cd1-130">**クエリ結果を使用する方法について**</span><span class="sxs-lookup"><span data-stu-id="42cd1-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="42cd1-131">グラフと、結果を表示またはエクスポートするさまざまな方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="42cd1-132">クエリをすばやく調整し、ドリルダウンしてより豊富な情報を取得し、対応アクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="42cd1-133">- [クエリ結果を処理する](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="42cd1-134">- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="42cd1-135">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="42cd1-135">**Understand the schema**</span></span> | <span data-ttu-id="42cd1-136">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="42cd1-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="42cd1-137">クエリを作成するときにデータを検索する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="42cd1-138">- [スキーマ リファレンス](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="42cd1-139">- [Microsoft Defender for Endpoint からの移行](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="42cd1-140">**エキスパートのヒントと例を取得する**</span><span class="sxs-lookup"><span data-stu-id="42cd1-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="42cd1-141">Microsoft の専門家によるガイドを使用して無料でトレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="42cd1-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="42cd1-142">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="42cd1-143">- [エキスパート トレーニングを受け取る](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="42cd1-144">- [共有クエリを使用する](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="42cd1-145">- [ハントを行う](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="42cd1-146">- [デバイス、メール、アプリ、ID 間で脅威を検出する](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="42cd1-147">**クエリを最適化し、エラーを処理する**</span><span class="sxs-lookup"><span data-stu-id="42cd1-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="42cd1-148">効率的でエラーが発生していないクエリを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="42cd1-149">- [クエリのベスト プラクティス](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="42cd1-150">- [エラーの処理](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="42cd1-151">**検出ルールの作成**</span><span class="sxs-lookup"><span data-stu-id="42cd1-151">**Create custom detection rules**</span></span> | <span data-ttu-id="42cd1-152">高度な検索クエリを使用してアラートをトリガーし、応答アクションを自動的に実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="42cd1-153">- [カスタム検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="42cd1-154">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="42cd1-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="42cd1-155">アクセス権を取得する</span><span class="sxs-lookup"><span data-stu-id="42cd1-155">Get access</span></span>
<span data-ttu-id="42cd1-156">高度な検索機能または他の [Microsoft 365 Defender](microsoft-threat-protection.md) 機能を使用するには、Azure Active Directory で適切な役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="42cd1-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="42cd1-157">また、エンドポイント データへのアクセスは、Microsoft Defender for Endpoint の役割ベースのアクセス制御 (RBAC) 設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="42cd1-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="42cd1-158">Microsoft 365 Defender へのアクセスの管理に関する説明</span><span class="sxs-lookup"><span data-stu-id="42cd1-158">Read about managing access to Microsoft 365 Defender</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="42cd1-159">データの鮮度と更新頻度</span><span class="sxs-lookup"><span data-stu-id="42cd1-159">Data freshness and update frequency</span></span>
<span data-ttu-id="42cd1-160">高度なハンティング データは 2 つの異なる種類に分類できます。それぞれの種類は統合方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="42cd1-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="42cd1-161">**イベントまたはアクティビティ データ**— アラート、セキュリティ イベント、システム イベント、および定期的な評価に関するテーブルを設定します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="42cd1-162">高度な検索では、収集したセンサーがデータを正常に対応するクラウド サービスに送信した直後に、このデータを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="42cd1-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="42cd1-163">たとえば、ワークステーションまたはドメイン コントローラーで正常なセンサーから得たイベント データは、Microsoft Defender for Endpoint と Microsoft Defender for Identity で利用できる直後に照会できます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="42cd1-164">**エンティティ データ**— ユーザーとデバイスに関する情報をテーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="42cd1-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="42cd1-165">このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的ソースの両方から取得されます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="42cd1-166">新しいデータを提供するために、テーブルは 15 分ごとに新しい情報で更新され、完全に入力されていない可能性がある行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="42cd1-167">24 時間ごとにデータが統合され、各エンティティに関する最新の包括的なデータ セットを含むレコードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="42cd1-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="42cd1-168">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="42cd1-168">Time zone</span></span>
<span data-ttu-id="42cd1-169">高度な検索の時間情報は、UTC タイム ゾーンにあります。</span><span class="sxs-lookup"><span data-stu-id="42cd1-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="42cd1-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="42cd1-170">Related topics</span></span>
- [<span data-ttu-id="42cd1-171">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="42cd1-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="42cd1-172">エキスパート トレーニングを受ける</span><span class="sxs-lookup"><span data-stu-id="42cd1-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="42cd1-173">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="42cd1-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="42cd1-174">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="42cd1-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="42cd1-175">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="42cd1-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="42cd1-176">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="42cd1-176">Custom detections overview</span></span>](custom-detections-overview.md)

