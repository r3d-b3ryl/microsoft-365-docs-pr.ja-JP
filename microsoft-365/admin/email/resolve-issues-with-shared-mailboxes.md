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
description: 共有メールボックスに問題が発生した場合は、次の解決策を試してください。
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926488"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="6a1bf-103">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="6a1bf-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="6a1bf-104">共有メールボックスを作成または使用するときにエラー メッセージが表示される場合は、次の解決策を試してください。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="6a1bf-105">共有メールボックスを作成するときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="6a1bf-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="6a1bf-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="6a1bf-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="6a1bf-107">エラー メッセージが表示された場合は、プロキシ アドレス "smtp:<共有メールボックス名" が既に "" のプロキシ アドレスまたは **\> LegacyExchangeDN によって使用されています。 \<name>別のプロキシ アドレスを選択** してください。これは、共有メールボックスに既に使用されている名前を付けようとしているという意味です。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="6a1bf-108">たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="6a1bf-109">これを行うには次に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="6a1bf-110">Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-110">Use Windows PowerShell.</span></span> <span data-ttu-id="6a1bf-111">手順については、このブログの投稿を参照してください。 異なるドメインで同じエイリアスを使用 [して共有メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6a1bf-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="6a1bf-112">エラーを回避するには、2 番目の共有メールボックスに最初とは異なる名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="6a1bf-113">次に、管理センターで共有メールボックスの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="6a1bf-114">共有メールボックスの使用時に送信アクセス許可を持たない場合のエラー</span><span class="sxs-lookup"><span data-stu-id="6a1bf-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="6a1bf-115">共有メールボックスを作成し、そのメールボックスからメッセージを送信しようとする場合は、次の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="6a1bf-116">**このメッセージを送信する必要があります。指定したユーザーに代わってメッセージを送信するアクセス許可を持つ必要があります。**</span><span class="sxs-lookup"><span data-stu-id="6a1bf-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="6a1bf-117">このメッセージは、レプリケーションMicrosoft 365が発生している場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="6a1bf-118">新しい共有メールボックス (または追加ユーザー) に関する情報がすべてのデータ センターにレプリケートされた場合、1 時間かそれ以上で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="6a1bf-119">1 時間待って、もう一度やり直してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6a1bf-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6a1bf-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="6a1bf-120">Related articles</span></span>

[<span data-ttu-id="6a1bf-121">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="6a1bf-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="6a1bf-122">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="6a1bf-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="6a1bf-123">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="6a1bf-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="6a1bf-124">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="6a1bf-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="6a1bf-125">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="6a1bf-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

