---
title: Microsoft 365 を使用したハイブリッドワーク用のインフラストラクチャを設定する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: 在宅勤務、在宅勤務、ハイブリッド、リモート ワーカー、ハイブリッド ワーク、リモート従業員、ハイブリッド接続、リモート アクセス、在宅勤務、テレワーク、テレワーク、モバイル ワーク、リモート ジョブ、どこからでも作業、柔軟な職場
description: ハイブリッド ワーカーがオンプレミスおよび Microsoft 365 のリソースに安全にアクセスできるように、インフラストラクチャのレイヤーをステップ スルーします。
ms.openlocfilehash: 55f1cf5c922166e1fe3932b6fe89fbdfcbfba466
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788887"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a><span data-ttu-id="b1539-104">Microsoft 365 を使用したハイブリッドワーク用のインフラストラクチャを設定する</span><span class="sxs-lookup"><span data-stu-id="b1539-104">Set up your infrastructure for hybrid work with Microsoft 365</span></span>

<span data-ttu-id="b1539-105">従業員の生産性とコラボレーションをセキュリティで保護して最適化するには、オンプレミスとリモートのワーカーが組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに簡単かつ安全にアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1539-105">To secure and optimize your worker’s productivity and collaboration, you need to allow on-site and remote workers to easily and securely access your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="b1539-106">このソリューションは、従業員がどこにいても最高の仕事を行えるようにするインフラストラクチャの主要なレイヤーの展開を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="b1539-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="b1539-107">ハイブリッドワーカーは、場所を組み合わせてオンサイトまたはリモートで作業できます。</span><span class="sxs-lookup"><span data-stu-id="b1539-107">Hybrid workers can work on-site or remotely in a combination of locations.</span></span> <span data-ttu-id="b1539-108">多くの組織にとって、ワーカーが伝統的なオフィスから離れて仕事ができるようにすることは、以下のために重要です。</span><span class="sxs-lookup"><span data-stu-id="b1539-108">Allowing workers to work away from a traditional office is important for many organizations to:</span></span>

- <span data-ttu-id="b1539-109">再配置を望まない、または柔軟な作業環境を必要とする従業員を雇用および維持する。</span><span class="sxs-lookup"><span data-stu-id="b1539-109">Hire and retain workers who are unwilling to relocate or require a flexible work environment.</span></span>
- <span data-ttu-id="b1539-110">ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。</span><span class="sxs-lookup"><span data-stu-id="b1539-110">Reduce worker commuting, leaving workers with more time to be productive and for stress-reducing activities outside of work.</span></span>
- <span data-ttu-id="b1539-111">オフィス スペースの節約。</span><span class="sxs-lookup"><span data-stu-id="b1539-111">Save on office space.</span></span>

<span data-ttu-id="b1539-112">Microsoft 365 には、ハイブリッド ワーカーがオンサイトまたはリモートで作業できるようにする機能があります。</span><span class="sxs-lookup"><span data-stu-id="b1539-112">Microsoft 365 has the capabilities to empower your hybrid workers to work either on-site or remotely.</span></span>

![Microsoft 365 を使用してハイブリッド ワーカーを強化する](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
><span data-ttu-id="b1539-114">Microsoft 365 を初めて使用する場合は、[こちらのリソース](https://www.microsoft.com/microsoft-365) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1539-114">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>
>

<span data-ttu-id="b1539-115">このビデオでは、展開プロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1539-115">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="b1539-116">オンサイトおよびクラウド ベースのインフラストラクチャを管理してハイブリッド ワーカーの生産性を向上させる IT プロフェッショナル向けに、このソリューションは次の主要な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1539-116">For IT professionals managing onsite and cloud-based infrastructure to enable hybrid worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="b1539-117">接続しました</span><span class="sxs-lookup"><span data-stu-id="b1539-117">Connected</span></span>

  <span data-ttu-id="b1539-118">世界中のどこからでも、いつでも、ワーカーたちは以下にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b1539-118">From anywhere in the world and at any time, your workers are able to access:</span></span> 

  - <span data-ttu-id="b1539-119">Microsoft 365 サブスクリプションのクラウドベースのサービスとデータ。</span><span class="sxs-lookup"><span data-stu-id="b1539-119">Cloud-based services and data in your Microsoft 365 subscription.</span></span> 

  - <span data-ttu-id="b1539-120">オンプレミスのアプリケーション データセンターで提供されるような組織のリソース。</span><span class="sxs-lookup"><span data-stu-id="b1539-120">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="b1539-121">セキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="b1539-121">Secure</span></span>

  <span data-ttu-id="b1539-122">サインインは、多要素認証 (MFA) や Microsoft 365 と Windows 10 の組み込みセキュリティ機能により、マルウェア、悪意のある攻撃、データ損失から保護されています。</span><span class="sxs-lookup"><span data-stu-id="b1539-122">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="b1539-123">管理対象</span><span class="sxs-lookup"><span data-stu-id="b1539-123">Managed</span></span>

  <span data-ttu-id="b1539-124">ハイブリッド ワーカーのデバイスは、、システム正常性への準拠を要求するために、セキュリティ設定を備えた許可されたアプリを介して、クラウドから管理されます。</span><span class="sxs-lookup"><span data-stu-id="b1539-124">Your hybrid worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="b1539-125">共同作業と生産性</span><span class="sxs-lookup"><span data-stu-id="b1539-125">Collaborative and productive</span></span>

  <span data-ttu-id="b1539-126">ハイブリッド ワーカーは、次の高度な共同作業の手法により、オンプレミスと同じように生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b1539-126">Your hybrid workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="b1539-127">Teams を使用したオンライン会議とチャット セッション。</span><span class="sxs-lookup"><span data-stu-id="b1539-127">Online meetings and chat sessions with Teams.</span></span> 

  - <span data-ttu-id="b1539-128">SharePoint と OneDrive を使用してグローバルなアクセシビリティとリアルタイムの共同作業を実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="b1539-128">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="b1539-129">作業を分割して完了するための共有タスクとワークフロー。</span><span class="sxs-lookup"><span data-stu-id="b1539-129">Shared tasks and workflows to divide up the work and get things done.</span></span> 

<span data-ttu-id="b1539-130">シームレスなサインイン エクスペリエンスを実現するには、オンプレミスの Active Directory ドメイン サービス (AD DS) のユーザー アカウントを Azure Active Directory (Azure AD) と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1539-130">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b1539-131">Windows 10 デバイスを保護するには、そのデバイスを Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1539-131">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="b1539-132">インフラストラクチャの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b1539-132">Here is a high-level view of the infrastructure.</span></span>

![ハイブリッド ワーカー向けの Microsoft 365 の基本インフラストラクチャ](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="b1539-134">ハイブリッド ワーカーに対して Microsoft 365 の機能を有効にするには、これらの Microsoft 365 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1539-134">To enable the capabilities of Microsoft 365 for your hybrid workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="b1539-135">機能</span><span class="sxs-lookup"><span data-stu-id="b1539-135">Capability or feature</span></span> | <span data-ttu-id="b1539-136">説明</span><span class="sxs-lookup"><span data-stu-id="b1539-136">Description</span></span> | <span data-ttu-id="b1539-137">ライセンス</span><span class="sxs-lookup"><span data-stu-id="b1539-137">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="b1539-138">セキュリティの既定値が適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="b1539-138">MFA enforced with security defaults</span></span>   | <span data-ttu-id="b1539-139">サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1539-139">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="b1539-140">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-140">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="b1539-141">条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="b1539-141">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="b1539-142">条件付きアクセス ポリシーを使用したサインインのプロパティに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="b1539-142">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="b1539-143">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-143">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="b1539-144">リスクベースの条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="b1539-144">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="b1539-145">ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="b1539-145">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="b1539-146">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="b1539-146">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="b1539-147">セルフサービスによるパスワードのリセット (SSPR)</span><span class="sxs-lookup"><span data-stu-id="b1539-147">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="b1539-148">ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。</span><span class="sxs-lookup"><span data-stu-id="b1539-148">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="b1539-149">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-149">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="b1539-150">Azure AD アプリケーション プロキシ</span><span class="sxs-lookup"><span data-stu-id="b1539-150">Azure AD Application Proxy</span></span>    | <span data-ttu-id="b1539-151">イントラネット サーバーでホストされている Web ベースのアプリケーションに安全なリモート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1539-151">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="b1539-152">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="b1539-152">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="b1539-153">Azure ポイント対サイト VPN</span><span class="sxs-lookup"><span data-stu-id="b1539-153">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="b1539-154">Azure 仮想ネットワークを介してリモート ワーカーのデバイスからイントラネットへの安全な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1539-154">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="b1539-155">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="b1539-155">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="b1539-156">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="b1539-156">Windows Virtual Desktop</span></span>   | <span data-ttu-id="b1539-157">Azure で実行されている仮想デスクトップで、個人の管理されていないデバイスのみを使用できるリモート ワーカーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1539-157">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="b1539-158">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="b1539-158">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="b1539-159">リモート デスクトップ サービス (RDS)</span><span class="sxs-lookup"><span data-stu-id="b1539-159">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="b1539-160">従業員によるイントラネット上の Windows ベースのコンピューターへの接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="b1539-160">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="b1539-161">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-161">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="b1539-162">リモート デスクトップ サービス ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="b1539-162">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="b1539-163">通信を暗号化し、RDS ホストがインターネットに直接公開されないようにします。</span><span class="sxs-lookup"><span data-stu-id="b1539-163">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="b1539-164">別の Windows サーバー ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="b1539-164">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="b1539-165">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b1539-165">Microsoft Intune</span></span> | <span data-ttu-id="b1539-166">デバイスとアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="b1539-166">Manage devices and applications.</span></span>   | <span data-ttu-id="b1539-167">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="b1539-168">構成マネージャーを使用するための</span><span class="sxs-lookup"><span data-stu-id="b1539-168">Configuration Manager</span></span> | <span data-ttu-id="b1539-169">デバイスでのソフトウェアのインストール、更新、設定を管理します</span><span class="sxs-lookup"><span data-stu-id="b1539-169">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="b1539-170">別の Configuration Manager ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="b1539-170">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="b1539-171">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="b1539-171">Desktop Analytics</span></span> | <span data-ttu-id="b1539-172">Windows クライアントの更新プログラムの準備状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="b1539-172">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="b1539-173">別の Configuration Manager ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="b1539-173">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="b1539-174">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="b1539-174">Windows Autopilot</span></span> | <span data-ttu-id="b1539-175">生産的に使用するために、新しいWindows 10デバイスをセットアップして事前構成します。</span><span class="sxs-lookup"><span data-stu-id="b1539-175">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="b1539-176">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-176">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="b1539-177">Microsoft Teams、Exchange Online、SharePoint Online、OneDrive、Microsoft 365 アプリ、Microsoft Power Platform、Yammer</span><span class="sxs-lookup"><span data-stu-id="b1539-177">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="b1539-178">作成、連絡、共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="b1539-178">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="b1539-179">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="b1539-179">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="b1539-180">セキュリティとコンプライアンスの基準については、「[リモート ワーカーのためのセキュリティとコンプライアンスの展開](empower-people-to-work-remotely-security-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1539-180">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a> <span data-ttu-id="b1539-181">このソルーションを 2 ページにまとめた [「ハイブリッド ワーカーを支援するポスター」](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1539-181">For a 2-page summary of this solution, see the [Empower hybrid workers poster](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf).</span></span>

<span data-ttu-id="b1539-182">[![ハイブリッド ワーカーのポスターを強化する](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)</span><span class="sxs-lookup"><span data-stu-id="b1539-182">[![Empower hybrid workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)</span></span>

<span data-ttu-id="b1539-183">このポスターを [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) 形式でダウンロードし、レター、リーガル、タブロイド (11 x 17) のサイズの用紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1539-183">You can also download this poster in [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-hybrid-working-for-all-of-your-workers"></a><span data-ttu-id="b1539-184">すべてのワーカーにハイブリッド ワークを提供する</span><span class="sxs-lookup"><span data-stu-id="b1539-184">Provide hybrid working for all of your workers</span></span>

<span data-ttu-id="b1539-185">これらのデバイスを使用すると、すべての従業員がどこからでも生産性を維持できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1539-185">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="b1539-186">Surface Laptop や Windows 10 などの最新のデバイスです。Web 経由で直接 Microsoft 365 クラウド アプリやサービスにアクセスするための機能、セキュリティ、パフォーマンスを備えています。</span><span class="sxs-lookup"><span data-stu-id="b1539-186">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="b1539-187">迅速に展開された [Windows 10 ベースの仮想デスクトップ](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices)を介して間接的に Microsoft 365 クラウド アプリとサービスにアクセスできる、自宅で使用されている以前のラップトップやデスクトップを含むすべてのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="b1539-187">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="b1539-188">このオプションは、高い性能、強力なセキュリティ、およびシンプルな IT 管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1539-188">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1539-189">次の手順</span><span class="sxs-lookup"><span data-stu-id="b1539-189">Next steps</span></span>

<span data-ttu-id="b1539-190">次の手順を実行することにより、組織のサーバー、クラウド サービスへのアクセスをセキュリティで保護して最適化し、リモート ワーカーの生産性を最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b1539-190">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your hybrid worker's productivity.</span></span>

1. [<span data-ttu-id="b1539-191">MFA を使用してリモート ワーカーのサインイン セキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="b1539-191">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="b1539-192">オンプレミスのアプリとサービスへのリモート アクセスを提供する</span><span class="sxs-lookup"><span data-stu-id="b1539-192">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="b1539-193">セキュリティおよびコンプライアンスの展開</span><span class="sxs-lookup"><span data-stu-id="b1539-193">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="b1539-194">デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する</span><span class="sxs-lookup"><span data-stu-id="b1539-194">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="b1539-195">ハイブリッド ワーカー生産性向上アプリとサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="b1539-195">Deploy hybrid worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="b1539-196">ワーカーをトレーニングし、使用状況のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="b1539-196">Train your workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="b1539-197">[![Microsoft 365 を使用したハイブリッド ワーク用のインフラストラクチャを設定する手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="b1539-197">[![The steps to set up your infrastructure for hybrid work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="b1539-198">架空ではあるものの、代表的な多国籍組織がハイブリッド ワーク用のインフラストラクチャをどのように設定したかを確認するハイブリッド ワーク向けの 「[Contoso の COVID-19 対応](contoso-remote-onsite-work.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1539-198">To see how a fictional but representative multi-national organization set up its infrastructure for hybrid work, see [Contoso's COVID-19 response and infrastructure for hybrid work](contoso-remote-onsite-work.md).</span></span>
