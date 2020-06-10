---
title: Microsoft 365 でリモート ワーカーを支援する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: ワーカーがいつでもどこからでもリモートで作業できるようにするセキュリティとサービスのインフラストラクチャを構成します。
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560464"
---
# <a name="empower-remote-workers-with-microsoft-365"></a><span data-ttu-id="b9070-103">Microsoft 365 でリモート ワーカーを支援する</span><span class="sxs-lookup"><span data-stu-id="b9070-103">Empower remote workers with Microsoft 365</span></span>

<span data-ttu-id="b9070-104">組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに、ワーカーが自宅から安全にアクセスできるようにすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9070-104">Your business may need to enable your workers to have secure access to your organization's on-premises and cloud-based information, tools, and resources from their homes.</span></span> <span data-ttu-id="b9070-105">多くの組織にとって、ワーカーがシームレスかつ安全にオフィスから離れて仕事ができるようにすることは、以下のために重要です。</span><span class="sxs-lookup"><span data-stu-id="b9070-105">Allowing workers to work away from the office seamlessly and securely is important for many organizations to:</span></span>

- <span data-ttu-id="b9070-106">オフィス スペースの節約。</span><span class="sxs-lookup"><span data-stu-id="b9070-106">Save on office space.</span></span>
- <span data-ttu-id="b9070-107">配置転換を望まないワーカーを雇用し、維持する。</span><span class="sxs-lookup"><span data-stu-id="b9070-107">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="b9070-108">ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。</span><span class="sxs-lookup"><span data-stu-id="b9070-108">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="b9070-109">リモート作業 (テレワーキングとも呼ばれる) は、次のような範囲に及ぶ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b9070-109">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="b9070-110">会議やクライアント会議のために時々オフィスを離れるワーカー。</span><span class="sxs-lookup"><span data-stu-id="b9070-110">workers that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="b9070-111">リモートでフルタイムで働く一部のワーカー。</span><span class="sxs-lookup"><span data-stu-id="b9070-111">Some workers that work remotely full-time.</span></span>
- <span data-ttu-id="b9070-112">オフィスがなく、すべてのワーカーがリモートで作業をする完全なリモートの組織。</span><span class="sxs-lookup"><span data-stu-id="b9070-112">A fully remote organization in which there is no office and all workers are remote.</span></span>

<span data-ttu-id="b9070-113">世界中のどこからでも、いつでも、リモート ワーカーは以下にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9070-113">From anywhere in the world and at any time, remote workers must be able to access:</span></span>

- <span data-ttu-id="b9070-114">オンプレミスのアプリケーション データセンターで提供されるような組織のリソース。</span><span class="sxs-lookup"><span data-stu-id="b9070-114">Organization resources, such those offered by on-premises application datacenters.</span></span>
- <span data-ttu-id="b9070-115">Microsoft 365 サブスクリプションのクラウドベースのサービスとデータ (Teams、Exchange Online、SharePoint、OneDrive など)。</span><span class="sxs-lookup"><span data-stu-id="b9070-115">Cloud-based services and data in your Microsoft 365 subscription, such as Teams, Exchange Online, SharePoint, and OneDrive.</span></span>

<span data-ttu-id="b9070-116">シームレスなサインイン エクスペリエンスを実現するには、Active Directory ドメイン サービス (AD DS) のユーザー アカウントを Azure Active Directory (Azure AD) と同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9070-116">For a seamless sign-in experience, your Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b9070-117">Windows 10 デバイスを保護するには、そのデバイスを Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9070-117">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="b9070-118">インフラストラクチャの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b9070-118">Here is a high-level view of the infrastructure.</span></span>

![リモート ワーカー向けの Microsoft 365 の基本インフラストラクチャ](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


<span data-ttu-id="b9070-120">たとえば COVID-19 危機への対応として、リモート ワーカーをサポートするために、Microsoft 365 Enterprise の機能を組み合わせることで、次のような高度な共同作業が可能になります。</span><span class="sxs-lookup"><span data-stu-id="b9070-120">To support remote workers, for example in response to the COVID-19 crisis, a combination of features in Microsoft 365 enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="b9070-121">オンライン会議およびチャット セッション。</span><span class="sxs-lookup"><span data-stu-id="b9070-121">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="b9070-122">グローバルなアクセシビリティとリアルタイムのコラボレーションを実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="b9070-122">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="b9070-123">作業を分割して完了するための共有タスクとワークフロー。</span><span class="sxs-lookup"><span data-stu-id="b9070-123">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="b9070-124">セキュリティを強化するために、Microsoft 365 には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9070-124">For strong security, Microsoft 365 includes:</span></span>

- <span data-ttu-id="b9070-125">認証要件の適用、高リスクのサインインの検出と応答、選択したアプリと非準拠デバイスのブロック。</span><span class="sxs-lookup"><span data-stu-id="b9070-125">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="b9070-126">クラウド内の暗号化された接続とデジタル資産。</span><span class="sxs-lookup"><span data-stu-id="b9070-126">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="b9070-127">ファイルに対して誰が何を実行できるかを定義する権限。</span><span class="sxs-lookup"><span data-stu-id="b9070-127">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="b9070-128">Windows 10 デバイスを保護する包括的なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="b9070-128">Comprehensive security features to protect Windows 10 devices.</span></span>

<span data-ttu-id="b9070-129">これらのリモート ワーカーの基準を満たすには、次の Microsoft 365 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9070-129">To meet these criteria for remote workers, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="b9070-130">機能</span><span class="sxs-lookup"><span data-stu-id="b9070-130">Capability or feature</span></span> | <span data-ttu-id="b9070-131">説明</span><span class="sxs-lookup"><span data-stu-id="b9070-131">Description</span></span> | <span data-ttu-id="b9070-132">ライセンス</span><span class="sxs-lookup"><span data-stu-id="b9070-132">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="b9070-133">セキュリティの既定値が適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="b9070-133">MFA enforced with security defaults</span></span>   | <span data-ttu-id="b9070-134">サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9070-134">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="b9070-135">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-135">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="b9070-136">条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="b9070-136">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="b9070-137">条件付きアクセス ポリシーを使用したサインインのプロパティに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="b9070-137">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="b9070-138">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-138">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="b9070-139">リスクベースの条件付きアクセスが適用されている MFA</span><span class="sxs-lookup"><span data-stu-id="b9070-139">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="b9070-140">Azure Advanced Threat Protection によるユーザー サインインのリスクに基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="b9070-140">Require MFA based on the risk of the user sign-in with Azure Advanced Threat Protection.</span></span> | <span data-ttu-id="b9070-141">Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3</span><span class="sxs-lookup"><span data-stu-id="b9070-141">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="b9070-142">セルフサービスによるパスワードのリセット (SSPR)</span><span class="sxs-lookup"><span data-stu-id="b9070-142">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="b9070-143">ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。</span><span class="sxs-lookup"><span data-stu-id="b9070-143">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="b9070-144">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-144">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="b9070-145">Azure AD アプリケーション プロキシ</span><span class="sxs-lookup"><span data-stu-id="b9070-145">Azure AD Application Proxy</span></span>    | <span data-ttu-id="b9070-146">イントラネット サーバーでホストされている Web ベースのアプリケーションに安全なリモート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b9070-146">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="b9070-147">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="b9070-147">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="b9070-148">Azure ポイント対サイト VPN</span><span class="sxs-lookup"><span data-stu-id="b9070-148">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="b9070-149">Azure 仮想ネットワークを介してリモート ワーカーのデバイスからイントラネットへの安全な接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="b9070-149">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="b9070-150">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="b9070-150">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="b9070-151">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="b9070-151">Windows Virtual Desktop</span></span>   | <span data-ttu-id="b9070-152">Azure で実行されている仮想デスクトップで、個人の管理されていないデバイスのみを使用できるリモート ワーカーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b9070-152">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="b9070-153">別の有料 Azure サブスクリプションが必要</span><span class="sxs-lookup"><span data-stu-id="b9070-153">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="b9070-154">リモート デスクトップ サービス (RDS)</span><span class="sxs-lookup"><span data-stu-id="b9070-154">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="b9070-155">従業員によるイントラネット上の Windows ベースのコンピューターへの接続を許可します。</span><span class="sxs-lookup"><span data-stu-id="b9070-155">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="b9070-156">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-156">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="b9070-157">リモート デスクトップ サービス ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="b9070-157">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="b9070-158">通信を暗号化し、RDS ホストがインターネットに直接公開されないようにします。</span><span class="sxs-lookup"><span data-stu-id="b9070-158">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="b9070-159">別の Windows サーバー ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="b9070-159">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="b9070-160">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b9070-160">Microsoft Intune</span></span> | <span data-ttu-id="b9070-161">デバイスとアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="b9070-161">Manage devices and applications.</span></span>   | <span data-ttu-id="b9070-162">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-162">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="b9070-163">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b9070-163">Configuration Manager</span></span> | <span data-ttu-id="b9070-164">デバイスでのソフトウェアのインストール、更新、設定を管理します</span><span class="sxs-lookup"><span data-stu-id="b9070-164">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="b9070-165">別の Configuration Manager ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="b9070-165">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="b9070-166">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="b9070-166">Desktop Analytics</span></span> | <span data-ttu-id="b9070-167">Windows クライアントの更新プログラムの準備状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9070-167">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="b9070-168">別の Configuration Manager ライセンスが必要</span><span class="sxs-lookup"><span data-stu-id="b9070-168">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="b9070-169">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="b9070-169">Windows Autopilot</span></span> | <span data-ttu-id="b9070-170">生産的に使用するために、新しいWindows 10デバイスをセットアップして事前構成します。</span><span class="sxs-lookup"><span data-stu-id="b9070-170">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="b9070-171">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-171">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="b9070-172">Microsoft Teams、Exchange Online、SharePoint Online、OneDrive、Microsoft 365 アプリ、Microsoft Power Platform、Yammer、Power Apps</span><span class="sxs-lookup"><span data-stu-id="b9070-172">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps</span></span> | <span data-ttu-id="b9070-173">作成、連絡、共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="b9070-173">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="b9070-174">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="b9070-174">Microsoft 365 E3 and E5</span></span> |
||||

<span data-ttu-id="b9070-175">次の手順を実行することにより、組織のサーバー、データ、クラウド サービスへのアクセスをセキュリティで保護して最適化し、従業員の生産性を最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b9070-175">Use these steps to secure and optimize access to your organization's servers, data, and cloud services and enable maximum worker productivity.</span></span>

1. [<span data-ttu-id="b9070-176">MFA を使用してリモート ワーカーのサインイン セキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="b9070-176">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="b9070-177">オンプレミスのアプリとサービスへのリモート アクセスを提供する</span><span class="sxs-lookup"><span data-stu-id="b9070-177">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="b9070-178">デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する</span><span class="sxs-lookup"><span data-stu-id="b9070-178">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
4. [<span data-ttu-id="b9070-179">リモート ワーカー向けの生産性向上アプリとサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="b9070-179">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [<span data-ttu-id="b9070-180">コミュニケーション会場を作成する</span><span class="sxs-lookup"><span data-stu-id="b9070-180">Create communication venues</span></span>](empower-people-to-work-remotely-communication-venues.md)
6. [<span data-ttu-id="b9070-181">リモート ワーカーをトレーニングし、使用状況のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="b9070-181">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

![Microsoft 365 でリモート ワーカーを支援するための手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

<span data-ttu-id="b9070-183">リモート ワーカーのサポートに関する Microsoft の最新情報については、「[Enabling remote work Tech Community site (リモート ワークを可能にする技術コミュニティ サイト)](https://resources.techcommunity.microsoft.com/enabling-remote-work/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9070-183">For the latest information from Microsoft about supporting remote workers, see the [Enabling remote work Tech Community site](https://resources.techcommunity.microsoft.com/enabling-remote-work/).</span></span>
