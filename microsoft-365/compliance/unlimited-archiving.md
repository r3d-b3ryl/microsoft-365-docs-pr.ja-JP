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
description: 自動拡張アーカイブについて説明します。これにより、Exchange Online メールボックスには無制限のアーカイブストレージが提供されます。
ms.openlocfilehash: 584502092e04822a91bf6d04c77daa277ed70547
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633402"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="db974-103">無制限アーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="db974-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="db974-104">Office 365 のアーカイブ メールボックスは、ユーザーに追加のメールボックス記憶領域を提供します。</span><span class="sxs-lookup"><span data-stu-id="db974-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="db974-105">ユーザーのアーカイブ メールボックスを有効にすると、最大 100 GB の追加記憶域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="db974-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="db974-106">以前は、100 GB の記憶域クォータに達したとき、組織は、Microsoft に問い合わせてアーカイブ メールボックス用の追加記憶領域を要求する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="db974-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="db974-107">このようなことはもうなくなります。</span><span class="sxs-lookup"><span data-stu-id="db974-107">That's no longer the case.</span></span>

<span data-ttu-id="db974-108">Microsoft 365 の無制限アーカイブ機能 (*自動拡張アーカイブ*と呼ばれます) は、アーカイブメールボックスに追加の記憶域を提供します。</span><span class="sxs-lookup"><span data-stu-id="db974-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="db974-109">アーカイブメールボックスの格納域の制限に達すると、Microsoft 365 によってアーカイブのサイズが自動的に増加します。つまり、ユーザーはメールボックスの記憶域を使用しなくなり、管理者はアーカイブメールボックスに追加の記憶域を要求する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="db974-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="db974-110">自動拡張アーカイブを有効にするための詳細な手順については、「 [Enable 無制限アーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db974-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="db974-111">アーカイブの自動拡張では、共有メールボックスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="db974-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="db974-112">共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="db974-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="db974-113">自動拡張アーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="db974-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="db974-114">前に説明したように、ユーザーのアーカイブ メールボックスが有効になっていると、追加のメールボックス記憶領域が作成されます。</span><span class="sxs-lookup"><span data-stu-id="db974-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="db974-115">自動拡張アーカイブが有効になっている場合、Microsoft 365 は定期的にアーカイブメールボックスのサイズをチェックします。</span><span class="sxs-lookup"><span data-stu-id="db974-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="db974-116">アーカイブメールボックスが格納域の制限に近づいた場合、Microsoft 365 によってアーカイブ用の追加の記憶域が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="db974-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="db974-117">ユーザーがこの追加の記憶域を使い超えた場合は、Microsoft 365 によってユーザーのアーカイブに格納領域が追加されます。</span><span class="sxs-lookup"><span data-stu-id="db974-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="db974-118">この処理は自動的に行われるので、管理者は追加のアーカイブ記憶域を要求したり、自動拡張アーカイブを管理したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db974-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="db974-119">処理の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="db974-119">Here's a quick overview of the process.</span></span>

![自動拡張アーカイブ プロセスの概要](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="db974-121">ユーザーのメールボックスまたは共有のメールボックスに対してアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="db974-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="db974-122">100 GB の記憶領域を持つアーカイブ メールボックスが作成され、アーカイブ メールボックスの警告のクォータが 90 GB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="db974-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="db974-123">管理者がメールボックスの自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="db974-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="db974-124">アーカイブメールボックス (回復可能なアイテムフォルダーを含む) が 90 GB に達すると、自動拡張アーカイブに変換され、Microsoft 365 はアーカイブに記憶域スペースを追加します。</span><span class="sxs-lookup"><span data-stu-id="db974-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="db974-125">追加記憶領域がプロビジョニングされるには、最大 30 日かかります。</span><span class="sxs-lookup"><span data-stu-id="db974-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="db974-126">メールボックスが保持されている場合、またはアイテム保持ポリシーに割り当てられている場合、自動拡張アーカイブが有効になっている場合、アーカイブメールボックスの記憶域クォータは 110 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="db974-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="db974-127">同様に、アーカイブ警告クォータは、100 GB に増やされます。</span><span class="sxs-lookup"><span data-stu-id="db974-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="db974-128">Microsoft 365 では、必要に応じてストレージ容量が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="db974-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db974-129">自動拡張アーカイブがサポートされているのは、個々のユーザーのメールボックスまたは 1 日あたりの成長率が 1 GB 未満の共有メールボックスのみです。</span><span class="sxs-lookup"><span data-stu-id="db974-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="db974-130">ユーザーのアーカイブ メールボックスは、そのユーザー専用です。</span><span class="sxs-lookup"><span data-stu-id="db974-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="db974-131">ジャーナリング、トランスポート ルール、または自動転送ルールを使用してメッセージをアーカイブ メールボックスにコピーすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="db974-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="db974-132">Microsoft は、ユーザーのアーカイブメールボックスを使用して他のユーザーのアーカイブデータを保存したり、不適切に使用されている場合には、無制限のアーカイブを拒否する権利を有します。</span><span class="sxs-lookup"><span data-stu-id="db974-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="db974-133">追加のアーカイブ記憶領域に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="db974-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="db974-134">自動拡張アーカイブストレージを効率的に使用するために、フォルダーが移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="db974-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="db974-135">Microsoft 365 は、アーカイブに追加の記憶域が追加されたときに移動するフォルダーを決定します。</span><span class="sxs-lookup"><span data-stu-id="db974-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="db974-136">フォルダーを移動すると、1つまたは複数のサブフォルダーが自動的に作成され、移動処理を容易にするために、元のフォルダーのアイテムがこれらのフォルダーに配布されることがあります。</span><span class="sxs-lookup"><span data-stu-id="db974-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="db974-137">Outlook でフォルダー一覧のアーカイブ部分を表示すると、これらのサブフォルダーは元のフォルダーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db974-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="db974-138">Microsoft 365 では、これらのサブフォルダー名を指定するために使用する名前付け規則は\*\* \<、フォルダー\>名 _yyyy (mmm dd, yyyy h_mm で作成さ\*\*れます) で、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="db974-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="db974-139">**yyyy** は、フォルダー内のメッセージが受信された年です。</span><span class="sxs-lookup"><span data-stu-id="db974-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="db974-140">**mmm dd, yyyy h_m** は、Office 365 によってサブフォルダーが作成された日時 (UTC 形式) であり、Outlook でのユーザーのタイム ゾーンと地域の設定に基づきます。</span><span class="sxs-lookup"><span data-stu-id="db974-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="db974-141">次のスクリーンショットは、メッセージが自動拡張アーカイブに移動される前と後のフォルダー一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="db974-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="db974-142">**追加記憶域が追加される前**</span><span class="sxs-lookup"><span data-stu-id="db974-142">**Before additional storage is added**</span></span>

![自動拡張アーカイブがプロビジョニングされる前のアーカイブ メールボックスのフォルダー一覧](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="db974-144">**追加記憶域が追加された後**</span><span class="sxs-lookup"><span data-stu-id="db974-144">**After additional storage is added**</span></span>

![自動拡張アーカイブがプロビジョニングされた後のアーカイブ メールボックスのフォルダー一覧](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="db974-146">前述したように、Microsoft 365 は、コンテンツを補助アーカイブに配布するために、アイテムをサブフォルダーに移動します (上記の命名規則に従って名前を付けます)。</span><span class="sxs-lookup"><span data-stu-id="db974-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="db974-147">ただし、サブフォルダーへのアイテムの移動は、必ずしもそうでない場合があります。</span><span class="sxs-lookup"><span data-stu-id="db974-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="db974-148">フォルダー全体を補助アーカイブに移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="db974-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="db974-149">この場合、フォルダーは元の名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="db974-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="db974-150">フォルダーが補助アーカイブに移動されたことは、Outlook のフォルダー一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="db974-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="db974-151">自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件</span><span class="sxs-lookup"><span data-stu-id="db974-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="db974-152">自動拡張アーカイブに保存されているメッセージにアクセスするには、ユーザーは次のいずれかの Outlook クライアントを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="db974-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="db974-153">Windows 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="db974-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="db974-154">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="db974-154">Outlook on the web</span></span>

- <span data-ttu-id="db974-155">Mac 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="db974-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="db974-156">Outlook または Outlook on the web を使って自動拡張アーカイブに保存されているメッセージにアクセスするときは、いくつかのことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db974-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="db974-157">自動拡張記憶域に移動されたものも含め、アーカイブ メールボックスの任意のフォルダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="db974-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="db974-158">フォルダー自体を検索することによってのみ、追加記憶域に移動されたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="db974-158">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="db974-159">つまり、フォルダー一覧でアーカイブ フォルダーを選択し、検索範囲として [**現在の​​フォルダー**] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db974-159">This means that you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="db974-160">同様に、自動拡張記憶域内のフォルダーにサブフォルダーがある場合は、各サブフォルダーを個別に検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db974-160">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span>

- <span data-ttu-id="db974-161">自動拡張アーカイブ内の Outlook のアイテム数および閲覧済み/未読数 (Outlook および Outlook on the web) は正しくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="db974-161">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="db974-162">自動拡張記憶域を参照しているサブフォルダー内のアイテムを削除することはできますが、フォルダー自体を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="db974-162">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="db974-163">[削除済みアイテムを復元] 機能を使って、自動拡張記憶域から削除されたアイテムを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="db974-163">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="db974-164">自動拡張アーカイブとその他のコンプライアンス機能</span><span class="sxs-lookup"><span data-stu-id="db974-164">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="db974-165">このセクションでは、自動拡張アーカイブとその他のコンプライアンスおよびデータガバナンス機能の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="db974-165">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="db974-166">**電子情報開示:** コンテンツ検索やインプレース電子情報開示などの電子情報開示ツールを使用すると、自動拡張アーカイブ内の追加のストレージ領域も検索されます。</span><span class="sxs-lookup"><span data-stu-id="db974-166">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="db974-167">**保持:** Exchange Online または電子情報開示センターでの訴訟ホールドなどのツールを使用してメールボックスを保留にすると、自動拡張されたアーカイブにあるコンテンツも保持に配置されます。</span><span class="sxs-lookup"><span data-stu-id="db974-167">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="db974-168">**メッセージング レコード管理 (MRM)**: Exchange Online の MRM 削除ポリシーを使って期限切れのメールボックス アイテムを完全に削除した場合、自動拡張アーカイブにある期限切れアイテムも削除されます。</span><span class="sxs-lookup"><span data-stu-id="db974-168">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="db974-169">**サービスのインポート:** Office 365 インポートサービスを使用して、PST ファイルをユーザーの自動拡張アーカイブにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="db974-169">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="db974-170">PST ファイルの最大 100 GB のデータをユーザーのアーカイブ メールボックスにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="db974-170">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="db974-171">詳細情報</span><span class="sxs-lookup"><span data-stu-id="db974-171">More information</span></span>

<span data-ttu-id="db974-172">自動拡張アーカイブの技術的な詳細については、「 [Microsoft 365: 自動拡張アーカイブ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db974-172">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
