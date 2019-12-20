---
title: Microsoft Threat Protection の高度な捜索スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、データ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 631b328168003668ed06e37d76177c327794ed18
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808662"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="c825c-104">高度な捜索スキーマの概要</span><span class="sxs-lookup"><span data-stu-id="c825c-104">Understand the advanced hunting schema</span></span>

<span data-ttu-id="c825c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c825c-105">**Applies to:**</span></span>
- <span data-ttu-id="c825c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c825c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c825c-107">[高度な捜索](advanced-hunting-overview.md)スキーマは、イベント情報またはマシンとエンティティに関する情報を提供する複数のテーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c825c-107">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about machines and entities.</span></span> <span data-ttu-id="c825c-108">複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c825c-108">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="schema-tables"></a><span data-ttu-id="c825c-109">スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="c825c-109">Schema tables</span></span>

<span data-ttu-id="c825c-110">次の参照は、スキーマ内のすべてのテーブルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c825c-110">The following reference lists all the tables in the schema.</span></span> <span data-ttu-id="c825c-111">各テーブル名は、そのテーブルの列名を説明するページにリンクします。</span><span class="sxs-lookup"><span data-stu-id="c825c-111">Each table name links to a page describing the column names for that table.</span></span> <span data-ttu-id="c825c-112">テーブル名と列名は、高度な捜索画面のスキーマ表現の一部として、セキュリティ センターにも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c825c-112">Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="c825c-113">テーブル名</span><span class="sxs-lookup"><span data-stu-id="c825c-113">Table name</span></span> | <span data-ttu-id="c825c-114">説明</span><span class="sxs-lookup"><span data-stu-id="c825c-114">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="c825c-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="c825c-116">OS 情報を含むマシン情報</span><span class="sxs-lookup"><span data-stu-id="c825c-116">Machine information, including OS information</span></span> |
| <span data-ttu-id="c825c-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="c825c-118">アダプタ、IP アドレス、MAC アドレス、および接続されたネットワークとドメインを含むマシンのネットワーク プロパティ</span><span class="sxs-lookup"><span data-stu-id="c825c-118">Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="c825c-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="c825c-120">プロセスの作成と関連イベント</span><span class="sxs-lookup"><span data-stu-id="c825c-120">Process creation and related events</span></span> |
| <span data-ttu-id="c825c-121">**[DeviceNetworkEvents 孔](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="c825c-122">ネットワーク接続と関連イベント</span><span class="sxs-lookup"><span data-stu-id="c825c-122">Network connection and related events</span></span> |
| <span data-ttu-id="c825c-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="c825c-124">ファイルの作成、変更、およびその他のファイル システム イベント</span><span class="sxs-lookup"><span data-stu-id="c825c-124">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="c825c-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="c825c-126">レジストリ エントリの作成と変更</span><span class="sxs-lookup"><span data-stu-id="c825c-126">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="c825c-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="c825c-128">サインインとその他の認証イベント</span><span class="sxs-lookup"><span data-stu-id="c825c-128">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="c825c-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="c825c-130">DLL の読み込みイベント</span><span class="sxs-lookup"><span data-stu-id="c825c-130">DLL loading events</span></span> |
| <span data-ttu-id="c825c-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="c825c-132">Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント </span><span class="sxs-lookup"><span data-stu-id="c825c-132">Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="c825c-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-133">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span></span> | <span data-ttu-id="c825c-134">メール配信やブロック イベントを含む Office 365 のメール イベント</span><span class="sxs-lookup"><span data-stu-id="c825c-134">Office 365 email events, including email delivery and blocking events</span></span> |
| <span data-ttu-id="c825c-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-135">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span></span> | <span data-ttu-id="c825c-136">Office 365 メールに添付されたファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="c825c-136">Information about files attached to Office 365 emails</span></span> |
| <span data-ttu-id="c825c-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-137">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span></span> | <span data-ttu-id="c825c-138">Office 365 メールの URL に関する情報</span><span class="sxs-lookup"><span data-stu-id="c825c-138">Information about URLs on Office 365 emails</span></span> |
| <span data-ttu-id="c825c-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-139">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span></span> | <span data-ttu-id="c825c-140">デバイス上のソフトウェアのインベントリ、およびこれらのソフトウェア製品の既知の脆弱性</span><span class="sxs-lookup"><span data-stu-id="c825c-140">Inventory of software on devices as well as any known vulnerabilities in these software products</span></span> |
| <span data-ttu-id="c825c-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-141">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span></span> | <span data-ttu-id="c825c-142">悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報</span><span class="sxs-lookup"><span data-stu-id="c825c-142">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="c825c-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-143">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span></span> | <span data-ttu-id="c825c-144">デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント</span><span class="sxs-lookup"><span data-stu-id="c825c-144">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="c825c-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="c825c-145">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span></span> | <span data-ttu-id="c825c-146">脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　</span><span class="sxs-lookup"><span data-stu-id="c825c-146">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="c825c-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="c825c-147">Related topics</span></span>
- [<span data-ttu-id="c825c-148">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="c825c-148">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c825c-149">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="c825c-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c825c-150">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="c825c-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c825c-151">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="c825c-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c825c-152">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="c825c-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
