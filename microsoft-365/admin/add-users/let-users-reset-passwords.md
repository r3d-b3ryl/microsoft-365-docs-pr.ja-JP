---
title: ユーザーが自分でパスワードをリセットできるようにする
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: セルフサービスのパスワードリセットツールを使用してパスワードをリセットする方法について説明します。
ms.openlocfilehash: 5c30d1da20998fb7e9681431173070ba57e1b090
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387035"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="1ff4a-103">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="1ff4a-103">Let users reset their own passwords</span></span>

<span data-ttu-id="1ff4a-104">パスワードのリセットを求められるユーザーとの間でクラッシュしますか?</span><span class="sxs-lookup"><span data-stu-id="1ff4a-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="1ff4a-105">Microsoft 365 管理者は、[セルフサービスのパスワードリセットツール](https://go.microsoft.com/fwlink/p/?LinkId=522677)を使用して、ユーザーのパスワードをリセットする必要がないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="1ff4a-106">作業が少なくてすみます。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-106">Less work for you!</span></span> 
  
<span data-ttu-id="1ff4a-107">以下の点を知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="1ff4a-108">Microsoft 365 business、エデュケーション、または非営利**団体の有料プランを使用し**て、クラウドユーザーのセルフサービスのパスワードリセットを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="1ff4a-109">Microsoft 365 の試用版では動作しません。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-109">It doesn't work with Microsoft 365 trial.</span></span> 
    
- <span data-ttu-id="1ff4a-p103">この操作には Azure を使用します。これらの手順を行うときに、自動的に **無料** で Azure にあるこの機能を取得できます。その他の Azure 機能を使用しない場合は、セルフサービスによるパスワード リセットをオンにするために費用はかかりません。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="1ff4a-113">**オンプレミスの Active Directory を使用している場合**は、上の2つのポイントは適用されません。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="1ff4a-114">代わりに、これを設定できますが、 **AZURE AD Premium への有料サブスクリプションが必要**です。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="1ff4a-115">ユーザーが自分のパスワードをリセットできるようにするための短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="1ff4a-116">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="1ff4a-117">ユーザーが自分のパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="1ff4a-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="1ff4a-118">次の手順を行うと、社内のすべてのユーザーに対してセルフサービスによるパスワードのリセットがオンになります。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1. <span data-ttu-id="1ff4a-119">管理センターで、[**設定**の \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">設定</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1ff4a-120"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**設定** \> **セキュリティ &amp; プライバシー** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1ff4a-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**設定**の設定] [ \> **Settings** \> **セキュリティ &amp; プライバシー** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="1ff4a-122">[設定] ページの上部で、[**セキュリティ & プライバシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-122">At the top of the Settings page select **Security & Privacy**.</span></span>
  
3. <span data-ttu-id="1ff4a-123">[**セルフサービスのパスワードのリセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-123">Select **Self Service Password Reset**.</span></span>
  
4. <span data-ttu-id="1ff4a-124">[プロパティ] ページで、[**すべて**] を選択して、会社のすべてのユーザーに対して有効にし、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-124">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="1ff4a-125">ユーザーがサインインすると、今後、パスワードを再設定するのに役立つ追加の連絡先情報を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ff4a-125">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1ff4a-126">関連記事</span><span class="sxs-lookup"><span data-stu-id="1ff4a-126">Related articles</span></span>

[<span data-ttu-id="1ff4a-127">組織のパスワード有効期限ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="1ff4a-127">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="1ff4a-128">有効期限が切れないように個別のユーザーのパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="1ff4a-128">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="1ff4a-129">Microsoft 365 Business のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="1ff4a-129">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
