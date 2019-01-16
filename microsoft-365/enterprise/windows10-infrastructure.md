---
title: 365 企業の Microsoft Windows の 10 のエンタープライズ ・ インフラストラクチャ
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869003"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="c0e9d-104">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0e9d-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="c0e9d-p101">Microsoft 365 エンタープライズには、複数の操作を行い、安全性を確保するためのツールを使用する、Windows 10 企業が含まれています。Windows 10 企業。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-p101">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure. Windows 10 Enterprise:</span></span>

- <span data-ttu-id="c0e9d-107">サイズに関係なく、今日の IT デバイス環境の**簡略化のための統合は、** 今日の管理の複雑さを軽減するのには、クラウドの機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="c0e9d-108">**インテリジェントなセキュリティに**、これまで最もセキュリティで保護された Windows のリリースは、インテリジェントなセキュリティ機能を適切に連携して動作するように設計された保護を実現します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="c0e9d-109">ロックを解除**により創造性とチームワーク**の創造性とチームワークを最も生産性の高い配信が発生する両方のユーザーと IT が大好きです。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="c0e9d-p102">10 の Windows オペレーティング システムを展開して、組織にふさわしいものを選択するには、さまざまな方法を理解する必要があります。によって、Microsoft 365 エンタープライズ サブスクリプションの場合はまた 10 の Windows サービスとセキュリティ機能を Windows の 10 を最大限に活用するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-p102">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization. Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="c0e9d-112">Windows 10 では、Microsoft 365 企業の戦略的なビジネス シナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="c0e9d-113">集合知や専門知識を活用し、組織全体でファイル、情報、アイデアを発見、共有、発展させるよう人々を支援します</span><span class="sxs-lookup"><span data-stu-id="c0e9d-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="c0e9d-114">柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます</span><span class="sxs-lookup"><span data-stu-id="c0e9d-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="c0e9d-115">業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します</span><span class="sxs-lookup"><span data-stu-id="c0e9d-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="c0e9d-116">情報を保護して、データ損失のリスクを軽減します</span><span class="sxs-lookup"><span data-stu-id="c0e9d-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="c0e9d-117">検出し外部の脅威--モニター レポートからの保護し、組織のセキュリティを提供するのには迅速に対応する利用状況を分析</span><span class="sxs-lookup"><span data-stu-id="c0e9d-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="c0e9d-118">ユーザーと自分のアカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="c0e9d-119">一般データ保護規則 (GDPR) に適合するように、強化されたプライバシーと法令遵守によって組織をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="c0e9d-120">デスクトップ ソフトウェアやデバイスで最新情報を入手し、セキュリティ上のリスクの軽減と IT 効率の最大化を図ります</span><span class="sxs-lookup"><span data-stu-id="c0e9d-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="c0e9d-121">詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="c0e9d-122">Windows 10 Enterprise と Office 365 ProPlus の両方を展開し、[モダン デスクトップ](https://www.microsoft.com/microsoft-365/modern-desktop)に移行するには、「[モダン デスクトップ展開センター](http://aka.ms/howtoshift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="c0e9d-123">10 の Windows の展開</span><span class="sxs-lookup"><span data-stu-id="c0e9d-123">Windows 10 deployment</span></span>

<span data-ttu-id="c0e9d-p103">10 エンタープライズの Windows を展開するには、組織の複数の方法もあります。ここでは、構成し、これらの最近の展開シナリオを 10 企業の Windows イメージを展開する方法に注目しています。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-p103">There are multiple ways you can deploy Windows 10 Enterprise for your organization. Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="c0e9d-126">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="c0e9d-126">Deployment scenario</span></span> | <span data-ttu-id="c0e9d-127">それを使用する場合</span><span class="sxs-lookup"><span data-stu-id="c0e9d-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="c0e9d-128">システム センター構成マネージャーを使用して、インプレース アップグレードとして</span><span class="sxs-lookup"><span data-stu-id="c0e9d-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="c0e9d-129">Windows 7 をアップグレードする必要があるか、10 企業の Windows の<a href="https://aka.ms/windows-10-release-information" target="_blank">現在のバージョン</a>の Windows 8.1 のコンピューターと、コンピューターが<a href="https://aka.ms/introtosccm" target="_blank">システム センター構成マネージャー (現在の分岐)</a>で現在管理は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="c0e9d-130">Windows の自動操縦を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="c0e9d-p104">Windows 10 企業、1703 または後で、事前にインストールされたバージョンを持つ新規の Windows コンピューターを設定する場合は、このオプションを選択します。エンド ・ ユーザーは、作業時間を入力して、適切な構成を使用してセットアップの開始や、アカウントの資格情報の学校します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-p104">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed. End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="c0e9d-p105">これらの展開シナリオは、組織のニーズを格納できない場合は、他のシナリオについて説明し、機能と[10 の Windows 展開シナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)では、それぞれの制限事項を理解できます。独自の<a href="https://aka.ms/planforwin10deployment" target="_blank">10 の Windows の展開を計画</a>することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-p105">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="c0e9d-135">10 の Windows の詳細については、これらの資料とします。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="c0e9d-136">Microsoft 365 Enterprise 製品ページ</span><span class="sxs-lookup"><span data-stu-id="c0e9d-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="c0e9d-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c0e9d-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="c0e9d-138">配置および 10 の Windows を更新</span><span class="sxs-lookup"><span data-stu-id="c0e9d-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="c0e9d-139">その他のサービスと機能</span><span class="sxs-lookup"><span data-stu-id="c0e9d-139">Additional services and features</span></span>
<span data-ttu-id="c0e9d-140">10 エンタープライズの Windows の展開の一部として、これらの他のサービスと機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="c0e9d-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="c0e9d-141">Windows Analytics</span></span>

<span data-ttu-id="c0e9d-142">Windows では、診断データを使用して、運用効率の向上と、環境内の Windows 10 デバイスの状態の詳細な洞察を得るうえで役立つ機能が豊富で実践的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="c0e9d-143">アップグレードの準備完了 - アップグレードの準備に役立つ Windows 10 に移動し、新しい Windows 10 の機能の更新と最新情報を入手します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="c0e9d-144">更新の対応の更新の対応は、10 の Windows デバイスをすべてせず、追加のインフラストラクチャ要件の全体像を得るために必要のある IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="c0e9d-145">デバイスの稼働状態をプロアクティブに検出し、エンド ・ ユーザーに影響を与えず問題を改善するデバイスの状態を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="c0e9d-146">詳細については、 [Windows の分析の概要](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="c0e9d-147">Windows のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c0e9d-147">Windows security</span></span>

<span data-ttu-id="c0e9d-p106">Windows 10 には、上の脅威、ヘルプから、デバイスをセキュリティで保護し、アクセス制御を支援するコンピューターを保護する機能が用意されています。Windows 10 では、最初からデバイスを保護する重要なセキュリティ機能を取得します。Microsoft 365 E3 では、ビジネス、Windows Defender のアプリケーションの制御、および情報保護の Windows の Windows こんにちはなどのセキュリティ機能を追加します。Microsoft 365 E5、365 E3 のマイクロソフトのセキュリティおよびクラウド ベースのセキュリティ機能と Windows Defender の高度な脅威保護からすべての保護を取得します。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-p106">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control. With Windows 10, you get critical security features that protect your device right from the start. Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection. With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="c0e9d-152">10 エンタープライズの Windows と取得についてはどのようにすることができます展開、管理、構成、および 3 つのキーのセキュリティ機能のトラブルシューティングを行うことで得られるセキュリティ機能に関する詳細についてを参照してください[手順 5: Windows 10 企業の展開のセキュリティ機能](windows10-enable-security-features.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="c0e9d-153">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="c0e9d-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c0e9d-154">マイクロソフトの内部を見るし、学習の会社の計画、展開、および方法 10 の Windows の更新の管理が、参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="c0e9d-155">Windows 10 をシームレスに展開するための組織の準備</span><span class="sxs-lookup"><span data-stu-id="c0e9d-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="c0e9d-156">Microsoft では、サービスとして Windows を使用</span><span class="sxs-lookup"><span data-stu-id="c0e9d-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="c0e9d-157">Microsoft における、Windows 10 のインプレース アップグレードとしての展開方法</span><span class="sxs-lookup"><span data-stu-id="c0e9d-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="c0e9d-158">Windows Hello for Business を使用した、強力なユーザー認証の実装</span><span class="sxs-lookup"><span data-stu-id="c0e9d-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="c0e9d-159">[Windows 10 の展開: Microsoft の IT 担当者からのヒント](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="c0e9d-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="c0e9d-160">Windows Defender ATP により高度な脅威の検出が可能</span><span class="sxs-lookup"><span data-stu-id="c0e9d-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="c0e9d-161">[Windows Defender および Windows Defender ATP を使用した、現代の企業のセキュリティ保護](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="c0e9d-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="c0e9d-162">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="c0e9d-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c0e9d-163">コントソ株式会社、架空であるが、代表的な多国籍のビジネス、 [10 企業の Windows を展開](contoso-win10.md)する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0e9d-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="c0e9d-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="c0e9d-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="c0e9d-165">Windows 10 Enterprise を組織で展開するための準備</span><span class="sxs-lookup"><span data-stu-id="c0e9d-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
