---
title: Microsoft 365 キャンペーンの条件付きアクセスポリシーを設定する
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: セキュリティを強化するために、Microsoft 365 キャンペーンの条件付きアクセスポリシーをセットアップする方法について説明します。
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470649"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="2e49e-103">条件付きアクセス ポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2e49e-103">Set up conditional access policies</span></span>

<span data-ttu-id="2e49e-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e49e-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="2e49e-105">[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシーによって追加のセキュリティが大幅に強化します。</span><span class="sxs-lookup"><span data-stu-id="2e49e-105">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="2e49e-106">Microsoft は、すべてのお客様に推奨される基準条件付きアクセスポリシーのセットを提供しています。</span><span class="sxs-lookup"><span data-stu-id="2e49e-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="2e49e-107">ベースラインポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ、定義済みのポリシーのセットです。</span><span class="sxs-lookup"><span data-stu-id="2e49e-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="2e49e-108">これらの一般的な攻撃には、パスワードのスプレー、リプレイ、フィッシングを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2e49e-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="2e49e-109">これらのポリシーでは、管理者とユーザーは、一定の条件が満たされたときに2番目の形式の認証 (多元的な認証、または MFA) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e49e-109">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="2e49e-110">たとえば、ユーザーが別の国からサインインしている場合、サインインが危険であると見なされ、ユーザーは追加の認証形式を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e49e-110">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="2e49e-111">現在、ベースラインポリシーには次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e49e-111">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="2e49e-112">**管理者** &ndash; に MFA を要求するグローバル管理者など、最も権限のある管理者の役割に対して多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e49e-112">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="2e49e-113">**エンドユーザーによる保護** &ndash;サインインが危険な場合にのみ、ユーザーに対して多要素認証を要求します。</span><span class="sxs-lookup"><span data-stu-id="2e49e-113">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="2e49e-114">**従来の認証** &ndash; をブロックする以前のクライアントアプリや一部の新しいアプリでは、より新しいセキュリティで保護された認証プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="2e49e-114">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="2e49e-115">これらの古いアプリは、条件付きアクセスポリシーをバイパスし、環境への権限のないアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="2e49e-115">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="2e49e-116">このポリシーは、条件付きアクセスをサポートしていないクライアントからのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2e49e-116">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="2e49e-117">**サービス管理** &ndash; に MFA を必要とするAzure portal (基準ポリシーの構成場所) を含む、管理ツールへのアクセスに多要素認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e49e-117">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="2e49e-118">Microsoft では、これらのベースラインポリシーのすべてを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e49e-118">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="2e49e-119">これらのポリシーを有効にした後、管理者とユーザーは Azure Multii authentication を登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2e49e-119">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="2e49e-120">これらのポリシーの詳細については、「 [baseline ポリシーとは](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e49e-120">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="2e49e-121">ベースラインポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="2e49e-121">Set up baseline policies</span></span>

1. <span data-ttu-id="2e49e-122">[Azure portal](https://portal.azure.com)に移動して、 **azure Active Directory**の \> **条件付きアクセス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e49e-122">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="2e49e-123">ベースラインポリシーがページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e49e-123">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="2e49e-124">![条件付きアクセスのベースラインポリシーを一覧表示するページ。](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="2e49e-124">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="2e49e-125">各ポリシーについて、次の具体的な手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e49e-125">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="2e49e-126">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="2e49e-126">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="2e49e-127">ユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="2e49e-127">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="2e49e-128">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="2e49e-128">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="2e49e-129">サービス管理に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="2e49e-129">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="2e49e-130">承認済みのクライアントアプリの要求など、多くの追加のポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2e49e-130">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="2e49e-131">詳細については、[条件付きアクセスのドキュメント](https://docs.microsoft.com/azure/active-directory/conditional-access/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e49e-131">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
