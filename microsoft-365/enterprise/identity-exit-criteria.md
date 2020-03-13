---
title: 'フェーズ 2: ID インフラストラクチャの終了条件'
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
description: 構成が Microsoft 365 Enterprise の ID ベースのサービスとインフラストラクチャの条件を満たしていることを確認します。
ms.openlocfilehash: 3fd4d0a1df50d55cb7a21668b609341d0c01aa35
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544066"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="41174-103">フェーズ 2: ID インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="41174-103">Phase 2: Identity infrastructure exit criteria</span></span>

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="41174-105">ID インフラストラクチャが次の必須基準を満たすとともに、オプションの基準も考慮済みであることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="41174-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="41174-106">ID インフラストラクチャに関する追加の推奨事項については、[前提条件](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="41174-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="41174-107">必須: 全体管理者アカウントが保護されている</span><span class="sxs-lookup"><span data-stu-id="41174-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="41174-108">[Office 365 全体管理者アカウントが保護される](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)ことで、Microsoft 365 サブスクリプションの侵害につながる可能性がある攻撃者による資格情報の侵害を阻止します。</span><span class="sxs-lookup"><span data-stu-id="41174-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="41174-109">この必須条件を省略した場合、全体管理者アカウントが攻撃および侵害を受けやすくなり、攻撃者は獲得攻撃、破壊、または身代金要求の目的で、システム全体でデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="41174-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="41174-110">必要に応じて、[手順 1](identity-create-protect-global-admins.md#identity-global-admin) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-111">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-111">How to test</span></span>

<span data-ttu-id="41174-112">全体管理者アカウントを保護していることを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="41174-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="41174-113">PowerShell コマンドプロンプトで、次の Azure Active Directory PowerShell for Graph コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41174-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="41174-114">専用のグローバル管理者アカウントのリストのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41174-114">You should see only the list of dedicated global administrator accounts.</span></span>
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="41174-115">手順 1 の各アカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-115">Sign in to Office 365 using each of the accounts from step 1.</span></span> <span data-ttu-id="41174-116">それぞれのサインインでは、Azure 多要素認証および組織で使用できる最も強力な2 次認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="41174-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="41174-117">Azure Active Directory PowerShell for Graph モジュールのインストールと Office 365 へのサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41174-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="41174-118">オプション: 全体管理者ロールをオンデマンドで割り当てることができるように、Privileged Identity Management をセットアップしている</span><span class="sxs-lookup"><span data-stu-id="41174-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="41174-119">「[Azure AD Privileged Identity Management (PIM) とは](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」の手順を実行して、Azure AD テナントで PIM を有効にし、全体管理者アカウントを適格な管理者として構成しています。</span><span class="sxs-lookup"><span data-stu-id="41174-119">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="41174-120">また、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」の推奨事項に従って、サイバー攻撃者から特権アクセスを保護するロードマップを策定しています。</span><span class="sxs-lookup"><span data-stu-id="41174-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="41174-121">このオプション条件を省略した場合、全体管理者アカウントが継続的なオンライン攻撃の対象となり、このアカウントが侵害された場合には、攻撃者が機密情報の獲得、破壊、または身代金要求の目的で保持することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="41174-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="41174-122">必要に応じて、[手順 1](identity-create-protect-global-admins.md#identity-pim) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="41174-123">省略可能: 特権アクセス管理を Office 365 で構成している</span><span class="sxs-lookup"><span data-stu-id="41174-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="41174-124">[Office 365 での特権アクセス管理を設定する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)トピックにある情報を使用して、特権アクセスを有効にし、組織内に 1 つまたは複数の特権アクセス ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="41174-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="41174-125">これらのポリシーを構成して、機密データへのアクセスや重要な構成設定へのアクセスのために just-in-time アクセスが有効にされました。</span><span class="sxs-lookup"><span data-stu-id="41174-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="41174-126">必要に応じて、[手順 1](identity-create-protect-global-admins.md#identity-pam) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="41174-127">省略可能: Azure AD パスワード保護により、脆弱なパスワードの使用が禁止されている</span><span class="sxs-lookup"><span data-stu-id="41174-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="41174-128">グローバル禁止パスワードとカスタムの用語 (省略可能) に対応する形で、[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)、および [オンプレミス Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) に対する脆弱なパスワードの禁止を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="41174-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="41174-129">必要に応じて、[手順 2](identity-secure-your-passwords.md#identity-password-prot) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="41174-130">オプション: ユーザーが各自のパスワードをリセットできる</span><span class="sxs-lookup"><span data-stu-id="41174-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="41174-131">「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」に従って、ユーザーのパスワード リセットを構成しています。</span><span class="sxs-lookup"><span data-stu-id="41174-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="41174-132">この条件を満たしていない場合は、ユーザーはパスワードをリセットする際にユーザー アカウント管理者に依頼する必要があるため、追加の ID 管理オーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="41174-132">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="41174-133">必要に応じて、[手順 2](identity-secure-your-passwords.md#identity-pw-reset) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="41174-134">オプション: ユーザーは Azure AD シームレス シングル サインオンを使用してサインインできます</span><span class="sxs-lookup"><span data-stu-id="41174-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="41174-135">クラウドベースのアプリケーション (Office 365 など) へのユーザーのサインイン方法を組織が簡素化できるように、[Azure AD Connect: シームレス シングル サインオン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="41174-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="41174-136">このオプション条件を省略した場合、Azure AD テナントを使用する他のアプリケーションにユーザーがアクセスすると、ユーザーに対して資格情報の入力が求められることがあります。</span><span class="sxs-lookup"><span data-stu-id="41174-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="41174-137">必要に応じて、[手順 2](identity-secure-your-passwords.md#identity-sso) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="41174-138">オプション: Office 365 のサインイン画面を組織に合わせてカスタマイズしている</span><span class="sxs-lookup"><span data-stu-id="41174-138">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="41174-139">「[クイック スタート: Azure AD のサインイン ページに会社のブランドを追加する](https://aka.ms/aadpaddbranding)」に従って組織のブランドを Office 365 サインイン ページに追加しています。</span><span class="sxs-lookup"><span data-stu-id="41174-139">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="41174-140">このオプション条件を省略した場合、ユーザーに対して汎用 Office 365 サインイン画面が表示され、ユーザーが当該組織のサイトにサインインすることを確信できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41174-140">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="41174-141">必要に応じて、[手順 2](identity-secure-your-passwords.md#identity-custom-sign-in) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="41174-142">オプション: ユーザーに対して Azure 多要素認証が有効になっている</span><span class="sxs-lookup"><span data-stu-id="41174-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="41174-143">「[Azure 多要素認証の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)」と「[条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)」を使用して、ユーザー アカウントのAzure 多要素認証 (MFA) を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="41174-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="41174-p104">このオプション条件を省略した場合、ユーザー アカウントはサイバー攻撃による資格情報の侵害に対して脆弱になります。ユーザー アカウントのパスワードが侵害されると、そのアカウントのすべてのリソースと機能 (管理者ロールなど) を攻撃者が利用できるようになります。これにより、攻撃者は内部資料やその他のデータを複製、破壊、または身代金要求目的で保持することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="41174-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="41174-147">必要に応じて、[手順 3](identity-secure-user-sign-ins.md#identity-mfa) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-148">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-148">How to test</span></span>

1.  <span data-ttu-id="41174-149">テスト ユーザー アカウントを作成して、それらにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="41174-149">Create a test user account and assign them a license.</span></span> 
2.  <span data-ttu-id="41174-150">実際のユーザー アカウントに使用している (電話へのテキスト メッセージの送信など) 追加の検証方式を使用して、テスト ユーザー アカウントの Azure 多要素認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="41174-150">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.  <span data-ttu-id="41174-151">テスト ユーザー アカウントを使用して Office 365 ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-151">Sign in to the Office 36 portal with the test user account.</span></span>
4.  <span data-ttu-id="41174-152">MFA により、追加の確認情報を入力するように求められ、その結果認証が正常に完了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="41174-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="41174-153">テスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="41174-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a><span data-ttu-id="41174-154">省略可能: 資格情報が侵害されないよう保護するための Azure AD Identity Protection の有効化 (Microsoft 365 E5 のみ)</span><span class="sxs-lookup"><span data-stu-id="41174-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="41174-155">次の目的で Azure AD Identity Protection を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="41174-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="41174-156">潜在的な ID の脆弱性に対処する。</span><span class="sxs-lookup"><span data-stu-id="41174-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="41174-157">資格情報の侵害の疑いがあるものを検出する。</span><span class="sxs-lookup"><span data-stu-id="41174-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="41174-158">発生している不審な ID インシデントを調査して対処する。</span><span class="sxs-lookup"><span data-stu-id="41174-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="41174-p105">このオプション条件を省略した場合、資格情報の侵害を試みる操作の検出または自動的な防止、ID 関連のセキュリティ インシデントの調査を実行できません。その結果、資格情報の侵害に対して組織が脆弱になり、組織の機密データに対する脅威が生じます。</span><span class="sxs-lookup"><span data-stu-id="41174-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="41174-161">必要に応じて、[手順 3](identity-secure-user-sign-ins.md#identity-ident-prot) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="41174-162">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-162">How to test</span></span>

1. <span data-ttu-id="41174-163">テスト ユーザー アカウントを作成し、初期パスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="41174-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="41174-164">「[Office 365 でユーザーが自分のパスワードを再設定する](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords)」の手順に従って、テスト ユーザー アカウントのパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="41174-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="41174-165">サインアウトし、リセット後のパスワードを使用してテスト ユーザー アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="41174-166">テスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="41174-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="41174-167">ハイブリッド アイデンティティの場合必須: ユーザーとグループが Azure AD と同期されている</span><span class="sxs-lookup"><span data-stu-id="41174-167">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="41174-168">既存のオンプレミス Active Directory Domain Services (AD DS) がある場合は、Azure AD Connect を使用して、オンプレミス AD DS から Azure AD テナントへユーザー アカウントとグループを同期しています。</span><span class="sxs-lookup"><span data-stu-id="41174-168">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="41174-169">ディレクトリ同期により、ユーザーは各自のコンピューターやオンプレミス リソースにサインインするときに使用する資格情報で、Office 365 やその他の Microsoft クラウド サービスにもサインインできます。</span><span class="sxs-lookup"><span data-stu-id="41174-169">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="41174-170">必要に応じて、[手順 4](identity-add-user-accounts.md#identity-sync) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="41174-171">この必須条件を省略した場合、2 つのセットのユーザー アカウントとグループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="41174-171">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="41174-172">オンプレミス AD DS に存在するユーザー アカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="41174-172">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="41174-173">Azure AD テナントに存在するユーザー アカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="41174-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="41174-p106">この状態では、IT 管理者とユーザーが、ユーザー アカウントとグループの 2 つのセットを手動で保守する必要があります。このため、アカウント、パスワード、グループが同期されていない状況が必然的に発生します。</span><span class="sxs-lookup"><span data-stu-id="41174-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-176">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-176">How to test</span></span>
<span data-ttu-id="41174-177">オンプレミスの資格情報を使用した認証が正しく機能することを確認するには、オンプレミスの資格情報を使用して Office ポータルにログインします。</span><span class="sxs-lookup"><span data-stu-id="41174-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="41174-178">ディレクトリ同期が正しく動作していることを確認するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="41174-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="41174-179">AD DS で新しいテスト グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="41174-179">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="41174-180">同期時刻まで待ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-180">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="41174-181">Azure AD テナントを調べ、新しいテスト グループ名があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41174-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="41174-182">オプション: ディレクトリ同期を監視している</span><span class="sxs-lookup"><span data-stu-id="41174-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="41174-183">「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」(パスワード同期の場合) または「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」(フェデレーテッド認証の場合) に従い、Azure AD Connect Health を展開しています。この展開では次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="41174-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="41174-184">オンプレミスの各 ID サーバーに Azure AD Connect Health エージェントをインストールする。</span><span class="sxs-lookup"><span data-stu-id="41174-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="41174-185">Azure AD Connect Health ポータルを使用して、継続的な同期の状態を監視する。</span><span class="sxs-lookup"><span data-stu-id="41174-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="41174-186">このオプション条件を省略した場合、クラウドベースの ID インフラストラクチャの状態をより正確に評価できます。</span><span class="sxs-lookup"><span data-stu-id="41174-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="41174-187">必要に応じて、[手順 4](identity-add-user-accounts.md#identity-sync-health) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-188">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-188">How to test</span></span>
<span data-ttu-id="41174-189">Azure AD Connect Health ポータルには、オンプレミス ドメイン コントローラーと継続中の同期の正確な現在の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41174-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="41174-190">オプション: ユーザーに対してパスワードの書き戻しが有効になっている</span><span class="sxs-lookup"><span data-stu-id="41174-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="41174-191">「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」の手順に従い、Microsoft 365 Enterprise サブスクリプションの Azure AD テナントのパスワードの書き戻しを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="41174-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="41174-192">このオプション条件を省略した場合、オンプレミスのネットワークに接続していないユーザーは、IT 管理者を通じて AD DS のパスワードをリセットまたはロック解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41174-192">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="41174-193">必要に応じて、[手順 4](identity-add-user-accounts.md#identity-pw-writeback) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="41174-194">パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生するリスクが高いことが Azure AD により検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="41174-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="41174-195">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-195">How to test</span></span>

<span data-ttu-id="41174-196">パスワードの書き戻しをテストするには、Office 365 でパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="41174-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="41174-197">オンプレミス AD DS リソースにアクセスするには、自分のアカウントと新しいパスワードを使用できるようする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41174-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="41174-198">オンプレミスの AD DS にテスト ユーザー アカウントを作成し、ディレクトリ同期を実行して、Microsoft 365 管理センターで Microsoft 365 Enterprise ライセンスをそのテスト ユーザー アカウントに付与します。</span><span class="sxs-lookup"><span data-stu-id="41174-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="41174-199">オンプレミスの AD DS ドメインに参加しているリモート コンピューターから、テスト ユーザー アカウントの資格情報を使用してコンピューターと Office ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="41174-200">**[設定] > [Office 365 の設定] > [パスワード] > [パスワードの設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="41174-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="41174-201">現在のパスワードを入力し、新しいパスワードを入力し、確認のため新しいパスワードをもう一度入力します。</span><span class="sxs-lookup"><span data-stu-id="41174-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="41174-202">Office ポータルとリモート コンピューターからサインアウトし、テスト ユーザー アカウントと新しいパスワードを使用してコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="41174-203">Azure AD テナントを使用したオンプレミスの AD DS のユーザー アカウントパスワードを変更することができたことが、これで証明されます。</span><span class="sxs-lookup"><span data-stu-id="41174-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-204">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-204">How to test</span></span>

<span data-ttu-id="41174-205">ユーザーのアカウント名と Azure 多要素認証を使用して、Office 365 ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-205">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="41174-206">サインイン ページにカスタムのブランド化要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41174-206">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="41174-207">オプション: 特定の Azure AD セキュリティと Office 365 グループでセルフサービスによるグループの管理が有効になっている</span><span class="sxs-lookup"><span data-stu-id="41174-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="41174-208">セルフサービスによる管理に適しているグループを判別し、各グループの所有者に対してグループ管理のワークフローと責任を説明し、これらのグループに対して[Azure AD でのセルフサービスによる管理をセットアップ](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)しています。</span><span class="sxs-lookup"><span data-stu-id="41174-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="41174-209">このオプション条件を省略した場合、IT 管理者がすべての Azure AD グループ管理タスクを手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41174-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="41174-210">必要に応じて、[手順 5](identity-use-group-management.md#identity-self-service-groups) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-211">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-211">How to test</span></span>
1.  <span data-ttu-id="41174-212">Azure Portal で Azure AD にテスト ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="41174-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="41174-213">テスト ユーザー アカウントとしてサインインし、テスト Azure AD セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="41174-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="41174-214">サインアウトして、IT 管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="41174-215">テスト セキュリティ グループで、テスト ユーザー アカウントをセルフサービスにより管理するように構成します。</span><span class="sxs-lookup"><span data-stu-id="41174-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="41174-216">サインアウトし、テスト ユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="41174-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="41174-217">Azure Portal を使用して、テスト セキュリティ グループにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="41174-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="41174-218">テスト セキュリティ グループとテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="41174-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="41174-219">オプション: 動的グループ メンバーシップの設定により、ユーザー アカウントの属性に基づいてユーザー アカウントがグループに自動的に追加される</span><span class="sxs-lookup"><span data-stu-id="41174-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="41174-220">Azure AD の動的グループを決定し、「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」の手順に従って、グループを作成し、グループ メンバーシップのユーザー アカウント属性と値を指定するルールを作成しています。</span><span class="sxs-lookup"><span data-stu-id="41174-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="41174-p110">このオプション条件を省略した場合、新しいアカウントが追加されるか、またはユーザー アカウントの属性が時間の経過に伴って変化するときに、グループ メンバーシップを手動で設定する必要があります。たとえば、Sales 部門から Accounting 部門にユーザーが移動した場合、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="41174-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="41174-223">ユーザーの Departement 属性の値を更新する。</span><span class="sxs-lookup"><span data-stu-id="41174-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="41174-224">Sales グループからユーザーを手動で削除する。</span><span class="sxs-lookup"><span data-stu-id="41174-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="41174-225">Accounting グループにユーザーを手動で追加する。</span><span class="sxs-lookup"><span data-stu-id="41174-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="41174-226">Sales グループと Accounting グループが動的グループである場合は、必要な操作はユーザー アカウントの Department の値の変更だけです。</span><span class="sxs-lookup"><span data-stu-id="41174-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="41174-227">必要に応じて、[手順 5](identity-use-group-management.md#identity-dyn-groups) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-228">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-228">How to test</span></span>

1. <span data-ttu-id="41174-229">Azure Portal で Azure AD にテスト用の動的グループを作成し、Department が「test 1」であるというルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="41174-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="41174-230">Azure AD でテスト ユーザー アカウントを作成し、Department プロパティに「test1」を設定します。</span><span class="sxs-lookup"><span data-stu-id="41174-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="41174-231">テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41174-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="41174-232">テスト ユーザー アカウントの Department プロパティの値を「test2」に変更します。</span><span class="sxs-lookup"><span data-stu-id="41174-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="41174-233">テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーではないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="41174-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="41174-234">テスト用の動的グループとテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="41174-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="41174-235">オプション: グループ メンバーシップに基づいてユーザー アカウントに対しライセンスを自動的に割り当てるか削除するグループベースのライセンス</span><span class="sxs-lookup"><span data-stu-id="41174-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="41174-236">Microsoft 365 Enterprise ライセンスを自動的に割り当てたり、未割り当てにしたりするため、適切な Azure AD セキュリティ グループの[グループベースのライセンスを有効にしています](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="41174-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="41174-237">このオプション条件を省略した場合、次の操作を手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="41174-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="41174-238">アクセス権を付与する予定の新しいユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="41174-238">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="41174-239">組織に所属していないユーザーや、アクセス権がないユーザーへのライセンスの割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="41174-239">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="41174-240">必要に応じて、[手順 5](identity-use-group-management.md#identity-group-license) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="41174-241">テスト方法</span><span class="sxs-lookup"><span data-stu-id="41174-241">How to test</span></span>

1. <span data-ttu-id="41174-242">Azure ポータルを使用して Azure AD にテスト セキュリティ グループを作成し、Microsoft 365 Enterprise ライセンスを割り当てるためにグループベースのライセンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="41174-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="41174-243">テスト ユーザー アカウントを Azure AD に作成して、このアカウントをテスト セキュリティ グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="41174-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="41174-244">Microsoft 365 管理センターでユーザー アカウントのプロパティを調査し、そのアカウントに Microsoft 365 Enterprise ライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41174-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="41174-245">テスト セキュリティ グループからテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="41174-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="41174-246">ユーザー アカウントのプロパティを調べて、そのアカウントに Microsoft 365 Enterprise ライセンスが割り当てられていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="41174-246">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="41174-247">テスト セキュリティ グループとテスト ユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="41174-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="41174-248">省略可能: アクセスを監視するために構成して使用されるアクセス ビュー</span><span class="sxs-lookup"><span data-stu-id="41174-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="41174-249">グループ メンバーシップ、エンタープライズ アプリケーションへのアクセス、ロールの割り当てを監視するためのさまざまな種類のアクセス レビューを構成するために、これらの記事を使用しました。</span><span class="sxs-lookup"><span data-stu-id="41174-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="41174-250">グループとアプリ</span><span class="sxs-lookup"><span data-stu-id="41174-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="41174-251">Azure AD ロール</span><span class="sxs-lookup"><span data-stu-id="41174-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="41174-252">Azure リソース ロール</span><span class="sxs-lookup"><span data-stu-id="41174-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="41174-253">必要に応じて、[手順 6](identity-configure-identity-governance.md#identity-access-reviews) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41174-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="41174-254">結果と次の手順</span><span class="sxs-lookup"><span data-stu-id="41174-254">Results and next steps</span></span>

<span data-ttu-id="41174-255">Microsoft 365 クラウド内の ID インフラストラクチャは、強力な認証、保護されている管理者アカウント、簡略化されたユーザーのアクセスと管理を使用します。</span><span class="sxs-lookup"><span data-stu-id="41174-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![フェーズ 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="41174-257">Microsoft 365 Enterprise のエンド ツー エンド展開のフェーズを実行している場合、次の手順は [Windows 10 Enterprise](windows10-infrastructure.md) です。</span><span class="sxs-lookup"><span data-stu-id="41174-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

