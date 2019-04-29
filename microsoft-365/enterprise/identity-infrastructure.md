---
title: 'フェーズ 2: ID'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の ID インフラストラクチャを展開する手順。
ms.openlocfilehash: 932b6fb2cfeb86edcf708bdfdea55cdd8b580838
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288740"
---
# <a name="phase-2-identity"></a><span data-ttu-id="19ee8-103">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="19ee8-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="19ee8-104">Microsoft 365 enterprise では、ID インフラストラクチャを入念に計画および実施することで、セキュリティを強化し、認証されたユーザーとデバイスだけが生産性ワークロードとそのデータにアクセスできるようにする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="19ee8-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="19ee8-105">既に ID インフラストラクチャを展開している場合は、[ID インフラストラクチャの終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="19ee8-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="19ee8-106">Microsoft 365 Enterprise の ID インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="19ee8-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="19ee8-107">開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19ee8-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="19ee8-p101">クラウドで新しい ID インフラストラクチャを計画および展開するには、次の手順を使用します。また、これらの手順を使用して既存のオンプレミスまたはハイブリッド ID インフラストラクチャを導入し、Microsoft 365 Enterprise と連携することができます。</span><span class="sxs-lookup"><span data-stu-id="19ee8-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="19ee8-110">ユーザーおよびグループを計画する</span><span class="sxs-lookup"><span data-stu-id="19ee8-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="19ee8-111">特権 ID をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="19ee8-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="19ee8-112">ハイブリッド ID の構成</span><span class="sxs-lookup"><span data-stu-id="19ee8-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="19ee8-113">セキュリティで保護されたユーザー認証を構成する</span><span class="sxs-lookup"><span data-stu-id="19ee8-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="19ee8-114">ユーザーのアクセスを簡素化する</span><span class="sxs-lookup"><span data-stu-id="19ee8-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="19ee8-115">管理を容易にするためのグループの使用</span><span class="sxs-lookup"><span data-stu-id="19ee8-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="19ee8-116">上記の手順が完了したら、このフェーズの[終了条件](identity-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="19ee8-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="19ee8-117">ID とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="19ee8-117">Identity and device access recommendations</span></span>

<span data-ttu-id="19ee8-p102">Microsoft では、セキュアで生産性の高い要員を確保するために [ID とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する一連の推奨事項を提供しています。たとえば、このフェーズの手順で、以下の記事に記されている推奨事項と設定を使用してください。</span><span class="sxs-lookup"><span data-stu-id="19ee8-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="19ee8-120">前提条件</span><span class="sxs-lookup"><span data-stu-id="19ee8-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="19ee8-121">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="19ee8-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="19ee8-122">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="19ee8-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="19ee8-123">以下のリソースで、Microsoft の IT 担当者による Microsoft 365 Enterprise の ID 機能の計画方法および展開方法を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="19ee8-123">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="19ee8-124">Microsoft でのユーザー ID の管理とアクセスの保護</span><span class="sxs-lookup"><span data-stu-id="19ee8-124">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="19ee8-125">アクセス許可を昇格するために、Azure AD Privileged Identity Management を使用する</span><span class="sxs-lookup"><span data-stu-id="19ee8-125">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="19ee8-126">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="19ee8-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="19ee8-127">架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ハイブリッド ID インフラストラクチャを展開](contoso-identity.md)した方法をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="19ee8-127">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="19ee8-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="19ee8-128">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="19ee8-129">ユーザーおよびグループを計画する</span><span class="sxs-lookup"><span data-stu-id="19ee8-129">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
