---
title: Microsoft 365 Enterprise の基礎インフラストラクチャチャ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の基礎インフラストラクチャを組織に展開するための主要フェーズ (別名、コア展開) について理解します。
ms.openlocfilehash: c18e4d770aec63da091ad38fc341a87f9d71e9be
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370354"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="8cbae-103">Microsoft 365 Enterprise の基礎インフラストラクチャチャ</span><span class="sxs-lookup"><span data-stu-id="8cbae-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="8cbae-104">Microsoft 365 Enterprise のエンド ツー エンドの展開を自分で行っている場合は、まずアプリケーションとサービスによる創造性とチームワークが安全な環境で発揮される強固な基盤を構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cbae-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="8cbae-105">この基盤は、*コア展開*と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="8cbae-105">This foundation is sometimes referred to as the core deployment.</span></span>

<span data-ttu-id="8cbae-106">展開に関して定義されたエンド ツー エンドのパスの次のフェーズを使用して Microsoft 365 Enterprise の基礎インフラストラクチャを計画して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="8cbae-107">フェーズ</span><span class="sxs-lookup"><span data-stu-id="8cbae-107">Phase</span></span> | <span data-ttu-id="8cbae-108">結果</span><span class="sxs-lookup"><span data-stu-id="8cbae-108">Results</span></span> |
|:-------|:-----|:-----|
|![フェーズ 1: ネットワーク](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="8cbae-110">フェーズ 1: ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8cbae-110">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="8cbae-111">ネットワークは、Microsoft 365 のクラウドベースのサービスへのアクセスに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-111">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![フェーズ 2: ID](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="8cbae-113">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="8cbae-113">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="8cbae-114">管理者アカウントの保護と、ユーザーおよびグループの同期が行われ、強固なセキュリティによるユーザー認証が実現します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-114">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="8cbae-116">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8cbae-116">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="8cbae-117">既存の Windows ベースのコンピューターは Windows 10 Enterprise にアップグレードすることができ、新しいデバイスは Windows 10 Enterprise と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-117">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![フェーズ 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="8cbae-119">フェーズ 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="8cbae-119">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="8cbae-120">Microsoft Office の既存のユーザーは Office 365 ProPlus にアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-120">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![フェーズ 5: モバイル デバイス管理](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="8cbae-122">フェーズ 5: モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="8cbae-122">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="8cbae-123">デバイスを登録し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-123">Your devices can be enrolled and managed.</span></span> |
|![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="8cbae-125">フェーズ 6: 情報保護</span><span class="sxs-lookup"><span data-stu-id="8cbae-125">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="8cbae-126">Office 365 のセキュリティ機能が有効になると、ラベルとポリシーを使用して、ドキュメントとメールを保護する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="8cbae-126">Office 365 security features are enabled and your sensitivity or Azure Information Protection labels are ready to protect documents.</span></span> |

<span data-ttu-id="8cbae-127">フェーズは最も基本的なもの (ネットワークと ID) から始めます。その後に、インフラストラクチャの設定とグループのレイヤーを作成し以下を実施します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-127">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="8cbae-128">最新かつセキュリティで保護されたバージョンの Windows をデバイスにインストールし、最新状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-128">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="8cbae-129">デバイスに最新バージョンの Microsoft Office をインストールし、最新状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-129">Install the most current version of Microsoft Office on your devices and keep it current.</span></span>
- <span data-ttu-id="8cbae-130">組織のデバイスおよびデバイスのアプリへのアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-130">Manage your organization's devices and their access to apps.</span></span>
- <span data-ttu-id="8cbae-131">デバイス上およびクラウド内の情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-131">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="8cbae-132">また、IT リソースやビジネス ニーズに合わせて、フェーズそのものやフェーズ内の手順の構成を変えて臨機応変に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-132">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="8cbae-133">**小規模または新しい組織の場合**、次のフェーズにそって必要に応じてインフラストラクチャを体系的に構築します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-133">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span> <span data-ttu-id="8cbae-134">簡略化された非エンタープライズの展開については、[こちら](deploy-foundation-infrastructure-non-enterprises.md)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="8cbae-134">For a simplified deployment for non-enterprises, click [here](deploy-foundation-infrastructure-non-enterprises.md).</span></span>

-  <span data-ttu-id="8cbae-135">**企業組織の場合**、フェーズを定義されたパスではなく IT インフラストラクチャのレイヤーとして表示し、組織全体の各レイヤーに必要な条件に対して最終的に一番最適な方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-135">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="8cbae-136">各フェーズの最後には*終了条件*がありますので、その条件を確認するようにしてください。満たさなければならない必須条件、検討する必要があるオプションの条件を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-136">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="8cbae-137">各フェーズの終了条件は、オンプレミスとクラウドのインフラストラクチャ、およびそのフェーズから得られるエンド ツー エンドの構成が、Microsoft 365 Enterprise 展開の要件を満たしているかどうかの判断基準となります。</span><span class="sxs-lookup"><span data-stu-id="8cbae-137">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="8cbae-138">以下の短時間のビデオでコンテンツの構造を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-138">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="8cbae-139">以下が Microsoft 365 Enterprise の全体的な展開ガイドの基礎インフラストラクチャとなります。</span><span class="sxs-lookup"><span data-stu-id="8cbae-139">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![Microsoft 365 Enterprise の全体的な展開ガイドの基礎インフラストラクチャ](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a><span data-ttu-id="8cbae-141">概要</span><span class="sxs-lookup"><span data-stu-id="8cbae-141">At-a-glance</span></span>

<span data-ttu-id="8cbae-142">[Microsoft 365 Enterprise の基盤インフラストラクチャのポスター](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)は、各フェーズで参照できる中心的な場所です。</span><span class="sxs-lookup"><span data-stu-id="8cbae-142">The [Microsoft 365 Enterprise foundation infrastructure poster](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf) is a central location for you to view, for each phase:</span></span>

- <span data-ttu-id="8cbae-143">管理者とユーザーのフェーズの全体的な目標</span><span class="sxs-lookup"><span data-stu-id="8cbae-143">The overall goals of the phase for administrators and users</span></span>
- <span data-ttu-id="8cbae-144">サービス、機能、およびツール</span><span class="sxs-lookup"><span data-stu-id="8cbae-144">The services, features, and tools</span></span>
- <span data-ttu-id="8cbae-145">計画の主な設計の決定</span><span class="sxs-lookup"><span data-stu-id="8cbae-145">The key design decisions for planning</span></span>
- <span data-ttu-id="8cbae-146">構成の結果</span><span class="sxs-lookup"><span data-stu-id="8cbae-146">The configuration results</span></span>
- <span data-ttu-id="8cbae-147">新しいユーザーのオンボード プロセス</span><span class="sxs-lookup"><span data-stu-id="8cbae-147">The process for onboarding a new user</span></span>
- <span data-ttu-id="8cbae-148">モニターと更新の方法</span><span class="sxs-lookup"><span data-stu-id="8cbae-148">How to monitor and update</span></span>

<span data-ttu-id="8cbae-149">[![Microsoft 365 Enterprise の基盤インフラストラクチャ ポスターの画像](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)</span><span class="sxs-lookup"><span data-stu-id="8cbae-149">[![Image for the Microsoft 365 Enterprise foundation infrastructure poster](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)</span></span>

<span data-ttu-id="8cbae-150">ポスターのコピーをダウンロードするには、[ここ](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbae-150">To download a copy of the poster, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).</span></span>


## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="8cbae-151">インフラストラクチャの構成とユーザー ロールアウト</span><span class="sxs-lookup"><span data-stu-id="8cbae-151">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="8cbae-152">構成されたソフトウェアとサービス一式が、基礎インフラストラクチャになります。これらのソフトウェアやサービスをユーザー向けに組み合わせることで、安全な環境で Microsoft 365 Enterprise が提供するすべての機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-152">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="8cbae-153">エンド ツー エンドの展開の最終目的は、お客様の全ユーザーとそのユーザーの Windows ベースのデバイスに基礎インフラストラクチャを適用することです。</span><span class="sxs-lookup"><span data-stu-id="8cbae-153">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="8cbae-154">ただし、Microsoft 365 Enterprise の基礎インフラストラクチャと、ユーザーへのソフトウェアおよびサービスのロールアウトは別のものになります。</span><span class="sxs-lookup"><span data-stu-id="8cbae-154">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="8cbae-155">***基礎インフラストラクチャのレイヤーは、すべてのユーザーにロールアウトしなくても構成することができます。***</span><span class="sxs-lookup"><span data-stu-id="8cbae-155">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="8cbae-156">組織のオフィス、地域、あるいは部署の多数のユーザーにロールアウトする前に、基礎インフラストラクチャの要素を構成、テスト、試験運用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-156">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="8cbae-157">たとえば、以下を目的とした設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-157">For example, you create the settings for:</span></span>

| <span data-ttu-id="8cbae-158">フェーズ</span><span class="sxs-lookup"><span data-stu-id="8cbae-158">Phase</span></span> | <span data-ttu-id="8cbae-159">結果</span><span class="sxs-lookup"><span data-stu-id="8cbae-159">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="8cbae-160">ID</span><span class="sxs-lookup"><span data-stu-id="8cbae-160">Identity</span></span> | <span data-ttu-id="8cbae-161">アカウント同期と ID ベースの条件付きアクセス ポリシーのグループ。</span><span class="sxs-lookup"><span data-stu-id="8cbae-161">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="8cbae-162">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8cbae-162">Windows 10 Enterprise</span></span> | <span data-ttu-id="8cbae-163">Windows 7 または Windows 8.1 を実行しているコンピューターを Windows 10 Enterprise に自動的にアップグレードするためのグループ。</span><span class="sxs-lookup"><span data-stu-id="8cbae-163">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="8cbae-164">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="8cbae-164">Office 365 ProPlus</span></span> | <span data-ttu-id="8cbae-165">Office 2010、Office 2013、または Office 2016 を使用しているユーザーに Office 365 ProPlus を自動的に展開するためのグループ。</span><span class="sxs-lookup"><span data-stu-id="8cbae-165">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="8cbae-166">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="8cbae-166">Mobile device management</span></span> | <span data-ttu-id="8cbae-167">デバイス登録とデバイス ベースの条件付きアクセス ポリシーのグループ。</span><span class="sxs-lookup"><span data-stu-id="8cbae-167">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="8cbae-168">情報保護</span><span class="sxs-lookup"><span data-stu-id="8cbae-168">Information protection</span></span> | <span data-ttu-id="8cbae-169">Office 365 の機密ラベルのグループ。</span><span class="sxs-lookup"><span data-stu-id="8cbae-169">Groups for Office 365 sensitivity labels.</span></span> |

<span data-ttu-id="8cbae-170">基礎インフラストラクチャの要素をユーザーにロールアウトする準備ができたら、以下を実施します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-170">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="8cbae-171">フェーズ</span><span class="sxs-lookup"><span data-stu-id="8cbae-171">Phase</span></span> | <span data-ttu-id="8cbae-172">ロールアウト アクション</span><span class="sxs-lookup"><span data-stu-id="8cbae-172">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="8cbae-173">ID</span><span class="sxs-lookup"><span data-stu-id="8cbae-173">Identity</span></span> | <span data-ttu-id="8cbae-174">ID ベースの条件付きアクセス ポリシーのグループにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-174">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="8cbae-175">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8cbae-175">Windows 10 Enterprise</span></span> | <span data-ttu-id="8cbae-176">グループにアカウントを追加して、Windows 7 または Windows 8.1 を使用しているユーザーに Windows 10 Enterprise を自動的に展開します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-176">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="8cbae-177">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="8cbae-177">Office 365 ProPlus</span></span> | <span data-ttu-id="8cbae-178">ユーザー アカウントをグループに追加して、Office 2010、Office 2013、または Office 2016 を使用しているユーザーに Office 365 ProPlus を自動的に展開します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-178">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="8cbae-179">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="8cbae-179">Mobile device management</span></span> | <span data-ttu-id="8cbae-180">デバイス登録とデバイス ベースの条件付きアクセス ポリシーのグループにアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-180">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="8cbae-181">情報保護</span><span class="sxs-lookup"><span data-stu-id="8cbae-181">Information protection</span></span> | <span data-ttu-id="8cbae-182">機密ラベルのグループにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-182">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="8cbae-183">基礎インフラストラクチャのフェーズと要素が完成し、テストおよび試験運用が行われると、ユーザーのビジネス目標と IT リソースに最も適した方法で、Windows 10 Enterprise および Office 365 ProPlus などのインストール済みソフトウェアと、デバイス登録および条件付きアクセス ポリシーなどのクラウドベースのサービスと保護をロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-183">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="8cbae-184">展開およびプロジェクト管理の戦略</span><span class="sxs-lookup"><span data-stu-id="8cbae-184">Deployment and project management strategies</span></span>

<span data-ttu-id="8cbae-185">パイロット ユーザーおよび他の組織の基礎インフラストラクチャのさまざまなフェーズにおけるプロジェクト管理への取り組み方については、「[展開戦略](deployment-strategies-microsoft-365-enterprise.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbae-185">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>

## <a name="deployment-for-non-enterprises"></a><span data-ttu-id="8cbae-186">非エンタープライズの展開</span><span class="sxs-lookup"><span data-stu-id="8cbae-186">Deployment for non-enterprises</span></span>

<span data-ttu-id="8cbae-187">組織の規模が小さく、Microsoft 365 Business が適していない場合は、「[非エンタープライズの展開](deploy-foundation-infrastructure-non-enterprises.md)」に記載されている簡略化された展開方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbae-187">If your organization is smaller and Microsoft 365 Business is not suitable for you, see [deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md) for a simplified deployment method.</span></span>


## <a name="next-step"></a><span data-ttu-id="8cbae-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="8cbae-188">Next step</span></span>

| <span data-ttu-id="8cbae-189">現在地</span><span class="sxs-lookup"><span data-stu-id="8cbae-189">Where I am</span></span> | <span data-ttu-id="8cbae-190">行く必要がある場所</span><span class="sxs-lookup"><span data-stu-id="8cbae-190">Where I need to go</span></span> |
|:-------|:-----|
| <span data-ttu-id="8cbae-191">Office 365、Enterprise Mobility + Security (EMS)、または Windows 10 Enterprise の既存のインフラストラクチャがある場合</span><span class="sxs-lookup"><span data-stu-id="8cbae-191">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span> | <span data-ttu-id="8cbae-192">「[既存のインフラストラクチャを使用して展開する](deploy-with-existing-infrastructure.md)」から開始し、各フェーズの終了条件に進みます。</span><span class="sxs-lookup"><span data-stu-id="8cbae-192">Start with [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md), which steps you through the exit criteria for each phase.</span></span> |
| <span data-ttu-id="8cbae-193">エンタープライズとして最初から始めている</span><span class="sxs-lookup"><span data-stu-id="8cbae-193">I'm starting from scratch as an enterprise</span></span> | <span data-ttu-id="8cbae-194">「[フェーズ 1: ネットワーク](networking-infrastructure.md)」を参照して、エンド ツー エンドの展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-194">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span> |
| <span data-ttu-id="8cbae-195">非エンタープライズとして最初から始めている</span><span class="sxs-lookup"><span data-stu-id="8cbae-195">I'm starting from scratch as a non-enterprise</span></span> | <span data-ttu-id="8cbae-196">「[非エンタープライズの展開](deploy-foundation-infrastructure-non-enterprises.md)」を参照して、エンド ツー エンドの展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="8cbae-196">Begin your end-to-end deployment journey with [Deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md).</span></span> |
