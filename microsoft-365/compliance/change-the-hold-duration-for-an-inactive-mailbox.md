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
description: メールボックスをOffice 365した後、非アクティブなメールボックスに割り当てられている保持ポリシーまたは保持ポリシー Office 365期間を変更します。
ms.openlocfilehash: 49d133c64763cee12cb26e27d372a16ba4ad7e94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918203"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="7277c-103">非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="7277c-103">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="7277c-104">非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7277c-104">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="7277c-105">訴訟ホールド、In-Place ホールド、Microsoft 365 アイテム保持ポリシー、または電子情報開示ケースに関連付けられている保留リストがメールボックスに配置され、対応するユーザー アカウントが削除された場合、メールボックスは非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="7277c-105">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, a Microsoft 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding user account is deleted.</span></span> <span data-ttu-id="7277c-106">非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間保持されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-106">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="7277c-107">保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="7277c-107">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="7277c-108">[回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-108">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="7277c-109">メールボックスを非アクティブにした後で、非アクティブなメールボックスに割り当てられた保持ポリシー Microsoft 365保持ポリシーの期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-109">After a mailbox is made inactive, you can change the duration of the hold or Microsoft 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7277c-110">メールボックスのコンテンツを保持するためにさまざまな方法に投資を続ける中、Exchange 管理センターのインプレース ホールドを廃止することを発表します。</span><span class="sxs-lookup"><span data-stu-id="7277c-110">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="7277c-111">つまり、非アクティブなメールボックスを作成するには、訴訟ホールドMicrosoft 365保持ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7277c-111">That means you should use Litigation Holds and Microsoft 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="7277c-112">2020 年 4 月 1 日から、In-Place で新しいExchange Online。</span><span class="sxs-lookup"><span data-stu-id="7277c-112">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="7277c-113">ただし、非アクティブなメールボックスに配置されたインプレース ホールドのホールド期間は引き続き変更できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-113">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="7277c-114">ただし、2020 年 7 月 1 日から、保持期間を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7277c-114">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="7277c-115">インプレース ホールドを削除することによってのみ、非アクティブなメールボックスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-115">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="7277c-116">インプレース ホールドになっている既存の非アクティブなメールボックスは、ホールドが解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-116">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="7277c-117">インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7277c-117">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
## <a name="connect-to-powershell"></a><span data-ttu-id="7277c-118">Connect PowerShell へのアクセス</span><span class="sxs-lookup"><span data-stu-id="7277c-118">Connect to PowerShell</span></span>

- <span data-ttu-id="7277c-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="7277c-119">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="7277c-120">You can't use the Exchange admin center (EAC).</span><span class="sxs-lookup"><span data-stu-id="7277c-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="7277c-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="7277c-121">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="7277c-122">セキュリティとコンプライアンス センターまたはセキュリティ & コンプライアンス センター PowerShell を使用して、Microsoft 365保持ポリシーの保持期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-122">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for a Microsoft 365 retention policy.</span></span>
    
- <span data-ttu-id="7277c-123">コンプライアンス センター powerShell Exchange Onlineセキュリティ &接続するには、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7277c-123">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="7277c-124">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="7277c-124">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [<span data-ttu-id="7277c-125">セキュリティ/コンプライアンス センターの PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="7277c-125">Connect to Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)
    
- <span data-ttu-id="7277c-126">電子情報開示ケースに関連付けられた保留は無限保持であり、変更できる保持期間はありません。</span><span class="sxs-lookup"><span data-stu-id="7277c-126">Holds associated with eDiscovery cases are infinite holds, which means there's no hold duration that can be changed.</span></span> <span data-ttu-id="7277c-127">アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-127">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="7277c-128">非アクティブなメールボックスの詳細については、「非アクティブなメールボックス」を参照[Microsoft 365。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7277c-128">For more information about inactive mailboxes, see [Inactive mailboxes in Microsoft 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="7277c-129">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="7277c-129">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="7277c-130">異なる種類の保留リストまたは 1 つ以上の Microsoft 365 保持ポリシーが非アクティブなメールボックスに配置される可能性があるため、最初の手順は非アクティブなメールボックスの保留リストを識別します。</span><span class="sxs-lookup"><span data-stu-id="7277c-130">Because different types of holds or one or more Microsoft 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="7277c-131">Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7277c-131">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

<span data-ttu-id="7277c-132">**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスは訴訟ホールド中ということになります。</span><span class="sxs-lookup"><span data-stu-id="7277c-132">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="7277c-133">In-Place 保持ポリシー、電子情報開示保持ポリシー、または Microsoft 365 保持ポリシーが非アクティブなメールボックスに配置されている場合、保持ポリシーまたは保持ポリシーの GUID が **InPlaceHolds** プロパティの値として表示されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-133">If an In-Place Hold, eDiscovery hold, or Microsoft 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="7277c-134">たとえば、5 つの非アクティブなメールボックスの結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7277c-134">For example, the following shows results for five inactive mailboxes.</span></span> 
  
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

<span data-ttu-id="7277c-135">次の表は、各メールボックスを非アクティブにするのに使用された 5 つの異なる種類のホールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="7277c-135">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="7277c-136">**非アクティブなメールボックス**</span><span class="sxs-lookup"><span data-stu-id="7277c-136">**Inactive mailbox**</span></span>|<span data-ttu-id="7277c-137">**ホールドの種類**</span><span class="sxs-lookup"><span data-stu-id="7277c-137">**Hold type**</span></span>|<span data-ttu-id="7277c-138">**非アクティブなメールボックスのホールドを識別する方法**</span><span class="sxs-lookup"><span data-stu-id="7277c-138">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7277c-139">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="7277c-139">Ann Beebe</span></span>  <br/> |<span data-ttu-id="7277c-140">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="7277c-140">Litigation Hold</span></span>  <br/> |<span data-ttu-id="7277c-141">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7277c-141">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="7277c-142">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="7277c-142">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="7277c-143">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="7277c-143">In-Place Hold</span></span>  <br/> |<span data-ttu-id="7277c-p106">*InPlaceHolds*  プロパティには非アクティブなメールボックスに設定されたインプレース ホールドの GUID が含まれています。ID がプレフィックスから始まっていないため、これはインプレース ホールドだとわかります。  </span><span class="sxs-lookup"><span data-stu-id="7277c-p106">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox. You can tell this is an In-Place Hold because the ID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="7277c-146">Exchange Online PowerShell で  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` コマンドを使用して、非アクティブのメールボックスのインプレース ホールドについての情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-146">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="7277c-147">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="7277c-147">Mario Necaise</span></span>  <br/> |<span data-ttu-id="7277c-148">セキュリティ Microsoft 365 コンプライアンス センターの組織全体&保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="7277c-148">Organization-wide Microsoft 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="7277c-149">*InPlaceHolds*  プロパティが空になっています。</span><span class="sxs-lookup"><span data-stu-id="7277c-149">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="7277c-150">これは、1 つ以上の組織全体または (Exchange) Microsoft 365が非アクティブなメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-150">This indicates that one or more organization-wide or (Exchange-wide) Microsoft 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="7277c-151">この場合、PowerShell でコマンドをExchange Onlineして、組織全体のアイテム保持ポリシーの `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` GUID のMicrosoft 365取得できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-151">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Microsoft 365 retention policies.</span></span> <span data-ttu-id="7277c-152">メールボックスに適用される組織全体の保持ポリシーの GUID は、Exchangeプレフィックスで始まる。たとえば `mbx` `mbxa3056bb15562480fadb46ce523ff7b02` 、 です。</span><span class="sxs-lookup"><span data-stu-id="7277c-152">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="7277c-153">非アクティブなMicrosoft 365に適用されるアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7277c-153">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="7277c-154">Carol Olson</span><span class="sxs-lookup"><span data-stu-id="7277c-154">Carol Olson</span></span>  <br/> |<span data-ttu-id="7277c-155">Microsoft 365に適用されるセキュリティ & コンプライアンス センターのアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="7277c-155">Microsoft 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="7277c-156">*InPlaceHolds* プロパティには、非アクティブなメールボックスにMicrosoft 365保持ポリシーの GUID が含まれる。</span><span class="sxs-lookup"><span data-stu-id="7277c-156">The  *InPlaceHolds*  property contains the GUID of the Microsoft 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="7277c-157">GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="7277c-157">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="7277c-158">非アクティブなメールボックスに適用される保持ポリシーの GUID がプレフィックスで始まった場合、保持ポリシーがユーザーの会話に適用Skype for Business `skp` されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-158">If the GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, it would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="7277c-159">非アクティブなMicrosoft 365に適用されるアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7277c-159">To identity the Microsoft 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="7277c-160">このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="7277c-160">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="7277c-161">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="7277c-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="7277c-162">セキュリティ コンプライアンス センターでの電子情報開示&保持</span><span class="sxs-lookup"><span data-stu-id="7277c-162">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="7277c-p109">*InPlaceHolds*  プロパティに、非アクティブなメールボックスに設定されている電子情報開示ケース ホールドの GUID が含まれています。GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  </span><span class="sxs-lookup"><span data-stu-id="7277c-p109">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="7277c-165">Security & コンプライアンス センター PowerShell のコマンドレットを使用して、非アクティブなメールボックスの保留が関連付けられている電子情報開示ケースに関する情報  `Get-CaseHoldPolicy` を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7277c-165">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="7277c-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="7277c-166">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="7277c-167">Be sure to remove the  `UniH` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="7277c-167">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="7277c-168">非アクティブなメールボックスのホールドが関連付けられている電子情報開示ケースを特定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7277c-168">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="7277c-169">**注:** 非アクティブなメールボックスに電子情報開示ホールドを使用することをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7277c-169">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="7277c-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span><span class="sxs-lookup"><span data-stu-id="7277c-170">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="7277c-171">ある時点で、法的ケースはおそらく終了し、ケースに関連付けられている保留リストは削除され、電子情報開示ケースは閉じ (または削除) されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-171">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="7277c-172">実際、非アクティブなメールボックスに配置された保留リストが電子情報開示ケースに関連付けられている場合、ホールドが解放された場合、または電子情報開示ケースが閉じたり削除された場合、非アクティブなメールボックスは完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-172">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="7277c-173">アイテム保持ポリシーのMicrosoft 365詳細については、「アイテム保持ポリシーと保持ラベルについて」[を参照してください](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="7277c-173">For more information about Microsoft 365 retention policies, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="7277c-174">手順 2: 非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="7277c-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="7277c-175">非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="7277c-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="7277c-176">訴訟ホールドの期間を変更する</span><span class="sxs-lookup"><span data-stu-id="7277c-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="7277c-p112">Exchange Online PowerShell を使用して、非アクティブなメールボックスに配置されている訴訟ホールドの保持期間を変更する方法を次に示します。EAC を使用することはできません。保持期間を変更するには、次のコマンドを実行します。この例では、保持期間を無期限に変更しています。</span><span class="sxs-lookup"><span data-stu-id="7277c-p112">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox. You can't use the EAC. Run the following command to change the hold duration. In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="7277c-181">結果として、非アクティブなメールボックス内のアイテムは、無期限に、あるいは、ホールドが削除されるか保持期間が別の値に変更されるまで、保持されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="7277c-p113">非アクティブなメールボックスを特定する最もよい方法は、 **Distinguished Name** または **Exchange GUID** の値を使用することです。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。</span><span class="sxs-lookup"><span data-stu-id="7277c-p113">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="7277c-184">インプレース ホールドの期間を変更する</span><span class="sxs-lookup"><span data-stu-id="7277c-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="7277c-185">In-Place保留は廃止され、変更できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7277c-185">In-Place Holds have been retired and can no longer be modified.</span></span> <span data-ttu-id="7277c-186">非アクティブなメールボックスにIn-Place保持が適用されている場合は、保持期間を変更できません。</span><span class="sxs-lookup"><span data-stu-id="7277c-186">If an inactive mailbox has an In-Place Hold applied to it, you can't change the hold duration.</span></span> <span data-ttu-id="7277c-187">削除できるのは、非アクティブなIn-Place削除される保留リストの保持のみです。</span><span class="sxs-lookup"><span data-stu-id="7277c-187">You can only remove the In-Place Hold, which will result in the deletion of the inactive mailbox.</span></span> <span data-ttu-id="7277c-188">詳細については、「非アクティブな [メールボックスを削除する」を参照してください](delete-an-inactive-mailbox.md#remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="7277c-188">For more information, see [Delete an inactive mailbox](delete-an-inactive-mailbox.md#remove-in-place-holds).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="7277c-189">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7277c-189">More information</span></span>

- <span data-ttu-id="7277c-p115">**非アクティブなメールボックス内のアイテムの保持期間はどのように計算されますか。** 保持期間は、メールボックス アイテムを受信または作成した最初の日付から計算されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-p115">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="7277c-192">**保持期間を過ぎるとどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="7277c-192">**What happens when the hold duration expires?**</span></span> <span data-ttu-id="7277c-193">[回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-193">When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="7277c-194">非アクティブなメールボックスに保持期間が指定されていない場合、回復可能なアイテム フォルダー内のアイテムは削除されません (非アクティブなメールボックスの保持期間が変更されていない限り)。</span><span class="sxs-lookup"><span data-stu-id="7277c-194">If there's no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="7277c-p117">**Exchange アイテム保持ポリシーの処理は、非アクティブなメールボックスに対しても継続されますか。** メールボックスが非アクティブになったときにメールボックスに Exchange アイテム保持ポリシー (Exchange Online の機能であるメッセージング レコード管理 (MRM)) が適用されていた場合は、その非アクティブなメールボックスに対して削除ポリシー ( **Delete** 保持アクションが設定された保持タグ) の処理が継続されます。つまり、保持期間を過ぎると、削除ポリシーのタグが付けられたアイテムは [回復可能なアイテム] フォルダーに移動されます。その後、保持期間を過ぎると、それらのアイテムは非アクティブなメールボックスから消去されます。</span><span class="sxs-lookup"><span data-stu-id="7277c-p117">**Is an Exchange retention policy still processed on inactive mailboxes?** If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires. Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="7277c-p118">逆に、非アクティブなメールボックスに割り当てられた保持ポリシーにアーカイブ ポリシー ( **MoveToArchive** 保持アクションが設定された保持タグ) が含まれている場合、それらはすべて無視されます。つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。ユーザーは非アクティブなメールボックスにサインインできないので、アーカイブ ポリシーを処理するためにデータセンターのリソースを消費する理由はありません。</span><span class="sxs-lookup"><span data-stu-id="7277c-p118">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 

- <span data-ttu-id="7277c-203">**訴訟ホールドの新しい保持期間を確認するには、次のコマンドを実行します。**</span><span class="sxs-lookup"><span data-stu-id="7277c-203">**To check the new hold duration for a Litigation Hold, run the following commands**</span></span> 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- <span data-ttu-id="7277c-204">**通常のメールボックスのように、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。**</span><span class="sxs-lookup"><span data-stu-id="7277c-204">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.**</span></span> <span data-ttu-id="7277c-205">このExchange Online MFA は約 7 日に 1 回メールボックスを処理します。</span><span class="sxs-lookup"><span data-stu-id="7277c-205">In Exchange Online, the MFA processes mailboxes approximately once every seven days.</span></span> <span data-ttu-id="7277c-206">非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。</span><span class="sxs-lookup"><span data-stu-id="7277c-206">After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox.</span></span> <span data-ttu-id="7277c-207">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7277c-207">Run the following command.</span></span> 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="7277c-208">**非アクティブなメールボックスに多数の保留リストが配置されている場合は、すべての保留 GUID が表示されません。**</span><span class="sxs-lookup"><span data-stu-id="7277c-208">**If many holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="7277c-209">非アクティブなメールボックスに設定されているすべてのホールド (訴訟ホールドを除く) の GUID を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7277c-209">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```