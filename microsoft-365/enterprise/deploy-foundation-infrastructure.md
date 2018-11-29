---
title: Microsoft 365 Enterprise の基礎インフラストラクチャチャ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の基礎インフラストラクチャを組織に展開するための主要フェーズについて理解します。
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868998"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="d7412-103">Microsoft 365 Enterprise の基礎インフラストラクチャチャ</span><span class="sxs-lookup"><span data-stu-id="d7412-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="d7412-104">Microsoft 365 Enterprise のメリットをフルに発揮するには、その基礎インフラストラクチャから展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="d7412-104">To fully realize the benefits of Microsoft 365 Enterprise, you’ll begin your deployment with its foundation infrastructure.</span></span> 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a><span data-ttu-id="d7412-105">Microsoft 365 Enterprise 展開の基礎インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="d7412-105">Foundation infrastructure for deploying Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d7412-p101">基礎インフラストラクチャは、生産性ワークロード (Microsoft Teams や Office 365 の Exchange Online など) およびシナリオ (Microsoft 365 の移行や自動クライアント更新など) を展開できる基盤です。インテリジェント セキュリティと統合が実現し、これにより継続的な管理が簡素化され、クライアント ソフトウェアが確実に最新の生産性拡張機能およびセキュリティ機能拡張で更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d7412-p101">The foundation infrastructure is the groundwork upon which you can deploy productivity workloads (such as Microsoft Teams and Exchange Online in Office 365) and scenarios (such as migrating to Microsoft 365 and automating client updates). It provides intelligent security and integration that simplifies ongoing management, which ensures that your client software is updated with the latest productivity and security enhancements.</span></span>

<span data-ttu-id="d7412-108">次のフェーズに従って、組織における Microsoft 365 Enterprise の基礎インフラストラクチャを計画し展開します。</span><span class="sxs-lookup"><span data-stu-id="d7412-108">You'll use the following phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise in your organization:</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="d7412-109">フェーズ 1: ネットワーク</span><span class="sxs-lookup"><span data-stu-id="d7412-109">Phase 1: Networking</span></span>](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="d7412-110">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="d7412-110">Phase 2: Identity</span></span>](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="d7412-111">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d7412-111">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="d7412-112">フェーズ 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="d7412-112">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="d7412-113">フェーズ 5: モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="d7412-113">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="d7412-114">フェーズ 6: 情報保護</span><span class="sxs-lookup"><span data-stu-id="d7412-114">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)|


<span data-ttu-id="d7412-p102">各フェーズを終了する前に、フェーズの終了条件を確認する必要があります。終了条件は、満たしている必要がある必須条件と、検討すべきオプションの条件からなります。各フェーズの終了条件により、オンプレミスおよびクラウド インフラストラクチャとその結果としてのエンドツーエンド構成が、Microsoft 365 Enterprise 展開の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d7412-p102">Before you can exit each phase, you must examine its exit criteria, which is a set of required conditions that you must meet and optional conditions to consider. Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="d7412-117">この短いビデオで、基礎インフラストラクチャ コンテンツの機能を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7412-117">Watch this short video on how the foundation infrastructure content works.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="d7412-118">次の図に、Microsoft 365 Enterprise 展開全体における基礎インフラストラクチャの内容と、このインフラストラクチャの進み方を示します。</span><span class="sxs-lookup"><span data-stu-id="d7412-118">The following figure shows the foundation infrastructure in the overall Microsoft 365 Enterprise deployment content and your path through it.</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a><span data-ttu-id="d7412-119">FastTrack</span><span class="sxs-lookup"><span data-stu-id="d7412-119">FastTrack</span></span>

<span data-ttu-id="d7412-p103">FastTrack は、サブスクリプションの一部として利用可能であり、Microsoft エンジニアがお客様のペースに合わせたクラウドへの移行を支援する継続的かつ反復的なサービスです。FastTrack では、必要に応じて追加サービスを提供する認定パートナーにアクセスできます。FastTrack はこれまでに 40,000 以上のお客様に対応しており、ROI の最大化、展開の迅速化、組織全体での採用の拡充を支援してきました。「[Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7412-p103">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span> 

<span data-ttu-id="d7412-p104">FastTrack を利用して Microsoft 365 Enterprise を展開する場合は、基礎インフラストラクチャを展開およびセットアップする方法のガイダンスとして FastTrack「[Microsoft 365 展開アドバイザー](https://aka.ms/microsoft365setupguide)」を使用できます。このページにアクセスするため、Office 365 または Microsoft 365 テナントでグローバル管理者としてサインオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7412-p104">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7412-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="d7412-126">Next step</span></span>

<span data-ttu-id="d7412-p105">Office 365、Enterprise Mobility + Security、または Windows 10 Enterprise の既存のインフラストラクチャがある場合は、「[既存のインフラストラクチャを使用した Microsoft 365 Enterprise の展開](deploy-with-existing-infrastructure.md)」を参照してください。この記事では、各フェーズの終了条件について説明しています。この情報から、IT インフラストラクチャを Microsoft 365 Enterprise 対応にするために変更する必要がある内容を容易に判別できます。</span><span class="sxs-lookup"><span data-stu-id="d7412-p105">If you have existing infrastructure for Office 365, Enterprise Mobility + Security, or Windows 10 Enterprise, see [Deployment of Microsoft 365 Enterprise with existing infrastructure](deploy-with-existing-infrastructure.md). This article steps you through the exit criteria for each phase. With this information, you can more quickly determine what you need to change to make your IT infrastructure Microsoft 365 Enterprise-compliant.</span></span>

<span data-ttu-id="d7412-130">それ以外の場合は、Microsoft 365 Enterprise のエンドツーエンドの展開を[フェーズ 1: ネットワーキング](networking-infrastructure.md)から開始できます。</span><span class="sxs-lookup"><span data-stu-id="d7412-130">Otherwise, you can begin your Microsoft 365 Enterprise end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>