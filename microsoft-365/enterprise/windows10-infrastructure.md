---
title: Microsoft 365 enterprise の Windows 10 enterprise インフラストラクチャ
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289439"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="95e64-104">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="95e64-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="95e64-105">Microsoft 365 enterprise には、Windows 10 enterprise が含まれています。これにより、より多くの機能を提供し、安全な状態を維持できます。</span><span class="sxs-lookup"><span data-stu-id="95e64-105">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="95e64-106">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="95e64-106">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="95e64-107">**は、シンプル化のために統合されてい**ます-クラウドのパワーを活用して、今日の最新の IT デバイス環境の管理の複雑さを軽減します。サイズに関係なく使用できます。</span><span class="sxs-lookup"><span data-stu-id="95e64-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="95e64-108">**インテリジェントセキュリティがあり**ます。これは、Windows の最も安全なリリースです。これは、組織の保護を強化するために連携して機能するように設計されたインテリジェントなセキュリティ機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="95e64-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="95e64-109">**創造性とチームワークを有効**にして、創造性とチームワークのロックを解除することで、ユーザーとユーザーの両方にとって最も生産性の高い操作性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="95e64-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="95e64-110">Windows 10 オペレーティングシステムを展開するためのさまざまな方法を理解し、組織に適したものを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95e64-110">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="95e64-111">Microsoft 365 Enterprise のサブスクリプションによっては、windows 10 のサービスとセキュリティ機能も備えており、windows 10 を最大限に活用するために構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95e64-111">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="95e64-112">Windows 10 では、Microsoft 365 Enterprise の次の戦略的なビジネスシナリオが有効になります。</span><span class="sxs-lookup"><span data-stu-id="95e64-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="95e64-113">集合知や専門知識を活用し、組織全体でファイル、情報、アイデアを発見、共有、発展させるよう人々を支援します</span><span class="sxs-lookup"><span data-stu-id="95e64-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="95e64-114">柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます</span><span class="sxs-lookup"><span data-stu-id="95e64-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="95e64-115">業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します</span><span class="sxs-lookup"><span data-stu-id="95e64-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="95e64-116">情報を保護して、データ損失のリスクを軽減します</span><span class="sxs-lookup"><span data-stu-id="95e64-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="95e64-117">外部の脅威を検出して保護する--監視、報告、および分析を行って、組織のセキュリティを迅速に提供する</span><span class="sxs-lookup"><span data-stu-id="95e64-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="95e64-118">ユーザーとそのアカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="95e64-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="95e64-119">一般データ保護規則 (GDPR) に適合するように、強化されたプライバシーと法令遵守によって組織をサポートします。</span><span class="sxs-lookup"><span data-stu-id="95e64-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="95e64-120">デスクトップ ソフトウェアやデバイスで最新情報を入手し、セキュリティ上のリスクの軽減と IT 効率の最大化を図ります</span><span class="sxs-lookup"><span data-stu-id="95e64-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="95e64-121">詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="95e64-122">Windows 10 Enterprise と Office 365 ProPlus の両方を展開し、[モダン デスクトップ](https://www.microsoft.com/microsoft-365/modern-desktop)に移行するには、「[モダン デスクトップ展開センター](http://aka.ms/howtoshift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="95e64-123">Windows 10 の展開</span><span class="sxs-lookup"><span data-stu-id="95e64-123">Windows 10 deployment</span></span>

<span data-ttu-id="95e64-124">組織に Windows 10 Enterprise を展開する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="95e64-124">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="95e64-125">ここでは、これらのモダン展開シナリオを使用して Windows 10 Enterprise イメージを構成および展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95e64-125">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="95e64-126">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="95e64-126">Deployment scenario</span></span> | <span data-ttu-id="95e64-127">使用する状況</span><span class="sxs-lookup"><span data-stu-id="95e64-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="95e64-128">System Center Configuration Manager を一括アップグレードとして使用する</span><span class="sxs-lookup"><span data-stu-id="95e64-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="95e64-129">windows 7 または windows 8.1 コンピューターを windows 10 Enterprise の<a href="https://aka.ms/windows-10-release-information" target="_blank">現在のバージョン</a>にアップグレードする必要があり、コンピューターが現在<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (current branch)</a>で管理されている場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="95e64-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="95e64-130">Windows 自動操縦の使用</span><span class="sxs-lookup"><span data-stu-id="95e64-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="95e64-131">windows 10 Enterprise、バージョン1703以降が事前インストールされている windows コンピューターを新たにセットアップする場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="95e64-131">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="95e64-132">エンドユーザーは、職場または学校のアカウントの資格情報を入力することによって、目的の構成を使用してセットアップを開始します。</span><span class="sxs-lookup"><span data-stu-id="95e64-132">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="95e64-133">これらの展開シナリオが組織のニーズに合わない場合は、他のシナリオについて学習し、 [Windows 10 の展開シナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)での各機能と制限事項について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="95e64-133">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="95e64-134">また、 <a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 の展開を</a>独自に計画することもできます。</span><span class="sxs-lookup"><span data-stu-id="95e64-134">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="95e64-135">Windows 10 の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="95e64-136">Microsoft 365 Enterprise 製品ページ</span><span class="sxs-lookup"><span data-stu-id="95e64-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="95e64-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="95e64-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="95e64-138">Windows 10 を展開、更新する</span><span class="sxs-lookup"><span data-stu-id="95e64-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="95e64-139">その他のサービスと機能</span><span class="sxs-lookup"><span data-stu-id="95e64-139">Additional services and features</span></span>
<span data-ttu-id="95e64-140">Windows 10 Enterprise の展開の一環として、これらの追加のサービスと機能を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="95e64-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="95e64-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="95e64-141">Windows Analytics</span></span>

<span data-ttu-id="95e64-142">windows は診断データを使用して、環境内の windows 10 デバイスの運用効率と正常性に関する詳細な洞察を得るために役立つ豊富で実用的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="95e64-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="95e64-143">アップグレードの準備状況-アップグレードの準備は、windows 10 に移行し、新しい windows 10 機能の更新プログラムを最新の状態に保つのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95e64-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="95e64-144">コンプライアンスの更新-更新プログラムのコンプライアンスは、追加のインフラストラクチャ要件を伴わずに、すべての Windows 10 デバイスの全体的なビューを取得する IT 管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="95e64-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="95e64-145">デバイスの正常性-デバイスの正常性を使用して、問題に影響を与えるエンドユーザーを事前に検出して修復することができます。</span><span class="sxs-lookup"><span data-stu-id="95e64-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="95e64-146">詳細については、「 [Windows Analytics の概要](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="95e64-147">Windows セキュリティ</span><span class="sxs-lookup"><span data-stu-id="95e64-147">Windows security</span></span>

<span data-ttu-id="95e64-148">Windows 10 では、脅威からの保護、デバイスのセキュリティ保護、およびアクセス制御のサポートに役立つ機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="95e64-148">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="95e64-149">Windows 10 では、デバイスを最初から保護する重要なセキュリティ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="95e64-149">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="95e64-150">Microsoft 365 E3 は、windows Hello for business、windows Defender アプリケーションコントロール、および windows 情報保護などのセキュリティ機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="95e64-150">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="95e64-151">microsoft 365 E5 を使用すると、microsoft 365 E3 セキュリティ、クラウドベースのセキュリティ機能、および Windows Defender Advanced Threat protection からのすべての保護を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="95e64-151">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="95e64-152">windows 10 enterprise で利用できるセキュリティ機能の詳細については、「[手順 5: windows 10 enterprise のセキュリティ機能](windows10-enable-security-features.md)を展開、管理、構成、およびトラブルシューティングする」のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="95e64-153">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="95e64-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="95e64-154">Microsoft の内部をピークし、Windows 10 の更新プログラムを展開し、管理する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="95e64-155">Windows 10 をシームレスに展開するための組織の準備</span><span class="sxs-lookup"><span data-stu-id="95e64-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="95e64-156">Microsoft では、サービスとして Windows を使用</span><span class="sxs-lookup"><span data-stu-id="95e64-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="95e64-157">Microsoft における、Windows 10 のインプレース アップグレードとしての展開方法</span><span class="sxs-lookup"><span data-stu-id="95e64-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="95e64-158">Windows Hello for Business を使用した、強力なユーザー認証の実装</span><span class="sxs-lookup"><span data-stu-id="95e64-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="95e64-159">[Windows 10 の展開: Microsoft の IT 担当者からのヒント](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="95e64-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="95e64-160">Windows Defender ATP により高度な脅威の検出が可能</span><span class="sxs-lookup"><span data-stu-id="95e64-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="95e64-161">[Windows Defender および Windows Defender ATP を使用した、現代の企業のセキュリティ保護](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="95e64-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="95e64-162">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="95e64-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="95e64-163">架空の多国籍企業である Contoso Corporation が[Windows 10 Enterprise を展開](contoso-win10.md)した方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e64-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="95e64-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="95e64-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="95e64-165">Windows 10 Enterprise を組織で展開するための準備</span><span class="sxs-lookup"><span data-stu-id="95e64-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
