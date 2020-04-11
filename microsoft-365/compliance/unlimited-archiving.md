---
title: Office 365 での無制限アーカイブの概要
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
description: Exchange Online メールボックスに無制限のアーカイブ記憶域を提供する Office 365 の自動拡張アーカイブについて説明します。
ms.openlocfilehash: eb7d75e87ac26dcf4f920b4858bc2f23862b0366
ms.sourcegitcommit: 7bb340f6b47378bcd1c6e770dc975931470bbc26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/10/2020
ms.locfileid: "43225966"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="d2d9a-103">Office 365 での無制限アーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="d2d9a-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="d2d9a-104">Office 365 のアーカイブ メールボックスは、ユーザーに追加のメールボックス記憶領域を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="d2d9a-105">ユーザーのアーカイブ メールボックスを有効にすると、最大 100 GB の追加記憶域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="d2d9a-106">以前は、100 GB の記憶域クォータに達したとき、組織は、Microsoft に問い合わせてアーカイブ メールボックス用の追加記憶領域を要求する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="d2d9a-107">このようなことはもうなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-107">That's no longer the case.</span></span>

<span data-ttu-id="d2d9a-108">Office 365 の無制限アーカイブ機能 (*自動拡張アーカイブ*と呼ばれます) は、アーカイブメールボックスに追加のストレージを提供します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="d2d9a-109">アーカイブ メールボックスの記憶域クォータに達した場合、Office 365 はアーカイブのサイズを自動的に増やします。これにより、ユーザーはメールボックスの記憶領域を使い切ることがなくなり、管理者はアーカイブ メールボックス用の追加記憶域を要求する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-109">When the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="d2d9a-110">自動拡張アーカイブを有効にする詳しい手順については、「[Office 365 で無制限アーカイブを有効にする](enable-unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d2d9a-111">アーカイブの自動拡張では、共有メールボックスもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="d2d9a-112">共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="d2d9a-113">自動拡張アーカイブのしくみ</span><span class="sxs-lookup"><span data-stu-id="d2d9a-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="d2d9a-114">前に説明したように、ユーザーのアーカイブ メールボックスが有効になっていると、追加のメールボックス記憶領域が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="d2d9a-115">自動拡張アーカイブを有効にすると、Office 365 は定期的にアーカイブ メールボックスのサイズを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="d2d9a-116">アーカイブ メールボックスが記憶域の制限に近づくと、Office 365 はアーカイブに対する追加の記憶領域を自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="d2d9a-117">ユーザーがこの追加記憶領域を使い切ると、Office 365 はユーザーのアーカイブの記憶領域をさらに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-117">If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="d2d9a-118">この処理は自動的に行われるので、管理者は追加のアーカイブ記憶域を要求したり、自動拡張アーカイブを管理したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="d2d9a-119">処理の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-119">Here's a quick overview of the process.</span></span>

![自動拡張アーカイブ プロセスの概要](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="d2d9a-121">ユーザーのメールボックスまたは共有のメールボックスに対してアーカイブが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="d2d9a-122">100 GB の容量のアーカイブメールボックスが作成され (*メインアーカイブ*とも呼ばれます)、アーカイブメールボックスの警告クォータは 90 GB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-122">An archive mailbox with 100 GB of storage space is created (also called the *main archive*), and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="d2d9a-123">管理者がメールボックスの自動拡張アーカイブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="d2d9a-124">アーカイブ メールボックス ([回復可能なアイテム] フィルダーを含む) が 90 GB に達すると、自動拡張アーカイブに変換されて、Office 365 はアーカイブに記憶領域を追加します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="d2d9a-125">この追加のアーカイブ記憶域は、*補助アーカイブ*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-125">This additional archive storage is also called the *auxiliary archive*.</span></span> <span data-ttu-id="d2d9a-126">追加記憶領域がプロビジョニングされるには、最大 30 日かかります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-126">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d2d9a-127">メールボックスが保持されている場合、または Office 365 アイテム保持ポリシーに割り当てられている場合、自動拡張アーカイブが有効になっていると、アーカイブメールボックスの記憶域クォータは 110 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-127">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="d2d9a-128">同様に、アーカイブ警告クォータは、100 GB に増やされます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-128">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="d2d9a-129">Office 365 は、必要に応じて、補助アーカイブに格納スペースを自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-129">Office 365 automatically adds more storage space to the auxiliary archive when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2d9a-130">自動拡張アーカイブは、個々のユーザー (または共有メールボックス) に使用され、1日あたり 1 GB を超える成長率を持つメールボックスに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-130">Auto-expanding archiving is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="d2d9a-131">ユーザーのアーカイブ メールボックスは、そのユーザー専用です。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-131">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="d2d9a-132">ジャーナリング、トランスポート ルール、または自動転送ルールを使用してメッセージをアーカイブ メールボックスにコピーすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-132">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="d2d9a-133">Microsoft は、ユーザーのアーカイブメールボックスを使用して他のユーザーのアーカイブデータを保存したり、不適切な使用をしたりする場合に、無制限のアーカイブを拒否する権利を留保します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-133">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="d2d9a-134">追加のアーカイブ記憶領域に移動されるもの</span><span class="sxs-lookup"><span data-stu-id="d2d9a-134">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="d2d9a-135">自動拡張アーカイブストレージを効率的に使用するために、フォルダーが移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-135">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="d2d9a-136">Office 365 では、追加記憶域がアーカイブに追加されたときに、どのフォルダーを移動するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-136">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="d2d9a-137">フォルダーを移動すると、1つまたは複数のサブフォルダーが自動的に作成され、移動処理を容易にするために、元のフォルダーのアイテムがこれらのフォルダーに配布されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-137">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="d2d9a-138">Outlook でフォルダー一覧のアーカイブ部分を表示すると、これらのサブフォルダーは元のフォルダーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-138">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="d2d9a-139">Office 365 がこれらのサブフォルダーに名前を付けるために使用する名前付け規則は\*\* \<、フォルダー\>名 _yyyy (mmm dd, yyyy h_mm で作成)\*\* で、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-139">The naming convention that Office 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="d2d9a-140">**yyyy** は、フォルダー内のメッセージが受信された年です。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-140">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="d2d9a-141">**mmm dd, yyyy h_m** は、Office 365 によってサブフォルダーが作成された日時 (UTC 形式) であり、Outlook でのユーザーのタイム ゾーンと地域の設定に基づきます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-141">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="d2d9a-142">次のスクリーンショットは、メッセージが自動拡張アーカイブに移動される前と後のフォルダー一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-142">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="d2d9a-143">**追加記憶域が追加される前**</span><span class="sxs-lookup"><span data-stu-id="d2d9a-143">**Before additional storage is added**</span></span>

![自動拡張アーカイブがプロビジョニングされる前のアーカイブ メールボックスのフォルダー一覧](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="d2d9a-145">**追加記憶域が追加された後**</span><span class="sxs-lookup"><span data-stu-id="d2d9a-145">**After additional storage is added**</span></span>

![自動拡張アーカイブがプロビジョニングされた後のアーカイブ メールボックスのフォルダー一覧](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="d2d9a-147">前述したように、Office 365 はアイテムをサブフォルダーに移動します (上記の命名規則に従って名前を付けます)。コンテンツを補助アーカイブに配布するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-147">As previously described, Office 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="d2d9a-148">ただし、サブフォルダーへのアイテムの移動は、必ずしもそうでない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-148">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="d2d9a-149">フォルダー全体を補助アーカイブに移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-149">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="d2d9a-150">この場合、フォルダーは元の名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-150">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="d2d9a-151">フォルダーが補助アーカイブに移動されたことは、Outlook のフォルダー一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-151">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="d2d9a-152">自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件</span><span class="sxs-lookup"><span data-stu-id="d2d9a-152">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="d2d9a-153">自動拡張アーカイブに保存されているメッセージにアクセスするには、ユーザーは次のいずれかの Outlook クライアントを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-153">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="d2d9a-154">Windows 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="d2d9a-154">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="d2d9a-155">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="d2d9a-155">Outlook on the web</span></span>

- <span data-ttu-id="d2d9a-156">Mac 版の Outlook 2016、Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="d2d9a-156">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="d2d9a-157">Outlook または web 上の Outlook を使用して、自動拡張アーカイブに格納されているメッセージにアクセスする場合は、以下の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-157">Consider the following when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="d2d9a-158">自動拡張記憶域に移動されたものも含め、アーカイブ メールボックスの任意のフォルダーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-158">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="d2d9a-159">フォルダー自体を検索することによってのみ、追加記憶域に移動されたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-159">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="d2d9a-160">つまり、フォルダー一覧でアーカイブ フォルダーを選び、検索範囲として [**現在の​​フォルダー**] オプションを選ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-160">This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="d2d9a-161">同様に、自動拡張記憶域内のフォルダーにサブフォルダーがある場合は、各サブフォルダーを個別に検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-161">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span>

- <span data-ttu-id="d2d9a-162">自動拡張記憶域を参照しているサブフォルダー内のアイテムを削除することはできますが、フォルダー自体を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-162">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span> <span data-ttu-id="d2d9a-163">メールボックスに対して自動拡張アーカイブが有効になっている場合は、メインアーカイブ内のすべてのフォルダーや自動拡張ストレージ領域内のすべてのフォルダーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-163">In fact when auto-expanding archiving is enabled for a mailbox, you can't delete any folders in the main archive or in an auto-expanded storage area.</span></span>

- <span data-ttu-id="d2d9a-164">自動拡張アーカイブ内の Outlook のアイテム数および閲覧済み/未読数 (Outlook および Outlook on the web) は正しくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-164">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="d2d9a-165">[削除済みアイテムを復元] 機能を使って、自動拡張記憶域から削除されたアイテムを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-165">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="d2d9a-166">自動拡張アーカイブと Office 365 のその他の法令遵守機能</span><span class="sxs-lookup"><span data-stu-id="d2d9a-166">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="d2d9a-167">ここでは、自動拡張アーカイブと、Office 365 のその他の法令遵守およびデータ ガバナンス機能の間の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-167">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>

- <span data-ttu-id="d2d9a-168">**電子情報開示:** コンテンツ検索、コア電子情報開示、高度な電子情報開示などの Office 365 電子情報開示ツールを使用すると、自動拡張アーカイブ内の追加のストレージ領域も検索されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-168">**eDiscovery:** When you use an Office 365 eDiscovery tool, such as Content Search, Core eDiscovery, or Advanced eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="d2d9a-169">**保持:** セキュリティ/コンプライアンスセンターでの Exchange Online または電子情報開示の保持、およびアイテム保持ポリシーの訴訟ホールドなどのツールを使用してメールボックスを保留にすると、自動展開されたアーカイブ内にあるコンテンツも保持に配置されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-169">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="d2d9a-170">**メッセージング レコード管理 (MRM)**: Exchange Online の MRM 削除ポリシーを使って期限切れのメールボックス アイテムを完全に削除した場合、自動拡張アーカイブにある期限切れアイテムも削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-170">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="d2d9a-171">**サービスのインポート:** Office 365 インポートサービスを使用して、PST ファイルをユーザーの自動拡張アーカイブにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-171">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="d2d9a-172">PST ファイルの最大 100 GB のデータをユーザーのアーカイブ メールボックスにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-172">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="d2d9a-173">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d2d9a-173">More information</span></span>

<span data-ttu-id="d2d9a-174">自動拡張アーカイブについての技術的な詳細については、「[Office 365: 自動拡張アーカイブに関する FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2d9a-174">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
