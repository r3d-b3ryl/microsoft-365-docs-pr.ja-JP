---
title: Office 365 の非アクティブなメールボックスを削除する
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
description: Office 365 の非アクティブなメールボックスの内容を保持する必要がなくなった場合は、保留リストを削除することによって、非アクティブなメールボックスを完全に削除することができます。 ホールドを削除すると、非アクティブなメールボックスは削除するようにマークされ、処理された後は完全に削除されます。
ms.openlocfilehash: e0b28603fe617a96ebd94ed3bd0e3d881313c5b7
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558354"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="cd920-104">Office 365 の非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="cd920-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="cd920-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="cd920-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span><span class="sxs-lookup"><span data-stu-id="cd920-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="cd920-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="cd920-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="cd920-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="cd920-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="cd920-109">さらに、Office 365 アイテム保持ポリシー (Office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成されたもの) は、非アクティブなメールボックスに適用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd920-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="cd920-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span><span class="sxs-lookup"><span data-stu-id="cd920-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="cd920-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span><span class="sxs-lookup"><span data-stu-id="cd920-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cd920-112">メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるので、Exchange 管理センターでのインプレースホールドの廃止を発表しています。</span><span class="sxs-lookup"><span data-stu-id="cd920-112">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="cd920-113">つまり、訴訟ホールドと Office 365 アイテム保持ポリシーを使用して、非アクティブなメールボックスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd920-113">That means you should use Litigation Holds and Office 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="cd920-114">2020年4月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd920-114">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="cd920-115">ただし、非アクティブなメールボックスに設定されたインプレースホールドの保持期間を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="cd920-115">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="cd920-116">ただし、2020年7月1日以降、保持期間を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd920-116">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="cd920-117">インプレースホールドを削除しても、非アクティブなメールボックスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd920-117">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="cd920-118">インプレース保持されている既存の非アクティブなメールボックスは、保留が解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-118">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="cd920-119">インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-119">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="cd920-120">保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[More information](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-120">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="cd920-121">開始する前に</span><span class="sxs-lookup"><span data-stu-id="cd920-121">Before you begin</span></span>

- <span data-ttu-id="cd920-122">非アクティブなメールボックスから訴訟ホールドを削除するには、Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd920-122">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="cd920-123">Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd920-123">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="cd920-124">詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-124">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="cd920-125">非アクティブなメールボックスからインプレース ホールドを削除する場合は、Exchange Online PowerShell または EAC を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd920-125">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="cd920-126">非アクティブなメールボックスの内容は、ホールドを解除して、非アクティブなメールボックスを削除する前に別のメールボックスにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="cd920-126">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="cd920-127">詳細については、「 [Office の非アクティブなメールボックスを復元する 365](restore-an-inactive-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-127">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="cd920-128">非アクティブなメールボックスからホールドまたは Office 365 アイテム保持ポリシーを解除すると、メールボックスの回復可能な削除によって削除されたメールボックスの保持期間の有効期限が切れていれば、メールボックスは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-128">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="cd920-129">削除後に回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd920-129">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="cd920-130">ホールドを解除する前に、メールボックスの中身が不要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-130">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="cd920-131">非アクティブなメールボックスを再アクティブ化することが必要な場合、メールボックスを回復することは可能です。</span><span class="sxs-lookup"><span data-stu-id="cd920-131">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="cd920-132">詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-132">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="cd920-133">非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-133">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="cd920-134">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="cd920-134">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="cd920-p107">前述のように、訴訟ホールド、インプレース ホールド、または Office 365 アイテム保持ポリシーが非アクティブなメールボックスに設定されていることがあります。最初の手順として、非アクティブなメールボックスのホールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="cd920-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="cd920-137">組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd920-137">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="cd920-p108">**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスが訴訟ホールドに設定されていることを示します。インプレース ホールドが非アクティブなメールボックスに設定されていると、保留リストの GUID が **InPlaceHolds** プロパティの値として表示されます。たとえば、2 つの非アクティブなメールボックスの次の結果は、1 つの訴訟ホールドが Ann Beebe に設定され、2 つのインプレース ホールドが Pilar Pinilla に設定されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="cd920-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="cd920-141">多数のインプレース ホールドが非アクティブなメールボックスに設定されている場合、一部のインプレース ホールドの GUID が表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd920-141">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="cd920-142">すべてのインプレースホールド Guid を表示するには、次のコマンドを実行します。`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="cd920-142">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="cd920-143">手順 2:非アクティブなメールボックスから保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-143">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="cd920-p110">非アクティブなメールボックスにどの種類の保留リストが設定されているか (および複数の保留リストがあるかどうか) を特定したら、次の手順ではメールボックスの保留リストを削除します。前述のように、非アクティブなメールボックスを完全に削除するには、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd920-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="cd920-146">訴訟ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-146">Remove a Litigation Hold</span></span>

<span data-ttu-id="cd920-p111">前述のように、非アクティブなメールボックスから訴訟ホールドを削除するには、Windows PowerShell を使用する必要があります。EAC は使用できません。次のコマンドを実行して、訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd920-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="cd920-p112">非アクティブなメールボックスを特定するには、識別名または Exchange GUID 値を使用するのが最適です。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="cd920-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="cd920-152">インプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-152">Remove In-Place Holds</span></span>

 <span data-ttu-id="cd920-153">非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="cd920-153">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="cd920-154">**インプレースホールドオブジェクトを削除する**完全に削除する非アクティブなメールボックスが、インプレースホールドの唯一のソースメールボックスである場合は、インプレース保持オブジェクトを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="cd920-154">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cd920-p113">インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="cd920-157">**インプレース ホールドのソース メールボックスとして非アクティブなメールボックスを削除する** インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="cd920-157">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="cd920-158">EAC を使用してインプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-158">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="cd920-p114">削除するインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、完全に削除する非アクティブなメールボックスに設定されているインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース ホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd920-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="cd920-162">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="cd920-162">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="cd920-163">削除するインプレースホールドを選択し、 **[編集]** ![編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd920-163">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="cd920-164">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="cd920-164">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="cd920-165">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="cd920-165">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="cd920-166">警告が表示されたら、 **[はい]** をクリックして、インプレース保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd920-166">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="cd920-167">Exchange Online PowerShell を使用してインプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-167">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="cd920-p115">削除するインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd920-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="cd920-170">インプレース ホールドの保留リストを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cd920-170">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="cd920-171">インプレース ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd920-171">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="cd920-172">EAC を使用してインプレース ホールドから非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-172">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="cd920-p116">非アクティブなメールボックスに設定されたインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、メールボックスに設定されたインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース ホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd920-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="cd920-176">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="cd920-176">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="cd920-177">非アクティブなメールボックスに配置されたインプレースホールドを選択し、[ \*\*\*\* ![編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)の編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd920-177">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="cd920-178">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="cd920-178">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="cd920-179">ソース メールボックスのリストで、削除する非アクティブなメールボックスの名前をクリックして、 **[削除]**![[削除] アイコン](media/adf01106-cc79-475c-8673-065371c1897b.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd920-179">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="cd920-p117">**[保存]** をクリックして変更を保存します。操作が正常に完了したことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-p117">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="cd920-182">手順 1 から手順 6 を繰り返して、非アクティブなメールボックスに設定された他のインプレース保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd920-182">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="cd920-183">Exchange Online PowerShell を使用してインプレース保持から非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="cd920-183">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="cd920-p118">インプレース ホールドに多数のソース メールボックスが含まれている場合、EAC の **[ソース]** ページに非アクティブなメールボックスがリストされないことがあります。インプレース ホールドを編集する場合、 **[ソース]** ページに最大 3,000 のメールボックスが表示されます。非アクティブなメールボックスが **[ソース]** ページにリストされない場合は、Exchange Online PowerShell を使用してインプレース ホールドから削除できます。</span><span class="sxs-lookup"><span data-stu-id="cd920-p118">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="cd920-p119">非アクティブなメールボックスに設定されたインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd920-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="cd920-189">非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd920-189">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="cd920-190">**注:** インプレースホールドの*Sources*プロパティは、 *LegacyExchangeDN*プロパティによってソースメールボックスを識別します。</span><span class="sxs-lookup"><span data-stu-id="cd920-190">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="cd920-191">このプロパティは非アクティブなメールボックスを一意に特定するため、インプレース ホールドの *Sources* プロパティを削除すると、正しくないメールボックスの削除を回避できます。</span><span class="sxs-lookup"><span data-stu-id="cd920-191">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="cd920-192">これはまた、2 つのメールボックスが同じエイリアスまたは SMTP アドレスを持っているときの問題も回避できます。</span><span class="sxs-lookup"><span data-stu-id="cd920-192">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="cd920-p121">変数のソース メールボックスのリストから非アクティブなメールボックスを削除します。前の手順のコマンドで返された非アクティブなメールボックスの **LegacyExchangeDN** を必ず使用してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-p121">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="cd920-195">たとえば、次のコマンドは、Pilar Pinilla の非アクティブなメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd920-195">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="cd920-196">変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd920-196">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="cd920-197">非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="cd920-197">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="cd920-198">インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd920-198">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="cd920-199">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cd920-199">More information</span></span>

- <span data-ttu-id="cd920-p122">**非アクティブなメールボックスは、回復可能な削除によって削除されたメールボックスの一種です。** Exchange Onlineで、回復可能な削除によって削除されたメールボックスは、メールボックスが削除されてはいるものの、特定の保持期間内であれば回復することができます。Exchange Online で回復可能な削除によって削除されたメールボックスの保存期間は 30 日です。つまり、回復可能な削除によって削除されてから 30 日以内なら、メールボックスを復元できます。30 日が経過すると、回復可能な削除によって削除されたメールボックスは完全削除のマークが付けられ、回復できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cd920-p122">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="cd920-p123">**非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。** 非アクティブなメールボックスは、他の回復可能な削除によって削除されたメールボックスと同様に扱われ、回復可能な削除によって削除されたメールボックスの保持期間である 30 日が経過した後に完全削除のマークが付けられます。この保存期間は、メールボックスが最初に非アクティブになった日から始まります。この日付は、回復可能な削除によって削除された日付と呼ばれ、対応する Office 365 ユーザー アカウントが削除された日、またはExchange Online メールボックスが **Remove-Mailbox** コマンドレットを使用して削除された日になります。回復可能な削除によって削除された日は、保留リストを削除した日ではありません。</span><span class="sxs-lookup"><span data-stu-id="cd920-p123">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="cd920-p124">**ホールドを解除した直後に、非アクティブなメールボックスは完全に削除されますか。** 非アクティブなメールボックスが回復可能な削除によって削除された日付が 30 日より前であっても、ホールドを解除するとすぐにメールボックスが完全に削除されるということはありません。メールボックスに完全に削除するようマークが付けられ、次に処理されるときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-p124">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="cd920-213">**回復可能な削除によって削除されたメールボックスの保持期間は非アクティブなメールボックスにどのように影響しますか。**</span><span class="sxs-lookup"><span data-stu-id="cd920-213">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="cd920-214">非アクティブなメールボックスが回復可能な削除によって削除された日付が、ホールドが解除された日付からさかのぼって 30 日目よりも前である場合は、メールボックスに完全削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="cd920-214">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="cd920-215">ただし、非アクティブなメールボックスの回復可能な削除によって削除された日から 30 日が経過しないうちにホールドを解除した場合は、回復可能な削除によって削除されたメールボックスの保持期間内であれば、メールボックスを回復することが可能です。</span><span class="sxs-lookup"><span data-stu-id="cd920-215">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="cd920-216">詳細については、「 [Exchange Online でユーザーメールボックスを削除または復元](https://go.microsoft.com/fwlink/?linkid=856835)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-216">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="cd920-217">回復可能な削除によって削除されたメールボックスの保持期間が経過した後は、非アクティブなメールボックスを回復するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd920-217">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="cd920-218">詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd920-218">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="cd920-219">**ホールドを解除した後、どうすれば非アクティブなメールボックスの情報を表示できますか。**</span><span class="sxs-lookup"><span data-stu-id="cd920-219">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="cd920-220">保持が削除され、非アクティブなメールボックスが回復可能な削除によって削除されたメールボックスに戻された後は、**メールボックスの取得**コマンドレットで*Inactivemailboxonly*パラメーターを使用して返されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cd920-220">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="cd920-221">ただし、 **Get-Mailbox -SoftDeletedMailbox** コマンドを使用して、メールボックスの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cd920-221">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="cd920-222">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cd920-222">For example:</span></span> 
    
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

  <span data-ttu-id="cd920-223">上記の例では、 *Whensoftdeleted*プロパティは、回復可能な削除によって削除された日付 (この例では、2014年10月30日) を示しています。</span><span class="sxs-lookup"><span data-stu-id="cd920-223">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="cd920-224">この回復可能な削除によって削除されたメールボックスが以前は、保留が削除された非アクティブなメールボックスであった場合、 *Whensoftdeleted*プロパティの値の30日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-224">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="cd920-225">この場合、メールボックスは 2014 年 11 月 30 日に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd920-225">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

