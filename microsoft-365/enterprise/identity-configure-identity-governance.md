---
title: '手順 7: Identity Governance を構成する'
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
description: Azure AD テナントの Identity Governance を理解し、構成します。
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543996"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="9ac44-103">手順 6: Identity Governance を構成する</span><span class="sxs-lookup"><span data-stu-id="9ac44-103">Step 6: Configure identity governance</span></span>

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="9ac44-105">Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。</span><span class="sxs-lookup"><span data-stu-id="9ac44-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="9ac44-106">たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="9ac44-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="9ac44-107">Azure Active Directory (Azure AD) のIdentity Governance の詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac44-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="9ac44-108">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="9ac44-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="9ac44-109">Azure AD アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="9ac44-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="9ac44-110">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="9ac44-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9ac44-111">この手順では、Azure AD アクセス レビューを設定します。これにより、ユーザーのアクセスを確認し、適切なユーザーのみが引き続きアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9ac44-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="9ac44-112">例:</span><span class="sxs-lookup"><span data-stu-id="9ac44-112">For example:</span></span>

- <span data-ttu-id="9ac44-113">新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="9ac44-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="9ac44-114">従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac44-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="9ac44-115">従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ac44-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="9ac44-116">これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9ac44-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="9ac44-117">Azure AD アクセス レビューの詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac44-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="9ac44-118">Azure AD Privileged Identity Management (PIM) により、Azure AD、Azure、およびその他の Microsoft クラウド サービスの全体で、リソースに対するアクセス権のセキュリティ保護に合わせた管理を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="9ac44-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="9ac44-119">Azure AD PIM には、会社のリソース (ディレクトリ、Office 365、Azure リソースの役割など) のセキュリティを確保するために、包括的なガバナンス管理のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9ac44-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="9ac44-120">他のアクセス方法と同様、組織では、アクセス レビューを使用して、管理者の役割に属するすべてのユーザーの定期的なアクセス再認定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9ac44-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="9ac44-121">Azure AD PIM は、Microsoft 365 Enterprise の E5 バージョンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ac44-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="9ac44-122">さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ac44-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="9ac44-123">グループとアプリ</span><span class="sxs-lookup"><span data-stu-id="9ac44-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="9ac44-124">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="9ac44-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="9ac44-125">Azure リソースの役割</span><span class="sxs-lookup"><span data-stu-id="9ac44-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="9ac44-126">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-access-reviews)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9ac44-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="9ac44-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ac44-127">Next step</span></span>

[<span data-ttu-id="9ac44-128">ID インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="9ac44-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

