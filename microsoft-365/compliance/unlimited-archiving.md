---
title: 無制限アーカイブの概要
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online メールボックスに無制限のアーカイブ ストレージを提供する自動拡張アーカイブについて説明します。
ms.openlocfilehash: 9692ba27c64f41ac584bb4008a8b860daab031f5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029433"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="be3de-103">無制限アーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="be3de-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="be3de-104">Office 365 のアーカイブ メールボックスは、ユーザーに追加のメールボックス記憶領域を提供します。</span><span class="sxs-lookup"><span data-stu-id="be3de-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="be3de-105">ユーザーのアーカイブ メールボックスを有効にすると、最大 100 GB の追加記憶域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="be3de-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="be3de-106">以前は、100 GB の記憶域クォータに達したとき、組織は、Microsoft に問い合わせてアーカイブ メールボックス用の追加記憶領域を要求する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="be3de-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="be3de-107">このようなことはもうなくなります。</span><span class="sxs-lookup"><span data-stu-id="be3de-107">That's no longer the case.</span></span>

<span data-ttu-id="be3de-108">Microsoft 365 の無制限アーカイブ機能 (自動拡張 *アーカイブと呼* ばれる) は、アーカイブ メールボックスに追加の記憶域を提供します。</span><span class="sxs-lookup"><span data-stu-id="be3de-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="be3de-109">アーカイブ メールボックスの記憶域クォータに達すると、Microsoft 365 はアーカイブのサイズを自動的に増やします。つまり、ユーザーはメールボックスの記憶領域を使い切らないので、管理者はアーカイブ メールボックスの追加の記憶域を要求する必要がなされます。</span><span class="sxs-lookup"><span data-stu-id="be3de-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="be3de-110">自動拡張アーカイブを有効にする詳しい手順については、「無制限アーカイブを有効にする」を [参照してください](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="be3de-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="be3de-111">アーカイブの自動拡張では、共有メールボックスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="be3de-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="be3de-112">共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="be3de-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="be3de-113">自動拡張アーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="be3de-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="be3de-114">前に説明したように、ユーザーのアーカイブ メールボックスが有効になっていると、追加のメールボックス記憶領域が作成されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="be3de-115">自動拡張アーカイブを有効にすると、Microsoft 365 はアーカイブ メールボックスのサイズを定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="be3de-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="be3de-116">アーカイブ メールボックスが記憶域の制限に近くなると、Microsoft 365 はアーカイブ用の追加の記憶領域を自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="be3de-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="be3de-117">ユーザーが追加の記憶領域を使い切った場合、Microsoft 365 はユーザーのアーカイブにより多くの記憶領域を追加します。</span><span class="sxs-lookup"><span data-stu-id="be3de-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="be3de-118">この処理は自動的に行われるので、管理者は追加のアーカイブ記憶域を要求したり、自動拡張アーカイブを管理したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="be3de-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="be3de-119">処理の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="be3de-119">Here's a quick overview of the process.</span></span>

![自動拡張アーカイブ プロセスの概要](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="be3de-121">ユーザーのメールボックスまたは共有のメールボックスに対してアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="be3de-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="be3de-122">100 GB の記憶領域を持つアーカイブ メールボックスが作成され、アーカイブ メールボックスの警告のクォータが 90 GB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="be3de-123">管理者がメールボックスの自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="be3de-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="be3de-124">アーカイブ メールボックス (回復可能なアイテム フォルダーを含む) が 90 GB に達すると、自動拡張アーカイブに変換され、Microsoft 365 はアーカイブに記憶領域を追加します。</span><span class="sxs-lookup"><span data-stu-id="be3de-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="be3de-125">追加記憶領域がプロビジョニングされるには、最大 30 日かかります。</span><span class="sxs-lookup"><span data-stu-id="be3de-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="be3de-126">メールボックスが保留にされている場合、またはアイテム保持ポリシーに割り当てられている場合、自動拡張アーカイブが有効な場合、アーカイブ メールボックスの記憶域クォータは 110 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="be3de-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="be3de-127">同様に、アーカイブ警告クォータは、100 GB に増やされます。</span><span class="sxs-lookup"><span data-stu-id="be3de-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="be3de-128">Microsoft 365 では、必要に応じて記憶域が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be3de-129">自動拡張アーカイブがサポートされているのは、個々のユーザーのメールボックスまたは 1 日あたりの成長率が 1 GB 未満の共有メールボックスのみです。</span><span class="sxs-lookup"><span data-stu-id="be3de-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="be3de-130">ユーザーのアーカイブ メールボックスは、そのユーザー専用です。</span><span class="sxs-lookup"><span data-stu-id="be3de-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="be3de-131">ジャーナリング、トランスポート ルール、または自動転送ルールを使用してメッセージをアーカイブ メールボックスにコピーすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="be3de-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="be3de-132">Microsoft は、ユーザーのアーカイブ メールボックスを使用して他のユーザーのアーカイブ データを格納したり、不適切な使用をした場合に、無制限アーカイブを拒否する権利を保持します。</span><span class="sxs-lookup"><span data-stu-id="be3de-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="be3de-133">追加のアーカイブ記憶領域に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="be3de-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="be3de-134">自動拡張アーカイブ ストレージを効率的に使用するために、フォルダーが移動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="be3de-135">Microsoft 365 は、アーカイブに追加の記憶域が追加された場合に移動するフォルダーを決定します。</span><span class="sxs-lookup"><span data-stu-id="be3de-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="be3de-136">フォルダーを移動すると、1 つ以上のサブフォルダーが自動的に作成され、元のフォルダーのアイテムがこれらのフォルダーに配布され、移動プロセスが容易になります。</span><span class="sxs-lookup"><span data-stu-id="be3de-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="be3de-137">Outlook でフォルダー一覧のアーカイブ部分を表示すると、これらのサブフォルダーは元のフォルダーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="be3de-138">これらのサブフォルダーの名前を指定するために Microsoft 365 が使用する名前付け規則は _yyyy **\<folder name\> (mmm dd、yyyy h_mm)** で作成され、次の場所に設定されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="be3de-139">**yyyy** は、フォルダー内のメッセージが受信された年です。</span><span class="sxs-lookup"><span data-stu-id="be3de-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="be3de-140">**mmm dd, yyyy h_m** は、Office 365 によってサブフォルダーが作成された日時 (UTC 形式) であり、Outlook でのユーザーのタイム ゾーンと地域の設定に基づきます。</span><span class="sxs-lookup"><span data-stu-id="be3de-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="be3de-141">次のスクリーンショットは、メッセージが自動拡張アーカイブに移動される前と後のフォルダー一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="be3de-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="be3de-142">**追加記憶域が追加される前**</span><span class="sxs-lookup"><span data-stu-id="be3de-142">**Before additional storage is added**</span></span>

![自動拡張アーカイブがプロビジョニングされる前のアーカイブ メールボックスのフォルダー一覧](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="be3de-144">**追加記憶域が追加された後**</span><span class="sxs-lookup"><span data-stu-id="be3de-144">**After additional storage is added**</span></span>

![自動拡張アーカイブがプロビジョニングされた後のアーカイブ メールボックスのフォルダー一覧](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="be3de-146">前に説明したように、Microsoft 365 は、補助アーカイブにコンテンツを配布するために、アイテムをサブフォルダーに移動します (また、前述の名前付け規則を使用して名前を付ける)。</span><span class="sxs-lookup"><span data-stu-id="be3de-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="be3de-147">ただし、アイテムをサブフォルダーに移動しても、常にそうなるとは限りない場合があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="be3de-148">フォルダー全体が補助アーカイブに移動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="be3de-149">この場合、フォルダーは元の名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="be3de-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="be3de-150">フォルダーが補助アーカイブに移動されたのは、Outlook のフォルダー一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="be3de-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="be3de-151">自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件</span><span class="sxs-lookup"><span data-stu-id="be3de-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="be3de-152">自動拡張アーカイブに保存されているメッセージにアクセスするには、ユーザーは次のいずれかの Outlook クライアントを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="be3de-153">Windows 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="be3de-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="be3de-154">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="be3de-154">Outlook on the web</span></span>

- <span data-ttu-id="be3de-155">Mac 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="be3de-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="be3de-156">Outlook または Outlook on the web を使って自動拡張アーカイブに保存されているメッセージにアクセスするときは、いくつかのことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="be3de-157">自動拡張記憶域に移動されたものも含め、アーカイブ メールボックスの任意のフォルダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="be3de-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="be3de-158">自動拡張アーカイブの検索は、Outlook for the web で使用できます。</span><span class="sxs-lookup"><span data-stu-id="be3de-158">Search for auto-expanded archiving is available in Outlook for the web.</span></span> <span data-ttu-id="be3de-159">オンライン アーカイブと同様に、現在のフォルダー自体を検索することでのみ、追加の記憶域に移動されたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="be3de-159">Similar to Online Archive, you can search for items that were moved to an additional storage area only by searching the current folder itself.</span></span> <span data-ttu-id="be3de-160">つまり、フォルダー一覧でアーカイブ フォルダーを選択し、検索範囲として 1 つのフォルダーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-160">This means that you must select the archive folder in the folder list, and then select a single folder as your search scope.</span></span> <span data-ttu-id="be3de-161">同様に、自動拡張ストレージ領域内のフォルダーにサブフォルダーが含まれている場合は、各サブフォルダーを個別に検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be3de-161">Similarly, if a folder in an auto-expanded storage area contains subfolders, you must search each subfolder separately.</span></span>
- <span data-ttu-id="be3de-162">自動拡張アーカイブ検索は、現在のチャネル (プレビュー) の Outlook デスクトップで利用できます。</span><span class="sxs-lookup"><span data-stu-id="be3de-162">Auto-expanded archive search is available in Outlook Desktop in Current Channel (Preview).</span></span> <span data-ttu-id="be3de-163">このプレビューでは、現在のメールボックススコープが使用可能なので、自動拡張アーカイブを検索できます。</span><span class="sxs-lookup"><span data-stu-id="be3de-163">Within this preview, the Current Mailbox scope is available, thus allowing you to search the auto-expanded archive.</span></span> <span data-ttu-id="be3de-164">この機能および他の Microsoft Search サポート機能の詳細については [、「Exchange Online](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045)に接続された Outlook for Windows で Microsoft Search を利用する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be3de-164">For more information about this and other Microsoft Search support features, see [How Outlook for Windows connected to Exchange Online utilizes Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045).</span></span> 

- <span data-ttu-id="be3de-165">自動拡張アーカイブ内の Outlook のアイテム数および閲覧済み/未読数 (Outlook および Outlook on the web) は正しくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="be3de-165">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="be3de-166">自動拡張記憶域を参照しているサブフォルダー内のアイテムを削除することはできますが、フォルダー自体を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="be3de-166">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="be3de-167">[削除済みアイテムを復元] 機能を使って、自動拡張記憶域から削除されたアイテムを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="be3de-167">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="be3de-168">自動拡張アーカイブおよび他のコンプライアンス機能</span><span class="sxs-lookup"><span data-stu-id="be3de-168">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="be3de-169">このセクションでは、自動拡張アーカイブと他のコンプライアンスおよびデータ ガバナンス機能の間の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="be3de-169">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="be3de-170">**電子情報開示:** コンテンツ検索や In-Place 電子情報開示などの電子情報開示ツールを使用すると、自動拡張アーカイブ内の追加の記憶域も検索されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-170">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="be3de-171">**保持期間:** Exchange Online の訴訟ホールドや、セキュリティ/コンプライアンス センターの電子情報開示ケースの保留とアイテム保持ポリシーなどのツールを使用してメールボックスを保留にした場合、自動拡張アーカイブにあるコンテンツも保持の対象にされます。</span><span class="sxs-lookup"><span data-stu-id="be3de-171">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="be3de-172">**メッセージング レコード管理 (MRM)**: Exchange Online の MRM 削除ポリシーを使って期限切れのメールボックス アイテムを完全に削除した場合、自動拡張アーカイブにある期限切れアイテムも削除されます。</span><span class="sxs-lookup"><span data-stu-id="be3de-172">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="be3de-173">**インポート サービス:** Office 365 インポート サービスを使用して、PST ファイルをユーザーの自動拡張アーカイブにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="be3de-173">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="be3de-174">PST ファイルの最大 100 GB のデータをユーザーのアーカイブ メールボックスにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="be3de-174">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="be3de-175">詳細情報</span><span class="sxs-lookup"><span data-stu-id="be3de-175">More information</span></span>

<span data-ttu-id="be3de-176">自動拡張アーカイブの技術的な詳細については [、「Microsoft 365: 自動](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)拡張アーカイブに関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be3de-176">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).</span></span>
