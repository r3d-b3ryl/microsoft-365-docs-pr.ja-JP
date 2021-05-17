---
title: エンドポイント用 Microsoft Defender を他の Microsoft ソリューションと統合する
description: Microsoft Defender for Endpoint が、Microsoft Defender for Identity や Azure Defender を含む他の Microsoft ソリューションと統合する方法について説明します。
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, 条件付きアクセス, office, エンドポイント用 Microsoft Defender, id 用 microsoft Defender, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935535"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="442fa-104">エンドポイント向け Microsoft Defender および他の Microsoft ソリューション</span><span class="sxs-lookup"><span data-stu-id="442fa-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="442fa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="442fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="442fa-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="442fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="442fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="442fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="442fa-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="442fa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="442fa-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="442fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="442fa-110">他の Microsoft ソリューションとの統合</span><span class="sxs-lookup"><span data-stu-id="442fa-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="442fa-111">Microsoft Defender for Endpoint は、さまざまな Microsoft ソリューションと直接統合します。</span><span class="sxs-lookup"><span data-stu-id="442fa-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="442fa-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="442fa-112">Azure Defender</span></span>
<span data-ttu-id="442fa-113">Microsoft Defender for Endpoint は、エンドポイント検出と応答 (EDR) 機能を含む包括的なサーバー保護ソリューションをWindowsします。</span><span class="sxs-lookup"><span data-stu-id="442fa-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="442fa-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="442fa-114">Azure Sentinel</span></span>
<span data-ttu-id="442fa-115">Microsoft Defender for Endpoint コネクタを使用すると、Microsoft Defender for Endpoint から Azure Sentinel にアラートをストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="442fa-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="442fa-116">これにより、組織全体のセキュリティ イベントをより包括的に分析し、プレイブックを構築して効果的かつ迅速に対応できます。</span><span class="sxs-lookup"><span data-stu-id="442fa-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="442fa-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="442fa-117">Azure Information Protection</span></span>
<span data-ttu-id="442fa-118">エンドポイント DLP 機能には、ソリューション間の可視性と統合を容易にするエンドポイント デバイスに保存されている機密データの検出と保護ソリューションが強化されたので、Azure Information Protection の統合は最近廃止されました。</span><span class="sxs-lookup"><span data-stu-id="442fa-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="442fa-119">これは、次のブログで発表 [されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)。</span><span class="sxs-lookup"><span data-stu-id="442fa-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="442fa-120">エンドポイント DLP の使用に移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="442fa-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="442fa-121">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="442fa-121">Conditional Access</span></span>
<span data-ttu-id="442fa-122">Microsoft Defender for Endpoint の動的デバイス リスク スコアは条件付きアクセス評価に統合され、セキュリティで保護されたデバイスだけがリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="442fa-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="442fa-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="442fa-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="442fa-124">Microsoft Cloud App Securityは、Microsoft Defender for Endpoint エンドポイント信号を活用して、すべての Microsoft Defender for Endpoint 監視対象デバイスからサポートされていないクラウド サービス (シャドウ IT) の使用を含む、クラウド アプリケーションの使用状況を直接可視化できます。</span><span class="sxs-lookup"><span data-stu-id="442fa-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="442fa-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="442fa-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="442fa-126">疑わしいアクティビティは、ユーザー コンテキストで実行されているプロセスです。</span><span class="sxs-lookup"><span data-stu-id="442fa-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="442fa-127">Microsoft Defender for Endpoint と Microsoft Defender for Identity の統合により、アクティビティと ID 全体でサイバーセキュリティ調査を柔軟に実施できます。</span><span class="sxs-lookup"><span data-stu-id="442fa-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="442fa-128">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="442fa-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="442fa-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)は、セーフ リンク、セーフ 添付ファイル、高度なフィッシング対策、スプーフィング インテリジェンス機能を通じて、電子メール メッセージまたはファイル内のマルウェアから組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="442fa-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="442fa-130">Microsoft Defender for Office 365 と Microsoft Defender for Endpoint の統合により、セキュリティ アナリストは攻撃のエントリ ポイントを調査するために上流に移動できます。</span><span class="sxs-lookup"><span data-stu-id="442fa-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="442fa-131">脅威インテリジェンスの共有を通じて、攻撃を封じ込め、ブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="442fa-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="442fa-132">過去 30 日以内Office 365データの Defender が表示されます。</span><span class="sxs-lookup"><span data-stu-id="442fa-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="442fa-133">アラートの場合、最初のOffice 365に基づいて、データの Defender が表示されます。</span><span class="sxs-lookup"><span data-stu-id="442fa-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="442fa-134">その後、データは Defender で使用できなくなりました。Office 365。</span><span class="sxs-lookup"><span data-stu-id="442fa-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="442fa-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="442fa-135">Skype for Business</span></span>
<span data-ttu-id="442fa-136">このSkype for Business統合により、アナリストはポータルからの簡単なボタンを使用して、侵害される可能性のあるユーザーまたはデバイスの所有者と通信できます。</span><span class="sxs-lookup"><span data-stu-id="442fa-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="442fa-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="442fa-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="442fa-138">Microsoft 365 Defender を使用すると、Microsoft Defender for Endpoint とさまざまな Microsoft セキュリティ ソリューションが統合された侵害前および侵害後のエンタープライズ防御スイートを形成し、エンドポイント、ID、電子メール、およびアプリケーション間でネイティブに統合され、高度な攻撃を検出、防止、調査、および自動的に対応します。</span><span class="sxs-lookup"><span data-stu-id="442fa-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="442fa-139">Defender の詳細Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="442fa-139">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="442fa-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="442fa-140">Related topics</span></span>
- [<span data-ttu-id="442fa-141">統合などの高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="442fa-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="442fa-142">Microsoft 365Defender の概要</span><span class="sxs-lookup"><span data-stu-id="442fa-142">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="442fa-143">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="442fa-143">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="442fa-144">条件付きアクセスを使用してユーザー、データ、デバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="442fa-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
