---
title: '手順 12: 自動ライセンスをセットアップする'
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
description: Azure AD グループのグループベースのライセンスについて理解し、構成します。
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868981"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="5d066-103">手順 12: 自動ライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5d066-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="5d066-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="5d066-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5d066-p101">この手順では、一連のサブスクリプションのライセンスをグループのすべてのメンバーに自動的に割り当てるため、Azure AD でセキュリティ グループを構成します。これは*グループベースのライセンス* と呼ばれます。グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="5d066-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="5d066-108">Microsoft 365 Enterprise では、次の両方のライセンスを割り当てる Azure AD セキュリティ グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d066-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="5d066-109">Office 365 Enterprise E3 または E5</span><span class="sxs-lookup"><span data-stu-id="5d066-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="5d066-110">Enterprise Mobility + Security (EMS) E3 または E5</span><span class="sxs-lookup"><span data-stu-id="5d066-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="5d066-p102">手順 2 で指定したグループを使用して、グループ内のすべてのユーザーに Office 365 と EMS の両方のライセンスが割り当てられている必要があるアカウントのリストが含まれているグループを検索します。すべてのグループ メンバーに割り当てることができる十分な数のライセンスがあることを確認します。ライセンスが不足すると、ライセンスが使用可能になるまで、新しいユーザーにライセンスが割り当てらません。</span><span class="sxs-lookup"><span data-stu-id="5d066-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="5d066-114">Azure B2B (企業間) アカウントが含まれているグループに対しては*グループベースのライセンス*を構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="5d066-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="5d066-115">「[Azure Active Directory のグループベースのライセンスの基礎](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)」にある追加情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d066-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="5d066-116">「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d066-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="5d066-117">この手順の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5d066-117">The results of this step are:</span></span>

- <span data-ttu-id="5d066-118">グループベースのライセンスに適したセキュリティ グループを特定している。</span><span class="sxs-lookup"><span data-stu-id="5d066-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="5d066-119">グループベースのライセンスに対応してこれらのグループを構成している。</span><span class="sxs-lookup"><span data-stu-id="5d066-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5d066-121">テスト ラボ ガイド: ライセンスとグループのメンバーシップの自動化</span><span class="sxs-lookup"><span data-stu-id="5d066-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5d066-122">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-group-license)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5d066-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5d066-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="5d066-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="5d066-124">テナントとサインイン アクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="5d066-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

