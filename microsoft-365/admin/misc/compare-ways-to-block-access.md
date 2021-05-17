---
title: アクセスをブロックする方法を比較する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 従業員が組織を離れるときにMicrosoft 365アクセスをブロックする方法について学習します。
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399436"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="1f7c9-103">アクセスをブロックする方法を比較する</span><span class="sxs-lookup"><span data-stu-id="1f7c9-103">Compare ways to block access</span></span>

<span data-ttu-id="1f7c9-104">従業員が組織を離れる場合、良い条件か悪い場合は、組織へのアクセスをブロックMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="1f7c9-105">ここでは、いくつかの方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="1f7c9-106">**アクセスをブロックする方法**</span><span class="sxs-lookup"><span data-stu-id="1f7c9-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="1f7c9-107">**定義**</span><span class="sxs-lookup"><span data-stu-id="1f7c9-107">**Definition**</span></span> <br/> |<span data-ttu-id="1f7c9-108">**注意事項**</span><span class="sxs-lookup"><span data-stu-id="1f7c9-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="1f7c9-109">サインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="1f7c9-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="1f7c9-110">ユーザーがアクセスをブロックする 1 つの方法Microsoft 365、サインインの状態を [サインインがブロック済み]**に変更します**。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="1f7c9-111">これにより、以前にダウンロードまたは同期Microsoft 365した電子メールやドキュメントを表示することができますが、コンピューターやモバイル デバイスからデバイスにサインインできません。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="1f7c9-112">Blackberry Enterpriseサービスを使用している場合は、アクセスを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="1f7c9-113">従業員が組織を離れる場合や、長期休暇を取得する予定であるときに使います。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="1f7c9-114">ユーザー パスワードを再設定する</span><span class="sxs-lookup"><span data-stu-id="1f7c9-114">Reset user password</span></span>  <br/> |<span data-ttu-id="1f7c9-115">ユーザーがパスワードにアクセスMicrosoft 365もう 1 つの方法は、パスワードをリセットする方法です。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="1f7c9-116">これにより、以前にダウンロードまたは同期された電子メールやドキュメントを表示することができますが、アカウントを使用できません。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="1f7c9-117">その後、ユーザーとしてサインインし、パスワードを選択したパスワードに変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="1f7c9-118">従業員が突然組織を離れ、今後戻る様子がなく、ビジネス データに問題があると思われる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="1f7c9-119">割り当てられたすべてのライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="1f7c9-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="1f7c9-120">別のオプションは、ユーザーに割りMicrosoft 365ライセンスを削除する方法です。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="1f7c9-121">これにより、Office スイート、Office アプリなど、web、Yammer、および SharePoint Online のようなアプリケーションとサービスを使用SharePointします。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="1f7c9-122">サインインすることはできますが、これらのサービスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="1f7c9-123">このユーザーが特定の機能にアクセスする必要がなくなったと感じた場合にMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="1f7c9-124">**重要:** ライセンスを削除すると、ユーザーのメールボックスは 30 日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="1f7c9-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="1f7c9-125">関連記事</span><span class="sxs-lookup"><span data-stu-id="1f7c9-125">Related articles</span></span>

[<span data-ttu-id="1f7c9-126">ユーザーをオフボードMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="1f7c9-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="1f7c9-127">ユーザーのパスワードをパスワードでリセットMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="1f7c9-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="1f7c9-128">一般法人向け Microsoft 365 ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="1f7c9-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="1f7c9-129">ビジネス向けユーザーからライセンスMicrosoft 365削除する</span><span class="sxs-lookup"><span data-stu-id="1f7c9-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

