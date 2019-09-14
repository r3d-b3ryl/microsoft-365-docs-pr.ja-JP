---
title: 'フェーズ 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の Office 365 ProPlus インフラストラクチャを展開する手順。
ms.openlocfilehash: f20435edc4cdc675d0308774eb493a67723054f4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982768"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="4a1b8-103">フェーズ 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="4a1b8-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="4a1b8-104">*これは Microsoft 365 Enterprise および Microsoft 365 Education のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="4a1b8-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="4a1b8-p101">Microsoft 365 Enterprise に含まれている Office 365 ProPlus は、Office のサブスクリプション版です。Office 2016 と同様に、Office 365 ProPlus にはすべての Office アプリケーションが含まれており、これらのアプリケーションはクライアント デバイスに直接インストールされます。Office 2016 とは異なり、Office 365 ProPlus は定期的に更新され新機能が導入されます。また、ユーザーベースのライセンス モデルを採用しており、Office を最大 5 台のデバイスにインストールできます。詳細については、「[企業内での Office 365 ProPlus について](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="4a1b8-p102">このフェーズでは、Microsoft 365 Enterprise の一部である Office 365 ProPlus をクライアント デバイスに展開します。このガイダンスの他に、展開の際に役立つ [Microsoft Fastrack](https://fasttrack.microsoft.com/office) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="4a1b8-111">既に Office 365 ProPlus を展開している場合は、このフェーズの[終了条件](office365proplus-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-111">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="4a1b8-112">Windows 10 Enterprise と Office 365 ProPlus の両方を展開するには、[デスクトップ展開センター](desktop-deployment-center-home.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-112">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="4a1b8-113">手順 1: 環境を評価する</span><span class="sxs-lookup"><span data-stu-id="4a1b8-113">Step 1: Assess your environment</span></span>

<span data-ttu-id="4a1b8-p103">Office 365 ProPlus を展開する前に、「[Office 365 ProPlus を展開するため、実際の環境と要件を評価する](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)」のガイダンスに従います。この評価では、システム要件、クライアント デバイスの詳細 (アーキテクチャや必要な言語など)、ライセンスの要件、ネットワーク容量、アプリケーションの互換性などを評価します。評価を実施すると、展開計画の一部としていくつかの重要な決定をする上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="4a1b8-117">手順 2: 展開を計画する</span><span class="sxs-lookup"><span data-stu-id="4a1b8-117">Step 2: Plan your deployment</span></span>

<span data-ttu-id="4a1b8-p104">実際の環境の評価が完了したら、「[Office 365 ProPlus の展開を計画する](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)」のガイダンスに従って展開計画を策定します。この計画には次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="4a1b8-120">使用するツール (System Center Configuration Manger や Office 展開ツール (OTD) など) を含め、Office を展開する方法と Office のインストールを実行する場所</span><span class="sxs-lookup"><span data-stu-id="4a1b8-120">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="4a1b8-121">Office の更新の管理方法</span><span class="sxs-lookup"><span data-stu-id="4a1b8-121">How to manage updates to Office</span></span>
- <span data-ttu-id="4a1b8-122">使用する更新チャネル (Office の更新チャネルにより、ユーザーが Office アプリケーションの機能更新を受け取る頻度が制御されます)</span><span class="sxs-lookup"><span data-stu-id="4a1b8-122">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="4a1b8-123">使用する Office インストール パッケージと展開グループ (どのユーザーにどの Office アプリケーションと言語をインストールするかなど)</span><span class="sxs-lookup"><span data-stu-id="4a1b8-123">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="4a1b8-124">「[計画資料](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)」にはこれらのすべてのオプションのベスト プラクティスが収録されています (展開の管理、更新の管理、インストール パッケージの定義、展開グループの作成など)。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-124">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="4a1b8-125">手順 3: 展開する</span><span class="sxs-lookup"><span data-stu-id="4a1b8-125">Step 3: Deploy</span></span>

<span data-ttu-id="4a1b8-126">手順 2 で策定した展開計画に基づき、展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-126">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="4a1b8-127">**[System Center Configuration Manager を使用して Office 365 ProPlus を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Configuration Manager を使用して展開を管理し、ネットワーク内の配布ポイントから Office をダウンロードして展開します。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-127">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="4a1b8-128">**[ODT を使用してクラウドから Office 365 ProPlus を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** ODT を使用して展開を管理し、Office CDN からクライアント デバイスに Office を直接インストールします。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-128">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="4a1b8-129">**[ODT を使用してローカル ソースから Office 365 ProPlus を展開する](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** ODT を使用して展開を管理し、ネットワーク内のローカル ソースから Office をダウンロードして展開します。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-129">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="4a1b8-130">**[Office ポータルから Office 365 ProPlus をセルフインストールする](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Office ポータルから展開を管理し、ユーザーがポータルから各自のクライアント デバイスに Office インストールします。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-130">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="4a1b8-p105">多くの組織では、ユーザーに応じて前述のオプションを組み合わせて使用します。たとえば、ほとんどのユーザーに対しては Configuration Manager を使用して Office を展開しますが、社内ネットワークに頻繁に接続しない少数の作業員のグループにはセルフ インストールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="4a1b8-p106">組織が Configuration Manager を使用する場合は、Current Branch にアップグレードし、最新リリースに更新することをお勧めします。詳細については、「[Configuration Manager のどのブランチを使用するか](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="4a1b8-135">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="4a1b8-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4a1b8-136">Microsoft のエキスパートが [Office 365 ProPlus の更新プログラムを展開および管理](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365#primaryR7)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-136">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="4a1b8-137">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="4a1b8-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4a1b8-138">架空の代表的な多国籍企業である Contoso Corporation の [Office 365 ProPlus の展開](contoso-o365pp.md)方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4a1b8-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="4a1b8-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="4a1b8-139">Next step</span></span>

[<span data-ttu-id="4a1b8-140">Office 365 ProPlus インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="4a1b8-140">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
