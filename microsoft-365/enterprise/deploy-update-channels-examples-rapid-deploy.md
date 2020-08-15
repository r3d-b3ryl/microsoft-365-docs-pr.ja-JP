---
title: 最新リリースの幅広い展開例
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
description: 最新リリースを導入している組織での、Windows 10 アプリ、 Microsoft 365 アプリのチャネルの使用方法。
ms.openlocfilehash: fd1d8ddd342b2781470378c879ef70d2ba304316
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686168"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a><span data-ttu-id="55235-103">最新リリースの幅広い展開例</span><span class="sxs-lookup"><span data-stu-id="55235-103">Example of broad deployment for the latest releases</span></span>

<span data-ttu-id="55235-104">このチャネル構成例は、次のビジネスの優先度に適合するように、最新のリリースの迅速な展開を使用する組織を対象としています。</span><span class="sxs-lookup"><span data-stu-id="55235-104">This channel configuration example is for an organization that uses rapid deployment of the latest releases to fit these business priorities:</span></span>

- <span data-ttu-id="55235-105">Microsoft のアプリとサービスにより、事業の継続性を確立できます。</span><span class="sxs-lookup"><span data-stu-id="55235-105">Ensure business continuity with Microsoft apps and services.</span></span>
- <span data-ttu-id="55235-106">デバイス、サービス、データセキュリティを最大限に活用するための Microsoft の最新の機能と修正プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="55235-106">Maximize device, service, and data security with the latest features and fixes from Microsoft.</span></span>
- <span data-ttu-id="55235-107">Microsoft の最新機能で、ユーザーの生産性を最大にします。</span><span class="sxs-lookup"><span data-stu-id="55235-107">Maximize user productivity with the latest features from Microsoft.</span></span>

<span data-ttu-id="55235-108">このような目標のために、ITタスクには、迅速な運用展開と、ユーザーとデバイスの代表的なサブセットによる早期審査との間のバランスを見つけ、広範な展開の前に機能的に検証するということが課せられます。</span><span class="sxs-lookup"><span data-stu-id="55235-108">These goals translate to the IT task of finding the balance between rapid production deployment and early vetting with a representative subset of users and devices to validate functionally before broad deployment.</span></span>

<span data-ttu-id="55235-109">私たちの組織の例として、ヨーロッパ、アフリカ、アジア、南北アメリカなど世界中に5,000人の従業員がいます。</span><span class="sxs-lookup"><span data-stu-id="55235-109">Our example organization has 5,000 employees in buildings across the world in Europe, Africa, Asia, and the Americas.</span></span> <span data-ttu-id="55235-110">従業員の70% が Microsoft 365 E3 を使用しており、その他の残りの組織で Microsoft 365 E5 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="55235-110">70% of the employees use Microsoft 365 E3 and the rest of the organization uses Microsoft 365 E5.</span></span>

>[!Note]
><span data-ttu-id="55235-111">この例では、さまざまな種類や規模の組織で利用できる展開ステージとグループの使用方法について説明します。　　　</span><span class="sxs-lookup"><span data-stu-id="55235-111">This example is designed to show you how you can use deployment stages and groups, which can work for organizations of many types and sizes.</span></span>
>

<span data-ttu-id="55235-112">組織の IT インフラストラクチャ:</span><span class="sxs-lookup"><span data-stu-id="55235-112">This organization's IT infrastructure:</span></span> 

- <span data-ttu-id="55235-113">Windows、Microsoft 365 アプリ、およびインストールされているベースの60% を構成する Microsoft クラウドサービスの主な機能です。　</span><span class="sxs-lookup"><span data-stu-id="55235-113">Is largely homogeneous, with Windows, Microsoft 365 Apps, and Microsoft cloud services comprising 60% of the installed base.</span></span> <span data-ttu-id="55235-114">ITインフラストラクチャを簡素化および合理化するための数年にわたる努力の結果、いくつかのレガシーシステムが残っています。</span><span class="sxs-lookup"><span data-stu-id="55235-114">A few legacy systems remain after an intensive, multi-year effort to simplify and streamline the IT infrastructure.</span></span>
- <span data-ttu-id="55235-115">経験豊富なスタッフが管理し、リリースの際、Microsoftのリードによって、ユーザーとデバイスの生産性と安全性を維持することを任されています。</span><span class="sxs-lookup"><span data-stu-id="55235-115">Is maintained by highly experienced staff and tasked with keeping users and their devices productive and secure by following Microsoft’s lead in their releases.</span></span>

## <a name="deployment-and-update-stages"></a><span data-ttu-id="55235-116">展開と更新のステージ</span><span class="sxs-lookup"><span data-stu-id="55235-116">Deployment and update stages</span></span>

<span data-ttu-id="55235-117">この組織例では、最新のリリースの迅速な導入目標に基づいて、、2段階の展開プロセスを使用しています。　</span><span class="sxs-lookup"><span data-stu-id="55235-117">Based on rapid deployment goals of the latest release, this example organization uses a two-step deployment process.</span></span>

1. <span data-ttu-id="55235-118">**プレビューやパイロット展開を使用する：** 早期導入者、IT スタッフ、代表的な構成を使用しているユーザー、トレーニングスタッフと検証および反復します。　　</span><span class="sxs-lookup"><span data-stu-id="55235-118">**Use a preview or pilot deployment:** Validate and iterate with early adopters, IT staff, users with representative configurations, and training staff.</span></span> 

   <span data-ttu-id="55235-119">早期導入者、IT スタッフ、および代表的な構成を使用しているユーザーは、新しい機能が組織の他の部分に展開される前に、他のアプリやデバイスで機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="55235-119">The early adopters, IT staff, users with representative configurations can validate functionality with other apps and on devices before the new features roll out to the rest of the organization.</span></span>

   <span data-ttu-id="55235-120">この新機能は、導入変更マネージャーは、広範囲にわたるロールアウトの前に新機能を早い段階で確認し、メッセージングとロールアウトが計画できます。</span><span class="sxs-lookup"><span data-stu-id="55235-120">Change managers have an early peek at the new features before widespread rollout and can plan messaging and rollout.</span></span>

   <span data-ttu-id="55235-121">トレーニングスタッフは、広範囲にロールアウトする前に、新しい内部コースを計画したり、新機能に関しては、既存のコースを更新したりできます。</span><span class="sxs-lookup"><span data-stu-id="55235-121">Training staff can plan new internal courses or update existing courses for the new features before widespread rollout.</span></span>

2. <span data-ttu-id="55235-122">**運用展開：** 地域、部署、またはその他の導入方法によって、すべての残りのユーザーにロールアウトます。　　</span><span class="sxs-lookup"><span data-stu-id="55235-122">**Production deployment:** Roll out to all remaining users by region, department, or other deployment method.</span></span>

## <a name="deployment-configuration-for-windows-10"></a><span data-ttu-id="55235-123">Windows 10 の展開構成</span><span class="sxs-lookup"><span data-stu-id="55235-123">Deployment configuration for Windows 10</span></span>

<span data-ttu-id="55235-124">全体的な目標は、代表的なユーザーとそのデバイスのグループによるリリースプレビューチャネルの変更の検証後に、最新の半期チャネルリリースの広範な展開を実行することです。</span><span class="sxs-lookup"><span data-stu-id="55235-124">The overall goal is to perform a broad deployment of the latest Semi-Annual Channel release after validation of Release Preview Channel changes by a group of representative users and their devices.</span></span>

<span data-ttu-id="55235-125">Windows 10の展開方法と戦略の詳細については、[Windows 10 の展開](https://docs.microsoft.com/windows/deployment/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55235-125">See [Windows 10 deployment](https://docs.microsoft.com/windows/deployment/) for more information on Windows 10 deployment methods and strategies.</span></span>

| <span data-ttu-id="55235-126">ステージ</span><span class="sxs-lookup"><span data-stu-id="55235-126">Stage</span></span> | <span data-ttu-id="55235-127">チャネル</span><span class="sxs-lookup"><span data-stu-id="55235-127">Channel</span></span> | <span data-ttu-id="55235-128">展開グループ</span><span class="sxs-lookup"><span data-stu-id="55235-128">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="55235-129">パイロット</span><span class="sxs-lookup"><span data-stu-id="55235-129">Pilot</span></span> |  <span data-ttu-id="55235-130">**リリースプレビューチャネル**</span><span class="sxs-lookup"><span data-stu-id="55235-130">**Release Preview Channel**</span></span>  <ul><li><span data-ttu-id="55235-131">目的: 機能更新プログラムを IT スタッフと早期導入者に展開し、代表的なデバイスと構成 (言語、サードパーティ製アプリ) の検証をします。　　　</span><span class="sxs-lookup"><span data-stu-id="55235-131">Purpose: Deployment of feature updates to IT staff and early adopters for validation on representative devices and configurations (languages, 3rd party apps).</span></span> </li><li> <span data-ttu-id="55235-132">状態：完全に準拠しており、商用顧客向けにサポートされています。サポート契約には含まれません。</span><span class="sxs-lookup"><span data-stu-id="55235-132">State: Fully compliant and supported for commercial customers and it does not count against your support agreements.</span></span> </li></ul> | <span data-ttu-id="55235-133">**Win10リリースプレビューチャネル** (名前の例)</span><span class="sxs-lookup"><span data-stu-id="55235-133">**Win10ReleasePreviewChannel** (example name)</span></span> <br><br> <span data-ttu-id="55235-134">メンバーは以下を含むグループになります：</span><span class="sxs-lookup"><span data-stu-id="55235-134">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="55235-135">部門や場所を越えた Windows 愛好家</span><span class="sxs-lookup"><span data-stu-id="55235-135">Windows enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="55235-136">検証が必要な構成を持つスタッフ</span><span class="sxs-lookup"><span data-stu-id="55235-136">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="55235-137">IT 管理者と IT 展開スタッフ</span><span class="sxs-lookup"><span data-stu-id="55235-137">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="55235-138">導入変更マネージャー</span><span class="sxs-lookup"><span data-stu-id="55235-138">Change managers</span></span> </li><li> <span data-ttu-id="55235-139">社内トレーニングスタッフ</span><span class="sxs-lookup"><span data-stu-id="55235-139">Internal training staff</span></span> </li></ul> |
| <span data-ttu-id="55235-140">生産</span><span class="sxs-lookup"><span data-stu-id="55235-140">Production</span></span> |  <span data-ttu-id="55235-141">**半期チャネル**</span><span class="sxs-lookup"><span data-stu-id="55235-141">**Semi-Annual Channel**</span></span>  <ul><li><span data-ttu-id="55235-142">目的: 最新の機能更新を組織の他のユーザーに広く展開します。　　</span><span class="sxs-lookup"><span data-stu-id="55235-142">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="55235-143">状態: 完全に準拠し、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="55235-143">State: Fully compliant and supported.</span></span> </li></ul> | <span data-ttu-id="55235-144">**Win10半期チャネル** (名前の例)</span><span class="sxs-lookup"><span data-stu-id="55235-144">**Win10SemiAnnualChannel** (example name)</span></span> <br><br> <span data-ttu-id="55235-145">メンバーは、Win10半期チャネル グループに含まれていないすべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="55235-145">Members are all users that are not in the Win10ReleasePreviewChannel group.</span></span> |
||||

<span data-ttu-id="55235-146">この組織では、Windows Update や Windows Server Update Services などの半期単位のチャネルのリリースを展開する場合と同じ方法で、リリースプレビューチャネルペイロードを展開するベストプラクティスを使用しています。また、両方のチャネル更新に同じポリシーを適用します。　</span><span class="sxs-lookup"><span data-stu-id="55235-146">This organization uses the best practice of deploying the Release Preview Channel payload in the same way as they deploy Semi-Annual Channel releases, such as Windows Update or Windows Server Update Services, and that they apply the same policies for both channel updates.</span></span>

<span data-ttu-id="55235-147">継続的な更新のプロセス:</span><span class="sxs-lookup"><span data-stu-id="55235-147">Ongoing updates process:</span></span>

1. <span data-ttu-id="55235-148">リリースプレビューチャネルの変更は、Win10リリースプレビューチャネル (仮の名前) 展開グループに展開されます。</span><span class="sxs-lookup"><span data-stu-id="55235-148">Release Preview Channel changes are deployed to the Win10ReleasePreviewChannel (example name) deployment group.</span></span>
2. <span data-ttu-id="55235-149">Win10リリースプレビューチャネルグループメンバーは、リリースプレビューチャネルの変更がIT導入スタッフにより取り組まれていることを確認します。IT 導入スタッフは、Microsoft にフィードバックを提供し、追加の検証のために次のリリースプレビューチャネルの変更を待つことができます。</span><span class="sxs-lookup"><span data-stu-id="55235-149">Win10ReleasePreviewChannel group members confirm that Release Preview Channel changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Release Preview Channel changes for additional validation.</span></span>
3. <span data-ttu-id="55235-150">半期チャネル機能の変更がは、Win10半期チャネル展開グループに展開されます。</span><span class="sxs-lookup"><span data-stu-id="55235-150">Semi-Annual Channel feature changes are deployed to the Win10SemiAnnualChannel deployment group.</span></span> 

>[!Note]
><span data-ttu-id="55235-151">半期チャネルは推奨されるチャネルですが、IT の部署は、管理ツールを使用して、組織内に最新の半期チャネルのリリースを展開してからロールバックする時期を決定する必要があります。　　　</span><span class="sxs-lookup"><span data-stu-id="55235-151">While the Semi-Annual Channel is the recommended channel, your IT department should utilize their management tools and determine when to deploy the latest Semi-Annual Channel release within their organization and then roll it out in waves.</span></span>
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a><span data-ttu-id="55235-152">Microsoft 365 アプリの展開構成</span><span class="sxs-lookup"><span data-stu-id="55235-152">Deployment configuration for Microsoft 365 Apps</span></span>

<span data-ttu-id="55235-153">全体的な目標は、代表的なユーザーグループが現在のチャネル（プレビュー）の変更を検証した後に、最新の現在のチャネルリリースの広範な展開を実行することです。</span><span class="sxs-lookup"><span data-stu-id="55235-153">The overall goal is to perform a broad deployment of the latest Current Channel release after validation of Current Channel (Preview) changes by a group of representative users.</span></span>

<span data-ttu-id="55235-154">Microsoft 365 アプリの展開方法と戦略の詳細については、[Microsoft 365 アプリの 展開 ](https://docs.microsoft.com/deployoffice/plan-office-365-proplus)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55235-154">See [Microsoft 365 Apps deployment](https://docs.microsoft.com/deployoffice/plan-office-365-proplus) for more information on Microsoft 365 Apps deployment methods and strategies.</span></span>

| <span data-ttu-id="55235-155">ステージ</span><span class="sxs-lookup"><span data-stu-id="55235-155">Stage</span></span> | <span data-ttu-id="55235-156">チャネル</span><span class="sxs-lookup"><span data-stu-id="55235-156">Channel</span></span> | <span data-ttu-id="55235-157">展開グループ</span><span class="sxs-lookup"><span data-stu-id="55235-157">Deployment group</span></span> |
|:-------|:-------|:-----|
| <span data-ttu-id="55235-158">パイロット</span><span class="sxs-lookup"><span data-stu-id="55235-158">Pilot</span></span> |  <span data-ttu-id="55235-159">**最新機能提供チャネル (プレビュー)**</span><span class="sxs-lookup"><span data-stu-id="55235-159">**Current Channel (Preview)**</span></span> <ul><li> <span data-ttu-id="55235-160">目的: {代表的なユーザーのグループに、新しい Microsoft 365 アプリの新機能を簡単にご紹介します。}最新のチャネル (プレビュー) を使用しているユーザーがテストし、運用可能な状態になったらすぐに、機能の更新を展開します。　　　</span><span class="sxs-lookup"><span data-stu-id="55235-160">Purpose: {give a group of representative users a sneak peek of new Microsoft 365 Apps features} Deployment of feature updates as soon as they are tested with Current Channel (Preview) users and are production-ready.</span></span> </li><li> <span data-ttu-id="55235-161">状態: 完全に準拠し、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="55235-161">State: Fully compliant and supported.</span></span></li><li> <span data-ttu-id="55235-162">頻度: 月に2-3 回更新します。</span><span class="sxs-lookup"><span data-stu-id="55235-162">How often: Updates 2-3 times each month.</span></span> </li></ul> | <span data-ttu-id="55235-163">**AppsCurrentChannelPreview** (名前の例)</span><span class="sxs-lookup"><span data-stu-id="55235-163">**AppsCurrentChannelPreview** (example name)</span></span> <br><br> <span data-ttu-id="55235-164">メンバーは以下を含むグループになります：</span><span class="sxs-lookup"><span data-stu-id="55235-164">Members are groups containing:</span></span> <ul><li> <span data-ttu-id="55235-165">部門や場所を越えた Office アプリ愛好家</span><span class="sxs-lookup"><span data-stu-id="55235-165">Office apps enthusiasts across departments and locations</span></span> </li><li> <span data-ttu-id="55235-166">検証が必要な構成を持つスタッフ</span><span class="sxs-lookup"><span data-stu-id="55235-166">Staff with configurations that need validation</span></span> </li><li> <span data-ttu-id="55235-167">IT 管理者と IT 展開スタッフ</span><span class="sxs-lookup"><span data-stu-id="55235-167">IT admins and IT deployment staff</span></span> </li><li> <span data-ttu-id="55235-168">導入変更マネージャー</span><span class="sxs-lookup"><span data-stu-id="55235-168">Change managers</span></span> </li><li> <span data-ttu-id="55235-169">社内トレーニングスタッフ</span><span class="sxs-lookup"><span data-stu-id="55235-169">Internal training staff</span></span> </li></ul>|
| <span data-ttu-id="55235-170">生産</span><span class="sxs-lookup"><span data-stu-id="55235-170">Production</span></span> | <span data-ttu-id="55235-171">**最新機能提供チャネル**</span><span class="sxs-lookup"><span data-stu-id="55235-171">**Current Channel**</span></span> <ul><li> <span data-ttu-id="55235-172">目的: 最新の機能更新を組織の他のユーザーに広く展開します。　　</span><span class="sxs-lookup"><span data-stu-id="55235-172">Purpose: Broad deployment of the latest feature updates to the rest of the organization.</span></span> </li><li> <span data-ttu-id="55235-173">状態: 完全に準拠し、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="55235-173">State: Fully compliant and supported.</span></span> </li></ul> |  <span data-ttu-id="55235-174">\*\* アプリ最新機能提供チャネルプレビュー\*\* (名前の例)</span><span class="sxs-lookup"><span data-stu-id="55235-174">**AppsCurrentChannel** (example name)</span></span> <br><br> <span data-ttu-id="55235-175">メンバーは、Win10半期チャネル グループに含まれていないすべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="55235-175">Members are all users that are not in the AppsCurrentChannelPreview group.</span></span> |
|||

<span data-ttu-id="55235-176">継続的な更新のプロセス:</span><span class="sxs-lookup"><span data-stu-id="55235-176">Ongoing updates process:</span></span>

1. <span data-ttu-id="55235-177">現在のチャネル (プレビュー) の変更は アプリ最新機能提供チャネルプレビュー展開グループに展開されます。</span><span class="sxs-lookup"><span data-stu-id="55235-177">Current Channel (Preview) changes are deployed to the AppsCurrentChannelPreview deployment group.</span></span>
2. <span data-ttu-id="55235-178">アプリ最新機能提供チャネルプレビューグループメンバーは、現在のチャネル (プレビュー) の変更が IT 導入スタッフによって取り組まれていることを確認します。 Microsoft にフィードバックを送信して、その他の検証のための最新のチャネル (プレビュー) リリースをお待ちください。</span><span class="sxs-lookup"><span data-stu-id="55235-178">AppsCurrentChannelPreview group members confirm that Current Channel (Preview) changes are working to IT deployment staff, who can provide feedback to Microsoft and wait for the next Current Channel (Preview) release for additional validation.</span></span>
3. <span data-ttu-id="55235-179">現在のチャネルの変更は アプリ最新機能提供チャネルプレビュー展開グループに展開されます。</span><span class="sxs-lookup"><span data-stu-id="55235-179">Current Channel changes are deployed to the AppsCurrentChannel deployment group.</span></span> 

## <a name="visual-summary"></a><span data-ttu-id="55235-180">視覚的な概要</span><span class="sxs-lookup"><span data-stu-id="55235-180">Visual summary</span></span>

<span data-ttu-id="55235-181">この組織例で使用されている製品、チャネル、展開グループを次に示します。</span><span class="sxs-lookup"><span data-stu-id="55235-181">Here are the products, their channels, and the deployment groups used by this example organization.</span></span> 

![最新リリースの幅広い展開のための展開グループ](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a><span data-ttu-id="55235-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="55235-183">See also</span></span>

[<span data-ttu-id="55235-184">展開および更新プログラム チャネルの構成例</span><span class="sxs-lookup"><span data-stu-id="55235-184">Deployment and update channel example configurations</span></span>](deploy-update-channels-examples.md)

[<span data-ttu-id="55235-185">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="55235-185">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="55235-186">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="55235-186">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
