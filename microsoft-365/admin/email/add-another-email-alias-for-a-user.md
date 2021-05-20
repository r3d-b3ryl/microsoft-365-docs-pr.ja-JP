---
title: ユーザーに別のメール エイリアスを追加する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'ビジネスアカウントのMicrosoft 365に関連付けられた電子メール エイリアスと呼ばれる複数の電子メール アドレスを設定する方法について説明します。 '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572107"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="540bc-103">ユーザーに別のメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="540bc-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="540bc-104">この記事は、ビジネス サブスクリプションを持つMicrosoft 365管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="540bc-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="540bc-105">ホーム ユーザー向けではありません。</span><span class="sxs-lookup"><span data-stu-id="540bc-105">It's not for home users.</span></span>
  
<span data-ttu-id="540bc-106">Microsoft 365のプライマリ電子メール アドレスは、通常、アカウントの作成時にユーザーが割り当てられた電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="540bc-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="540bc-107">ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。</span><span class="sxs-lookup"><span data-stu-id="540bc-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="540bc-108">また、ビジネス アカウントのMicrosoft 365に関連付けられた複数の電子メール アドレスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="540bc-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="540bc-109">これらの追加アドレスをエイリアスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="540bc-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="540bc-110">たとえば、Jenna が jenna@contosoco.com メールアドレスを持っているが、その名前で彼女を参照する人がいるため、jen@contosoco.com でメールを受信したいとします。</span><span class="sxs-lookup"><span data-stu-id="540bc-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="540bc-111">両方のメールアドレスが Jenna の受信トレイに移動するように、彼女のエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="540bc-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="540bc-p104">ユーザーあたり最大 400 個のエイリアスを作成できます。追加の料金やライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="540bc-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="540bc-114">info@NodPublishers.com や sales@NodPublishers.com などの単一の電子メール アドレスに送信された電子メールを複数のユーザーが管理する場合は、共有メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="540bc-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="540bc-115">詳細については、「 [共有メールボックスを作成する](create-a-shared-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="540bc-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="540bc-116">ユーザーにメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="540bc-116">Add email aliases to a user</span></span>

<span data-ttu-id="540bc-117">これを行うには [、管理者権限](../add-users/about-admin-roles.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="540bc-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="540bc-118">管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="540bc-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="540bc-119">[ **アクティブなユーザー** ] ページで、[ **ユーザー名と電子メールの管理**] >ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="540bc-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="540bc-120">ユーザーに割り当てられたライセンスがない場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="540bc-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="540bc-121">[+ **エイリアスの追加] を** 選択し、ユーザの新しいエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="540bc-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="540bc-122">**"EmailAddresses" というパラメータ名と一致するパラメータが見つからない** というエラー メッセージが表示された場合は、テナントの設定が完了するまでに少し時間がかかっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="540bc-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="540bc-123">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="540bc-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="540bc-124">セットアッププロセスが完了するまでしばらく待ってから、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="540bc-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="540bc-125">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="540bc-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="540bc-126">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="540bc-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="540bc-127">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="540bc-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="540bc-128">別のドメイン名を一覧に追加するには、「 [Microsoft 365にドメインを追加する](../setup/add-domain.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="540bc-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="540bc-129">完了したら、[ **変更を保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="540bc-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="540bc-130">新しいエイリアスがMicrosoft 365全体を通して入力されるまで 24 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="540bc-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="540bc-131">これで、ユーザーはプライマリ アドレスとエイリアスを持つことになります。</span><span class="sxs-lookup"><span data-stu-id="540bc-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="540bc-132">たとえば、イライザ・ホフマンのプライマリアドレスである Eliza@NodPublishers.com と彼女のエイリアス Sales@NodPublishers.com に送信されるすべてのメールは、イライザの受信トレイに送信されます。</span><span class="sxs-lookup"><span data-stu-id="540bc-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="540bc-133">**ユーザーが返信すると *、From* アドレスは、Outlookクライアントに依存します。ウェブ上のOutlookは、電子メールが受信されたエイリアスを使用します(これをピンポン原則と呼びます)。Outlookデスクトップは、彼女のプライマリ電子メールエイリアスを使用します。**</span><span class="sxs-lookup"><span data-stu-id="540bc-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="540bc-134">たとえば、メッセージが Sales@NodPublishers.com に送信され、そのメッセージが Eliza の受信トレイに届く場合を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="540bc-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="540bc-135">イライザがデスクトップを使用 Outlookしてメッセージに返信すると、プライマリ電子メール アドレスは Sales@NodPublishers.com ではなく Eliza@NodPublishers.com として表示されます。</span><span class="sxs-lookup"><span data-stu-id="540bc-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="540bc-136">"パラメータ名 EmailAddresses と一致するパラメータが見つかりません" が表示されましたか?</span><span class="sxs-lookup"><span data-stu-id="540bc-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="540bc-137">**"EmailAddresses" というパラメータ名と一致するパラメータが見つからない** 場合は、テナントの設定が完了するまでに少し時間がかかっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="540bc-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="540bc-138">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="540bc-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="540bc-139">セットアッププロセスが完了するまでしばらく待ってから、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="540bc-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="540bc-140">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="540bc-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="540bc-141">GoDaddy または別のパートナーからサブスクリプションを購入した場合</span><span class="sxs-lookup"><span data-stu-id="540bc-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="540bc-142">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="540bc-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="540bc-143">プロキシ アドレスから簡単にメールを送信する</span><span class="sxs-lookup"><span data-stu-id="540bc-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="540bc-144">2021 年 4 月に、ユーザーが web 上でOutlookを使用するときにエイリアスから簡単に送信できる新機能が展開されています。</span><span class="sxs-lookup"><span data-stu-id="540bc-144">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="540bc-145">テナント管理者がコマンドレットを使用するテナント管理者に機能がロールアウトされると `Set-OrganizationConfig -SendFromAliasEnabled $true` 、テナント内のユーザーは、各エントリがOutlook設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="540bc-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="540bc-146">エイリアスを選択すると、[作成] フォームの [差出人] ドロップダウンにエイリアスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="540bc-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="540bc-147">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="540bc-147">Related content</span></span>

<span data-ttu-id="540bc-148">[別のアドレスからメールを送信](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) する (記事)</span><span class="sxs-lookup"><span data-stu-id="540bc-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="540bc-149">[ユーザー名と電子メール アドレスを変更](../add-users/change-a-user-name-and-email-address.md) する (記事)</span><span class="sxs-lookup"><span data-stu-id="540bc-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="540bc-150">[Microsoft 365 でメールの転送を構成する](configure-email-forwarding.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="540bc-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
