---
title: 非アクティブなメールボックスを削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: Microsoft 365 非アクティブなメールボックスの内容を保持する必要がなくなった場合は、非アクティブなメールボックスを完全に削除できます。
ms.openlocfilehash: 94a20bee1ca3d11a193a25efeb6d73f356e1d58d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909927"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="d2810-103">非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="d2810-104">非アクティブなメールボックスは、元従業員が組織を離れた後に、元の従業員のメールを保持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="d2810-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span><span class="sxs-lookup"><span data-stu-id="d2810-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="d2810-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="d2810-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="d2810-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="d2810-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="d2810-108">さらに、保持ポリシー (Office 365 または Microsoft 365 のセキュリティとコンプライアンス センターで作成) が非アクティブなメールボックスに適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="d2810-109">非アクティブなメールボックスからすべての保持ポリシーと保持ポリシーを削除して削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="d2810-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span><span class="sxs-lookup"><span data-stu-id="d2810-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d2810-111">メールボックスのコンテンツを保持するためにさまざまな方法に投資を続ける中、Exchange 管理センターのインプレース ホールドを廃止することを発表します。</span><span class="sxs-lookup"><span data-stu-id="d2810-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="d2810-112">つまり、非アクティブなメールボックスを作成するには、訴訟ホールドとアイテム保持ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="d2810-113">2020 年 7 月 1 日以降、Exchange Online で新しいインプレース ホールドを作成することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2810-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="d2810-114">ただし、非アクティブなメールボックスに配置されたインプレース ホールドのホールド期間は引き続き変更できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="d2810-115">ただし、2020 年 10 月 1 日以降、ホールド期間を変更することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2810-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="d2810-116">インプレース ホールドを削除することによってのみ、非アクティブなメールボックスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="d2810-117">インプレース ホールドになっている既存の非アクティブなメールボックスは、ホールドが解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="d2810-118">インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="d2810-119">保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="d2810-120">非アクティブなメールボックスを削除する前に</span><span class="sxs-lookup"><span data-stu-id="d2810-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="d2810-121">非アクティブなメールボックスから訴訟ホールドを削除するには、Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="d2810-122">Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2810-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="d2810-123">詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d2810-124">非アクティブなメールボックスの内容は、ホールドを解除して、非アクティブなメールボックスを削除する前に別のメールボックスにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="d2810-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="d2810-125">詳細については [、「365 で非アクティブなメールボックスを復元するOfficeを参照してください](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d2810-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="d2810-126">非アクティブなメールボックスから保持ポリシーまたは保持ポリシーを削除し、そのメールボックスの回復可能な削除済みメールボックスの保持期間が経過した場合、メールボックスは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="d2810-127">削除後に回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="d2810-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="d2810-128">ホールドを解除する前に、メールボックスの中身が不要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="d2810-129">非アクティブなメールボックスを再アクティブ化する場合は、そのメールボックスを回復できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="d2810-130">詳細については、「365 で非アクティブなメールボックスを [回復するOfficeを参照してください](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d2810-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="d2810-131">非アクティブなメールボックスの詳細については、「365 の非アクティブなメールボックス [」をOfficeしてください](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d2810-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="d2810-132">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="d2810-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="d2810-133">前に述べたように、訴訟ホールド、In-Place保持、または保持ポリシーが非アクティブなメールボックスに配置される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="d2810-134">最初の手順として、非アクティブなメールボックスのホールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="d2810-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="d2810-135">組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d2810-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="d2810-136">**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスが訴訟ホールドに設定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d2810-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="d2810-137">インプレース ホールドが非アクティブなメールボックスに設定されていると、保留リストの GUID が **InPlaceHolds** プロパティの値として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="d2810-138">たとえば、2 つの非アクティブなメールボックスの次の結果は、訴訟ホールドが Ann Beebe に配置され、In-Place 保持ポリシーが Pilar Pinilla に配置されているという結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2810-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="d2810-139">アクティブでないメールボックスIn-Place保持ポリシーの多くが配置されている場合は、すべてのユーザー保持 GUID がIn-Place表示されません。</span><span class="sxs-lookup"><span data-stu-id="d2810-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="d2810-140">次のコマンドを実行して、InPlaceHolds プロパティ内のすべての GUID を表示できます。  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="d2810-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="d2810-141">保留リストの識別の詳細については、「メールボックスに配置された保留の種類を識別する方法 [」を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d2810-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="d2810-142">手順 2:非アクティブなメールボックスから保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="d2810-p109">非アクティブなメールボックスにどの種類の保留リストが設定されているか (および複数の保留リストがあるかどうか) を特定したら、次の手順ではメールボックスの保留リストを削除します。前述のように、非アクティブなメールボックスを完全に削除するには、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="d2810-145">訴訟ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="d2810-p110">前述のように、非アクティブなメールボックスから訴訟ホールドを削除するには、Windows PowerShell を使用する必要があります。EAC は使用できません。次のコマンドを実行して、訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="d2810-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="d2810-p111">非アクティブなメールボックスを特定するには、識別名または Exchange GUID 値を使用するのが最適です。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを回避できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="d2810-151">アイテム保持ポリシーから非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="d2810-152">Microsoft 365 アイテム保持ポリシーから非アクティブなメールボックスを削除する手順は、非アクティブなメールボックスに割り当てられたアイテム保持ポリシーが組織全体か明示的かによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d2810-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="d2810-153">非アクティブなメールボックスに割り当てられているアイテム保持ポリシーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2810-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="d2810-154">組織内のすべてのメールボックスに割り当てられた組織全体の保持ポリシー。</span><span class="sxs-lookup"><span data-stu-id="d2810-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="d2810-155">Exchange Online **PowerShell の Get-OrganizationConfig** コマンドレットを使用して、組織全体の保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d2810-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="d2810-156">特定のメールボックスに割り当てられた特定の場所保持ポリシー。</span><span class="sxs-lookup"><span data-stu-id="d2810-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="d2810-157">これらは、特定のユーザーのコンテンツの場所に割り当てられるポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d2810-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="d2810-158">Exchange Online PowerShell **の Get-Mailbox -IncludeInactiveMailbox** コマンドレットを使用して、特定の非アクティブなメールボックスに割り当てられた保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d2810-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="d2810-159">組織全体のアイテム保持ポリシーから非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="d2810-160">Exchange Online PowerShell で次のコマンドを実行して、非アクティブなメールボックスを組織全体の保持ポリシーから除外します。</span><span class="sxs-lookup"><span data-stu-id="d2810-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="d2810-161">非アクティブなメールボックスに適用される組織全体の保持ポリシーを識別し、アイテム保持ポリシーの GUID を取得する方法の詳細については、「メールボックスに配置された保持[](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)の種類を識別する方法」の「Get-OrganizationConfig」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="d2810-162">または、次のコマンドを実行して、非アクティブなメールボックスを組織全体のすべてのポリシーから削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2810-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="d2810-163">特定の場所保持ポリシーから非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="d2810-164">コンプライアンス センター [PowerShell](/powershell/exchange/connect-to-scc-powershell) のセキュリティ &コマンドを実行して、非アクティブなメールボックスを明示的な保持ポリシーから削除します。</span><span class="sxs-lookup"><span data-stu-id="d2810-164">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="d2810-165">非アクティブなメールボックスに適用される特定の場所保持ポリシーを特定し、アイテム保持ポリシーの GUID を取得する方法の詳細については、「メールボックスに配置[](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)された保持の種類を識別する方法」の「Get-Mailbox」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="d2810-166">インプレース ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="d2810-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="d2810-167">非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d2810-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="d2810-168">**Hold オブジェクトIn-Place削除します**。</span><span class="sxs-lookup"><span data-stu-id="d2810-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="d2810-169">完全に削除する非アクティブなメールボックスが In-Place Hold の唯一のソース メールボックスである場合は、保持オブジェクトIn-Placeできます。</span><span class="sxs-lookup"><span data-stu-id="d2810-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d2810-p116">インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-p116">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="d2810-172">**非アクティブなメールボックスを、保留リストのソース メールボックスとしてIn-Placeします**。</span><span class="sxs-lookup"><span data-stu-id="d2810-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="d2810-173">インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="d2810-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="d2810-174">保留リストをIn-Placeする</span><span class="sxs-lookup"><span data-stu-id="d2810-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="d2810-p118">削除するインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2810-p118">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="d2810-177">インプレース ホールドの保留リストを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d2810-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="d2810-178">インプレース ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="d2810-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="d2810-179">非アクティブなメールボックスを保留リストからIn-Placeする</span><span class="sxs-lookup"><span data-stu-id="d2810-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="d2810-p119">インプレース ホールドに多数のソース メールボックスが含まれている場合、EAC の **[ソース]** ページに非アクティブなメールボックスがリストされないことがあります。インプレース ホールドを編集する場合、 **[ソース]** ページに最大 3,000 のメールボックスが表示されます。非アクティブなメールボックスが **[ソース]** ページにリストされない場合は、Exchange Online PowerShell を使用してインプレース ホールドから削除できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-p119">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="d2810-p120">非アクティブなメールボックスに設定されたインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2810-p120">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="d2810-185">非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2810-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="d2810-p121">インプレース ホールドの *Sources* プロパティは、 *LegacyExchangeDN* プロパティでソース メールボックスを特定します。このプロパティは非アクティブなメールボックスを一意に特定するため、インプレース ホールドの *Sources* プロパティを削除すると、正しくないメールボックスの削除を回避できます。これはまた、2 つのメールボックスが同じエイリアスまたは SMTP アドレスを持っているときの問題も回避できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-p121">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="d2810-p122">変数のソース メールボックスのリストから非アクティブなメールボックスを削除します。前の手順のコマンドで返された非アクティブなメールボックスの **LegacyExchangeDN** を必ず使用してください。</span><span class="sxs-lookup"><span data-stu-id="d2810-p122">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="d2810-191">たとえば、次のコマンドは、Pilar Pinilla の非アクティブなメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="d2810-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="d2810-192">変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2810-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="d2810-193">非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="d2810-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="d2810-194">インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2810-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="d2810-195">詳細</span><span class="sxs-lookup"><span data-stu-id="d2810-195">More information</span></span>

- <span data-ttu-id="d2810-p123">**非アクティブなメールボックスは、回復可能な削除によって削除されたメールボックスの一種です。** Exchange Onlineで、回復可能な削除によって削除されたメールボックスは、メールボックスが削除されてはいるものの、特定の保持期間内であれば回復することができます。Exchange Online で回復可能な削除によって削除されたメールボックスの保存期間は 30 日です。つまり、回復可能な削除によって削除されてから 30 日以内なら、メールボックスを復元できます。30 日が経過すると、回復可能な削除によって削除されたメールボックスは完全削除のマークが付けられ、回復できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d2810-p123">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="d2810-201">**非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="d2810-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="d2810-202">非アクティブなメールボックスは、他の回復可能な削除によって削除されたメールボックスと同様に扱われ、回復可能な削除によって削除されたメールボックスの保持期間である 30 日が経過した後に完全削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="d2810-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="d2810-203">この保存期間は、メールボックスが最初に非アクティブになった日から始まります。</span><span class="sxs-lookup"><span data-stu-id="d2810-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="d2810-204">この日付は、対応するユーザー アカウントが削除された日付、または Exchange Online メールボックスが Remove-Mailbox コマンドレットで削除された日付と呼ばれる、ソフト削除された **日付と呼** ばれるものです。</span><span class="sxs-lookup"><span data-stu-id="d2810-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="d2810-205">回復可能な削除によって削除された日は、保留リストを削除した日ではありません。</span><span class="sxs-lookup"><span data-stu-id="d2810-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="d2810-p125">**ホールドを解除した直後に、非アクティブなメールボックスは完全に削除されますか。** 非アクティブなメールボックスが回復可能な削除によって削除された日付が 30 日より前であっても、ホールドを解除するとすぐにメールボックスが完全に削除されるということはありません。メールボックスに完全に削除するようマークが付けられ、次に処理されるときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-p125">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="d2810-209">**回復可能な削除によって削除されたメールボックスの保持期間は非アクティブなメールボックスにどのように影響しますか。**</span><span class="sxs-lookup"><span data-stu-id="d2810-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="d2810-210">非アクティブなメールボックスが回復可能な削除によって削除された日付が、ホールドが解除された日付からさかのぼって 30 日目よりも前である場合は、メールボックスに完全削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="d2810-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="d2810-211">ただし、非アクティブなメールボックスの回復可能な削除によって削除された日から 30 日が経過しないうちにホールドを解除した場合は、回復可能な削除によって削除されたメールボックスの保持期間内であれば、メールボックスを回復することが可能です。</span><span class="sxs-lookup"><span data-stu-id="d2810-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="d2810-212">詳細については [、「Exchange Online でユーザー メールボックスを削除または復元する」を参照してください](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="d2810-212">For details, see [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="d2810-213">回復可能な削除済みメールボックスの保持期間が経過した後、非アクティブなメールボックスを回復する手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2810-213">After the soft-deleted mailbox retention period expires, you have to follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="d2810-214">詳細については、「365 で非アクティブなメールボックスを [回復するOfficeを参照してください](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d2810-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="d2810-215">**ホールドを解除した後、どうすれば非アクティブなメールボックスの情報を表示できますか。**</span><span class="sxs-lookup"><span data-stu-id="d2810-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="d2810-216">保留リストが削除され、非アクティブなメールボックスが削除されたメールボックスに戻された後 **、Get-Mailbox** コマンドレットで *InactiveMailboxOnly* パラメーターを使用しても、そのメールボックスは返されません。</span><span class="sxs-lookup"><span data-stu-id="d2810-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="d2810-217">ただし、 **Get-Mailbox -SoftDeletedMailbox** コマンドを使用して、メールボックスの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d2810-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="d2810-218">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d2810-218">For example:</span></span>

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

  <span data-ttu-id="d2810-219">上記の例では *、WhenSoftDeleted* プロパティは、この例では 2014 年 10 月 30 日である、ソフト削除された日付を識別します。</span><span class="sxs-lookup"><span data-stu-id="d2810-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="d2810-220">このソフト削除されたメールボックスが以前に保持が削除された非アクティブなメールボックスだった場合 *、WhenSoftDeleted* プロパティの値の 30 日後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="d2810-221">この場合、メールボックスは 2014 年 11 月 30 日に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2810-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>