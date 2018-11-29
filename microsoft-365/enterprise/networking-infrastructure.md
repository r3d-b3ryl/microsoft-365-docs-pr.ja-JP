---
title: 'フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: " Microsoft 365 Enterprise のネットワーク インフラストラクチャを展開する手順。"
ms.openlocfilehash: d575d8c3156ac1fc1a8a2bca96c875d4587ebf05
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869260"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="04988-103">フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="04988-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="04988-p101">Microsoft 365 Enterprise には、Office 365 と、Enterprise Management + Security (EMS) の一部である Windows Intune が含まれています。この 2 つのクラウドベース サービスはいずれも、クライアント デバイスからインターネットまたは専用回線経由での接続のセキュリティ、パフォーマンス、信頼性に依存しています。これらのサービスをホストし、世界中のお客様が利用できるようにするため、Microsoft はパフォーマンスと統合を重視したネットワーク アーキテクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="04988-p101">Microsoft 365 Enterprise includes Office 365 and Windows Intune as part of Enterprise Management + Security (EMS). Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits. To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="04988-p102">このフェーズでは、Microsoft 365 Enterprise のクラウド サービスへの高パフォーマンス接続を作成するための主な検討事項について、順を追って説明します。概要については、「[Office 365 のネットワークの原則](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04988-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="04988-109">既にネットワーク インフラストラクチャを展開している場合は、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="04988-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="04988-110">Microsoft 365 Enterprise のネットワーク インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="04988-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="04988-111">Microsoft 365 Enterprise の要件と機能に対応したネットワーク インフラストラクチャを構築するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="04988-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="04988-112">Microsoft 365 のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="04988-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="04988-113">オフィスごとにローカルのインターネット接続を構成する</span><span class="sxs-lookup"><span data-stu-id="04988-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="04988-114">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="04988-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="04988-115">トラフィック バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="04988-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="04988-116">クライアントと Office 365 サービスのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="04988-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="04988-117">上記の手順が完了したら、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04988-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="04988-118">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="04988-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="04988-119">「[Microsoft Office 365 のネットワーク パフォーマンスを最適化する](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)」を参照すると、Microsoft が会社として、内部的にどのように Office 365 クラウド サービス用に Microsoft ネットワークを最適化しているかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="04988-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="04988-120">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="04988-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="04988-121">架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ネットワークを最適化](contoso-networking.md)している方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="04988-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="04988-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="04988-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="04988-123">Microsoft 365 のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="04988-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

