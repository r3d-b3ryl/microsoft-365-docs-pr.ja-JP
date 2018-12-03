---
title: '手順 14: ユーザーが各自のグループを作成および管理できるようにする'
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
description: Azure AD のセルフ サービスによるグループ管理について理解し、構成します。
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869328"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a><span data-ttu-id="5565e-103">手順 14: ユーザーが各自のグループを作成および管理できるようにする</span><span class="sxs-lookup"><span data-stu-id="5565e-103">Step 14: Allow users to create and manage their own groups</span></span>

<span data-ttu-id="5565e-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="5565e-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5565e-p101">この手順では、IT 管理者ではなくグループの所有者が管理できる Azure Active Directory (AD) グループを指定します。*セルフ サービスによるグループ管理*と呼ばれるこの機能では、管理者ロールが割り当てられていないグループ所有者がセキュリティ グループを作成および管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5565e-p101">In Step 14, you'll identify Azure Active Directory (AD) groups that can be managed by group owners instead of IT administrators. Known as *self-service group management*, this feature allows group owners who are not assigned an administrative role to create and manage security groups.</span></span> 

<span data-ttu-id="5565e-p102">ユーザーがセキュリティ グループのメンバーシップを要求できます。この要求は IT 管理者ではなくグループ所有者に送られます。これにより、グループ メンバーシップの日常的な管理が、業務でのグループの用途を理解してグループのメンバーシップを管理できるチーム所有者、プロジェクト所有者、またはビジネス所有者に委任されます。</span><span class="sxs-lookup"><span data-stu-id="5565e-p102">Users can request membership in a security group and that request goes to the group owner, rather than an IT administrator. This allows the day-to-day control of group membership to be delegated to team, project, or business owners who understand the business use for the group and can manage its membership.</span></span>

>[!Note]
><span data-ttu-id="5565e-p103">セルフサービスによるグループ管理は、Azure AD セキュリティと Office 365 のグループでのみ使用できます。メール対応グループ、配布リスト、またはオンプレミス Windows Server Active Directory (AD) から同期されているグループには使用できません。</span><span class="sxs-lookup"><span data-stu-id="5565e-p103">Self-service group management is available only for Azure AD security and Office 365 groups. It is not available for mail-enabled groups, distribution lists, or any group that has been synchronized from your on-premises Windows Server Active Directory (AD).</span></span>
>

<span data-ttu-id="5565e-111">詳細については、「[セルフサービス グループ管理に必要な Azure Active Directory の設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5565e-111">For more information, see the [instructions to configure an Azure AD group for self-service management](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).</span></span>

<span data-ttu-id="5565e-112">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-self-service-groups)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5565e-112">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-self-service-groups) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5565e-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="5565e-113">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="5565e-114">動的グループ メンバーシップをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5565e-114">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |
