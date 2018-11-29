---
title: 手順 7 - サービスとしての Windows および Office
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: サービスとしての Windows および Office をお使いの環境で準備する方法について説明します。
ms.openlocfilehash: 5c3eb54e07b1cc5492a6d938e97286283fc47ca7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869393"
---
# <a name="step-7-windows-and-office-as-a-service"></a><span data-ttu-id="1dac7-103">手順 7: サービスとしての Windows および Office</span><span class="sxs-lookup"><span data-stu-id="1dac7-103">Step 7: Windows and Office as a Service</span></span>

<span data-ttu-id="1dac7-104">System Center Configuration Manager の Current Branch の管理ツールに対応する更新とともに、Windows 10 および Office 365 ProPlus の新機能を備えた半期チャネルの更新を行う準備をします。</span><span class="sxs-lookup"><span data-stu-id="1dac7-104">Prepare for semi-annual channel updates with new features and capabilities in Windows 10 and Office 365 ProPlus along with corresponding updates to management tools with System Center Configuration Manager Current Branch.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><span data-ttu-id="1dac7-105"><strong>手順 7: サービスとしての Windows および Office の準備</strong></span><span class="sxs-lookup"><span data-stu-id="1dac7-105"><strong>Step 7: Preparing for Windows and Office as a Service</strong></span></span></p>
<p><span data-ttu-id="1dac7-p101">Windows 10 と Office 365 ProPlus には、最新の技術革新によりユーザー エクスペリエンスとセキュリティを継続的に維持するための新しい機能が継続的に追加されます。更新プログラムを半期ごと、および毎月適用して最新の状態を維持する方法について説明します。また、新しいサービス モデルがどのように機能し、どういったツールやオプションを利用できるのかについても紹介します。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p101">Both Windows 10 and Office 365 ProPlus continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</span></span></p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="1dac7-p102">サービスとしての Windows および Office は、半期ごとの機能の更新のための準備の計画局面をカバーする、推奨される展開プロセス全体の中で 7 つ目の手順です。完全なデスクトップの展開プロセスを確認するには、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p102">Windows and Office as a Service is the seventh step in our recommended deployment process wheel covering the planning aspects of preparing for semi-annual updates to features. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="1dac7-p103">Windows 10 と Office 365 ProPlus には、新しいサービス オプション、モデルのサポート、更新タイムラインが導入されています。これらのサポートにより、最新機能の状態を維持するプロセスが簡素化されます。また、これらの更新機能に加えて、お客様のニーズに即したサービス計画を実現させる新しい設定オプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p103">Both Windows 10 and Office 365 ProPlus introduce new servicing options, support models and update timelines. These changes simplify the process for staying current on the latest features. Along with these updates are new configuration options to enable servicing plans that meet your needs.</span></span>

[<span data-ttu-id="1dac7-113">ユーザーのモダン デスクトップへの移行のサポート</span><span class="sxs-lookup"><span data-stu-id="1dac7-113">Helping customers shift to a modern desktop</span></span>](https://www.microsoft.com/ja-JP/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a><span data-ttu-id="1dac7-114">更新プログラムの種類</span><span class="sxs-lookup"><span data-stu-id="1dac7-114">Update Types</span></span>

<span data-ttu-id="1dac7-p104">更新プログラムは主に 2 つのカテゴリに分類されます。機能の更新プログラムと、品質およびセキュリティの更新プログラムで、後者には累積的なセキュリティ、信頼性、バグの修正プログラムが含まれます。半期チャネルの具体的な時期は 3 月と 9 月の年 2 回で、Windows と Office の両方に新機能が提供されます。品質とセキュリティの更新は毎月行われます。ただし、Office 365 アプリの場合は例外で、機能の更新プログラムと品質の更新プログラムの両方が完全にサポートされている月次チャネルが配信されます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p104">Updates fall into two main categories, feature updates and then quality and security updates which contain cumulative security, reliability and bug fixes. In terms of cadence both Windows and Office deliver a semi-annual channel which delivers new features twice per year around March and September while Quality and Security Updates occur Monthly. Additionally, unique to Office 365 Apps, we deliver Monthly Channel updates that are fully-supported and contain both new features and quality updates.</span></span>

<span data-ttu-id="1dac7-118">デスクトップ OS の更新プログラムとアプリの更新プログラムの長いサイクルをご存知であれば、以下のような疑問点が出てくるかと思います。</span><span class="sxs-lookup"><span data-stu-id="1dac7-118">If you’re used to a longer cycle between desktop OS and app updates, you might be wondering;</span></span>

  - <span data-ttu-id="1dac7-119">更新プログラムに互換性はあるのか</span><span class="sxs-lookup"><span data-stu-id="1dac7-119">Will the updates be compatible?</span></span>

  - <span data-ttu-id="1dac7-120">ユーザーの再トレーニングは必要なのか</span><span class="sxs-lookup"><span data-stu-id="1dac7-120">Will I need to keep retraining my users?</span></span>

  - <span data-ttu-id="1dac7-121">どんなリスクがあるか</span><span class="sxs-lookup"><span data-stu-id="1dac7-121">And what are the risks?</span></span>

<span data-ttu-id="1dac7-122">上記疑問の解消につながるよう、以下に新しい機能を頻繁に提供する理由とその利点をいくつか挙げています</span><span class="sxs-lookup"><span data-stu-id="1dac7-122">To answer those questions and the rationale for delivering new capabilities more frequently, we’ll some of the advantages of this approach</span></span>

### <a name="feature-update-benefits"></a><span data-ttu-id="1dac7-123">機能の更新の利点</span><span class="sxs-lookup"><span data-stu-id="1dac7-123">Feature Update Benefits</span></span>

<span data-ttu-id="1dac7-p105">まず、3 年ごとに大規模な変更を加える過去のモデルから、年に 2 回の機能更新を行う小規模な変化へと移行しました。テクノロジの動向は急速に変化し、セキュリティ上の脅威も増え続けており、頻繁な機能更新を行えばエクスペリエンスと保護を最新の状態に保てるというのが主な理由です。たとえば、セキュリティに関連する更新プログラムの一部は、毎月のセキュリティ更新プログラムやウイルス対策シグネチャ ファイルだけでは配信できません。仮想化ベースのセキュリティのような低レベルの変更のプラットフォームなどがこの例に該当します。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p105">First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.</span></span>

[<span data-ttu-id="1dac7-128">サービスとしての Windows のクイック ガイド</span><span class="sxs-lookup"><span data-stu-id="1dac7-128">Quick guide to Windows as a service</span></span>](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-quick-start)

[<span data-ttu-id="1dac7-129">Windows 10 のセキュリティ機能を使用して脅威を軽減する</span><span class="sxs-lookup"><span data-stu-id="1dac7-129">Mitigate threats by using Windows 10 security features</span></span>](https://docs.microsoft.com/ja-JP/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a><span data-ttu-id="1dac7-130">累積的な更新モデルの利点</span><span class="sxs-lookup"><span data-stu-id="1dac7-130">Cumulative Update Model Benefits</span></span>

<span data-ttu-id="1dac7-p106">また、累積的な更新プログラムのパッケージとして品質およびセキュリティの更新プログラムを提供することは、過去の多くの問題を修正します。これまでは、Windows と Office の両方について、毎月 12 個以上の更新プログラムを選択しなければならない場合がありました。その場合、サポートがほぼ不可能な一連のテスト行列が作成されてしまいます。また、1 年以上経過した Windows または Office のバージョンをインストールする場合、そのバージョンのリリース後に配信されたすべての更新プログラムの適用には、数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p106">Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.</span></span>

<span data-ttu-id="1dac7-p107">累積モデルでは、常に最新のものから 1 つの更新が行われます。そのため、導入する必要がある毎月の更新プログラムの数が減ります。それぞれの更新プログラムは、過去数か月の更新に基づいて構成されており、最新の状態に保つために必要なすべての修正プログラムが含まれています。特に、数か月間 PC の電源が切られている場合は、PC が別のユーザーに再割り当てされるのを待機している保存状態にあるため、累積的な更新プログラムが特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p107">With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.</span></span>

[<span data-ttu-id="1dac7-138">サービスとしての Windows の概要</span><span class="sxs-lookup"><span data-stu-id="1dac7-138">Overivew of Windows as a service</span></span>](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-overview)

### <a name="expanded-validation-of-updates"></a><span data-ttu-id="1dac7-139">更新プログラムの検証の範囲が拡大</span><span class="sxs-lookup"><span data-stu-id="1dac7-139">Expanded Validation of Updates</span></span>

<span data-ttu-id="1dac7-p108">他にも利点があります。広範囲な展開を行う更新プログラムを公開する前に、[Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) と [Windows](https://insider.windows.com/ja-JP/) の Insider Program を介して最初にビルドをリリースすることにより、広範囲に更新プログラムをリリースする前に、テレメトリとフィードバックの収集ができます。Insider Program は一般公開されているので、更新プログラムよりも先に内容を確認することができます。更新プログラムをリリースする時までに何百万もの構成からテレメトリを取得しているため、更新プログラムの公開時に、品質を本質的に予測できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p108">Another advantage is that, before we roll out updates for broad deployment, we first release builds via the Insider programs for [Office](https://products.office.com/en-us/office-insider?tab=Windows-Desktop) and [Windows](https://insider.windows.com/ja-JP/), and this allows us to gather telemetry and feedback ahead of us releasing updates broadly. Now the Insider programs are open to everyone so that you can get ahead of understanding the updates. By the time we release updates we will have received telemetry from millions of configurations, so when we do roll out updates, quality is now inherently more predictable</span></span>

<span data-ttu-id="1dac7-143">もう 1 つの点として、Office 365 ProPlus の Insider ビルドに月次チャネルの更新が反映されるため、Windows に準じて、Office に半期チャネルを適用して機能の更新プログラムを年に 2 回配信する場合は、半期チャネル対象のリリースによる半期ごとの検証を早期に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-143">AND one more thing, because Office 365 ProPlus Insider builds reflect monthly channel updates, if you are using semi-annual channel for Office to deliver feature updates twice per year aligned to Windows, you can validate those builds early as well using the semi-annual channel targeted releases.</span></span>

### <a name="supporting-management-tools"></a><span data-ttu-id="1dac7-144">管理ツールをサポート</span><span class="sxs-lookup"><span data-stu-id="1dac7-144">Supporting Management Tools</span></span>

<span data-ttu-id="1dac7-p109">更新プログラムの展開をどのようにシームレスに行うかについても検討を重ねました。Windows、Office、その他の新しい機能に対する更新プログラムの公開をサポートするために、System Center Configuration Manager の Current Branch は頻繁に更新されています。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p109">We've also thought through how to make the deployment of updates seamless to you. System Center Configuration Manager Current Branch is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.</span></span>

[<span data-ttu-id="1dac7-147">System Center Configuration Manager を使用した Windows 10 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="1dac7-147">Deploy Windows 10 updates using System Center Configuration Manager</span></span>](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-manage-updates-configuration-manager)

[<span data-ttu-id="1dac7-148">Configuration Manager を使用した Office 365 ProPlus の管理</span><span class="sxs-lookup"><span data-stu-id="1dac7-148">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/ja-JP/sccm/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="phased-deployment-of-updates"></a><span data-ttu-id="1dac7-149">更新プログラムの段階的な展開</span><span class="sxs-lookup"><span data-stu-id="1dac7-149">Phased Deployment of Updates</span></span>

<span data-ttu-id="1dac7-p110">ここで、これらの更新プログラムの公開の方法について説明します。いずれのリリースについても、IT の少なくとも 3 つの導入フェーズ (検証、パイロット、幅広い製品展開) を取り入れることを推奨します。Windows 10 および Office 365 ProPlus を起動し実行してからは、毎月のサービスを使用し、セキュリティと品質に関する重要な更新プログラムを適用して最新の状態に保ちます。その後、新しい機能向けに半期のサービスに移行します。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p110">Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Office 365 ProPlus, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.</span></span>

### <a name="monthly-updating"></a><span data-ttu-id="1dac7-153">毎月の更新</span><span class="sxs-lookup"><span data-stu-id="1dac7-153">Monthly Updating</span></span>

<span data-ttu-id="1dac7-p111">サービス モデルは、新機能の公開を年 2 回に制限するように設計されており、必要に応じて半期の更新をスキップして、品質とセキュリティの更新プログラムを引き続き受信することもできます。前述のように、毎月の累積的な更新プログラムは、月ごとにサイズが増加していきます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p111">The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.</span></span>

#### <a name="express-updates"></a><span data-ttu-id="1dac7-156">簡易更新プログラム</span><span class="sxs-lookup"><span data-stu-id="1dac7-156">Express Updates</span></span>

<span data-ttu-id="1dac7-p112">Windows の「簡易更新プログラム」と、Office のバイナリ差分圧縮と呼ばれる技術を使用して、ダウンロード サイズを大幅に削減することができます。どちらのアプローチでも、更新プログラムのエンジンは PC に何があるかを比較し、その PC 上で更新する必要な差分のみを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p112">Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.</span></span>

[<span data-ttu-id="1dac7-159">Windows 10 の品質の更新プログラムの説明と、差分更新プログラムの終了</span><span class="sxs-lookup"><span data-stu-id="1dac7-159">Windows 10 quality updates explained & the end of delta updates</span></span>](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

<span data-ttu-id="1dac7-160">Windows Update for Business および Windows Server Update Services では簡易更新プログラムを長期間サポートしてきましたが、System Center Configuration Manager でも簡易更新プログラムを利用できるようにサポートを拡張しました。</span><span class="sxs-lookup"><span data-stu-id="1dac7-160">Windows Update for Business and Windows Server Update Services have supported express updates for a long time, but we've now extended that support to System Center Configuration Manager so that it can also use Express Updates.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a><span data-ttu-id="1dac7-161">バイナリ差分圧縮</span><span class="sxs-lookup"><span data-stu-id="1dac7-161">Binary Delta Compression</span></span>

<span data-ttu-id="1dac7-162">Office のバイナリ差分圧縮は、Office 365 ProPlus の最新バージョンから更新する場合にのみ使用します。このアプローチを使用するには、以前のビルドから更新する必要があり、更新のスキップはできません。</span><span class="sxs-lookup"><span data-stu-id="1dac7-162">Binary Delta Compression in Office is only used if you're updating from the most recent version of Office 365 ProPlus-- so to use this approach you need to be updating from the previous build and can’t skip updates.</span></span>

<span data-ttu-id="1dac7-p113">Windows および Office の更新プログラム チャネルは、標準レベルの承認およびターゲット プロセスを使用して Configuration Manager で管理できます。さらに、Office および Windows のポリシー設定で、使用中の更新プログラム チャネルと関連する設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p113">Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.</span></span>

### <a name="semi-annual-updates"></a><span data-ttu-id="1dac7-165">半期の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="1dac7-165">Semi-Annual Updates</span></span>

<span data-ttu-id="1dac7-166">月次更新について考慮しているなら、この機会に、より規模の大きな半期の更新プログラムに移行しましょう。</span><span class="sxs-lookup"><span data-stu-id="1dac7-166">So those are your considerations for monthly updates, now let’s move to the larger, semi-annual updates.</span></span>

<span data-ttu-id="1dac7-167">デバイスとアプリの準備で網羅したように、展開プロセス全体の手順 1 でセットアップしたのと同じ準備ツールを使用して、この大規模な更新プログラムの準備を開始します。</span><span class="sxs-lookup"><span data-stu-id="1dac7-167">As we covered in Device and App Readiness, you’ll want to begin your preparation for these larger updates using the same readiness tools we set up in Step 1 of the deployment process wheel.</span></span>

<span data-ttu-id="1dac7-p114">ツールに関しては、Windows Update for Business でのポリシー設定、System Center Configuration Manager によるソフトウェアの更新管理、Windows Server Update Services (WSUS)、または Microsoft Intune で設定された更新ポリシーを使用できます。ネットワーク帯域幅に関して懸念がある場合は、「手順 2: ディレクトリとネットワークの準備」を参照してください。配信の最適化や他のピアツーピアのキャッシング技術によるネットワーク トラフィック削減に関するオプションの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p114">As for tooling, you can use policy settings with Windows Update for Business, software update management via System Center Configuration Manager, Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[<span data-ttu-id="1dac7-170">Windows の半期チャネル</span><span class="sxs-lookup"><span data-stu-id="1dac7-170">Windows Semi-Annual Channel</span></span>](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-overview#semi-annual-channel)

[<span data-ttu-id="1dac7-171">Office 365 ProPlus の半期チャネル</span><span class="sxs-lookup"><span data-stu-id="1dac7-171">Semi-Annual Channel for Office 365 ProPlus</span></span>](https://docs.microsoft.com/ja-JP/DeployOffice/overview-of-update-channels-for-office-365-proplus#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a><span data-ttu-id="1dac7-172">タスク シーケンスのアップグレード</span><span class="sxs-lookup"><span data-stu-id="1dac7-172">Upgrade Task Sequences</span></span>

<span data-ttu-id="1dac7-173">標準レベルのソフトウェア更新管理のルーチンによる大きな機能の更新プログラムのインストールもサポートされていますが、多くの組織では System Center Configuration Manager でのアップグレードのタスク シーケンス、または Microsoft Deployment Toolkit を使用することを選びます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-173">Installing the larger feature updates via standard software update management routines is a supported option, but many organizations will opt to use an Upgrade Task Sequence with System Center Configuration Manager or the Microsoft Deployment Toolkit.</span></span>

<span data-ttu-id="1dac7-174">タスク シーケンスを使用すると、機能の更新プログラムをインストールする前にカスタム チェックやタスクを作成でき、更新プログラムのインストール自体が完了した後にカスタム タスクを実行できます。更新、ドライバーのインストールと置き換え、アプリケーションのアップグレード、タスクバーおよび Windows 10 のスタート画面の個人用設定などで、必要に応じてサービスを一時停止することも、更新後のタスクに含まれます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-174">A Task Sequence allows you to create custom checks or tasks BEFORE to the installing the Feature Update and allows you to perform custom tasks AFTER the update installation itself has completed – post-update tasks might include temporarily suspending services if needed during the update, driver installation and replacement, application upgrades or taskbar and Windows 10 Start personalization settings.</span></span>

![](media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

<span data-ttu-id="1dac7-p115">Windows 7 のコンピューターを Windows 10 に移行するために既にタスク シーケンスを使用していて、それらのツールに精通している場合は、移行を開始することをお勧めします。移行後は操作性も格段に向上します。アップグレード全体で 1 つのみのタスク シーケンスを使用することはできますが、組織では 2 つのタスク シーケンスを使用するのが一般的です。1 つのタスク シーケンスは、コンピューターがアップグレードの準備ができていることを確認し、対象のコンピューター上に必要なセットアップ ファイルすべてを、ダイアログを表示せずに事前にステージングします。もう 1 つのタスク シーケンスは実際のアップグレードを行います。このアプローチにより、ユーザーの生産性の低下を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-p115">If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.</span></span>

[<span data-ttu-id="1dac7-179">Configuration Manager で OS をアップグレードするタスク シーケンスを作成する</span><span class="sxs-lookup"><span data-stu-id="1dac7-179">Create a task sequence to upgrade an OS in Configuration Manager</span></span>](https://docs.microsoft.com/ja-JP/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a><span data-ttu-id="1dac7-180">機能の更新プログラム向けの半期チャネルのサポート</span><span class="sxs-lookup"><span data-stu-id="1dac7-180">Semi-annual channel support for feature updates</span></span>

<span data-ttu-id="1dac7-181">[2018 年 9 月の発表](https://www.microsoft.com/ja-JP/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)にもあるように、半期チャネルの更新プログラムでサポートされているタイムラインには、次のモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1dac7-181">[As announced in September 2018](https://www.microsoft.com/ja-JP/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), support timeline for semi-annual channel updates will use the following model.</span></span>

  - <span data-ttu-id="1dac7-182">Windows 10 Enterprise および Windows 10 Education でサポートされている機能のすべての更新プログラムは、バージョン 1607 以降、元のリリース日から 30 か月間サポート。</span><span class="sxs-lookup"><span data-stu-id="1dac7-182">All currently supported feature updates of Windows 10 Enterprise and Education, starting with version 1607, will be supported for 30 months from their original release date.</span></span>

  - <span data-ttu-id="1dac7-183">更新を 9 月に予定している 1809 以降の今後のすべての機能更新プログラムは、リリース日から 30 か月間サポート。</span><span class="sxs-lookup"><span data-stu-id="1dac7-183">All future feature updates, starting with 1809, with a targeting September will be supported for 30 months from their release date.</span></span>

  - <span data-ttu-id="1dac7-184">更新を 3 月に予定している機能更新プログラムで、1903 以降のものは、引き続きリリース日から 18 か月間サポート。</span><span class="sxs-lookup"><span data-stu-id="1dac7-184">Future feature updates targeting March and starting with 1903 will continue to be supported for 18 months from their release date.</span></span>

  - <span data-ttu-id="1dac7-185">Office 365 ProPlus の半期の更新プログラムは、引き続き 18 か月間サポート</span><span class="sxs-lookup"><span data-stu-id="1dac7-185">Office 365 ProPlus semi-annual updates continue to be supported for 18 months</span></span>

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a><span data-ttu-id="1dac7-186">他のセットアップの自動オプション (タスク シーケンス以外)</span><span class="sxs-lookup"><span data-stu-id="1dac7-186">Additional setup automation options outside of task sequences</span></span>

<span data-ttu-id="1dac7-187">アップグレード タスク シーケンスを使用しない場合、現在はカスタム アクションの実行やドライバー ファイルの適用ができます。この操作は、プレインストールでの機能の更新中 (セットアップによる互換性のチェック前)、またはコミット前の段階 (アップグレードの適用前) に実施します。</span><span class="sxs-lookup"><span data-stu-id="1dac7-187">If you don’t use Upgrade Task Sequences, you can now run custom actions or apply driver files during feature updates in the Pre-install phase – before setup runs its compatibility checks – or in the pre-commit phase – before the upgrade is applied.</span></span>

[<span data-ttu-id="1dac7-188">Windows 10 のセットアップの新機能 (バージョン 1803)</span><span class="sxs-lookup"><span data-stu-id="1dac7-188">What's new in Windows 10 setup, version 1803</span></span>](https://docs.microsoft.com/ja-JP/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a><span data-ttu-id="1dac7-189">次の手順</span><span class="sxs-lookup"><span data-stu-id="1dac7-189">Next Step</span></span> 

## <a name="step-8-user-communications-and-traininghttpsakamsmdd8"></a>[<span data-ttu-id="1dac7-190">手順 8: ユーザーのコミュニケーションとトレーニング</span><span class="sxs-lookup"><span data-stu-id="1dac7-190">Step 8: User Communications and Training</span></span>](https://aka.ms/mdd8)

## <a name="previous-step"></a><span data-ttu-id="1dac7-191">前の手順</span><span class="sxs-lookup"><span data-stu-id="1dac7-191">Previous Step</span></span> 

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[<span data-ttu-id="1dac7-192">手順 6: OS の展開と機能の更新</span><span class="sxs-lookup"><span data-stu-id="1dac7-192">Step 6 OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)