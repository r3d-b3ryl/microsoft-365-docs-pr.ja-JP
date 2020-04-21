---
title: 共有メールボックスの問題を解決する
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスに問題が発生した場合は、これらのソリューションを試してみてください。
ms.openlocfilehash: 52aac8ab6936dfeba2ae4b5b7a80c45029ec6105
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628749"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="7ad71-103">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="7ad71-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="7ad71-104">共有メールボックスの作成時または使用時にエラーメッセージが表示する場合は、次の考えられる解決策を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="7ad71-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="7ad71-105">共有メールボックスの作成時のエラー</span><span class="sxs-lookup"><span data-stu-id="7ad71-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="7ad71-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad71-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="7ad71-107">エラーメッセージが表示された場合は、**プロキシアドレス "smtp: <共有\>メールボックス名" が、プロキシアドレスまたは "\<名前>" の LegacyExchangeDN によって既に使用されています。別のプロキシアドレスを選択してください**。これは、共有メールボックスに既に使用されている名前を付けようとしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7ad71-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="7ad71-108">たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="7ad71-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="7ad71-109">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="7ad71-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="7ad71-110">Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ad71-110">Use Windows PowerShell.</span></span> <span data-ttu-id="7ad71-111">手順:[異なるドメインで同じエイリアスを使用して共有メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)方法については、次のブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ad71-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="7ad71-112">エラーを回避するために、2番目の共有メールボックスの名前を開始日とは別のものにします。</span><span class="sxs-lookup"><span data-stu-id="7ad71-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="7ad71-113">次に、管理センターで、共有メールボックスの名前を目的の名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="7ad71-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="7ad71-114">共有メールボックスを使用している場合に送信アクセス許可を持たないエラー</span><span class="sxs-lookup"><span data-stu-id="7ad71-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="7ad71-115">共有メールボックスを作成してから、そのメールボックスからメッセージを送信しようとすると、次のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7ad71-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="7ad71-116">**このメッセージを送信できませんでした。指定したユーザーの代わりにメッセージを送信するためのアクセス許可がありません。**</span><span class="sxs-lookup"><span data-stu-id="7ad71-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="7ad71-117">このメッセージは、Microsoft 365 でレプリケーションの遅延の問題が発生した場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ad71-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="7ad71-118">新しい共有メールボックス (または追加されたユーザー) に関する情報がすべてのデータセンターでレプリケートされるときには、1時間以内に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ad71-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="7ad71-119">1時間待機してから、もう一度メッセージを送信してください。</span><span class="sxs-lookup"><span data-stu-id="7ad71-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7ad71-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="7ad71-120">Related articles</span></span>

[<span data-ttu-id="7ad71-121">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="7ad71-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="7ad71-122">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="7ad71-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="7ad71-123">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="7ad71-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="7ad71-124">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="7ad71-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="7ad71-125">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="7ad71-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

