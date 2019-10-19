---
title: Microsoft 365 Enterprise の Windows 10 Enterprise インフラストラクチャ
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 7253ea698613a38988bd7a6942a4908e9c797e2a
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37372768"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="7d8ac-104">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7d8ac-104">Phase 3: Windows 10 Enterprise</span></span>

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="7d8ac-106">Microsoft 365 Enterprise には、Windows 10 Enterprise が含まれています。これにより、より多くの機能を提供し、安全な状態を維持できます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="7d8ac-107">Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="7d8ac-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="7d8ac-108">**は、シンプル化のために統合されてい**ます-クラウドのパワーを活用して、今日の最新の IT デバイス環境の管理の複雑さを軽減します。サイズに関係なく使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="7d8ac-109">**インテリジェントセキュリティがあり**ます。これは、Windows の最も安全なリリースです。これは、組織の保護を強化するために連携して機能するように設計されたインテリジェントなセキュリティ機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="7d8ac-110">**創造性とチームワークを有効**にして、創造性とチームワークのロックを解除することで、ユーザーとユーザーの両方にとって最も生産性の高い操作性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="7d8ac-111">Windows 10 オペレーティングシステムを展開するためのさまざまな方法を理解し、組織に適したものを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="7d8ac-112">Microsoft 365 Enterprise のサブスクリプションによっては、windows 10 のサービスとセキュリティ機能も備えており、Windows 10 を最大限に活用するために構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="7d8ac-113">Windows 10 Enterprise と Office 365 ProPlus の両方を展開し、[モダン デスクトップ](https://www.microsoft.com/microsoft-365/modern-desktop)に移行するには、「[モダン デスクトップ展開センター](http://aka.ms/howtoshift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="7d8ac-114">Windows 10 の展開</span><span class="sxs-lookup"><span data-stu-id="7d8ac-114">Windows 10 deployment</span></span>

<span data-ttu-id="7d8ac-115">組織に Windows 10 Enterprise を展開する方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="7d8ac-116">ここでは、これらのモダン展開シナリオを使用して Windows 10 Enterprise イメージを構成および展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="7d8ac-117">展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="7d8ac-117">Deployment scenario</span></span> | <span data-ttu-id="7d8ac-118">使用する状況</span><span class="sxs-lookup"><span data-stu-id="7d8ac-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="7d8ac-119">System Center Configuration Manager を一括アップグレードとして使用する</span><span class="sxs-lookup"><span data-stu-id="7d8ac-119">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="7d8ac-120">Windows 7 または Windows 8.1 コンピューターを Windows 10 Enterprise の<a href="https://aka.ms/windows-10-release-information" target="_blank">現在のバージョン</a>にアップグレードする必要があり、コンピューターが現在<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (current branch)</a>で管理されている場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="7d8ac-121">Windows 自動操縦の使用</span><span class="sxs-lookup"><span data-stu-id="7d8ac-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="7d8ac-122">Windows 10 Enterprise、バージョン1703以降が事前インストールされている Windows コンピューターを新たにセットアップする場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="7d8ac-123">エンドユーザーは、職場または学校のアカウントの資格情報を入力することによって、目的の構成を使用してセットアップを開始します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="7d8ac-124">これらの展開シナリオが組織のニーズに合わない場合は、他のシナリオについて学習し、 [Windows 10 の展開シナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)での各機能と制限事項について理解することができます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="7d8ac-125">自分で<a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 の展開を計画</a>することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="7d8ac-126">Windows 10 の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="7d8ac-127">Microsoft 365 Enterprise 製品ページ</span><span class="sxs-lookup"><span data-stu-id="7d8ac-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="7d8ac-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7d8ac-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="7d8ac-129">Windows 10 を展開、更新する</span><span class="sxs-lookup"><span data-stu-id="7d8ac-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="7d8ac-130">その他のサービスと機能</span><span class="sxs-lookup"><span data-stu-id="7d8ac-130">Additional services and features</span></span>
<span data-ttu-id="7d8ac-131">Windows 10 Enterprise の展開の一環として、これらの追加のサービスと機能を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="7d8ac-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="7d8ac-132">Windows Analytics</span></span>

<span data-ttu-id="7d8ac-133">Windows は診断データを使用して、環境内の Windows 10 デバイスの運用効率と正常性に関する詳細な洞察を得るために役立つ豊富で実用的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="7d8ac-134">アップグレードの準備状況-アップグレードの準備は、Windows 10 に移行し、新しい Windows 10 機能の更新プログラムを最新の状態に保つのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="7d8ac-135">コンプライアンスの更新-更新プログラムのコンプライアンスは、追加のインフラストラクチャ要件を伴わずに、すべての Windows 10 デバイスの全体的なビューを取得する IT 管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="7d8ac-136">デバイスの正常性-デバイスの正常性を使用して、問題に影響を与えるエンドユーザーを事前に検出して修復することができます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="7d8ac-137">詳細については、「 [Windows Analytics の概要](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="7d8ac-138">Windows セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7d8ac-138">Windows security</span></span>

<span data-ttu-id="7d8ac-139">Windows 10 では、脅威からの保護、デバイスのセキュリティ保護、およびアクセス制御のサポートに役立つ機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="7d8ac-140">Windows 10 では、デバイスを最初から保護する重要なセキュリティ機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="7d8ac-141">Microsoft 365 E3 は、Windows Hello for Business、Windows Defender アプリケーションコントロール、および Windows 情報保護などのセキュリティ機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="7d8ac-142">Microsoft 365 E5 を使用すると、Microsoft 365 E3 セキュリティとクラウドベースのセキュリティ機能および Microsoft Defender Advanced Threat Protection からすべての保護を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="7d8ac-143">Windows 10 Enterprise で利用できるセキュリティ機能の詳細については、「[手順 5: windows 10 enterprise のセキュリティ機能](windows10-enable-security-features.md)を展開、管理、構成、およびトラブルシューティングする」のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="7d8ac-144">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="7d8ac-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7d8ac-145">Microsoft の内部を見ることで、会社が[Windows 10 Enterprise を展開し、強力な認証、Intune、Microsoft DEFENDER ATP を使用して](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6)いる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="7d8ac-146">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="7d8ac-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7d8ac-147">架空の多国籍企業である Contoso Corporation が[Windows 10 Enterprise を展開](contoso-win10.md)した方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d8ac-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso 社](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="7d8ac-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="7d8ac-149">Next step</span></span>

|||
|:-------|:-----|
|![手順 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="7d8ac-151">Windows 10 Enterprise を組織で展開するための準備</span><span class="sxs-lookup"><span data-stu-id="7d8ac-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
