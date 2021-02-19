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
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 使用、要件、およびそれらで使用できる機能を含む、分離した SharePoint Online チーム サイトについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286587"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="7cb4b-103">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="7cb4b-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7cb4b-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7cb4b-104">**Applies to**</span></span>
- [<span data-ttu-id="7cb4b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7cb4b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7cb4b-106">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="7cb4b-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="7cb4b-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7cb4b-107">SharePoint Online</span></span> 

 <span data-ttu-id="7cb4b-108">**概要:** 分離した SharePoint Online チーム サイトの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="7cb4b-p101">SharePoint Online チーム サイトは、コラボレーション用のスペースをすばやく作成する簡単な方法です。ユーザーは、Microsoft Office 365 のノート、ドキュメント、記事、予定表、およびその他のリソースで共同作業できます。SharePoint Online チーム サイトは、Microsoft 365 グループをベースとしており、グループ メンバーや組織全体の非公開セットを使用したオープンなコラボレーションを可能にする簡略化された管理モデルを備えています。既定の SharePoint Online チーム サイトでは、Microsoft 365 のグループのメンバーが他のユーザーを招待し、アクセス許可の設定を制御することが可能です。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="7cb4b-113">ただし、グループ メンバーシップによって制御されるサイト アクセスと、SharePoint 管理者によって管理される SharePoint Online のアクセス許可レベルが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="7cb4b-114">これは、分離したサイトと呼ばれ、コラボレーション、コンテンツの表示、またはサイトの管理を実行するユーザーのセットに分離されています。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="7cb4b-115">以下を対象として、分離したサイトが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="7cb4b-116">組織内での機密プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-116">A secret project within your organization.</span></span>

- <span data-ttu-id="7cb4b-117">組織にとって機密度が高い、または知的財産となる場所。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="7cb4b-118">組織によって実施された、または現在遵守されている法的措置のリソース。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="7cb4b-119">一部が重複する複数の組織間で Microsoft 365 サブスクリプションを共有するものの、ほとんどの部分は個別のビジネス エンティティとして存在する場合。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="7cb4b-120">分離したサイトの要件を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="7cb4b-121">SharePoint Online 管理者だけが、サイトの管理を実行できます。これには、サイトにアクセスし、カスタム アクセス許可を構成するためのグループ メンバーシップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="7cb4b-122">サイトのメンバーは、他のメンバーをチーム サイトに招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="7cb4b-p103">分離したサイトのメンバーではないユーザーは、サイトへのアクセスを要求できません。サイトに関連付けられているいずれかの URL にアクセスしようとすると、アクセスが拒否された Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="7cb4b-p104">一元的なアクセス制御を必要とすることと SharePoint Online 管理者によるカスタム アクセス許可とのトレードオフは、時間が経過してもサイトが分離されたままであるということです。たとえば、現在のメンバーは、意図的であれ偶然であれ、サイトのメンバーではない Microsoft 365 サブスクリプション内の他のユーザーを招待したり、他のユーザーのためにカスタムのアクセス許可を構成したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="7cb4b-127">分離したサイトは次のようにその他の機能と一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="7cb4b-128">Information Rights Management。ローカルにダウンロードしたり、組織全体で利用可能な別のサイトにアップロードしたりする場合でも、サイト上のリソースを暗号化されたままにします。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="7cb4b-129">データ損失防止。ユーザーがファイルなどのサイトのリソースを電子メールで送信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7cb4b-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="7cb4b-130">Next steps</span></span>

<span data-ttu-id="7cb4b-131">SharePoint Online チーム サイトを試用サブスクリプションで使用するには、「[Office 365 開発/テスト環境での分離した SharePoint Online チーム サイト](isolated-sharepoint-online-team-site-dev-test-environment.md)」にあるステップごとの指示を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="7cb4b-132">分離した SharePoint Online チーム サイトを実稼働に展開する準備ができたら、「[分離した SharePoint Online チーム サイトの設計](design-an-isolated-sharepoint-online-team-site.md)」にある設計に関するステップバイステップの考慮事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cb4b-132">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7cb4b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cb4b-133">Related topics</span></span>

[<span data-ttu-id="7cb4b-134">分離した SharePoint Online チーム サイトの設計</span><span class="sxs-lookup"><span data-stu-id="7cb4b-134">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="7cb4b-135">分離した SharePoint Online チーム サイトの管理</span><span class="sxs-lookup"><span data-stu-id="7cb4b-135">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="7cb4b-136">分離した SharePoint Online チーム サイトの展開</span><span class="sxs-lookup"><span data-stu-id="7cb4b-136">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
