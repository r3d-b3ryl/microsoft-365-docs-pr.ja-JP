---
title: Microsoft 365 を使用したリモート ワーク用のインフラストラクチャを設定する
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
description: リモート ワーカーがオンプレミスおよび Microsoft 365 のリソースに安全にアクセスできるように、インフラストラクチャのレイヤーをステップ スルーします。
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246322"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a><span data-ttu-id="3d6e0-104">Microsoft 365 を使用したリモート ワーク用のインフラストラクチャを設定する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-104">Set up your infrastructure for remote work with Microsoft 365</span></span>

<span data-ttu-id="3d6e0-105">リモート ワーカーの生産性とコラボレーションを保護および最適化するには、IT とクラウドのインフラストラクチャを構成して、リモート ワークを可能にし、組織のオンプレミスおよびクラウドベースの情報、ツール、およびリソースへのアクセスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-105">To secure and optimize your remote worker’s productivity and collaboration, you need to configure your IT and cloud infrastructure to enable remote work and to provide access to your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="3d6e0-106">このソリューションは、従業員がどこにいても最高の仕事を行えるようにするインフラストラクチャの主要なレイヤーの展開を段階的に実行します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="3d6e0-107">多くの組織にとって、ワーカーがオフィスから離れて仕事ができるようにすることは、以下のために重要です。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-107">Allowing workers to work away from the office is important for many organizations to:</span></span>

- <span data-ttu-id="3d6e0-108">オフィス スペースの節約。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-108">Save on office space.</span></span>
- <span data-ttu-id="3d6e0-109">配置転換を望まないワーカーを雇用し、維持する。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-109">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="3d6e0-110">ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-110">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="3d6e0-111">Microsoft 365 には、ワーカーがリモートで作業できるようにするための機能があります。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-111">Microsoft 365 has the capabilities to empower your workers to work remotely.</span></span>

![Microsoft 365 でリモート ワーカーを支援する](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
><span data-ttu-id="3d6e0-113">Microsoft 365 を初めて使用する場合は、[こちらのリソース](https://www.microsoft.com/microsoft-365) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-113">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>
>

<span data-ttu-id="3d6e0-114">このビデオでは、展開プロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-114">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="3d6e0-115">オンサイトおよびクラウド ベースのインフラストラクチャを管理して従業員の生産性を向上させる IT プロフェッショナル向けに、このソリューションは次の主要な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-115">For IT professionals managing onsite and cloud-based infrastructure to enable worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="3d6e0-116">接続しました</span><span class="sxs-lookup"><span data-stu-id="3d6e0-116">Connected</span></span>

  <span data-ttu-id="3d6e0-117">世界中のどこからでも、いつでも、リモート ワーカーは以下にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-117">From anywhere in the world and at any time, remote workers are able to access:</span></span> 

  - <span data-ttu-id="3d6e0-118">Microsoft 365 サブスクリプションのクラウドベースのサービスとデータ。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-118">Cloud-based services and data in your Microsoft 365 subscription.</span></span> 

  - <span data-ttu-id="3d6e0-119">オンプレミスのアプリケーション データセンターで提供されるような組織のリソース。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-119">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="3d6e0-120">セキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3d6e0-120">Secure</span></span>

  <span data-ttu-id="3d6e0-121">サインインは、多要素認証 (MFA) や Microsoft 365 と Windows 10 の組み込みセキュリティ機能により、マルウェア、悪意のある攻撃、データ損失から保護されています。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-121">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="3d6e0-122">管理対象</span><span class="sxs-lookup"><span data-stu-id="3d6e0-122">Managed</span></span>

  <span data-ttu-id="3d6e0-123">リモート ワーカーのデバイスは、許可されたアプリを介して、セキュリティ設定を備えたクラウドから管理され、システム正常性への準拠を要求します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-123">Your remote worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="3d6e0-124">共同作業と生産性</span><span class="sxs-lookup"><span data-stu-id="3d6e0-124">Collaborative and productive</span></span>

  <span data-ttu-id="3d6e0-125">リモート ワーカーは、次の高度な共同作業の手法により、オンプレミスと同じように生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-125">Your remote workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="3d6e0-126">Teams を使用したオンライン会議とチャット セッション。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-126">Online meetings and chat sessions with Teams.</span></span> 

  - <span data-ttu-id="3d6e0-127">SharePoint と OneDrive を使用してグローバルなアクセシビリティとリアルタイムの共同作業を実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-127">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="3d6e0-128">作業を分割して完了するための共有タスクとワークフロー。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-128">Shared tasks and workflows to divide up the work and get things done.</span></span> 

<span data-ttu-id="3d6e0-129">シームレスなサインイン エクスペリエンスを実現するには、オンプレミスの Active Directory ドメイン サービス (AD DS) のユーザー アカウントを Azure Active Directory (Azure AD) と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-129">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3d6e0-130">Windows 10 デバイスを保護するには、そのデバイスを Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-130">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="3d6e0-131">インフラストラクチャの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-131">Here is a high-level view of the infrastructure.</span></span>

![リモート ワーカー向けの Microsoft 365 の基本インフラストラクチャ](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="3d6e0-133">リモート ワーカーに対して Microsoft 365 の機能を有効にするには、これらの Microsoft 365 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-133">To enable the capabilities of Microsoft 365 for your remote workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="3d6e0-134">機能</span><span class="sxs-lookup"><span data-stu-id="3d6e0-134">Capability or feature</span></span> | <span data-ttu-id="3d6e0-135">説明</span><span class="sxs-lookup"><span data-stu-id="3d6e0-135">Description</span></span> | <span data-ttu-id="3d6e0-136">ライセンス</span><span class="sxs-lookup"><span data-stu-id="3d6e0-136">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="3d6e0-137">セキュリティの既定値が適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="3d6e0-137">MFA enforced with security defaults</span></span>   | <span data-ttu-id="3d6e0-138">サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-138">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="3d6e0-139">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-139">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="3d6e0-140">条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="3d6e0-140">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="3d6e0-141">条件付きアクセス ポリシーを使用したサインインのプロパティに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-141">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="3d6e0-142">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-142">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="3d6e0-143">リスクベースの条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="3d6e0-143">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="3d6e0-144">ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-144">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="3d6e0-145">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="3d6e0-145">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="3d6e0-146">セルフサービスによるパスワードのリセット (SSPR)</span><span class="sxs-lookup"><span data-stu-id="3d6e0-146">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="3d6e0-147">ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-147">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="3d6e0-148">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-148">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="3d6e0-149">Azure AD アプリケーション プロキシ</span><span class="sxs-lookup"><span data-stu-id="3d6e0-149">Azure AD Application Proxy</span></span>    | <span data-ttu-id="3d6e0-150">イントラネット サーバーでホストされている Web ベースのアプリケーションに安全なリモート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-150">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="3d6e0-151">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="3d6e0-151">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="3d6e0-152">Azure ポイント対サイト VPN</span><span class="sxs-lookup"><span data-stu-id="3d6e0-152">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="3d6e0-153">Azure 仮想ネットワークを介してリモート ワーカーのデバイスからイントラネットへの安全な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-153">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="3d6e0-154">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="3d6e0-154">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="3d6e0-155">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="3d6e0-155">Windows Virtual Desktop</span></span>   | <span data-ttu-id="3d6e0-156">Azure で実行されている仮想デスクトップで、個人の管理されていないデバイスのみを使用できるリモート ワーカーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-156">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="3d6e0-157">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="3d6e0-157">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="3d6e0-158">リモート デスクトップ サービス (RDS)</span><span class="sxs-lookup"><span data-stu-id="3d6e0-158">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="3d6e0-159">従業員によるイントラネット上の Windows ベースのコンピューターへの接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-159">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="3d6e0-160">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="3d6e0-161">リモート デスクトップ サービス ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="3d6e0-161">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="3d6e0-162">通信を暗号化し、RDS ホストがインターネットに直接公開されないようにします。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-162">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="3d6e0-163">別の Windows サーバー ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="3d6e0-163">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="3d6e0-164">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3d6e0-164">Microsoft Intune</span></span> | <span data-ttu-id="3d6e0-165">デバイスとアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-165">Manage devices and applications.</span></span>   | <span data-ttu-id="3d6e0-166">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-166">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="3d6e0-167">構成マネージャーを使用するための</span><span class="sxs-lookup"><span data-stu-id="3d6e0-167">Configuration Manager</span></span> | <span data-ttu-id="3d6e0-168">デバイスでのソフトウェアのインストール、更新、設定を管理します</span><span class="sxs-lookup"><span data-stu-id="3d6e0-168">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="3d6e0-169">別の Configuration Manager ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="3d6e0-169">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="3d6e0-170">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="3d6e0-170">Desktop Analytics</span></span> | <span data-ttu-id="3d6e0-171">Windows クライアントの更新プログラムの準備状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-171">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="3d6e0-172">別の Configuration Manager ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="3d6e0-172">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="3d6e0-173">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="3d6e0-173">Windows Autopilot</span></span> | <span data-ttu-id="3d6e0-174">生産的に使用するために、新しいWindows 10デバイスをセットアップして事前構成します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-174">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="3d6e0-175">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-175">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="3d6e0-176">Microsoft Teams、Exchange Online、SharePoint Online、OneDrive、Microsoft 365 アプリ、Microsoft Power Platform、Yammer</span><span class="sxs-lookup"><span data-stu-id="3d6e0-176">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="3d6e0-177">作成、連絡、共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-177">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="3d6e0-178">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="3d6e0-178">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="3d6e0-179">セキュリティとコンプライアンスの基準については、「[リモート ワーカーのためのセキュリティとコンプライアンスの展開](empower-people-to-work-remotely-security-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-179">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a> <span data-ttu-id="3d6e0-180">このソルーションを 2 ページにまとめた [「リモート ワーカーを支援するポスター」](../downloads/empower-remote-workers.pdf) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-180">For a 2-page summary of this solution, see the [Empower remote workers poster](../downloads/empower-remote-workers.pdf).</span></span>

<span data-ttu-id="3d6e0-181">[![リモート ワーカーを支援するポスター](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span><span class="sxs-lookup"><span data-stu-id="3d6e0-181">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)</span></span>

<span data-ttu-id="3d6e0-182">このポスターを [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) または [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) 形式でダウンロードして、レター、リーガル、タブロイド (11 x 17) のサイズの紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-182">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) or  [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-remote-working-for-all-of-your-workers"></a><span data-ttu-id="3d6e0-183">すべての従業員にリモート ワークを提供する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-183">Provide remote working for all of your workers</span></span>

<span data-ttu-id="3d6e0-184">これらのデバイスを使用すると、すべての従業員がどこからでも生産性を維持できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-184">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="3d6e0-185">Surface Laptop や Windows 10 などの最新のデバイスです。Web 経由で直接 Microsoft 365 クラウド アプリやサービスにアクセスするための機能、セキュリティ、パフォーマンスを備えています。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-185">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="3d6e0-186">迅速に展開された [Windows 10 ベースの仮想デスクトップ](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices)を介して間接的に Microsoft 365 クラウド アプリとサービスにアクセスできる、自宅で使用されている以前のラップトップやデスクトップを含むすべてのデバイスです。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-186">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="3d6e0-187">このオプションは、高い性能、強力なセキュリティ、およびシンプルな IT 管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-187">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d6e0-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="3d6e0-188">Next steps</span></span>

<span data-ttu-id="3d6e0-189">次の手順を実行することにより、組織のサーバー、クラウド サービスへのアクセスをセキュリティで保護して最適化し、リモート ワーカーの生産性を最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-189">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your remote worker's productivity.</span></span>

1. [<span data-ttu-id="3d6e0-190">MFA を使用してリモート ワーカーのサインイン セキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-190">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="3d6e0-191">オンプレミスのアプリとサービスへのリモート アクセスを提供する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-191">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="3d6e0-192">セキュリティおよびコンプライアンスの展開</span><span class="sxs-lookup"><span data-stu-id="3d6e0-192">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="3d6e0-193">デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-193">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="3d6e0-194">リモート ワーカー向けの生産性向上アプリとサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-194">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="3d6e0-195">リモート ワーカーをトレーニングし、使用状況のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="3d6e0-195">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="3d6e0-196">[![Microsoft 365 を使用したリモート ワーク用のインフラストラクチャを設定する手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="3d6e0-196">[![The steps to set up your infrastructure for remote work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="3d6e0-197">架空ではあるものの、代表的な多国籍組織がリモート ワーク用のインフラストラクチャをどのように設定したかを確認するには、「[リモート ワークやオンサイト ワーク向けの Contoso の COVID-19 対応とインフラストラクチャ](contoso-remote-onsite-work.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d6e0-197">To see how a fictional but representative multi-national organization set up its infrastructure for remote work, see [Contoso's COVID-19 response and infrastructure for remote and onsite work](contoso-remote-onsite-work.md).</span></span>
