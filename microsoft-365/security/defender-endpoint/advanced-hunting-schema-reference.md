---
title: 高度な検索スキーマリファレンス
description: 高度な検索スキーマのテーブルについて説明し、脅威検出クエリを実行できるデータを理解します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、data
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: 38fe205227089acaec1ba0cbecffdfb76acf6a24
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615473"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="88d53-104">Microsoft Defender for Endpoint の高度なハンティング スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="88d53-104">Understand the advanced hunting schema in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88d53-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="88d53-105">**Applies to:**</span></span>
- [<span data-ttu-id="88d53-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="88d53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="88d53-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="88d53-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="88d53-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="88d53-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="88d53-109">高度 [な検索スキーマ](advanced-hunting-overview.md) は、イベント情報またはデバイスや他のエンティティに関する情報を提供する複数のテーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="88d53-109">The [advanced hunting](advanced-hunting-overview.md) schema is made up of multiple tables that provide either event information or information about devices and other entities.</span></span> <span data-ttu-id="88d53-110">複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88d53-110">To effectively build queries that span multiple tables, you need to understand the tables and the columns in the advanced hunting schema.</span></span>

## <a name="get-schema-information-in-the-security-center"></a><span data-ttu-id="88d53-111">セキュリティ センターでスキーマ情報を取得する</span><span class="sxs-lookup"><span data-stu-id="88d53-111">Get schema information in the security center</span></span>
<span data-ttu-id="88d53-112">クエリを作成する場合は、組み込みのスキーマ参照を使用して、スキーマ内の各テーブルに関する次の情報をすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="88d53-112">While constructing queries, use the built-in schema reference to quickly get the following information about each table in the schema:</span></span>

- <span data-ttu-id="88d53-113">**テーブルの** 説明 —テーブルに含まれるデータの種類と、そのデータのソース。</span><span class="sxs-lookup"><span data-stu-id="88d53-113">**Tables description**—type of data contained in the table and the source of that data.</span></span>
- <span data-ttu-id="88d53-114">**列**—テーブル内のすべての列。</span><span class="sxs-lookup"><span data-stu-id="88d53-114">**Columns**—all the columns in the table.</span></span>
- <span data-ttu-id="88d53-115">**アクションの** 種類 —テーブルでサポートされるイベントの種類を表す列 `ActionType` の可能な値。</span><span class="sxs-lookup"><span data-stu-id="88d53-115">**Action types**—possible values in the `ActionType` column representing the event types supported by the table.</span></span> <span data-ttu-id="88d53-116">これは、イベント情報を含むテーブルにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="88d53-116">This is provided only for tables that contain event information.</span></span>
- <span data-ttu-id="88d53-117">**サンプル クエリ**—テーブルの利用方法を特徴付けするクエリの例。</span><span class="sxs-lookup"><span data-stu-id="88d53-117">**Sample query**—example queries that feature how the table can be utilized.</span></span>

### <a name="access-the-schema-reference"></a><span data-ttu-id="88d53-118">スキーマ参照へのアクセス</span><span class="sxs-lookup"><span data-stu-id="88d53-118">Access the schema reference</span></span>
<span data-ttu-id="88d53-119">スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある [参照の表示] アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="88d53-119">To quickly access the schema reference, select the **View reference** action next to the table name in the schema representation.</span></span> <span data-ttu-id="88d53-120">[スキーマ参照] **を選択して** テーブルを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="88d53-120">You can also select **Schema reference** to search for a table.</span></span>

![ポータル内スキーマ参照にアクセスする方法を示すイメージ](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a><span data-ttu-id="88d53-122">スキーマ テーブルの詳細</span><span class="sxs-lookup"><span data-stu-id="88d53-122">Learn the schema tables</span></span>

<span data-ttu-id="88d53-123">次の参照では、高度な検索スキーマのすべてのテーブルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="88d53-123">The following reference lists all the tables in the advanced hunting schema.</span></span> <span data-ttu-id="88d53-124">各テーブル名は、そのテーブルの列名を説明するページにリンクします。</span><span class="sxs-lookup"><span data-stu-id="88d53-124">Each table name links to a page describing the column names for that table.</span></span>

<span data-ttu-id="88d53-125">テーブル名と列名は、高度な検索画面のスキーマ表現の Microsoft Defender セキュリティ センター内にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="88d53-125">Table and column names are also listed within the Microsoft Defender Security Center, in the schema representation on the advanced hunting screen.</span></span>

| <span data-ttu-id="88d53-126">テーブル名</span><span class="sxs-lookup"><span data-stu-id="88d53-126">Table name</span></span> | <span data-ttu-id="88d53-127">説明</span><span class="sxs-lookup"><span data-stu-id="88d53-127">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="88d53-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-128">**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**</span></span> | <span data-ttu-id="88d53-129">Microsoft Defender セキュリティ センターに関する通知</span><span class="sxs-lookup"><span data-stu-id="88d53-129">Alerts on Microsoft Defender Security Center</span></span> |
| <span data-ttu-id="88d53-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-130">**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**</span></span> | <span data-ttu-id="88d53-131">OS 情報を含むデバイス情報</span><span class="sxs-lookup"><span data-stu-id="88d53-131">Device information, including OS information</span></span> |
| <span data-ttu-id="88d53-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-132">**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**</span></span> | <span data-ttu-id="88d53-133">アダプター、IP アドレス、MAC アドレス、接続されたネットワークおよびドメインを含むデバイスのネットワーク プロパティ</span><span class="sxs-lookup"><span data-stu-id="88d53-133">Network properties of devices, including adapters, IP and MAC addresses, as well as connected networks and domains</span></span> |
| <span data-ttu-id="88d53-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-134">**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**</span></span> | <span data-ttu-id="88d53-135">プロセスの作成と関連イベント</span><span class="sxs-lookup"><span data-stu-id="88d53-135">Process creation and related events</span></span> |
| <span data-ttu-id="88d53-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-136">**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**</span></span> | <span data-ttu-id="88d53-137">ネットワーク接続と関連イベント</span><span class="sxs-lookup"><span data-stu-id="88d53-137">Network connection and related events</span></span> |
| <span data-ttu-id="88d53-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-138">**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**</span></span> | <span data-ttu-id="88d53-139">ファイルの作成、変更、およびその他のファイル システム イベント</span><span class="sxs-lookup"><span data-stu-id="88d53-139">File creation, modification, and other file system events</span></span> |
| <span data-ttu-id="88d53-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-140">**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**</span></span> | <span data-ttu-id="88d53-141">レジストリ エントリの作成と変更</span><span class="sxs-lookup"><span data-stu-id="88d53-141">Creation and modification of registry entries</span></span> |
| <span data-ttu-id="88d53-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-142">**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**</span></span> | <span data-ttu-id="88d53-143">サインインとその他の認証イベント</span><span class="sxs-lookup"><span data-stu-id="88d53-143">Sign-ins and other authentication events</span></span> |
| <span data-ttu-id="88d53-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-144">**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**</span></span> | <span data-ttu-id="88d53-145">DLL の読み込みイベント</span><span class="sxs-lookup"><span data-stu-id="88d53-145">DLL loading events</span></span> |
| <span data-ttu-id="88d53-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-146">**[DeviceEvents](advanced-hunting-deviceevents-table.md)**</span></span> | <span data-ttu-id="88d53-147">Microsoft Defender ウイルス対策やエクスプロイト保護などのセキュリティ制御によってトリガーされるイベントを含む、複数のイベントの種類</span><span class="sxs-lookup"><span data-stu-id="88d53-147">Multiple event types, including events triggered by security controls such as Microsoft Defender Antivirus and exploit protection</span></span> |
| <span data-ttu-id="88d53-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-148">**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**</span></span> | <span data-ttu-id="88d53-149">エンドポイント上の証明書検証イベントから取得した署名済みファイルの証明書情報</span><span class="sxs-lookup"><span data-stu-id="88d53-149">Certificate information of signed files obtained from certificate verification events on endpoints</span></span> |
| <span data-ttu-id="88d53-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-150">**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**</span></span> | <span data-ttu-id="88d53-151">デバイスにインストールされているソフトウェアのインベントリ (バージョン情報とサポート終了の状態を含む)</span><span class="sxs-lookup"><span data-stu-id="88d53-151">Inventory of software installed on devices, including their version information and end-of-support status</span></span> |
| <span data-ttu-id="88d53-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-152">**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**</span></span> | <span data-ttu-id="88d53-153">デバイスで見つかったソフトウェアの脆弱性と、各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧</span><span class="sxs-lookup"><span data-stu-id="88d53-153">Software vulnerabilities found on devices and the list of available security updates that address each vulnerability</span></span> |
| <span data-ttu-id="88d53-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-154">**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**</span></span> | <span data-ttu-id="88d53-155">悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報</span><span class="sxs-lookup"><span data-stu-id="88d53-155">Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available</span></span> |
| <span data-ttu-id="88d53-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-156">**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**</span></span> | <span data-ttu-id="88d53-157">デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント</span><span class="sxs-lookup"><span data-stu-id="88d53-157">Threat & Vulnerability Management assessment events, indicating the status of various security configurations on devices</span></span> |
| <span data-ttu-id="88d53-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span><span class="sxs-lookup"><span data-stu-id="88d53-158">**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**</span></span> | <span data-ttu-id="88d53-159">脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　</span><span class="sxs-lookup"><span data-stu-id="88d53-159">Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span> |

>[!TIP]
><span data-ttu-id="88d53-160">[Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview)の高度な検索を使用して、Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity のデータを使用して脅威を探します。</span><span class="sxs-lookup"><span data-stu-id="88d53-160">Use [advanced hunting in Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> [<span data-ttu-id="88d53-161">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="88d53-161">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-enable)<br><br>
<span data-ttu-id="88d53-162">高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defender に移動する方法については、「Advanced Hunting [queries](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)を Microsoft Defender for Endpoint から移行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88d53-162">Learn more about how to move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).</span></span>

## <a name="related-topics"></a><span data-ttu-id="88d53-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="88d53-163">Related topics</span></span>
- [<span data-ttu-id="88d53-164">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="88d53-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="88d53-165">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="88d53-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="88d53-166">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="88d53-166">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="88d53-167">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="88d53-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="88d53-168">カスタム検出の概要</span><span class="sxs-lookup"><span data-stu-id="88d53-168">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="88d53-169">高度なハンティング データ スキーマの変更</span><span class="sxs-lookup"><span data-stu-id="88d53-169">Advanced hunting data schema changes</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
