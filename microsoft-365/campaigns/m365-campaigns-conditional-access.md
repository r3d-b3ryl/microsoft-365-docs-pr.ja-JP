---
title: 条件付きアクセスポリシーを設定する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: MFA を要求する方法と、Microsoft 365 Business の条件付きアクセスポリシーを設定する方法について説明します。
ms.openlocfilehash: 0279fff8dd4143c883b2f1633907ac197c65f04a
ms.sourcegitcommit: b535fe233234fd25146cfe15478e20d954f71e03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "38748288"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="aed1b-103">多要素認証を必要とし、条件付きアクセスポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="aed1b-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="aed1b-104">多要素認証および条件付きアクセスポリシーを使用して、データへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="aed1b-105">これらにより、セキュリティが大幅に強化します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-105">These add substantial additional security.</span></span> <span data-ttu-id="aed1b-106">Microsoft は、すべてのお客様に推奨される基準条件付きアクセスポリシーのセットを提供しています。</span><span class="sxs-lookup"><span data-stu-id="aed1b-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="aed1b-107">ベースラインポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ、定義済みのポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="aed1b-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="aed1b-108">これらの一般的な攻撃には、パスワードのスプレー、リプレイ、フィッシングを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="aed1b-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="aed1b-109">これらのポリシーでは、管理者とユーザーは、一定の条件が満たされたときに、2番目の形式の認証 (多要素認証または MFA と呼ばれる) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aed1b-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="aed1b-110">たとえば、組織内のユーザーが、別の国または不明なデバイスから Microsoft 365 にサインインしようとした場合、そのサインインは危険であると見なされることがあります。</span><span class="sxs-lookup"><span data-stu-id="aed1b-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="aed1b-111">ユーザーは、id を証明するために、特別な形式の認証 (指紋やコードなど) を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aed1b-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="aed1b-112">現在、ベースラインポリシーには次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aed1b-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="aed1b-113">Microsoft 365 管理センターでのセットアップ:</span><span class="sxs-lookup"><span data-stu-id="aed1b-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="aed1b-114">管理者**に MFA を要求**—グローバル管理者を含む、最も特権のある管理者の役割に対して多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="aed1b-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="aed1b-115">**エンドユーザーによる保護**—サインインが危険な場合にのみ、ユーザーに対して多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="aed1b-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="aed1b-116">Azure Active Directory ポータルで設定します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="aed1b-117">**従来の認証をブロック**する: 以前のクライアントアプリや一部の新しいアプリでは、より新しい、より安全な認証プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="aed1b-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="aed1b-118">これらの古いアプリは、条件付きアクセスポリシーをバイパスし、環境への権限のないアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="aed1b-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="aed1b-119">このポリシーは、条件付きアクセスをサポートしていないクライアントからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="aed1b-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="aed1b-120">**サービス管理に MFA を必要と**する— Azure portal を含む、管理ツールへのアクセスに多要素認証が必要です (基準ポリシーの構成場所)。</span><span class="sxs-lookup"><span data-stu-id="aed1b-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="aed1b-121">Microsoft では、これらのベースラインポリシーのすべてを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aed1b-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="aed1b-122">これらのポリシーが有効になると、管理者とユーザーは Azure 多要素認証を登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="aed1b-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="aed1b-123">これらのポリシーの詳細については、「 [baseline ポリシーとは](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aed1b-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="aed1b-124">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="aed1b-124">Require MFA</span></span>

<span data-ttu-id="aed1b-125">すべてのユーザーに2番目の形式の ID を使用してサインインするよう要求するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="aed1b-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="aed1b-126">管理センターに移動し<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>て、[**セットアップ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="aed1b-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="aed1b-127">[セットアップ] ページで、[サインイン] の [**セキュリティで保護さ**れたカードの作成] で [**表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![サインインして、より安全なカードを作成します。](media/setupmfa.png)
3. <span data-ttu-id="aed1b-129">[サインインを強化する] ページで、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="aed1b-130">[サインインのセキュリティを強化する] ウィンドウで、[**管理者に多要素認証を必要**とする] の横にあるチェックボックスをオンにし、[**ユーザーに多要素認証の登録を要求し、リスクが検出された場合はアクセスをブロック**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="aed1b-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="aed1b-131">[**ユーザーの検索**] ボックスの [MFA] 要件から、[緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)または "破損" 管理者アカウントを除外するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="aed1b-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![[セキュリティを強化する] ページ。](media/requiremfa.png)

5. <span data-ttu-id="aed1b-133">ページの下部にある [**ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="aed1b-134">ベースラインポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="aed1b-134">Set up baseline policies</span></span>

1. <span data-ttu-id="aed1b-135">[Azure portal](https://portal.azure.com)に移動して、 **azure Active Directory** \>の**条件付きアクセス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="aed1b-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="aed1b-136">ベースラインポリシーはページに一覧表示されており、管理者と**エンドユーザー保護\*\*\*\*を必要**とする手順が完了した後、 [mfa が必要](#require-mfa)であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="aed1b-136">The baseline policies are listed on the page, and you can see that **Require MFA for admins** and **End user protection** are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![条件付きアクセスのベースラインポリシーを一覧表示するページ。](media/casettings.png)
2. <span data-ttu-id="aed1b-138">各ポリシーについて、次の具体的な手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aed1b-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="aed1b-139">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="aed1b-139">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [<span data-ttu-id="aed1b-140">ユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="aed1b-140">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="aed1b-141">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="aed1b-141">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="aed1b-142">サービス管理に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="aed1b-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="aed1b-143">承認済みのクライアントアプリの要求など、特別なポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="aed1b-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="aed1b-144">詳細については、[条件付きアクセスのドキュメント](https://docs.microsoft.com/azure/active-directory/conditional-access/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aed1b-144">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
