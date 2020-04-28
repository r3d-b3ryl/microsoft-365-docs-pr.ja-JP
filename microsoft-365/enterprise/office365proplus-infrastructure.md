---
title: 'フェーズ 4: Microsoft 365 Apps for enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の Microsoft 365 Apps for enterprises インフラストラクチャを展開する手順。
ms.openlocfilehash: fe29b8025a8ccf5babf2c52cd62ebc72860a8a5c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631431"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="cb64d-103">フェーズ 4: Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="cb64d-103">Phase 4: Microsoft 365 Apps for enterprise</span></span>

![フェーズ 4: Microsoft 365 Apps for enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="cb64d-105">*これは Microsoft 365 Enterprise および Microsoft 365 Education のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="cb64d-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="cb64d-106">Microsoft 365 Enterprise には、Office のサブスクリプション版である Microsoft 365 Apps for enterprise が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb64d-106">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Office.</span></span> <span data-ttu-id="cb64d-107">Office 2019 と同様に、Microsoft 365 Apps for enterprise にはすべての Office アプリケーションが含まれており、それらのアプリケーションはクライアント デバイスに直接インストールされます。</span><span class="sxs-lookup"><span data-stu-id="cb64d-107">Like Office 2019, Microsoft 365 Apps for enterprise includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="cb64d-108">Office 2019とは異なり、Microsoft 365 Apps for enterprise は定期的に新機能が更新され、複数のデバイスに Office をインストールできるユーザーベースのライセンス モデルを採用しています。</span><span class="sxs-lookup"><span data-stu-id="cb64d-108">Unlike Office 2019, Microsoft 365 Apps for enterprise is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="cb64d-109">詳細については、[企業向けのMicrosoft 365 Apps for enterprise について](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb64d-109">For more details, see [About Microsoft 365 Apps for enterprise in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="cb64d-p102">このフェーズでは、Microsoft 365 Apps for enterprise の一部である Office 365 ProPlus をクライアント デバイスに展開します。このガイダンスの他に、展開の際に役立つ [Microsoft Fastrack](https://fasttrack.microsoft.com/office) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb64d-p102">In this phase, you deploy Microsoft 365 Apps for enterprise to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="cb64d-112">既に Microsoft 365 Apps for enterprise を展開している場合は、このフェーズの[終了条件](office365proplus-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb64d-112">If you already have Microsoft 365 Apps for enterprise deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="cb64d-113">Windows 10 Enterprise と Microsoft 365 Apps for enterprise の両方を展開するには、[デスクトップ展開センター](desktop-deployment-center-home.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb64d-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="cb64d-114">手順 1: 環境を評価する</span><span class="sxs-lookup"><span data-stu-id="cb64d-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="cb64d-p103">Microsoft 365 Apps for enterprise を展開する前に、「[Microsoft 365 Apps for enterprise を展開するため、実際の環境と要件を評価する](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)」のガイダンスに従います。この評価では、システム要件、クライアント デバイスの詳細 (アーキテクチャや必要な言語など)、ライセンスの要件、ネットワーク容量、アプリケーションの互換性などを評価します。評価を実施すると、展開計画の一部としていくつかの重要な決定をする上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cb64d-p103">Before deploying Microsoft 365 Apps for enterprise, follow the guidance in [Assess your environment and requirements for deploying Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="cb64d-118">手順 2: 展開を計画する</span><span class="sxs-lookup"><span data-stu-id="cb64d-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="cb64d-p104">実際の環境の評価が完了したら、「[Microsoft 365 Apps for enterprise の展開を計画する](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)」のガイダンスに従って展開計画を策定します。この計画には次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb64d-p104">After assessing your environment, follow the guidance in [Plan your deployment of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="cb64d-121">使用するツール (Microsoft Endpoint Configuration Manger や Office 展開ツールなど) を含め、Office を展開する方法と Office のインストールを実行する場所</span><span class="sxs-lookup"><span data-stu-id="cb64d-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="cb64d-122">Office の更新の管理方法</span><span class="sxs-lookup"><span data-stu-id="cb64d-122">How to manage updates to Office</span></span>
- <span data-ttu-id="cb64d-123">使用する更新チャネル (Office の更新チャネルにより、ユーザーが Office アプリケーションの機能更新を受け取る頻度が制御されます)</span><span class="sxs-lookup"><span data-stu-id="cb64d-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="cb64d-124">使用する Office インストール パッケージと展開グループ (どのユーザーにどの Office アプリケーションと言語をインストールするかなど)</span><span class="sxs-lookup"><span data-stu-id="cb64d-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="cb64d-125">「[計画資料](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)」にはこれらのすべてのオプションのベスト プラクティスが収録されています (展開の管理、更新の管理、インストール パッケージの定義、展開グループの作成など)。</span><span class="sxs-lookup"><span data-stu-id="cb64d-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="cb64d-126">手順 3: 展開する</span><span class="sxs-lookup"><span data-stu-id="cb64d-126">Step 3: Deploy</span></span>

<span data-ttu-id="cb64d-127">展開計画に基づき、展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb64d-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="cb64d-128">**[構成マネージャーを使用して、Microsoft 365 Apps for enterprise を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** 構成マネージャーを使用して展開を管理し、ネットワーク内の配布ポイントから Office をダウンロードして展開します。</span><span class="sxs-lookup"><span data-stu-id="cb64d-128">**[Deploy Microsoft 365 Apps for enterprise with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="cb64d-129">**[ODT を使用してクラウドから Microsoft 365 Apps for enterprise を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** ODT を使用して展開を管理し、Office CDN からクライアント デバイスに Office を直接インストールします。</span><span class="sxs-lookup"><span data-stu-id="cb64d-129">**[Deploy Microsoft 365 Apps for enterprise with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="cb64d-130">**[Office ポータルから Microsoft 365 Apps for enterprise をセルフインストールする](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Office ポータルから展開を管理し、ユーザーがポータルから各自のクライアント デバイスに Office インストールします。</span><span class="sxs-lookup"><span data-stu-id="cb64d-130">**[Self-install Microsoft 365 Apps for enterprise from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="cb64d-p105">多くの組織では、ユーザーに応じて前述のオプションを組み合わせて使用します。たとえば、ほとんどのユーザーに対しては Configuration Manager を使用して Office を展開しますが、社内ネットワークに頻繁に接続しない少数の作業員のグループにはセルフ インストールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cb64d-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="cb64d-p106">組織が Configuration Manager を使用する場合は、Current Branch にアップグレードし、最新リリースに更新することをお勧めします。詳細については、「[Configuration Manager のどのブランチを使用するか](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb64d-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="cb64d-135">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="cb64d-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cb64d-136">Microsoft のエキスパートが [Microsoft 365 Apps for enterprise の更新プログラムを展開および管理](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb64d-136">Learn how the experts at Microsoft are [deploying and managing updates for Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="cb64d-137">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="cb64d-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="cb64d-138">架空の代表的な多国籍企業である Contoso Corporation の [Microsoft 365 Apps for enterprise の展開](contoso-o365pp.md)方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb64d-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Microsoft 365 Apps for enterprise](contoso-o365pp.md).</span></span>

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="cb64d-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="cb64d-140">Next step</span></span>

[<span data-ttu-id="cb64d-141">Microsoft 365 Apps for enterprise インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="cb64d-141">Microsoft 365 Apps for enterprise infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
