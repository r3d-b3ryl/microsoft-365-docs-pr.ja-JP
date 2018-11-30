---
title: '手順 15: 動的グループ メンバーシップをセットアップする'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: アカウントの属性に基づいた自動グループ メンバーシップについて理解し、構成します。
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869515"
---
# <a name="step-15-set-up-dynamic-group-membership"></a><span data-ttu-id="641ad-103">手順 15: 動的グループ メンバーシップをセットアップする</span><span class="sxs-lookup"><span data-stu-id="641ad-103">Step 15: Set up dynamic group membership</span></span>

<span data-ttu-id="641ad-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="641ad-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="641ad-p101">この手順では、ユーザー アカウントを Azure AD グループのメンバーとして自動的に追加または削除するための一連のルールを作成します。これは*動的グループ メンバーシップ* と呼ばれます。ルールはユーザー アカウントの属性 (部門や国など) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="641ad-p101">In Step 12, you'll create a series of rules that automatically add or remove user accounts as members of an Azure AD group. This is known as *dynamic group membership*. The rules are based on user account attributes, such as Department or Country.</span></span>

<span data-ttu-id="641ad-108">ルールの適用方法を次に説明します。</span><span class="sxs-lookup"><span data-stu-id="641ad-108">Here’s how the rules are applied:</span></span>

- <span data-ttu-id="641ad-109">新しいユーザー アカウントがグループのすべてのルールに一致すると、そのアカウントはメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="641ad-109">If a new user account matches all the rules for the group, it becomes a member.</span></span>
- <span data-ttu-id="641ad-110">ユーザー アカウントがグループのメンバーではないものの、その属性が変更されグループのすべてのルールに一致した場合は、そのグループのメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="641ad-110">If a user account isn’t a member of the group, but its attributes change so that it matches all the rules for the group, it becomes a member of that group.</span></span>
- <span data-ttu-id="641ad-111">ユーザー アカウントがグループのすべてのルールに一致しない場合、そのアカウントはグループに追加されません。</span><span class="sxs-lookup"><span data-stu-id="641ad-111">If a user account doesn’t match all the rules for the group, it isn’t added to the group.</span></span>
- <span data-ttu-id="641ad-112">ユーザー アカウントがグループのメンバーであるものの、その属性が変更されそのグループのすべてのルールに一致しなくなると、グループのメンバーではなくなります。</span><span class="sxs-lookup"><span data-stu-id="641ad-112">If a user account is a member of the group, but its attributes change so that it no longer matches all the rules for the group, it is removed as a member of the group.</span></span>

<span data-ttu-id="641ad-p102">動的メンバーシップを使用するには、最初に共通のユーザー アカウント属性セットを持つ一連のグループを判別します。たとえば、Sales 部門のすべてのメンバーは、ユーザー アカウントの Department 属性が「Sales」に設定されていることに基づき、Sales Azure AD グループに入れます。</span><span class="sxs-lookup"><span data-stu-id="641ad-p102">To use dynamic membership, you must first determine the sets of groups that have a common set of user account attributes. For example, all members of the Sales department should be in the Sales Azure AD group, based on the user account attribute Department set to “Sales”.</span></span>

<span data-ttu-id="641ad-115">「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641ad-115">See the [instructions to create and configure the rules for a dynamic Azure AD group](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

<span data-ttu-id="641ad-116">この手順の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="641ad-116">The results of this step are:</span></span>

- <span data-ttu-id="641ad-117">動的メンバーシップを構成できる Azure AD グループのセット</span><span class="sxs-lookup"><span data-stu-id="641ad-117">A set of Azure AD groups that can be configured for dynamic membership</span></span>
- <span data-ttu-id="641ad-118">各動的グループのルール セット</span><span class="sxs-lookup"><span data-stu-id="641ad-118">A set of rules on each dynamic group</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="641ad-120">テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化</span><span class="sxs-lookup"><span data-stu-id="641ad-120">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="641ad-121">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-dyn-groups)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="641ad-121">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-dyn-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="641ad-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="641ad-122">Next step</span></span>

[<span data-ttu-id="641ad-123">ID インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="641ad-123">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)
