---
title: High と DoD のネットワーク セキュリティOffice 365 GCC追加の要件
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '概要: Office 365 GCC DoD には追加のネットワーク セキュリティ要件があります'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926561"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="e1cba-103">Office 365 GCC High および DOD の追加のネットワーク セキュリティ要件</span><span class="sxs-lookup"><span data-stu-id="e1cba-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="e1cba-104">*この記事は、OFFICE 365 GCC DOD、Office 365、Microsoft 365 GCC、および DOD にMicrosoft 365します。*</span><span class="sxs-lookup"><span data-stu-id="e1cba-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="e1cba-105">Office 365 GCC高および DOD は、米国政府とそのサプライヤーおよび請負業者のニーズを満たす安全なクラウド環境です。</span><span class="sxs-lookup"><span data-stu-id="e1cba-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="e1cba-106">これらのクラウド環境には、サービスがアクセスを許可する外部エンドポイントに関する追加のネットワーク制限があります。</span><span class="sxs-lookup"><span data-stu-id="e1cba-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="e1cba-107">GCCフェデレーション ID またはハイブリッド共存の使用を計画している高値および DOD のお客様は、Microsoft が既存のオンプレミス展開への受信および/または送信アクセスを許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1cba-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="e1cba-108">これらのアクティビティの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e1cba-108">Examples of these activities include:</span></span>

* <span data-ttu-id="e1cba-109">フェデレーション ID の使用 (Active Directory フェデレーション サービスまたは同様のサポートされている STS を使用)</span><span class="sxs-lookup"><span data-stu-id="e1cba-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="e1cba-110">オンプレミスの展開とハイブリッド共存Exchange ServerまたはSkype for Business展開</span><span class="sxs-lookup"><span data-stu-id="e1cba-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="e1cba-111">オンプレミス システムからの既存のユーザー コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="e1cba-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="e1cba-112">サービスがオンプレミスのエンドポイントと通信するには、ネットワークの変更を行うエンジニアリングにOffice 365送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cba-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="e1cba-113">すべての要求は **3** 週間の SLA を持ち、必要なセキュリティとコンプライアンスの制御と展開パイプラインのために迅速に処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1cba-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="e1cba-114">これには、サービスに移行した後の初期オンボーディング ネットワーク要求と変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1cba-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="e1cba-115">ネットワーク チームがこのタイムラインを認識し、計画サイクルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cba-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="e1cba-116">次の情報をOffice 365 Government Allow-List[要求に電子](mailto:o365gwlt@microsoft.com)メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="e1cba-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="e1cba-117">**To**: [Office 365 Government Allow-List要求](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e1cba-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="e1cba-118">**From**: テナント管理者 - 送信メールが **テナント** のグローバル管理者連絡先と一致している必要があります</span><span class="sxs-lookup"><span data-stu-id="e1cba-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="e1cba-119">**電子メール** の件名 : Office 365 GCC高ネットワーク要求 - contoso.onmicrosoft.us (テナント名に置き換える)</span><span class="sxs-lookup"><span data-stu-id="e1cba-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="e1cba-120">メッセージの本文には、次のデータが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cba-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="e1cba-121">テナントMicrosoft Online Services名 (たとえば、contoso.onmicrosoft.com、fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="e1cba-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="e1cba-122">ネットワークの変更や無効なサブネットのフォローアップに関連する、Microsoft が通信中の通信用に通信する電子メール配布リスト</span><span class="sxs-lookup"><span data-stu-id="e1cba-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="e1cba-123">オンプレミスの展開とハイブリッドMicrosoft Teamsを使用するかどうかを示す</span><span class="sxs-lookup"><span data-stu-id="e1cba-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="e1cba-124">フェデレーション ID システムの外部アクセス可能な URL (sts.contoso.com など) と、CIDR 表記の IP アドレス範囲 (たとえば、</span><span class="sxs-lookup"><span data-stu-id="e1cba-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="e1cba-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="e1cba-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="e1cba-126">CIDR 表記のオンプレミス PKI 証明書失効リスト URL と IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="e1cba-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="e1cba-127">CIDR 表記でのオンプレミス展開Exchange Server外部アクセス可能な URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="e1cba-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="e1cba-128">CIDR 表記のオンプレミス展開Skype for Business外部アクセス可能な URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="e1cba-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="e1cba-129">セキュリティとコンプライアンスの理由から、要求に対する次の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e1cba-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="e1cba-130">テナントごとに 4 つのサブネット制限があります</span><span class="sxs-lookup"><span data-stu-id="e1cba-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="e1cba-131">サブネットは CIDR 表記 (10.1.1.0/28 など) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cba-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="e1cba-132">サブネット範囲は、サブネット範囲より大/24</span><span class="sxs-lookup"><span data-stu-id="e1cba-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="e1cba-133">商用 **クラウド** サービス (商用クラウド サービス、Google G-Suite、Amazon Web Services など) へのアクセスを許可する要求Office 365対応できません。</span><span class="sxs-lookup"><span data-stu-id="e1cba-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="e1cba-134">要求が Microsoft によって受信および承認されると、3 週間の SLA が実装され、迅速化できません。</span><span class="sxs-lookup"><span data-stu-id="e1cba-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="e1cba-135">要求を受け取った場合は最初の確認応答と、要求が完了すると最終的な確認応答が送信されます。</span><span class="sxs-lookup"><span data-stu-id="e1cba-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
