---
title: SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: この記事では、SIEM server と Microsoft 365 との統合の概要について説明します。
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677510"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="f6938-103">SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="f6938-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="f6938-104">Summary</span><span class="sxs-lookup"><span data-stu-id="f6938-104">Summary</span></span>

<span data-ttu-id="f6938-105">組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用している場合、または SIEM サーバーを近いうちに購入する予定の場合は、Microsoft 365 または Office 365 との統合について不思議に思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f6938-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f6938-106">この記事では、Microsoft 365 サービスとアプリケーションとの SIEM サーバー統合のセットアップに使用できるリソースの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f6938-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="f6938-107">SIEM サーバーがまだなく、オプションを調査している場合は、 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f6938-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="f6938-108">SIEM サーバーは必要ですか?</span><span class="sxs-lookup"><span data-stu-id="f6938-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="f6938-109">SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの格納場所など、さまざまな要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f6938-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="f6938-110">Microsoft 365 には、SIEM サーバーのような追加のサーバーを使用せずに、多くの組織のセキュリティニーズに合ったさまざまなセキュリティ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6938-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="f6938-111">組織によっては、SIEM サーバーの使用を必要とする特別な状況があります。</span><span class="sxs-lookup"><span data-stu-id="f6938-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="f6938-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f6938-112">Here are some examples:</span></span>

- <span data-ttu-id="f6938-113">*Fabrikam*には、オンプレミスのコンテンツとアプリケーションがあります。クラウドには、ハイブリッドクラウド展開があります。</span><span class="sxs-lookup"><span data-stu-id="f6938-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="f6938-114">すべてのコンテンツとアプリケーションでセキュリティレポートを取得するために、Fabrikam は SIEM サーバーを実装しています。</span><span class="sxs-lookup"><span data-stu-id="f6938-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="f6938-115">*Contoso 社*は、特に厳しいセキュリティ要件を持つ金融サービス組織です。</span><span class="sxs-lookup"><span data-stu-id="f6938-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="f6938-116">SIEM サーバーを環境に追加して、必要な追加のセキュリティ保護を利用しています。</span><span class="sxs-lookup"><span data-stu-id="f6938-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="f6938-117">SIEM server と Microsoft 365 の統合</span><span class="sxs-lookup"><span data-stu-id="f6938-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="f6938-118">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="f6938-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="f6938-119">次の表に、SIEM サーバーの入力と共に Microsoft 365 サービスとアプリケーションをいくつかと、SIEM サーバー統合の詳細を理解するためのリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="f6938-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="f6938-120">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f6938-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="f6938-121">SIEM サーバーの入力</span><span class="sxs-lookup"><span data-stu-id="f6938-121">SIEM server inputs</span></span> | <span data-ttu-id="f6938-122">追加情報</span><span class="sxs-lookup"><span data-stu-id="f6938-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="f6938-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f6938-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="f6938-124">監査ログ</span><span class="sxs-lookup"><span data-stu-id="f6938-124">Audit logs</span></span> | [<span data-ttu-id="f6938-125">Office 365 Advanced Threat Protection との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="f6938-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="f6938-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f6938-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="f6938-127">Azure でホストされている HTTPS エンドポイント</span><span class="sxs-lookup"><span data-stu-id="f6938-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="f6938-128">REST API</span><span class="sxs-lookup"><span data-stu-id="f6938-128">REST API</span></span>| [<span data-ttu-id="f6938-129">SIEM ツールに通知を取得する</span><span class="sxs-lookup"><span data-stu-id="f6938-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="f6938-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f6938-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="f6938-131">ログの統合</span><span class="sxs-lookup"><span data-stu-id="f6938-131">Log integration</span></span> | [<span data-ttu-id="f6938-132">SIEM と Microsoft Cloud App Security との統合</span><span class="sxs-lookup"><span data-stu-id="f6938-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="f6938-133">「 [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)」に目を通してください。これには、microsoft のソリューションのためのさまざまなコネクタが用意されており、Microsoft の脅威保護ソリューションや microsoft の365ソース (Office 365、azure AD、azure ATP、Microsoft Cloud App Security など) を含むリアルタイム統合が提供されています。</span><span class="sxs-lookup"><span data-stu-id="f6938-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="f6938-134">監査ログを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="f6938-134">Audit logging must be turned on</span></span>

<span data-ttu-id="f6938-135">SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6938-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="f6938-136">SharePoint Online、OneDrive for Business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。</span><span class="sxs-lookup"><span data-stu-id="f6938-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="f6938-137">Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。</span><span class="sxs-lookup"><span data-stu-id="f6938-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="f6938-138">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="f6938-138">Additional resources</span></span>

[<span data-ttu-id="f6938-139">Azure セキュリティセンターでのセキュリティソリューションの統合</span><span class="sxs-lookup"><span data-stu-id="f6938-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="f6938-140">Microsoft Graph Security API の警告と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="f6938-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)