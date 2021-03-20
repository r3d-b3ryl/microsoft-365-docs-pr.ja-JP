---
title: Microsoft Bookings を有効または無効にする
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365 で Microsoft Bookings にアクセスする方法について説明します。
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913768"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="bb739-103">Microsoft Bookings を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="bb739-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="bb739-104">予約は、組織全体または特定のユーザーに対して有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bb739-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="bb739-105">ユーザーの予約を有効にした場合、ユーザーは [予約] ページを作成し、予定表を作成し、他のユーザーが自分と一緒に時間を予約できます。</span><span class="sxs-lookup"><span data-stu-id="bb739-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="bb739-106">これらのセクションで説明されている管理コントロールは、21Vianet (中国) のお客様Office 365 Operated では使用できません。</span><span class="sxs-lookup"><span data-stu-id="bb739-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="bb739-107">Microsoft 365 管理センターを使用して組織の予約をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="bb739-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="bb739-108">グローバル管理者として Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="bb739-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="bb739-109">管理センターで、[設定] [組織の  **設定**]   \> **に移動し、[** 予約]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bb739-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="bb739-110">[組織で予約 **を使用して組織の予約** を有効または無効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bb739-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bb739-111">Bookings をオフにすると、Bookings ページの作成と管理を含むサービスへのすべてのアクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="bb739-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="bb739-112">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bb739-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="bb739-113">PowerShell を使用して組織の予約を有効またはオフにする</span><span class="sxs-lookup"><span data-stu-id="bb739-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="bb739-114">PowerShell コマンドレット [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)を使用して組織の予約を有効またはオフにする場合は [、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb739-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="bb739-115">個々のユーザーの予約をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="bb739-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="bb739-116">個々のユーザーの予約を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="bb739-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="bb739-117">Microsoft 365 管理センターに移動し、[ユーザー] [アクティブユーザー **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bb739-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="bb739-118">目的のユーザーを選択し、[ライセンスとアプリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bb739-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="bb739-119">[アプリ **] を展開** し、[Microsoft Bookings] のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="bb739-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="bb739-120">空き時間情報を共有する前にスタッフの承認を要求する</span><span class="sxs-lookup"><span data-stu-id="bb739-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="bb739-121">管理者は、予約ページを通じて予約可能になる前に、利用可能な情報を共有する前に、組織内の従業員にオプトインを要求できます。</span><span class="sxs-lookup"><span data-stu-id="bb739-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="bb739-122">この設定は、Microsoft 365 管理センターの[設定設定の予約] \> **で** \> **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="bb739-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="bb739-123">この設定を有効にすると、予約カレンダーにスタッフとして追加された従業員は、受信した電子メール通知に [承認/拒否] リンクを見つける。</span><span class="sxs-lookup"><span data-stu-id="bb739-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="bb739-124">この機能は、Microsoft 365 のお客様に世界全体で段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="bb739-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="bb739-125">Microsoft 365 管理センターにこのオプションが表示しない場合は、すぐに確認してください。</span><span class="sxs-lookup"><span data-stu-id="bb739-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="bb739-126">ソーシャル共有オプションをブロックする</span><span class="sxs-lookup"><span data-stu-id="bb739-126">Block social sharing options</span></span>

<span data-ttu-id="bb739-127">管理者は、予約ページをソーシャル ネットワーク上で共有する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb739-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="bb739-128">この設定は、Microsoft 365 管理センターの[設定設定の予約] \> **で** \> **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="bb739-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="bb739-129">この機能は、Microsoft 365 のお客様に世界全体で段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="bb739-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="bb739-130">Microsoft 365 管理センターにこのオプションが表示しない場合は、すぐに確認してください。</span><span class="sxs-lookup"><span data-stu-id="bb739-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="bb739-131">選択したユーザーにのみ予約カレンダーの作成を許可する</span><span class="sxs-lookup"><span data-stu-id="bb739-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="bb739-132">ポリシー制限を使用すると、ライセンスユーザーが予約カレンダーを作成できないのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="bb739-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="bb739-133">まず、組織全体で予約を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb739-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="bb739-134">組織内のすべてのユーザーは Bookings ライセンスを持ちますが、ポリシーに含まれているユーザーだけが Bookings カレンダーを作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb739-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="bb739-135">このポリシーに含まれるユーザーは、新しい Bookings カレンダーを作成し、既存の Bookings カレンダーに任意の容量 (管理者ロールを含む) のスタッフとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="bb739-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="bb739-136">このポリシーに含まれていないユーザーは、新しい予約カレンダーを作成できないので、新しい予約カレンダーを作成しようとしてもエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb739-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="bb739-137">Exchange Online PowerShell を使用して次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb739-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="bb739-138">Exchange Online コマンドレットの実行の詳細については [、「Connect to Exchange Online PowerShell」を参照してください](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bb739-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb739-139">以下の手順では、組織内に他Outlook Web App (OWA) メールボックス ポリシーが作成されていないことを前提とします。</span><span class="sxs-lookup"><span data-stu-id="bb739-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="bb739-140">予約カレンダーの作成を許可する必要があるユーザー用の新しいメールボックス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb739-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="bb739-141">(予約カレンダーの作成は、新しいメールボックス ポリシーによって既定で許可されます)。</span><span class="sxs-lookup"><span data-stu-id="bb739-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="bb739-142">詳細については [、「New-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/new-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="bb739-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="bb739-143">このポリシーを関連するユーザーに割り当てるには、予約カレンダーを作成するアクセス許可を付与するユーザーごとにこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb739-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="bb739-144">詳細については、「[Set-CASMailbox](/powershell/module/exchange/set-casmailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb739-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="bb739-145">オプション: 組織内の他のすべてのユーザーの予約を無効にする場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb739-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="bb739-146">詳細については、「[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb739-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="bb739-147">OWA メールボックス ポリシーの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb739-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="bb739-148">Exchange Online で Outlook on the Web メールボックス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="bb739-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="bb739-149">Exchange Online のメールボックスで Outlook on the Web メールボックス ポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="bb739-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)