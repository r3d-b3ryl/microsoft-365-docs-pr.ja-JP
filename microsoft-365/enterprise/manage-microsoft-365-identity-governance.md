---
title: ID ガバナンスMicrosoft 365管理する
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
description: ID ガバナンス機能を使用するMicrosoft 365について説明します。
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910956"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="8eafc-103">ID ガバナンスMicrosoft 365管理する</span><span class="sxs-lookup"><span data-stu-id="8eafc-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="8eafc-104">Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。</span><span class="sxs-lookup"><span data-stu-id="8eafc-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="8eafc-105">たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="8eafc-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="8eafc-106">詳細については、「この概要の ID[ガバナンス for Azure Active Directory (Azure AD) 」を参照してください](/azure/active-directory/governance/identity-governance-overview)。</span><span class="sxs-lookup"><span data-stu-id="8eafc-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="8eafc-107">Azure AD アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="8eafc-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="8eafc-108">Azure ADアクセス レビューを使用すると、ユーザーのアクセスを確認して、適切なユーザーだけがアクセスを継続するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8eafc-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="8eafc-109">例:</span><span class="sxs-lookup"><span data-stu-id="8eafc-109">For example:</span></span>

- <span data-ttu-id="8eafc-110">新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="8eafc-111">従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="8eafc-112">従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="8eafc-113">これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="8eafc-114">詳細については、「アクセス レビューの [概要」を参照してください](/azure/active-directory/governance/access-reviews-overview)。</span><span class="sxs-lookup"><span data-stu-id="8eafc-114">For more information, see the [overview of access reviews](/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="8eafc-115">さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eafc-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="8eafc-116">グループとアプリ</span><span class="sxs-lookup"><span data-stu-id="8eafc-116">Groups and apps</span></span>](/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="8eafc-117">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="8eafc-117">Azure AD roles</span></span>](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="8eafc-118">Azure リソース ロール</span><span class="sxs-lookup"><span data-stu-id="8eafc-118">Azure resource roles</span></span>](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="8eafc-119">Azure のライセンスADを設定する</span><span class="sxs-lookup"><span data-stu-id="8eafc-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="8eafc-120">Wiht Azure AD、アクセス要求ワークフロー、アクセス割り当て、レビュー、有効期限を自動化することで、ID とアクセス ライフサイクルを大規模に管理できます。</span><span class="sxs-lookup"><span data-stu-id="8eafc-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="8eafc-121">従業員は、自分の仕事を実行するために、さまざまなグループ、アプリケーション、およびサイトにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="8eafc-122">このアクセスの管理は、要件の変更、新しいアプリケーションの追加、またはユーザーが追加のアクセス権を必要とするために困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="8eafc-123">他の組織と共同作業を行う場合、他の組織の誰が組織のリソースにアクセスする必要があるのか分からなかったり、外部のユーザーは組織が使用しているアプリケーション、グループ、またはサイトを知らない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8eafc-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="8eafc-124">Azure ADエンタイトルメント管理を使用すると、グループ、アプリケーション、および内部および外部のユーザー SharePointサイトへのアクセスを効率的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="8eafc-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="8eafc-125">詳細については、「Azure の権利管理 [の概要」AD参照してください](/azure/active-directory/governance/entitlement-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="8eafc-125">For more information, see the [overview of Azure AD entitlement management](/azure/active-directory/governance/entitlement-management-overview).</span></span>