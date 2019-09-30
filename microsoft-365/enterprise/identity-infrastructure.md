---
title: 'フェーズ 2: ID'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の ID インフラストラクチャを展開する手順。
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981954"
---
# <a name="phase-2-identity"></a><span data-ttu-id="d4e49-103">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="d4e49-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="d4e49-104">Microsoft 365 enterprise では、ID インフラストラクチャを入念に計画および実施することで、セキュリティを強化し、認証されたユーザーとデバイスだけが生産性ワークロードとそのデータにアクセスできるようにする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="d4e49-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="d4e49-105">Microsoft 365 Enterprise の ID モデルと認証の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d4e49-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="d4e49-106">既に ID インフラストラクチャを展開している場合は、[ID インフラストラクチャの終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4e49-106">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="d4e49-107">各 Microsoft 365 Enterprise プランの ID 機能、Azure Active Directory (Azure AD) の役割、オンプレミスおよびクラウドベースのコンポーネント、および最も一般的な認証構成については、[ID インフラストラクチャのポスター](media/identity-infrastructure/M365E-ID-Infra.pdf) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4e49-107">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="d4e49-108">[![ID インフラストラクチャ ポスター](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="d4e49-108">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="d4e49-109">この 2 ページのポスターで、Microsoft 365 Enterprise の ID の概念と構成をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="d4e49-109">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d4e49-110">[このポスターをダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4e49-110">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="d4e49-111">Microsoft 365 Enterprise の ID インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="d4e49-111">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="d4e49-p101">クラウドで新しい ID インフラストラクチャを計画および展開するには、次の手順を使用します。また、これらの手順を使用して既存のオンプレミスまたはハイブリッド ID インフラストラクチャを導入し、Microsoft 365 Enterprise と連携することができます。</span><span class="sxs-lookup"><span data-stu-id="d4e49-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="d4e49-114">ユーザーおよびグループを計画する</span><span class="sxs-lookup"><span data-stu-id="d4e49-114">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="d4e49-115">特権 ID をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="d4e49-115">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="d4e49-116">ハイブリッド ID の構成</span><span class="sxs-lookup"><span data-stu-id="d4e49-116">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="d4e49-117">セキュリティで保護されたユーザー認証を構成する</span><span class="sxs-lookup"><span data-stu-id="d4e49-117">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="d4e49-118">ユーザーのアクセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="d4e49-118">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="d4e49-119">管理を容易にするためのグループの使用</span><span class="sxs-lookup"><span data-stu-id="d4e49-119">Use groups for easier management</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="d4e49-120">identity governance を設定する</span><span class="sxs-lookup"><span data-stu-id="d4e49-120">Configure identity governance</span></span>](identity-governance.md) |

<span data-ttu-id="d4e49-121">上記の手順が完了したら、このフェーズの[終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise ID の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4e49-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="d4e49-122">ID とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="d4e49-122">Identity and device access recommendations</span></span>

<span data-ttu-id="d4e49-p102">Microsoft では、セキュアで生産性の高い要員を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。たとえば、このフェーズの手順で、以下の記事に記されている推奨事項と設定を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d4e49-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="d4e49-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="d4e49-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="d4e49-126">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="d4e49-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="d4e49-127">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="d4e49-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d4e49-128">Microsoft の IT エキスパートが [ID を管理し、アクセスをセキュリティで保護](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365#primaryR5)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4e49-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="d4e49-129">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="d4e49-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="d4e49-130">架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ハイブリッド ID インフラストラクチャを展開](contoso-identity.md)した方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="d4e49-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="d4e49-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="d4e49-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="d4e49-132">ユーザーおよびグループを計画する</span><span class="sxs-lookup"><span data-stu-id="d4e49-132">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
