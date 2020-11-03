---
title: SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Microsoft 365 クラウドサービスおよびアプリケーションとのセキュリティ情報およびイベント管理 (SIEM) サーバーの統合の概要を理解する
ms.openlocfilehash: 0e582333615d11c500b114225435903cea386ade
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846402"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="09e22-103">セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 のサービスおよびアプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="09e22-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="09e22-104">要約</span><span class="sxs-lookup"><span data-stu-id="09e22-104">Summary</span></span>

<span data-ttu-id="09e22-105">組織は、セキュリティ情報およびイベント管理 (SIEM) サーバーの取得を使用または計画していますか。</span><span class="sxs-lookup"><span data-stu-id="09e22-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="09e22-106">Microsoft 365 または Office 365 との統合について疑問があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="09e22-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="09e22-107">この記事では、SIEM サーバーと Microsoft 365 のサービスおよびアプリケーションを統合するために使用できるリソースの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="09e22-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="09e22-108">SIEM サーバーがまだなく、オプションを調査している場合は、 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** を検討してください。</span><span class="sxs-lookup"><span data-stu-id="09e22-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="09e22-109">SIEM サーバーは必要ですか?</span><span class="sxs-lookup"><span data-stu-id="09e22-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="09e22-110">SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの格納場所など、さまざまな要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="09e22-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="09e22-111">Microsoft 365 には、SIEM サーバーのような追加のサーバーを使用せずに、多くの組織のセキュリティニーズに合ったさまざまなセキュリティ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09e22-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="09e22-112">組織によっては、SIEM サーバーの使用を必要とする特別な状況があります。</span><span class="sxs-lookup"><span data-stu-id="09e22-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="09e22-113">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="09e22-113">Here are some examples:</span></span>

- <span data-ttu-id="09e22-114">*Fabrikam* には、オンプレミスのコンテンツとアプリケーションがあります。クラウドには、ハイブリッドクラウド展開があります。</span><span class="sxs-lookup"><span data-stu-id="09e22-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="09e22-115">すべてのコンテンツとアプリケーションでセキュリティレポートを取得するために、Fabrikam は SIEM サーバーを実装しています。</span><span class="sxs-lookup"><span data-stu-id="09e22-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="09e22-116">*Contoso 社* は、特に厳しいセキュリティ要件を持つ金融サービス組織です。</span><span class="sxs-lookup"><span data-stu-id="09e22-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="09e22-117">SIEM サーバーを環境に追加して、必要な追加のセキュリティ保護を利用しています。</span><span class="sxs-lookup"><span data-stu-id="09e22-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="09e22-118">SIEM server と Microsoft 365 の統合</span><span class="sxs-lookup"><span data-stu-id="09e22-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="09e22-119">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="09e22-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="09e22-120">次の表に、SIEM server のサービスとアプリケーションと、詳細について説明するリソースを365示します。</span><span class="sxs-lookup"><span data-stu-id="09e22-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="09e22-121">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="09e22-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="09e22-122">SIEM サーバーの入力/メソッド</span><span class="sxs-lookup"><span data-stu-id="09e22-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="09e22-123">追加情報</span><span class="sxs-lookup"><span data-stu-id="09e22-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="09e22-124">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="09e22-124">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="09e22-125">監査ログ</span><span class="sxs-lookup"><span data-stu-id="09e22-125">Audit logs</span></span>|[<span data-ttu-id="09e22-126">Office 365 用の Microsoft Defender との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="09e22-126">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="09e22-127">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="09e22-127">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="09e22-128">Azure でホストされている HTTPS エンドポイント</span><span class="sxs-lookup"><span data-stu-id="09e22-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="09e22-129">REST API</span><span class="sxs-lookup"><span data-stu-id="09e22-129">REST API</span></span>|[<span data-ttu-id="09e22-130">SIEM ツールに通知を取得する</span><span class="sxs-lookup"><span data-stu-id="09e22-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="09e22-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="09e22-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="09e22-132">ログの統合</span><span class="sxs-lookup"><span data-stu-id="09e22-132">Log integration</span></span>|[<span data-ttu-id="09e22-133">SIEM と Microsoft Cloud App Security との統合</span><span class="sxs-lookup"><span data-stu-id="09e22-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="09e22-134">[Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="09e22-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="09e22-135">Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。</span><span class="sxs-lookup"><span data-stu-id="09e22-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="09e22-136">これらのコネクタは、"すぐに使用可能" となり、リアルタイム統合のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="09e22-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="09e22-137">Azure Sentinel は、Microsoft 365 Defender ソリューションおよび Microsoft 365 サービスで使用できます。これには、Office 365、Azure AD、Id の Microsoft Defender、Microsoft Cloud App Security などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09e22-137">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="09e22-138">監査ログを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="09e22-138">Audit logging must be turned on</span></span>

<span data-ttu-id="09e22-139">SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09e22-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="09e22-140">SharePoint Online、OneDrive for Business、および Azure Active Directory で [は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](../../compliance/turn-audit-log-search-on-or-off.md)ています。</span><span class="sxs-lookup"><span data-stu-id="09e22-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="09e22-141">Exchange Online の場合は、「 [メールボックスの監査を管理](../../compliance/enable-mailbox-auditing.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09e22-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="09e22-142">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="09e22-142">More resources</span></span>

[<span data-ttu-id="09e22-143">Azure Defender でのセキュリティソリューションの統合 \*</span><span class="sxs-lookup"><span data-stu-id="09e22-143">Integrate security solutions in Azure Defender\*</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="09e22-144">Microsoft Graph Security API の警告と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="09e22-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
