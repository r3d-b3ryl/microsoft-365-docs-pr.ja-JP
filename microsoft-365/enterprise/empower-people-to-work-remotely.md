---
title: リモート ワーカーを支援する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: 従業員がいつでもどこからでもリモートで作業できるようにするインフラストラクチャとセキュリティを構成します。
ms.openlocfilehash: 3c4d34e21993f3b0c9327b27dd0a5a14f430b1b8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637506"
---
# <a name="empower-remote-workers"></a><span data-ttu-id="16ec6-103">リモート ワーカーを支援する</span><span class="sxs-lookup"><span data-stu-id="16ec6-103">Empower remote workers</span></span>

<span data-ttu-id="16ec6-104">*このシナリオは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*</span><span class="sxs-lookup"><span data-stu-id="16ec6-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="16ec6-105">従業員がオフィスからシームレスかつ安全に離れて作業できるようにすることは、多くの組織にとって、オフィス スペースの節約、転勤を望まない従業員の採用および維持、通勤時間の短縮など、従業員の生産性の向上と仕事以外でストレスを軽減するために重要です。</span><span class="sxs-lookup"><span data-stu-id="16ec6-105">Allowing employees to work away from the office seamlessly and securely is important for many organizations to save on office space, hire and retain employees who are unwilling to relocate, and reduce employee commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="16ec6-106">リモート作業 (テレワーキングとも呼ばれる) は、次のような範囲に及ぶことがあります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-106">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="16ec6-107">会議やクライアント会議のために時々オフィスを離れる従業員。</span><span class="sxs-lookup"><span data-stu-id="16ec6-107">Employees that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="16ec6-108">リモートでフルタイムで働く一部の従業員。</span><span class="sxs-lookup"><span data-stu-id="16ec6-108">Some employees that work remotely full-time.</span></span>
- <span data-ttu-id="16ec6-109">オフィスがなく、すべての従業員が離れている完全なリモートの組織。</span><span class="sxs-lookup"><span data-stu-id="16ec6-109">A fully remote organization in which there is no office and all employees are remote.</span></span>

<span data-ttu-id="16ec6-110">リモート ワーカーをサポートするために、Microsoft 365 Enterprise の機能を組み合わせることで、次のような高度な共同作業が可能になります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-110">To support remote workers, a combination of features in Microsoft 365 Enterprise enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="16ec6-111">オンライン会議およびチャット セッション。</span><span class="sxs-lookup"><span data-stu-id="16ec6-111">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="16ec6-112">グローバルなアクセシビリティとリアルタイムのコラボレーションを実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="16ec6-112">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="16ec6-113">作業を分割して完了するための共有タスクとワークフロー。</span><span class="sxs-lookup"><span data-stu-id="16ec6-113">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="16ec6-114">セキュリティを強化するために、Microsoft 365 Enterprise には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-114">For strong security, Microsoft 365 Enterprise includes:</span></span>

- <span data-ttu-id="16ec6-115">認証要件の適用、高リスクのサインインの検出と応答、選択したアプリと非準拠デバイスのブロック。</span><span class="sxs-lookup"><span data-stu-id="16ec6-115">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="16ec6-116">クラウド内の暗号化された接続とデジタル資産。</span><span class="sxs-lookup"><span data-stu-id="16ec6-116">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="16ec6-117">ファイルに対して誰が何を実行できるかを定義する権限。</span><span class="sxs-lookup"><span data-stu-id="16ec6-117">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="16ec6-118">高度に規制されたデータの漏洩を防ぐデータ損失防止 (DLP)。</span><span class="sxs-lookup"><span data-stu-id="16ec6-118">Data loss prevention (DLP) to prevent leakage of highly regulated data.</span></span>

<span data-ttu-id="16ec6-119">これらのリモート ワーカーの基準を満たすには、次の Microsoft 365 Enterprise 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-119">To meet these criteria for remote workers, use the following Microsoft 365 Enterprise features:</span></span>

- <span data-ttu-id="16ec6-120">ユーザー ID とサインイン セキュリティ</span><span class="sxs-lookup"><span data-stu-id="16ec6-120">User identity and sign-in security</span></span>
  - <span data-ttu-id="16ec6-121">多要素認証 (MFA) を使用する Azure Active Directory (Azure AD) ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="16ec6-121">Azure Active Directory (Azure AD) user accounts with multi-factor authentication (MFA)</span></span>
  - <span data-ttu-id="16ec6-122">危険なサインインに MFA を要求する条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="16ec6-122">Conditional Access policies to require MFA for risky sign-ins</span></span>
- <span data-ttu-id="16ec6-123">コラボレーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="16ec6-123">Collaboration platforms</span></span>
  - <span data-ttu-id="16ec6-124">リモート ワーカーがオンライン ビデオベースの会議にスケジュールおよび参加し、同時に同じドキュメントで作業できるようにする Microsoft Teams、SharePoint、および OneDrive</span><span class="sxs-lookup"><span data-stu-id="16ec6-124">Microsoft Teams, SharePoint, and OneDrive, with which remote workers can schedule and attend online video-based meetings and work on the same documents at the same time</span></span>
- <span data-ttu-id="16ec6-125">リソースへのアクセスを保護する</span><span class="sxs-lookup"><span data-stu-id="16ec6-125">Secure access to resources</span></span>
  - <span data-ttu-id="16ec6-126">Teams、SharePoint サイト、および OneDrive のグループとアクセス許可により、認証および許可されたユーザーのみがアクセス可能</span><span class="sxs-lookup"><span data-stu-id="16ec6-126">Groups and permissions for Teams, SharePoint sites, and OneDrive so that only authenticated and permitted users have access</span></span>
- <span data-ttu-id="16ec6-127">漏洩ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="16ec6-127">Protection for leaked files</span></span>
  - <span data-ttu-id="16ec6-128">DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="16ec6-128">DLP policies</span></span>
  - <span data-ttu-id="16ec6-129">暗号化のための機密ラベルとファイルとともに移動するアクセス許可</span><span class="sxs-lookup"><span data-stu-id="16ec6-129">Sensitivity labels for encryption and permissions that travel with files</span></span>
- <span data-ttu-id="16ec6-130">Microsoft Intune によるデバイス管理とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="16ec6-130">Device management and security with Microsoft Intune</span></span>
  - <span data-ttu-id="16ec6-131">管理対象デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="16ec6-131">Enrollment for managed devices</span></span>
  - <span data-ttu-id="16ec6-132">個人用デバイスのアプリ設定</span><span class="sxs-lookup"><span data-stu-id="16ec6-132">App settings for personal devices</span></span>
  - <span data-ttu-id="16ec6-133">デバイスとアプリのポリシー</span><span class="sxs-lookup"><span data-stu-id="16ec6-133">Device and app policies</span></span>
- <span data-ttu-id="16ec6-134">デバイス用の生産性アプリ</span><span class="sxs-lookup"><span data-stu-id="16ec6-134">Productivity apps for devices</span></span>
  - <span data-ttu-id="16ec6-135">Teams、SharePoint、および OneDrive とのコラボレーション エクスペリエンスのための Microsoft 365 Apps for enterprise アプリ</span><span class="sxs-lookup"><span data-stu-id="16ec6-135">Microsoft 365 Apps for enterprise apps for collaborative experiences with Teams, SharePoint, and OneDrive</span></span> 
- <span data-ttu-id="16ec6-136">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="16ec6-136">Windows 10 Enterprise</span></span>
  - <span data-ttu-id="16ec6-137">サイバー攻撃から保護し、データ漏洩を防止する包括的なセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="16ec6-137">Comprehensive security features to protect against cyberattacks and prevent data leakage</span></span>
- <span data-ttu-id="16ec6-138">オンプレミス アプリへのアクセス</span><span class="sxs-lookup"><span data-stu-id="16ec6-138">Access to on-premises apps</span></span>
  - <span data-ttu-id="16ec6-139">ハイブリッド ID を持つ組織は、仮想プライベート ネットワーク (VPN) 接続の代わりに Azure AD アプリケーション プロキシを使用可能</span><span class="sxs-lookup"><span data-stu-id="16ec6-139">Organizations that have hybrid identity can use Azure AD Application Proxy instead of virtual private network (VPN) connections</span></span>

<span data-ttu-id="16ec6-140">次のフェーズでは、リモート アクセスを可能にする Microsoft 365 Enterprise の機能を展開し、リモート ワーカーの採用を推進する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-140">The following phases step you through deploying the feature of Microsoft 365 Enterprise for remote access and driving adoption for remote workers.</span></span> <span data-ttu-id="16ec6-141">これらのフェーズの要素がすでに展開されている場合は、次の要素に進む前に、それらの要素が上記の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="16ec6-141">If you have already deployed elements of these phases, ensure that they meet the stated requirements before moving on to the next element.</span></span>

<a name="poster"></a> <span data-ttu-id="16ec6-142">このシナリオを 1 ページにまとめた「[リモート ワーカーを支援するポスター](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ec6-142">For a 1-page summary of this scenario, see the [Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf).</span></span>

<span data-ttu-id="16ec6-143">[![リモート ワーカーを支援するポスター](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span><span class="sxs-lookup"><span data-stu-id="16ec6-143">[![Empower remote workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)</span></span>

<span data-ttu-id="16ec6-144">このポスターを [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) または [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) 形式でダウンロードして、レター、リーガル、タブロイド (11 x 17) のサイズの紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-144">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a><span data-ttu-id="16ec6-145">フェーズ 1: リモート ワーカーに Microsoft 365 の機能を展開する</span><span class="sxs-lookup"><span data-stu-id="16ec6-145">Phase 1: Deploy Microsoft 365 features and capabilities for remote workers</span></span>

<span data-ttu-id="16ec6-146">このシナリオに必要な機能の幅と数が多いため、「[Microsoft 365 Enterprise の展開ガイド](deploy-microsoft-365-enterprise.md)」の基盤インフラストラクチャとワークロード セクションの必須要素を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-146">Because of the breadth and number of features and capabilities required for this scenario, we’ll step you through the required elements of the foundation infrastructure and workloads sections of the [Microsoft 365 Enterprise Deployment Guide](deploy-microsoft-365-enterprise.md).</span></span>

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a><span data-ttu-id="16ec6-147">手順 1: リモート ワーカーの基盤インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="16ec6-147">Step 1: Foundation infrastructure requirements for remote workers</span></span>

<span data-ttu-id="16ec6-148">この手順では、[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)のフェーズにアクセスし、リモート ワーカーを有効にするために必要な要素を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-148">In this step, we’ll visit the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) and list the required elements to enable remote workers.</span></span>

<span data-ttu-id="16ec6-149">[フェーズ 2: ID](identity-infrastructure.md) の場合、ユーザー ID およびサインイン セキュリティ用に次を展開します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-149">For [Phase 2: Identity](identity-infrastructure.md), deploy the following for user identity and sign-in security:</span></span>

- <span data-ttu-id="16ec6-150">ハイブリッド ID の場合、オンプレミスの Active Directory ドメイン サービス (AD DS) から同期されたユーザー アカウントとグループ。</span><span class="sxs-lookup"><span data-stu-id="16ec6-150">For hybrid identity, user accounts and groups synchronized from on-premises Active Directory Domain Services (AD DS).</span></span>
- <span data-ttu-id="16ec6-151">権限を割り当てる場合、適切なメンバーと同期または Azure AD グループ。</span><span class="sxs-lookup"><span data-stu-id="16ec6-151">For assigning permissions, synchronized or Azure AD groups with the appropriate members.</span></span>
- <span data-ttu-id="16ec6-152">MFA の要求などの認証設定。</span><span class="sxs-lookup"><span data-stu-id="16ec6-152">Authentication settings, such as requiring MFA.</span></span>
- <span data-ttu-id="16ec6-153">危険なサインインに MFA を要求する条件付きアクセス ポリシーおよび先進認証をサポートしないクライアントのブロック。</span><span class="sxs-lookup"><span data-stu-id="16ec6-153">Conditional Access policies to require MFA for risky sign-ins and block clients that don’t support modern authentication.</span></span>

<span data-ttu-id="16ec6-154">次に、ID 要素を強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-154">Here's the resulting configuration with the identity elements highlighted.</span></span>

![リモート ワーカーの ID 要素](../media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
<span data-ttu-id="16ec6-156">[フェーズ 3: Windows 10 Enterprise](windows10-infrastructure.md):</span><span class="sxs-lookup"><span data-stu-id="16ec6-156">For [Phase 3: Windows 10 Enterprise](windows10-infrastructure.md):</span></span>

- <span data-ttu-id="16ec6-157">インフラストラクチャを展開して、Windows 10 Enterprise で新しいデバイスを展開し、Windows 7 または Windows 8.1 デバイスを Windows 10 Enterprise にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="16ec6-157">Deploy the infrastructure to deploy new devices with Windows 10 Enterprise and to upgrade your Windows 7 or Windows 8.1 devices to Windows 10 Enterprise</span></span>
- <span data-ttu-id="16ec6-158">ID、脅威、および情報保護のための包括的なセキュリティ機能を有効化する</span><span class="sxs-lookup"><span data-stu-id="16ec6-158">Enable comprehensive security features for identity, threat, and information protection</span></span>

<span data-ttu-id="16ec6-159">次に、Windows 10 Enterprise デバイスの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-159">Here's the resulting configuration with Windows 10 Enterprise devices.</span></span>

![リモート ワーカー向けの Windows 10 Enterprise の要素](../media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
<span data-ttu-id="16ec6-161">[フェーズ 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md):インフラストラクチャを展開してMicrosoft 365 Apps for enterprise をインストールするか、 Office 2010、Office 2013 など、現在インストールされている Office スイートを組織のデバイスのMicrosoft 365 Apps for enterprise にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="16ec6-161">For [Phase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md), deploy the infrastructure to install Microsoft 365 Apps for enterprise or upgrade your currently installed Office suite, such as Office 2010 or Office 2013, to Microsoft 365 Apps for enterprise on your organization devices.</span></span> <span data-ttu-id="16ec6-162">これにより、ユーザーがセキュリティと共同作業エクスペリエンスを最大限活用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-162">This will give your users the best security and collaborative experiences.</span></span>

<span data-ttu-id="16ec6-163">次に、Microsoft 365 Apps for enterprise がデバイスにインストールされた場合の構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-163">Here's the resulting configuration with Microsoft 365 Apps for enterprise installed on devices.</span></span>

![リモート ワーカー向けの Microsoft 365 Apps for enterprise の要素](../media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
<span data-ttu-id="16ec6-165">[フェーズ 5: モバイル デバイス管理](mobility-infrastructure.md)の場合、次の目的で Intune デバイスとアプリの管理を展開します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-165">For [Phase 5: Mobile device management](mobility-infrastructure.md), deploy Intune device and app management for:</span></span>

- <span data-ttu-id="16ec6-166">組織が定義した機能とセキュリティ設定を受信するように、Windows 10 Enterprise、iOS、macOS、Android、および Android Enterprise デバイスを登録。</span><span class="sxs-lookup"><span data-stu-id="16ec6-166">Enrollment of your Windows 10 Enterprise, iOS, macOS, Android, and Android Enterprise devices so they receive features and security settings defined by your organization.</span></span>
- <span data-ttu-id="16ec6-167">従業員が所有する個人用デバイスであっても、セキュリティを強化するため、アプリを許可またはブロックするアプリの設定。</span><span class="sxs-lookup"><span data-stu-id="16ec6-167">App settings for extra security and to allow or block apps, even on employee-owned personal devices.</span></span>
- <span data-ttu-id="16ec6-168">非準拠デバイスの接続を防ぐための条件付きアクセスを備えたコンプライアンス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="16ec6-168">Compliance policies with Conditional Access to prevent non-compliant devices from connecting.</span></span>

<span data-ttu-id="16ec6-169">次に、Intune の登録済みデバイスとポリシーを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-169">Here's the resulting configuration with Intune enrolled devices and policies highlighted.</span></span>

![リモート ワーカー向けのモバイル デバイス管理の要素](../media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
<span data-ttu-id="16ec6-171">[フェーズ 6: 情報保護](infoprotect-infrastructure.md)の場合、デジタル資産の保護を次の機能により設計および構成します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-171">For [Phase 6: Information protection](infoprotect-infrastructure.md), design and configure protection for your digital assets with:</span></span>

- <span data-ttu-id="16ec6-172">DLP ポリシー。</span><span class="sxs-lookup"><span data-stu-id="16ec6-172">DLP policies.</span></span>
- <span data-ttu-id="16ec6-173">暗号化のためのMicrosoft 365 機密ラベルとファイルとともに移動するアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="16ec6-173">Microsoft 365 sensitivity labels for encryption and permissions that travel with files.</span></span>

<span data-ttu-id="16ec6-174">次に、DLP ポリシーと機密度ラベルを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-174">Here's the resulting configuration with DLP policies and sensitivity labels highlighted.</span></span>

![リモート ワーカー向けの情報保護の要素](../media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
<span data-ttu-id="16ec6-176">オンプレミス アプリにアクセスするには、ハイブリッド ID 環境を必要とする [Azure AD アプリケーション プロキシ](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-176">For access to on-premises apps, you can use [Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy), which requires a hybrid identity environment.</span></span>

<span data-ttu-id="16ec6-177">次に、アプリケーション プロキシ コンポーネントを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-177">Here's the resulting configuration with the application proxy components highlighted.</span></span>

![リモート ワーカーのアプリケーション プロキシの要素](../media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a><span data-ttu-id="16ec6-179">手順 2: リモート ワーカーのワークロード</span><span class="sxs-lookup"><span data-stu-id="16ec6-179">Step 2: Workloads for remote workers</span></span>

<span data-ttu-id="16ec6-180">[Exchange Online](exchangeonline-workload.md) の場合、Exchange Online メールボックスを各ユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-180">For [Exchange Online](exchangeonline-workload.md), deploy Exchange Online mailboxes to each of your users.</span></span>

<span data-ttu-id="16ec6-181">[Teams](teams-workload.md) の場合、Teams をユーザーとグループに展開します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-181">For [Teams](teams-workload.md), deploy Teams to your users and groups.</span></span>

<span data-ttu-id="16ec6-182">[SharePoint および OneDrive](sharepoint-online-onedrive-workload.md) の場合、SharePoint チームまたはコミュニケーション サイトと OneDrive フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-182">For [SharePoint and OneDrive](sharepoint-online-onedrive-workload.md), deploy SharePoint team or communication sites and OneDrive folders.</span></span>

<span data-ttu-id="16ec6-183">次に、ワークロードを強調表示した構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-183">Here's the resulting configuration with the workloads highlighted.</span></span>

![リモート ワーカー向けの Microsoft 365 ワークロード](../media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a><span data-ttu-id="16ec6-185">展開結果</span><span class="sxs-lookup"><span data-stu-id="16ec6-185">Deployment results</span></span>

<span data-ttu-id="16ec6-186">基盤インフラストラクチャとワークロードを展開し、Windows 10 Enterprise および Microsoft 365 Apps for enterprise を展開した後、リモート ワーカーは次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="16ec6-186">After deploying the foundation infrastructure and workloads and rolling out Windows 10 Enterprise and Microsoft 365 Apps for enterprise, remote workers:</span></span>

- <span data-ttu-id="16ec6-187">強力な認証および ID 保護の対象になります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-187">Are subject to strong authentication and identity protection.</span></span>
- <span data-ttu-id="16ec6-188">Windows デバイスで最新かつ最も安全なバージョンの Windows を使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-188">Have the latest and most secure version of Windows on their Windows devices.</span></span>
- <span data-ttu-id="16ec6-189">デバイスで最新かつ最も生産的なバージョンの Office スイートを使用するようになります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-189">Have the latest and most productive version of the Office suite on their devices.</span></span>
- <span data-ttu-id="16ec6-190">アプリ管理およびデバイス コンプライアンス ポリシーの対象になります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-190">Are subject to app management and device compliance policies.</span></span>
- <span data-ttu-id="16ec6-191">DLP ポリシーおよび制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-191">Are subject to DLP policies and restrictions.</span></span>
- <span data-ttu-id="16ec6-192">ファイルおよびメールとともに送信される暗号化およびアクセス許可に機密度ラベルを割り当てられるようになります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-192">Can assign sensitivity labels for encryption and permissions that travel with files and email.</span></span>
- <span data-ttu-id="16ec6-193">VPN 接続なしでオンプレミスのアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-193">Can access on-premises apps without a VPN connection.</span></span>
- <span data-ttu-id="16ec6-194">Teams 内のチャット、会議、ファイル、SharePoint および OneDrive 内のファイルを使用して、自分の作業を実行し、同僚とのリアルタイム コラボレーションに参加できます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-194">Can perform their own work and participate in real-time collaboration with co-workers with chats, meetings, and files in Teams and files in SharePoint and OneDrive.</span></span>

<span data-ttu-id="16ec6-195">オフライン (インターネットに接続されていない) の場合、リモート ワーカーはファイルのローカル コピーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-195">When offline (not connected to the Internet), your remote workers can change local copies of files.</span></span> <span data-ttu-id="16ec6-196">インターネットに再接続すると、OneDrive はローカル コピーを Microsoft 365 サブスクリプションに保存されているファイルと同期します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-196">When they reconnect to the Internet, OneDrive synchronizes local copies with the files stored in your Microsoft 365 subscription.</span></span> 

<span data-ttu-id="16ec6-197">次に、ハイブリッド ID を使用する場合の、組織のリモート ワーカーの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-197">Here's the resulting configuration for remote workers of your organization if you use hybrid identity.</span></span>

![ハイブリッド ID を持つ組織の最終の構成](../media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
<span data-ttu-id="16ec6-199">次に、クラウド専用 ID を使用する場合の、組織のリモート ワーカーの構成を示します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-199">Here's the resulting configuration for remote workers your organization if you use cloud-only identity.</span></span>

![クラウド専用 ID を持つ組織の最終の構成](../media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a><span data-ttu-id="16ec6-201">フェーズ 2: リモート ワーカーに導入を促す</span><span class="sxs-lookup"><span data-stu-id="16ec6-201">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="16ec6-202">基盤インフラストラクチャとワークロードが整ったので、これらの機能の継続的な使用をリモート ワーカーに促し、いつでもどこでも生産的になるようにします。</span><span class="sxs-lookup"><span data-stu-id="16ec6-202">Now that the foundation infrastructure and workloads are in place, it’s time to drive the ongoing usage of these capabilities to your remote workers so they can be productive anywhere and at any time.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="16ec6-203">手順 1: ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="16ec6-203">Step 1: Train your users</span></span>

<span data-ttu-id="16ec6-204">リモート ワーカーを以下の内容についてトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="16ec6-204">Train your remote workers on:</span></span>

- <span data-ttu-id="16ec6-205">MFA 登録を含む適切なサインインの手順、およびリスクが検出されたときにサインインにチャレンジする方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-205">Proper sign-in procedures, including MFA registration, and how sign ins can be challenged when risk is detected.</span></span>
- <span data-ttu-id="16ec6-206">デバイスの使用と、ポリシーを使用して非準拠デバイスのアクセスをブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-206">The use of devices and how policies can be used to block access for non-compliant devices.</span></span>
- <span data-ttu-id="16ec6-207">許可されたアプリの使用と、Intune アプリ ポリシーを使用してアプリをブロックする方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-207">The use of allowed apps and how Intune app polices can be used to block apps.</span></span>
- <span data-ttu-id="16ec6-208">Windows 10 Enterprise のセキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="16ec6-208">Windows 10 Enterprise security features.</span></span>
- <span data-ttu-id="16ec6-209">電子メールと予定表に Outlook を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-209">How to use Outlook for email and calendaring.</span></span>
- <span data-ttu-id="16ec6-210">[Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) を使用してチャット、ビデオベースの会議、ドキュメント共有、およびスレッド形式の会話を行う方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-210">How to use [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) for chat, video-based conferencing, document sharing, and threaded conversations.</span></span>
- <span data-ttu-id="16ec6-211">SharePoint チームまたはコミュニケーション サイトと OneDrive フォルダーを使用して、ユーザーのライブラリおよびグループに属するファイルを閲覧する方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-211">How to use SharePoint team or communication sites and OneDrive folders to browse files in a user's library and those belonging to a group.</span></span>
- <span data-ttu-id="16ec6-212">ファイルのローカル バージョンとオンライン バージョンの両方で、機密データまたは厳しく規制されたデータを含むファイルに機密度ラベルを使用および適用する方法。</span><span class="sxs-lookup"><span data-stu-id="16ec6-212">How to use and apply sensitivity labels for files containing sensitive or highly regulated data, for both local and online versions of files.</span></span>

<span data-ttu-id="16ec6-213">このトレーニングには、生徒が上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="16ec6-213">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a><span data-ttu-id="16ec6-214">手順 2: 使用状況を定期的にレビューし、作業者のフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="16ec6-214">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="16ec6-215">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="16ec6-215">In the weeks after training:</span></span>

- <span data-ttu-id="16ec6-216">リモート ワーカーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-216">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="16ec6-217">チーム、SharePoint サイト、および OneDrive フォルダーの使用状況を分析し、予想される使用状況と比較します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-217">Analyze usage for teams, SharePoint sites, and OneDrive folders and compare it with usage expectations.</span></span>
- <span data-ttu-id="16ec6-218">機密または厳しく規制されたファイルが適切な機密度ラベルで適切にラベル付けされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16ec6-218">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="16ec6-219">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="16ec6-219">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="16ec6-220">ユーザーによる採用の結果</span><span class="sxs-lookup"><span data-stu-id="16ec6-220">User adoption results</span></span>

<span data-ttu-id="16ec6-221">リモート ワーカーは、Windows 10 Enterprise または他のデバイスと Microsoft 365 Apps for enterprise を使用して、安全な環境で共有 Microsoft 365 Enterprise クラウド サービスとリソースにアクセスして作業し、リアルタイムで会議、作成、コラボレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-221">Your remote workers can use their Windows 10 Enterprise or other devices and Microsoft 365 Apps for enterprise to access and work on shared Microsoft 365 Enterprise cloud services and resources in a secure environment, and they’re meeting, creating, and collaborating in real time.</span></span>

## <a name="additional-microsoft-features-to-support-remote-workers"></a><span data-ttu-id="16ec6-222">リモート ワーカーをサポートするために Microsoft が提供しているその他の機能</span><span class="sxs-lookup"><span data-stu-id="16ec6-222">Additional Microsoft features to support remote workers</span></span>

<span data-ttu-id="16ec6-223">[Azure ポイント対サイト VPN 接続](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about)を使用すると、Azure 仮想ネットワーク内で稼働しているサーバーにリモート ワーカーを接続できます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-223">You can use [Azure Point-to-Site VPN connections](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about) to connect remote workers to servers running in an Azure virtual network.</span></span>

<span data-ttu-id="16ec6-224">[Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) を使用すると、Azure でホストされているデスクトップおよびアプリを仮想化できます。</span><span class="sxs-lookup"><span data-stu-id="16ec6-224">You can use [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) for desktop and app virtualization hosted by Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="16ec6-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="16ec6-225">See also</span></span>

[<span data-ttu-id="16ec6-226">ワークロードとシナリオ</span><span class="sxs-lookup"><span data-stu-id="16ec6-226">Workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="16ec6-227">[Microsoft 365 生産性向上ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="16ec6-227">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="16ec6-228">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="16ec6-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
