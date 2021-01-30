---
title: 共有メールボックスについて
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
description: 共有メールボックスは、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。 共有メールボックスを作成する前に知る必要がある情報について説明します。
ms.openlocfilehash: c8d29ac2dfe8670181064e61a7fba145ae00fed1
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058449"
---
# <a name="about-shared-mailboxes"></a><span data-ttu-id="2e593-104">共有メールボックスについて</span><span class="sxs-lookup"><span data-stu-id="2e593-104">About shared mailboxes</span></span>

<span data-ttu-id="2e593-105">共有メールボックスは、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e593-105">Shared mailboxes are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="2e593-106">グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。</span><span class="sxs-lookup"><span data-stu-id="2e593-106">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="2e593-107">これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2e593-107">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="2e593-108">共有メールボックス [を作成する前に](create-a-shared-mailbox.md)、次の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-108">Before you [create a shared mailbox](create-a-shared-mailbox.md), here are some things you should know:</span></span>

- <span data-ttu-id="2e593-109">**ライセンス:** 共有メールボックスには、ライセンスを割り当てずに最大 50 GB のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="2e593-109">**Licenses:** Your shared mailbox can store up to 50GB of data without you assigning a license to it.</span></span> <span data-ttu-id="2e593-110">その後に、より多くのデータを格納するには、メールボックスにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-110">After that, you need to assign a license to the mailbox to store more data.</span></span> <span data-ttu-id="2e593-111">共有メールボックスのライセンスの詳細については [、「Exchange Online の制限」を参照してください](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)。</span><span class="sxs-lookup"><span data-stu-id="2e593-111">For more details on shared mailbox licensing, please see [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits).</span></span> <span data-ttu-id="2e593-112">共有メールボックスが記憶域の上限に達した場合、しばらくはメールを受信できますが、新しいメールを送信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2e593-112">When a shared mailbox reaches the storage limit, you'll be able to receive email for a while, but you won't be able to send new email.</span></span> <span data-ttu-id="2e593-113">その後、メールも受信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2e593-113">Then, after that, it will stop receiving email.</span></span> <span data-ttu-id="2e593-114">そのメールボックスにメールを送信したユーザーには、配信不能エラーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="2e593-114">Senders to the mailbox will get a non-delivery receipt.</span></span>

- <span data-ttu-id="2e593-115">**ユーザーのアクセス許可:** 共有メールボックスを使用するには、ユーザーにアクセス許可 (メンバーシップ) を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-115">**User permissions:** You need to give users permissions (membership) to use the shared mailbox.</span></span> <span data-ttu-id="2e593-116">組織内のユーザーのみが共有メールボックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e593-116">Only people inside your organization can use a shared mailbox.</span></span>

- <span data-ttu-id="2e593-117">**外部ユーザー:** 社外のユーザー (Gmail アカウントを持つユーザーなど) に共有メールボックスへのアクセス権を与えすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e593-117">**External users:** You can't give people outside your business (such as people with a Gmail account) access to your shared mailbox.</span></span> <span data-ttu-id="2e593-118">この操作を行う必要がある場合は、代わりに Outlook 用グループを作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2e593-118">If you want to do this, consider creating a group for Outlook instead.</span></span> <span data-ttu-id="2e593-119">詳細については、管理センターで [Microsoft 365 グループを作成するを参照してください](../create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2e593-119">To learn more, see [Create a Microsoft 365 group in the admin center](../create-groups/create-groups.md).</span></span>

- <span data-ttu-id="2e593-120">**Outlook と一緒に使用します。** ブラウザーから Outlook on the web を使用して共有メールボックスにアクセスする以外に、Outlook for iOS アプリまたは Outlook for Android アプリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e593-120">**Use with Outlook:** In addition to using Outlook on the web from your browser to access shared mailboxes, you can also use the Outlook for iOS app or the Outlook for Android app.</span></span> <span data-ttu-id="2e593-121">詳細については、「共有メールボックス [を Outlook Mobile に追加する」を参照してください](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f)。</span><span class="sxs-lookup"><span data-stu-id="2e593-121">To learn more, see [Add a shared mailbox to Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f).</span></span> <span data-ttu-id="2e593-122">もう 1 つのオプションは、共有メールボックスのグループを作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="2e593-122">Another option is to create a group for your shared mailbox.</span></span> <span data-ttu-id="2e593-123">詳細については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2e593-123">To learn more, see [Compare Groups](../create-groups/compare-groups.md).</span></span>

- <span data-ttu-id="2e593-124">**暗号化:** 共有メールボックスから送信された電子メールは暗号化できません。</span><span class="sxs-lookup"><span data-stu-id="2e593-124">**Encryption:** You can't encrypt email sent from a shared mailbox.</span></span> <span data-ttu-id="2e593-125">これは、共有メールボックスに独自のセキュリティ コンテキスト (ユーザー名/パスワード) が設定されていないので、キーを割り当てられていないためです。</span><span class="sxs-lookup"><span data-stu-id="2e593-125">This is because a shared mailbox does not have its own security context (username/password) so it cannot be assigned a key.</span></span> <span data-ttu-id="2e593-126">複数のユーザーがメンバーであり、暗号化した電子メールを自分のキーで送受信する場合、他のメンバーは電子メールを読み取れ、他のメンバーは電子メールが暗号化された公開キーによっては読めない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-126">If more than one person is a member, and they send/receive emails they encrypted with their own keys, other members might be able to read the email and others might not, depending which public key the email was encrypted with.</span></span>

- <span data-ttu-id="2e593-127">**メールボックスの変換:** ユーザー メールボックスを共有メールボックスに変換できます。</span><span class="sxs-lookup"><span data-stu-id="2e593-127">**Mailbox conversion:** You can convert user mailboxes to shared mailboxes.</span></span> <span data-ttu-id="2e593-128">「[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e593-128">See [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span>

- <span data-ttu-id="2e593-129">**管理者ロール:** グローバル管理者または Exchange 管理者の役割を持つユーザーは、共有メールボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e593-129">**Admin roles:** Users with global admin or Exchange admin roles can create shared mailboxes.</span></span>

- <span data-ttu-id="2e593-130">**サブスクリプションの要件:** 共有メールボックスを作成するには、電子メール (Exchange Online サービス) を含む Microsoft 365 for Business プランをサブスクライブする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-130">**Subscription requirements:** To create a shared mailbox, you need to subscribe to a Microsoft 365 for business plan that includes email (the Exchange Online service).</span></span> <span data-ttu-id="2e593-131">Microsoft 365 Apps for business サブスクリプションには電子メールは含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e593-131">The Microsoft 365 Apps for business subscription doesn't include email.</span></span> <span data-ttu-id="2e593-132">Microsoft 365 Business Standard には電子メールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e593-132">Microsoft 365 Business Standard does include email.</span></span>

- <span data-ttu-id="2e593-133">**サインイン:** 共有メールボックスは、関連付けられたユーザー アカウントによる直接サインインを意図したのではありません。</span><span class="sxs-lookup"><span data-stu-id="2e593-133">**Signing in:** A shared mailbox is not intended for direct sign-in by its associated user account.</span></span> <span data-ttu-id="2e593-134">共有メールボックス アカウントのサインインは常にブロックし、ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-134">You should always block sign-in for the shared mailbox account and keep it blocked.</span></span>

- <span data-ttu-id="2e593-135">**ユーザーが多すぎます。** 共有メールボックスに同時にアクセスする指定ユーザーが多すぎる場合、このメールボックスへの接続が断続的に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-135">**Too many users:** When there are too many designated users concurrently accessing a shared mailbox, they may intermittently fail to connect to this mailbox.</span></span> <span data-ttu-id="2e593-136">この場合は、ユーザーの数を減らすか、Microsoft 365 グループやパブリック フォルダーなど、異なるワークロードを使用する方法を検討できます。</span><span class="sxs-lookup"><span data-stu-id="2e593-136">In this case, you can consider reducing the number of the users or using a different workload, such a Microsoft 365 group or Public folder.</span></span>

- <span data-ttu-id="2e593-137">**メッセージの削除:** 残念ながら、ユーザーが共有メールボックス内のメッセージを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e593-137">**Message deletion:** Unfortunately, you can't prevent people from deleting messages in a shared mailbox.</span></span> <span data-ttu-id="2e593-138">これを回避する唯一の方法は、共有メールボックスの代わりに Microsoft 365 グループを作成する方法です。</span><span class="sxs-lookup"><span data-stu-id="2e593-138">The only way around this is to create a Microsoft 365 group instead of a shared mailbox.</span></span> <span data-ttu-id="2e593-139">Outlook のグループは、共有メールボックスに似たものがあります。</span><span class="sxs-lookup"><span data-stu-id="2e593-139">A group in Outlook is like a shared mailbox.</span></span> <span data-ttu-id="2e593-140">2 つの比較については、「グループの比較」 [を参照してください](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2e593-140">For a comparison of the two, see [Compare groups](../create-groups/compare-groups.md).</span></span> <span data-ttu-id="2e593-141">グループの詳細については、「グループの詳細 [」を参照してください](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="2e593-141">To learn more about groups, see [Learn more about groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>


> [!NOTE]
> <span data-ttu-id="2e593-142">共有メールボックスにアクセスするには、ユーザーは Exchange Online ライセンスを持っている必要がありますが、共有メールボックスには別のライセンスは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="2e593-142">To access a shared mailbox, a user must have an Exchange Online license, but the shared mailbox doesn't require a separate license.</span></span> <span data-ttu-id="2e593-143">ライセンスがない場合は、共有メールボックスは 50 GB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="2e593-143">Without a license, shared mailboxes are limited to 50 GB.</span></span> <span data-ttu-id="2e593-144">サイズ制限を 100 GB に増やすには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving アドオンのライセンス付きの Exchange Online プラン 1 のライセンスを共有メールボックスに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e593-144">To increase the size limit to 100 GB, the shared mailbox must be assigned an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving add-on license.</span></span> <span data-ttu-id="2e593-145">これにより、無制限のアーカイブ記憶域を得るための自動拡張アーカイブを有効にできるようにもなります。</span><span class="sxs-lookup"><span data-stu-id="2e593-145">This will also let you enable auto-expanding archiving for an unlimited amount of archive storage capacity.</span></span> <span data-ttu-id="2e593-146">同様に、共有メールボックスに訴訟ホールドをかける場合は、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving アドオン ライセンス付帯のExchange Online Plan 1 ライセンスが共有メールボックスで必要です。</span><span class="sxs-lookup"><span data-stu-id="2e593-146">Similarly, if you want to place a shared mailbox on litigation hold, the shared mailbox must have an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving add-on license.</span></span> <span data-ttu-id="2e593-147">microsoft Defender for Office 365、Advanced eDiscovery、自動アイテム保持ポリシーなどの高度な機能を適用する場合は、それらの機能に対して共有メールボックスのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e593-147">If you want to apply advanced features such as Microsoft Defender for Office 365, Advanced eDiscovery, or automatic retention policies, the shared mailbox must be licensed for those features.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2e593-148">関連記事</span><span class="sxs-lookup"><span data-stu-id="2e593-148">Related articles</span></span>

[<span data-ttu-id="2e593-149">共有メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="2e593-149">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="2e593-150">共有メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="2e593-150">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="2e593-151">ユーザー メールボックスを共有メールボックスに変換する</span><span class="sxs-lookup"><span data-stu-id="2e593-151">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="2e593-152">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="2e593-152">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="2e593-153">共有メールボックスの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="2e593-153">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
