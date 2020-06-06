---
title: Microsoft 365 でリモート ワーカーを支援する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 05/27/2020
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
ms.openlocfilehash: ce287cdf5bcbd0283252b08c035dc954044a9c0e
ms.sourcegitcommit: 416a4b87bfd7e5aff80194b59b2776f054aa8eb5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44534962"
---
# <a name="empower-remote-workers-with-microsoft-365"></a><span data-ttu-id="a4d66-103">Microsoft 365 でリモート ワーカーを支援する</span><span class="sxs-lookup"><span data-stu-id="a4d66-103">Empower remote workers with Microsoft 365</span></span>

<span data-ttu-id="a4d66-104">組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに、ワーカーが自宅から安全にアクセスできるようにすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4d66-104">Your business may need to enable your workers to have secure access to your organization's on-premises and cloud-based information, tools, and resources from their homes.</span></span> <span data-ttu-id="a4d66-105">多くの組織にとって、ワーカーがシームレスかつ安全にオフィスから離れて仕事ができるようにすることは、以下のために重要です。</span><span class="sxs-lookup"><span data-stu-id="a4d66-105">Allowing workers to work away from the office seamlessly and securely is important for many organizations to:</span></span>

- <span data-ttu-id="a4d66-106">オフィス スペースの節約。</span><span class="sxs-lookup"><span data-stu-id="a4d66-106">Save on office space.</span></span>
- <span data-ttu-id="a4d66-107">配置転換を望まないワーカーを雇用し、維持する。</span><span class="sxs-lookup"><span data-stu-id="a4d66-107">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="a4d66-108">ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。</span><span class="sxs-lookup"><span data-stu-id="a4d66-108">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="a4d66-109">リモート作業 (テレワーキングとも呼ばれる) は、次のような範囲に及ぶ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a4d66-109">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="a4d66-110">会議やクライアント会議のために時々オフィスを離れるワーカー。</span><span class="sxs-lookup"><span data-stu-id="a4d66-110">workers that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="a4d66-111">リモートでフルタイムで働く一部のワーカー。</span><span class="sxs-lookup"><span data-stu-id="a4d66-111">Some workers that work remotely full-time.</span></span>
- <span data-ttu-id="a4d66-112">オフィスがなく、すべてのワーカーがリモートで作業をする完全なリモートの組織。</span><span class="sxs-lookup"><span data-stu-id="a4d66-112">A fully remote organization in which there is no office and all workers are remote.</span></span>

<span data-ttu-id="a4d66-113">たとえば COVID-19 危機への対応として、リモート ワーカーをサポートするために、Microsoft 365 Enterprise の機能を組み合わせることで、次のような高度な共同作業が可能になります。</span><span class="sxs-lookup"><span data-stu-id="a4d66-113">To support remote workers, for example in response to the COVID-19 crisis, a combination of features in Microsoft 365 enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="a4d66-114">オンライン会議およびチャット セッション。</span><span class="sxs-lookup"><span data-stu-id="a4d66-114">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="a4d66-115">グローバルなアクセシビリティとリアルタイムのコラボレーションを実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="a4d66-115">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="a4d66-116">作業を分割して完了するための共有タスクとワークフロー。</span><span class="sxs-lookup"><span data-stu-id="a4d66-116">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="a4d66-117">セキュリティを強化するために、Microsoft 365 には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4d66-117">For strong security, Microsoft 365 includes:</span></span>

- <span data-ttu-id="a4d66-118">認証要件の適用、高リスクのサインインの検出と応答、選択したアプリと非準拠デバイスのブロック。</span><span class="sxs-lookup"><span data-stu-id="a4d66-118">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="a4d66-119">クラウド内の暗号化された接続とデジタル資産。</span><span class="sxs-lookup"><span data-stu-id="a4d66-119">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="a4d66-120">ファイルに対して誰が何を実行できるかを定義する権限。</span><span class="sxs-lookup"><span data-stu-id="a4d66-120">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="a4d66-121">Windows 10 デバイスを保護する包括的なセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="a4d66-121">Comprehensive security features to protect Windows 10 devices.</span></span>

<span data-ttu-id="a4d66-122">これらのリモート ワーカーの基準を満たすには、次の Microsoft 365 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4d66-122">To meet these criteria for remote workers, use the following Microsoft 365 features:</span></span>

- <span data-ttu-id="a4d66-123">ユーザー ID とサインイン セキュリティ</span><span class="sxs-lookup"><span data-stu-id="a4d66-123">User identity and sign-in security</span></span>
  - <span data-ttu-id="a4d66-124">多要素認証 (MFA) を使用する Azure Active Directory (Azure AD) ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="a4d66-124">Azure Active Directory (Azure AD) user accounts with multi-factor authentication (MFA)</span></span>
  - <span data-ttu-id="a4d66-125">危険なサインインに MFA を要求する条件付きアクセス ポリシー (Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="a4d66-125">A Conditional Access policy to require MFA for risky sign-ins (Microsoft 365 E5)</span></span>
- <span data-ttu-id="a4d66-126">コラボレーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="a4d66-126">Collaboration platforms</span></span>
  - <span data-ttu-id="a4d66-127">リモート ワーカーがオンライン ビデオベースの会議にスケジュールおよび参加し、同時に同じドキュメントで作業できるようにする Microsoft Teams、SharePoint、および OneDrive</span><span class="sxs-lookup"><span data-stu-id="a4d66-127">Microsoft Teams, SharePoint, and OneDrive, with which remote workers can schedule and attend online video-based meetings and work on the same documents at the same time</span></span>
- <span data-ttu-id="a4d66-128">リソースへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="a4d66-128">Secure access to resources</span></span>
  - <span data-ttu-id="a4d66-129">Teams、SharePoint サイト、および OneDrive のグループとアクセス許可により、認証および許可されたユーザーのみがアクセス可能</span><span class="sxs-lookup"><span data-stu-id="a4d66-129">Groups and permissions for Teams, SharePoint sites, and OneDrive so that only authenticated and permitted users have access</span></span>
- <span data-ttu-id="a4d66-130">漏洩ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="a4d66-130">Protection for leaked files</span></span>
  - <span data-ttu-id="a4d66-131">暗号化のための機密ラベルとファイルとともに移動するアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a4d66-131">Sensitivity labels for encryption and permissions that travel with files</span></span>
- <span data-ttu-id="a4d66-132">Microsoft Intune によるデバイス管理とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a4d66-132">Device management and security with Microsoft Intune</span></span>
  - <span data-ttu-id="a4d66-133">管理対象デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="a4d66-133">Enrollment for managed devices</span></span>
  - <span data-ttu-id="a4d66-134">個人用デバイスのアプリ設定</span><span class="sxs-lookup"><span data-stu-id="a4d66-134">App settings for personal devices</span></span>
  - <span data-ttu-id="a4d66-135">デバイスとアプリのポリシー</span><span class="sxs-lookup"><span data-stu-id="a4d66-135">Device and app policies</span></span>
- <span data-ttu-id="a4d66-136">デバイス用の生産性アプリ</span><span class="sxs-lookup"><span data-stu-id="a4d66-136">Productivity apps for devices</span></span>
  - <span data-ttu-id="a4d66-137">Teams、Exchange、SharePoint、OneDrive とのコラボレーション エクスペリエンスのための Microsoft 365 Apps (Word、PowerPoint、Excel) </span><span class="sxs-lookup"><span data-stu-id="a4d66-137">Microsoft 365 Apps (Word, PowerPoint, Excel) for collaborative experiences with Teams, Exchange, SharePoint, and OneDrive</span></span> 
- <span data-ttu-id="a4d66-138">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a4d66-138">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="a4d66-139">サイバー攻撃から保護し、データ漏洩を防止する包括的なセキュリティ機能の組み込みスイート</span><span class="sxs-lookup"><span data-stu-id="a4d66-139">Built-in suite of security features to protect against cyberattacks and prevent data leakage</span></span>
- <span data-ttu-id="a4d66-140">オンプレミス アプリやサービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="a4d66-140">Access to on-premises apps and servers</span></span>
  - <span data-ttu-id="a4d66-141">仮想プライベート ネットワーク (VPN) 接続、Azure AD アプリケーション プロキシ、Azure ポイント対サイト VPN</span><span class="sxs-lookup"><span data-stu-id="a4d66-141">Virtual private network (VPN) connections, Azure AD Application Proxy, or Azure Point-to-Site VPN</span></span>

<span data-ttu-id="a4d66-142">次の手順を実行することにより、組織のサーバー、データ、クラウド サービスへのアクセスをセキュリティで保護して最適化し、従業員の生産性を最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a4d66-142">Use these steps to secure and optimize access to your organization's servers, data, and cloud services and enable maximum worker productivity.</span></span>

1. [<span data-ttu-id="a4d66-143">MFA を使用してリモート ワーカーのサインイン セキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="a4d66-143">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="a4d66-144">オンプレミスのアプリとサービスへのリモート アクセスを提供する</span><span class="sxs-lookup"><span data-stu-id="a4d66-144">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="a4d66-145">デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する</span><span class="sxs-lookup"><span data-stu-id="a4d66-145">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
4. [<span data-ttu-id="a4d66-146">リモート ワーカー向けの生産性向上アプリとサービスを展開する</span><span class="sxs-lookup"><span data-stu-id="a4d66-146">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [<span data-ttu-id="a4d66-147">コミュニケーション会場を作成する</span><span class="sxs-lookup"><span data-stu-id="a4d66-147">Create communication venues</span></span>](empower-people-to-work-remotely-communication-venues.md)
6. [<span data-ttu-id="a4d66-148">リモート ワーカーをトレーニングし、使用状況のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="a4d66-148">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

![Microsoft 365 でリモート ワーカーを支援するための手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

<span data-ttu-id="a4d66-150">リモート ワーカーのサポートに関する Microsoft の最新情報については、「[Enabling remote work Tech Community site (リモート ワークを可能にする技術コミュニティ サイト)](https://resources.techcommunity.microsoft.com/enabling-remote-work/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4d66-150">For the latest information from Microsoft about supporting remote workers, see the [Enabling remote work Tech Community site](https://resources.techcommunity.microsoft.com/enabling-remote-work/).</span></span>
