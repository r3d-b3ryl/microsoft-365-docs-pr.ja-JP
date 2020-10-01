---
title: Microsoft 365 identity ガバナンスを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 identity ガバナンス機能の使用方法について説明します。
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328512"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="f4fb1-103">Microsoft 365 identity ガバナンスを管理する</span><span class="sxs-lookup"><span data-stu-id="f4fb1-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="f4fb1-104">Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="f4fb1-105">たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="f4fb1-106">詳細については、「 [Azure Active Directory の id ガバナンスの概要 (AZURE AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="f4fb1-107">Azure AD アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="f4fb1-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="f4fb1-108">Azure AD のアクセスレビューを使用すると、ユーザーのアクセスを確認して、適切な人物だけがアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="f4fb1-109">例:</span><span class="sxs-lookup"><span data-stu-id="f4fb1-109">For example:</span></span>

- <span data-ttu-id="f4fb1-110">新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="f4fb1-111">従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="f4fb1-112">従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="f4fb1-113">これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="f4fb1-114">詳細については、「 [access のレビューの概要](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="f4fb1-115">Azure AD Privileged Identity Management (PIM) により、Azure AD、Azure、およびその他の Microsoft クラウド サービスの全体で、リソースに対するアクセス権のセキュリティ保護に合わせた管理を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-115">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="f4fb1-116">Azure AD PIM には、会社のリソース (ディレクトリ、Office 365、Azure リソースの役割など) のセキュリティを確保するために、包括的なガバナンス管理のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-116">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="f4fb1-117">他のアクセス方法と同様、組織では、アクセス レビューを使用して、管理者の役割に属するすべてのユーザーの定期的なアクセス再認定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-117">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="f4fb1-118">Azure AD PIM は、Microsoft 365 Enterprise の E5 バージョンでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-118">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="f4fb1-119">さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-119">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="f4fb1-120">グループとアプリ</span><span class="sxs-lookup"><span data-stu-id="f4fb1-120">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="f4fb1-121">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="f4fb1-121">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="f4fb1-122">Azure リソース ロール</span><span class="sxs-lookup"><span data-stu-id="f4fb1-122">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="f4fb1-123">Azure AD 受給管理の設定</span><span class="sxs-lookup"><span data-stu-id="f4fb1-123">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="f4fb1-124">Wiht Azure AD 受給管理では、アクセス要求ワークフロー、アクセス割り当て、レビュー、および有効期限を自動化することで、id とアクセスのライフサイクルをスケールで管理できます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-124">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="f4fb1-125">従業員は、ジョブを実行するためにさまざまなグループ、アプリケーション、およびサイトにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-125">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="f4fb1-126">要件の変更、新しいアプリケーションの追加、またはユーザーに対する追加のアクセス許可が必要になるため、このアクセスを管理するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-126">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="f4fb1-127">他の組織と共同作業を行う場合は、他の組織内のユーザーが組織のリソースにアクセスする必要があるかどうかを確認することはできません。また、外部ユーザーには、組織が使用しているアプリケーション、グループ、またはサイトがわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-127">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="f4fb1-128">Azure AD 受給管理は、内部および外部ユーザーのグループ、アプリケーション、および SharePoint サイトへのアクセスをより効率的に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-128">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="f4fb1-129">詳細については、「 [AZURE AD 資格情報管理の概要](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4fb1-129">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
