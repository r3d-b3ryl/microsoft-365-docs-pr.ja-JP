---
title: Microsoft 365 Enterprise の基礎インフラストラクチャチャ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の基礎インフラストラクチャを組織に展開するための主要フェーズ (別名、コア展開) について理解します。
ms.openlocfilehash: e6b8a71f59f20633e323c71e931b930198bc4deb
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400051"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="53145-103">Microsoft 365 Enterprise の基礎インフラストラクチャチャ</span><span class="sxs-lookup"><span data-stu-id="53145-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="53145-104">Microsoft 365 Enterprise のエンド ツー エンドの展開を自分で行っている場合は、まずアプリケーションとサービスによる創造性とチームワークが安全な環境で発揮される強固な基盤を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53145-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="53145-105">この機能は、コア展開と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="53145-105">This foundation is sometimes referred to as the core deployment.</span></span>

<span data-ttu-id="53145-106">展開に関して定義されたエンド ツー エンドのパスの次のフェーズを使用して Microsoft 365 Enterprise の基礎インフラストラクチャを計画して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="53145-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="53145-107">フェーズ</span><span class="sxs-lookup"><span data-stu-id="53145-107">Phase</span></span> | <span data-ttu-id="53145-108">結果</span><span class="sxs-lookup"><span data-stu-id="53145-108">Results</span></span> |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="53145-109">フェーズ 1: ネットワーク</span><span class="sxs-lookup"><span data-stu-id="53145-109">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="53145-110">ネットワークは、Microsoft 365 のクラウドベースのサービスへのアクセスに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="53145-110">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="53145-111">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="53145-111">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="53145-112">管理者アカウントの保護と、ユーザーおよびグループの同期が行われ、強固なセキュリティによるユーザー認証が実現します。</span><span class="sxs-lookup"><span data-stu-id="53145-112">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="53145-113">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="53145-113">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="53145-114">既存の Windows ベースのコンピューターは Windows 10 Enterprise にアップグレードすることができ、新しいデバイスは Windows 10 Enterprise と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="53145-114">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="53145-115">フェーズ 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="53145-115">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="53145-116">Microsoft Office の既存のユーザーは Office 365 ProPlus にアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="53145-116">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="53145-117">フェーズ 5: モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="53145-117">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="53145-118">デバイスを登録し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="53145-118">Your devices can be enrolled and managed.</span></span> |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="53145-119">フェーズ 6: 情報保護</span><span class="sxs-lookup"><span data-stu-id="53145-119">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="53145-120">ラベルを使用してドキュメントを保護する準備が整い、Office 365 のセキュリティ機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="53145-120">Your labels are ready to protect documents and Office 365 security features are enabled.</span></span> |

<span data-ttu-id="53145-121">フェーズは最も基本的なもの (ネットワークと ID) から始めます。その後に、インフラストラクチャの設定とグループのレイヤーを作成し以下を実施します。</span><span class="sxs-lookup"><span data-stu-id="53145-121">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="53145-122">最新かつセキュリティで保護されたバージョンの Windows をデバイスにインストールします。</span><span class="sxs-lookup"><span data-stu-id="53145-122">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="53145-123">デバイスに最新バージョンの Office をインストールします。</span><span class="sxs-lookup"><span data-stu-id="53145-123">Install the most current version of Office on your devices.</span></span>
- <span data-ttu-id="53145-124">組織のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="53145-124">Manage your organization's devices.</span></span>
- <span data-ttu-id="53145-125">デバイス上およびクラウド内の情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="53145-125">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="53145-126">また、IT リソースやビジネス ニーズに合わせて、フェーズそのものやフェーズ内の手順の構成を変えて臨機応変に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="53145-126">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="53145-127">**小規模または新しい組織の場合**、次のフェーズにそって必要に応じてインフラストラクチャを体系的に構築します。</span><span class="sxs-lookup"><span data-stu-id="53145-127">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span>

-  <span data-ttu-id="53145-128">**企業組織の場合**、フェーズを定義されたパスではなく IT インフラストラクチャのレイヤーとして表示し、組織全体の各レイヤーに必要な条件に対して最終的に一番最適な方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="53145-128">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="53145-129">各フェーズの最後に終了条件がありますので、この条件を確認するようにしてください。満たさなければならない必須条件、検討する必要があるオプションの条件を確認できます。</span><span class="sxs-lookup"><span data-stu-id="53145-129">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="53145-130">各フェーズの終了条件は、オンプレミスとクラウドのインフラストラクチャ、およびそのフェーズから得られるエンド ツー エンドの構成が、Microsoft 365 Enterprise 展開の要件を満たしているかどうかの判断基準となります。</span><span class="sxs-lookup"><span data-stu-id="53145-130">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="53145-131">以下の短時間のビデオでコンテンツの構造を確認できます。</span><span class="sxs-lookup"><span data-stu-id="53145-131">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="53145-132">以下が Microsoft 365 Enterprise の全体的な展開ガイドの基礎インフラストラクチャとなります。</span><span class="sxs-lookup"><span data-stu-id="53145-132">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="53145-133">インフラストラクチャの構成とユーザー ロールアウト</span><span class="sxs-lookup"><span data-stu-id="53145-133">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="53145-134">構成されたソフトウェアとサービス一式が、基礎インフラストラクチャになります。これらのソフトウェアやサービスをユーザー向けに組み合わせることで、安全な環境で Microsoft 365 Enterprise が提供するすべての機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="53145-134">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="53145-135">エンド ツー エンドの展開の最終目的は、お客様の全ユーザーとそのユーザーの Windows ベースのデバイスに基礎インフラストラクチャを適用することです。</span><span class="sxs-lookup"><span data-stu-id="53145-135">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="53145-136">ただし、Microsoft 365 Enterprise の基礎インフラストラクチャと、ユーザーへのソフトウェアおよびサービスのロールアウトは別のものになります。</span><span class="sxs-lookup"><span data-stu-id="53145-136">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="53145-137">***基礎インフラストラクチャのレイヤーは、すべてのユーザーにロールアウトしなくても構成することができます。***</span><span class="sxs-lookup"><span data-stu-id="53145-137">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="53145-138">したがって、組織のオフィス、地域、あるいは部署の多数のユーザーにロールアウトする前に、基礎インフラストラクチャの要素を構成、テスト、試験運用することができます。</span><span class="sxs-lookup"><span data-stu-id="53145-138">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="53145-139">たとえば、以下を目的とした設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="53145-139">For example, you create the settings for:</span></span>

| <span data-ttu-id="53145-140">フェーズ</span><span class="sxs-lookup"><span data-stu-id="53145-140">Phase</span></span> | <span data-ttu-id="53145-141">結果</span><span class="sxs-lookup"><span data-stu-id="53145-141">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="53145-142">ID</span><span class="sxs-lookup"><span data-stu-id="53145-142">Identity</span></span> | <span data-ttu-id="53145-143">アカウント同期と ID ベースの条件付きアクセス ポリシーのグループ。</span><span class="sxs-lookup"><span data-stu-id="53145-143">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="53145-144">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="53145-144">Windows 10 Enterprise</span></span> | <span data-ttu-id="53145-145">Windows 7 または Windows 8.1 を実行しているコンピューターを Windows 10 Enterprise に自動的にアップグレードするためのグループ。</span><span class="sxs-lookup"><span data-stu-id="53145-145">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="53145-146">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="53145-146">Office 365 ProPlus</span></span> | <span data-ttu-id="53145-147">Office 2010、Office 2013、または Office 2016 を使用しているユーザーに Office 365 ProPlus を自動的に展開するためのグループ。</span><span class="sxs-lookup"><span data-stu-id="53145-147">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="53145-148">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="53145-148">Mobile device management</span></span> | <span data-ttu-id="53145-149">デバイス登録とデバイス ベースの条件付きアクセス ポリシーのグループ。</span><span class="sxs-lookup"><span data-stu-id="53145-149">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="53145-150">情報保護</span><span class="sxs-lookup"><span data-stu-id="53145-150">Information protection</span></span> | <span data-ttu-id="53145-151">Office 365 と Azure Information Protection のラベルとグループ。</span><span class="sxs-lookup"><span data-stu-id="53145-151">Office 365 and Azure Information Protection labels and groups.</span></span> |

<span data-ttu-id="53145-152">基礎インフラストラクチャの要素をユーザーにロールアウトする準備ができたら、以下を実施します。</span><span class="sxs-lookup"><span data-stu-id="53145-152">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="53145-153">フェーズ</span><span class="sxs-lookup"><span data-stu-id="53145-153">Phase</span></span> | <span data-ttu-id="53145-154">ロールアウト アクション</span><span class="sxs-lookup"><span data-stu-id="53145-154">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="53145-155">ID</span><span class="sxs-lookup"><span data-stu-id="53145-155">Identity</span></span> | <span data-ttu-id="53145-156">ID ベースの条件付きアクセス ポリシーのグループにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="53145-156">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="53145-157">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="53145-157">Windows 10 Enterprise</span></span> | <span data-ttu-id="53145-158">グループにアカウントを追加して、Windows 7 または Windows 8.1 を使用しているユーザーに Windows 10 Enterprise を自動的に展開します。</span><span class="sxs-lookup"><span data-stu-id="53145-158">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="53145-159">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="53145-159">Office 365 ProPlus</span></span> | <span data-ttu-id="53145-160">ユーザー アカウントをグループに追加して、Office 2010、Office 2013、または Office 2016 を使用しているユーザーに Office 365 ProPlus を自動的に展開します。</span><span class="sxs-lookup"><span data-stu-id="53145-160">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="53145-161">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="53145-161">Mobile device management</span></span> | <span data-ttu-id="53145-162">デバイス登録とデバイス ベースの条件付きアクセス ポリシーのグループにアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="53145-162">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="53145-163">情報保護</span><span class="sxs-lookup"><span data-stu-id="53145-163">Information protection</span></span> | <span data-ttu-id="53145-164">情報保護ラベルのグループにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="53145-164">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="53145-165">基礎インフラストラクチャが完成し、テストおよび試験運用が完了したら、Windows 10 Enterprise や Office 365 ProPlus などのインストール済みソフトウェアをロールアウトすることができます。デバイス登録や条件付きアクセス ポリシーなどのクラウドベースのサービスの運用も安全な環境で行えます。ビジネス目標と IT リソースに最も適した方法で、ユーザーに提供することができます。</span><span class="sxs-lookup"><span data-stu-id="53145-165">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="53145-166">展開およびプロジェクト管理の戦略</span><span class="sxs-lookup"><span data-stu-id="53145-166">Deployment and project management strategies</span></span>

<span data-ttu-id="53145-167">パイロット ユーザーおよび他の組織の基礎インフラストラクチャのさまざまなフェーズにおけるプロジェクト管理への取り組み方については、「[展開戦略](deployment-strategies-microsoft-365-enterprise.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53145-167">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>


## <a name="next-step"></a><span data-ttu-id="53145-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="53145-168">Next step</span></span>

- <span data-ttu-id="53145-169">Office 365、Enterprise Mobility + Security (EMS)、または Windows 10 Enterprise の既存のインフラストラクチャがある場合:</span><span class="sxs-lookup"><span data-stu-id="53145-169">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span>
  - <span data-ttu-id="53145-170">「[既存のインフラストラクチャで展開する](deploy-with-existing-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53145-170">See [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md).</span></span> <span data-ttu-id="53145-171">この記事では、各フェーズの終了条件について説明しています。</span><span class="sxs-lookup"><span data-stu-id="53145-171">This article steps you through the exit criteria for each phase.</span></span>
- <span data-ttu-id="53145-172">最初から始める場合:</span><span class="sxs-lookup"><span data-stu-id="53145-172">I'm starting from scratch:</span></span> 
   - <span data-ttu-id="53145-173">「[フェーズ 1: ネットワーク](networking-infrastructure.md)」を参照して、エンド ツー エンドの展開を始めてください。</span><span class="sxs-lookup"><span data-stu-id="53145-173">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>
