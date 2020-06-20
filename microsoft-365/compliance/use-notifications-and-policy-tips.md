---
title: メール通知を送信して、DLP ポリシーのポリシーのヒントを表示する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: データ損失防止 (DLP) ポリシーにポリシーヒントを追加して、DLP ポリシーと競合するコンテンツを使用していることをユーザーに通知する方法について説明します。
ms.openlocfilehash: a36d1de9a24136943b41f12fe7f12a44d9df59f1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819307"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="a781f-103">メール通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="a781f-103">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="a781f-104">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span><span class="sxs-lookup"><span data-stu-id="a781f-104">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span></span> <span data-ttu-id="a781f-105">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span><span class="sxs-lookup"><span data-stu-id="a781f-105">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span></span> <span data-ttu-id="a781f-106">This is where email notifications and policy tips can help.</span><span class="sxs-lookup"><span data-stu-id="a781f-106">This is where email notifications and policy tips can help.</span></span>
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="a781f-108">ポリシー ヒントは、誰かがコンテンツを使用していて、それが DLP ポリシーと競合している場合に表示される通知または警告です。たとえば、個人情報 (PII) が含まれ、外部ユーザーと共有されている OneDrive for Business サイト上の Excel ブックなどのコンテンツがこれに該当します。</span><span class="sxs-lookup"><span data-stu-id="a781f-108">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="a781f-109">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span><span class="sxs-lookup"><span data-stu-id="a781f-109">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span></span> <span data-ttu-id="a781f-110">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span><span class="sxs-lookup"><span data-stu-id="a781f-110">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="a781f-111">セキュリティ &amp; /コンプライアンスセンターでは、DLP ポリシーを作成するときに、ユーザー通知を次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-111">In the Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="a781f-112">選択したユーザーに、問題を説明するメール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="a781f-112">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="a781f-113">DLP ポリシーと競合しているコンテンツのポリシー ヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="a781f-113">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="a781f-114">Outlook on the web および Outlook 2013 以降のメールの場合は、メッセージの作成中、受信者の上のメッセージの上部にポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-114">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="a781f-115">OneDrive for Business アカウントまたは SharePoint Online サイトのドキュメントの場合、ポリシーヒントには、アイテムに表示される警告アイコンが示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-115">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="a781f-116">詳細情報を表示するには、アイテムを選択して**Information**から、 ![ ページの右上隅にある [情報情報] ウィンドウのアイコンを選択し ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) て、詳細ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="a781f-116">To view more information, you can select an item and then choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="a781f-117">DLP ポリシーに含まれている OneDrive for Business サイトまたは SharePoint Online サイトに格納されている Excel、PowerPoint、および Word ドキュメントでは、ポリシーヒントがメッセージバーおよび Backstage ビュー ([**ファイル**] メニュー情報) に表示され \> **Info**ます。</span><span class="sxs-lookup"><span data-stu-id="a781f-117">For Excel, PowerPoint, and Word documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="a781f-118">ユーザー通知を DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="a781f-118">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="a781f-119">DLP ポリシーを作成するときに、**ユーザー通知**を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a781f-119">When you create a DLP policy, you can enable **User notifications**.</span></span> <span data-ttu-id="a781f-120">ユーザー通知が有効になっている場合、Microsoft 365 は電子メール通知とポリシーヒントの両方を送信します。</span><span class="sxs-lookup"><span data-stu-id="a781f-120">When user notifications are enabled, Microsoft 365 sends out both email notifications and policy tips.</span></span> <span data-ttu-id="a781f-121">通知メールを送信するユーザー、電子メールテキスト、ポリシーヒントテキストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a781f-121">You can customize who notification emails are sent to, the email text and the policy tip text.</span></span>
  
1. <span data-ttu-id="a781f-122">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a781f-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a781f-123">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a781f-123">Sign in using your work or school account.</span></span> <span data-ttu-id="a781f-124">これで、セキュリティ/コンプライアンスセンターになってい &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="a781f-124">You're now in the Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="a781f-125">セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[データ損失防止]** \> **[ポリシー]** \> **[+ ポリシーの作成]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a781f-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[ポリシーの作成] ボタン](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="a781f-127">必要な種類の機密情報を保護する DLP ポリシー テンプレートを選び、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a781f-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="a781f-128">空のテンプレートから始めるには、**[カスタム]** \> **[カスタム ポリシー]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="a781f-129">ポリシーの名前を設定し、**[次へ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="a781f-130">DLP ポリシーで保護する場所を選ぶには、次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="a781f-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
   - <span data-ttu-id="a781f-131">**[Office 365 のすべての場所]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
   - <span data-ttu-id="a781f-132">**[自分で特定の場所を選択する]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
   <span data-ttu-id="a781f-133">すべての Exchange メールやすべての OneDrive アカウントなど、特定の場所全体を含めたり除外したりするには、その場所の **[状態]** をオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a781f-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
   <span data-ttu-id="a781f-134">特定の SharePoint サイトまたは OneDrive アカウントだけを含めるには、**[状態]** をオンに切り替えた後、**[含める]** の下のリンクをクリックして、特定のサイトまたはアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="a781f-135">**[詳細設定を使う]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="a781f-136">**[+ 新しいルール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a781f-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="a781f-137">ルール エディターで、**[ユーザー通知]** の状態をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a781f-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![ルール エディターのユーザー通知セクション](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> <span data-ttu-id="a781f-139">DLP ポリシーは、それらのドキュメントが新規か既存かにかかわらず、ポリシーに一致するすべてのドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-139">DLP policies apply to all documents that match the policy, whether those documents are new or existing.</span></span> <span data-ttu-id="a781f-140">ただし、電子メール通知は、新しいコンテンツが既存の DLP ポリシーと一致する場合にのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-140">However, an email notification is only generated when new content matches an existing DLP policy.</span></span> <span data-ttu-id="a781f-141">既存のコンテンツは保護されますが、電子メールによるユーザー通知は生成されません。</span><span class="sxs-lookup"><span data-stu-id="a781f-141">Existing content is protected, but will not generate a user notification via email.</span></span>
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="a781f-142">メール通知を設定するためのオプション</span><span class="sxs-lookup"><span data-stu-id="a781f-142">Options for configuring email notifications</span></span>

<span data-ttu-id="a781f-143">DLP ポリシーのそれぞれのルールで、次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="a781f-143">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="a781f-144">Send the notification to the people you choose.</span><span class="sxs-lookup"><span data-stu-id="a781f-144">Send the notification to the people you choose.</span></span> <span data-ttu-id="a781f-145">These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span><span class="sxs-lookup"><span data-stu-id="a781f-145">These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="a781f-146">Customize the text that's included in the notification by using HTML or tokens.</span><span class="sxs-lookup"><span data-stu-id="a781f-146">Customize the text that's included in the notification by using HTML or tokens.</span></span> <span data-ttu-id="a781f-147">See the section below for more information.</span><span class="sxs-lookup"><span data-stu-id="a781f-147">See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="a781f-148">電子メール通知は、グループまたは配布リストではなく、個々の受信者にのみ送信できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-148">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="a781f-149">電子メール通知をトリガーするのは新しいコンテンツだけです。</span><span class="sxs-lookup"><span data-stu-id="a781f-149">Only new content will trigger an email notification.</span></span> <span data-ttu-id="a781f-150">既存のコンテンツを編集すると、ポリシーヒントが表示されますが、電子メール通知はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="a781f-150">Editing existing content will trigger policy tips, but not an email notification.</span></span> 
  
![メール通知オプション](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="a781f-152">既定のメール通知</span><span class="sxs-lookup"><span data-stu-id="a781f-152">Default email notification</span></span>

<span data-ttu-id="a781f-153">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span><span class="sxs-lookup"><span data-stu-id="a781f-153">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span></span> <span data-ttu-id="a781f-154">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span><span class="sxs-lookup"><span data-stu-id="a781f-154">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span></span> <span data-ttu-id="a781f-155">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span><span class="sxs-lookup"><span data-stu-id="a781f-155">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知メッセージ](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="a781f-157">By default, notifications display text similar to the following for an item on a site.</span><span class="sxs-lookup"><span data-stu-id="a781f-157">By default, notifications display text similar to the following for an item on a site.</span></span> <span data-ttu-id="a781f-158">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span><span class="sxs-lookup"><span data-stu-id="a781f-158">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="a781f-159">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="a781f-159">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="a781f-160">**SharePoint または OneDrive for Business のドキュメントの既定の通知内容**</span><span class="sxs-lookup"><span data-stu-id="a781f-160">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="a781f-161">**Outlook メッセージの既定の通知内容**</span><span class="sxs-lookup"><span data-stu-id="a781f-161">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a781f-162">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="a781f-162">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="a781f-163">このアイテムは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-163">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="a781f-164">あなたのメール メッセージは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-164">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="a781f-165">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="a781f-165">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="a781f-166">This item conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-166">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-167">If you don't resolve this conflict, access to this file might be blocked.</span><span class="sxs-lookup"><span data-stu-id="a781f-167">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="a781f-168">あなたのメール メッセージは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-168">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-169">メッセージはすべての受信者に配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a781f-169">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="a781f-170">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="a781f-170">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="a781f-171">This item conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-171">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-172">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span><span class="sxs-lookup"><span data-stu-id="a781f-172">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="a781f-173">Your email message conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-173">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-174">The message wasn't delivered to all recipients.</span><span class="sxs-lookup"><span data-stu-id="a781f-174">The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="a781f-175">ユーザー設定のメール通知</span><span class="sxs-lookup"><span data-stu-id="a781f-175">Custom email notification</span></span>

<span data-ttu-id="a781f-176">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span><span class="sxs-lookup"><span data-stu-id="a781f-176">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span></span> <span data-ttu-id="a781f-177">The custom email notification supports HTML and has a 5,000-character limit.</span><span class="sxs-lookup"><span data-stu-id="a781f-177">The custom email notification supports HTML and has a 5,000-character limit.</span></span> <span data-ttu-id="a781f-178">You can use HTML to include images, formatting, and other branding in the notification.</span><span class="sxs-lookup"><span data-stu-id="a781f-178">You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="a781f-179">You can also use the following tokens to help customize the email notification.</span><span class="sxs-lookup"><span data-stu-id="a781f-179">You can also use the following tokens to help customize the email notification.</span></span> <span data-ttu-id="a781f-180">These tokens are variables that are replaced by specific information in the notification that's sent.</span><span class="sxs-lookup"><span data-stu-id="a781f-180">These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="a781f-181">**トークン**</span><span class="sxs-lookup"><span data-stu-id="a781f-181">**Token**</span></span>|<span data-ttu-id="a781f-182">**説明**</span><span class="sxs-lookup"><span data-stu-id="a781f-182">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a781f-183">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="a781f-183">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="a781f-184">アクションがコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-184">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="a781f-185">%%ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="a781f-185">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="a781f-186">SharePoint Online サイトまたは OneDrive for Business サイトのドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="a781f-186">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="a781f-187">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="a781f-187">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="a781f-188">The conditions that were matched by the content.</span><span class="sxs-lookup"><span data-stu-id="a781f-188">The conditions that were matched by the content.</span></span> <span data-ttu-id="a781f-189">Use this token to inform people of possible issues with the content.</span><span class="sxs-lookup"><span data-stu-id="a781f-189">Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![トークンがどこに表示されているかを示す通知メッセージ](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="a781f-191">ポリシー ヒントを構成するためのオプション</span><span class="sxs-lookup"><span data-stu-id="a781f-191">Options for configuring policy tips</span></span>

<span data-ttu-id="a781f-192">DLP ポリシー内の各ルールに関して、次の事柄を行うポリシー ヒントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-192">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="a781f-193">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span><span class="sxs-lookup"><span data-stu-id="a781f-193">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span></span> <span data-ttu-id="a781f-194">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span><span class="sxs-lookup"><span data-stu-id="a781f-194">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="a781f-195">Allow the person to override the DLP policy.</span><span class="sxs-lookup"><span data-stu-id="a781f-195">Allow the person to override the DLP policy.</span></span> <span data-ttu-id="a781f-196">Optionally, you can:</span><span class="sxs-lookup"><span data-stu-id="a781f-196">Optionally, you can:</span></span>
    
  - <span data-ttu-id="a781f-197">Require the person to enter a business justification for overriding the policy.</span><span class="sxs-lookup"><span data-stu-id="a781f-197">Require the person to enter a business justification for overriding the policy.</span></span> <span data-ttu-id="a781f-198">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a781f-198">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="a781f-199">Allow the person to report a false positive and override the DLP policy.</span><span class="sxs-lookup"><span data-stu-id="a781f-199">Allow the person to report a false positive and override the DLP policy.</span></span> <span data-ttu-id="a781f-200">This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span><span class="sxs-lookup"><span data-stu-id="a781f-200">This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![ポリシー ヒント オプション](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="a781f-202">たとえば、個人を特定できる情報 (PII) を検出する DLP ポリシーを OneDrive for Business サイトに適用する場合、このポリシーに次の 3 つのルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a781f-202">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="a781f-203">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip.</span><span class="sxs-lookup"><span data-stu-id="a781f-203">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip.</span></span> <span data-ttu-id="a781f-204">For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span><span class="sxs-lookup"><span data-stu-id="a781f-204">For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="a781f-205">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span><span class="sxs-lookup"><span data-stu-id="a781f-205">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span></span> <span data-ttu-id="a781f-206">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span><span class="sxs-lookup"><span data-stu-id="a781f-206">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="a781f-207">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally.</span><span class="sxs-lookup"><span data-stu-id="a781f-207">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally.</span></span> <span data-ttu-id="a781f-208">Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-208">Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="a781f-209">ルールを上書きするポリシー ヒントを使用する際に把握しておくべきいくつかの点を以下に記します。</span><span class="sxs-lookup"><span data-stu-id="a781f-209">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="a781f-210">上書きオプションはルールごとのオプションで、対象ルール内のすべてのアクションを上書きします (ただし、上書きできない通知の送信は除きます)。</span><span class="sxs-lookup"><span data-stu-id="a781f-210">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="a781f-211">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span><span class="sxs-lookup"><span data-stu-id="a781f-211">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span></span> <span data-ttu-id="a781f-212">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span><span class="sxs-lookup"><span data-stu-id="a781f-212">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="a781f-213">This prevents people from seeing a cascade of policy tips.</span><span class="sxs-lookup"><span data-stu-id="a781f-213">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="a781f-214">	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="a781f-214">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="a781f-215">OneDrive for Business サイトおよび SharePoint Online サイトのポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="a781f-215">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="a781f-216">OneDrive for Business サイトまたは SharePoint Online サイト上のドキュメントが DLP ポリシー内のルールに一致し、そのルールがポリシー ヒントを使用する場合、ポリシー ヒントは特別なアイコンをドキュメント上に表示します。</span><span class="sxs-lookup"><span data-stu-id="a781f-216">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="a781f-217">ルールがファイルに関する通知を送信する場合、警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-217">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="a781f-218">ルールがドキュメントへのアクセスをブロックする場合、ブロックされたアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-218">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
   ![OneDrive アカウントのドキュメントのポリシー ヒント アイコン](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="a781f-220">ドキュメントに対してアクションを実行するには、 \> **Information** ![ ページの右上隅にある [情報情報の選択] ウィンドウのアイコンを選択し ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) て、[詳細] ウィンドウの [ \> **ポリシーヒント] ヒント**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a781f-220">To take action on a document, you can select an item \> choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="a781f-221">ポリシー ヒントにはコンテンツに関する問題が一覧表示され、ポリシー ヒントにオプションが構成されている場合には、[**解決**] を検索してから、ポリシー ヒントの [**上書き**] または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-221">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![ポリシー ヒントが表示されている情報ウィンドウ](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![上書きするオプションを使用するポリシーのヒント](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="a781f-224">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips.</span><span class="sxs-lookup"><span data-stu-id="a781f-224">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips.</span></span> <span data-ttu-id="a781f-225">There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span><span class="sxs-lookup"><span data-stu-id="a781f-225">There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="a781f-226">サイト上のポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="a781f-226">Default text for policy tips on sites</span></span>

<span data-ttu-id="a781f-227">By default, policy tips display text similar to the following for an item on a site.</span><span class="sxs-lookup"><span data-stu-id="a781f-227">By default, policy tips display text similar to the following for an item on a site.</span></span> <span data-ttu-id="a781f-228">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span><span class="sxs-lookup"><span data-stu-id="a781f-228">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="a781f-229">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="a781f-229">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="a781f-230">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="a781f-230">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a781f-231">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="a781f-231">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="a781f-232">このアイテムは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-232">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="a781f-233">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="a781f-233">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="a781f-234">This item conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-234">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-235">If you don't resolve this conflict, access to this file might be blocked.</span><span class="sxs-lookup"><span data-stu-id="a781f-235">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="a781f-236">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="a781f-236">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="a781f-237">This item conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-237">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-238">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span><span class="sxs-lookup"><span data-stu-id="a781f-238">Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="a781f-239">サイトのポリシー ヒントのユーザー設定テキスト</span><span class="sxs-lookup"><span data-stu-id="a781f-239">Custom text for policy tips on sites</span></span>

<span data-ttu-id="a781f-240">You can customize the text for policy tips separately from the email notification.</span><span class="sxs-lookup"><span data-stu-id="a781f-240">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="a781f-241">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span><span class="sxs-lookup"><span data-stu-id="a781f-241">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="a781f-242">Instead, custom text for policy tips is plain text only with a 256-character limit.</span><span class="sxs-lookup"><span data-stu-id="a781f-242">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="a781f-243">Outlook on the web および Outlook 2013 以降におけるポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="a781f-243">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="a781f-244">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span><span class="sxs-lookup"><span data-stu-id="a781f-244">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span></span> <span data-ttu-id="a781f-245">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span><span class="sxs-lookup"><span data-stu-id="a781f-245">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![作成中のメッセージの上部に表示されるポリシー ヒント](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="a781f-247">ポリシー ヒントは、次のように、機密情報がメッセージの本文、件名行、またはメッセージの添付ファイルに含まれる場合でも機能します。</span><span class="sxs-lookup"><span data-stu-id="a781f-247">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![添付ファイルが DLP ポリシーと競合していることを示すポリシー ヒント](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="a781f-249">ポリシー ヒントが上書きできるように構成されている場合は、**[詳細の表示]**、**[上書き]** を選択し、業務上の妥当性を入力するか、誤検知を報告し、**[上書き]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a781f-249">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![展開されて上書きオプションを示す、メッセージ内のポリシー ヒント](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![ポリシー ヒントを上書きできるポリシー ヒント ダイアログ](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="a781f-252">メールに機密情報を追加すると、機密情報を追加してからポリシー ヒントが表示されるまでに遅延が生じる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a781f-252">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="a781f-253">Outlook 2013 以降では、一部の条件に対するポリシー ヒントのみが表示</span><span class="sxs-lookup"><span data-stu-id="a781f-253">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="a781f-254">現在、Outlook 2013 以降では、次の条件に対するポリシー ヒントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-254">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="a781f-255">コンテンツが含まれている</span><span class="sxs-lookup"><span data-stu-id="a781f-255">Content contains</span></span>
- <span data-ttu-id="a781f-256">コンテンツが共有されている</span><span class="sxs-lookup"><span data-stu-id="a781f-256">Content is shared</span></span>

<span data-ttu-id="a781f-257">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span><span class="sxs-lookup"><span data-stu-id="a781f-257">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="a781f-258">But showing policy tips to users is not yet supported.</span><span class="sxs-lookup"><span data-stu-id="a781f-258">But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a><span data-ttu-id="a781f-259">Exchange 管理センターおよびセキュリティ/コンプライアンスセンターのポリシーヒント &amp;</span><span class="sxs-lookup"><span data-stu-id="a781f-259">Policy tips in the Exchange admin center vs. the Security &amp; Compliance Center</span></span>

<span data-ttu-id="a781f-260">ポリシーヒントは、Exchange 管理センターで作成された DLP ポリシーとメールフロールール、またはセキュリティ/コンプライアンスセンターで作成された DLP ポリシーによって機能しますが、両方を使用することはでき &amp; ません。</span><span class="sxs-lookup"><span data-stu-id="a781f-260">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="a781f-261">これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。</span><span class="sxs-lookup"><span data-stu-id="a781f-261">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="a781f-262">Exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ/コンプライアンスセンターで設定したポリシーヒントは、 &amp; outlook on the web および outlook 2013 以降のユーザーには表示されません。そのためには、exchange 管理センターのヒントをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a781f-262">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="a781f-263">これにより、現在の Exchange メールフロールール (トランスポートルールとも呼ばれます) は、セキュリティコンプライアンスセンターへの切り替えを選択するまで引き続き機能し &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="a781f-263">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="a781f-264">ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ &amp; コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a781f-264">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange admin center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="a781f-265">メールのポリシー ヒントの既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="a781f-265">Default text for policy tips in email</span></span>

<span data-ttu-id="a781f-266">既定では、ポリシー ヒントは、次のようなテキストでメールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-266">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="a781f-267">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="a781f-267">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="a781f-268">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="a781f-268">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a781f-269">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="a781f-269">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="a781f-270">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-270">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="a781f-271">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="a781f-271">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="a781f-272">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-272">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="a781f-273">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="a781f-273">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="a781f-274">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="a781f-274">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="a781f-275">Excel、PowerPoint、Word のポリシーヒント</span><span class="sxs-lookup"><span data-stu-id="a781f-275">Policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="a781f-276">ユーザーがデスクトップバージョンの Excel、PowerPoint、および Word の機密コンテンツを操作する場合、ポリシーヒントは、コンテンツが DLP ポリシーと競合することをリアルタイムで通知できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-276">When people work with sensitive content in the desktop versions of Excel, PowerPoint, and Word, policy tips can notify them in real time that the content conflicts with a DLP policy.</span></span> <span data-ttu-id="a781f-277">そのためには以下のことが必要となります。</span><span class="sxs-lookup"><span data-stu-id="a781f-277">This requires that:</span></span>
  
- <span data-ttu-id="a781f-278">Office ドキュメントが OneDrive for Business サイトまたは SharePoint Online サイトに保存されていること。</span><span class="sxs-lookup"><span data-stu-id="a781f-278">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="a781f-279">サイトが、ポリシー ヒントを使用するように構成された DLP ポリシーに含まれていること。</span><span class="sxs-lookup"><span data-stu-id="a781f-279">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="a781f-280">Office デスクトッププログラムは、自動的に Office 365 から DLP ポリシーを同期し、ドキュメントをスキャンして DLP ポリシーと競合しないことを確認し、リアルタイムでポリシーヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="a781f-280">Office desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="a781f-281">DLP ポリシーにおけるポリシー ヒントの構成法によっては、ユーザーがポリシー ヒントを単に無視すること、業務上の理由を提供してまたは提供せずにポリシーを上書きすること、誤検知を報告することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-281">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="a781f-282">ポリシー ヒントは、メッセージ バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-282">Policy tips appear on the Message Bar.</span></span>
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="a781f-284">ポリシー ヒントは、(**[ファイル]** タブ上の) Backstage ビューにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a781f-284">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Excel 2016 の Backstage にポリシー ヒントが表示される](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="a781f-286">DLP ポリシーのポリシー ヒントにこれらのオプションが設定されている場合、[**解決**] を選択した後、ポリシー ヒントの [**上書き**]、または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-286">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 の Backstage のポリシー ヒントに関するオプション](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="a781f-288">これらの各 Office デスクトッププログラムでは、ユーザーがポリシーヒントをオフにすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a781f-288">In each of these Office desktop programs, people can choose to turn off policy tips.</span></span> <span data-ttu-id="a781f-289">無効にすると、通知を単に行うポリシー ヒントはメッセージ バーにも Backstage ビュー ([**ファイル**] タブ) にも表示されません。</span><span class="sxs-lookup"><span data-stu-id="a781f-289">If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab).</span></span> <span data-ttu-id="a781f-290">ただし、ブロックおよび上書きに関するポリシー ヒントは依然表示され、電子メール通知も引き続き受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a781f-290">However, policy tips about blocking and overriding will still appear, and they will still receive the email notification.</span></span> <span data-ttu-id="a781f-291">さらに、ポリシー ヒントを無効にしても、適用されている DLP ポリシーがドキュメントに対して無効になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a781f-291">In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="a781f-292">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="a781f-292">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="a781f-293">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document.</span><span class="sxs-lookup"><span data-stu-id="a781f-293">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document.</span></span> <span data-ttu-id="a781f-294">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span><span class="sxs-lookup"><span data-stu-id="a781f-294">The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="a781f-295">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="a781f-295">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="a781f-296">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="a781f-296">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a781f-297">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="a781f-297">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="a781f-298">This file conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-298">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-299">Go to the **File** menu for more information.</span><span class="sxs-lookup"><span data-stu-id="a781f-299">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="a781f-300">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="a781f-300">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="a781f-301">This file conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-301">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-302">If you don't resolve this conflict, access to this file might be blocked.</span><span class="sxs-lookup"><span data-stu-id="a781f-302">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="a781f-303">Go to the **File** menu for more information.</span><span class="sxs-lookup"><span data-stu-id="a781f-303">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="a781f-304">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="a781f-304">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="a781f-305">This file conflicts with a policy in your organization.</span><span class="sxs-lookup"><span data-stu-id="a781f-305">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="a781f-306">If you don't resolve this conflict, access to this file might be blocked.</span><span class="sxs-lookup"><span data-stu-id="a781f-306">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="a781f-307">Go to the **File** menu for more information.</span><span class="sxs-lookup"><span data-stu-id="a781f-307">Go to the **File** menu for more information.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="a781f-308">Excel、PowerPoint、および Word のポリシーヒントのカスタムテキスト</span><span class="sxs-lookup"><span data-stu-id="a781f-308">Custom text for policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="a781f-309">You can customize the text for policy tips separately from the email notification.</span><span class="sxs-lookup"><span data-stu-id="a781f-309">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="a781f-310">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span><span class="sxs-lookup"><span data-stu-id="a781f-310">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="a781f-311">Instead, custom text for policy tips is plain text only with a 256-character limit.</span><span class="sxs-lookup"><span data-stu-id="a781f-311">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="a781f-312">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a781f-312">More information</span></span>

- [<span data-ttu-id="a781f-313">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="a781f-313">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="a781f-314">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="a781f-314">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="a781f-315">FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a781f-315">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="a781f-316">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="a781f-316">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="a781f-317">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="a781f-317">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
