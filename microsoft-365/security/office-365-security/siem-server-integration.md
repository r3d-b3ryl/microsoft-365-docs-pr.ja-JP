---
title: SIEM サーバーと Microsoft 365 サービスおよびアプリケーションの統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 クラウド サービスおよびアプリケーションの統合の概要を説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290383"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="0ef52-103">セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 サービスおよびアプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="0ef52-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="0ef52-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0ef52-104">**Applies to**</span></span>
- [<span data-ttu-id="0ef52-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ef52-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ef52-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0ef52-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0ef52-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ef52-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="0ef52-108">要約</span><span class="sxs-lookup"><span data-stu-id="0ef52-108">Summary</span></span>

<span data-ttu-id="0ef52-109">組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用するか、または取得を計画していますか。</span><span class="sxs-lookup"><span data-stu-id="0ef52-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="0ef52-110">Microsoft 365 または Office 365 と統合する方法を疑問に思う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ef52-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0ef52-111">この記事では、SIEM サーバーを Microsoft 365 サービスおよびアプリケーションと統合するために使用できるリソースの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0ef52-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="0ef52-112">SIEM サーバーをまだお持ちで、オプションを検討している場合は **[、Microsoft Azure Sentinel を検討してください](https://docs.microsoft.com/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="0ef52-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="0ef52-113">SIEM サーバーは必要ですか?</span><span class="sxs-lookup"><span data-stu-id="0ef52-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="0ef52-114">SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの保存場所など、多くの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0ef52-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="0ef52-115">Microsoft 365 には、SIEM サーバーなどの追加サーバーを使用せずに、多くの組織のセキュリティ ニーズを満たすさまざまなセキュリティ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ef52-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="0ef52-116">組織によっては、SIEM サーバーの使用が必要な特殊な状況があります。</span><span class="sxs-lookup"><span data-stu-id="0ef52-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="0ef52-117">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="0ef52-117">Here are some examples:</span></span>

- <span data-ttu-id="0ef52-118">*Fabrikam には* オンプレミスのコンテンツとアプリケーションと、クラウド内のコンテンツとアプリケーションがあります (ハイブリッド クラウド展開があります)。</span><span class="sxs-lookup"><span data-stu-id="0ef52-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="0ef52-119">Fabrikam は、すべてのコンテンツとアプリケーションのセキュリティ レポートを取得するために、SIEM サーバーを実装しています。</span><span class="sxs-lookup"><span data-stu-id="0ef52-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="0ef52-120">*Contoso* 社は、特に厳しいセキュリティ要件を持つ金融サービス組織です。</span><span class="sxs-lookup"><span data-stu-id="0ef52-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="0ef52-121">ユーザーは、必要な追加のセキュリティ保護を利用するために、環境に SIEM サーバーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="0ef52-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="0ef52-122">SIEM サーバーと Microsoft 365 の統合</span><span class="sxs-lookup"><span data-stu-id="0ef52-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="0ef52-123">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="0ef52-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="0ef52-124">次の表に、いくつかの Microsoft 365 サービスとアプリケーション、SIEM サーバーの入力、詳細を確認するリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="0ef52-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="0ef52-125">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0ef52-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="0ef52-126">SIEM サーバーの入力/メソッド</span><span class="sxs-lookup"><span data-stu-id="0ef52-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="0ef52-127">追加情報</span><span class="sxs-lookup"><span data-stu-id="0ef52-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="0ef52-128">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0ef52-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="0ef52-129">監査ログ</span><span class="sxs-lookup"><span data-stu-id="0ef52-129">Audit logs</span></span>|[<span data-ttu-id="0ef52-130">siem integration with Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0ef52-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="0ef52-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ef52-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="0ef52-132">Azure でホストされている HTTPS エンドポイント</span><span class="sxs-lookup"><span data-stu-id="0ef52-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="0ef52-133">REST API</span><span class="sxs-lookup"><span data-stu-id="0ef52-133">REST API</span></span>|[<span data-ttu-id="0ef52-134">SIEM ツールにアラートをプルする</span><span class="sxs-lookup"><span data-stu-id="0ef52-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="0ef52-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0ef52-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="0ef52-136">ログ統合</span><span class="sxs-lookup"><span data-stu-id="0ef52-136">Log integration</span></span>|[<span data-ttu-id="0ef52-137">SIEM と Microsoft Cloud App Security の統合</span><span class="sxs-lookup"><span data-stu-id="0ef52-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="0ef52-138">[Azure Sentinel を確認してください](https://docs.microsoft.com/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="0ef52-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="0ef52-139">Azure Sentinel には、Microsoft ソリューションのコネクタが付属しています。</span><span class="sxs-lookup"><span data-stu-id="0ef52-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="0ef52-140">これらのコネクタは、"既定で" 使用可能であり、リアルタイム統合を実現します。</span><span class="sxs-lookup"><span data-stu-id="0ef52-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="0ef52-141">Azure Sentinel は、Microsoft 365 Defender ソリューションと Microsoft 365 サービス (Office 365、Azure AD、Id 用 Microsoft Defender、Microsoft Cloud App Security など) と一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ef52-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="0ef52-142">監査ログを有効にする必要があります</span><span class="sxs-lookup"><span data-stu-id="0ef52-142">Audit logging must be turned on</span></span>

<span data-ttu-id="0ef52-143">SIEM サーバー統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ef52-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="0ef52-144">SharePoint Online、OneDrive for Business、および Azure Active Directory の場合、セキュリティ/コンプライアンス センターで監査 [ログ&オンになります](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef52-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="0ef52-145">Exchange Online については、「メールボックス監査 [の管理」を参照してください](../../compliance/enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef52-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="0ef52-146">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="0ef52-146">More resources</span></span>

[<span data-ttu-id="0ef52-147">Azure Defender でのセキュリティ ソリューションの統合</span><span class="sxs-lookup"><span data-stu-id="0ef52-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="0ef52-148">Microsoft Graph Security API の警告と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="0ef52-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
