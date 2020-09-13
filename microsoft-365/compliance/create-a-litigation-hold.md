---
title: 訴訟ホールドを作成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: 調査中にメールボックスのすべてのコンテンツを保持しながら、メールボックスを訴訟ホールドの対象にする方法について説明します。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4bcb857095a63c06caa6e9762496ca74afeead04
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546989"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="f6131-103">訴訟ホールドを作成する</span><span class="sxs-lookup"><span data-stu-id="f6131-103">Create a Litigation Hold</span></span>

<span data-ttu-id="f6131-104">メールボックスを訴訟ホールドの対象にして、削除済みアイテムや変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="f6131-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="f6131-105">ユーザーメールボックスを訴訟ホールドの対象にすると、ユーザーのアーカイブメールボックス内のコンテンツ (有効になっている場合) も保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="f6131-106">保持を作成するときに、削除および変更されたアイテムが指定した期間保持され、メールボックスから完全に削除されるように、保持期間 ( *時間ベースの保持*とも呼ばれます) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6131-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="f6131-107">または、コンテンツを無期限に ( *無限保持*と呼ばれます)、または訴訟ホールドが解除されるまで保持することができます。</span><span class="sxs-lookup"><span data-stu-id="f6131-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="f6131-108">保持期間を指定する場合は、メッセージが受信された日付、またはメールボックスアイテムが作成された日付から計算されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="f6131-109">訴訟ホールドを作成すると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="f6131-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="f6131-110">ユーザーによって完全に削除されたアイテムは、保留中のユーザーのメールボックス内の [回復可能なアイテム] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="f6131-111">ユーザーが [回復可能なアイテム] フォルダーから削除されたアイテムは、保持期間中は保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="f6131-112">回復可能なアイテムフォルダーの記憶域のクォータは、30 GB から 110 GB に増加しました。</span><span class="sxs-lookup"><span data-stu-id="f6131-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="f6131-113">ユーザーのプライマリおよびアーカイブメールボックスのアイテムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-113">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="f6131-114">Exchange Online プラン2ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f6131-114">Assign an Exchange Online Plan 2 license</span></span>

- <span data-ttu-id="f6131-115">Exchange Online メールボックスを訴訟ホールドの対象にするには、Exchange online プラン2ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6131-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="f6131-116">メールボックスに Exchange Online プラン1ライセンスが割り当てられている場合は、それを保持するために別の Exchange Online アーカイブライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6131-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="f6131-117">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="f6131-117">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="f6131-118">Exchange 管理センターを使用してメールボックスを訴訟ホールドの対象にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6131-118">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="f6131-119">に移動 [https://outlook.office.com/ecp](https://outlook.office.com/ecp) し、全体管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f6131-119">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="f6131-120">左側のナビゲーションウィンドウで [ **受信者 > メールボックス** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6131-120">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="f6131-121">訴訟ホールドに配置するメールボックスを選択し、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6131-121">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="f6131-122">メールボックスのプロパティ ページで、 **[メールボックスの機能]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6131-122">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="f6131-123">**[訴訟ホールド:無効]** で、 **[有効]** をクリックすると、メールボックスが訴訟ホールドの対象になります。</span><span class="sxs-lookup"><span data-stu-id="f6131-123">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="f6131-124">[ **訴訟ホールド** ] ページで、次のオプション情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f6131-124">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="f6131-125">[**訴訟ホールド期間**(日)]-このボックスを使用して、時間ベースの保持を作成し、メールボックスが訴訟ホールドの対象となっているときにメールボックスアイテムを保持する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6131-125">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="f6131-126">期間は、メールボックス アイテムが受信または作成された日から計算されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-126">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="f6131-127">特定のアイテムの保持期間が経過すると、そのアイテムは保持されなくなります。</span><span class="sxs-lookup"><span data-stu-id="f6131-127">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="f6131-128">このボックスを空白のままにすると、アイテムは無期限に、または保持が解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-128">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="f6131-129">日数で期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6131-129">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="f6131-130">**注** : このボックスを使用して、メールボックスが訴訟ホールドの対象であることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f6131-130">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="f6131-131">メモは、Outlook 2010 以降を使用している場合は、ユーザーのメールボックスの [アカウント情報] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-131">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="f6131-132">このページにアクセスするには、ユーザーが Outlook で [ **ファイル** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6131-132">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="f6131-133">**URL** -訴訟ホールドの詳細については、このボックスを使用して、ユーザーに web サイトを送信します。</span><span class="sxs-lookup"><span data-stu-id="f6131-133">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="f6131-134">この URL は、Outlook 2010 以降を使用している場合に、ユーザーのメールボックスの [アカウント情報] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-134">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="f6131-135">このページにアクセスするには、ユーザーが Outlook で [ **ファイル** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6131-135">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="f6131-136">[**訴訟ホールド**] ページの [**保存**] をクリックし、メールボックスのプロパティページで [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6131-136">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="f6131-137">PowerShell を使用して訴訟ホールドを作成する</span><span class="sxs-lookup"><span data-stu-id="f6131-137">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="f6131-138">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行して、訴訟ホールドを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6131-138">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="f6131-139">保持期間が指定されていないため、前のコマンドではアイテムが無制限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-139">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="f6131-140">時間ベースの保持を作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6131-140">To created a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="f6131-141">詳細については、「[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6131-141">For more information, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="f6131-142">訴訟ホールドのしくみ</span><span class="sxs-lookup"><span data-stu-id="f6131-142">How does Litigation Hold work?</span></span>

<span data-ttu-id="f6131-143">通常、削除済みアイテムワークフローでは、ユーザーが完全に削除 (Shift + Delete) したり、[削除済みアイテム] フォルダーから削除したりすると、メールボックスアイテムは回復可能なアイテムフォルダーの削除サブフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-143">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="f6131-144">削除ポリシー (削除保持アクションで構成された保持タグ) も、保持期間が経過すると、アイテムを削除サブフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f6131-144">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="f6131-145">ユーザーが [回復可能なアイテム] フォルダー内のアイテムを削除したとき、またはアイテムの削除済みアイテムの保存期間が経過すると、アイテムは [回復可能なアイテム] フォルダー内の [消去] サブフォルダーに移動され、永続的な削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="f6131-145">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="f6131-146">このメールボックスは、次に管理フォルダーアシスタント (MFA) によって処理されたときに Exchange から削除されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-146">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="f6131-p108">メールボックスが訴訟ホールドの対象になっている場合、Purges サブフォルダーのアイテムは、訴訟ホールドで指定された保持期間中は保持されます。保持期間は、アイテムが受信または作成された日付から計算され、Purges サブフォルダーでのアイテムの保持期間を定義します。Purges サブフォルダーでのアイテムの保持期間を過ぎると、アイテムには完全削除のマークが付けられ、次回そのメールボックスが、MFA で処理されるときに、Exchange から消去されます。メールボックスが無期限の保持の対象になっている場合、そのアイテムは Purges サブフォルダーから消去されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f6131-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="f6131-151">次の図は、[回復可能なアイテム] フォルダー内のサブフォルダーと保持のワークフロー プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f6131-151">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![訴訟ホールドライフサイクル](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="f6131-153">電子情報開示ケースに関連付けられた保留リストがメールボックスに配置されている場合、削除されたアイテムは、削除サブフォルダーから DiscoveryHolds サブフォルダーに移動され、メールボックスが電子情報開示ホールドから解放されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="f6131-153">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
  
