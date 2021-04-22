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
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="a5eb4-104">エンドポイント向け Microsoft Defender および他の Microsoft ソリューション</span><span class="sxs-lookup"><span data-stu-id="a5eb4-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a5eb4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a5eb4-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5eb4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5eb4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a5eb4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5eb4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5eb4-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="a5eb4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5eb4-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="a5eb4-110">他の Microsoft ソリューションとの統合</span><span class="sxs-lookup"><span data-stu-id="a5eb4-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="a5eb4-111">Microsoft Defender for Endpoint は、さまざまな Microsoft ソリューションと直接統合します。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="a5eb4-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="a5eb4-112">Azure Defender</span></span>
<span data-ttu-id="a5eb4-113">Microsoft Defender for Endpoint は、Windows サーバー上のエンドポイント検出および応答 (EDR) 機能を含む包括的なサーバー保護ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="a5eb4-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="a5eb4-114">Azure Sentinel</span></span>
<span data-ttu-id="a5eb4-115">Microsoft Defender for Endpoint コネクタを使用すると、Microsoft Defender for Endpoint から Azure Sentinel にアラートをストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="a5eb4-116">これにより、組織全体のセキュリティ イベントをより包括的に分析し、プレイブックを構築して効果的かつ迅速に対応できます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="a5eb4-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="a5eb4-117">Azure Information Protection</span></span>
<span data-ttu-id="a5eb4-118">エンドポイント DLP 機能には、ソリューション間の可視性と統合を容易にするエンドポイント デバイスに保存されている機密データの検出と保護ソリューションが強化されたので、Azure Information Protection の統合は最近廃止されました。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="a5eb4-119">これは、次のブログで発表 [されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="a5eb4-120">エンドポイント DLP の使用に移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="a5eb4-121">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="a5eb4-121">Conditional Access</span></span>
<span data-ttu-id="a5eb4-122">Microsoft Defender for Endpoint の動的デバイス リスク スコアは条件付きアクセス評価に統合され、セキュリティで保護されたデバイスだけがリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="a5eb4-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a5eb4-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="a5eb4-124">Microsoft Cloud App Security では、Microsoft Defender for Endpoint エンドポイント信号を活用して、サポートされていないクラウド サービス (シャドウ IT) をすべての Microsoft Defender for Endpoint 監視対象デバイスから使用するなど、クラウド アプリケーションの使用状況を直接可視化できます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="a5eb4-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a5eb4-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="a5eb4-126">疑わしいアクティビティは、ユーザー コンテキストで実行されているプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="a5eb4-127">Microsoft Defender for Endpoint と Microsoft Defender for Identity の統合により、アクティビティと ID 全体でサイバーセキュリティ調査を柔軟に実施できます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="a5eb4-128">Microsoft Defender for Office</span><span class="sxs-lookup"><span data-stu-id="a5eb4-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="a5eb4-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) は、安全なリンク、安全な添付ファイル、高度なフィッシング対策、スプーフィング インテリジェンス機能を通じて、電子メール メッセージまたはファイル内のマルウェアから組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="a5eb4-130">Microsoft Defender for Office 365 と Microsoft Defender for Endpoint の統合により、セキュリティ アナリストは攻撃のエントリ ポイントを調査するために上流に移動できます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="a5eb4-131">脅威インテリジェンスの共有を通じて、攻撃を封じ込め、ブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="a5eb4-132">過去 30 Office内のイベントに対して、365 データの Defender が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="a5eb4-133">アラートの場合、365 Officeの Defender は、最初のアクティビティ時間に基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="a5eb4-134">その後、データは Defender で 365 以降Officeされます。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="a5eb4-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a5eb4-135">Skype for Business</span></span>
<span data-ttu-id="a5eb4-136">Skype for Business 統合は、アナリストがポータルから簡単なボタンを使用して、侵害される可能性のあるユーザーまたはデバイスの所有者と通信する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="a5eb4-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5eb4-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="a5eb4-138">Microsoft 365 Defender を使用すると、Microsoft Defender for Endpoint とさまざまな Microsoft セキュリティ ソリューションが統合された侵害前および侵害後のエンタープライズ防御スイートを形成し、エンドポイント、ID、電子メール、およびアプリケーション間でネイティブに統合され、高度な攻撃を検出、防止、調査、および自動的に対応します。</span><span class="sxs-lookup"><span data-stu-id="a5eb4-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="a5eb4-139">Microsoft 365 Defender の詳細</span><span class="sxs-lookup"><span data-stu-id="a5eb4-139">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="a5eb4-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5eb4-140">Related topics</span></span>
- [<span data-ttu-id="a5eb4-141">統合などの高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="a5eb4-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="a5eb4-142">Microsoft 365 Defender の概要</span><span class="sxs-lookup"><span data-stu-id="a5eb4-142">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="a5eb4-143">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="a5eb4-143">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="a5eb4-144">条件付きアクセスを使用してユーザー、データ、デバイスを保護する</span><span class="sxs-lookup"><span data-stu-id="a5eb4-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
