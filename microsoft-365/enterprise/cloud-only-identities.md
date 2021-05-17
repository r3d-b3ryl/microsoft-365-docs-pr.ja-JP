---
title: Microsoft 365専用 ID
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: サブスクリプションでクラウド専用 ID を使用している場合Microsoft 365グループを作成する方法について説明します。
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327929"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="bfcfb-103">Microsoft 365専用 ID</span><span class="sxs-lookup"><span data-stu-id="bfcfb-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="bfcfb-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="bfcfb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bfcfb-105">クラウド専用 ID を使用すると、すべてのユーザー、グループ、連絡先が Azure Active Directory (Azure AD) テナントの Microsoft 365 サブスクリプションに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="bfcfb-106">クラウド専用 ID の基本的なコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-106">Here are the basic components of cloud-only identity.</span></span>
 
![クラウド専用 ID の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="bfcfb-108">組織のユーザーとユーザー アカウントは、さまざまな方法で分類できます。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="bfcfb-109">たとえば、従業員であり、永続的なステータスを持つユーザーもいます。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="bfcfb-110">一部のベンダー、請負業者、または一時的なステータスを持つパートナーがあります。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="bfcfb-111">一部のユーザー は、ユーザー アカウントを持たず、対話とコラボレーションをサポートするために特定のサービスとリソースへのアクセスを許可する必要がある外部ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="bfcfb-112">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-112">For example:</span></span>

- <span data-ttu-id="bfcfb-113">テナント アカウントは、組織内でクラウド サービスのライセンスを付与したユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="bfcfb-114">B2B (Business to Busines) アカウントは、コラボレーションへの参加のために招待された組織外部のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="bfcfb-115">組織内のユーザーの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="bfcfb-116">グループ化とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="bfcfb-116">What are the groupings?</span></span> <span data-ttu-id="bfcfb-117">たとえば、ユーザーを組織に対して高レベルの機能または目的でグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="bfcfb-p104">また、一部のクラウド サービスを、ユーザー アカウントを持たない組織外のユーザーと共有できます。この場合、このような外部ユーザーのグループも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="bfcfb-120">Azure ADグループは、クラウド環境の管理を簡素化する目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="bfcfb-121">たとえば、Azure ADを使用すると、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="bfcfb-122">グループ ベースのライセンスを使用して、Microsoft 365アカウントがメンバーとして追加されたとすぐに自動的にユーザー アカウントにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="bfcfb-123">部署名などのユーザー アカウント属性に基づいて、ユーザー アカウントを特定のグループに動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="bfcfb-124">サービスとしてのソフトウェア (SaaS) アプリケーションのユーザーを自動的にプロビジョニングし、多要素認証 (MFA) および他の条件付きアクセス ポリシーを使用してそれらのアプリケーションへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="bfcfb-125">オンライン チーム サイトに対するアクセス許可SharePointレベルをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="bfcfb-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="bfcfb-126">クラウド専用 ID の次の手順</span><span class="sxs-lookup"><span data-stu-id="bfcfb-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="bfcfb-127">ユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="bfcfb-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="bfcfb-128">ユーザー アカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bfcfb-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="bfcfb-129">グループとグループ メンバーシップの管理</span><span class="sxs-lookup"><span data-stu-id="bfcfb-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="bfcfb-130">ユーザー アカウントのパスワードを管理する</span><span class="sxs-lookup"><span data-stu-id="bfcfb-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
