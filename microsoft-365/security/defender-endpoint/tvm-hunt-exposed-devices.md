---
title: 露出したデバイスの追求
description: セキュリティ管理者、IT 管理者、および SecOps の共同作業に脅威と脆弱性の管理を使用する方法について説明します。
keywords: mdatp-tvm のシナリオ、mdatp、tvm、tvm のシナリオ、脅威& の脆弱性の暴露を減らす、脅威と脆弱性を軽減する、セキュリティ構成を改善する、デバイスの Microsoft Secure Score を増やす、デバイスの脅威 & の脆弱性を増やす Microsoft Secure Score、Microsoft Secure Score for Devices、露出スコア、セキュリティコントロール
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8e3a80e73d9847837ae0a1542e7d16ee8ae0f29
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500089"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="716c6-104">公開されているデバイスを探す - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="716c6-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="716c6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="716c6-105">**Applies to:**</span></span>

- [<span data-ttu-id="716c6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="716c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="716c6-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="716c6-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="716c6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="716c6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="716c6-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="716c6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="716c6-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="716c6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="716c6-111">高度な検索を使用して脆弱性のあるデバイスを検索する</span><span class="sxs-lookup"><span data-stu-id="716c6-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="716c6-112">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="716c6-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="716c6-113">ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを特定できます。</span><span class="sxs-lookup"><span data-stu-id="716c6-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="716c6-114">データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する拘束されていない検出が可能です。</span><span class="sxs-lookup"><span data-stu-id="716c6-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="716c6-115">高度な狩猟の詳細</span><span class="sxs-lookup"><span data-stu-id="716c6-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="716c6-116">スキーマ テーブル</span><span class="sxs-lookup"><span data-stu-id="716c6-116">Schema tables</span></span>

- <span data-ttu-id="716c6-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - デバイスにインストールされているソフトウェアのインベントリ (バージョン情報やサポート終了の状態を含む)。</span><span class="sxs-lookup"><span data-stu-id="716c6-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="716c6-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - デバイスで見つかったソフトウェアの脆弱性と、各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧。</span><span class="sxs-lookup"><span data-stu-id="716c6-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="716c6-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - 悪用コードが一般に公開されているかどうかを含む、一般に公開された脆弱性のナレッジ ベース。</span><span class="sxs-lookup"><span data-stu-id="716c6-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="716c6-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理評価イベント。</span><span class="sxs-lookup"><span data-stu-id="716c6-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="716c6-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Threat & 脆弱性管理でデバイスを評価するために使用されるさまざまなセキュリティ構成のナレッジ ベース。さまざまな標準とベンチマークへのマッピングが含まれています</span><span class="sxs-lookup"><span data-stu-id="716c6-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="716c6-122">重大度の高いアラートに関係するデバイスを確認する</span><span class="sxs-lookup"><span data-stu-id="716c6-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="716c6-123">Microsoft Defender **セキュリティ センターの** 左側のナビゲーション ウィンドウから [高度な検索] に移動します。</span><span class="sxs-lookup"><span data-stu-id="716c6-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="716c6-124">TVM 高度なハンティング スキーマまで下にスクロールして、列名を理解します。</span><span class="sxs-lookup"><span data-stu-id="716c6-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="716c6-125">次のクエリを入力します。</span><span class="sxs-lookup"><span data-stu-id="716c6-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="716c6-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="716c6-126">Related topics</span></span>

- [<span data-ttu-id="716c6-127">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="716c6-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="716c6-128">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="716c6-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="716c6-129">API</span><span class="sxs-lookup"><span data-stu-id="716c6-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="716c6-130">脅威と脆弱性管理の役割のデータ アクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="716c6-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="716c6-131">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="716c6-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="716c6-132">すべての高度な検索テーブル</span><span class="sxs-lookup"><span data-stu-id="716c6-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
