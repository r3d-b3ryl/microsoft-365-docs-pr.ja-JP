---
title: 保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: アーカイブ メールボックスを有効にし、自動拡張アーカイブを有効にして、メールボックスの回復可能なアイテム フォルダーのサイズを増やMicrosoft 365。
ms.openlocfilehash: 7b4ee808bc3004438c9eb7424a89c01567fc04d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911275"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="327be-103">保留中のメールボックスの回復可能なアイテムのクォータを拡大する</span><span class="sxs-lookup"><span data-stu-id="327be-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="327be-104">Exchange Online の新しいメールボックスに自動的に適用される既定のアイテム保持ポリシー (Default *MRM Policy)* には、回復可能なアイテム 14 日という名前の保持タグがアーカイブに移動されます。 Exchange</span><span class="sxs-lookup"><span data-stu-id="327be-104">The default Exchange retention policy—named *Default MRM Policy*—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="327be-105">このアイテム保持タグは、アイテムの 14 日間の保存期間が経過すると、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダーから、ユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダーへ、アイテムを移動します。</span><span class="sxs-lookup"><span data-stu-id="327be-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="327be-106">この処理を実行するためには、ユーザーのアーカイブ メールボックスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="327be-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="327be-107">アーカイブ メールボックスを有効にしていない場合は、処理が実行されないため、保持中のメールボックスの [回復可能なアイテム] フォルダー内のアイテムは、14 日間の保存期間が経過しても、アーカイブ メールボックスに移動されません。</span><span class="sxs-lookup"><span data-stu-id="327be-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="327be-108">特に、ユーザーのアーカイブ メールボックスを有効にしないと、保持中のメールボックスから何も削除されないため、[回復可能なアイテム] フォルダーの記憶域クォータを超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="327be-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="327be-109">この制限を超える可能性を減らすのに役立つ、回復可能なアイテム フォルダーの記憶域クォータは、Exchange Online のメールボックスに保持が置かれると、自動的に 30 GB から 100 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="327be-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="327be-110">アーカイブ メールボックスを有効にした場合は、アーカイブ メールボックスの [回復可能なアイテム] フォルダーの記憶域クォータも、30 GB から 100 GB へ拡大されます。</span><span class="sxs-lookup"><span data-stu-id="327be-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="327be-111">Exchange Online で自動拡張アーカイブ機能が有効になっている場合、ユーザーのアーカイブ内の回復可能なアイテム フォルダーの記憶域クォータは無制限になります。</span><span class="sxs-lookup"><span data-stu-id="327be-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="327be-112"> [回復可能なアイテム] フォルダーの記憶域クォータを次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="327be-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="327be-113">**[回復可能なアイテム] フォルダーの場所**</span><span class="sxs-lookup"><span data-stu-id="327be-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="327be-114">**保持中でないメールボックス**</span><span class="sxs-lookup"><span data-stu-id="327be-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="327be-115">**保持中のメールボックス**</span><span class="sxs-lookup"><span data-stu-id="327be-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="327be-116">プライマリ メールボックス</span><span class="sxs-lookup"><span data-stu-id="327be-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="327be-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="327be-117">30 GB</span></span>  <br/> |<span data-ttu-id="327be-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="327be-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="327be-119">アーカイブ メールボックス<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="327be-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="327be-120">無制限</span><span class="sxs-lookup"><span data-stu-id="327be-120">Unlimited</span></span>  <br/> |<span data-ttu-id="327be-121">無制限</span><span class="sxs-lookup"><span data-stu-id="327be-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="327be-122">**[回復可能なアイテム] フォルダーの記憶域クォータの合計**</span><span class="sxs-lookup"><span data-stu-id="327be-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="327be-123">無制限</span><span class="sxs-lookup"><span data-stu-id="327be-123">Unlimited</span></span>  <br/> |<span data-ttu-id="327be-124">無制限</span><span class="sxs-lookup"><span data-stu-id="327be-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="327be-125"><sup>\*</sup>アーカイブ メールボックスの初期記憶域クォータは、ライセンスを持つユーザーの場合は 100 GB Exchange Online (プラン 2)です。</span><span class="sxs-lookup"><span data-stu-id="327be-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="327be-126">ただし、保持中のメールボックスに対して自動拡張アーカイブを有効にすると、アーカイブ メールボックスと回復可能なアイテム フォルダーの両方の記憶域クォータが 110 GB に増加します。</span><span class="sxs-lookup"><span data-stu-id="327be-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="327be-127">必要に応じて追加のアーカイブ ストレージ領域が準備され、その結果、無制限の量のアーカイブ ストレージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="327be-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="327be-128">自動拡張アーカイブの詳細については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="327be-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="327be-129">保持中のメールボックスのプライマリ メールボックスに含まれる [回復可能なアイテム] フォルダーの記憶域クォータが上限に近づいたら、次の対策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="327be-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="327be-130">**アーカイブ メールボックスを有効にして、自動拡張アーカイブを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="327be-130">**Enable the archive mailbox and turn on auto-expanding archiving.**</span></span> <span data-ttu-id="327be-131">[回復可能なアイテム] フォルダーに対して無制限のストレージ容量を有効にするには、アーカイブ メールボックスを有効にしてから、Exchange Online で自動拡張アーカイブ機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="327be-131">You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="327be-132">これにより、プライマリ メールボックスの [回復可能なアイテム] フォルダーに対して 110 GB、ユーザーのアーカイブにある [回復可能なアイテム] フォルダーの記憶域容量が無制限になります。</span><span class="sxs-lookup"><span data-stu-id="327be-132">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="327be-133">詳細については、「セキュリティ コンプライアンス センター[で](enable-archive-mailboxes.md)アーカイブ メールボックスを有効にする」と「コンプライアンス センターで&無制限のアーカイブを有効にする」を[参照](enable-unlimited-archiving.md)Office 365。</span><span class="sxs-lookup"><span data-stu-id="327be-133">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="327be-134">回復可能なアイテム フォルダーの記憶域クォータを超える近いメールボックスのアーカイブを有効にした後、管理フォルダー アシスタントを実行して、期限切れのアイテムをアーカイブ メールボックスの回復可能なアイテム フォルダーに移動するために、手動でアシスタントをトリガーしてメールボックスを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="327be-134">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved to the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="327be-135">この手順については、[手順 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="327be-135">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="327be-136">ユーザーのメールボックス内のその他のアイテムも新しいアーカイブ メールボックスに移動される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="327be-136">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="327be-137">アーカイブ メールボックスを有効にした後に、これが発生する可能性があることをユーザーに伝える方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="327be-137">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="327be-138">**保持中のメールボックスExchangeアイテム保持ポリシーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="327be-138">**Create a custom Exchange retention policy for mailboxes on hold.**</span></span> <span data-ttu-id="327be-139">訴訟ホールドまたは In-Place ホールドのメールボックスに対してアーカイブ メールボックスを有効にし、アーカイブを自動的に拡張する以外に、保持中のメールボックスのカスタム Exchange 保持ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="327be-139">In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom Exchange retention policy for mailboxes on hold.</span></span> <span data-ttu-id="327be-140">これにより、保持されていないメールボックスに適用される既定の MRM ポリシーとは異なる保持ポリシーを保留メールボックスに適用し、保持中のメールボックス用に設計された保持タグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="327be-140">This lets you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold, and lets you apply retention tags that are designed for mailboxes on hold.</span></span> <span data-ttu-id="327be-141">これには、回復可能なアイテム フォルダーの新しい保持タグの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="327be-141">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="327be-142">このトピックの残りの部分では、保持中のメールボックスのカスタム アイテム保持ポリシーを作成Exchange手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="327be-142">The remainder of this topic describes the step-by-step procedures to create a custom Exchange retention policy for mailboxes on hold.</span></span>
  
<span data-ttu-id="327be-143">[手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span><span class="sxs-lookup"><span data-stu-id="327be-143">[Step 1: Create a custom retention tag for the Recoverable Items folder](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)</span></span>

[<span data-ttu-id="327be-144">手順 2: 保持中のメールボックスExchange新しいアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="327be-144">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[<span data-ttu-id="327be-145">手順 3: 保持中のメールボックスExchange新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="327be-145">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="327be-146">(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する</span><span class="sxs-lookup"><span data-stu-id="327be-146">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="327be-147">手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する</span><span class="sxs-lookup"><span data-stu-id="327be-147">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="327be-148">最初の手順では、[回復可能なアイテム] フォルダーのカスタム保持タグ (アイテム保持ポリシー タグまたは RPT と呼ばれる) を作成します。</span><span class="sxs-lookup"><span data-stu-id="327be-148">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="327be-149">先に説明したように、この RPT により、ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダー内のアイテムは、ユーザーのアーカイブ メールボックスの [回復可能なアイテム] フォルダーへ移動されます。</span><span class="sxs-lookup"><span data-stu-id="327be-149">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="327be-150">回復可能なアイテム フォルダーの RPT を作成するには、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="327be-150">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="327be-151">Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="327be-151">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="327be-152">リモート PowerShell で Exchange Online に接続する</span><span class="sxs-lookup"><span data-stu-id="327be-152">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="327be-153">[回復可能なアイテム] フォルダーの新しい RPT を作成するには、次のコマンドを実行します。 </span><span class="sxs-lookup"><span data-stu-id="327be-153">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="327be-154">たとえば、次のコマンドは、保持期間が 30 日間の "回復可能なアイテム 30 日間" という名前の回復可能なアイテム フォルダーの RPT を作成します。</span><span class="sxs-lookup"><span data-stu-id="327be-154">For example, the following command creates an RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days.</span></span> <span data-ttu-id="327be-155">これは、アイテムが [回復可能なアイテム] フォルダーに移動されてから 30 日後に、そのアイテムがユーザーのアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されるということです。</span><span class="sxs-lookup"><span data-stu-id="327be-155">This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="327be-156">回復可能なアイテム RPT の保持期間  _(AgeLimitForRetention_ パラメーターで定義) は、RPT が適用されるメールボックスの削除済みアイテム保持期間と同じにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="327be-156">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="327be-157">これによりユーザーは、削除済みアイテムの保持期間全体にわたって、削除済みアイテムがアーカイブ メールボックスに移動される前に、削除済みアイテムを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="327be-157">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="327be-158">前の例では、保持期間は、メールボックスの削除済みアイテムの保持期間も 30 日であるという前提を基に、30 日に設定されていました。</span><span class="sxs-lookup"><span data-stu-id="327be-158">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="327be-159">既定Exchange Online削除済みアイテムを 14 日間保持するようにメールボックスが構成されています。</span><span class="sxs-lookup"><span data-stu-id="327be-159">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="327be-160">ただしこの設定は、最大 30 日にまで変更できます。</span><span class="sxs-lookup"><span data-stu-id="327be-160">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="327be-161">詳細については、「メールボックス内のメールボックスの削除済みアイテム保持期間を変更する[」を参照Exchange Online。](https://www.microsoft.com/?ref=go)</span><span class="sxs-lookup"><span data-stu-id="327be-161">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="327be-162">手順 2: 保持中のメールボックスExchange新しいアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="327be-162">Step 2: Create a new Exchange retention policy for mailboxes on hold</span></span>

<span data-ttu-id="327be-p110">次の手順では、新しいアイテム保持ポリシーを作成し、そのポリシーに保持タグ (手順 1 で作成した回復可能なアイテムの RPT を含む) を追加します。この新しいポリシーは、次の手順で保持中のメールボックスに適用します。 </span><span class="sxs-lookup"><span data-stu-id="327be-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="327be-p111">新しいアイテム保持ポリシーを作成する前に、追加する保持タグを決定します。Default MRM Policy に追加されている保持タグの一覧、および新しい保持タグを作成する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="327be-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="327be-167">Exchange Online の既定のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="327be-167">Default Retention Policy in Exchange Online </span></span>](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)
    
- [<span data-ttu-id="327be-168">アイテム保持ポリシー タグをサポートする既定のフォルダー</span><span class="sxs-lookup"><span data-stu-id="327be-168">Default folders that support Retention Policy Tags</span></span>](/exchange/security-and-compliance/messaging-records-management/default-folders)
    
- <span data-ttu-id="327be-169">「アイテム保持ポリシーの作成」の「保持タグの作成 [」セクション](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) 。</span><span class="sxs-lookup"><span data-stu-id="327be-169">The "Create a retention tag" section in the [Create a Retention Policy](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) topic.</span></span>
    
<span data-ttu-id="327be-170">EAC または PowerShell を使用Exchange Online保持ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="327be-170">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="327be-171">EAC を使用してアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="327be-171">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="327be-172">EAC で、[コンプライアンス管理の保持ポリシー] に \> **移動** し、[アイコンの追加 **]** ![ をクリックします ](../media/ITPro-EAC-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="327be-172">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="327be-173">**[新しい保持ポリシー]** ページの **[名前]** に、アイテム保持ポリシーの目的を説明する名前 (例: **MRM Policy for Mailboxes on Hold**) を入力します。 </span><span class="sxs-lookup"><span data-stu-id="327be-173">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="327be-174">[保持 **タグ] で、[** 追加アイコン **]** ![ をクリックします ](../media/ITPro-EAC-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="327be-174">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="327be-175">保持タグの一覧で、手順 1 で作成した回復可能なアイテムの RPT を選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="327be-175">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![カスタムの [回復可能なアイテム] 保持タグを選択する](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="327be-p112">アイテム保持ポリシーに追加する保持タグを選択します。たとえば、Default MRM Policy に含まれているのと同じタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="327be-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="327be-179">保持タグの追加が完了したら、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="327be-179">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="327be-180">**[保存]** をクリックして新しいアイテム保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="327be-180">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="327be-181">アイテム保持ポリシーにリンクされている保持タグが詳細ウィンドウに表示されることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="327be-181">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![アイテム保持ポリシーにリンクした保持タグが詳細ウィンドウに表示される](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="327be-183">PowerShell Exchange Online使用してアイテム保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="327be-183">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="327be-184">保持中のメールボックスの新しいアイテム保持ポリシーを作成するには、次のコマンドを実行します。 </span><span class="sxs-lookup"><span data-stu-id="327be-184">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="327be-185">たとえば、次のコマンドは、前の図に表示される保持ポリシーとリンクされた保持タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="327be-185">For example, the following command creates the retention policy and linked retention tags that are displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="327be-186">手順 3: 保持中のメールボックスExchange新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="327be-186">Step 3: Apply the new Exchange retention policy to mailboxes on hold</span></span>

<span data-ttu-id="327be-187">最後のステップでは、手順 2 で作成した新しいアイテム保持ポリシーを、組織内の保持中のメールボックスに適用します。</span><span class="sxs-lookup"><span data-stu-id="327be-187">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="327be-188">EAC または PowerShell Exchange Onlineを使用して、1 つのメールボックスまたは複数のメールボックスにアイテム保持ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="327be-188">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="327be-189">EAC を使用して新しい保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="327be-189">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="327be-190">[受信者 **メールボックス]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="327be-190">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="327be-191">リスト ビューで、アイテム保持ポリシーを適用するメールボックスを選択し、[編集] アイコン **を** ![ クリックします ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="327be-191">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="327be-192">**[ユーザー メールボックス]** ページで、**[メールボックスの機能]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="327be-192">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="327be-193">**[アイテム保持ポリシー]** から、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="327be-193">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="327be-194">EAC を使用して、アイテム保持ポリシーを複数のメールボックスに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="327be-194">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="327be-195">[受信者 **メールボックス]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="327be-195">Go to **Recipients** > **Mailboxes**.</span></span>
    
2. <span data-ttu-id="327be-196">リスト ビューで、Shift キーまたは Ctrl キーを使用して複数のメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="327be-196">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="327be-197">詳細ウィンドウで、**[その他のオプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="327be-197">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="327be-198">
            **[アイテム保持ポリシー]*\* 下で \*\*[更新]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="327be-198">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="327be-199">**[アイテム保持ポリシーの一括割り当て]** ページで、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="327be-199">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="327be-200">PowerShell Exchange Onlineを使用して新しいアイテム保持ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="327be-200">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="327be-201">PowerShell を使用Exchange Online単一のメールボックスに新しいアイテム保持ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="327be-201">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="327be-202">ただし、PowerShell の実際の機能は、訴訟ホールドまたは In-Place 保留に設定されている組織内のすべてのメールボックスをすばやく識別し、1 つのコマンドで保持中のすべてのメールボックスに新しい保持ポリシーを適用する方法です。</span><span class="sxs-lookup"><span data-stu-id="327be-202">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="327be-203">PowerShell を使用して 1 つExchangeメールボックスにアイテム保持ポリシーを適用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="327be-203">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="327be-204">すべての例で、手順 2 で作成したアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="327be-204">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="327be-205">この例では、Pilar Pinilla のメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="327be-205">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="327be-206">この例では、組織内の訴訟ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="327be-206">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="327be-207">この例では、組織内のインプレース ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="327be-207">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="327be-208">**Get-Mailbox** コマンドレットを使用すると、新しいアイテム保持ポリシーが適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="327be-208">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="327be-209">以下は、前の例で実行したコマンドを使用して、"MRM Policy for Mailboxes on Hold" というアイテム保持ポリシーが、訴訟ホールド中のメールボックスとインプレース ホールド中のメールボックスに適用されたことを確認する例です。</span><span class="sxs-lookup"><span data-stu-id="327be-209">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="327be-210">(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する</span><span class="sxs-lookup"><span data-stu-id="327be-210">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="327be-211">新しい Exchange アイテム保持ポリシーを保留メールボックスに適用した後、管理フォルダー アシスタントが新しいアイテム保持ポリシーの設定を使用してこれらのメールボックスを処理するには、Exchange Online で最大 7 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="327be-211">After you apply the new Exchange retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="327be-212">管理フォルダー アシスタントが実行されるのを待つ代わりに、**Start-ManagedFolderAssistant** コマンドレットを使用して、アシスタントを手動でトリガーし、新しいアイテム保持ポリシーを適用したメールボックスを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="327be-212">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="327be-213">Pilar Pinilla のメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="327be-213">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="327be-214">保持中のすべてのメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="327be-214">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="327be-215">詳細情報</span><span class="sxs-lookup"><span data-stu-id="327be-215">More information</span></span>

- <span data-ttu-id="327be-216">ユーザーのアーカイブ メールボックスを有効にした後は、メールボックスの他のアイテムも ([回復可能なアイテム] フォルダー内のアイテムだけではなく) アーカイブ メールボックスに移動される可能性があることをユーザーに通知することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="327be-216">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="327be-217">これは、Exchange Online メールボックスに割り当てられた既定の MRM ポリシーには、アイテムがメールボックスに配信された日付から 2 年後、またはユーザーが作成した日付から 2 年後にアイテムをアーカイブ メールボックスに移動する保持タグ (Default 2 years move to archive) が含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="327be-217">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="327be-218">詳細については、「既定のアイテム保持[ポリシー」を参照Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="327be-218">For more information, see [Default Retention Policy in Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)</span></span>
    
- <span data-ttu-id="327be-219">ユーザーのアーカイブ メールボックスを有効にした後は、アーカイブ メールボックス内の [回復可能なアイテム] フォルダーに含まれる削除済みアイテムを回復できることをユーザーに通知することもできます。</span><span class="sxs-lookup"><span data-stu-id="327be-219">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="327be-220">アーカイブ メールボックスの [削除済みOutlook] フォルダーを選択し、[ホーム] タブの [サーバーから削除済みアイテムを回復する] をクリックすると、この操作を **実行できます。** 削除済みアイテムの回復の詳細については、「削除済みアイテムを復元する」を参照 [OutlookをWindows。](https://go.microsoft.com/fwlink/p/?LinkId=624829)</span><span class="sxs-lookup"><span data-stu-id="327be-220">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span>