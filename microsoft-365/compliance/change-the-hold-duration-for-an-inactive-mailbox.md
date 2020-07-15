---
title: 非アクティブなメールボックスの保持期間を変更する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Office 365 メールボックスが非アクティブになった後、非アクティブなメールボックスに割り当てられているホールドまたは Office 365 アイテム保持ポリシーの期間を変更します。
ms.openlocfilehash: 675e6eb36f762a50c3caafce07d09fda9ba9d98e
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126378"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="23c0a-103">非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="23c0a-103">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="23c0a-104">非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-104">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="23c0a-105">メールボックスは、訴訟ホールド、インプレースホールド、Microsoft 365 アイテム保持ポリシー、または電子情報開示ケースに関連付けられた保留リストがメールボックスに配置され、対応するユーザーアカウントが削除されると、非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="23c0a-105">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, a Microsoft 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding user account is deleted.</span></span> <span data-ttu-id="23c0a-106">非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間、保持されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-106">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="23c0a-107">保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-107">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="23c0a-108">[回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-108">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="23c0a-109">メールボックスが非アクティブになった後は、非アクティブなメールボックスに割り当てられている保留または Microsoft 365 アイテム保持ポリシーの期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-109">After a mailbox is made inactive, you can change the duration of the hold or Microsoft 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="23c0a-110">メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるので、Exchange 管理センターでのインプレースホールドの廃止を発表しています。</span><span class="sxs-lookup"><span data-stu-id="23c0a-110">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="23c0a-111">つまり、非アクティブなメールボックスを作成するには、訴訟ホールドと Microsoft 365 のアイテム保持ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23c0a-111">That means you should use Litigation Holds and Microsoft 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="23c0a-112">2020年4月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="23c0a-112">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="23c0a-113">ただし、非アクティブなメールボックスに設定されたインプレースホールドの保持期間を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-113">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="23c0a-114">ただし、2020年7月1日以降、保持期間を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="23c0a-114">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="23c0a-115">インプレースホールドを削除しても、非アクティブなメールボックスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="23c0a-115">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="23c0a-116">インプレース保持されている既存の非アクティブなメールボックスは、保留が解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-116">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="23c0a-117">インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23c0a-117">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
## <a name="connect-to-powershell"></a><span data-ttu-id="23c0a-118">PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="23c0a-118">Connect to PowerShell</span></span>

- <span data-ttu-id="23c0a-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="23c0a-120">You can't use the Exchange admin center (EAC).</span><span class="sxs-lookup"><span data-stu-id="23c0a-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="23c0a-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="23c0a-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="23c0a-122">セキュリティ/コンプライアンスセンターまたはセキュリティ & コンプライアンスセンターの PowerShell を使用して、Microsoft 365 のアイテム保持ポリシーの保持期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-122">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for a Microsoft 365 retention policy.</span></span>
    
- <span data-ttu-id="23c0a-123">Exchange Online PowerShell または Security & コンプライアンスセンター PowerShell に接続するには、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23c0a-123">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="23c0a-124">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="23c0a-124">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="23c0a-125">セキュリティ/コンプライアンス センターの PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="23c0a-125">Connect to Security & Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="23c0a-126">電子情報開示ケースに関連付けられている保留は無限保持で、変更可能な保持期間がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-126">Holds associated with eDiscovery cases are infinite holds, which means there's no hold duration that can be changed.</span></span> <span data-ttu-id="23c0a-127">アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-127">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="23c0a-128">非アクティブなメールボックスの詳細については、「 [Microsoft 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23c0a-128">For more information about inactive mailboxes, see [Inactive mailboxes in Microsoft 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="23c0a-129">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="23c0a-129">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="23c0a-130">非アクティブなメールボックスには、さまざまな種類の保留または1つ以上の Microsoft 365 保持ポリシーが設定されている場合があるため、最初の手順は非アクティブなメールボックスの保留リストを識別することです。</span><span class="sxs-lookup"><span data-stu-id="23c0a-130">Because different types of holds or one or more Microsoft 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="23c0a-131">Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-131">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

<span data-ttu-id="23c0a-132">**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスは訴訟ホールド中ということになります。</span><span class="sxs-lookup"><span data-stu-id="23c0a-132">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="23c0a-133">インプレースホールド、電子情報開示の保持、または Microsoft 365 のアイテム保持ポリシーが非アクティブなメールボックスに設定されている場合、保留またはアイテム保持ポリシーの GUID が**InPlaceHolds**プロパティの値として表示されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-133">If an In-Place Hold, eDiscovery hold, or Microsoft 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="23c0a-134">たとえば、次の例は、5つの非アクティブなメールボックスの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="23c0a-134">For example, the following shows results for five inactive mailboxes.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

<span data-ttu-id="23c0a-135">次の表は、各メールボックスを非アクティブにするのに使用された 5 つの異なる種類のホールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="23c0a-135">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="23c0a-136">**非アクティブなメールボックス**</span><span class="sxs-lookup"><span data-stu-id="23c0a-136">**Inactive mailbox**</span></span>|<span data-ttu-id="23c0a-137">**ホールドの種類**</span><span class="sxs-lookup"><span data-stu-id="23c0a-137">**Hold type**</span></span>|<span data-ttu-id="23c0a-138">**非アクティブなメールボックスのホールドを識別する方法**</span><span class="sxs-lookup"><span data-stu-id="23c0a-138">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23c0a-139">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="23c0a-139">Ann Beebe</span></span>  <br/> |<span data-ttu-id="23c0a-140">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="23c0a-140">Litigation Hold</span></span>  <br/> |<span data-ttu-id="23c0a-141">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="23c0a-141">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="23c0a-142">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="23c0a-142">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="23c0a-143">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="23c0a-143">In-Place Hold</span></span>  <br/> |<span data-ttu-id="23c0a-144">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-144">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="23c0a-145">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span><span class="sxs-lookup"><span data-stu-id="23c0a-145">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="23c0a-146">Exchange Online PowerShell で  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` コマンドを使用して、非アクティブのメールボックスのインプレース ホールドについての情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-146">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="23c0a-147">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="23c0a-147">Mario Necaise</span></span>  <br/> |<span data-ttu-id="23c0a-148">セキュリティ & コンプライアンスセンターの組織全体にわたる Microsoft 365 のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="23c0a-148">Organization-wide Microsoft 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="23c0a-149">*InPlaceHolds*  プロパティが空になっています。</span><span class="sxs-lookup"><span data-stu-id="23c0a-149">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="23c0a-150">これは、1つ以上の組織全体または (Exchange ワイド) Microsoft 365 アイテム保持ポリシーが非アクティブなメールボックスに適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-150">This indicates that one or more organization-wide or (Exchange-wide) Microsoft 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="23c0a-151">この場合、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Exchange Online PowerShell でコマンドを実行して、組織全体の Microsoft 365 保持ポリシーの guid の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-151">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Microsoft 365 retention policies.</span></span> <span data-ttu-id="23c0a-152">Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID は、というプレフィックスで始まり `mbx` ます (例:) `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="23c0a-152">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="23c0a-153">非アクティブなメールボックスに適用されている Microsoft 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-153">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="23c0a-154">Carol Olson</span><span class="sxs-lookup"><span data-stu-id="23c0a-154">Carol Olson</span></span>  <br/> |<span data-ttu-id="23c0a-155">特定のメールボックスに適用されるセキュリティ & コンプライアンスセンターの Microsoft 365 アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="23c0a-155">Microsoft 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="23c0a-156">*InPlaceHolds*プロパティには、非アクティブなメールボックスに適用される Microsoft 365 アイテム保持ポリシーの GUID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="23c0a-156">The  *InPlaceHolds*  property contains the GUID of the Microsoft 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="23c0a-157">GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="23c0a-157">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="23c0a-158">非アクティブなメールボックスに適用されたアイテム保持ポリシーの GUID がプレフィックスで開始されている場合は `skp` 、アイテム保持ポリシーが Skype For business の会話に適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-158">If the GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, it would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="23c0a-159">非アクティブなメールボックスに適用されている Microsoft 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-159">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="23c0a-160">このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="23c0a-160">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="23c0a-161">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="23c0a-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="23c0a-162">セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド</span><span class="sxs-lookup"><span data-stu-id="23c0a-162">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="23c0a-163">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-163">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="23c0a-164">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span><span class="sxs-lookup"><span data-stu-id="23c0a-164">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="23c0a-165">`Get-CaseHoldPolicy`セキュリティ & コンプライアンスセンターの PowerShell でコマンドレットを使用して、非アクティブなメールボックスの保留リストが関連付けられている電子情報開示ケースに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-165">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="23c0a-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="23c0a-167">Be sure to remove the  `UniH` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="23c0a-167">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="23c0a-168">非アクティブなメールボックスのホールドが関連付けられている電子情報開示ケースを特定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-168">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="23c0a-169">**注:** 非アクティブなメールボックスに対して電子情報開示保持を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="23c0a-169">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="23c0a-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span><span class="sxs-lookup"><span data-stu-id="23c0a-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="23c0a-171">いずれかの時点で、訴訟ケースが終了し、ケースに関連付けられている保留リストが削除され、電子情報開示ケースがクローズされる (または削除される) 場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c0a-171">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="23c0a-172">実際には、非アクティブなメールボックスに配置されたホールドが電子情報開示ケースに関連付けられていて、保留が解除されるか、または電子情報開示ケースが閉じられるか削除されると、非アクティブなメールボックスは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-172">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="23c0a-173">Microsoft 365 の保持ポリシーの詳細については、「[アイテム保持ポリシーと保持ラベルについ](retention.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23c0a-173">For more information about Microsoft 365 retention policies, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="23c0a-174">手順 2: 非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="23c0a-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="23c0a-175">非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="23c0a-176">訴訟ホールドの期間を変更する</span><span class="sxs-lookup"><span data-stu-id="23c0a-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="23c0a-177">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-177">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="23c0a-178">You can't use the EAC.</span><span class="sxs-lookup"><span data-stu-id="23c0a-178">You can't use the EAC.</span></span> <span data-ttu-id="23c0a-179">Run the following command to change the hold duration.</span><span class="sxs-lookup"><span data-stu-id="23c0a-179">Run the following command to change the hold duration.</span></span> <span data-ttu-id="23c0a-180">In this example, the hold duration is changed to an unlimited period of time.</span><span class="sxs-lookup"><span data-stu-id="23c0a-180">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="23c0a-181">結果として、非アクティブなメールボックス内のアイテムは、無期限に、あるいは、ホールドが削除されるか保持期間が別の値に変更されるまで、保持されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="23c0a-182">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value.</span><span class="sxs-lookup"><span data-stu-id="23c0a-182">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value.</span></span> <span data-ttu-id="23c0a-183">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-183">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="23c0a-184">インプレース ホールドの期間を変更する</span><span class="sxs-lookup"><span data-stu-id="23c0a-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="23c0a-185">インプレース ホールドの保持期間の変更は、EAC か Exchange Online PowerShell を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-185">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="23c0a-186">EAC を使用して保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="23c0a-186">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="23c0a-187">変更するインプレース ホールドの名前が分かっている場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-187">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="23c0a-188">そうでない場合は、次のコマンドを実行して、非アクティブなメールボックスに設定されたインプレース ホールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-188">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="23c0a-189">[手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得したインプレースホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-189">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="23c0a-190">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="23c0a-190">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="23c0a-191">変更するインプレースホールドを選択し、[編集アイコンの**編集**] を選択し ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-191">Select the In-Place Hold you want to change, and then select **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="23c0a-192">[**インプレースの電子情報開示 &amp; 保持**のプロパティ] ページで、[**インプレースホールド**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-192">On the **In-Place eDiscovery &amp; Hold** properties page, select **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="23c0a-193">現在の保持期間に基づいて、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-193">Do one of the following based on the current hold duration:</span></span>
    
    1. <span data-ttu-id="23c0a-194">無制限にアイテムを保持するには、[**無期限に保持**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-194">Select **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
    2. <span data-ttu-id="23c0a-195">特定の期間のアイテムを保持するために **、受信日を基準**としてアイテムを保持する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-195">Select **Specify number of days to hold items relative to their received date** to hold items for a specific period.</span></span> <span data-ttu-id="23c0a-196">Type the number of days that you want to hold items for.</span><span class="sxs-lookup"><span data-stu-id="23c0a-196">Type the number of days that you want to hold items for.</span></span> 
    
    ![インプレース ホールド期間の変更に関するスクリーン ショット](../media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="23c0a-198">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-198">Select **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="23c0a-199">Exchange Online PowerShell を使用して保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="23c0a-199">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="23c0a-200">変更するインプレース ホールドの名前が分かっている場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-200">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="23c0a-201">そうでない場合は、次のコマンドを実行して、非アクティブなメールボックスに設定されたインプレース ホールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-201">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="23c0a-202">[手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得したインプレースホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-202">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="23c0a-203">保持期間を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-203">Run the following command to change the hold duration.</span></span> <span data-ttu-id="23c0a-204">この例では、保持期間を2555日 (約7年間) に変更します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-204">In this example, the hold duration is changed to 2,555 days (approximately seven years).</span></span> 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="23c0a-205">保持期間を無制限の期間に変更するには、 _-ItemHoldPeriod unlimited_ を使用します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-205">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="23c0a-206">詳細情報</span><span class="sxs-lookup"><span data-stu-id="23c0a-206">More information</span></span>

- <span data-ttu-id="23c0a-207">**How is the hold duration calculated for an item in an inactive mailbox?**</span><span class="sxs-lookup"><span data-stu-id="23c0a-207">**How is the hold duration calculated for an item in an inactive mailbox?**</span></span> <span data-ttu-id="23c0a-208">The duration is calculated from the original date a mailbox item was received or created.</span><span class="sxs-lookup"><span data-stu-id="23c0a-208">The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="23c0a-209">**保持期間を過ぎるとどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="23c0a-209">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="23c0a-210">[回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。</span><span class="sxs-lookup"><span data-stu-id="23c0a-210">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="23c0a-211">非アクティブなメールボックスに設定されている保持期間が指定されていない場合、[回復可能なアイテム] フォルダー内のアイテムは削除されません (非アクティブなメールボックスの保持期間が変更されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="23c0a-211">If there's no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="23c0a-212">**Is an Exchange retention policy still processed on inactive mailboxes?**</span><span class="sxs-lookup"><span data-stu-id="23c0a-212">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="23c0a-213">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-213">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="23c0a-214">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span><span class="sxs-lookup"><span data-stu-id="23c0a-214">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="23c0a-215">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span><span class="sxs-lookup"><span data-stu-id="23c0a-215">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="23c0a-216">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored.</span><span class="sxs-lookup"><span data-stu-id="23c0a-216">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored.</span></span> <span data-ttu-id="23c0a-217">That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires.</span><span class="sxs-lookup"><span data-stu-id="23c0a-217">That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires.</span></span> <span data-ttu-id="23c0a-218">They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox.</span><span class="sxs-lookup"><span data-stu-id="23c0a-218">They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="23c0a-219">Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span><span class="sxs-lookup"><span data-stu-id="23c0a-219">Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="23c0a-220">**To check the new hold duration, run one of the following commands.**</span><span class="sxs-lookup"><span data-stu-id="23c0a-220">**To check the new hold duration, run one of the following commands.**</span></span> <span data-ttu-id="23c0a-221">The first command is for Litigation Hold; the second is for In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="23c0a-221">The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="23c0a-222">**通常のメールボックスのように、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。**</span><span class="sxs-lookup"><span data-stu-id="23c0a-222">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="23c0a-223">Exchange Online では、MFA は約7日に1回、メールボックスを処理します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-223">In Exchange Online, the MFA processes mailboxes approximately once every seven days.</span></span> <span data-ttu-id="23c0a-224">非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-224">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="23c0a-225">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-225">Run the following command.</span></span> 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="23c0a-226">**非アクティブなメールボックスに多数のホールドが設定されている場合、保留中の Guid のすべてが表示されるわけではありません。**</span><span class="sxs-lookup"><span data-stu-id="23c0a-226">**If many holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="23c0a-227">非アクティブなメールボックスに設定されているすべてのホールド (訴訟ホールドを除く) の GUID を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="23c0a-227">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
