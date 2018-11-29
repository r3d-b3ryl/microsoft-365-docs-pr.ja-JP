---
title: 'フェーズ 2: ID インフラストラクチャの終了条件'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が Microsoft 365 Enterprise の ID ベースのサービスとインフラストラクチャの条件を満たしていることを確認します。
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869603"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="4886e-103">フェーズ 2: ID インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="4886e-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4886e-p101">フェーズ 3 に進む前に、ID インフラストラクチャが次の条件を満たしていることを確認してください。また、ID インフラストラクチャのその他の推奨事項については、「[必要条件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4886e-p101">Before you move on to Phase 3, make sure that your identity infrastructure meets these conditions. Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="4886e-106">必須: すべてのユーザー、グループ、およびグループ メンバーシップが作成されている</span><span class="sxs-lookup"><span data-stu-id="4886e-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="4886e-107">次の目的でユーザー アカウントとグループを作成しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="4886e-108">組織内の従業員、ベンダー、契約社員、または組織で勤務または組織に協力するパートナーが、Azure Active Directory (AD) で対応するユーザー アカウントを持っている。</span><span class="sxs-lookup"><span data-stu-id="4886e-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (AD).</span></span>
- <span data-ttu-id="4886e-109">Azure AD のグループとそのメンバーに、さまざまな目的 (Microsoft クラウド サービスのセキュリティ設定のプロビジョニング、自動ライセンスなど) でユーザー アカウントとその他のグループが含まれている。</span><span class="sxs-lookup"><span data-stu-id="4886e-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="4886e-110">必要に応じて、[手順 1](identity-plan-users-groups.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="4886e-111">必須: ユーザーとグループが Azure AD と同期される</span><span class="sxs-lookup"><span data-stu-id="4886e-111">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="4886e-112">既存のオンプレミス ID プロバイダー (Windows Server Active Directory (AD) など) がある場合は、Azure AD Connect を使用して、オンプレミス ID プロバイダーから Azure AD テナントへユーザー アカウントとグループを同期しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-112">If you have an existing on-premises identity provider, such as Windows Server Active Directory (AD), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="4886e-113">ディレクトリ同期により、ユーザーは各自のコンピューターやオンプレミス リソースにサインインするときに使用する資格情報で、Office 365 やその他の Microsoft クラウド サービスにもサインインできます。</span><span class="sxs-lookup"><span data-stu-id="4886e-113">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="4886e-114">必要に応じて、[手順 7](identity-azure-ad-connect.md) がこの必須条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-114">If needed, [Step 7](identity-azure-ad-connect.md) can help you meet this requirement.</span></span>

<span data-ttu-id="4886e-115">この必須条件を省略した場合、ユーザー アカウントとグループの 2 つのセットが作成されています。</span><span class="sxs-lookup"><span data-stu-id="4886e-115">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="4886e-116">オンプレミス ID プロバイダーに存在するユーザー アカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="4886e-116">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="4886e-117">Azure AD テナントに存在するユーザー アカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="4886e-117">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="4886e-p102">この状態では、IT 管理者とユーザーが、ユーザー アカウントとグループの 2 つのセットを手動で保守する必要があります。このため、アカウント、パスワード、グループが同期されていない状況が必然的に発生します。</span><span class="sxs-lookup"><span data-stu-id="4886e-p102">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-120">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-120">How to test</span></span>
<span data-ttu-id="4886e-121">オンプレミスの資格情報を使用した認証が正しく機能することを確認するには、オンプレミスの資格情報を使用して Office 365 ポータルにログインします。</span><span class="sxs-lookup"><span data-stu-id="4886e-121">To verify that authentication with on-premises credentials works correctly, sign in to the Office 365 portal with your on-premises credentials.</span></span>

<span data-ttu-id="4886e-122">ディレクトリ同期が正しく動作していることを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4886e-122">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="4886e-123">Windows Server AD で新しいテスト グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-123">Create a new test group in Windows Server AD.</span></span>
2.  <span data-ttu-id="4886e-124">同期時刻まで待ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-124">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="4886e-125">Azure AD テナントを調べ、新しいテスト グループ名があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4886e-125">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="4886e-126">必須: 全体管理者アカウントが保護されている</span><span class="sxs-lookup"><span data-stu-id="4886e-126">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="4886e-127">Office 365 サブスクリプションの侵害の原因となる資格情報の侵害を防ぐため、[Office 365 全体管理者アカウントを保護しています](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560)。</span><span class="sxs-lookup"><span data-stu-id="4886e-127">You've [protected your Office 365 global administrator accounts](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="4886e-128">この必須条件を省略した場合、全体管理者アカウントが攻撃および侵害を受けやすくなり、攻撃者は獲得攻撃、破壊、または身代金要求の目的で、システム全体でデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4886e-128">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="4886e-129">必要に応じて、[手順 2](identity-designate-protect-admin-accounts.md) がこの必須条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-129">If needed, [Step 2](identity-designate-protect-admin-accounts.md) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-130">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-130">How to test</span></span>

<span data-ttu-id="4886e-131">全体管理者アカウントを保護していることを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4886e-131">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="4886e-p103">PowerShell コマンド プロンプトで次の Azure AD V2 コマンドを実行します。専用の全体管理者アカウントだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4886e-p103">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="4886e-p104">手順 1 で表示された各アカウントを使用して Office 365 にサインインします。各サインインには多要素認証と、組織で使用可能なセカンダリ認証のうち最も強力なセカンダリ認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="4886e-p104">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="4886e-136">Azure AD V2 PowerShell モジュールのインストールと Office 365 へのサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4886e-136">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in to Office 365.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="4886e-137">オプション: Office 365 のサインイン画面を組織に合わせてカスタマイズしている</span><span class="sxs-lookup"><span data-stu-id="4886e-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="4886e-138">「[クイック スタート: Azure AD のサインイン ページに会社のブランドを追加する](http://aka.ms/aadpaddbranding)」に従って組織のブランドを Office 365 サインイン ページに追加しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="4886e-139">このオプション条件を省略した場合、ユーザーに対して汎用 Office 365 サインイン画面が表示され、ユーザーが当該組織のサイトにサインインすることを確信できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4886e-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="4886e-140">必要に応じて、[手順 11](identity-customize-office-365-sign-in.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-140">If needed, [Step 11](identity-customize-office-365-sign-in.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-141">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-141">How to test</span></span>

<span data-ttu-id="4886e-p105">アカウント名と多要素認証を使用して Office 365 ポータルにサインインします。カスタム ブランド要素がサインイン ページに表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="4886e-p105">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="4886e-144">オプション: ユーザーに対して多要素認証が有効になっている</span><span class="sxs-lookup"><span data-stu-id="4886e-144">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="4886e-145">「[Office 365 展開用の多要素認証の計画](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)」と「[Office 365 ユーザー用の多要素認証を設定する](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)」に従い、ユーザー アカウントに対して多要素認証 (MFA) を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="4886e-145">You used [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) and [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="4886e-p106">このオプション条件を省略した場合、ユーザー アカウントはサイバー攻撃による資格情報の侵害に対して脆弱になります。ユーザー アカウントのパスワードが侵害されると、そのアカウントのすべてのリソースと機能 (管理者ロールなど) を攻撃者が利用できるようになります。これにより、攻撃者は内部資料やその他のデータを複製、破壊、または身代金要求目的で保持することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="4886e-p106">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="4886e-149">必要に応じて、[手順 5](identity-multi-factor-authentication.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-149">If needed, [Step 5](identity-multi-factor-authentication.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-150">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-150">How to test</span></span>

1.  <span data-ttu-id="4886e-151">Office 365 Admin ポータルでテスト ユーザー アカウントを作成し、ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4886e-151">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="4886e-152">実際のユーザー アカウントに使用している追加の検証方式 (電話へのメッセージの送信など) を使用して、テスト ユーザー アカウントの多要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-152">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="4886e-153">テスト ユーザー アカウントを使用して Office 365 または Azure Portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4886e-153">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="4886e-154">MFA により、追加の確認情報を入力するように求められ、その結果認証が正常に完了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4886e-154">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="4886e-155">テスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4886e-155">Delete the test user account.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="4886e-156">オプション: ディレクトリ同期を監視している</span><span class="sxs-lookup"><span data-stu-id="4886e-156">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="4886e-157">「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」(パスワード同期の場合) または「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」(フェデレーテッド認証の場合) に従い、Azure AD Connect Health を展開しています。この展開では次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="4886e-157">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="4886e-158">オンプレミスの各 ID サーバーに Azure AD Connect Health エージェントをインストールする。</span><span class="sxs-lookup"><span data-stu-id="4886e-158">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="4886e-159">Azure AD Connect Health ポータルを使用して、継続的な同期の状態を監視する。</span><span class="sxs-lookup"><span data-stu-id="4886e-159">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="4886e-160">このオプション条件を省略した場合、クラウドベースの ID インフラストラクチャの状態をより正確に評価できます。</span><span class="sxs-lookup"><span data-stu-id="4886e-160">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="4886e-161">必要に応じて、[手順 8](identity-azure-ad-connect-health.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-161">If needed, [Step 8](identity-azure-ad-connect-health.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-162">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-162">How to test</span></span>
<span data-ttu-id="4886e-163">Azure AD Connect Health ポータルには、オンプレミス ID サーバーと継続的な同期の正確な最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4886e-163">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="4886e-164">オプション: ユーザーが各自のパスワードをリセットできる</span><span class="sxs-lookup"><span data-stu-id="4886e-164">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="4886e-165">「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」に従って、ユーザーのパスワード リセットを構成しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-165">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="4886e-166">この条件を満たしていない場合は、ユーザーはパスワードをリセットする際にユーザー アカウント管理者に依頼する必要があるため、追加の ID 管理オーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="4886e-166">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="4886e-167">必要に応じて、[手順 4](identity-password-reset.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-167">If needed, [Step 4](identity-password-reset.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-168">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-168">How to test</span></span>

1. <span data-ttu-id="4886e-169">テスト ユーザー アカウントを作成し、初期パスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="4886e-169">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="4886e-170">「[Office 365 でユーザーが自分のパスワードを再設定する](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a)」の手順に従って、テスト ユーザー アカウントのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4886e-170">Use the steps in [Let users reset their own passwords in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="4886e-171">サインアウトし、リセット後のパスワードを使用してテスト ユーザー アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4886e-171">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="4886e-172">テスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4886e-172">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="4886e-173">オプション: ユーザーに対してパスワードの書き戻しが有効になっている</span><span class="sxs-lookup"><span data-stu-id="4886e-173">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="4886e-174">「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」の手順に従い、Microsoft 365 Enterprise サブスクリプションの Azure AD テナントのパスワードの書き戻しを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="4886e-174">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="4886e-175">このオプション条件を省略した場合、オンプレミスのネットワークに接続していないユーザーは、IT 管理者を通じて Windows Server AD のパスワードをリセットまたはロック解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4886e-175">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their Windows Server AD passwords through an IT administrator.</span></span>

<span data-ttu-id="4886e-176">必要に応じて、[手順 9](identity-password-writeback.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-176">If needed, [Step 9](identity-password-writeback.md) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="4886e-177">パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生するリスクが高いことが Azure AD により検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="4886e-177">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="4886e-178">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-178">How to test</span></span>

<span data-ttu-id="4886e-p107">パスワードの書き戻しをテストするには、Office 365 でパスワードを変更します。各自のアカウントと新しいパスワードを使用して、オンプレミスの Windows Server AD リソースにアクセスできるはずです。</span><span class="sxs-lookup"><span data-stu-id="4886e-p107">You test password writeback by changing your password in Office 365. You should be able to use your account and new password to access on-premises Windows Server AD resources.</span></span>

1. <span data-ttu-id="4886e-181">オンプレミスの Windows Server AD にテスト ユーザー アカウントを作成し、ディレクトリ同期を許可し、Office 365 管理ポータルで Office 365 ライセンスをこのテスト ユーザー アカウントに付与します。</span><span class="sxs-lookup"><span data-stu-id="4886e-181">Create a test user account in your on-premises Windows Server AD, allow directory synchronization to occur, and then grant it an Office 365 license in the Office 365 admin portal.</span></span>
2. <span data-ttu-id="4886e-182">オンプレミスの Windows Server AD ドメインに参加しているリモート コンピューターから、テスト ユーザー アカウントの資格情報を使用してコンピューターと Office 365 ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4886e-182">From a remote computer that is joined to your on-premises Windows Server AD domain, sign in to the computer and the Office 365 portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="4886e-183">**[設定] > [Office 365 の設定] > [パスワード] > [パスワードの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4886e-183">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="4886e-184">現在のパスワードを入力し、新しいパスワードを入力し、確認のため新しいパスワードをもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="4886e-184">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="4886e-p108">Office 365 ポータルとリモート コンピューターからサインアウトし、テスト ユーザー アカウントと新しいパスワードを使用してコンピューターにサインインします。これにより、Azure AD テナントを使用して、オンプレミス Windows Server AD ユーザー アカウントのパスワードを変更できたことが証明されます。</span><span class="sxs-lookup"><span data-stu-id="4886e-p108">Sign out of the Office 365 portal and the remote computer and then sign in to the computer using the test user account and its new password. This proves that you were able to change the password of an on-premises Windows Server AD user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a><span data-ttu-id="4886e-187">オプション: ユーザーはシングル サインオンを使用してサインインできる</span><span class="sxs-lookup"><span data-stu-id="4886e-187">Optional: Users can sign in using single sign-on</span></span>

<span data-ttu-id="4886e-188">クラウドベースのアプリケーション (Office 365 など) へのユーザーのサインイン方法を組織が簡素化できるように、[Azure AD Connect: シームレス シングル サインオン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="4886e-188">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="4886e-189">このオプション条件を省略した場合、Azure AD を使用するその他のアプリケーションにユーザーがアクセスすると、ユーザーに対して資格情報の入力が求められることがあります。</span><span class="sxs-lookup"><span data-stu-id="4886e-189">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="4886e-190">必要に応じて、[手順 10](identity-single-sign-on.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-190">If needed, [Step 10](identity-single-sign-on.md) can help you with this option.</span></span>


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="4886e-191">オプション: グループ メンバーシップに基づいてユーザー アカウントに対しライセンスを自動的に割り当てるか削除するグループベースのライセンス</span><span class="sxs-lookup"><span data-stu-id="4886e-191">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="4886e-192">Office 365 と EMS の両方のライセンスの割り当てと削除が自動的に実行されるようにするため、適切な Azure AD セキュリティ グループに対して[グループベースのライセンスを有効にしています](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="4886e-192">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="4886e-193">このオプション条件を省略した場合、次の操作を手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4886e-193">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="4886e-194">Office 365 および EMS へのアクセス権を付与する予定の新しいユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="4886e-194">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="4886e-195">組織に所属していないユーザーや、Office 365 および EMS へのアクセス権がないユーザーからライセンスを削除する。</span><span class="sxs-lookup"><span data-stu-id="4886e-195">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="4886e-196">必要に応じて、[手順 12](identity-group-based-licensing.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-196">If needed, [Step 12](identity-group-based-licensing.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-197">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-197">How to test</span></span>

1. <span data-ttu-id="4886e-198">Azure Portal を使用して Azure AD にテスト セキュリティ グループを作成し、Office 365 と EMS のライセンスを割り当てるグループベースのライセンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-198">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="4886e-199">Azure AD にテスト ユーザー アカウントを作成し、テスト セキュリティ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="4886e-199">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="4886e-200">Office 365 管理ポータルでこのユーザー アカウントのプロパティを調べ、このアカウントに Office 365 と EMS のライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4886e-200">Examine the properties of the user account in the Office 365 admin portal to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="4886e-201">テスト セキュリティ グループからテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4886e-201">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="4886e-202">このユーザー アカウントのプロパティを調べ、このアカウントに Office 365 と EMS のライセンスが割り当てられていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4886e-202">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="4886e-203">テスト セキュリティ グループとテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4886e-203">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="4886e-204">オプション: 動的グループ メンバーシップの設定により、ユーザー アカウントの属性に基づいてユーザー アカウントがグループに自動的に追加される</span><span class="sxs-lookup"><span data-stu-id="4886e-204">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="4886e-205">Azure AD の動的グループを決定し、「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」の手順に従って、グループを作成し、グループ メンバーシップのユーザー アカウント属性と値を指定するルールを作成しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-205">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="4886e-p109">このオプション条件を省略した場合、新しいアカウントが追加されるか、またはユーザー アカウントの属性が時間の経過に伴って変化するときに、グループ メンバーシップを手動で設定する必要があります。たとえば、Sales 部門から Accounting 部門にユーザーが移動した場合、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4886e-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="4886e-208">ユーザーの Departement 属性の値を更新する。</span><span class="sxs-lookup"><span data-stu-id="4886e-208">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="4886e-209">Sales グループからユーザーを手動で削除する。</span><span class="sxs-lookup"><span data-stu-id="4886e-209">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="4886e-210">Accounting グループにユーザーを手動で追加する。</span><span class="sxs-lookup"><span data-stu-id="4886e-210">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="4886e-211">Sales グループと Accounting グループが動的グループである場合は、必要な操作はユーザー アカウントの Department の値の変更だけです。</span><span class="sxs-lookup"><span data-stu-id="4886e-211">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="4886e-212">必要に応じて、[手順 15](identity-automatic-group-membership.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-212">If needed, [Step 15](identity-automatic-group-membership.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-213">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-213">How to test</span></span>

1. <span data-ttu-id="4886e-214">Azure Portal で Azure AD にテスト用の動的グループを作成し、Department が「test 1」であるというルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-214">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="4886e-215">Azure AD でテスト ユーザー アカウントを作成し、Department プロパティに「test1」を設定します。</span><span class="sxs-lookup"><span data-stu-id="4886e-215">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="4886e-216">テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4886e-216">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="4886e-217">テスト ユーザー アカウントの Department プロパティの値を「test2」に変更します。</span><span class="sxs-lookup"><span data-stu-id="4886e-217">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="4886e-218">テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーではないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4886e-218">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="4886e-219">テスト用の動的グループとテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4886e-219">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="4886e-220">オプション: 特定の Azure AD セキュリティと Office 365 グループでセルフサービスによるグループの管理が有効になっている</span><span class="sxs-lookup"><span data-stu-id="4886e-220">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="4886e-221">セルフサービスによる管理に適しているグループを判別し、各グループの所有者に対してグループ管理のワークフローと責任を説明し、これらのグループに対して[Azure AD でのセルフサービスによる管理をセットアップ](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-221">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="4886e-222">このオプション条件を省略した場合、IT 管理者がすべての Azure AD グループ管理タスクを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4886e-222">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="4886e-223">必要に応じて、[手順 14](identity-self-service-group-management.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-223">If needed, [Step 14](identity-self-service-group-management.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="4886e-224">テスト方法</span><span class="sxs-lookup"><span data-stu-id="4886e-224">How to test</span></span>
1.  <span data-ttu-id="4886e-225">Azure Portal で Azure AD にテスト ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-225">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="4886e-226">テスト ユーザー アカウントとしてサインインし、テスト Azure AD セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-226">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="4886e-227">サインアウトして、IT 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="4886e-227">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="4886e-228">テスト セキュリティ グループで、テスト ユーザー アカウントをセルフサービスにより管理するように構成します。</span><span class="sxs-lookup"><span data-stu-id="4886e-228">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="4886e-229">サインアウトし、テスト ユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="4886e-229">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="4886e-230">Azure Portal を使用して、テスト セキュリティ グループにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4886e-230">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="4886e-231">テスト セキュリティ グループとテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4886e-231">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="4886e-232">オプション: 資格情報を侵害から保護するため、Azure AD Identity Protection が有効になっている</span><span class="sxs-lookup"><span data-stu-id="4886e-232">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="4886e-233">次の目的で Azure AD Identity Protection を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="4886e-233">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="4886e-234">潜在的な ID の脆弱性に対処する。</span><span class="sxs-lookup"><span data-stu-id="4886e-234">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="4886e-235">資格情報の侵害の疑いがあるものを検出する。</span><span class="sxs-lookup"><span data-stu-id="4886e-235">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="4886e-236">発生している不審な ID インシデントを調査して対処する。</span><span class="sxs-lookup"><span data-stu-id="4886e-236">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="4886e-p110">このオプション条件を省略した場合、資格情報の侵害を試みる操作の検出または自動的な防止、ID 関連のセキュリティ インシデントの調査を実行できません。その結果、資格情報の侵害に対して組織が脆弱になり、組織の機密データに対する脅威が生じます。</span><span class="sxs-lookup"><span data-stu-id="4886e-p110">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="4886e-239">必要に応じて、[手順 6](identity-azure-ad-identity-protection.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-239">If needed, [Step 6](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="4886e-240">オプション: 全体管理者ロールをオンデマンドで割り当てることができるように、Privileged Identity Management をセットアップしている</span><span class="sxs-lookup"><span data-stu-id="4886e-240">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="4886e-241">「[Azure AD Privileged Identity Management とは](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」の手順に従い Azure AD テナントで PIM を有効にしており、全体管理者アカウントを適格な管理者として構成しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-241">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="4886e-242">また、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」の推奨事項に従って、サイバー攻撃者から特権アクセスを保護するロードマップを策定しています。</span><span class="sxs-lookup"><span data-stu-id="4886e-242">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="4886e-243">このオプション条件を省略した場合、全体管理者アカウントが継続的なオンライン攻撃の対象となり、このアカウントが侵害された場合には、攻撃者が機密情報の獲得、破壊、または身代金要求の目的で保持することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4886e-243">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="4886e-244">必要に応じて、[手順 3](identity-azure-ad-identity-protection.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4886e-244">If needed, [Step 3](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>


## <a name="next-phase"></a><span data-ttu-id="4886e-245">次のフェーズ</span><span class="sxs-lookup"><span data-stu-id="4886e-245">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="4886e-246">Microsoft 365 Enterprise のエンドツーエンド展開プロセスの次のフェーズは、[Windows 10 Enterprise](windows10-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="4886e-246">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

