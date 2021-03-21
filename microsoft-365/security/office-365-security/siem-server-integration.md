---
title: SIEM サーバーと Microsoft 365 サービスとアプリケーションの統合
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
description: Microsoft 365 クラウド サービスとアプリケーションとのセキュリティ情報とイベント管理 (SIEM) サーバーの統合の概要を確認する
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21aaad71f40a01a3bea2f9535d1c3256ae667bae
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916588"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="c6338-103">Microsoft 365 サービスおよびアプリケーションとのセキュリティ情報とイベント管理 (SIEM) サーバーの統合</span><span class="sxs-lookup"><span data-stu-id="c6338-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="c6338-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c6338-104">**Applies to**</span></span>
- [<span data-ttu-id="c6338-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c6338-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c6338-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c6338-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c6338-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6338-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="c6338-108">要約</span><span class="sxs-lookup"><span data-stu-id="c6338-108">Summary</span></span>

<span data-ttu-id="c6338-109">組織がセキュリティ情報とイベント管理 (SIEM) サーバーを使用または取得する計画を立てましたか?</span><span class="sxs-lookup"><span data-stu-id="c6338-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="c6338-110">Microsoft 365 または Microsoft 365 と統合する方法Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="c6338-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c6338-111">この記事では、SIEM サーバーと Microsoft 365 サービスおよびアプリケーションを統合するために使用できるリソースの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c6338-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="c6338-112">SIEM サーバーがまだない場合で、オプションを検討している場合は **[、Microsoft Azure Sentinel を検討してください](/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="c6338-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="c6338-113">SIEM サーバーが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="c6338-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="c6338-114">SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの場所など、多くの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c6338-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="c6338-115">Microsoft 365 には、SIEM サーバーなどの追加サーバーを使用せずに、多くの組織のセキュリティ ニーズを満たすさまざまなセキュリティ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6338-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="c6338-116">一部の組織では、SIEM サーバーの使用が必要な特別な状況があります。</span><span class="sxs-lookup"><span data-stu-id="c6338-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="c6338-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6338-117">Here are some examples:</span></span>

- <span data-ttu-id="c6338-118">*Fabrikam には* 、オンプレミスのコンテンツとアプリケーションと、クラウド内の一部があります (ハイブリッド クラウド展開があります)。</span><span class="sxs-lookup"><span data-stu-id="c6338-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="c6338-119">Fabrikam は、すべてのコンテンツとアプリケーションのセキュリティ レポートを取得するために、SIEM サーバーを実装しました。</span><span class="sxs-lookup"><span data-stu-id="c6338-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="c6338-120">*Contoso* は、特に厳しいセキュリティ要件を持つ金融サービス組織です。</span><span class="sxs-lookup"><span data-stu-id="c6338-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="c6338-121">ユーザーは、必要な追加のセキュリティ保護を利用するために、環境に SIEM サーバーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="c6338-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="c6338-122">SIEM サーバーと Microsoft 365 との統合</span><span class="sxs-lookup"><span data-stu-id="c6338-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="c6338-123">SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからデータを受信できます。</span><span class="sxs-lookup"><span data-stu-id="c6338-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="c6338-124">次の表に、いくつかの Microsoft 365 サービスとアプリケーション、および SIEM サーバーの入力と詳細を確認するリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="c6338-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="c6338-125">Microsoft 365 サービスまたはアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c6338-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="c6338-126">SIEM サーバーの入力/メソッド</span><span class="sxs-lookup"><span data-stu-id="c6338-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="c6338-127">追加情報</span><span class="sxs-lookup"><span data-stu-id="c6338-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="c6338-128">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c6338-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="c6338-129">監査ログ</span><span class="sxs-lookup"><span data-stu-id="c6338-129">Audit logs</span></span>|[<span data-ttu-id="c6338-130">SIEM との Microsoft Defender との統合 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="c6338-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="c6338-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c6338-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="c6338-132">Azure でホストされる HTTPS エンドポイント</span><span class="sxs-lookup"><span data-stu-id="c6338-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="c6338-133">REST API</span><span class="sxs-lookup"><span data-stu-id="c6338-133">REST API</span></span>|[<span data-ttu-id="c6338-134">SIEM ツールにアラートをプルする</span><span class="sxs-lookup"><span data-stu-id="c6338-134">Pull alerts to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="c6338-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c6338-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="c6338-136">ログの統合</span><span class="sxs-lookup"><span data-stu-id="c6338-136">Log integration</span></span>|[<span data-ttu-id="c6338-137">SIEM と Microsoft Cloud App Security の統合</span><span class="sxs-lookup"><span data-stu-id="c6338-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="c6338-138">[Azure Sentinel を見てみろ](/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="c6338-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="c6338-139">Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。</span><span class="sxs-lookup"><span data-stu-id="c6338-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="c6338-140">これらのコネクタは「箱から出して」利用できます。リアルタイムの統合を実現します。</span><span class="sxs-lookup"><span data-stu-id="c6338-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="c6338-141">Azure Sentinel は、Microsoft 365 Defender ソリューションと Microsoft 365 サービス (Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Cloud App Security など) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6338-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="c6338-142">監査ログを有効にする必要があります</span><span class="sxs-lookup"><span data-stu-id="c6338-142">Audit logging must be turned on</span></span>

<span data-ttu-id="c6338-143">SIEM サーバー統合を構成する前に、監査ログが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c6338-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="c6338-144">SharePoint Online、OneDrive for Business、Azure Active Directory の場合は、セキュリティ コンプライアンス センターで監査ログ [&オンになります](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="c6338-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="c6338-145">Exchange Online の場合は、「メールボックス監査 [の管理」を参照してください](../../compliance/enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="c6338-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="c6338-146">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="c6338-146">More resources</span></span>

[<span data-ttu-id="c6338-147">Azure Defender にセキュリティ ソリューションを統合する</span><span class="sxs-lookup"><span data-stu-id="c6338-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="c6338-148">Microsoft Graph Security API の警告と SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="c6338-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)