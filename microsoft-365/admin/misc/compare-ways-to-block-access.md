---
title: Office 365 へのアクセスをブロックする方法を比較する
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: 従業員が組織を離れたときに Office 365 へのアクセスをブロックする方法について説明します。
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257397"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="f2403-103">Office 365 へのアクセスをブロックする方法を比較する</span><span class="sxs-lookup"><span data-stu-id="f2403-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="f2403-p101">従業員が組織を離れたときは、その条件に関わらず、Office 365 へのアクセスをブロックする必要があります。ここでは、いくつかの方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f2403-p101">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365. Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="f2403-106">**アクセスをブロックする方法**</span><span class="sxs-lookup"><span data-stu-id="f2403-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="f2403-107">**定義**</span><span class="sxs-lookup"><span data-stu-id="f2403-107">**Definition**</span></span> <br/> |<span data-ttu-id="f2403-108">**注意事項**</span><span class="sxs-lookup"><span data-stu-id="f2403-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="f2403-109">サインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="f2403-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="f2403-p102">特定のユーザーからの Office 365 へのアクセスをブロックする 1 つの方法は、そのユーザーのサインイン状態を [ **サインインのブロック**] に変更することです。これにより、組織を離れた従業員がコンピューターやモバイル デバイスから Office 365 にサインインすることを防ぎます。ただし、以前にダウンロードした、または同期したメールとドキュメントは表示されます。Blackberry Enterprise Service を使用している場合は、組織を離れたユーザーの Blackberry Enterprise Service へのアクセスも無効にすることができます。  </span><span class="sxs-lookup"><span data-stu-id="f2403-p102">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**. This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents. If you're using Blackberry Enterprise Service, you can disable their access there as well.  </span></span><br/> |<span data-ttu-id="f2403-113">従業員が組織を離れる場合や、長期休暇を取得する予定であるときに使います。</span><span class="sxs-lookup"><span data-stu-id="f2403-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="f2403-114">ユーザー パスワードを再設定する</span><span class="sxs-lookup"><span data-stu-id="f2403-114">Reset user password</span></span>  <br/> |<span data-ttu-id="f2403-p103">特定のユーザーが Office 365 にアクセスすることを防止するには、パスワードをリセットする方法もあります。これにより、そのユーザーが自分のアカウントを使用することを防ぎます。ただし、以前にダウンロードした、または同期したメールとドキュメントは表示されます。そのユーザーとしてサインインし、パスワードを別のパスワードに変更します。</span><span class="sxs-lookup"><span data-stu-id="f2403-p103">Another way to prevent a user from accessing Office 365 is to reset their password. This prevents them from using their account though they can still view previously downloaded or synced email and documents. You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="f2403-118">従業員が突然組織を離れ、今後戻る様子がなく、ビジネス データに問題があると思われる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f2403-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="f2403-119">割り当てられたすべてのライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="f2403-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="f2403-120">もう一つのオプションは、ユーザーに割り当てられたすべての Office 365 ライセンスを削除することです。</span><span class="sxs-lookup"><span data-stu-id="f2403-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="f2403-121">これにより、Office スイート、web 用の Office アプリ、Yammer、SharePoint Online などのアプリケーションやサービスを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2403-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="f2403-122">サインインすることはできますが、これらのサービスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2403-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="f2403-123">そのユーザーが Office 365 の特定の機能にアクセスする必要がなくなったと感じる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f2403-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="f2403-124">**重要:** ライセンスを削除すると、ユーザーのメールボックスは30日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f2403-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="f2403-125">関連記事</span><span class="sxs-lookup"><span data-stu-id="f2403-125">Related articles</span></span>

[<span data-ttu-id="f2403-126">Office 365 からユーザーを削除する</span><span class="sxs-lookup"><span data-stu-id="f2403-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="f2403-127">Office 365 でユーザーのパスワードを再設定する</span><span class="sxs-lookup"><span data-stu-id="f2403-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="f2403-128">一般法人向け Office 365 ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f2403-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="f2403-129">一般法人向け Office 365 のユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="f2403-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

