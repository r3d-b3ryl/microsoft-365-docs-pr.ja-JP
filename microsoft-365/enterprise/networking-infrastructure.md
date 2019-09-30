---
title: 'フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: " Microsoft 365 Enterprise のネットワーク インフラストラクチャを展開する手順。"
ms.openlocfilehash: 35c65515854bb0c47a45e48d8e3c6af6a80d907c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982798"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="82113-103">フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="82113-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="82113-104">Microsoft 365 Enterprise には、Office 365、Microsoft Intune、および Microsoft Azure の多くの ID やセキュリティ サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82113-104">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="82113-105">これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。</span><span class="sxs-lookup"><span data-stu-id="82113-105">Both of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="82113-106">これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="82113-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="82113-p102">このフェーズでは、Microsoft 365 Enterprise のクラウド サービスへの高パフォーマンス接続を作成するための主な検討事項について、順を追って説明します。概要については、「[Office 365 のネットワークの原則](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82113-p102">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise. For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="82113-109">既にネットワーク インフラストラクチャを展開している場合は、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82113-109">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="82113-110">Microsoft 365 Enterprise のネットワーク インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="82113-110">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="82113-111">Microsoft 365 Enterprise の要件と機能に対応したネットワーク インフラストラクチャを構築するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="82113-111">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="82113-112">Microsoft 365 のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="82113-112">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="82113-113">オフィスごとにローカルのインターネット接続を構成する</span><span class="sxs-lookup"><span data-stu-id="82113-113">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="82113-114">ネットワーク ヘアピンを回避する</span><span class="sxs-lookup"><span data-stu-id="82113-114">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="82113-115">トラフィック バイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="82113-115">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="82113-116">クライアントと Office 365 サービスのパフォーマンスを最適化する</span><span class="sxs-lookup"><span data-stu-id="82113-116">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="82113-117">上記の手順が完了したら、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82113-117">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="82113-118">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="82113-118">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="82113-119">Microsoft の内部を見て、[クラウド サービス向けに Microsoft ネットワークを最適化](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365#primaryR4)している方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="82113-119">Peek inside Microsoft and learn how the company prepared for and optimized the Microsoft network for the Office 365 cloud services with [Optimizing network performance for Microsoft Office 365](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="82113-120">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="82113-120">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="82113-121">架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ネットワーク デバイスとインターネットの接続を最適化](contoso-networking.md)している方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="82113-121">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="82113-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="82113-122">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[<span data-ttu-id="82113-123">Microsoft 365 のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="82113-123">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

