---
title: Microsoft Threat Protection の高度な捜索スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、データ
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
ms.openlocfilehash: aa2fbeebed10bcb1f0c4078a161be99d16d3b97b
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210322"
---
# <a name="understand-the-advanced-hunting-schema"></a><span data-ttu-id="ee559-104">高度な捜索スキーマの概要</span><span class="sxs-lookup"><span data-stu-id="ee559-104">Understand the advanced hunting schema</span></span>

<span data-ttu-id="ee559-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ee559-105">**Applies to:**</span></span>
- <span data-ttu-id="ee559-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee559-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ee559-107">[高度な捜索](advanced-hunting-overview.md)スキーマは、イベント情報またはマシンとエンティティに関する情報を提供する複数のテーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ee559-107">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about machines and entities.</span></span> <span data-ttu-id="ee559-108">複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee559-108">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="schema-tables"></a><span data-ttu-id="ee559-109">スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="ee559-109">Schema tables</span></span>

<span data-ttu-id="ee559-110">次の参照は、スキーマ内のすべてのテーブルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ee559-110">The following reference lists all the tables in the schema.</span></span> <span data-ttu-id="ee559-111">各テーブル名は、そのテーブルの列名を説明するページにリンクします。</span><span class="sxs-lookup"><span data-stu-id="ee559-111">Each table name links to a page describing the column names for that table.</span></span> <span data-ttu-id="ee559-112">テーブル名と列名は、高度な捜索画面のスキーマ表現の一部として、セキュリティ センターにも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee559-112">Table and column names are also listed in the security center as part of the the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="ee559-113">テーブル名</span><span class="sxs-lookup"><span data-stu-id="ee559-113">Table name</span></span> | <span data-ttu-id="ee559-114">説明</span><span class="sxs-lookup"><span data-stu-id="ee559-114">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="ee559-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-115">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="ee559-116">OS 情報を含むマシン情報</span><span class="sxs-lookup"><span data-stu-id="ee559-116">Machine information, including OS information</span></span> |
| <span data-ttu-id="ee559-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-117">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="ee559-118">アダプタ、IP アドレス、MAC アドレス、および接続されたネットワークとドメインを含むマシンのネットワーク プロパティ</span><span class="sxs-lookup"><span data-stu-id="ee559-118">Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="ee559-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-119">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="ee559-120">プロセスの作成と関連イベント</span><span class="sxs-lookup"><span data-stu-id="ee559-120">Process creation and related events</span></span> |
| <span data-ttu-id="ee559-121">**[DeviceNetworkEvents 孔](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-121">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="ee559-122">ネットワーク接続と関連イベント</span><span class="sxs-lookup"><span data-stu-id="ee559-122">Network connection and related events</span></span> |
| <span data-ttu-id="ee559-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-123">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="ee559-124">ファイルの作成、変更、およびその他のファイル システム イベント</span><span class="sxs-lookup"><span data-stu-id="ee559-124">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="ee559-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-125">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="ee559-126">レジストリ エントリの作成と変更</span><span class="sxs-lookup"><span data-stu-id="ee559-126">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="ee559-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-127">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="ee559-128">サインインとその他の認証イベント</span><span class="sxs-lookup"><span data-stu-id="ee559-128">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="ee559-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-129">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="ee559-130">DLL の読み込みイベント</span><span class="sxs-lookup"><span data-stu-id="ee559-130">DLL loading events</span></span> |
| <span data-ttu-id="ee559-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-131">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="ee559-132">Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント </span><span class="sxs-lookup"><span data-stu-id="ee559-132">Multiple event types, including events triggered by security controls such as Windows Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="ee559-133">**[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-133">**[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)**</span></span> | <span data-ttu-id="ee559-134">エンドポイントの証明書検証イベントから取得された署名済みファイルの証明書情報</span><span class="sxs-lookup"><span data-stu-id="ee559-134">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="ee559-135">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-135">**[EmailEvents](advanced-hunting-emailevents-table.md)**</span></span> | <span data-ttu-id="ee559-136">メール配信やブロック イベントを含む Office 365 のメール イベント</span><span class="sxs-lookup"><span data-stu-id="ee559-136">Office 365 email events, including email delivery and blocking events</span></span> |
| <span data-ttu-id="ee559-137">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-137">**[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)**</span></span> | <span data-ttu-id="ee559-138">Office 365 メールに添付されたファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="ee559-138">Information about files attached to Office 365 emails</span></span> |
| <span data-ttu-id="ee559-139">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-139">**[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)**</span></span> | <span data-ttu-id="ee559-140">Office 365 メールの URL に関する情報</span><span class="sxs-lookup"><span data-stu-id="ee559-140">Information about URLs on Office 365 emails</span></span> |
| <span data-ttu-id="ee559-141">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-141">**[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)**</span></span> | <span data-ttu-id="ee559-142">デバイス上のソフトウェアのインベントリ、およびこれらのソフトウェア製品の既知の脆弱性</span><span class="sxs-lookup"><span data-stu-id="ee559-142">Inventory of software on devices as well as any known vulnerabilities in these software products</span></span> |
| <span data-ttu-id="ee559-143">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-143">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)**</span></span> | <span data-ttu-id="ee559-144">悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報</span><span class="sxs-lookup"><span data-stu-id="ee559-144">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="ee559-145">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-145">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)**</span></span> | <span data-ttu-id="ee559-146">デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント</span><span class="sxs-lookup"><span data-stu-id="ee559-146">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="ee559-147">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="ee559-147">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)**</span></span> | <span data-ttu-id="ee559-148">脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　</span><span class="sxs-lookup"><span data-stu-id="ee559-148">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="ee559-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee559-149">Related topics</span></span>
- [<span data-ttu-id="ee559-150">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="ee559-150">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ee559-151">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ee559-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ee559-152">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ee559-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ee559-153">デバイスとメール全体で脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="ee559-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ee559-154">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ee559-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)