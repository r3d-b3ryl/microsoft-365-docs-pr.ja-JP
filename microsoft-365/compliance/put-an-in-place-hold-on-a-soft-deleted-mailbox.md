---
title: Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: 削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818866"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="deb15-103">Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="deb15-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="deb15-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span><span class="sxs-lookup"><span data-stu-id="deb15-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="deb15-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="deb15-106">メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるため、Exchange 管理センター (EAC) でのインプレースホールドの廃止を発表しています。</span><span class="sxs-lookup"><span data-stu-id="deb15-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="deb15-107">2020年7月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="deb15-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="deb15-108">ただし、EAC でインプレースホールドを管理することも、Exchange Online PowerShell で**get-mailboxsearch**コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="deb15-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="deb15-109">ただし、2020年10月1日以降、インプレースホールドを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="deb15-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="deb15-110">これらのアドインは、EAC または**get-mailboxsearch**コマンドレットを使用して削除します。</span><span class="sxs-lookup"><span data-stu-id="deb15-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="deb15-111">インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb15-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="deb15-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="deb15-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="deb15-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="deb15-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="deb15-114">What can you do?</span><span class="sxs-lookup"><span data-stu-id="deb15-114">What can you do?</span></span> <span data-ttu-id="deb15-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="deb15-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="deb15-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="deb15-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="deb15-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="deb15-118">メールボックスが非アクティブになった後は、Exchange Online のインプレース電子情報開示、セキュリティ & コンプライアンスセンターのコンテンツ検索、または SharePoint Online の電子情報開示センターを使用して、メールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="deb15-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="deb15-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span><span class="sxs-lookup"><span data-stu-id="deb15-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="deb15-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span><span class="sxs-lookup"><span data-stu-id="deb15-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="deb15-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span><span class="sxs-lookup"><span data-stu-id="deb15-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="deb15-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span><span class="sxs-lookup"><span data-stu-id="deb15-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="deb15-123">インプレース保持の要件</span><span class="sxs-lookup"><span data-stu-id="deb15-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="deb15-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="deb15-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="deb15-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="deb15-126">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb15-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="deb15-127">組織内の削除済みメールボックス (回復可能) の識別情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="deb15-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="deb15-128">非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックスの概要](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb15-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="deb15-129">削除済みメールボックス (回復可能) にインプレース ホールドを適用し、非アクティブなメールボックスにする</span><span class="sxs-lookup"><span data-stu-id="deb15-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="deb15-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="deb15-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="deb15-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="deb15-132">削除済みメールボックス (回復可能) のプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="deb15-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="deb15-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="deb15-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span><span class="sxs-lookup"><span data-stu-id="deb15-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="deb15-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="deb15-136">In this example, no hold duration is specified.</span><span class="sxs-lookup"><span data-stu-id="deb15-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="deb15-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="deb15-138">You can also specify a hold duration when you create the In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="deb15-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="deb15-139">This example holds items in the inactive mailbox for approximately 7 years.</span><span class="sxs-lookup"><span data-stu-id="deb15-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="deb15-140">しばらくしてから、次のコマンドのいずれかを実行して削除済みメールボックス (回復可能) が、非アクティブなメールボックスになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="deb15-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="deb15-141">または</span><span class="sxs-lookup"><span data-stu-id="deb15-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="deb15-142">詳細情報</span><span class="sxs-lookup"><span data-stu-id="deb15-142">More information</span></span>

<span data-ttu-id="deb15-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span><span class="sxs-lookup"><span data-stu-id="deb15-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="deb15-144">For more information, see:</span><span class="sxs-lookup"><span data-stu-id="deb15-144">For more information, see:</span></span>
  
- [<span data-ttu-id="deb15-145">非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="deb15-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="deb15-146">非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="deb15-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="deb15-147">非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="deb15-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="deb15-148">[非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)(保留リストを削除する)</span><span class="sxs-lookup"><span data-stu-id="deb15-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
