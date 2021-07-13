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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスをセットアップすると、エラーが発生する可能性があります。 共有メールボックスに問題が発生した場合は、次の解決策を試してください。
ms.openlocfilehash: ae76bc1cb97c44087be57adc7791ea8814b94b40
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393945"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="4d0fb-104">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="4d0fb-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="4d0fb-105">共有メールボックスを作成または使用するときにエラー メッセージが表示される場合は、次の解決策を試してください。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="4d0fb-106">共有メールボックスを作成するときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="4d0fb-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="4d0fb-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="4d0fb-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="4d0fb-108">エラー メッセージが表示された場合は、プロキシ アドレス "smtp:<共有メールボックス名" が既に "" のプロキシ アドレスまたは **\> LegacyExchangeDN によって使用されています。 \<name>別のプロキシ アドレスを選択** してください。これは、共有メールボックスに既に使用されている名前を付けようとしているという意味です。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="4d0fb-109">たとえば、info@domain1 と info@domain2 という名前の共有メールボックスが必要とします。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="4d0fb-110">これを行うには次に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="4d0fb-111">Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-111">Use Windows PowerShell.</span></span> <span data-ttu-id="4d0fb-112">手順については、このブログの投稿を参照してください。 異なるドメインで同じエイリアスを使用 [して共有メールボックスを作成する](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="4d0fb-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="4d0fb-113">エラーを回避するには、2 番目の共有メールボックスに最初とは異なる名前を付きます。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="4d0fb-114">次に、管理センターで共有メールボックスの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="4d0fb-115">共有メールボックスの使用時に送信アクセス許可を持たない場合のエラー</span><span class="sxs-lookup"><span data-stu-id="4d0fb-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="4d0fb-116">共有メールボックスを作成し、そのメールボックスからメッセージを送信しようとする場合は、次の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="4d0fb-117">**このメッセージを送信する必要があります。指定したユーザーに代わってメッセージを送信するアクセス許可を持つ必要があります。**</span><span class="sxs-lookup"><span data-stu-id="4d0fb-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="4d0fb-118">このメッセージは、レプリケーションMicrosoft 365が発生している場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="4d0fb-119">新しい共有メールボックス (または追加ユーザー) に関する情報がすべてのデータ センターにレプリケートされた場合、1 時間かそれ以上で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="4d0fb-120">1 時間待って、もう一度やり直してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4d0fb-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="4d0fb-121">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4d0fb-121">Related content</span></span>

<span data-ttu-id="4d0fb-122">[共有メールボックスについて](about-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4d0fb-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="4d0fb-123">[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4d0fb-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4d0fb-124">[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4d0fb-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4d0fb-125">[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4d0fb-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4d0fb-126">[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4d0fb-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

