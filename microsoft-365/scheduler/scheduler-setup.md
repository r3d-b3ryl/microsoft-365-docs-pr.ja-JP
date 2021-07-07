---
title: スケジューラの設定 Microsoft 365。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: スケジューラの設定 Microsoft 365。
ms.openlocfilehash: f44dc509e28c19c320418c28dda6146331669cde
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314478"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="22e9e-103">Scheduler for Microsoft 365 を設定する</span><span class="sxs-lookup"><span data-stu-id="22e9e-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="22e9e-104">スケジューラをセットアップするには、Microsoft 365前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="22e9e-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="22e9e-105">必要なもの</span><span class="sxs-lookup"><span data-stu-id="22e9e-105">What do I need?</span></span> | <span data-ttu-id="22e9e-106">説明</span><span class="sxs-lookup"><span data-stu-id="22e9e-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="22e9e-107">Cortanaメールボックス</span><span class="sxs-lookup"><span data-stu-id="22e9e-107">Cortana mailbox</span></span> |<span data-ttu-id="22e9e-108">テナント管理者は、"Cortana" メールボックス (つまり、cortana@yourdomain.com) として機能するメールボックスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e9e-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="22e9e-109">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="22e9e-109">Exchange Online mailbox</span></span> |<span data-ttu-id="22e9e-110">ユーザーはメールと予定表Exchange Online必要があります</span><span class="sxs-lookup"><span data-stu-id="22e9e-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="22e9e-111">スケジューラ ライセンス</span><span class="sxs-lookup"><span data-stu-id="22e9e-111">Scheduler license</span></span> |<span data-ttu-id="22e9e-112">ライセンスと価格の情報については[、「Scheduler for Microsoft 365」 を参照してください](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="22e9e-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="22e9e-113">ユーザーのメールボックスを作成Cortana</span><span class="sxs-lookup"><span data-stu-id="22e9e-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="22e9e-114">テナントExchangeメールボックスは、テナントの Cortana メールボックスとして機能し、テナントとの間で電子メールを送受信Cortana。</span><span class="sxs-lookup"><span data-stu-id="22e9e-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="22e9e-115">ユーザーに送信Cortanaメールは、保持ポリシーに基づいてCortanaのメールボックスに保持されます。</span><span class="sxs-lookup"><span data-stu-id="22e9e-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="22e9e-116">ユーザー メールボックスをMicrosoft 365 管理センターするには、ユーザー メールボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e9e-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="22e9e-117">30 日間の保持ポリシーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22e9e-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="22e9e-118">メールボックスのプライマリ SMTP Cortanaの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e9e-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="22e9e-119">"Cortana@yourdomain.com"、'CortanaScheduler@contoso.com'、"Cortana" などの名前。Scheduler@yourdomain.com」 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22e9e-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="22e9e-120">メールボックスをスケジューラ アシスタントとして指定する</span><span class="sxs-lookup"><span data-stu-id="22e9e-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="22e9e-121">スケジューラの一意のメールボックスCortanaした後、メールボックスを正式に作成Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e9e-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="22e9e-122">スケジューラ メールボックスを指定Cortana、ユーザーに代わって会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="22e9e-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="22e9e-123">スケジューラ メールボックスのCortana指定するには、承認された管理者が 1 行の PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e9e-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="22e9e-124">Connect、組織Microsoft 365 PowerShell のリモート実行領域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22e9e-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="22e9e-125">スケジューラのメールボックスを指定するには、次の PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="22e9e-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="22e9e-126">Cortana スケジューラ メールボックスでこの "set" コマンドを実行した後、このメールボックスが "SchedulerAssistant" である点に注意する新しい "PersistedCapability" がメールボックスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="22e9e-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="22e9e-127">以前に行ったことがない場合は、次の手順に従って組織を Power [Microsoft 365 Connect Shell](../enterprise/connect-to-microsoft-365-powershell.md)に接続します。</span><span class="sxs-lookup"><span data-stu-id="22e9e-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="22e9e-128">組織で現在スケジューラ アシスタントとして設定されているメールボックスをCortana、get 関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="22e9e-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="22e9e-129">SchedulerAssistant 機能を設定するには、スケジューラ メールボックスが完全なプロビジョニングを完了するために最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22e9e-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="22e9e-130">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="22e9e-130">Exchange Online mailbox</span></span>

<span data-ttu-id="22e9e-131">スケジューラは、ユーザーに対するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="22e9e-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="22e9e-132">会議の開催者は、スケジューラがExchange Onlineメールボックスと予定表を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e9e-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="22e9e-133">Exchange の要件</span><span class="sxs-lookup"><span data-stu-id="22e9e-133">Exchange requirements</span></span>

<span data-ttu-id="22e9e-134">スケジューラのライセンスに加えて、次のいずれかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="22e9e-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="22e9e-135">Microsoft 365 E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="22e9e-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="22e9e-136">Business Basic, Business, Business Standard, Business プレミアム</span><span class="sxs-lookup"><span data-stu-id="22e9e-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="22e9e-137">Office 365 E1、A1、E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="22e9e-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="22e9e-138">Business Essentials, Business プレミアム</span><span class="sxs-lookup"><span data-stu-id="22e9e-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="22e9e-139">Exchange Onlineプラン 1 またはプラン 2 ライセンス。</span><span class="sxs-lookup"><span data-stu-id="22e9e-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="22e9e-140">**現在、Microsoft 365** は英語でのみ、世界中のマルチテナントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="22e9e-140">**Scheduler for Microsoft 365** is currently available for worldwide multi-tenants, in English only.</span></span></br>
>
> <span data-ttu-id="22e9e-141">中国で 21Vianet がOffice 365を運用しているユーザー、またはデータ トラスティ German Telekom を使用するドイツのクラウドを使用する Microsoft 365 のユーザーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="22e9e-141">It is not available for users of Office 365 operated by 21Vianet in China or users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="22e9e-142">ドイツのユーザーでも、そのデータがドイツのデータセンター以外の場所にある場合は、サポートされます。</span><span class="sxs-lookup"><span data-stu-id="22e9e-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
> <span data-ttu-id="22e9e-143">この機能は、GCC、Consumer、GCC High、DoD などの政府機関向けクラウドのユーザーに対してもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22e9e-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
