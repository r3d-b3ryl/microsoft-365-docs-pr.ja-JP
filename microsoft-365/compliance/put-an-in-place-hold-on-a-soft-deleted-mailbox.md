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
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925523"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="a6f2a-103">Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する</span><span class="sxs-lookup"><span data-stu-id="a6f2a-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="a6f2a-p101">削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p101">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6f2a-106">メールボックス コンテンツを保持するためのさまざまな方法で投資を続ける中で、Exchange 管理センター (EAC) で In-Place Holds の削除を発表します。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="a6f2a-107">2020 年 7 月 1 日以降、Exchange Online で新しいインプレース ホールドを作成することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="a6f2a-108">ただし、EAC または PowerShell の **Set-MailboxSearch** コマンドレットを使用して、EAC In-Place保持を管理Exchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="a6f2a-109">ただし、2020 年 10 月 1 日から、保留の管理In-Placeされます。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="a6f2a-110">削除できるのは、EAC または **Remove-MailboxSearch コマンドレットを使用する場合** のみです。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="a6f2a-111">インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="a6f2a-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="a6f2a-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="a6f2a-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="a6f2a-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="a6f2a-114">What can you do?</span><span class="sxs-lookup"><span data-stu-id="a6f2a-114">What can you do?</span></span> <span data-ttu-id="a6f2a-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="a6f2a-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="a6f2a-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="a6f2a-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="a6f2a-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="a6f2a-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="a6f2a-118">メールボックスを非アクティブにした後は、Exchange Online の In-Place 電子情報開示、セキュリティ & コンプライアンス センターのコンテンツ検索、SharePoint Online の電子情報開示センターを使用してメールボックスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a6f2a-p104">Exchange Online では、削除済みメールボックス (回復可能) は、メールボックスが削除されていても、特定の保存期間内であれば回復することができます。Exchange Online の削除済みメールボックス (回復可能) の保存期間は 30 日です。つまり、削除してから 30 日以内なら、メールボックスは復元できます (または、非アクティブなメールボックスにできます)。30 日が経過すると、削除済みメールボックスには完全削除のマークが付けられ、回復または非アクティブにすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p104">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="a6f2a-123">ユーザー保持In-Place要件</span><span class="sxs-lookup"><span data-stu-id="a6f2a-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="a6f2a-p105">削除済みメールボックス (回復可能) にインプレース ホールドを設定するには、Windows PowerShell で **New-MailboxSearch** コマンドレットを使う必要があります。Exchange 管理センター (EAC) または SharePoint Online の電子情報開示センターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p105">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="a6f2a-126">Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a6f2a-127">組織内の削除済みメールボックス (回復可能) の識別情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="a6f2a-128">非アクティブなメールボックスの詳細については、「アクティブでないメールボックスの概要」を参照[Office 365。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a6f2a-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="a6f2a-129">削除済みメールボックス (回復可能) にインプレース ホールドを適用し、非アクティブなメールボックスにする</span><span class="sxs-lookup"><span data-stu-id="a6f2a-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="a6f2a-p106">**New-MailboxSearch** コマンドレットを使用して、削除済みメールボックス (回復可能) を非アクティブなメールボックスにします。詳細については、「 [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p106">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>
  
1. <span data-ttu-id="a6f2a-132">削除済みメールボックス (回復可能) のプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="a6f2a-p107">上記のコマンドでは、 **DistinguishedName** または **ExchangeGuid** プロパティの値を使用して削除済みメールボックス (回復可能) を識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと削除済みメールボックス (回復可能) でプライマリ SMTP アドレスが等しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="a6f2a-p108">インプレース ホールドを作成し、削除済みメールボックス (回復可能) に適用します。この例では、保存期間が指定されていません。この場合、アイテムは無制限に、または非アクティブなメールボックスからホールドが解除されるまで保存されます。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p108">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="a6f2a-p109">インプレース ホールドを作成するときに、保存期間を指定することもできます。この例では、非アクティブなメールボックスのアイテムを約 7 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p109">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="a6f2a-140">しばらくしてから、次のコマンドのいずれかを実行して削除済みメールボックス (回復可能) が、非アクティブなメールボックスになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="a6f2a-141">または</span><span class="sxs-lookup"><span data-stu-id="a6f2a-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="a6f2a-142">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a6f2a-142">More information</span></span>

<span data-ttu-id="a6f2a-p110">削除済みメールボックス (回復可能) を非アクティブなメールボックスにしてから、いろいろな方法でメールボックスを管理することができます。詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f2a-p110">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="a6f2a-145">非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="a6f2a-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="a6f2a-146">非アクティブなメールボックスを回復する</span><span class="sxs-lookup"><span data-stu-id="a6f2a-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="a6f2a-147">非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="a6f2a-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="a6f2a-148">[非アクティブなメールボックスを削除](delete-an-inactive-mailbox.md) する (保留リストを削除して)</span><span class="sxs-lookup"><span data-stu-id="a6f2a-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>