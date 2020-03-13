---
title: '手順 1: グローバル管理者アカウントを作成して保護する'
f1.keywords:
- NOCSH
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
description: グローバル管理者アカウントには、資格情報の侵害から保護できるように特別な対処が必要です。
ms.openlocfilehash: 27b76671581ebd2dac32304752a85f8a6f60ac98
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544036"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="8f61e-103">手順 1: グローバル管理者アカウントを作成して保護する</span><span class="sxs-lookup"><span data-stu-id="8f61e-103">Step 1: Create and protect your global admin accounts</span></span>

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="8f61e-105">グローバル管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="8f61e-105">Protect global administrator accounts</span></span>

<span data-ttu-id="8f61e-106">*これは必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*</span><span class="sxs-lookup"><span data-stu-id="8f61e-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8f61e-107">このセクションでは、管理者アカウントを可能な限り保護することで、組織へのデジタル攻撃を防止できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="8f61e-108">そのためには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-108">To do this, you must:</span></span>

- <span data-ttu-id="8f61e-109">[強力なパスワード](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)を設定したグローバル管理者専用アカウントを 1 つ以上作成し、必要な状況でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="8f61e-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="8f61e-110">必要に応じて特定の管理者ロール (Exchange 管理者やパスワード管理者など) をこのロール専用の他のアカウントや IT 担当員のユーザー アカウントに割り当て、日常的な管理を行います。</span><span class="sxs-lookup"><span data-stu-id="8f61e-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="8f61e-111">専用のグローバル管理者アカウントに対し、次の操作を実行する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="8f61e-112">テスト ユーザー アカウントを使用して、ユーザー アカウント別または条件付きアクセスに基づく Azure 多要素認証 (MFA) 設定をテストし、MFA が予期されているとおりに正しく機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f61e-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="8f61e-113">MFA には、スマートフォンに送信される確認コードなど、セカンダリ認証方式が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f61e-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="8f61e-114">MFA を必要とするグローバル管理者アカウントに対して条件付きアクセスポリシーを作成して有効にし、組織で利用可能な最も強力なセカンダリ認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f61e-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="8f61e-115">詳細については、「[Azure 多要素認証](identity-access-prerequisites.md#protecting-administrator-accounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="8f61e-116">追加の保護機能については、「[Office 365 グローバル管理者アカウントを保護する](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="8f61e-117">サイバー攻撃のような緊急時の非常事態に対する緊急アカウントは、クラウド専用アカウントになります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="8f61e-118">また、クラウド専用ではない (対象または永続的な) グローバル管理者アカウントを所有している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="8f61e-119">詳細については、「[Azure AD で緊急アクセス用管理者アカウントを管理する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="8f61e-120">このセクションの結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f61e-120">The results of this section are:</span></span>

- <span data-ttu-id="8f61e-121">グローバル管理者ロールを持つ、サブスクリプションのユーザー アカウントのみが、専用のグローバル管理者アカウントとなります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="8f61e-122">これを確認するには、次の Azure Active Directory PowerShell for Graph コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f61e-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="8f61e-123">サブスクリプションサービスを管理するその他のユーザー アカウントには、各自の職務に関連する管理ロールが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="8f61e-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="8f61e-124">Azure Active Directory PowerShell for Graph モジュールのインストールとサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="8f61e-126">テスト ラボ環境でこの構成の実習を行うには、「[グローバル管理者アカウントを保護する テスト ラボ ガイド](protect-global-administrator-accounts-microsoft-365-test-environment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="8f61e-127">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-global-admin)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="8f61e-128">オンデマンドの管理者を設定する</span><span class="sxs-lookup"><span data-stu-id="8f61e-128">Set up on-demand administrators</span></span>

<span data-ttu-id="8f61e-129">*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*</span><span class="sxs-lookup"><span data-stu-id="8f61e-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8f61e-130">このセクションでは、管理者アカウントが悪意のあるユーザーによる攻撃を受けやすい時間を短縮するために Azure AD Privileged Identity Management (PIM) をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="8f61e-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="8f61e-131">PIM では、必要なときに必要なだけ管理者ロールをオンデマンドで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="8f61e-132">管理者アカウントは永続的な管理者ではなく、対象管理者となります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="8f61e-133">管理者ロールは、誰かが必要とするまで非アクティブとなります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="8f61e-134">ライセンス認証プロセスを実行すると、特定の期間、管理者ロールが管理者アカウントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="8f61e-135">期限を過ぎると、PIM によって管理者アカウントから管理者ロールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="8f61e-136">PIM は、Microsoft 365 E5 に含まれている Azure Active Directory Premium P2 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="8f61e-137">または、管理者アカウントの Azure Active Directory Premium P2 ライセンスを個別に購入できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="8f61e-138">Azure AD テナントと管理者アカウントに対して Azure PIM を有効にする場合は、[PIM の構成手順](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="8f61e-139">サイバー攻撃者から特権アクセスをセキュリティで保護する包括的なロードマップを作成する場合は、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="8f61e-140">中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-pim)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="8f61e-141">特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="8f61e-141">Privileged access management</span></span>

<span data-ttu-id="8f61e-p109">特権アクセス管理は、Office 365 テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、Office 365 テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="8f61e-p110">この手順では、Office 365 テナントの特権アクセス管理を有効にして、組織の Office 365 データおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。Office 365 組織の特権アクセスは、次の 3 つの基本的な手順で開始します。</span><span class="sxs-lookup"><span data-stu-id="8f61e-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="8f61e-147">承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="8f61e-147">Creating an approver's group</span></span>
- <span data-ttu-id="8f61e-148">特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="8f61e-148">Enabling privileged access</span></span>
- <span data-ttu-id="8f61e-149">承認ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8f61e-149">Creating approval policies</span></span>

<span data-ttu-id="8f61e-p111">構成が完了すると、特権アクセス管理によって、継続的な特権なしで運用できるようになり、継続的な管理アクセスが原因で発生する脆弱性に対抗する防御層が得られます。定義済みの承認ポリシーが関連付けられているタスクを特権アクセスで実行するには、承認が必要になります。承認ポリシーに含まれているタスクの実行を必要とするユーザーは、そのポリシーで定義されているタスクの実行に必要なアクセス許可を得るために、アクセス承認を要求して承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f61e-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="8f61e-153">Office 365 の特権アクセス管理を有効にするには、「[Office 365 の特権アクセス管理を構成する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="8f61e-154">詳細については、「[Office 365 の特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="8f61e-156">テスト ラボ環境でこの構成の実習を行うには、「[特権アクセス管理テスト ラボ ガイド](privileged-access-microsoft-365-enterprise-dev-test-environment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f61e-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="8f61e-157">中間チェックポイントとして、この手順に対応する[終了条件](identity-exit-criteria.md#crit-identity-pam)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f61e-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8f61e-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="8f61e-158">Next step</span></span>

|||
|:-------|:-----|
|![手順 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="8f61e-160">パスワードをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="8f61e-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

