---
title: '手順 2: 特権 ID をセキュリティで保護する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 管理者アカウントについて理解し、管理者アカウントが最大限に保護されるよう構成します。
ms.openlocfilehash: 0be82fc6f431001c69e79a0a26007c54a87424c3
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353089"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="272d1-103">手順 2: 特権 ID をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="272d1-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="272d1-104">グローバル管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="272d1-104">Protect global administrator accounts</span></span>

<span data-ttu-id="272d1-105">*これは必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="272d1-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="272d1-106">このセクションでは、管理者アカウントを可能な限り保護することで、組織へのデジタル攻撃を防止できます。</span><span class="sxs-lookup"><span data-stu-id="272d1-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="272d1-107">そのためには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="272d1-107">To do this, you must:</span></span>

- <span data-ttu-id="272d1-108">非常に[強力なパスワード](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)を設定した全体管理者専用アカウントを作成し、必要な状況でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="272d1-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="272d1-109">必要に応じて特定の管理者ロール (Exchange 管理者やパスワード管理者など) を IT 担当員のユーザー アカウントに割り当て、日常的な管理を行います。</span><span class="sxs-lookup"><span data-stu-id="272d1-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="272d1-110">専用の全体管理者アカウントに対し、次の操作を実行する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="272d1-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="272d1-p102">テスト ユーザー アカウントを使用して、ユーザー アカウント別または条件付きアクセスに基づく多要素認証 (MFA) 設定をテストし、MFA が予期されているとおりに正しく機能することを確認します。MFA は、セカンダリ認証方式 (スマートフォンに送信される確認コードなど) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="272d1-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="272d1-p103">専用の Office 365 全体管理者アカウントごとに MFA を構成し、組織で使用可能なセカンダリ認証のうち最も強力な認証を使用します。詳細については、「[多要素認証をセットアップする](identity-multi-factor-authentication.md#identity-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) for more information.</span></span>
2. <span data-ttu-id="272d1-p104">条件付きアクセス ポリシーを使用して、全体管理者アカウントに対して MFA を要求します。詳細については、「[Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts)」 (管理者アカウントの保護) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="272d1-117">構成の詳細については、「[Office 365 グローバル管理者アカウントの保護](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-117">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="272d1-p105">組織では、サイバー攻撃などの緊急事態に備えた対策として、全体管理者などの特権アカウントを作成するときにはクラウド専用 ID を使用してください。詳細については、「[Azure AD で緊急アクセス用管理者アカウントを管理する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-p105">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="272d1-120">このセクションの手順を実行すると次のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="272d1-120">The results of this section are:</span></span>

- <span data-ttu-id="272d1-121">グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、新しい専用のグローバル管理者アカウント セットとなります。</span><span class="sxs-lookup"><span data-stu-id="272d1-121">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="272d1-122">これを確認するには、次の Azure Active Directory PowerShell for Graph コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="272d1-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="272d1-123">サブスクリプションを管理するその他の通常のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="272d1-123">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="272d1-124">Azure Active Directory PowerShell for Graph モジュールのインストールとサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="272d1-126">テスト ラボ ガイド: 全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="272d1-126">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="272d1-127">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-global-admin)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="272d1-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="272d1-128">オンデマンド グローバル管理者をセットアップする</span><span class="sxs-lookup"><span data-stu-id="272d1-128">Set up on-demand global administrators</span></span>

<span data-ttu-id="272d1-129">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="272d1-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="272d1-130">このセクションでは、グローバル管理者アカウントが悪意のあるユーザーによる攻撃を受けやすい時間を短縮するために Azure AD Privileged Identity Management (PIM) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="272d1-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="272d1-131">PIM では、必要なときに必要なだけ全体管理者ロールをオンデマンドで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="272d1-131">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="272d1-p108">全体管理者アカウントは永続的な管理者になるのではなく、対象の管理者になります。全体管理者ロールは、だれかに必要とされるまで非アクティブとなります。その後、アクティブ化プロセスを完了し、一定の時間、全体管理者アカウントに全体管理者ロールを追加します。この時間が経過すると、PIM で全体管理者アカウントから全体管理者ロールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="272d1-p108">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="272d1-p109">PIM は、Microsoft 365 Enterprise E5 に含まれる、Azure Active Directory Premium P2 で利用可能です。あるいは、全体管理者アカウントに対して個々の Azure Active Directory Premium P2 ライセンスを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="272d1-p109">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="272d1-138">Azure AD テナントと全体管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-138">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="272d1-139">サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="272d1-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="272d1-140">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pim)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="272d1-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="272d1-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="272d1-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="272d1-142">ハイブリッド ID の構成</span><span class="sxs-lookup"><span data-stu-id="272d1-142">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

