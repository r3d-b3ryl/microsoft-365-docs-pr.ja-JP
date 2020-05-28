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
localization_priority: Normal
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
description: 組織で多要素認証をセットアップする方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 2b4ac2b5950d2641254742e03f054f3e4c886833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399124"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="fe034-103">多要素認証をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fe034-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="fe034-104">[Microsoft 365 での多要素認証 (MFA) とそのサポート](multi-factor-authentication-microsoft-365.md)についての理解に基づいて、これを設定して組織にロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="fe034-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="fe034-105">開始する前に、これらの特殊条件が適用されるかどうかを確認し、適切な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fe034-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="fe034-106">Windows デバイス上に Office 2013 クライアントがある場合は、[先進認証を有効に](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)します。</span><span class="sxs-lookup"><span data-stu-id="fe034-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="fe034-107">Active Directory フェデレーションサービス (AD FS) を備えたサードパーティ製のディレクトリサービスがある場合は、Azure MFA サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="fe034-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="fe034-108">詳細については[、「Azure 多要素認証とサードパーティ製 VPN ソリューションを使用した高度なシナリオ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe034-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="fe034-109">手順 1: ユーザーに MFA の使用を要求する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="fe034-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="fe034-110">ユーザーがサインインに MFA を使用するよう要求するには、次の3つの方法があります。詳細については、「 [Microsoft 365 の MFA サポート](multi-factor-authentication-microsoft-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe034-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="fe034-111">セキュリティの既定値 (小規模企業に推奨)</span><span class="sxs-lookup"><span data-stu-id="fe034-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="fe034-112">2019年10月21日以降にサブスクリプションまたは試用版を購入した場合に、MFA を予期せずに要求されると、サブスクリプションに対して[セキュリティの既定値](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="fe034-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="fe034-113">すべての新しい Microsoft 365 サブスクリプションのセキュリティの既定値が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="fe034-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="fe034-114">これは、すべてのユーザーが MFA を設定し、モバイルデバイスに Microsoft Authenticator アプリをインストールする必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fe034-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="fe034-115">すべてのユーザーは、追加の検証方法として Microsoft Authenticator アプリを使用する必要があり、従来の認証はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fe034-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="fe034-116">条件付きアクセスポリシー (エンタープライズに推奨)</span><span class="sxs-lookup"><span data-stu-id="fe034-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="fe034-117">ユーザーは、MFA 登録時に追加の確認方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe034-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="fe034-118">ユーザーごとのアカウント (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="fe034-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="fe034-119">ユーザーは、MFA 登録時に追加の確認方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe034-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="fe034-120">手順 2. </span><span class="sxs-lookup"><span data-stu-id="fe034-120">Step 2.</span></span> <span data-ttu-id="fe034-121">パイロットユーザーの MFA をテストする</span><span class="sxs-lookup"><span data-stu-id="fe034-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="fe034-122">条件付きアクセスポリシーまたはユーザーごとの MFA (推奨されません) を使用している場合は、「ビジネスまたは組織のパイロットユーザー」を選択して、MFA の登録とサインインをテストします。例えば：</span><span class="sxs-lookup"><span data-stu-id="fe034-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="fe034-123">条件付きアクセスポリシーの場合は、パイロットユーザーグループと、グループのメンバーとすべてのアプリに対して MFA を必要とするポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe034-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="fe034-124">次に、パイロットユーザーのアカウントをグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="fe034-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="fe034-125">ユーザー単位の MFA の場合は、パイロットユーザーのユーザーアカウントに対して MFA を1度ずつ有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe034-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="fe034-126">パイロットユーザーと協力して、組織への円滑なロールアウトを準備するための質問や問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="fe034-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="fe034-127">手順 3.</span><span class="sxs-lookup"><span data-stu-id="fe034-127">Step 3.</span></span> <span data-ttu-id="fe034-128">MFA が届くことを組織に通知する</span><span class="sxs-lookup"><span data-stu-id="fe034-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="fe034-129">従業員が理解していることを確認するために、電子メール通知、hallway ポスター、チーム会議、または公式トレーニングを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe034-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="fe034-130">サインインに MFA が必要な理由</span><span class="sxs-lookup"><span data-stu-id="fe034-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="fe034-131">追加の確認方法を登録する方法</span><span class="sxs-lookup"><span data-stu-id="fe034-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="fe034-132">登録後のサインイン方法</span><span class="sxs-lookup"><span data-stu-id="fe034-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="fe034-133">その他の検証方法を変更する方法</span><span class="sxs-lookup"><span data-stu-id="fe034-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="fe034-134">新しいスマートフォンなどの状況を処理する方法</span><span class="sxs-lookup"><span data-stu-id="fe034-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="fe034-135">最も重要なのは、従業員が驚いていないように、 ***MFA 要件***を設定する時期を理解しておくことです。</span><span class="sxs-lookup"><span data-stu-id="fe034-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="fe034-136">手順 4.</span><span class="sxs-lookup"><span data-stu-id="fe034-136">Step 4.</span></span> <span data-ttu-id="fe034-137">組織またはユーザーに MFA 要件をロールアウトする</span><span class="sxs-lookup"><span data-stu-id="fe034-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="fe034-138">選択した MFA 要件の方法に基づいて、パイロットテスト担当者以外の従業員に MFA 認証をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="fe034-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="fe034-139">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="fe034-139">Security defaults</span></span>

<span data-ttu-id="fe034-140">Azure portal で Azure Active Directory (Azure AD) の [**プロパティ**] ウィンドウを使用して、セキュリティの既定値を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="fe034-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="fe034-141">グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe034-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="fe034-142">[ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe034-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="fe034-143">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe034-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="fe034-144">[**はい]** を選択して**セキュリティの既定**値を有効にし、セキュリティの既定値を無効にして [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe034-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="fe034-145">[基準条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)を使用している場合は、「セキュリティの既定値を使用して移動する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe034-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="fe034-146">[[条件付きアクセスポリシー] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe034-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="fe034-147">有効になっているそれぞれ**の**ベースラインポリシーを選択し、[**ポリシーの有効化**] を [**オフ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="fe034-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="fe034-148">[ [Azure Active Directory-プロパティ] ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)に移動します。</span><span class="sxs-lookup"><span data-stu-id="fe034-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="fe034-149">ページの下部で、[**セキュリティの既定値の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe034-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="fe034-150">[**はい]** を選択して**セキュリティの既定**値を有効にし、セキュリティの既定値を無効にして [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe034-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="fe034-151">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="fe034-151">Conditional Access policies</span></span>

<span data-ttu-id="fe034-152">サインインのための MFA を必要とするユーザーのグループを含む適切なポリシーを作成、構成、および有効化します。</span><span class="sxs-lookup"><span data-stu-id="fe034-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="fe034-153">ユーザーごとの MFA (推奨しません)</span><span class="sxs-lookup"><span data-stu-id="fe034-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="fe034-154">ロールアウトに対応する MFA のユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe034-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="fe034-155">従業員のサポート</span><span class="sxs-lookup"><span data-stu-id="fe034-155">Supporting your employees</span></span>

<span data-ttu-id="fe034-156">従業員が MFA を登録してサインインを開始する際には、IT 専門家、IT 部門、またはヘルプデスクが質問に答えて、問題を迅速に解決できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="fe034-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="fe034-157">MFA のサインインの[トラブルシューティングに](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)ついては、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe034-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


