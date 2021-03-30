---
title: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブル
description: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブルで、デバイス内のソフトウェアのインベントリについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威& 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408625"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="6a760-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="6a760-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a760-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6a760-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a760-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a760-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="6a760-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6a760-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a760-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6a760-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6a760-109">高度 `DeviceTvmSoftwareInventory` な検索スキーマの表には、ネットワーク内[](next-gen-threat-and-vuln-mgt.md)のデバイスに現在インストールされているソフトウェアの脅威と脆弱性管理インベントリ (サポート情報の終了など) が含まれている。</span><span class="sxs-lookup"><span data-stu-id="6a760-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="6a760-110">たとえば、現在脆弱なソフトウェア バージョンでインストールされているデバイスに関連するイベントを探します。</span><span class="sxs-lookup"><span data-stu-id="6a760-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="6a760-111">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a760-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6a760-112">DeviceTVMSoftwareInventory には、脅威と脆弱性の管理が共通プラットフォーム列挙 (CPE) と一致する可能性があるすべてのソフトウェアが含まれている 。脆弱性が存在するかどうかに関わりはありません。</span><span class="sxs-lookup"><span data-stu-id="6a760-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="6a760-113">テーブル `DeviceTvmSoftwareInventory` と `DeviceTvmSoftwareVulnerabilities` テーブルがテーブルを置き換 `DeviceTvmSoftwareInventoryVulnerabilities` えました。</span><span class="sxs-lookup"><span data-stu-id="6a760-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="6a760-114">最初の 2 つの表には、脆弱性管理アクティビティの通知に使用できる列が追加されています。</span><span class="sxs-lookup"><span data-stu-id="6a760-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="6a760-115">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a760-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="6a760-116">列名</span><span class="sxs-lookup"><span data-stu-id="6a760-116">Column name</span></span> | <span data-ttu-id="6a760-117">データ型</span><span class="sxs-lookup"><span data-stu-id="6a760-117">Data type</span></span> | <span data-ttu-id="6a760-118">説明</span><span class="sxs-lookup"><span data-stu-id="6a760-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6a760-119">string</span><span class="sxs-lookup"><span data-stu-id="6a760-119">string</span></span> | <span data-ttu-id="6a760-120">サービス内のデバイスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6a760-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="6a760-121">string</span><span class="sxs-lookup"><span data-stu-id="6a760-121">string</span></span> | <span data-ttu-id="6a760-122">デバイスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6a760-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="6a760-123">string</span><span class="sxs-lookup"><span data-stu-id="6a760-123">string</span></span> | <span data-ttu-id="6a760-124">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="6a760-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6a760-125">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="6a760-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="6a760-126">string</span><span class="sxs-lookup"><span data-stu-id="6a760-126">string</span></span> | <span data-ttu-id="6a760-127">デバイスで実行されているオペレーティング システムのバージョン。</span><span class="sxs-lookup"><span data-stu-id="6a760-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="6a760-128">string</span><span class="sxs-lookup"><span data-stu-id="6a760-128">string</span></span> | <span data-ttu-id="6a760-129">デバイスで実行されているオペレーティング システムのアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="6a760-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="6a760-130">string</span><span class="sxs-lookup"><span data-stu-id="6a760-130">string</span></span> | <span data-ttu-id="6a760-131">ソフトウェア ベンダーの名前。</span><span class="sxs-lookup"><span data-stu-id="6a760-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="6a760-132">string</span><span class="sxs-lookup"><span data-stu-id="6a760-132">string</span></span> | <span data-ttu-id="6a760-133">ソフトウェア製品の名前。</span><span class="sxs-lookup"><span data-stu-id="6a760-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="6a760-134">string</span><span class="sxs-lookup"><span data-stu-id="6a760-134">string</span></span> | <span data-ttu-id="6a760-135">ソフトウェア製品のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="6a760-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="6a760-136">string</span><span class="sxs-lookup"><span data-stu-id="6a760-136">string</span></span> | <span data-ttu-id="6a760-137">指定したサポート終了日 (EOS) または終了 (EOL) の日付を基準にしたソフトウェア製品のライフサイクル ステージを示します。</span><span class="sxs-lookup"><span data-stu-id="6a760-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="6a760-138">string</span><span class="sxs-lookup"><span data-stu-id="6a760-138">string</span></span> | <span data-ttu-id="6a760-139">ソフトウェア製品のサポート終了日 (EOS) または終了 (EOL) 日付。</span><span class="sxs-lookup"><span data-stu-id="6a760-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6a760-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a760-140">Related topics</span></span>

- [<span data-ttu-id="6a760-141">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="6a760-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6a760-142">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="6a760-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6a760-143">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="6a760-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6a760-144">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="6a760-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
