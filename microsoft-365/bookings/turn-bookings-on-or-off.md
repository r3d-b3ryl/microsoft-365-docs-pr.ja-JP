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
description: Microsoft Bookings にアクセスする方法については、Microsoft 365。
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913768"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="f6095-103">Microsoft Bookings を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f6095-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="f6095-104">予約は、組織全体または特定のユーザーに対して有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f6095-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="f6095-105">ユーザーの予約を有効にした場合、ユーザーは [予約] ページを作成し、予定表を作成し、他のユーザーが自分と一緒に時間を予約できます。</span><span class="sxs-lookup"><span data-stu-id="f6095-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="f6095-106">これらのセクションで説明する管理コントロールは、21Vianet (中国) Office 365によって運用されているユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="f6095-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="f6095-107">管理センターを使用して組織の予約を有効またはMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="f6095-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f6095-108">管理者センターにMicrosoft 365グローバル管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="f6095-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="f6095-109">管理センターで、[組織] \*\*\*\* ページに移動   \> **設定、[設定]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6095-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="f6095-110">[組織で予約 **を使用して組織の予約** を有効または無効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f6095-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f6095-111">Bookings をオフにすると、Bookings ページの作成と管理を含むサービスへのすべてのアクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="f6095-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="f6095-112">[変更 **の保存] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6095-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="f6095-113">PowerShell を使用して組織の予約を有効またはオフにする</span><span class="sxs-lookup"><span data-stu-id="f6095-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="f6095-114">PowerShell コマンドレット[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)を使用して組織の予約を有効またはConnect [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) Exchange Online実行し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6095-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="f6095-115">個々のユーザーの予約をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="f6095-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="f6095-116">個々のユーザーの予約を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f6095-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="f6095-117">管理センターに移動Microsoft 365、[ユーザー] [アクティブな **ユーザー]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6095-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="f6095-118">目的のユーザーを選択し、[ライセンスとアプリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6095-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="f6095-119">[アプリ **] を展開** し、[Microsoft Bookings] のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f6095-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="f6095-120">空き時間情報を共有する前にスタッフの承認を要求する</span><span class="sxs-lookup"><span data-stu-id="f6095-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="f6095-121">管理者は、予約ページを通じて予約可能になる前に、利用可能な情報を共有する前に、組織内の従業員にオプトインを要求できます。</span><span class="sxs-lookup"><span data-stu-id="f6095-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="f6095-122">この設定は、[予約] の下 **Microsoft 365管理センター** \> **設定設定** \> **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="f6095-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="f6095-123">この設定を有効にすると、予約カレンダーにスタッフとして追加された従業員は、受信した電子メール通知に [承認/拒否] リンクを見つける。</span><span class="sxs-lookup"><span data-stu-id="f6095-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="f6095-124">この機能は、世界中の顧客に徐々にMicrosoft 365されています。</span><span class="sxs-lookup"><span data-stu-id="f6095-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="f6095-125">管理センターでこのオプションが表示Microsoft 365、すぐに確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6095-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="f6095-126">ソーシャル共有オプションをブロックする</span><span class="sxs-lookup"><span data-stu-id="f6095-126">Block social sharing options</span></span>

<span data-ttu-id="f6095-127">管理者は、予約ページをソーシャル ネットワーク上で共有する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f6095-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="f6095-128">この設定は、[予約] の下 **Microsoft 365管理センター** \> **設定設定** \> **使用できます**。</span><span class="sxs-lookup"><span data-stu-id="f6095-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="f6095-129">この機能は、世界中の顧客に徐々にMicrosoft 365されています。</span><span class="sxs-lookup"><span data-stu-id="f6095-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="f6095-130">管理センターでこのオプションが表示Microsoft 365、すぐに確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6095-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="f6095-131">選択したユーザーにのみ予約カレンダーの作成を許可する</span><span class="sxs-lookup"><span data-stu-id="f6095-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="f6095-132">ポリシー制限を使用すると、ライセンスユーザーが予約カレンダーを作成できないのを制限できます。</span><span class="sxs-lookup"><span data-stu-id="f6095-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="f6095-133">まず、組織全体で予約を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6095-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="f6095-134">組織内のすべてのユーザーは Bookings ライセンスを持ちますが、ポリシーに含まれているユーザーだけが Bookings カレンダーを作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="f6095-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="f6095-135">このポリシーに含まれるユーザーは、新しい Bookings カレンダーを作成し、既存の Bookings カレンダーに任意の容量 (管理者ロールを含む) のスタッフとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="f6095-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="f6095-136">このポリシーに含まれていないユーザーは、新しい予約カレンダーを作成できないので、新しい予約カレンダーを作成しようとしてもエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6095-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="f6095-137">PowerShell を使用して次のコマンドを実行Exchange Onlineがあります。</span><span class="sxs-lookup"><span data-stu-id="f6095-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="f6095-138">コマンドレットの実行の詳細についてはExchange Online PowerShell のConnect[をExchange Onlineしてください](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f6095-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6095-139">以下の手順では、組織内に他Outlook Web App (OWA) メールボックス ポリシーが作成されていないことを前提とします。</span><span class="sxs-lookup"><span data-stu-id="f6095-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="f6095-140">予約カレンダーの作成を許可する必要があるユーザー用の新しいメールボックス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6095-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="f6095-141">(予約カレンダーの作成は、新しいメールボックス ポリシーによって既定で許可されます)。</span><span class="sxs-lookup"><span data-stu-id="f6095-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="f6095-142">詳細については [、「New-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/new-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f6095-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="f6095-143">このポリシーを関連するユーザーに割り当てるには、予約カレンダーを作成するアクセス許可を付与するユーザーごとにこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6095-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="f6095-144">詳細については、「[Set-CASMailbox](/powershell/module/exchange/set-casmailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6095-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="f6095-145">オプション: 組織内の他のすべてのユーザーの予約を無効にする場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6095-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="f6095-146">詳細については、「[Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6095-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="f6095-147">OWA メールボックス ポリシーの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6095-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="f6095-148">Web メールボックス ポリシー Outlookポリシーに対するポリシーを作成Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f6095-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="f6095-149">サーバー内のメールボックスOutlookの Web メールボックス ポリシーに対してメールボックスを適用または削除Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f6095-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)