---
title: ステップ7  -  WindowsとOfficeのサービス
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ご自身の環境でWindowsおよびOfficeのサービスを準備する方法を学びます。
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679004"
---
# <a name="step-7-windows-and-office-servicing"></a><span data-ttu-id="bcbae-103">ステップ7： WindowsとOfficeのサービス</span><span class="sxs-lookup"><span data-stu-id="bcbae-103">Step 7: Windows and Office Servicing</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><span data-ttu-id="bcbae-104"><strong>ステップ7：WindowsとOfficeのサービス</strong></span><span class="sxs-lookup"><span data-stu-id="bcbae-104"><strong>Step 7: Windows and Office Servicing</strong></span></span></p>
<p><span data-ttu-id="bcbae-105">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span><span class="sxs-lookup"><span data-stu-id="bcbae-105">Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations.</span></span> <span data-ttu-id="bcbae-106">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span><span class="sxs-lookup"><span data-stu-id="bcbae-106">Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="bcbae-107">WindowsおよびOfficeサービスは、半年ごとの機能更新に備えるための計画サイクルを統括する、推奨展開プロセスの第7段階です。</span><span class="sxs-lookup"><span data-stu-id="bcbae-107">Windows and Office Servicing is the seventh step in our recommended deployment process wheel covering the planning aspects of preparing for semi-annual updates to features.</span></span> <span data-ttu-id="bcbae-108">デスクトップ展開プロセス全体を確認するには、[デスクトップ展開センター](https://aka.ms/HowToShift)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcbae-108">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="bcbae-109">Windows 10 と Microsoft 365 Apps for enterprise の両方で、新しいサービス オプション、サポート モデル、および更新プログラムのタイムラインが導入されました。</span><span class="sxs-lookup"><span data-stu-id="bcbae-109">Both Windows 10 and Microsoft 365 Apps for enterprise introduce new servicing options, support models, and update timelines.</span></span> <span data-ttu-id="bcbae-110">これらの変更により、常に最新機能を導入しておくプロセスを単純化することができます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-110">These changes simplify the process for staying current on the latest features.</span></span> <span data-ttu-id="bcbae-111">これらの更新に加えて、ご自身に合ったサービスプランを有効にするための新しい設定オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bcbae-111">Along with these updates are new configuration options to enable servicing plans that meet your needs.</span></span> <span data-ttu-id="bcbae-112">Microsoft Endpoint Configuration Manager (Current Branch) の新機能を活用しながら、Windows 10 および Microsoft 365 Apps for enterprise の新機能を提供する半期チャンネルの更新を準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcbae-112">Let's learn how to prepare for semi-annual channel updates offering new features and capabilities in Windows 10 and Microsoft 365 Apps for enterprise while leveraging new features within Microsoft Endpoint Configuration Manager (Current Branch).</span></span>

[<span data-ttu-id="bcbae-113">Windows 10 および Microsoft 365 Apps for enterprise へ移行するには</span><span class="sxs-lookup"><span data-stu-id="bcbae-113">Helping customers shift to Windows 10 and Microsoft 365 Apps for enterprise</span></span>](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a><span data-ttu-id="bcbae-114">更新プログラムの種類</span><span class="sxs-lookup"><span data-stu-id="bcbae-114">Update Types</span></span>

<span data-ttu-id="bcbae-115">アップデートには2つの主なカテゴリがあり、機能のアップデート、そして累積されたセキュリティ、信頼性、そしてバグ修正を含んだ品質とセキュリティのアップデートに分けられます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-115">Updates fall into two main categories, feature updates and then quality and security updates which contain cumulative security, reliability and bug fixes.</span></span> <span data-ttu-id="bcbae-116">更新頻度では、WindowsとOffice双方で年2回、3月と9月に新機能を提供する半期ごとのチャンネルを渡しており、品質とセキュリティの更新は毎月行われます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-116">In terms of cadence both Windows and Office deliver a semi-annual channel which delivers new features twice per year around March and September while quality and security Updates occur Monthly.</span></span> <span data-ttu-id="bcbae-117">また、Office 365アプリケーションのみ、更新プログラムに新しい機能と品質更新プログラムの両方が含まれる完全サポート型の現在のチャネル オプションを用意しています。</span><span class="sxs-lookup"><span data-stu-id="bcbae-117">Additionally, unique to Office 365 applications, we offer a fully-supported Current Channel option where updates contain both new features and quality updates.</span></span>

<span data-ttu-id="bcbae-118">デスクトップ OS の更新プログラムとアプリの更新プログラムの長いサイクルをご存知であれば、以下のような疑問点が出てくるかと思います。</span><span class="sxs-lookup"><span data-stu-id="bcbae-118">If you’re used to a longer cycle between desktop OS and app updates, you might be wondering;</span></span>

  - <span data-ttu-id="bcbae-119">更新プログラムに互換性はあるのか</span><span class="sxs-lookup"><span data-stu-id="bcbae-119">Will the updates be compatible?</span></span>

  - <span data-ttu-id="bcbae-120">ユーザーの再トレーニングは必要なのか</span><span class="sxs-lookup"><span data-stu-id="bcbae-120">Will I need to keep retraining my users?</span></span>

  - <span data-ttu-id="bcbae-121">どんなリスクがあるか</span><span class="sxs-lookup"><span data-stu-id="bcbae-121">And what are the risks?</span></span>

<span data-ttu-id="bcbae-122">上記疑問の解消につながるよう、以下に新しい機能を頻繁に提供する理由とその利点をいくつか挙げています</span><span class="sxs-lookup"><span data-stu-id="bcbae-122">To answer those questions and the rationale for delivering new capabilities more frequently, we’ll some of the advantages of this approach</span></span>

### <a name="feature-update-benefits"></a><span data-ttu-id="bcbae-123">機能の更新の利点</span><span class="sxs-lookup"><span data-stu-id="bcbae-123">Feature Update Benefits</span></span>

<span data-ttu-id="bcbae-124">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year.</span><span class="sxs-lookup"><span data-stu-id="bcbae-124">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year.</span></span> <span data-ttu-id="bcbae-125">Why?</span><span class="sxs-lookup"><span data-stu-id="bcbae-125">Why?</span></span> <span data-ttu-id="bcbae-126">With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current.</span><span class="sxs-lookup"><span data-stu-id="bcbae-126">With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current.</span></span> <span data-ttu-id="bcbae-127">Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span><span class="sxs-lookup"><span data-stu-id="bcbae-127">Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span></span>

[<span data-ttu-id="bcbae-128">サービスとしての Windows のクイック ガイド</span><span class="sxs-lookup"><span data-stu-id="bcbae-128">Quick guide to Windows as a service</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[<span data-ttu-id="bcbae-129">Windows 10 のセキュリティ機能を使用して脅威を軽減する</span><span class="sxs-lookup"><span data-stu-id="bcbae-129">Mitigate threats by using Windows 10 security features</span></span>](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a><span data-ttu-id="bcbae-130">累積的な更新モデルの利点</span><span class="sxs-lookup"><span data-stu-id="bcbae-130">Cumulative Update Model Benefits</span></span>

<span data-ttu-id="bcbae-131">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past.</span><span class="sxs-lookup"><span data-stu-id="bcbae-131">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past.</span></span> <span data-ttu-id="bcbae-132">It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office.</span><span class="sxs-lookup"><span data-stu-id="bcbae-132">It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office.</span></span> <span data-ttu-id="bcbae-133">As you can imagine, this creates a nearly impossible set of test matrices for support.</span><span class="sxs-lookup"><span data-stu-id="bcbae-133">As you can imagine, this creates a nearly impossible set of test matrices for support.</span></span> <span data-ttu-id="bcbae-134">Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span><span class="sxs-lookup"><span data-stu-id="bcbae-134">Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span></span>

<span data-ttu-id="bcbae-135">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced.</span><span class="sxs-lookup"><span data-stu-id="bcbae-135">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced.</span></span> <span data-ttu-id="bcbae-136">Each update builds upon updates from previous months and contains all of the fixes that you need to get current.</span><span class="sxs-lookup"><span data-stu-id="bcbae-136">Each update builds upon updates from previous months and contains all of the fixes that you need to get current.</span></span> <span data-ttu-id="bcbae-137">Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span><span class="sxs-lookup"><span data-stu-id="bcbae-137">Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span></span>

### <a name="expanded-validation-of-updates"></a><span data-ttu-id="bcbae-138">更新プログラムの検証の範囲が拡大</span><span class="sxs-lookup"><span data-stu-id="bcbae-138">Expanded Validation of Updates</span></span>

<span data-ttu-id="bcbae-139">もう1つの利点は、広範環境への更新を展開する前に、まず[Office](https://products.office.com/office-insider?tab=Windows-Desktop)および[Windows ](https://insider.windows.com/)用のInsiderプログラムを介してビルドを配信します。これにより、広くアップデートを配信する前に、私達が統計データやフィードバックを集計することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="bcbae-139">Another advantage is that, before we roll out updates for broad deployment, we first release builds via the Insider programs for [Office](https://products.office.com/office-insider?tab=Windows-Desktop) and [Windows](https://insider.windows.com/), and this allows us to gather diagnostic data and feedback ahead of us releasing updates broadly.</span></span> <span data-ttu-id="bcbae-140">Insiderプログラムはどなたにも開かれており、アップデートを先立って確認することができます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-140">Now the Insider programs are open to everyone so that you can get ahead of understanding the updates.</span></span> <span data-ttu-id="bcbae-141">アップデートを配信するときには、何百万もの設定から統計データを受け取ることになるので、実際のアップデートを展開時には、より本質的に品質が予測しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="bcbae-141">By the time we release updates we will have received diagnostic data from millions of configurations, so when we do roll out updates, quality is now inherently more predictable</span></span>

<span data-ttu-id="bcbae-142">もう 1 つの点として、Microsoft 365 Apps for enterprise の Insider ビルドに月次チャネルの更新が反映されるため、Windows に準じて、Office に半期チャネルを適用して機能の更新プログラムを年に 2 回配信している場合は、半期エンタープライズ チャネル (プレビュー版) リリースによる検証を早期に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-142">AND one more thing, because Microsoft 365 Apps for enterprise Insider builds reflect monthly channel updates, if you are using semi-annual channel for Office to deliver feature updates twice per year aligned to Windows, you can validate those builds early as well using the Semi-Annual Enterprise Channel (Preview) releases.</span></span>

### <a name="supporting-management-tools"></a><span data-ttu-id="bcbae-143">管理ツールをサポート</span><span class="sxs-lookup"><span data-stu-id="bcbae-143">Supporting Management Tools</span></span>

<span data-ttu-id="bcbae-144">We've also thought through how to make the deployment of updates seamless to you.</span><span class="sxs-lookup"><span data-stu-id="bcbae-144">We've also thought through how to make the deployment of updates seamless to you.</span></span> <span data-ttu-id="bcbae-145">Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span><span class="sxs-lookup"><span data-stu-id="bcbae-145">Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span></span>

[<span data-ttu-id="bcbae-146">Configuration Manager を使用した Windows 10 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="bcbae-146">Deploy Windows 10 updates using Configuration Manager</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[<span data-ttu-id="bcbae-147">Configuration Manager を使用して Microsoft 365 Apps for enterprise を管理する</span><span class="sxs-lookup"><span data-stu-id="bcbae-147">Manage Microsoft 365 Apps for enterprise with Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a><span data-ttu-id="bcbae-148">WindowsとOfficeチャンネルの概要</span><span class="sxs-lookup"><span data-stu-id="bcbae-148">Overview of Windows and Office Channels</span></span>

<span data-ttu-id="bcbae-149">Windows 10は3つのサービスチャンネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="bcbae-149">Windows 10 offers three servicing channels:</span></span>

- <span data-ttu-id="bcbae-150">[\*\* Windows Insiderプログラム\*\*](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider)、組織が次回の機能アップデートで出荷される機能についてテスト、フィードバックを行えるようにする</span><span class="sxs-lookup"><span data-stu-id="bcbae-150">[**Windows Insider Program**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider) for organizations to test and provide feedback on features shipped in the next feature update</span></span>
- <span data-ttu-id="bcbae-151">**Semi-Annualチャンネル**、Feature Updateの配信で年2回、新機能を提供</span><span class="sxs-lookup"><span data-stu-id="bcbae-151">**Semi-Annual Channel** provides new functionality with Feature Update releases twice per year</span></span>
- <span data-ttu-id="bcbae-152">**長期保守チャネル**、長期保守オプションを必要とする専用機に特化して設計</span><span class="sxs-lookup"><span data-stu-id="bcbae-152">**Long Term Servicing Channel** is designed only for specialized devices needing a longer servicing option</span></span>

<span data-ttu-id="bcbae-153">Microsoft 365 は 4 つのサービスチャンネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="bcbae-153">Microsoft 365 offers four servicing channels:</span></span>

- <span data-ttu-id="bcbae-154">[**Office Insiderプログラム**](https://products.office.com/office-insider)、開発中の最新のOffice性能および機能についてテストし、フィードバックを行えるようにする</span><span class="sxs-lookup"><span data-stu-id="bcbae-154">[**Office Insider Program**](https://products.office.com/office-insider) for organizations to test and provide feedback on the newest Office features and functionalities still in development</span></span>
- <span data-ttu-id="bcbae-155">**現在のチャネル**: 利用可能になり次第、ユーザーに最新の Office 機能を提供</span><span class="sxs-lookup"><span data-stu-id="bcbae-155">**Current Channel** to provide users with the newest Office features as soon as they're available</span></span>
- <span data-ttu-id="bcbae-156">**半期エンタープライズ チャネル**: 年2回限定で、新しい機能の実装を提供</span><span class="sxs-lookup"><span data-stu-id="bcbae-156">**Semi-Annual Enterprise Channel** provides new functionality with new features only twice per year</span></span>
- <span data-ttu-id="bcbae-157">**半期エンタープライズ チャネル (プレビュー版)**: パイロット ユーザーとアプリケーション互換性テスト担当者が次回の半期エンタープライズ チャネルをテスト、検証できる、完全にサポートされた Office ビルド</span><span class="sxs-lookup"><span data-stu-id="bcbae-157">**Semi-Annual Enterprise Channel (Preview)** is a fully supported build of Office that enables pilot users and application compatibility testers to test and validate the next Semi-Annual Enterprise Channel</span></span>

<span data-ttu-id="bcbae-158">WindowsとOfficeのサービスチャネルの詳細については、以下のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcbae-158">For detailed information about Windows and Office servicing channels please review the below documentation:</span></span>

- [<span data-ttu-id="bcbae-159">サービスとしてのWindowsの概要</span><span class="sxs-lookup"><span data-stu-id="bcbae-159">Overview of Windows as a Service</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [<span data-ttu-id="bcbae-160">Microsoft 365 Apps 用更新プログラム チャネルの概要</span><span class="sxs-lookup"><span data-stu-id="bcbae-160">Overview of update channels for Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a><span data-ttu-id="bcbae-161">更新プログラムの段階的な展開</span><span class="sxs-lookup"><span data-stu-id="bcbae-161">Phased Deployment of Updates</span></span>

<span data-ttu-id="bcbae-162">Now let’s shift gears to how you will roll out these updates.</span><span class="sxs-lookup"><span data-stu-id="bcbae-162">Now let’s shift gears to how you will roll out these updates.</span></span> <span data-ttu-id="bcbae-163">For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment.</span><span class="sxs-lookup"><span data-stu-id="bcbae-163">For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment.</span></span> <span data-ttu-id="bcbae-164">Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span><span class="sxs-lookup"><span data-stu-id="bcbae-164">Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span></span>

### <a name="monthly-updating"></a><span data-ttu-id="bcbae-165">毎月の更新</span><span class="sxs-lookup"><span data-stu-id="bcbae-165">Monthly Updating</span></span>

<span data-ttu-id="bcbae-166">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates.</span><span class="sxs-lookup"><span data-stu-id="bcbae-166">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates.</span></span> <span data-ttu-id="bcbae-167">As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span><span class="sxs-lookup"><span data-stu-id="bcbae-167">As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span></span>

#### <a name="express-updates"></a><span data-ttu-id="bcbae-168">簡易更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bcbae-168">Express Updates</span></span>

<span data-ttu-id="bcbae-169">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly.</span><span class="sxs-lookup"><span data-stu-id="bcbae-169">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly.</span></span> <span data-ttu-id="bcbae-170">In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span><span class="sxs-lookup"><span data-stu-id="bcbae-170">In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span></span>

[<span data-ttu-id="bcbae-171">Windows 10 の品質の更新プログラムの説明と、差分更新プログラムの終了</span><span class="sxs-lookup"><span data-stu-id="bcbae-171">Windows 10 quality updates explained & the end of delta updates</span></span>](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

<span data-ttu-id="bcbae-172">Windows Update for Business および Windows Server Update Services では簡易更新プログラムを長期間サポートしてきましたが、Microsoft Endpoint Configuration Manager (Current Branch) でも簡易更新プログラムを利用できるようにサポートを拡張しました。</span><span class="sxs-lookup"><span data-stu-id="bcbae-172">Windows Update for Business and Windows Server Update Services have supported express updates for a long time, but we've now extended that support to Microsoft Endpoint Configuration Manager (Current Branch) so that it can also use Express Updates.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a><span data-ttu-id="bcbae-173">バイナリ差分圧縮は</span><span class="sxs-lookup"><span data-stu-id="bcbae-173">Binary Delta Compression</span></span>

<span data-ttu-id="bcbae-174">Office のバイナリ差分圧縮は、Microsoft 365 Apps for enterprise の最新バージョンから更新する場合にのみ使用します。このアプローチを使用するには、以前のビルドから更新する必要があり、更新のスキップはできません。</span><span class="sxs-lookup"><span data-stu-id="bcbae-174">Binary Delta Compression in Office is only used if you're updating from the most recent version of Microsoft 365 Apps for enterprise-- so to use this approach you need to be updating from the previous build and can’t skip updates.</span></span>

<span data-ttu-id="bcbae-175">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process.</span><span class="sxs-lookup"><span data-stu-id="bcbae-175">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process.</span></span> <span data-ttu-id="bcbae-176">Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span><span class="sxs-lookup"><span data-stu-id="bcbae-176">Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span></span>

### <a name="semi-annual-updates"></a><span data-ttu-id="bcbae-177">半期の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bcbae-177">Semi-Annual Updates</span></span>

<span data-ttu-id="bcbae-178">月次更新について考慮しているなら、この機会に、より規模の大きな半期の更新プログラムに移行しましょう。</span><span class="sxs-lookup"><span data-stu-id="bcbae-178">So those are your considerations for monthly updates, now let’s move to the larger, semi-annual updates.</span></span>

<span data-ttu-id="bcbae-179">デバイスとアプリの準備で網羅したように、展開プロセス全体の手順 1 でセットアップしたのと同じ準備ツールを使用して、この大規模な更新プログラムの準備を開始します。</span><span class="sxs-lookup"><span data-stu-id="bcbae-179">As we covered in Device and App Readiness, you’ll want to begin your preparation for these larger updates using the same readiness tools we set up in Step 1 of the deployment process wheel.</span></span>

<span data-ttu-id="bcbae-180">As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="bcbae-180">As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune.</span></span> <span data-ttu-id="bcbae-181">If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span><span class="sxs-lookup"><span data-stu-id="bcbae-181">If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[<span data-ttu-id="bcbae-182">Windows の半期チャネル</span><span class="sxs-lookup"><span data-stu-id="bcbae-182">Windows Semi-Annual Channel</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[<span data-ttu-id="bcbae-183">Microsoft 365 Apps for enterprise 半期エンタープライズ チャネル</span><span class="sxs-lookup"><span data-stu-id="bcbae-183">Semi-Annual Enterprise Channel for Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a><span data-ttu-id="bcbae-184">タスク シーケンスのアップグレード</span><span class="sxs-lookup"><span data-stu-id="bcbae-184">Upgrade Task Sequences</span></span>

<span data-ttu-id="bcbae-185">標準レベルのソフトウェア更新管理のルーチンによる大きな機能の更新プログラムのインストールもサポートされていますが、多くの組織では Microsoft Endpoint Configuration Manager (Current Branch) でのアップグレードのタスク シーケンス、または Microsoft Deployment Toolkit を使用することを選びます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-185">Installing the larger feature updates via standard software update management routines is a supported option, but many organizations will opt to use an Upgrade Task Sequence with Microsoft Endpoint Configuration Manager (Current Branch) or the Microsoft Deployment Toolkit.</span></span>

<span data-ttu-id="bcbae-186">タスク シーケンスを使用すると、機能の更新プログラムをインストールする前にカスタム チェックやタスクを作成でき、更新プログラムのインストール自体が完了した後にカスタム タスクを実行できます。更新、ドライバーのインストールと置き換え、アプリケーションのアップグレード、タスクバーおよび Windows 10 のスタート画面の個人用設定などで、必要に応じてサービスを一時停止することも、更新後のタスクに含まれます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-186">A Task Sequence allows you to create custom checks or tasks BEFORE to the installing the Feature Update and allows you to perform custom tasks AFTER the update installation itself has completed – post-update tasks might include temporarily suspending services if needed during the update, driver installation and replacement, application upgrades or taskbar and Windows 10 Start personalization settings.</span></span>

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

<span data-ttu-id="bcbae-187">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control.</span><span class="sxs-lookup"><span data-stu-id="bcbae-187">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control.</span></span> <span data-ttu-id="bcbae-188">While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences.</span><span class="sxs-lookup"><span data-stu-id="bcbae-188">While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences.</span></span> <span data-ttu-id="bcbae-189">One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade.</span><span class="sxs-lookup"><span data-stu-id="bcbae-189">One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade.</span></span> <span data-ttu-id="bcbae-190">This approach ensures that your user productivity is less impacted.</span><span class="sxs-lookup"><span data-stu-id="bcbae-190">This approach ensures that your user productivity is less impacted.</span></span>

[<span data-ttu-id="bcbae-191">Configuration Manager で OS をアップグレードするタスク シーケンスを作成する</span><span class="sxs-lookup"><span data-stu-id="bcbae-191">Create a task sequence to upgrade an OS in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a><span data-ttu-id="bcbae-192">機能の更新プログラム向けの半期チャネルのサポート</span><span class="sxs-lookup"><span data-stu-id="bcbae-192">Semi-annual channel support for feature updates</span></span>

<span data-ttu-id="bcbae-193">[2018 年 9 月の発表](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)にもあるように、半期チャネルの更新プログラムでサポートされているタイムラインには、次のモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcbae-193">[As announced in September 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), support timeline for semi-annual channel updates will use the following model.</span></span>

  - <span data-ttu-id="bcbae-194">Windows 10 Enterprise および Windows 10 Education でサポートされている機能のすべての更新プログラムは、バージョン 1607 以降、元のリリース日から 30 か月間サポート。</span><span class="sxs-lookup"><span data-stu-id="bcbae-194">All currently supported feature updates of Windows 10 Enterprise and Education, starting with version 1607, will be supported for 30 months from their original release date.</span></span>

  - <span data-ttu-id="bcbae-195">更新を 9 月に予定している 1809 以降の今後のすべての機能更新プログラムは、リリース日から 30 か月間サポート。</span><span class="sxs-lookup"><span data-stu-id="bcbae-195">All future feature updates, starting with 1809, with a targeting September will be supported for 30 months from their release date.</span></span>

  - <span data-ttu-id="bcbae-196">更新を 3 月に予定している機能更新プログラムで、1903 以降のものは、引き続きリリース日から 18 か月間サポート。</span><span class="sxs-lookup"><span data-stu-id="bcbae-196">Future feature updates targeting March and starting with 1903 will continue to be supported for 18 months from their release date.</span></span>

  - <span data-ttu-id="bcbae-197">Microsoft 365 Apps for enterprise 半期チャネル の半期の更新プログラムは、引き続き 18 か月間サポート</span><span class="sxs-lookup"><span data-stu-id="bcbae-197">Microsoft 365 Apps for enterprise semi-annual updates continue to be supported for 18 months</span></span>

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a><span data-ttu-id="bcbae-198">他のセットアップの自動オプション (タスク シーケンス以外)</span><span class="sxs-lookup"><span data-stu-id="bcbae-198">Additional setup automation options outside of task sequences</span></span>

<span data-ttu-id="bcbae-199">アップグレード タスク シーケンスを使用しない場合、現在はカスタム アクションの実行やドライバー ファイルの適用ができます。この操作は、プレインストールでの機能の更新中 (セットアップによる互換性のチェック前)、またはコミット前の段階 (アップグレードの適用前) に実施します。</span><span class="sxs-lookup"><span data-stu-id="bcbae-199">If you don’t use Upgrade Task Sequences, you can now run custom actions or apply driver files during feature updates in the Pre-install phase – before setup runs its compatibility checks – or in the pre-commit phase – before the upgrade is applied.</span></span>

[<span data-ttu-id="bcbae-200">Windows 10 のセットアップの新機能 (バージョン 1803)</span><span class="sxs-lookup"><span data-stu-id="bcbae-200">What's new in Windows 10 setup, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a><span data-ttu-id="bcbae-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="bcbae-201">Next Step</span></span> 

## <a name="step-8-user-communications-and-training"></a>[<span data-ttu-id="bcbae-202">手順 8: ユーザーのコミュニケーションとトレーニング</span><span class="sxs-lookup"><span data-stu-id="bcbae-202">Step 8: User Communications and Training</span></span>](https://aka.ms/mdd8)

## <a name="previous-step"></a><span data-ttu-id="bcbae-203">前の手順</span><span class="sxs-lookup"><span data-stu-id="bcbae-203">Previous Step</span></span> 

## <a name="step-6-os-deployment-and-feature-updates"></a>[<span data-ttu-id="bcbae-204">手順 6: OS の展開と機能の更新</span><span class="sxs-lookup"><span data-stu-id="bcbae-204">Step 6 OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)
