---
title: 共有メールボックスの問題を解決する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスで問題が発生した場合は、次の解決策を試してください。
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926488"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="6c69b-103">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="6c69b-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="6c69b-104">共有メールボックスを作成または使用するときにエラー メッセージが表示される場合は、次の解決策を試してください。</span><span class="sxs-lookup"><span data-stu-id="6c69b-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="6c69b-105">共有メールボックスを作成するときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="6c69b-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="6c69b-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="6c69b-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="6c69b-107">エラー メッセージが表示された場合は、プロキシ アドレス "smtp:<共有メールボックス名" が既にプロキシ アドレスまたは **\> " " の LegacyExchangeDN によって使用されています \<name> 。Please choose another proxy address**, it're trying to give the shared mailbox a name that's already in use.</span><span class="sxs-lookup"><span data-stu-id="6c69b-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="6c69b-108">たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="6c69b-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="6c69b-109">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6c69b-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="6c69b-110">Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c69b-110">Use Windows PowerShell.</span></span> <span data-ttu-id="6c69b-111">手順については、次のブログ投稿を参照してください。異なるドメインで同じエイリアスを持つ共有 [メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6c69b-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="6c69b-112">2 番目の共有メールボックスに、最初とは異なる名前を付け、エラーを回避します。</span><span class="sxs-lookup"><span data-stu-id="6c69b-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="6c69b-113">次に、管理センターで共有メールボックスの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6c69b-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="6c69b-114">共有メールボックスを使用するときに送信アクセス許可を持たない場合のエラー</span><span class="sxs-lookup"><span data-stu-id="6c69b-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="6c69b-115">共有メールボックスを作成し、そのメールボックスからメッセージを送信すると、次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6c69b-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="6c69b-116">**このメッセージを送信する必要があります。指定したユーザーの代わりにメッセージを送信するアクセス許可を持っている。**</span><span class="sxs-lookup"><span data-stu-id="6c69b-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="6c69b-117">このメッセージは、Microsoft 365 でレプリケーションの遅延の問題が発生している場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c69b-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="6c69b-118">新しい共有メールボックス (または追加されたユーザー) に関する情報がすべてのデータ センターにレプリケートされた場合は、1 時間以上後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="6c69b-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="6c69b-119">1 時間待って、もう一度メッセージを送信してください。</span><span class="sxs-lookup"><span data-stu-id="6c69b-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c69b-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="6c69b-120">Related articles</span></span>

[<span data-ttu-id="6c69b-121">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="6c69b-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="6c69b-122">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="6c69b-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="6c69b-123">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="6c69b-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="6c69b-124">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="6c69b-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="6c69b-125">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="6c69b-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

