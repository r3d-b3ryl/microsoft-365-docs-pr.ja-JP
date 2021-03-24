---
title: Windows の概要の情報保護
ms.reviewer: ''
description: 機密情報を特定して保護するために Windows で情報保護がどのように機能するのかについて説明します。
keywords: 情報、保護、dlp、データ、損失、防止、保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6d8f76786d4ee0bb96221d765bc1c3de0523c391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065819"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="d3cc9-104">Windows の概要の情報保護</span><span class="sxs-lookup"><span data-stu-id="d3cc9-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3cc9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d3cc9-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3cc9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d3cc9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d3cc9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3cc9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d3cc9-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d3cc9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d3cc9-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="d3cc9-110">情報保護は、Microsoft 365 Enterprise スイートの不可欠な部分で、機密性の高いデータを安全に保ちながら、職場での生産性を実現するためのインテリジェントな保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="d3cc9-111">Microsoft Defender ATP と Microsoft Information Protection の統合方法に関するブログ記事を参照して、Windows デバイス上の機密データを検出、保護、 [監視します](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-111">Read our blog post about how [Microsoft Defender ATP integrates with Microsoft Information Protection to discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="d3cc9-112">Defender for Endpoint は、データの検出、分類、および保護に次のメソッドを適用します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="d3cc9-113">**データ検出** - 危険にさらされている Windows デバイス上の機密データを特定する</span><span class="sxs-lookup"><span data-stu-id="d3cc9-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="d3cc9-114">**データの分類** - コンプライアンス センターで管理される一般的な Microsoft Information Protection (MIP) ポリシーに基づいてデータOffice自動的&分類します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="d3cc9-115">自動分類を使用すると、エンド ユーザーが手動で分類していなくても、機密データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="d3cc9-116">データ検出とデータ分類</span><span class="sxs-lookup"><span data-stu-id="d3cc9-116">Data discovery and data classification</span></span>

<span data-ttu-id="d3cc9-117">Defender for Endpoint は、機密ラベルを持つファイルと機密情報の種類を含むファイルを自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="d3cc9-118">機密ラベルは機密コンテンツを分類し、保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="d3cc9-119">365 データ損失防止 (DLP) Office実装の機密情報の種類は、次の 2 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="d3cc9-120">既定値</span><span class="sxs-lookup"><span data-stu-id="d3cc9-120">Default</span></span>
- <span data-ttu-id="d3cc9-121">Custom</span><span class="sxs-lookup"><span data-stu-id="d3cc9-121">Custom</span></span>

<span data-ttu-id="d3cc9-122">既定の機密情報の種類には、銀行口座番号、社会保障番号、国内の ID などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="d3cc9-123">詳細については、「機密情報の [種類の検索方法」を参照してください](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-123">For more information, see [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="d3cc9-124">カスタム型は、ユーザーが定義する種類であり、異なる種類の機密情報 (従業員の ID やプロジェクト番号など) を保護するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="d3cc9-125">詳細については、「カスタム機密情報の [種類を作成する」を参照してください](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-125">For more information see, [Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="d3cc9-126">Windows デバイスでファイルが作成または編集されると、Defender for Endpoint はコンテンツをスキャンして、機密情報が含まれているか評価します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="d3cc9-127">ラベルまたは情報の種類を使用して Defender for Endpoint によって機密情報を含むファイルが検出された場合、デバイスから Azure Information Protection に自動的に転送するように、Azure Information Protection 統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![Azure Information Protection を使用した設定ページのイメージ](images/atp-settings-aip.png)

<span data-ttu-id="d3cc9-129">報告された信号は、Azure Information Protection - データ検出ダッシュボードで表示できます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="d3cc9-130">Azure Information Protection - データ検出ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d3cc9-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="d3cc9-131">このダッシュボードには、Defender for Endpoint と Azure Information Protection の両方によって検出されたデータの要約された検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="d3cc9-132">Defender for Endpoint のデータは、場所の種類 - エンドポイントでマークされます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Azure Information Protection のイメージ - データ検出](images/azure-data-discovery.png)

<span data-ttu-id="d3cc9-134">右側の [デバイス リスク] 列に注意してください。このデバイス リスクは Defender for Endpoint から直接派生し、Defender for Endpoint によって検出されたアクティブなセキュリティ脅威に基づいて、ファイルが検出されたセキュリティ デバイスのリスク レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="d3cc9-135">デバイスをクリックすると、このデバイスで観察されたファイルの一覧が表示され、そのデバイスの感度ラベルと情報の種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="d3cc9-136">Azure Information Protection Dashboard Discovery が検出されたファイルを反映するには、約 15 ~ 20 分かかります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="d3cc9-137">Log Analytics</span><span class="sxs-lookup"><span data-stu-id="d3cc9-137">Log Analytics</span></span>

<span data-ttu-id="d3cc9-138">Defender for Endpoint に基づくデータ検出は [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)でも利用できます。ここで、生データに対して複雑なクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="d3cc9-139">Azure Information Protection analytics の詳細については、「Azure Information Protection の中央 [レポート」を参照してください](https://docs.microsoft.com/azure/information-protection/reports-aip)。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="d3cc9-140">Azure portal で Azure Log Analytics を開き、クエリ ビルダー (標準またはクラシック) を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="d3cc9-141">Defender for Endpoint データを表示するには、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="d3cc9-142">**前提条件:**</span><span class="sxs-lookup"><span data-stu-id="d3cc9-142">**Prerequisites:**</span></span>

- <span data-ttu-id="d3cc9-143">お客様は Azure Information Protection のサブスクリプションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="d3cc9-144">Microsoft Defender セキュリティ センターで Azure Information Protection の統合を有効にする:</span><span class="sxs-lookup"><span data-stu-id="d3cc9-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="d3cc9-145">[Microsoft Defender **セキュリティ センターの** 設定] に移動し、[全般] の [**詳細設定] を\*\*\*\*クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



