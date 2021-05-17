---
title: 展開および更新プログラム チャネルの構成例
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: パートナー組織がチャネルを使用してどのように展開および更新するか。
ms.openlocfilehash: a91ee948ca2051ceccb3883b2dd0198c1070bc03
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919064"
---
# <a name="deployment-and-update-channel-example-configurations"></a><span data-ttu-id="65ddc-103">展開および更新プログラム チャネルの構成例</span><span class="sxs-lookup"><span data-stu-id="65ddc-103">Deployment and update channel example configurations</span></span>

<span data-ttu-id="65ddc-104">Windows 10 および Microsoft 365 Apps で使用する更新チャネルの選択は、組織のタイプと、開発サイクルの展開場所および新機能の使用場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="65ddc-104">Choosing which update channels to use for Windows 10 and Microsoft 365 Apps can depend on your type of organization and where on the development cycle you want to be deploying and using new features and capabilities.</span></span> <span data-ttu-id="65ddc-105">ニーズに最適なプレリリースチャネルと運用チャネルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="65ddc-105">Find the pre-release and production channels that best fit your needs.</span></span>

## <a name="pre-release-channels"></a><span data-ttu-id="65ddc-106">プレリリースチャンネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-106">Pre-release channels</span></span>

| <span data-ttu-id="65ddc-107">顧客/チャネルオファリング</span><span class="sxs-lookup"><span data-stu-id="65ddc-107">Customer/Channel Offering</span></span> | <span data-ttu-id="65ddc-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="65ddc-108">Windows 10</span></span> | <span data-ttu-id="65ddc-109">Microsoft 365 Apps for Enterprise（Windows 10）</span><span class="sxs-lookup"><span data-stu-id="65ddc-109">Microsoft 365 Apps for Enterprise (Windows 10)</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="65ddc-110">高度に技術的なユーザーと開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-110">Right for highly technical users and developers.</span></span> <br><br> <span data-ttu-id="65ddc-111">最新のコードを使用して、開発サイクルの最も早い段階で、最新のビルドを最初に入手してください。</span><span class="sxs-lookup"><span data-stu-id="65ddc-111">Be the first to access the latest builds earliest in the development cycle with the newest code.</span></span> <br><br> <span data-ttu-id="65ddc-112">ラフエッジといくつかの不安定性があります。</span><span class="sxs-lookup"><span data-stu-id="65ddc-112">There will be rough edges and some instability.</span></span> | <span data-ttu-id="65ddc-113">Dev</span><span class="sxs-lookup"><span data-stu-id="65ddc-113">Dev</span></span> | <span data-ttu-id="65ddc-114">該当なし</span><span class="sxs-lookup"><span data-stu-id="65ddc-114">N/A</span></span> |
| <span data-ttu-id="65ddc-115">まだ開発中の、より信頼性の高いビルドを希望するアーリーアダプターとITプロフェッショナルを対象としています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-115">Right for early adopters and IT Pros who want more reliable builds that are still in development.</span></span> <br><br> <span data-ttu-id="65ddc-116">今後の予定を確認し、新機能の検証にご協力ください。</span><span class="sxs-lookup"><span data-stu-id="65ddc-116">See what’s coming up next and help validate new features.</span></span> | <span data-ttu-id="65ddc-117">ベータチャンネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-117">Beta Channel</span></span> | <span data-ttu-id="65ddc-118">ベータチャンネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-118">Beta Channel</span></span> |
| <span data-ttu-id="65ddc-119">今後のリリースへの早期アクセスを希望する方を対象としています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-119">Right for those who want early access to upcoming releases.</span></span> <br><br> <span data-ttu-id="65ddc-120">企業が広範に展開する前に、今後のリリースをプレビューして検証します。</span><span class="sxs-lookup"><span data-stu-id="65ddc-120">Where companies preview and validate upcoming releases before broad deployment.</span></span> <br><br> <span data-ttu-id="65ddc-121">これらはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-121">These are supported.</span></span> <br>  | <span data-ttu-id="65ddc-122">リリースプレビュー</span><span class="sxs-lookup"><span data-stu-id="65ddc-122">Release Preview</span></span> | <span data-ttu-id="65ddc-123">最新機能提供チャネル (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="65ddc-123">Current Channel (Preview)</span></span> <br><br> <span data-ttu-id="65ddc-124">半期エンタープライズ チャネル (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="65ddc-124">Semi-Annual Enterprise Channel (Preview)</span></span>|
||||

## <a name="production-channels-for-broad-deployment"></a><span data-ttu-id="65ddc-125">幅広い展開のための運用チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-125">Production channels for broad deployment</span></span>

<span data-ttu-id="65ddc-126">[**例**]列のリンクをクリックして、パートナー組織の展開段階とグループをステップスルーします。</span><span class="sxs-lookup"><span data-stu-id="65ddc-126">Click the link in the **Example** column to step through deployment stages and groups for an example organization.</span></span>

| <span data-ttu-id="65ddc-127">顧客/チャネルオファリング</span><span class="sxs-lookup"><span data-stu-id="65ddc-127">Customer/Channel Offering</span></span> | <span data-ttu-id="65ddc-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="65ddc-128">Windows 10</span></span> | <span data-ttu-id="65ddc-129">Microsoft 365 Apps for Enterprise（Windows 10）</span><span class="sxs-lookup"><span data-stu-id="65ddc-129">Microsoft 365 Apps for Enterprise (Windows 10)</span></span> | <span data-ttu-id="65ddc-130">例</span><span class="sxs-lookup"><span data-stu-id="65ddc-130">Example</span></span> |
|:-------|:-------|:-----|:-------|
| <span data-ttu-id="65ddc-131">準備ができ次第、最新のリリースを希望するお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-131">Right for customers who want the latest releases as soon as they are ready.</span></span> | <span data-ttu-id="65ddc-132">半期チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-132">Semi-Annual Channel</span></span> | [<span data-ttu-id="65ddc-133">最新機能提供チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-133">Current Channel</span></span>](/deployoffice/overview-update-channels#current-channel-overview) | [<span data-ttu-id="65ddc-134">最新リリース</span><span class="sxs-lookup"><span data-stu-id="65ddc-134">Latest releases</span></span>](deploy-update-channels-examples-rapid-deploy.md) |
| <span data-ttu-id="65ddc-135">予測可能性を追加で備えた最新のリリースが必要な企業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-135">Right for enterprises who want the latest release with additional predictability.</span></span> | <span data-ttu-id="65ddc-136">半期チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-136">Semi-Annual Channel</span></span> | [<span data-ttu-id="65ddc-137">月次エンタープライズ チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-137">Monthly Enterprise Channel</span></span>](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) |  |
| <span data-ttu-id="65ddc-138">各アップデートの前に広範なITテストが必要な企業を対象としています。</span><span class="sxs-lookup"><span data-stu-id="65ddc-138">Right for enterprises with need for extensive IT testing before each update.</span></span> | <span data-ttu-id="65ddc-139">半期チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-139">Semi-Annual Channel</span></span> | [<span data-ttu-id="65ddc-140">半期エンタープライズ チャネル</span><span class="sxs-lookup"><span data-stu-id="65ddc-140">Semi-Annual Enterprise Channel</span></span>](/deployoffice/overview-update-channels#semi-annual-enterprise-channel-overview) |  |
|||||


## <a name="see-also"></a><span data-ttu-id="65ddc-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="65ddc-141">See also</span></span>

[<span data-ttu-id="65ddc-142">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="65ddc-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="65ddc-143">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="65ddc-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)