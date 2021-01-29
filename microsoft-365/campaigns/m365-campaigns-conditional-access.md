---
title: 条件付きアクセス ポリシーのセットアップ
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: MFA を要求し、ビジネス向け Microsoft 365 の条件付きアクセス ポリシーを設定する方法について説明します。
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044502"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="47654-103">多要素認証を要求し、条件付きアクセス ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="47654-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="47654-104">多要素認証と条件付きアクセス ポリシーを使用して、データへのアクセスを保護します。</span><span class="sxs-lookup"><span data-stu-id="47654-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="47654-105">追加のセキュリティが大幅に強化されます。</span><span class="sxs-lookup"><span data-stu-id="47654-105">These add substantial additional security.</span></span> <span data-ttu-id="47654-106">Microsoft では、すべてのお客様に推奨される一連のベースライン条件付きアクセス ポリシーを提供しています。</span><span class="sxs-lookup"><span data-stu-id="47654-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="47654-107">ベースライン ポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ定義済みポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="47654-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="47654-108">これらの一般的な攻撃には、パスワード スプレー、リプレイ、フィッシングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="47654-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="47654-109">これらのポリシーでは、管理者とユーザーが特定の条件下で 2 番目の認証形式 (多要素認証 (MFA) と呼ばれる) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47654-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="47654-110">たとえば、組織内のユーザーが別の国または不明なデバイスから Microsoft 365 にサインインしようとすると、サインインは危険と見なされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47654-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="47654-111">ユーザーは、ID を証明するために、追加の形式の認証 (指紋やコードなど) を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47654-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="47654-112">現時点では、ベースライン ポリシーには次のポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="47654-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="47654-113">Microsoft 365 管理センターでセットアップします。</span><span class="sxs-lookup"><span data-stu-id="47654-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="47654-114">**管理者に MFA を要求** する : グローバル管理者を含む、最も特権のある管理者の役割に対して多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="47654-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="47654-115">**エンド ユーザー保護**: サインインが危険な場合にのみ、ユーザーに多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="47654-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="47654-116">Azure Active Directory ポータルで設定します。</span><span class="sxs-lookup"><span data-stu-id="47654-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="47654-117">**レガシ認証を** ブロックする : 古いクライアント アプリや一部の新しいアプリでは、より新しい、より安全な認証プロトコルを使用しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="47654-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="47654-118">これらの古いアプリは、条件付きアクセス ポリシーをバイパスして、環境への無許可のアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="47654-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="47654-119">このポリシーは、条件付きアクセスをサポートしないクライアントからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="47654-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="47654-120">**サービス管理に MFA が** 必要: Azure portal (ベースライン ポリシーを構成する場所) を含む管理ツールへのアクセスに多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="47654-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="47654-121">これらのベースライン ポリシーはすべて有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47654-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="47654-122">これらのポリシーを有効にすると、管理者とユーザーは、Azure AD多要素認証に登録するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47654-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="47654-123">これらのポリシーの詳細については、「ベースライン ポリシーとは [」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)。</span><span class="sxs-lookup"><span data-stu-id="47654-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="47654-124">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="47654-124">Require MFA</span></span>

<span data-ttu-id="47654-125">すべてのユーザーが 2 番目の形式の ID でサインインする必要がある場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="47654-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="47654-126">管理センターに移動し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="47654-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="47654-127">[セットアップ] ページで、[ **サインイン** のセキュリティを高くする] カードで **[表示] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="47654-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![サインインのセキュリティを高くするカードを作成します。](../media/setupmfa.png)
3. <span data-ttu-id="47654-129">[サインインのセキュリティを高める] ページで、[開始する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="47654-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="47654-130">[サインインセキュリティの強化] ウィンドウで、[管理者に多要素認証を要求する] と [リスクが検出された場合はユーザーに多要素認証の登録とアクセスのブロックを要求する] の横にあるチェック ボックスをオン **にします。**</span><span class="sxs-lookup"><span data-stu-id="47654-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="47654-131">[ユーザーの検索] [ボックスの](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) MFA 要件から、緊急または"ブレークプロセス" 管理者アカウント **を除外してください** 。</span><span class="sxs-lookup"><span data-stu-id="47654-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Sing-in セキュリティ ページを強化します。](../media/requiremfa.png)

5. <span data-ttu-id="47654-133">ページ **の下部にある [** ポリシーの作成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47654-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="47654-134">ベースライン ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="47654-134">Set up baseline policies</span></span>

1. <span data-ttu-id="47654-135">Azure portal に [移動し、Azure](https://portal.azure.com) **Active Directory** 条件付きアクセスに移動して \> 新しいポリシー **を作成します**。</span><span class="sxs-lookup"><span data-stu-id="47654-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="47654-136">各ポリシーについて、次の具体的な手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47654-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="47654-137">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="47654-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="47654-138">ユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="47654-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="47654-139">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="47654-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="47654-140">サービス管理に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="47654-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="47654-141">プレビュー ポリシーは存在しなくなったので、ユーザーは独自のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47654-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="47654-142">承認されたクライアント アプリの要求など、追加のポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="47654-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="47654-143">詳細については、条件付きアクセスの [ドキュメントを参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="47654-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
