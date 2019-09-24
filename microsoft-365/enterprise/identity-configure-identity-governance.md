---
title: '手順 7: Identity Governance を構成する'
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
ms.openlocfilehash: 7ba54db29335f4f8f6eefff0cafbdefe3c522d7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37086413"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="4e7a2-103">手順 7: Identity Governance を構成する</span><span class="sxs-lookup"><span data-stu-id="4e7a2-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4e7a2-104">Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="4e7a2-105">たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="4e7a2-106">Azure Active Directory (Azure AD) のIdentity Governance の詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="4e7a2-107">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="4e7a2-107">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="4e7a2-108">Azure AD アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="4e7a2-108">Set up Azure AD access reviews</span></span>

<span data-ttu-id="4e7a2-109">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="4e7a2-109">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="4e7a2-110">この手順では、Azure AD アクセス レビューを設定します。これにより、ユーザーのアクセスを確認し、適切なユーザーのみが引き続きアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-110">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="4e7a2-111">例:</span><span class="sxs-lookup"><span data-stu-id="4e7a2-111">For example:</span></span>

- <span data-ttu-id="4e7a2-112">新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-112">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="4e7a2-113">従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-113">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="4e7a2-114">従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-114">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="4e7a2-115">これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-115">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="4e7a2-116">Azure AD アクセス レビューの詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-116">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="4e7a2-117">Azure AD Privileged Identity Management (PIM) により、Azure AD、Azure、およびその他の Microsoft クラウド サービスの全体で、リソースに対するアクセス権のセキュリティ保護に合わせた管理を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-117">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="4e7a2-118">Azure AD PIM には、会社のリソース (ディレクトリ、Office 365、Azure リソースの役割など) のセキュリティを確保するために、包括的なガバナンス管理のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-118">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="4e7a2-119">他のアクセス方法と同様、組織では、アクセス レビューを使用して、管理者の役割に属するすべてのユーザーの定期的なアクセス再認定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-119">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="4e7a2-120">Azure AD PIM は、Microsoft 365 Enterprise の E5 バージョンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-120">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="4e7a2-121">さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-121">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="4e7a2-122">グループとアプリ</span><span class="sxs-lookup"><span data-stu-id="4e7a2-122">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="4e7a2-123">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="4e7a2-123">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="4e7a2-124">Azure リソースの役割</span><span class="sxs-lookup"><span data-stu-id="4e7a2-124">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="4e7a2-125">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-access-reviews)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4e7a2-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e7a2-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="4e7a2-126">Next step</span></span>

[<span data-ttu-id="4e7a2-127">ID インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="4e7a2-127">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

