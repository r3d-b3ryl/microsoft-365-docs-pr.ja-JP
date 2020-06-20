---
title: 非アクティブなメールボックスを削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 の非アクティブなメールボックスの内容を保持する必要がなくなった場合は、非アクティブなメールボックスを完全に削除することができます。
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817896"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="169c0-103">非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="169c0-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="169c0-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="169c0-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span><span class="sxs-lookup"><span data-stu-id="169c0-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="169c0-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="169c0-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="169c0-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="169c0-108">さらに、(Office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成された) アイテム保持ポリシーは、非アクティブなメールボックスに適用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="169c0-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="169c0-109">非アクティブなメールボックスを削除するには、保留リストとアイテム保持ポリシーをすべて削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="169c0-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="169c0-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span><span class="sxs-lookup"><span data-stu-id="169c0-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="169c0-111">メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるので、Exchange 管理センターでのインプレースホールドの廃止を発表しています。</span><span class="sxs-lookup"><span data-stu-id="169c0-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="169c0-112">つまり、非アクティブなメールボックスを作成するには、訴訟ホールドとアイテム保持ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="169c0-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="169c0-113">2020年7月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="169c0-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="169c0-114">ただし、非アクティブなメールボックスに設定されたインプレースホールドの保持期間を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="169c0-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="169c0-115">ただし、2020年10月1日以降、保持期間を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="169c0-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="169c0-116">インプレースホールドを削除しても、非アクティブなメールボックスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="169c0-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="169c0-117">インプレース保持されている既存の非アクティブなメールボックスは、保留が解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="169c0-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="169c0-118">インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="169c0-119">保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="169c0-120">非アクティブなメールボックスを削除する前に</span><span class="sxs-lookup"><span data-stu-id="169c0-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="169c0-121">非アクティブなメールボックスから訴訟ホールドを削除するには、Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="169c0-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="169c0-122">Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="169c0-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="169c0-123">詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="169c0-124">非アクティブなメールボックスからインプレース ホールドを削除する場合は、Exchange Online PowerShell または EAC を使用できます。</span><span class="sxs-lookup"><span data-stu-id="169c0-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="169c0-125">非アクティブなメールボックスの内容は、ホールドを解除して、非アクティブなメールボックスを削除する前に別のメールボックスにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="169c0-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="169c0-126">詳細については、「 [Office の非アクティブなメールボックスを復元する 365](restore-an-inactive-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="169c0-127">非アクティブなメールボックスからホールドまたはアイテム保持ポリシーを削除すると、そのメールボックスの回復可能な削除によって削除されたメールボックスの保存期間が切れた場合、そのメールボックスは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="169c0-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="169c0-128">削除後に回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="169c0-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="169c0-129">ホールドを解除する前に、メールボックスの中身が不要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="169c0-130">非アクティブなメールボックスを再アクティブ化することが必要な場合、メールボックスを回復することは可能です。</span><span class="sxs-lookup"><span data-stu-id="169c0-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="169c0-131">詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="169c0-132">非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="169c0-133">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="169c0-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="169c0-134">前述したように、非アクティブなメールボックスに訴訟ホールド、インプレースホールド、またはアイテム保持ポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="169c0-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="169c0-135">最初の手順として、非アクティブなメールボックスのホールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="169c0-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="169c0-136">組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="169c0-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="169c0-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="169c0-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="169c0-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span><span class="sxs-lookup"><span data-stu-id="169c0-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="169c0-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="169c0-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="169c0-140">多数のインプレース ホールドが非アクティブなメールボックスに設定されている場合、一部のインプレース ホールドの GUID が表示されません。</span><span class="sxs-lookup"><span data-stu-id="169c0-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="169c0-141">すべてのインプレースホールド Guid を表示するには、次のコマンドを実行します。`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="169c0-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="169c0-142">手順 2:非アクティブなメールボックスから保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="169c0-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="169c0-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="169c0-145">訴訟ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="169c0-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="169c0-147">You can't use the EAC.</span><span class="sxs-lookup"><span data-stu-id="169c0-147">You can't use the EAC.</span></span> <span data-ttu-id="169c0-148">Run the following command to remove a Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="169c0-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="169c0-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span><span class="sxs-lookup"><span data-stu-id="169c0-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="169c0-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="169c0-151">インプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="169c0-152">非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="169c0-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="169c0-153">**インプレースホールドオブジェクトを削除する**完全に削除する非アクティブなメールボックスが、インプレースホールドの唯一のソースメールボックスである場合は、インプレース保持オブジェクトを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="169c0-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="169c0-154">You have to disable the hold before you can delete an In-Place Hold object.</span><span class="sxs-lookup"><span data-stu-id="169c0-154">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="169c0-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span><span class="sxs-lookup"><span data-stu-id="169c0-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="169c0-156">**インプレース ホールドのソース メールボックスとして非アクティブなメールボックスを削除する** インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="169c0-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="169c0-157">EAC を使用してインプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="169c0-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span><span class="sxs-lookup"><span data-stu-id="169c0-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="169c0-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span><span class="sxs-lookup"><span data-stu-id="169c0-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="169c0-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="169c0-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="169c0-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="169c0-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="169c0-162">削除するインプレースホールドを選択し、[編集] 編集アイコンを**クリックし** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="169c0-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="169c0-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="169c0-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="169c0-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="169c0-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="169c0-165">警告が表示されたら、 **[はい]** をクリックして、インプレース保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="169c0-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="169c0-166">Exchange Online PowerShell を使用してインプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="169c0-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span><span class="sxs-lookup"><span data-stu-id="169c0-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="169c0-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="169c0-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="169c0-169">インプレース ホールドの保留リストを無効にします。</span><span class="sxs-lookup"><span data-stu-id="169c0-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="169c0-170">インプレース ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="169c0-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="169c0-171">EAC を使用してインプレース ホールドから非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="169c0-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span><span class="sxs-lookup"><span data-stu-id="169c0-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="169c0-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="169c0-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="169c0-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="169c0-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="169c0-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="169c0-176">非アクティブなメールボックスに配置されたインプレースホールドを選択し、[編集アイコンの**編集**] をクリックし ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="169c0-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="169c0-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="169c0-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="169c0-178">ソース メールボックスのリストで、削除する非アクティブなメールボックスの名前をクリックして、 **[削除]**![[削除] アイコン](../media/adf01106-cc79-475c-8673-065371c1897b.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="169c0-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="169c0-179">Click **Save** to save the change.</span><span class="sxs-lookup"><span data-stu-id="169c0-179">Click **Save** to save the change.</span></span> <span data-ttu-id="169c0-180">A message is displayed saying the operation was successfully completed.</span><span class="sxs-lookup"><span data-stu-id="169c0-180">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="169c0-181">手順 1 から手順 6 を繰り返して、非アクティブなメールボックスに設定された他のインプレース保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="169c0-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="169c0-182">Exchange Online PowerShell を使用してインプレース保持から非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="169c0-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="169c0-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span><span class="sxs-lookup"><span data-stu-id="169c0-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="169c0-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="169c0-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="169c0-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="169c0-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="169c0-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="169c0-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="169c0-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="169c0-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="169c0-188">非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="169c0-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="169c0-189">**注:** インプレースホールドの*Sources*プロパティは、 *LegacyExchangeDN*プロパティによってソースメールボックスを識別します。</span><span class="sxs-lookup"><span data-stu-id="169c0-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="169c0-190">このプロパティは非アクティブなメールボックスを一意に特定するため、インプレース ホールドの *Sources* プロパティを削除すると、正しくないメールボックスの削除を回避できます。</span><span class="sxs-lookup"><span data-stu-id="169c0-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="169c0-191">これはまた、2 つのメールボックスが同じエイリアスまたは SMTP アドレスを持っているときの問題も回避できます。</span><span class="sxs-lookup"><span data-stu-id="169c0-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="169c0-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span><span class="sxs-lookup"><span data-stu-id="169c0-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="169c0-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span><span class="sxs-lookup"><span data-stu-id="169c0-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="169c0-194">たとえば、次のコマンドは、Pilar Pinilla の非アクティブなメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="169c0-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="169c0-195">変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="169c0-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="169c0-196">非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="169c0-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="169c0-197">インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="169c0-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="169c0-198">詳細情報</span><span class="sxs-lookup"><span data-stu-id="169c0-198">More information</span></span>

- <span data-ttu-id="169c0-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span><span class="sxs-lookup"><span data-stu-id="169c0-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="169c0-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span><span class="sxs-lookup"><span data-stu-id="169c0-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="169c0-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span><span class="sxs-lookup"><span data-stu-id="169c0-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="169c0-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span><span class="sxs-lookup"><span data-stu-id="169c0-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="169c0-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span><span class="sxs-lookup"><span data-stu-id="169c0-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="169c0-204">**非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="169c0-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="169c0-205">非アクティブなメールボックスは、他の回復可能な削除によって削除されたメールボックスと同様に扱われ、回復可能な削除によって削除されたメールボックスの保持期間である 30 日が経過した後に完全削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="169c0-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="169c0-206">この保存期間は、メールボックスが最初に非アクティブになった日から始まります。</span><span class="sxs-lookup"><span data-stu-id="169c0-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="169c0-207">この日付は、対応するユーザーアカウントが削除された日付、または**メールボックスの削除**コマンドレットを使用して Exchange Online メールボックスが削除された日付である、回復可能な削除日と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="169c0-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="169c0-208">回復可能な削除によって削除された日は、保留リストを削除した日ではありません。</span><span class="sxs-lookup"><span data-stu-id="169c0-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="169c0-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span><span class="sxs-lookup"><span data-stu-id="169c0-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="169c0-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span><span class="sxs-lookup"><span data-stu-id="169c0-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="169c0-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span><span class="sxs-lookup"><span data-stu-id="169c0-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="169c0-212">**回復可能な削除によって削除されたメールボックスの保持期間は非アクティブなメールボックスにどのように影響しますか。**</span><span class="sxs-lookup"><span data-stu-id="169c0-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="169c0-213">非アクティブなメールボックスが回復可能な削除によって削除された日付が、ホールドが解除された日付からさかのぼって 30 日目よりも前である場合は、メールボックスに完全削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="169c0-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="169c0-214">ただし、非アクティブなメールボックスの回復可能な削除によって削除された日から 30 日が経過しないうちにホールドを解除した場合は、回復可能な削除によって削除されたメールボックスの保持期間内であれば、メールボックスを回復することが可能です。</span><span class="sxs-lookup"><span data-stu-id="169c0-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="169c0-215">詳細については、「 [Exchange Online でユーザーメールボックスを削除または復元](https://go.microsoft.com/fwlink/?linkid=856835)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="169c0-216">回復可能な削除によって削除されたメールボックスの保持期間が経過した後は、非アクティブなメールボックスを回復するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="169c0-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="169c0-217">詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169c0-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="169c0-218">**ホールドを解除した後、どうすれば非アクティブなメールボックスの情報を表示できますか。**</span><span class="sxs-lookup"><span data-stu-id="169c0-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="169c0-219">保持が削除され、非アクティブなメールボックスが回復可能な削除によって削除されたメールボックスに戻された後は、**メールボックスの取得**コマンドレットで*Inactivemailboxonly*パラメーターを使用して返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="169c0-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="169c0-220">ただし、 **Get-Mailbox -SoftDeletedMailbox** コマンドを使用して、メールボックスの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="169c0-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="169c0-221">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="169c0-221">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="169c0-222">上記の例では、 *Whensoftdeleted*プロパティは、回復可能な削除によって削除された日付 (この例では、2014年10月30日) を示しています。</span><span class="sxs-lookup"><span data-stu-id="169c0-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="169c0-223">この回復可能な削除によって削除されたメールボックスが以前は、保留が削除された非アクティブなメールボックスであった場合、 *Whensoftdeleted*プロパティの値の30日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="169c0-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="169c0-224">この場合、メールボックスは 2014 年 11 月 30 日に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="169c0-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

