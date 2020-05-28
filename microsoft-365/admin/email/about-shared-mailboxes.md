---
title: 共有メールボックスについて
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスは、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。 共有メールボックスを作成する前に知っておく必要のある情報について説明します。
ms.openlocfilehash: 6d9b7f59840b8eb4ce38822945066e14d9a86a4d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400210"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="40648-104">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="40648-104">About shared mailboxes</span></span>

<span data-ttu-id="40648-105">共有メールボックスは、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="40648-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="40648-106">グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="40648-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="40648-107">これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40648-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="40648-108">[共有メールボックスを作成](create-a-shared-mailbox.md)する前に、次の点を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="40648-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know:</span></span>

- <span data-ttu-id="40648-109">**ライセンス:** 共有メールボックスには、ライセンスを割り当てなくても最大 50 GB のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="40648-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="40648-110">その後に、より多くのデータを格納するには、メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="40648-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="40648-111">共有メールボックスのライセンスの詳細については、「 [Exchange Online の制限](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="40648-112">共有メールボックスが記憶域の上限に達した場合、しばらくはメールを受信できますが、新しいメールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="40648-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="40648-113">その後、メールも受信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="40648-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="40648-114">そのメールボックスにメールを送信したユーザーには、配信不能エラーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="40648-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="40648-115">**ユーザー権限:** ユーザーに共有メールボックスを使用する権限 (メンバーシップ) を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40648-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="40648-116">組織内のユーザーのみが共有メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40648-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="40648-117">**外部ユーザー:** 会社外のユーザー (Gmail アカウントを持つユーザーなど) に共有メールボックスへのアクセス権を付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="40648-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="40648-118">この操作を行う必要がある場合は、代わりに Outlook 用グループを作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="40648-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="40648-119">詳細については、「[管理センターで Microsoft 365 グループを作成](../create-groups/create-groups.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-119">To learn more, see [Create a Microsoft 365 group in the admin center](../create-groups/create-groups.md).</span></span>

-  <span data-ttu-id="40648-120">**Outlook で使用:** ブラウザーから web 上の Outlook を使用して共有メールボックスにアクセスするだけでなく、Outlook for iOS アプリまたは Outlook for Android アプリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="40648-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="40648-121">詳細については、「<a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">共有メールボックスを Outlook mobile に追加</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-121">To learn more, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span> <span data-ttu-id="40648-122">別の方法として、共有メールボックスのグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="40648-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="40648-123">詳細については、「[グループを比較](../create-groups/compare-groups.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>  

- <span data-ttu-id="40648-124">**暗号化:** 共有メールボックスから送信された電子メールを暗号化することはできません。</span><span class="sxs-lookup"><span data-stu-id="40648-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="40648-125">これは、共有メールボックスには独自のセキュリティコンテキスト (username/password) が含まれていないため、キーを割り当てることができないためです。</span><span class="sxs-lookup"><span data-stu-id="40648-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="40648-126">複数のユーザーがメンバーであり、自分のキーで暗号化された電子メールを送信または受信した場合、他のメンバーが電子メールの暗号化に使用された公開キーによっては電子メールを読むことができますが、そうでない場合があります。</span><span class="sxs-lookup"><span data-stu-id="40648-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="40648-127">**メールボックスの変換:** ユーザーメールボックスを共有メールボックスに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="40648-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="40648-128">「[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="40648-129">**管理者の役割:** グローバル管理者または Exchange 管理者の役割を持つユーザーは、共有メールボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="40648-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="40648-130">**サブスクリプションの要件:** 共有メールボックスを作成するには、電子メール (Exchange Online サービス) を含む Microsoft 365 for business プランを購読する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40648-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to a Microsoft 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="40648-131">Microsoft 365 Apps for business サブスクリプションには、電子メールは含まれていません。Microsoft 365 Business Standard。</span><span class="sxs-lookup"><span data-stu-id="40648-131">The Microsoft 365 Apps for business subscription doesn't include email; Microsoft 365 Business Standard does.</span></span>

- <span data-ttu-id="40648-132">**サインイン:** 共有メールボックスは、関連付けられたユーザーアカウントによる直接サインインを目的としたものではありません。</span><span class="sxs-lookup"><span data-stu-id="40648-132">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="40648-133">常に共有メールボックスアカウントのサインインをブロックし、ブロックしたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="40648-133">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="40648-134">**ユーザーが多すぎます:** 共有メールボックスに同時にアクセスする指定ユーザーの数が多すぎると、断続的にこのメールボックスへの接続に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40648-134">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="40648-135">この場合は、ユーザーの数を減らすか、Microsoft 365 グループまたはパブリックフォルダーなどの異なるワークロードを使用することを検討できます。</span><span class="sxs-lookup"><span data-stu-id="40648-135">In this case, you can consider reducing the number of the users or using a different workload, such a Microsoft 365 group or Public folder.</span></span>

- <span data-ttu-id="40648-136">**メッセージの削除:** 残念ながら、ユーザーが共有メールボックス内のメッセージを削除するのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="40648-136">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="40648-137">これを回避する唯一の方法は、共有メールボックスではなく、Microsoft 365 グループを作成することです。</span><span class="sxs-lookup"><span data-stu-id="40648-137">The only way around this is to create a Microsoft 365 group instead of a shared mailbox.</span></span> <span data-ttu-id="40648-138">Outlook のグループは、共有メールボックスに似ています。</span><span class="sxs-lookup"><span data-stu-id="40648-138">A group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="40648-139">両者の比較については、「[グループの比較](../create-groups/compare-groups.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-139">For a comparison of the two, see [Compare groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="40648-140">グループの詳細については、「[詳細](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40648-140">To learn more about groups, see [Learn more about groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="40648-141">関連記事</span><span class="sxs-lookup"><span data-stu-id="40648-141">Related articles</span></span>

[<span data-ttu-id="40648-142">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="40648-142">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="40648-143">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="40648-143">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="40648-144">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="40648-144">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="40648-145">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="40648-145">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="40648-146">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="40648-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
