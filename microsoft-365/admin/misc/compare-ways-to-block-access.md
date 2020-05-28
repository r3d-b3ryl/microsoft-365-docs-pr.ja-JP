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
description: 従業員が組織を離れたときに Microsoft 365 へのアクセスをブロックする方法について説明します。
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399436"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="9c5e0-103">アクセスをブロックする方法を比較する</span><span class="sxs-lookup"><span data-stu-id="9c5e0-103">Compare ways to block access</span></span>

<span data-ttu-id="9c5e0-104">従業員が組織を離れた場合は、Microsoft 365 へのアクセスを禁止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="9c5e0-105">ここでは、いくつかの方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="9c5e0-106">**アクセスをブロックする方法**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="9c5e0-107">**定義**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-107">**Definition**</span></span> <br/> |<span data-ttu-id="9c5e0-108">**注意事項**</span><span class="sxs-lookup"><span data-stu-id="9c5e0-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="9c5e0-109">サインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="9c5e0-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="9c5e0-110">ユーザーが Microsoft 365 にアクセスできないようにする方法の1つは、サインインの状態を **[サインインをブロック**する」に変更することです。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="9c5e0-111">これにより、それらのユーザーは、以前にダウンロードした、または同期した電子メールやドキュメントを引き続き表示できるが、コンピューターやモバイルデバイスから Microsoft 365 にサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="9c5e0-112">Blackberry Enterprise サービスを使用している場合は、それらへのアクセスを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="9c5e0-113">従業員が組織を離れる場合や、長期休暇を取得する予定であるときに使います。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="9c5e0-114">ユーザー パスワードを再設定する</span><span class="sxs-lookup"><span data-stu-id="9c5e0-114">Reset user password</span></span>  <br/> |<span data-ttu-id="9c5e0-115">ユーザーが Microsoft 365 にアクセスできないようにするもう1つの方法は、パスワードをリセットすることです。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="9c5e0-116">これにより、以前にダウンロードまたは同期されたメールやドキュメントを表示することはできますが、自分のアカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="9c5e0-117">その後、そのユーザーとしてサインインして、選択したパスワードに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="9c5e0-118">従業員が突然組織を離れ、今後戻る様子がなく、ビジネス データに問題があると思われる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="9c5e0-119">割り当てられたすべてのライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="9c5e0-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="9c5e0-120">別の方法として、ユーザーに割り当てられている Microsoft 365 ライセンスを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="9c5e0-121">これにより、Office スイート、web 用の Office アプリ、Yammer、SharePoint Online などのアプリケーションやサービスを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="9c5e0-122">サインインすることはできますが、これらのサービスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="9c5e0-123">このユーザーが Microsoft 365 の特定の機能にアクセスする必要がなくなったと感じる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="9c5e0-124">**重要:** ライセンスを削除すると、ユーザーのメールボックスは30日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="9c5e0-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="9c5e0-125">関連記事</span><span class="sxs-lookup"><span data-stu-id="9c5e0-125">Related articles</span></span>

[<span data-ttu-id="9c5e0-126">Microsoft 365 からのユーザーのオフボード</span><span class="sxs-lookup"><span data-stu-id="9c5e0-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="9c5e0-127">Microsoft 365 でユーザーのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="9c5e0-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="9c5e0-128">一般法人向け Microsoft 365 ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="9c5e0-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="9c5e0-129">Microsoft 365 for business のユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="9c5e0-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

