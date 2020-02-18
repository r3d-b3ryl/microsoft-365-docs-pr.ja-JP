---
title: 'フェーズ 2: ID'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の ID インフラストラクチャを展開する手順。
ms.openlocfilehash: f32df9a35e09b438b5034ad963523879a639a3fc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067330"
---
# <a name="phase-2-identity"></a><span data-ttu-id="a670f-103">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="a670f-103">Phase 2: Identity</span></span>

![フェーズ 2: ID](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="a670f-105">Microsoft 365 enterprise では、ID インフラストラクチャを入念に計画および実施することで、セキュリティを強化し、認証されたユーザーとデバイスだけが生産性ワークロードとそのデータにアクセスできるようにする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="a670f-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="a670f-106">Microsoft 365 Enterprise の ID モデルと認証の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a670f-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="a670f-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="a670f-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="a670f-108">既に ID インフラストラクチャを展開している場合は、[ID インフラストラクチャの終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a670f-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="a670f-109">各 Microsoft 365 Enterprise プランの ID 機能、Azure Active Directory (Azure AD) の役割、オンプレミスおよびクラウドベースのコンポーネント、および最も一般的な認証構成については、[ID インフラストラクチャのポスター](../media/identity-infrastructure/M365E-ID-Infra.pdf) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a670f-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="a670f-110">[![ID インフラストラクチャ ポスター](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="a670f-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="a670f-111">この 2 ページのポスターで、Microsoft 365 Enterprise の ID の概念と構成をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="a670f-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="a670f-112">[このポスターをダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="a670f-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="a670f-113">Microsoft 365 Enterprise の ID インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="a670f-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="a670f-p101">クラウドで新しい ID インフラストラクチャを計画および展開するには、次の手順を使用します。また、これらの手順を使用して既存のオンプレミスまたはハイブリッド ID インフラストラクチャを導入し、Microsoft 365 Enterprise と連携することができます。</span><span class="sxs-lookup"><span data-stu-id="a670f-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![手順 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="a670f-117">グローバル管理者アカウントを作成して保護する</span><span class="sxs-lookup"><span data-stu-id="a670f-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![手順 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="a670f-119">パスワードをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="a670f-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![手順 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="a670f-121">ユーザーのサインインをセキュリティで保護して管理する</span><span class="sxs-lookup"><span data-stu-id="a670f-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![手順 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="a670f-123">ユーザー アカウントを追加する</span><span class="sxs-lookup"><span data-stu-id="a670f-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![手順 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="a670f-125">管理にグループを使用する</span><span class="sxs-lookup"><span data-stu-id="a670f-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![手順 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="a670f-127">Identity Governance を構成する</span><span class="sxs-lookup"><span data-stu-id="a670f-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="a670f-128">上記の手順が完了したら、このフェーズの[終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise ID の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a670f-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="a670f-129">ID とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="a670f-129">Identity and device access recommendations</span></span>

<span data-ttu-id="a670f-p102">Microsoft では、セキュアで生産性の高い要員を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。たとえば、このフェーズの手順で、以下の記事に記されている推奨事項と設定を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a670f-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="a670f-132">前提条件</span><span class="sxs-lookup"><span data-stu-id="a670f-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="a670f-133">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="a670f-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="a670f-134">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="a670f-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a670f-135">Microsoft の IT エキスパートが [ID を管理し、アクセスをセキュリティで保護](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a670f-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="a670f-136">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="a670f-136">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a670f-137">架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ハイブリッド ID インフラストラクチャを展開](contoso-identity.md)した方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="a670f-137">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso 社](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="a670f-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="a670f-139">Next step</span></span>

|||
|:-------|:-----|
|![手順 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="a670f-141">グローバル管理者アカウントを作成して保護する</span><span class="sxs-lookup"><span data-stu-id="a670f-141">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
