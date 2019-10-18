---
title: Microsoft 365 キャンペーンの条件付きアクセスポリシーを設定する
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 キャンペーンの条件付きアクセスポリシーを設定する方法について説明します。
ms.openlocfilehash: 31f3b7f3678671af3b5ca3947dec37041b226fac
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575640"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="f4113-103">条件付きアクセスポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="f4113-103">Set up conditional access policies</span></span>

<span data-ttu-id="f4113-104">[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシー substancial 追加のセキュリティを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4113-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="f4113-105">Microsoft は、すべてのお客様に推奨される基準条件付きアクセスポリシーのセットを提供しています。</span><span class="sxs-lookup"><span data-stu-id="f4113-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="f4113-106">ベースラインポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ、定義済みのポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="f4113-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="f4113-107">これらの一般的な攻撃には、パスワードのスプレー、リプレイ、フィッシングを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f4113-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="f4113-108">これらのポリシーでは、管理者とユーザーは、一定の条件が満たされたときに2番目の形式の認証 (多元的な認証、または MFA) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4113-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="f4113-109">たとえば、ユーザーが別の国からサインインしている場合、サインインが危険であると見なされ、ユーザーは追加の認証形式を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4113-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="f4113-110">現在、ベースラインポリシーには次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4113-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="f4113-111">管理者**に MFA を要求**—グローバル管理者を含む、最も特権のある管理者の役割に対して多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4113-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="f4113-112">**エンドユーザーによる保護**—サインインが危険な場合にのみ、ユーザーに対して多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4113-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="f4113-113">**従来の認証をブロック**する: 以前のクライアントアプリや一部の新しいアプリでは、より新しい、より安全な認証プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="f4113-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="f4113-114">これらの古いアプリは、条件付きアクセスポリシーをバイパスし、環境への権限のないアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="f4113-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="f4113-115">このポリシーは、条件付きアクセスをサポートしていないクライアントからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="f4113-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="f4113-116">**サービス管理に MFA を必要と**する— Azure portal を含む、管理ツールへのアクセスに多要素認証が必要です (基準ポリシーの構成場所)。</span><span class="sxs-lookup"><span data-stu-id="f4113-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="f4113-117">Microsoft では、これらのベースラインポリシーのすべてを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4113-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="f4113-118">これらのポリシーを有効にした後、管理者とユーザーは Azure Multii authentication を登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="f4113-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="f4113-119">これらのポリシーの詳細については、「 [baseline ポリシーとは](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4113-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="f4113-120">ベースラインポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="f4113-120">Set up baseline policies</span></span>

1. <span data-ttu-id="f4113-121">[Azure portal](https://portal.azure.com)に移動して、 **azure Active Directory** \>の**条件付きアクセス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f4113-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="f4113-122">ベースラインポリシーがページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4113-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="f4113-123">![条件付きアクセスのベースラインポリシーを一覧表示するページ。](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="f4113-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="f4113-124">各ポリシーについて、次の具体的な手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4113-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="f4113-125">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="f4113-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="f4113-126">ユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="f4113-126">Require MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="f4113-127">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="f4113-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="f4113-128">サービス管理に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="f4113-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="f4113-129">承認済みのクライアントアプリの要求など、多くの追加のポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f4113-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="f4113-130">詳細については、[条件付きアクセスのドキュメント](https://docs.microsoft.com/azure/active-directory/conditional-access/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4113-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>