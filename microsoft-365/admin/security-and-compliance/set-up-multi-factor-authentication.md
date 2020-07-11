---
title: ユーザーの多要素認証を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 組織向けに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083540"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="18782-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="18782-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="18782-104">[多要素認証 (MFA) を理解し、Microsoft 365でサポートされていること](multi-factor-authentication-microsoft-365.md) を理解したら、それを設定し、組織にロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="18782-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="18782-105">作業を開始する前に、これらの特殊条件が適用されているかどうかを確認し、適切なアクションを行います。</span><span class="sxs-lookup"><span data-stu-id="18782-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="18782-106">Windows デバイスで Office 2013 クライアントを使用している場合は、[最新のライセンス認証を有効化](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) します。</span><span class="sxs-lookup"><span data-stu-id="18782-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="18782-107">Active Directory フェデレーション サービス (AD FS) を使用しているサードパーティ ディレクトリ サービスがある場合は、Azure MFA サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="18782-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="18782-108">詳細については、「[Azure Multi-factor Authentication およびサードパーティ製の VPN ソリューションでの高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18782-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="18782-109">他のすべてのユーザーは、必要に応じて追加認証を求められます。</span><span class="sxs-lookup"><span data-stu-id="18782-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="18782-110">詳細については、「[2要素検証方法と設定](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18782-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="18782-111">手順1: ユーザーに MFA の使用を要求する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="18782-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="18782-112">MFA を設定または変更するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="18782-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="18782-113">ユーザーがサインインのために MFA を使用するには、3つの方法があります。詳細については、「[Microsoft 365 の MFA サポート](multi-factor-authentication-microsoft-365.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18782-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="18782-114">セキュリティの既定値 (中小企業に推奨)</span><span class="sxs-lookup"><span data-stu-id="18782-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="18782-115">2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、MFA を要求するメッセージが予期せず表示されます。 [セキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) の設定は、サブスクリプションに対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="18782-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="18782-116">新しい Microsoft 365 サブスクリプションでは、すべてにおいて自動的にセキュリティの既定値が有効になります。</span><span class="sxs-lookup"><span data-stu-id="18782-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="18782-117">つまり、すべてのユーザーが MFA を設定し、モバイル デバイスに Microsoft Authenticator アプリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18782-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="18782-118">すべてのユーザーは、追加の検証方法として Microsoft Authenticator アプリを使用する必要があります。また、従来の認証がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="18782-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="18782-119">条件付きアクセス ポリシー (大企業に推奨)</span><span class="sxs-lookup"><span data-stu-id="18782-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="18782-120">ユーザーは、MFA の登録中に追加の検証方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="18782-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="18782-121">ユーザー アカウント単位 (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="18782-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="18782-122">ユーザーは、MFA の登録中に追加の検証方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="18782-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="18782-123">手順 2.</span><span class="sxs-lookup"><span data-stu-id="18782-123">Step 2.</span></span> <span data-ttu-id="18782-124">パイロット ユーザーに MFA をテストする</span><span class="sxs-lookup"><span data-stu-id="18782-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="18782-125">条件付きアクセス ポリシーまたはユーザー単位の MFA を使用している場合 (推奨されません)、MFA の登録とサインインをテストするために、会社または組織のパイロット ユーザーを選択します。例えば：</span><span class="sxs-lookup"><span data-stu-id="18782-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="18782-126">条件付きアクセス ポリシーの場合、パイロット ユーザー グループを作成し、グループとすべてのアプリのメンバーに MFA を要求するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="18782-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="18782-127">次に、パイロット ユーザーのアカウントをグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="18782-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="18782-128">ユーザーごとの MFA については、パイロット ユーザーのユーザー アカウントの MFA を1つずつ有効にします。</span><span class="sxs-lookup"><span data-stu-id="18782-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="18782-129">パイロット ユーザーと協力して質問や問題に対処し、組織にスムーズに展開するための準備を行います。</span><span class="sxs-lookup"><span data-stu-id="18782-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="18782-130">手順 3.</span><span class="sxs-lookup"><span data-stu-id="18782-130">Step 3.</span></span> <span data-ttu-id="18782-131">MFA の到来を組織に知らせる</span><span class="sxs-lookup"><span data-stu-id="18782-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="18782-132">従業員の理解を深めるために、メール通知、廊下ポスター、チーム会議、または公的な研修を活用します。</span><span class="sxs-lookup"><span data-stu-id="18782-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="18782-133">サインインに MFA が必要な理由</span><span class="sxs-lookup"><span data-stu-id="18782-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="18782-134">追加の検証手法を登録する方法</span><span class="sxs-lookup"><span data-stu-id="18782-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="18782-135">登録後のサインインの方法</span><span class="sxs-lookup"><span data-stu-id="18782-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="18782-136">追加の検証手法を変更する方法</span><span class="sxs-lookup"><span data-stu-id="18782-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="18782-137">新しいスマートフォンのような状況に対処する方法</span><span class="sxs-lookup"><span data-stu-id="18782-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="18782-138">最も重要な点は、従業員を驚かせることなく、***MFA の要件がいつ課されるか*** について彼らが理解しているかどうかを確認することです。</span><span class="sxs-lookup"><span data-stu-id="18782-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="18782-139">手順 4.</span><span class="sxs-lookup"><span data-stu-id="18782-139">Step 4.</span></span> <span data-ttu-id="18782-140">MFA 要件を組織またはユーザーに展開する</span><span class="sxs-lookup"><span data-stu-id="18782-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="18782-141">選択した MFA の要件に基づいて、パイロット テスター以外の従業員に MFA 認証を展開します。</span><span class="sxs-lookup"><span data-stu-id="18782-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="18782-142">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="18782-142">Security defaults</span></span>

<span data-ttu-id="18782-143">Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="18782-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="18782-144">グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="18782-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="18782-145">[[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="18782-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="18782-146">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18782-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="18782-147">セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18782-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="18782-148">[条件付きアクセスのベースライン ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) を使用している場合は、次の手順に従ってセキュリティの既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="18782-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="18782-149">[条件付きアクセス ポリシー ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) へ移動します。</span><span class="sxs-lookup"><span data-stu-id="18782-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="18782-150">各ベースライン ポリシーで [**オン**] を選択し、 [**ポリシーを有効にする**] を [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="18782-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="18782-151">[[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="18782-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="18782-152">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18782-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="18782-153">セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18782-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="18782-154">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="18782-154">Conditional Access policies</span></span>

<span data-ttu-id="18782-155">サインインに MFA が必要なユーザーのグループを含む適切なポリシーを作成し、構成して有効にします。</span><span class="sxs-lookup"><span data-stu-id="18782-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="18782-156">ユーザーごとの MFA (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="18782-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="18782-157">展開に対応する MFA のユーザー アカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="18782-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="18782-158">従業員をサポートする</span><span class="sxs-lookup"><span data-stu-id="18782-158">Supporting your employees</span></span>

<span data-ttu-id="18782-159">従業員が MFA を登録してサインインするときに、IT スペシャリスト、IT 部門、またはヘルプデスクが質問に回答して、問題にすばやく対処することができます。</span><span class="sxs-lookup"><span data-stu-id="18782-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="18782-160">[MFA サインインのトラブルシューティングに関する情報](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2) については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18782-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


