---
title: 分離した SharePoint Online チーム サイト
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 使用、要件、およびそれらで使用できる機能を含む、分離した SharePoint Online チーム サイトについて説明します。
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819535"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="24b27-103">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="24b27-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="24b27-104">**概要:** 分離した SharePoint Online チーム サイトの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24b27-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="24b27-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="24b27-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="24b27-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span><span class="sxs-lookup"><span data-stu-id="24b27-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="24b27-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span><span class="sxs-lookup"><span data-stu-id="24b27-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="24b27-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span><span class="sxs-lookup"><span data-stu-id="24b27-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="24b27-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span><span class="sxs-lookup"><span data-stu-id="24b27-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="24b27-110">You might need an isolated site for the following:</span><span class="sxs-lookup"><span data-stu-id="24b27-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="24b27-111">組織内での機密プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="24b27-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="24b27-112">組織にとって機密度が高い、または知的財産となる場所。</span><span class="sxs-lookup"><span data-stu-id="24b27-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="24b27-113">組織によって実施された、または現在遵守されている法的措置のリソース。</span><span class="sxs-lookup"><span data-stu-id="24b27-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="24b27-114">一部が重複する複数の組織間で Microsoft 365 サブスクリプションを共有するものの、ほとんどの部分は個別のビジネス エンティティとして存在する場合。</span><span class="sxs-lookup"><span data-stu-id="24b27-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="24b27-115">分離したサイトの要件を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="24b27-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="24b27-116">SharePoint Online 管理者だけが、サイトの管理を実行できます。これには、サイトにアクセスし、カスタム アクセス許可を構成するためのグループ メンバーシップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24b27-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="24b27-117">サイトのメンバーは、他のメンバーをチーム サイトに招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="24b27-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="24b27-118">Users who are not members of the isolated site cannot request access to the site.</span><span class="sxs-lookup"><span data-stu-id="24b27-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="24b27-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span><span class="sxs-lookup"><span data-stu-id="24b27-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="24b27-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span><span class="sxs-lookup"><span data-stu-id="24b27-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="24b27-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span><span class="sxs-lookup"><span data-stu-id="24b27-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="24b27-122">分離したサイトは次のようにその他の機能と一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="24b27-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="24b27-123">Information Rights Management。ローカルにダウンロードしたり、組織全体で利用可能な別のサイトにアップロードしたりする場合でも、サイト上のリソースを暗号化されたままにします。</span><span class="sxs-lookup"><span data-stu-id="24b27-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="24b27-124">データ損失防止。ユーザーがファイルなどのサイトのリソースを電子メールで送信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="24b27-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="24b27-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="24b27-125">Next steps</span></span>

<span data-ttu-id="24b27-126">SharePoint Online チーム サイトを試用サブスクリプションで使用するには、「[Office 365 開発/テスト環境での分離した SharePoint Online チーム サイト](isolated-sharepoint-online-team-site-dev-test-environment.md)」にあるステップごとの指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24b27-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="24b27-127">分離した SharePoint Online チーム サイトを実稼働に展開する準備ができたら、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」にある設計に関するステップバイステップの考慮事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24b27-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="24b27-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="24b27-128">Related topics</span></span>

[<span data-ttu-id="24b27-129">分離した SharePoint Online チーム サイトの設計</span><span class="sxs-lookup"><span data-stu-id="24b27-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="24b27-130">分離した SharePoint Online チーム サイトの管理</span><span class="sxs-lookup"><span data-stu-id="24b27-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="24b27-131">分離した SharePoint Online チーム サイトの展開</span><span class="sxs-lookup"><span data-stu-id="24b27-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


