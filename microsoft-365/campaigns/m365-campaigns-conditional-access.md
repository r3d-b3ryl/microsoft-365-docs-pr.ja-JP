---
title: セキュリティの既定値を有効にする
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
description: 事前に構成されたセキュリティ設定を提供することで、セキュリティの既定値が ID 関連の攻撃から組織を保護する方法について学習します。
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398293"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="96c68-103">セキュリティの既定値を有効にする</span><span class="sxs-lookup"><span data-stu-id="96c68-103">Turn on security defaults</span></span>

<span data-ttu-id="96c68-104">セキュリティの既定値は、Microsoft が組織の代わりに管理する構成済みのセキュリティ設定を提供することで、組織を ID 関連の攻撃から保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96c68-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="96c68-105">これらの設定には、すべての管理者およびユーザー アカウントに対して多要素認証 (MFA) を有効にする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="96c68-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="96c68-106">ほとんどの組織では、セキュリティの既定値は、優れたレベルの追加サインイン セキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="96c68-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="96c68-107">セキュリティの既定値と適用するポリシーの詳細については、「セキュリティの既定値 [とは」を参照してください。](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="96c68-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="96c68-108">2019 年 10 月 22 日以降にサブスクリプションが作成された場合は、セキュリティの既定値が自動的に有効になっている可能性があります。確認するには、設定を確認する &mdash; 必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c68-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="96c68-109">Azure Active Directory (Azure Active Directory AD) でセキュリティの既定値を有効にするか、既に有効になっているか確認するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="96c68-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="96c68-110">グローバル管理者資格情報を <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">使用して Microsoft 365</a> 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="96c68-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="96c68-111">左側のウィンドウで、[すべて表示] を選択し **、[** 管理センター] で **[Azure Active Directory] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96c68-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="96c68-112">Azure Active Directory 管理センターの左側のウィンドウ **で、[Azure Active Directory]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96c68-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="96c68-113">ダッシュボードの左側のメニューの [管理] セクション **で** 、[プロパティ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="96c68-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="[プロパティ] メニュー項目の場所を示す Azure Active Directory 管理センターのスクリーンショット。":::

5. <span data-ttu-id="96c68-115">[プロパティ] ページの下部 **で、[** セキュリティの既定の **管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96c68-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="96c68-116">右側のウィンドウに、[セキュリティの既定を有効 **にする] 設定が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="96c68-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="96c68-117">[ **はい** ] が選択されている場合、セキュリティの既定値は既に有効になっているので、それ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="96c68-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="96c68-118">セキュリティの既定値が現在有効になっていない場合は、[ **は** い] を選択して有効にし、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="96c68-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="96c68-119">条件付きアクセス ポリシーを使用している場合は、セキュリティの既定値を使用する前に、ポリシーをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c68-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="96c68-120">セキュリティの既定値または条件付きアクセス ポリシーを使用できますが、両方を同時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="96c68-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="96c68-121">条件付きアクセスの使用を検討する</span><span class="sxs-lookup"><span data-stu-id="96c68-121">Consider using Conditional Access</span></span>

<span data-ttu-id="96c68-122">組織が複雑なセキュリティ要件を持つ場合や、セキュリティ ポリシーを細かく制御する必要がある場合は、セキュリティの既定値ではなく条件付きアクセスを使用して、同様またはより高いセキュリティ体制を実現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c68-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="96c68-123">条件付きアクセスを使用すると、ユーザーにアプリケーションまたはサービスへのアクセスを許可する前に、サインイン イベントに対応するポリシーを作成および定義し、追加のアクションを要求できます。</span><span class="sxs-lookup"><span data-stu-id="96c68-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="96c68-124">条件付きアクセス ポリシーは、細かく具体的な場合があります。ユーザーはいつでもどこでも生産性を高めることができますが、組織を保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="96c68-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="96c68-125">セキュリティの既定値は、すべてのお客様が使用できます。条件付きアクセスには、次のいずれかのプランのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="96c68-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="96c68-126">Azure Active Directory Premium P1 または P2</span><span class="sxs-lookup"><span data-stu-id="96c68-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="96c68-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="96c68-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="96c68-128">Microsoft 365 E3 または E5</span><span class="sxs-lookup"><span data-stu-id="96c68-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="96c68-129">エンタープライズ モビリティ & E3 または E5</span><span class="sxs-lookup"><span data-stu-id="96c68-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="96c68-130">条件付きアクセスを使用して、セキュリティの既定値で有効になっているポリシーと同等のポリシーを構成する場合は、次の手順ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c68-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="96c68-131">管理者に対して MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="96c68-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="96c68-132">Azure 管理に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="96c68-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="96c68-133">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="96c68-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="96c68-134">すべてのユーザーに対して MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="96c68-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="96c68-135">[Azure AD MFA](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) ADする - Azure Active Directory Premium P2 の一部である Azure AD ID 保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="96c68-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="96c68-136">条件付きアクセスの詳細については、「条件付きアクセス [とは」を参照してください。](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="96c68-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="96c68-137">条件付きアクセス ポリシーの作成の詳細については、「条件付きアクセス ポリシー [の作成」を参照してください](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。</span><span class="sxs-lookup"><span data-stu-id="96c68-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="96c68-138">条件付きアクセスを提供するプランまたはライセンスを持っているが、条件付きアクセス ポリシーがまだ作成されていない場合は、セキュリティの既定値を使用してください。</span><span class="sxs-lookup"><span data-stu-id="96c68-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="96c68-139">ただし、条件付きアクセス ポリシーを使用するには、セキュリティの既定値をオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c68-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
