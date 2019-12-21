---
title: " セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 のサービスおよびアプリケーションとの統合"
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
description: Microsoft 365 クラウドサービスおよびアプリケーションとのセキュリティ情報およびイベント管理 (SIEM) サーバーの統合の概要を理解する
ms.openlocfilehash: b91d45235b61ff6a3c57ec70f3e6a8fee0fd39d2
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "38699597"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="e9749-103">セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 のサービスおよびアプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="e9749-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="e9749-104">概要</span><span class="sxs-lookup"><span data-stu-id="e9749-104">Summary</span></span>

<span data-ttu-id="e9749-105">組織は、セキュリティ情報およびイベント管理 (SIEM) サーバーの取得を使用または計画していますか。</span><span class="sxs-lookup"><span data-stu-id="e9749-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="e9749-106">Microsoft 365 または Office 365 との統合について疑問があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e9749-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e9749-107">この記事では、SIEM サーバーと Microsoft 365 のサービスおよびアプリケーションを統合するために使用できるリソースの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e9749-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="e9749-108">SIEM サーバーがまだなく、オプションを調査している場合は、 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e9749-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="e9749-109">SIEM サーバーは必要ですか?</span><span class="sxs-lookup"><span data-stu-id="e9749-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="e9749-110">SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの格納場所など、さまざまな要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9749-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="e9749-111">Microsoft 365 には、SIEM サーバーのような追加のサーバーを使用せずに、多くの組織のセキュリティニーズに合ったさまざまなセキュリティ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9749-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="e9749-112">組織によっては、SIEM サーバーの使用を必要とする特別な状況があります。</span><span class="sxs-lookup"><span data-stu-id="e9749-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="e9749-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e9749-113">Here are some examples:</span></span>

- <span data-ttu-id="e9749-114">*Fabrikam*には、オンプレミスのコンテンツとアプリケーションがあります。クラウドには、ハイブリッドクラウド展開があります。</span><span class="sxs-lookup"><span data-stu-id="e9749-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="e9749-115">すべてのコンテンツとアプリケーションでセキュリティレポートを取得するために、Fabrikam は SIEM サーバーを実装しています。</span><span class="sxs-lookup"><span data-stu-id="e9749-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="e9749-116">*Contoso 社*は、特に厳しいセキュリティ要件を持つ金融サービス組織です。</span><span class="sxs-lookup"><span data-stu-id="e9749-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="e9749-117">SIEM サーバーを環境に追加して、必要な追加のセキュリティ保護を利用しています。</span><span class="sxs-lookup"><span data-stu-id="e9749-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="e9749-118">SIEM server と Microsoft 365 の統合</span><span class="sxs-lookup"><span data-stu-id="e9749-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="e9749-119">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="e9749-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="e9749-120">次の表に、SIEM server のサービスとアプリケーションと、詳細について説明するリソースを365示します。</span><span class="sxs-lookup"><span data-stu-id="e9749-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span> 

| <span data-ttu-id="e9749-121">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="e9749-121">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="e9749-122">SIEM サーバーの入力/メソッド</span><span class="sxs-lookup"><span data-stu-id="e9749-122">SIEM server inputs/methods</span></span> | <span data-ttu-id="e9749-123">追加情報</span><span class="sxs-lookup"><span data-stu-id="e9749-123">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="e9749-124">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e9749-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="e9749-125">監査ログ</span><span class="sxs-lookup"><span data-stu-id="e9749-125">Audit logs</span></span> | [<span data-ttu-id="e9749-126">Office 365 Advanced Threat Protection との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="e9749-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="e9749-127">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e9749-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="e9749-128">Azure でホストされている HTTPS エンドポイント</span><span class="sxs-lookup"><span data-stu-id="e9749-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="e9749-129">REST API</span><span class="sxs-lookup"><span data-stu-id="e9749-129">REST API</span></span>| [<span data-ttu-id="e9749-130">SIEM ツールに通知を取得する</span><span class="sxs-lookup"><span data-stu-id="e9749-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="e9749-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e9749-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="e9749-132">ログの統合</span><span class="sxs-lookup"><span data-stu-id="e9749-132">Log integration</span></span> | [<span data-ttu-id="e9749-133">SIEM と Microsoft Cloud App Security との統合</span><span class="sxs-lookup"><span data-stu-id="e9749-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="e9749-134">[Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="e9749-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="e9749-135">Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。</span><span class="sxs-lookup"><span data-stu-id="e9749-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="e9749-136">これらのコネクタは、"すぐに使用可能" となり、リアルタイム統合のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="e9749-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="e9749-137">Microsoft の脅威保護ソリューションおよび Microsoft 365 サービスでは、Office 365、Azure AD、Azure ATP、Microsoft Cloud App Security などを含む Azure Sentinel を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9749-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="e9749-138">監査ログを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="e9749-138">Audit logging must be turned on</span></span>

<span data-ttu-id="e9749-139">SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e9749-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="e9749-140">SharePoint Online、OneDrive for Business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。</span><span class="sxs-lookup"><span data-stu-id="e9749-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="e9749-141">Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。</span><span class="sxs-lookup"><span data-stu-id="e9749-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="more-resources"></a><span data-ttu-id="e9749-142">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="e9749-142">More resources</span></span>

[<span data-ttu-id="e9749-143">Azure セキュリティセンターでのセキュリティソリューションの統合</span><span class="sxs-lookup"><span data-stu-id="e9749-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="e9749-144">Microsoft Graph Security API の警告と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="e9749-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)