---
title: 訴訟ホールドを作成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: メールボックスを訴訟ホールドの対象にし、調査中にすべてのメールボックスのコンテンツを保持する方法について説明します。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750061"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="8d833-103">訴訟ホールドを作成する</span><span class="sxs-lookup"><span data-stu-id="8d833-103">Create a Litigation Hold</span></span>

<span data-ttu-id="8d833-104">メールボックスを訴訟ホールドの対象にし、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツを保持できます。</span><span class="sxs-lookup"><span data-stu-id="8d833-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="8d833-105">メールボックスを訴訟ホールドの対象にすると、ユーザーのアーカイブ メールボックス (有効である場合) も保持されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="8d833-106">保持を作成するときに、保持期間 (*時間ベースの保持* とも呼ばれます) を指定すると、削除および変更されたアイテムが指定した期間保持され、その後メールボックスから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="8d833-107">または、コンテンツを無期限に保持 (*無限の保持* と呼ばれます) するか、訴訟ホールドが削除されるまで保持することができます。</span><span class="sxs-lookup"><span data-stu-id="8d833-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="8d833-108">保持期間を指定する場合は、メッセージが受信された、またはメールボックス アイテムが作成された日付から計算されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="8d833-109">訴訟ホールドを作成すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8d833-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="8d833-110">ユーザーによって完全に削除されたアイテムは、保持期間中ユーザーのメールボックス内にある回復可能なアイテム フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>

- <span data-ttu-id="8d833-111">ユーザーによって回復可能なアイテム フォルダーからパージされたアイテムは、保持期間中は保持されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>

- <span data-ttu-id="8d833-112">ユーザーのプライマリ メールボックスにある回復可能なアイテム フォルダーのストレージ クォータは、30 GB から 110 GB へと増加します。</span><span class="sxs-lookup"><span data-stu-id="8d833-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>

- <span data-ttu-id="8d833-113">ユーザーのプライマリ メールボックスおよびアーカイブ メールボックス内にあるアイテムは保持されます</span><span class="sxs-lookup"><span data-stu-id="8d833-113">Items in the user's primary and the archive mailboxes are retained</span></span>

## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="8d833-114">Exchange Online (プラン 2) ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8d833-114">Assign an Exchange Online Plan 2 license</span></span>

<span data-ttu-id="8d833-115">Exchange Online メールボックスを訴訟ホールドの対象にするには、Exchange Online (プラン 2) ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d833-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="8d833-116">メールボックスに Exchange Online (プラン 1) ライセンスが割り当てられている場合は、別の Exchange Online Archiving ライセンスをメールボックスに割り当てて、メールボックスを保持の対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d833-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="8d833-117">組織Office 365 Education訴訟ホールドは、補足機能を備えた Office 365 A1 プラン 1 ライセンスを含むExchange Onlineサブスクリプションでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8d833-117">For Office 365 Education organizations, Litigation Hold is supported in Office 365 A1 subscriptions, which include an Exchange Online Plan 1 license with supplemental features.</span></span> <span data-ttu-id="8d833-118">詳細については、「サービスの説明」の「Exchange Online機能」[セクションOffice 365 Education参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features)。</span><span class="sxs-lookup"><span data-stu-id="8d833-118">For more information, see the "Exchange Online features" section in the [Office 365 Education service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).</span></span>

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="8d833-119">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="8d833-119">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="8d833-120">ここでは、Exchange 管理センターを使用してメールボックスを訴訟ホールドの対象にする手順を示します。</span><span class="sxs-lookup"><span data-stu-id="8d833-120">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="8d833-121">[https://outlook.office.com/ecp](https://outlook.office.com/ecp) に移動し、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="8d833-121">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="8d833-122">左側のナビゲーション ウィンドウで、**[受信者]、[メールボックス]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d833-122">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="8d833-123">訴訟ホールドの対象とするメールボックスを選択し、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d833-123">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="8d833-124">メールボックスのプロパティ ページで、 **[メールボックスの機能]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d833-124">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="8d833-125">**[訴訟ホールド:無効]** で、 **[有効]** をクリックすると、メールボックスが訴訟ホールドの対象になります。</span><span class="sxs-lookup"><span data-stu-id="8d833-125">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="8d833-126">**[訴訟ホールド]** ページで、以下のオプション情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d833-126">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="8d833-127">**訴訟ホールド期間 (日)** - このボックスを使用して時間ベースの保持を作成し、メールボックスを訴訟ホールドの対象にするときにメールボックス アイテムを保持する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d833-127">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="8d833-128">期間は、メールボックス アイテムが受信または作成された日から計算されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-128">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="8d833-129">特定のアイテムの保持期間が終了すると、そのアイテムは保持されなくなります。</span><span class="sxs-lookup"><span data-stu-id="8d833-129">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="8d833-130">このボックスが空白の場合は、アイテムは無期限に、またはその保持が解除されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-130">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="8d833-131">日数で期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d833-131">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="8d833-132">**メモ** - このボックスを使用して、メールボックスが訴訟ホールドの対象であることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8d833-132">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="8d833-133">メモは、Outlook 2010 以降を使用しているユーザーのメールボックスの [アカウント情報] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-133">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="8d833-134">このページにアクセスするには、Outlook で **[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d833-134">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="8d833-135">**URL** - このボックスを使用して、訴訟ホールドに関する詳細については Web サイトを参照するようにユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="8d833-135">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="8d833-136">この URL は、Outlook 2010 以降を使用しているユーザーのメールボックスの [アカウント情報] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-136">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="8d833-137">このページにアクセスするには、Outlook で **[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d833-137">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="8d833-138">**[訴訟ホールド]** ページの **[保存]** をクリックして、メールボックスのプロパティ ページにある **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d833-138">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="8d833-139">PowerShell を使用して訴訟ホールドを作成する</span><span class="sxs-lookup"><span data-stu-id="8d833-139">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="8d833-140">[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) で次のコマンドを実行することで、訴訟ホールドを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d833-140">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="8d833-141">前のコマンドでは保持時間が指定されていないため、アイテムを無期限に保持します。</span><span class="sxs-lookup"><span data-stu-id="8d833-141">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="8d833-142">タイム ベースのホールドを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d833-142">To create a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="8d833-143">詳細については、「[Set-Mailbox](/powershell/module/exchange/set-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d833-143">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="8d833-144">訴訟ホールドはどのように機能しますか?</span><span class="sxs-lookup"><span data-stu-id="8d833-144">How does Litigation Hold work?</span></span>

<span data-ttu-id="8d833-145">通常の削除済みアイテムのワークフローでは、ユーザーがメールボックス アイテムを完全に削除 (Shift キー + Delete キー) したり、削除済みアイテム フォルダーから削除したりすると、そのアイテムは回復可能なアイテム フォルダーの Deletions サブフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-145">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="8d833-146">さらに削除ポリシー (削除の保持アクションで構成された保持タグ) によっても、アイテムは保存期間が終了したときに Deletions サブフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-146">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="8d833-147">ユーザーが回復可能なアイテム フォルダーのアイテムをパージすると、または、アイテムの削除済みアイテムの保持期間の有効期限が切れると、そのアイテムは回復可能なアイテム フォルダーの Purges サブフォルダーに移動され、完全削除のマークが付けられます。</span><span class="sxs-lookup"><span data-stu-id="8d833-147">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="8d833-148">このアイテムは、次にメールボックスが管理フォルダー アシスタント (MFA) によって処理されるときに Exchange からパージされます。</span><span class="sxs-lookup"><span data-stu-id="8d833-148">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="8d833-p109">メールボックスが訴訟ホールドの対象になっている場合、Purges サブフォルダーのアイテムは、訴訟ホールドで指定された保持期間中は保持されます。保持期間は、アイテムが受信または作成された日付から計算され、Purges サブフォルダーでのアイテムの保持期間を定義します。Purges サブフォルダーでのアイテムの保持期間を過ぎると、アイテムには完全削除のマークが付けられ、次回そのメールボックスが、MFA で処理されるときに、Exchange から消去されます。メールボックスが無期限の保持の対象になっている場合、そのアイテムは Purges サブフォルダーから消去されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8d833-p109">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="8d833-153">次の図は、[回復可能なアイテム] フォルダー内のサブフォルダーと保持のワークフロー プロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="8d833-153">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![訴訟ホールドのライフサイクル](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="8d833-155">メールボックスが電子情報開示ケースに関連する保持の対象になっている場合、パージされたアイテムは Deletions サブフォルダーから DiscoveryHolds サブフォルダーに移動され、メールボックスが電子情報開示の保持から解放されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="8d833-155">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
