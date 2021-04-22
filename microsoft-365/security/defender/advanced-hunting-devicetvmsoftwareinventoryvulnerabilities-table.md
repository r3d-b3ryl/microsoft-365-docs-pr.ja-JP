---
title: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブル
description: 高度なハンティング スキーマの DeviceTvmSoftwareInventory テーブルで、デバイス内のソフトウェアのインベントリについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、ソフトウェア、インベントリ、脆弱性、CVE ID、OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.technology: m365d
ms.openlocfilehash: 6e24b6aa7412c05324571bd22b380215219bdf44
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934839"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="2fdb1-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="2fdb1-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2fdb1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2fdb1-105">**Applies to:**</span></span>
- <span data-ttu-id="2fdb1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fdb1-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="2fdb1-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2fdb1-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="2fdb1-109">高度 `DeviceTvmSoftwareInventory` な検索スキーマの表には、ネットワーク [内のデバイスに現在インストール](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) されているソフトウェアの脅威&脆弱性管理インベントリ (サポート情報の終了など) が含まれている。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="2fdb1-110">たとえば、現在脆弱なソフトウェア バージョンでインストールされているデバイスに関連するイベントを探します。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="2fdb1-111">このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="2fdb1-112">テーブル `DeviceTvmSoftwareInventory` と `DeviceTvmSoftwareVulnerabilities` テーブルがテーブルを置き換 `DeviceTvmSoftwareInventoryVulnerabilities` えました。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="2fdb1-113">最初の 2 つのテーブルには、脆弱な管理アクティビティを通知したり、脆弱なデバイスを探したりするのに役立つ列が追加されています。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="2fdb1-114">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2fdb1-115">列名</span><span class="sxs-lookup"><span data-stu-id="2fdb1-115">Column name</span></span> | <span data-ttu-id="2fdb1-116">データ型</span><span class="sxs-lookup"><span data-stu-id="2fdb1-116">Data type</span></span> | <span data-ttu-id="2fdb1-117">説明</span><span class="sxs-lookup"><span data-stu-id="2fdb1-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2fdb1-118">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-118">string</span></span> | <span data-ttu-id="2fdb1-119">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="2fdb1-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2fdb1-120">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-120">string</span></span> | <span data-ttu-id="2fdb1-121">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="2fdb1-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2fdb1-122">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-122">string</span></span> | <span data-ttu-id="2fdb1-123">コンピューターで実行されているオペレーティング システムのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2fdb1-124">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="2fdb1-125">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-125">string</span></span> | <span data-ttu-id="2fdb1-126">コンピューターで実行されているオペレーティング システムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="2fdb1-127">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-127">string</span></span> | <span data-ttu-id="2fdb1-128">コンピューターで実行されているオペレーティング システムのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="2fdb1-129">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-129">string</span></span> | <span data-ttu-id="2fdb1-130">ソフトウェア ベンダーの名前</span><span class="sxs-lookup"><span data-stu-id="2fdb1-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="2fdb1-131">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-131">string</span></span> | <span data-ttu-id="2fdb1-132">ソフトウェア製品の名前</span><span class="sxs-lookup"><span data-stu-id="2fdb1-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="2fdb1-133">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-133">string</span></span> | <span data-ttu-id="2fdb1-134">ソフトウェア製品のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="2fdb1-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="2fdb1-135">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-135">string</span></span> | <span data-ttu-id="2fdb1-136">指定したサポート終了日 (EOS) または終了日 (EOL) を基準にしたソフトウェア製品のライフサイクル ステージを示します。</span><span class="sxs-lookup"><span data-stu-id="2fdb1-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="2fdb1-137">string</span><span class="sxs-lookup"><span data-stu-id="2fdb1-137">string</span></span> | <span data-ttu-id="2fdb1-138">ソフトウェア製品のサポート終了日 (EOS) または終了日 (EOL)</span><span class="sxs-lookup"><span data-stu-id="2fdb1-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="2fdb1-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fdb1-139">Related topics</span></span>

- [<span data-ttu-id="2fdb1-140">積極的に脅威を捜索する</span><span class="sxs-lookup"><span data-stu-id="2fdb1-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2fdb1-141">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="2fdb1-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2fdb1-142">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="2fdb1-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2fdb1-143">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="2fdb1-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2fdb1-144">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2fdb1-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2fdb1-145">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="2fdb1-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2fdb1-146">脅威および脆弱性管理の概要</span><span class="sxs-lookup"><span data-stu-id="2fdb1-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
