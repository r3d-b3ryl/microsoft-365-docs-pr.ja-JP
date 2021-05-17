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
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691911"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="cc9b3-103">Office 365 GCC High および DOD の追加のネットワーク セキュリティ要件</span><span class="sxs-lookup"><span data-stu-id="cc9b3-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="cc9b3-104">*この記事は、OFFICE 365 GCC DOD、Office 365、Microsoft 365 GCC、および DOD にMicrosoft 365します。*</span><span class="sxs-lookup"><span data-stu-id="cc9b3-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="cc9b3-105">Office 365 GCC高および DOD は、米国政府とそのサプライヤーおよび請負業者のニーズを満たす安全なクラウド環境です。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="cc9b3-106">これらのクラウド環境には、サービスがアクセスを許可する外部エンドポイントに関する追加のネットワーク制限があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="cc9b3-107">GCCフェデレーション ID またはハイブリッドの共同利用を計画している高値および DOD のお客様は、Microsoft が既存のオンプレミス展開への受信および/または送信アクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="cc9b3-108">これらのアクティビティの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-108">Examples of these activities include:</span></span>

* <span data-ttu-id="cc9b3-109">フェデレーション ID の使用 (Active Directory フェデレーション サービスまたは同様のサポートされている STS を使用)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="cc9b3-110">オンプレミスの展開とハイブリッド共存Exchange ServerまたはSkype for Business展開</span><span class="sxs-lookup"><span data-stu-id="cc9b3-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="cc9b3-111">オンプレミス システムからの既存のユーザー コンテンツの移行</span><span class="sxs-lookup"><span data-stu-id="cc9b3-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="cc9b3-112">サービスがオンプレミスのエンドポイントと通信するには、ネットワークの変更を行うエンジニアリングにOffice 365送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="cc9b3-113">すべての要求は **3** 週間の SLA を持ち、必要なセキュリティとコンプライアンスの制御と展開パイプラインのために迅速に処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="cc9b3-114">これには、サービスに移行した後の初期オンボーディング ネットワーク要求と変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="cc9b3-115">ネットワーク チームがこのタイムラインを認識し、計画サイクルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="cc9b3-116">ネットワーク ホワイトリストに次[Office 365 Governmentメール](mailto:o365gwlt@microsoft.com)を送信してください。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="cc9b3-117">**To**: Office 365 Government [ホワイトリスト](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="cc9b3-118">**From**: テナント管理者 - 送信メールが **テナント** のグローバル管理者連絡先と一致している必要があります</span><span class="sxs-lookup"><span data-stu-id="cc9b3-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="cc9b3-119">**電子メール** の件名 : Office 365 GCC高ネットワーク要求 - contoso.onmicrosoft.us (テナント名に置き換えてください)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="cc9b3-120">メッセージの本文には、次のデータが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="cc9b3-121">テナントMicrosoft Online Services名 (つまり、contoso.onmicrosoft.com、fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="cc9b3-122">ネットワークの変更や無効なサブネットのフォローアップに関連する、Microsoft が通信中の通信用に通信する電子メール配布リスト</span><span class="sxs-lookup"><span data-stu-id="cc9b3-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="cc9b3-123">オンプレミスの展開とハイブリッドMicrosoft Teamsを使用するかどうかを示す</span><span class="sxs-lookup"><span data-stu-id="cc9b3-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="cc9b3-124">フェデレーション ID システムの外部アクセス可能な URL (sts.contoso.com など) と CIDR 表記の IP アドレス範囲 (例: 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="cc9b3-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="cc9b3-125">CIDR 表記のオンプレミス PKI 証明書失効リスト URL と IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="cc9b3-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="cc9b3-126">CIDR 表記でのオンプレミス展開Exchange Server外部アクセス可能な URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="cc9b3-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="cc9b3-127">CIDR 表記のオンプレミス展開Skype for Business外部アクセス可能な URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="cc9b3-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="cc9b3-128">セキュリティとコンプライアンスの理由から、要求に対する次の制限に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="cc9b3-129">テナントごとに 4 つのサブネット制限があります</span><span class="sxs-lookup"><span data-stu-id="cc9b3-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="cc9b3-130">サブネットは CIDR 表記 (10.1.1.0/28 など) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="cc9b3-131">サブネット範囲は、サブネット範囲より大/24</span><span class="sxs-lookup"><span data-stu-id="cc9b3-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="cc9b3-132">商用 **クラウド** サービス (商用クラウド サービス、Google G-Suite、Amazon Web Services など) へのアクセスを許可する要求Office 365対応できません。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="cc9b3-133">要求が Microsoft によって受信および承認されると、3 週間の SLA が実装され、迅速化できません。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="cc9b3-134">要求を受け取った場合は最初の確認応答を受け取り、完了したら最終的な確認を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9b3-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
