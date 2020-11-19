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
ms.openlocfilehash: bab055036a8e7fdcf88329413c9fd86269af2aaa
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357227"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="dff92-104">Microsoft 365 Defender での高度な検索を使用して、積極的に脅威を探します。</span><span class="sxs-lookup"><span data-stu-id="dff92-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dff92-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dff92-105">**Applies to:**</span></span>
- <span data-ttu-id="dff92-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dff92-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="dff92-107">Microsoft 365 Defender を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="dff92-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="dff92-108">[ラボ環境で評価](https://aka.ms/mtp-trial-lab)することも、[運用環境でパイロットプロジェクトを実行](https://aka.ms/m365d-pilotplaybook)することもできます。</span><span class="sxs-lookup"><span data-stu-id="dff92-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="dff92-109">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="dff92-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="dff92-110">ネットワーク内のイベントを事前に検査して、脅威の指標とエンティティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="dff92-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="dff92-111">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威を無制限に探すことができます。</span><span class="sxs-lookup"><span data-stu-id="dff92-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="dff92-112">同じ脅威を捜索しているクエリを使用して、カスタムの検出ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dff92-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="dff92-113">これらのルールは自動的に実行され、疑わしい違反活動、不適切な構成のコンピューター、およびその他の結果をチェックして応答します。</span><span class="sxs-lookup"><span data-stu-id="dff92-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="dff92-114">この機能は、 [エンドポイントの Microsoft Defender での高度な](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)検索に似ています。</span><span class="sxs-lookup"><span data-stu-id="dff92-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="dff92-115">Microsoft 365 セキュリティセンターで利用可能です。この機能により、次のような幅広いデータセットをチェックするクエリがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dff92-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="dff92-116">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dff92-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="dff92-117">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="dff92-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="dff92-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dff92-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="dff92-119">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="dff92-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="dff92-120">高度な検索を使用するには、 [Microsoft 365 Defender をオン](mtp-enable.md)にします。</span><span class="sxs-lookup"><span data-stu-id="dff92-120">To use advanced hunting, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="dff92-121">高度な捜索を開始する</span><span class="sxs-lookup"><span data-stu-id="dff92-121">Get started with advanced hunting</span></span>

<span data-ttu-id="dff92-122">高度な検索をすばやく始めるには、いくつかの手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dff92-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="dff92-123">学習目標</span><span class="sxs-lookup"><span data-stu-id="dff92-123">Learning goal</span></span> | <span data-ttu-id="dff92-124">説明</span><span class="sxs-lookup"><span data-stu-id="dff92-124">Description</span></span> | <span data-ttu-id="dff92-125">リソース</span><span class="sxs-lookup"><span data-stu-id="dff92-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="dff92-126">**言語について**</span><span class="sxs-lookup"><span data-stu-id="dff92-126">**Learn the language**</span></span> | <span data-ttu-id="dff92-127">高度な検索は、 [Kusto クエリ言語](https://docs.microsoft.com/azure/kusto/query/)に基づいており、同じ構文および演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dff92-127">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="dff92-128">最初のクエリを実行して、クエリ言語を学習します。</span><span class="sxs-lookup"><span data-stu-id="dff92-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="dff92-129">クエリ言語の概要</span><span class="sxs-lookup"><span data-stu-id="dff92-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="dff92-130">**クエリ結果の使用方法について説明します。**</span><span class="sxs-lookup"><span data-stu-id="dff92-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="dff92-131">グラフと、結果を表示またはエクスポートするさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dff92-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="dff92-132">クエリをすばやく調整する方法、豊富な情報を取得するためのドリルダウン、および応答アクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dff92-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="dff92-133">- [クエリ結果を操作する](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="dff92-134">- [クエリ結果に対してアクションを実行する](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="dff92-135">**スキーマを理解する**</span><span class="sxs-lookup"><span data-stu-id="dff92-135">**Understand the schema**</span></span> | <span data-ttu-id="dff92-136">スキーマとその列のテーブルについて、高レベルで十分に理解してください。</span><span class="sxs-lookup"><span data-stu-id="dff92-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="dff92-137">クエリを作成するときにデータを検索する場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="dff92-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="dff92-138">- [スキーマリファレンス](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="dff92-139">- [エンドポイントの Microsoft Defender からの移行](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="dff92-140">**エキスパートのヒントと例を取得する**</span><span class="sxs-lookup"><span data-stu-id="dff92-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="dff92-141">Microsoft の専門家のガイドを使用して無料でトレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="dff92-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="dff92-142">さまざまな脅威の捜索シナリオを網羅する定義済みクエリのコレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="dff92-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="dff92-143">- [エキスパートトレーニングを受ける](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="dff92-144">- [共有クエリを使用する](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="dff92-145">- [ハントに移動](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="dff92-146">- [デバイス、メール、アプリ、および id 間の脅威を探します。](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="dff92-147">**クエリを最適化してエラーを処理する**</span><span class="sxs-lookup"><span data-stu-id="dff92-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="dff92-148">効率的でエラーのないクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dff92-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="dff92-149">- [クエリのベストプラクティス](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="dff92-150">- [エラーを処理する](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="dff92-151">**検出ルールの作成**</span><span class="sxs-lookup"><span data-stu-id="dff92-151">**Create custom detection rules**</span></span> | <span data-ttu-id="dff92-152">高度な検索クエリを使用して、通知をトリガーし、応答アクションを自動的に実行する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="dff92-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="dff92-153">- [ユーザー設定の検出の概要](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="dff92-154">- [カスタム検出ルール](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="dff92-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="dff92-155">アクセス権を取得する</span><span class="sxs-lookup"><span data-stu-id="dff92-155">Get access</span></span>
<span data-ttu-id="dff92-156">高度な検索やその他の [Microsoft 365 Defender](microsoft-threat-protection.md) 機能を使用するには、Azure Active Directory に適切なロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="dff92-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="dff92-157">また、エンドポイントのデータへのアクセスは、エンドポイントの Microsoft Defender の役割ベースのアクセス制御 (RBAC) 設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="dff92-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="dff92-158">Microsoft 365 Defender へのアクセスの管理について確認する</span><span class="sxs-lookup"><span data-stu-id="dff92-158">Read about managing access to Microsoft 365 Defender</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="dff92-159">データの鮮度と更新頻度</span><span class="sxs-lookup"><span data-stu-id="dff92-159">Data freshness and update frequency</span></span>
<span data-ttu-id="dff92-160">高度な検索データは、それぞれ異なる方法で2つの異なる種類に分類できます。</span><span class="sxs-lookup"><span data-stu-id="dff92-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="dff92-161">**イベントまたはアクティビティのデータ**—アラート、セキュリティイベント、システムイベント、および定期的な評価に関する表について説明します。</span><span class="sxs-lookup"><span data-stu-id="dff92-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="dff92-162">高度な検索では、このデータを収集するセンサーが、対応するクラウドサービスに正常に送信された直後に受信します。</span><span class="sxs-lookup"><span data-stu-id="dff92-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="dff92-163">たとえば、エンドポイントの Microsoft Defender および Id の Microsoft Defender で利用可能になった直後に、ワークステーションまたはドメインコントローラーの正常なセンサーのイベントデータをクエリできます。</span><span class="sxs-lookup"><span data-stu-id="dff92-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="dff92-164">**エンティティデータ**—ユーザーとデバイスに関する情報をテーブルに格納します。</span><span class="sxs-lookup"><span data-stu-id="dff92-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="dff92-165">このデータは、比較的静的なデータソースと、Active Directory エントリやイベントログなどの動的ソースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="dff92-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="dff92-166">新しいデータを提供するために、15分ごとに、完全には設定されていない可能性のある行を追加して、すべての新しい情報でテーブルを更新します。</span><span class="sxs-lookup"><span data-stu-id="dff92-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="dff92-167">24時間ごとにデータが統合され、各エンティティについての最新の最も包括的なデータセットを含むレコードが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="dff92-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="dff92-168">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="dff92-168">Time zone</span></span>
<span data-ttu-id="dff92-169">高度な検索の時間情報は UTC タイムゾーンにあります。</span><span class="sxs-lookup"><span data-stu-id="dff92-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dff92-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="dff92-170">Related topics</span></span>
- [<span data-ttu-id="dff92-171">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="dff92-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dff92-172">エキスパート トレーニングを受ける</span><span class="sxs-lookup"><span data-stu-id="dff92-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="dff92-173">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="dff92-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dff92-174">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="dff92-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dff92-175">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="dff92-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="dff92-176">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="dff92-176">Custom detections overview</span></span>](custom-detections-overview.md)

