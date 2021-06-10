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
ms.openlocfilehash: ba1e178545001473bf73eea3eb02b5ab1c7bf084
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861481"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="40f5d-103">スケジューラのセットアップ Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="40f5d-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="40f5d-104">スケジューラをセットアップするには、Microsoft 365前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40f5d-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="40f5d-105">**必要なもの**</span><span class="sxs-lookup"><span data-stu-id="40f5d-105">**What do I need?**</span></span> |<span data-ttu-id="40f5d-106">**説明**</span><span class="sxs-lookup"><span data-stu-id="40f5d-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="40f5d-107">Cortana メールボックス</span><span class="sxs-lookup"><span data-stu-id="40f5d-107">Cortana mailbox</span></span> |<span data-ttu-id="40f5d-108">テナント管理者は、"Cortana" メールボックスとして機能するメールボックスを設定する必要があります (つまり、cortana@yourdomain.com)。</span><span class="sxs-lookup"><span data-stu-id="40f5d-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="40f5d-109">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="40f5d-109">Exchange Online mailbox</span></span> |<span data-ttu-id="40f5d-110">ユーザーはメールと予定表Exchange Online必要があります</span><span class="sxs-lookup"><span data-stu-id="40f5d-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="40f5d-111">スケジューラ ライセンス</span><span class="sxs-lookup"><span data-stu-id="40f5d-111">Scheduler license</span></span> |<span data-ttu-id="40f5d-112">ライセンスと価格の情報については[、「Scheduler for Microsoft 365」 を参照してください](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="40f5d-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="40f5d-113">Cortana のメールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="40f5d-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="40f5d-114">テナントExchangeメールボックスは、Cortana との間で電子メールを送受信するテナントの Cortana メールボックスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="40f5d-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="40f5d-115">Cortana に送信されたメールはすべて、保持ポリシーに基づいてテナントの Cortana メールボックスに保持されます。</span><span class="sxs-lookup"><span data-stu-id="40f5d-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="40f5d-116">管理者センター Microsoft 365を使用して、ユーザー メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40f5d-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="40f5d-117">30 日間の保持ポリシーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40f5d-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="40f5d-118">メールボックスのプライマリ SMTP アドレスで Cortana という名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="40f5d-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="40f5d-119">"Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"、"Cortana.Scheduler@yourdomain.com" などの名前をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40f5d-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="40f5d-120">メールボックスをスケジューラ アシスタントとして指定する</span><span class="sxs-lookup"><span data-stu-id="40f5d-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="40f5d-121">Cortana Scheduler の一意のメールボックスが作成された後、メールボックスを正式に作成Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="40f5d-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="40f5d-122">Cortana Scheduler メールボックスを指定すると、ユーザーに代わって会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="40f5d-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="40f5d-123">Cortana Scheduler メールボックスを指定するには、承認された管理者が 1 行の PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40f5d-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="40f5d-124">Connect、組織Microsoft 365 PowerShell のリモート実行領域を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40f5d-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="40f5d-125">スケジューラのメールボックスを指定するには、次の PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="40f5d-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="40f5d-126">Cortana Scheduler メールボックスでこの "set" コマンドを実行した後、このメールボックスが "SchedulerAssistant" である点に注意する新しい "PersistedCapability" がメールボックスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="40f5d-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="40f5d-127">以前に行ったことがない場合は、次の手順に従って組織を PowerShell に接続します。 Connect PowerShell Microsoft 365 - Microsoft 365 Enterprise | [Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="40f5d-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="40f5d-128">現在 Cortana Scheduler アシスタントとして設定されている組織内のメールボックスを確認するには、get 関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="40f5d-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> <span data-ttu-id="40f5d-129">SchedulerAssistant 機能を設定するには、スケジューラ メールボックスが完全なプロビジョニングを完了するために最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40f5d-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="40f5d-130">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="40f5d-130">Exchange Online mailbox</span></span>
<span data-ttu-id="40f5d-131">スケジューラは、ユーザーに対するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="40f5d-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="40f5d-132">会議の開催者は、スケジューラがExchange Onlineメールボックスと予定表を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="40f5d-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="40f5d-133">Exchange の要件</span><span class="sxs-lookup"><span data-stu-id="40f5d-133">Exchange requirements</span></span>

<span data-ttu-id="40f5d-134">スケジューラのライセンスに加えて、次のいずれかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="40f5d-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="40f5d-135">Microsoft 365 E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="40f5d-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="40f5d-136">Business Basic, Business, Business Standard, Business プレミアム</span><span class="sxs-lookup"><span data-stu-id="40f5d-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="40f5d-137">Office 365E1、A1、E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="40f5d-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="40f5d-138">Business Essentials, Business プレミアム</span><span class="sxs-lookup"><span data-stu-id="40f5d-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="40f5d-139">Exchange Onlineプラン 1 またはプラン 2 ライセンス。</span><span class="sxs-lookup"><span data-stu-id="40f5d-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="40f5d-140">21Vianet **Microsoft 365** 21Vianet が運営するユーザーは、Office 365スケジューラを使用できません。</span><span class="sxs-lookup"><span data-stu-id="40f5d-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="40f5d-141">また、データ トラスティ German Telekom をMicrosoft 365ドイツのクラウドを使用しているユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="40f5d-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="40f5d-142">ドイツのユーザーでも、そのデータがドイツのデータセンター以外の場所にある場合は、サポートされます。</span><span class="sxs-lookup"><span data-stu-id="40f5d-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="40f5d-143">この機能は、GCC、Consumer、GCC High、DoD などの政府機関向けクラウドのユーザーに対してもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40f5d-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
