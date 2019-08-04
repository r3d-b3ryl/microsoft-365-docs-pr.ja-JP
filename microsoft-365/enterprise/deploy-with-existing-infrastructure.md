---
title: 既存のインフラストラクチャを使用した Microsoft 365 Enterprise の展開
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/04/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 既存のインフラストラクチャがある場合の Microsoft 365 Enterprise の展開の終了条件について順を追って説明します。
ms.openlocfilehash: 8c9c1d1900e9fd1a025d3fd74cc9f358b612a4d1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073917"
---
# <a name="deployment-of-microsoft-365-enterprise-with-existing-infrastructure"></a><span data-ttu-id="d7a0f-103">既存のインフラストラクチャを使用した Microsoft 365 Enterprise の展開</span><span class="sxs-lookup"><span data-stu-id="d7a0f-103">Deployment of Microsoft 365 Enterprise with existing infrastructure</span></span>

<span data-ttu-id="d7a0f-p101">多くの組織には、既存のネットワーク、ID、およびその他のコンポーネント、または Microsoft オンプレミス製品およびクラウドベース サービスが既に導入されています。この記事では、既存のインフラストラクチャを採用または変更する方法を容易に決定できるように、Microsoft 365 Enterprise 展開の各フェーズについて順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-p101">Many organizations have exisiting networking, identity, and other components or Microsoft on-premises products and cloud-based services. This article steps through each phase of the deployment of Microsoft 365 Enterprise so you can quickly determine how to adapt or change your existing infrastructure.</span></span>

<span data-ttu-id="d7a0f-p102">各フェーズを終了する前に、フェーズの終了条件を確認する必要があります。終了条件は、満たしている必要がある必須条件と、検討すべきオプションの条件からなります。各フェーズの終了条件により、オンプレミス インフラストラクチャおよびクラウド インフラストラクチャとその結果としてのエンドツーエンド構成が、Microsoft 365 Enterprise 展開の要件を満たしていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meets the requirements for a Microsoft 365 Enterprise deployment.</span></span>

> [!Note] 
> <span data-ttu-id="d7a0f-p103">FastTrack は、サブスクリプションの一部として利用可能であり、Microsoft エンジニアがお客様のペースに合わせたクラウドへの移行を支援する継続的かつ反復的なサービスです。FastTrack では、必要に応じて追加サービスを提供する認定パートナーにアクセスできます。FastTrack はこれまでに 40,000 以上のお客様に対応しており、ROI の最大化、展開の迅速化、組織全体での採用の拡充を支援してきました。「[Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

## <a name="exit-criteria-for-networking-phase-1"></a><span data-ttu-id="d7a0f-112">ネットワークの終了条件 (フェーズ 1)</span><span class="sxs-lookup"><span data-stu-id="d7a0f-112">Exit criteria for networking (phase 1)</span></span>

<span data-ttu-id="d7a0f-113">ネットワーク インフラストラクチャの次の必須条件とオプションの条件を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-113">Step through the following required and optional conditions for the networking infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for networking](./includes/deployment-exit-criteria-networking.md)]

## <a name="exit-criteria-for-identity-phase-2"></a><span data-ttu-id="d7a0f-114">ID の終了条件 (フェーズ 2)</span><span class="sxs-lookup"><span data-stu-id="d7a0f-114">Exit criteria for identity (phase 2)</span></span>

<span data-ttu-id="d7a0f-115">ID インフラストラクチャの次の必須条件とオプションの条件を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-115">Step through the following required and optional conditions for the identity infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-identity.md)]

## <a name="exit-criteria-for-windows-10-enterprise-phase-3"></a><span data-ttu-id="d7a0f-116">Windows 10 Enterprise の終了条件 (フェーズ 3)</span><span class="sxs-lookup"><span data-stu-id="d7a0f-116">Exit criteria for Windows 10 Enterprise (phase 3)</span></span>

<span data-ttu-id="d7a0f-117">Windows 10 Enterprise インフラストラクチャの次の必須条件とオプションの条件を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-117">Step through the following required and optional conditions for the Windows 10 Enterprise infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for identity](./includes/deployment-exit-criteria-windows10.md)]

## <a name="exit-criteria-for-office-365-proplus-phase-4"></a><span data-ttu-id="d7a0f-118">Office 365 ProPlus の終了条件 (フェーズ 4)</span><span class="sxs-lookup"><span data-stu-id="d7a0f-118">Exit criteria for Office 365 ProPlus (phase 4)</span></span>

<span data-ttu-id="d7a0f-119">Microsoft 365 Enterprise 用の Office 365 ProPlus インフラストラクチャの評価、展開計画、および展開の要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-119">Meet the requirements for assessment, deployment planning, and deployment of the Office 365 ProPlus infrastructure for Microsoft 365 Enterprise.</span></span>

[!INCLUDE [Deployment exit criteria for Office 365 ProPlus](./includes/deployment-exit-criteria-office365proplus.md)]

## <a name="exit-criteria-for-mobile-device-management-phase-5"></a><span data-ttu-id="d7a0f-120">モバイル デバイス管理の終了条件 (フェーズ 5)</span><span class="sxs-lookup"><span data-stu-id="d7a0f-120">Exit criteria for mobile device management (phase 5)</span></span>

<span data-ttu-id="d7a0f-121">モバイル デバイス管理インフラストラクチャの次の要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-121">Meet the following requirements for the mobile device management infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for mobile device management](./includes/deployment-exit-criteria-mobility.md)]

## <a name="exit-criteria-for-information-protection-phase-6"></a><span data-ttu-id="d7a0f-122">情報保護の終了条件 (フェーズ 6)</span><span class="sxs-lookup"><span data-stu-id="d7a0f-122">Exit criteria for information protection (phase 6)</span></span>

<span data-ttu-id="d7a0f-123">情報保護インフラストラクチャの次の必須条件とオプションの条件を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="d7a0f-123">Step through the following required and optional conditions for the information protection infrastructure.</span></span>

[!INCLUDE [Deployment exit criteria for information protection](./includes/deployment-exit-criteria-infoprotect.md)]

