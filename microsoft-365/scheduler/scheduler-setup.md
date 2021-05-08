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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286188"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="d0f3b-103">スケジューラのセットアップ Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0f3b-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="d0f3b-104">スケジューラをセットアップするには、Microsoft 365前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="d0f3b-105">**必要なもの**</span><span class="sxs-lookup"><span data-stu-id="d0f3b-105">**What do I need?**</span></span> |<span data-ttu-id="d0f3b-106">**説明**</span><span class="sxs-lookup"><span data-stu-id="d0f3b-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="d0f3b-107">Cortana メールボックス</span><span class="sxs-lookup"><span data-stu-id="d0f3b-107">Cortana mailbox</span></span> |<span data-ttu-id="d0f3b-108">テナント管理者は、"Cortana" メールボックスとして機能するメールボックスを設定する必要があります (つまり、cortana@yourdomain.com)。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="d0f3b-109">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="d0f3b-109">Exchange Online mailbox</span></span> |<span data-ttu-id="d0f3b-110">ユーザーはメールと予定表Exchange Online必要があります</span><span class="sxs-lookup"><span data-stu-id="d0f3b-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="d0f3b-111">スケジューラ ライセンス</span><span class="sxs-lookup"><span data-stu-id="d0f3b-111">Scheduler license</span></span> |<span data-ttu-id="d0f3b-112">ライセンスと価格の情報については[、「Scheduler for Microsoft 365」 を参照してください](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="d0f3b-113">Cortana のメールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="d0f3b-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="d0f3b-114">テナントExchangeメールボックスは、Cortana との間で電子メールを送受信するテナントの Cortana メールボックスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="d0f3b-115">Cortana に送信されたメールはすべて、保持ポリシーに基づいてテナントの Cortana メールボックスに保持されます。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="d0f3b-116">管理センター Microsoft 365を使用して、新しいメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="d0f3b-117">30 日間の保持ポリシーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="d0f3b-118">メールボックスのプライマリ SMTP アドレスで Cortana という名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="d0f3b-119">"Cortana@yourdomain.com"、"CortanaScheduler@contoso.com"、"Cortana.Scheduler@yourdomain.com" などの名前をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="d0f3b-120">Cortana メールボックスを有効にするには、microsoft (scheduler_m365@microsoft.com) に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d0f3b-121">スケジューラ サービスを使用する Cortana メールボックスを構成するには、Microsoft に問い合 scheduler_m365@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="d0f3b-122">Cortana メールボックスを有効にすると、最大 2 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="d0f3b-123">Exchange Online メールボックス</span><span class="sxs-lookup"><span data-stu-id="d0f3b-123">Exchange Online mailbox</span></span>
<span data-ttu-id="d0f3b-124">スケジューラは、ユーザーに対するMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="d0f3b-125">会議の開催者は、スケジューラがExchange Onlineメールボックスと予定表を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="d0f3b-126">Exchange の要件</span><span class="sxs-lookup"><span data-stu-id="d0f3b-126">Exchange requirements</span></span>

<span data-ttu-id="d0f3b-127">スケジューラのライセンスに加えて、次のいずれかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="d0f3b-128">Microsoft 365 E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="d0f3b-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="d0f3b-129">Business Basic, Business, Business Standard, Business プレミアム</span><span class="sxs-lookup"><span data-stu-id="d0f3b-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="d0f3b-130">Office 365E1、A1、E3、A3、E5、A5</span><span class="sxs-lookup"><span data-stu-id="d0f3b-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="d0f3b-131">Business Essentials, Business プレミアム</span><span class="sxs-lookup"><span data-stu-id="d0f3b-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="d0f3b-132">Exchange Onlineプラン 1 またはプラン 2 ライセンス。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="d0f3b-133">21Vianet **Microsoft 365** 21Vianet が運営するユーザーは、Office 365スケジューラを使用できません。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="d0f3b-134">また、データ トラスティ German Telekom をMicrosoft 365ドイツのクラウドを使用しているユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="d0f3b-135">ドイツのユーザーでも、そのデータがドイツのデータセンター以外の場所にある場合は、サポートされます。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="d0f3b-136">この機能は、GCC、Consumer、GCC High、DoD などの政府機関向けクラウドのユーザーに対してもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d0f3b-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
