---
title: Microsoft の予約をオンまたはオフにする
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365 で Microsoft の予約にアクセスする方法について説明します。
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126593"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="cfd5e-103">Microsoft の予約をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="cfd5e-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="cfd5e-104">予約は、組織全体または特定のユーザーに対してオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="cfd5e-105">ユーザーに対して予約を有効にすると、ユーザーは予約ページを作成し、予定表を作成して、他のユーザーに時間を表示させることができます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="cfd5e-106">これらのセクションで説明する管理者コントロールは、21Vianet (中国) のお客様が運用している Office 365 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="cfd5e-107">Microsoft 365 管理センターを使用して、組織の予約をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="cfd5e-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="cfd5e-108">グローバル管理者として Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="cfd5e-109">管理センターで、[ **設定**] [組織の設定] に移動し、   \> **Org Settings** [**予約**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="cfd5e-110">[組織で予約を **使用できるよう** にする] チェックボックスをオンにして、組織の予約を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cfd5e-111">予約を無効にすると、予約ページの作成と管理を含む、サービスへのすべてのアクセスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="cfd5e-112">[ **Save Changes**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="cfd5e-113">PowerShell を使用して組織の予約をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="cfd5e-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="cfd5e-114">PowerShell コマンドレット [Set](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)を使用して、組織の予約をオンまたはオフにするには、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="cfd5e-115">個々のユーザーの予約を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="cfd5e-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="cfd5e-116">個々のユーザーに対して予約を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="cfd5e-117">Microsoft 365 管理センターに移動し、[ **ユーザー** の \> **アクティブなユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="cfd5e-118">目的のユーザーを選択して、[ **ライセンスとアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="cfd5e-119">[ **アプリ** ] を展開し、[Microsoft 予約] のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="cfd5e-120">空き時間情報を共有する前にスタッフの承認を必須にする</span><span class="sxs-lookup"><span data-stu-id="cfd5e-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="cfd5e-121">管理者は、組織内の従業員に対して、予約ページを通じて書籍を参照できるようにするために、組織内の従業員にオプトインを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="cfd5e-122">この設定は、Microsoft 365 管理センターの [**設定** の予約] の下にあり \> **Settings** \> **Bookings** ます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="cfd5e-123">この設定を有効にすると、予定表にスタッフとして追加された従業員は、受信した電子メール通知の承認/拒否リンクを見つけます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="cfd5e-124">この機能は、全世界の Microsoft 365 ユーザーに徐々にロールアウトされています。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="cfd5e-125">Microsoft 365 管理センターでこのオプションが表示されない場合は、もう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="cfd5e-126">ソーシャル共有オプションをブロックする</span><span class="sxs-lookup"><span data-stu-id="cfd5e-126">Block social sharing options</span></span>

<span data-ttu-id="cfd5e-127">管理者は、ソーシャルネットワークで予約ページを共有する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="cfd5e-128">この設定は、Microsoft 365 管理センターの [**設定** の予約] の下にあり \> **Settings** \> **Bookings** ます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="cfd5e-129">この機能は、全世界の Microsoft 365 ユーザーに徐々にロールアウトされています。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="cfd5e-130">Microsoft 365 管理センターでこのオプションが表示されない場合は、もう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="cfd5e-131">選択したユーザーのみに予約予定表の作成を許可する</span><span class="sxs-lookup"><span data-stu-id="cfd5e-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="cfd5e-132">ポリシーの制限を使用すると、ライセンスが付与されたユーザーが予約予定表を作成できないように制限できます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="cfd5e-133">最初に、組織全体で予約を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="cfd5e-134">組織内のすべてのユーザーは、予約ライセンスを持っていますが、ポリシーに含まれるもののみが予約予定表を作成し、作成した予定表にアクセスできるユーザーを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="cfd5e-135">このポリシーに含まれているユーザーは、新しい予約予定表を作成したり、既存の予約予定表に任意の容量 (管理者の役割を含む) にスタッフとして追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="cfd5e-136">このポリシーに含まれていないユーザーは、新しい予約予定表を作成することができず、実行しようとするとエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="cfd5e-137">Exchange Online PowerShell を使用して、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="cfd5e-138">Exchange Online のコマンドレットの実行の詳細については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfd5e-139">次の手順では、組織内に他の Outlook Web App (OWA) メールボックスポリシーが作成されていないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="cfd5e-140">予約予定表の作成が許可されるユーザーの新しいメールボックスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="cfd5e-141">(予約予定表の作成は、新しいメールボックスポリシーによって既定で許可されます。)</span><span class="sxs-lookup"><span data-stu-id="cfd5e-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="cfd5e-142">詳細については、「 [新しい-Owamが Boxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="cfd5e-143">予約予定表を作成するためのアクセス許可を付与するユーザーごとに、このコマンドを実行して、このポリシーを関連するユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="cfd5e-144">詳細については、「[Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="cfd5e-145">オプション: 組織内の他のすべてのユーザーに対して予約を無効にする場合は、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="cfd5e-146">詳細については、「[Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="cfd5e-147">OWA メールボックスポリシーの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd5e-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="cfd5e-148">Exchange Online で Outlook on the web メールボックスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="cfd5e-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="cfd5e-149">Exchange Online のメールボックスで Outlook on the web メールボックスポリシーを適用または削除する</span><span class="sxs-lookup"><span data-stu-id="cfd5e-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
