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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'ビジネス アカウントに関連付けられたメール エイリアスと呼ばれる複数の電子メール アドレスをMicrosoft 365する方法について説明します。 '
ms.openlocfilehash: ab1a7b846bb35cce4656a3a5edf941961f5398c2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394029"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="20948-103">ユーザーに別のメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="20948-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="20948-104">この記事は、ビジネス サブスクリプションMicrosoft 365管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="20948-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="20948-105">ホーム ユーザー向けではありません。</span><span class="sxs-lookup"><span data-stu-id="20948-105">It's not for home users.</span></span>
  
<span data-ttu-id="20948-106">ユーザーがアカウントを作成Microsoft 365割り当てられた電子メール アドレスは、通常、ユーザーのプライマリ メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="20948-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="20948-107">ユーザーが別のユーザーにメールを送信するときに、通常、メール アプリの [ *差出人*  ] フィールドに表示されているものが、プライマリ メール アドレスとなります。</span><span class="sxs-lookup"><span data-stu-id="20948-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="20948-108">また、複数の電子メール アドレスをビジネス アカウントのユーザー Microsoft 365関連付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="20948-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="20948-109">これらの追加アドレスをエイリアスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="20948-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="20948-110">たとえば、Jenna が電子メール アドレス jenna@contosoco.com を持っているが、jen@contosoco.com でメールを受け取りたい場合は、その名前で彼女を参照する人もいたとします。</span><span class="sxs-lookup"><span data-stu-id="20948-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="20948-111">両方のメール アドレスが Jenna の受信トレイに移動できるよう、エイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="20948-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
  
<span data-ttu-id="20948-p104">ユーザーあたり最大 400 個のエイリアスを作成できます。追加の料金やライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="20948-p104">You can create up to 400 aliases for a user. No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="20948-114">複数のユーザーが 1 つの電子メール アドレスに送信されるメールを管理する場合 (info@NodPublishers.com、sales@NodPublishers.com メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="20948-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="20948-115">詳細については、「共有メールボックスの [作成」を参照してください](create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="20948-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="20948-116">ユーザーにメール エイリアスを追加する</span><span class="sxs-lookup"><span data-stu-id="20948-116">Add email aliases to a user</span></span>

<span data-ttu-id="20948-117">これを行うには [、管理者のアクセス許可](../add-users/about-admin-roles.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="20948-117">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

1. <span data-ttu-id="20948-118">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="20948-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="20948-119">[アクティブ な **ユーザー] ページ** で、[ユーザー名とメール> **管理する] のユーザーを選択します**。</span><span class="sxs-lookup"><span data-stu-id="20948-119">On the **Active Users** page, select the user > **Manage username and email**.</span></span> <span data-ttu-id="20948-120">ユーザーにライセンスが割り当てられていない場合、このオプションは表示しません。</span><span class="sxs-lookup"><span data-stu-id="20948-120">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="20948-121">[+ **エイリアスの追加] を選択** し、ユーザーの新しいエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="20948-121">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="20948-122">エラー メッセージが表示された場合は、パラメーター名 **'EmailAddresses,"** と一致するパラメーターが見つかりません。これは、テナントのセットアップを終了するにはもう少し時間がかかるか、最近追加した場合はカスタム ドメインを使用します。</span><span class="sxs-lookup"><span data-stu-id="20948-122">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="20948-123">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="20948-123">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="20948-124">しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="20948-124">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="20948-125">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="20948-125">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="20948-126">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20948-126">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="20948-127">メール エイリアスは、ドロップダウン リストにあるドメインで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20948-127">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="20948-128">リストに別のドメイン名を追加するには、「[ドメインをリストに追加する」をMicrosoft 365。](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="20948-128">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="20948-129">完了したら、[変更の保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20948-129">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="20948-130">新しいエイリアスが新しいエイリアスに設定されるまで 24 時間Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="20948-130">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="20948-131">これで、ユーザーはプライマリ アドレスとエイリアスを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="20948-131">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="20948-132">たとえば、Eliza Hoffman のプライマリ アドレス Eliza@NodPublishers.com とエイリアス Sales@NodPublishers.com に送信されたメールはすべて、Eliza の受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="20948-132">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="20948-133">**ユーザーが返信すると *、From* アドレスはユーザーのクライアントOutlookされます。Outlook on the webが受信されたエイリアスを使用します (これを ping-pong の原則と呼ぶ)。Outlookデスクトップは、プライマリ メール エイリアスを使用します。**</span><span class="sxs-lookup"><span data-stu-id="20948-133">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="20948-134">たとえば、メッセージがメールに送信され、Sales@NodPublishers.com 受信トレイに届いたとします。</span><span class="sxs-lookup"><span data-stu-id="20948-134">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="20948-135">Eliza がデスクトップを使用してメッセージに返信Outlook、メインの電子メール アドレスは、Eliza@NodPublishers.com として表示 Sales@NodPublishers.com。</span><span class="sxs-lookup"><span data-stu-id="20948-135">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="20948-136">"パラメーター名 EmailAddresses に一致するパラメーターが見つかりません" を取得しましたか?</span><span class="sxs-lookup"><span data-stu-id="20948-136">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>

<span data-ttu-id="20948-137">"パラメーター名 **EmailAddresses** に一致するパラメーターが見つかりません" というエラー メッセージが表示された場合は、テナントのセットアップを完了するにはもう少し時間がかかっています。最近追加した場合は、カスタム ドメインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20948-137">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="20948-138">セットアップ プロセスが完了するには、最大 4 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="20948-138">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="20948-139">しばらく待って、セットアップ プロセスが完了するまでの時間を持ち、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="20948-139">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="20948-140">問題が解決しない場合は、サポートにご連絡ください。サポートでは完全な同期を行います。</span><span class="sxs-lookup"><span data-stu-id="20948-140">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="20948-141">GoDaddy または別のパートナーからサブスクリプションを購入した場合</span><span class="sxs-lookup"><span data-stu-id="20948-141">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="20948-142">GoDaddy または別のパートナーからサブスクリプションを購入した場合、新しいエイリアスをプライマリとして設定するには、GoDaddy またはパートナーの管理コンソールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20948-142">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="20948-143">プロキシ アドレスからメールを簡単に送信する</span><span class="sxs-lookup"><span data-stu-id="20948-143">Sending email from the proxy address easily</span></span>

<span data-ttu-id="20948-144">2021 年 7 月に新しい機能が展開され、ユーザーはエイリアスから簡単にメールを送信Outlook on the web。</span><span class="sxs-lookup"><span data-stu-id="20948-144">A new feature is rolling out in July 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="20948-145">テナント管理者がコマンドレットを使用するテナントに機能がロールアウトすると、テナント内のユーザーは、各エントリが Outlook 設定のエイリアスに対応するチェック ボックスの一覧にアクセスできます。 `Set-OrganizationConfig -SendFromAliasEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="20948-145">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="20948-146">エイリアスを選択すると、[新規作成] フォームの [From] ドロップダウンにエイリアスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20948-146">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="20948-147">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="20948-147">Related content</span></span>

<span data-ttu-id="20948-148">[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (記事)</span><span class="sxs-lookup"><span data-stu-id="20948-148">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>

<span data-ttu-id="20948-149">[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="20948-149">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>

<span data-ttu-id="20948-150">[Microsoft 365 でメールの転送を構成する](configure-email-forwarding.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="20948-150">[Configure email forwarding in Microsoft 365](configure-email-forwarding.md) (article)</span></span>
