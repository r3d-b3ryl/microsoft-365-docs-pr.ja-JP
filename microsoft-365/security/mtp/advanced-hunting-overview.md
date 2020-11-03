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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 627791e9dc3d4bf18047a05734a4e275152d19da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845034"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="248db-104">Microsoft 365 Defender での高度な検索を使用して、積極的に脅威を探します。</span><span class="sxs-lookup"><span data-stu-id="248db-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="248db-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="248db-105">**Applies to:**</span></span>
- <span data-ttu-id="248db-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="248db-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="248db-107">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="248db-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="248db-108">ネットワーク内のイベントを事前に検査して、脅威の指標とエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="248db-108">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="248db-109">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威を無制限に探すことができます。</span><span class="sxs-lookup"><span data-stu-id="248db-109">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="248db-110">同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="248db-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="248db-111">これらのルールは自動的に実行され、疑わしい違反活動、不適切な構成のコンピューター、およびその他の結果をチェックして応答します。</span><span class="sxs-lookup"><span data-stu-id="248db-111">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="248db-112">この機能は、 [エンドポイントの Microsoft Defender での高度な](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)検索に似ています。</span><span class="sxs-lookup"><span data-stu-id="248db-112">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="248db-113">Microsoft 365 セキュリティセンターで利用可能です。この機能により、次のような幅広いデータセットをチェックするクエリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="248db-113">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="248db-114">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="248db-114">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="248db-115">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="248db-115">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="248db-116">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="248db-116">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="248db-117">Id の Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="248db-117">Microsoft Defender for Identity</span></span>

<span data-ttu-id="248db-118">高度な検索を使用するには、 [Microsoft 365 Defender をオン](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="248db-118">To use advanced hunting, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="248db-119">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="248db-119">Get started with advanced hunting</span></span>

<span data-ttu-id="248db-120">高度な検索をすばやく始めるには、いくつかの手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="248db-120">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="248db-121">学習目標</span><span class="sxs-lookup"><span data-stu-id="248db-121">Learning goal</span></span> | <span data-ttu-id="248db-122">説明</span><span class="sxs-lookup"><span data-stu-id="248db-122">Description</span></span> | <span data-ttu-id="248db-123">リソース</span><span class="sxs-lookup"><span data-stu-id="248db-123">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="248db-124">**言語について**</span><span class="sxs-lookup"><span data-stu-id="248db-124">**Learn the language**</span></span> | <span data-ttu-id="248db-125">高度な検索は、 [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいており、同じ構文および演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="248db-125">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="248db-126">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="248db-126">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="248db-127">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="248db-127">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="248db-128">**クエリ結果の使用方法について説明します。**</span><span class="sxs-lookup"><span data-stu-id="248db-128">**Learn how to use the query results**</span></span> | <span data-ttu-id="248db-129">グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="248db-129">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="248db-130">クエリをすばやく調整する方法、豊富な情報を取得するためのドリルダウン、および応答アクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="248db-130">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="248db-131">- [クエリ結果を操作する](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="248db-131">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="248db-132">- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="248db-132">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="248db-133">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="248db-133">**Understand the schema**</span></span> | <span data-ttu-id="248db-134">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="248db-134">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="248db-135">クエリを作成するときにデータを検索する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="248db-135">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="248db-136">- [スキーマリファレンス](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="248db-136">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="248db-137">- [エンドポイントの Microsoft Defender からの移行](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="248db-137">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="248db-138">**エキスパートのヒントと例を取得する**</span><span class="sxs-lookup"><span data-stu-id="248db-138">**Get expert tips and examples**</span></span> | <span data-ttu-id="248db-139">Microsoft の専門家のガイドを使用して無料でトレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="248db-139">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="248db-140">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="248db-140">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="248db-141">- [エキスパートトレーニングを受ける](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="248db-141">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="248db-142">- [共有クエリを使用する](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="248db-142">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="248db-143">- [ハントに移動](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="248db-143">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="248db-144">- [デバイス、メール、アプリ、および id 間の脅威を探します。](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="248db-144">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="248db-145">**クエリを最適化してエラーを処理する**</span><span class="sxs-lookup"><span data-stu-id="248db-145">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="248db-146">効率的でエラーのないクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="248db-146">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="248db-147">- [クエリのベストプラクティス](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="248db-147">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="248db-148">- [エラーを処理する](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="248db-148">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="248db-149">**検出ルールの作成**</span><span class="sxs-lookup"><span data-stu-id="248db-149">**Create custom detection rules**</span></span> | <span data-ttu-id="248db-150">高度な検索クエリを使用して、通知をトリガーし、応答アクションを自動的に実行する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="248db-150">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="248db-151">- [ユーザー設定の検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="248db-151">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="248db-152">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="248db-152">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="248db-153">アクセス権を取得する</span><span class="sxs-lookup"><span data-stu-id="248db-153">Get access</span></span>
<span data-ttu-id="248db-154">高度な検索やその他の [Microsoft 365 Defender](microsoft-threat-protection.md) 機能を使用するには、Azure Active Directory に適切なロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="248db-154">To use advanced hunting or other [Microsoft 365 Defender](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="248db-155">また、エンドポイントのデータへのアクセスは、エンドポイントの Microsoft Defender の役割ベースのアクセス制御 (RBAC) 設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="248db-155">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="248db-156">Microsoft 365 Defender へのアクセスの管理について確認する</span><span class="sxs-lookup"><span data-stu-id="248db-156">Read about managing access to Microsoft 365 Defender</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="248db-157">データの鮮度と更新頻度</span><span class="sxs-lookup"><span data-stu-id="248db-157">Data freshness and update frequency</span></span>
<span data-ttu-id="248db-158">高度な検索データは、それぞれ異なる方法で2つの異なる種類に分類できます。</span><span class="sxs-lookup"><span data-stu-id="248db-158">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="248db-159">**イベントまたはアクティビティのデータ** —アラート、セキュリティイベント、システムイベント、および定期的な評価に関する表について説明します。</span><span class="sxs-lookup"><span data-stu-id="248db-159">**Event or activity data** —populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="248db-160">高度な検索では、このデータを収集するセンサーが、対応するクラウドサービスに正常に送信された直後に受信します。</span><span class="sxs-lookup"><span data-stu-id="248db-160">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="248db-161">たとえば、エンドポイントの Microsoft Defender および Id の Microsoft Defender で利用可能になった直後に、ワークステーションまたはドメインコントローラーの正常なセンサーのイベントデータをクエリできます。</span><span class="sxs-lookup"><span data-stu-id="248db-161">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="248db-162">**エンティティデータ** —ユーザーとデバイスに関する情報をテーブルに格納します。</span><span class="sxs-lookup"><span data-stu-id="248db-162">**Entity data** —populates tables with information about users and devices.</span></span> <span data-ttu-id="248db-163">このデータは、比較的静的なデータソースと、Active Directory エントリやイベントログなどの動的ソースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="248db-163">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="248db-164">新しいデータを提供するために、15分ごとに、完全には設定されていない可能性のある行を追加して、すべての新しい情報でテーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="248db-164">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="248db-165">24時間ごとにデータが統合され、各エンティティについての最新の最も包括的なデータセットを含むレコードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="248db-165">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="248db-166">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="248db-166">Time zone</span></span>
<span data-ttu-id="248db-167">高度な検索の時間情報は UTC タイムゾーンにあります。</span><span class="sxs-lookup"><span data-stu-id="248db-167">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="248db-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="248db-168">Related topics</span></span>
- [<span data-ttu-id="248db-169">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="248db-169">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="248db-170">エキスパート トレーニングを受ける</span><span class="sxs-lookup"><span data-stu-id="248db-170">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="248db-171">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="248db-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="248db-172">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="248db-172">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="248db-173">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="248db-173">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="248db-174">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="248db-174">Custom detections overview</span></span>](custom-detections-overview.md)

