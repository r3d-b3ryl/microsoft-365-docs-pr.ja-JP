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
description: データ損失防止 (DLP) ポリシーにポリシー ヒントを追加して、DLP ポリシーと競合するコンテンツを操作しているユーザーに通知する方法について学習します。
ms.openlocfilehash: f4a4700f4250289ee3614320499bc7fbaa16d582
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007539"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="2a292-103">メール通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="2a292-103">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="2a292-p101">データ損失防止 (DLP) ポリシーを使用して、Office 365 全体の機密情報の識別、監視、保護を行うことができます。このような機密情報を扱う組織内のユーザーを DLP ポリシーに準拠させつつ、不必要にブロックしてユーザーの作業が完了できないような事態は避けたいでしょう。このような場合に、メール通知とポリシー ヒントが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p101">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365. You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done. This is where email notifications and policy tips can help.</span></span>
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="2a292-108">ポリシー ヒントは、誰かがコンテンツを使用していて、それが DLP ポリシーと競合している場合に表示される通知または警告です。たとえば、個人情報 (PII) が含まれ、外部ユーザーと共有されている OneDrive for Business サイト上の Excel ブックなどのコンテンツがこれに該当します。</span><span class="sxs-lookup"><span data-stu-id="2a292-108">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="2a292-p102">メール通知とポリシー ヒントを使用して、組織のポリシーに関する認識を高め、ユーザーの教育に役立てることができます。また、業務上の正当な理由がある場合や、ポリシーが誤検知した場合にブロックされないように、ユーザーにポリシーを上書きするオプションを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p102">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies. You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="2a292-111">コンプライアンス センターで、DLP ポリシーを作成するときに、次のユーザー通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-111">In the Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="2a292-112">選択したユーザーに、問題を説明するメール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="2a292-112">Send an email notification to the people you choose that describes the issue.</span></span>
> [!NOTE]
> <span data-ttu-id="2a292-113">通知メールは保護されていない状態で送信されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-113">Notification emails are sent unprotected.</span></span>
    
- <span data-ttu-id="2a292-114">DLP ポリシーと競合しているコンテンツのポリシー ヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a292-114">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="2a292-115">Outlook on the web および Outlook 2013 以降のメールの場合は、メッセージの作成中、受信者の上のメッセージの上部にポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-115">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="2a292-116">OneDrive for Business アカウントまたは SharePoint Online サイト内のドキュメントの場合、ポリシー ヒントはアイテムに表示される警告アイコンで示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-116">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="2a292-117">詳細情報を表示するには、アイテムを選択し、ページの右上隅にある [情報] ウィンドウ アイコンを選択して詳細ウィンドウ ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) を開きます。</span><span class="sxs-lookup"><span data-stu-id="2a292-117">To view more information, you can select an item and then choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="2a292-118">DLP ポリシーに含まれる OneDrive for Business サイトまたは SharePoint Online サイトに保存されている Excel、PowerPoint、および Word のドキュメントの場合、ポリシー ヒントはメッセージ バーと Backstage ビュー **(ファイル** メニュー \> **情報**) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-118">For Excel, PowerPoint, and Word documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="2a292-119">ユーザー通知を DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="2a292-119">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="2a292-120">DLP ポリシーを作成すると、ユーザー通知を **有効にできます**。</span><span class="sxs-lookup"><span data-stu-id="2a292-120">When you create a DLP policy, you can enable **User notifications**.</span></span> <span data-ttu-id="2a292-121">ユーザー通知を有効にすると、Microsoft 365 は電子メール通知とポリシー ヒントの両方を送信します。</span><span class="sxs-lookup"><span data-stu-id="2a292-121">When user notifications are enabled, Microsoft 365 sends out both email notifications and policy tips.</span></span> <span data-ttu-id="2a292-122">通知メールの送信先、電子メール テキスト、ポリシー ヒント テキストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2a292-122">You can customize who notification emails are sent to, the email text and the policy tip text.</span></span>
  
1. <span data-ttu-id="2a292-123">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a292-123">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="2a292-124">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2a292-124">Sign in using your work or school account.</span></span> <span data-ttu-id="2a292-125">これで、セキュリティ コンプライアンス センターに &amp; 入っています。</span><span class="sxs-lookup"><span data-stu-id="2a292-125">You're now in the Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="2a292-126">セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[データ損失防止]** \> **[ポリシー]** \> **[+ ポリシーの作成]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a292-126">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![[ポリシーの作成] ボタン](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="2a292-128">必要な種類の機密情報を保護する DLP ポリシー テンプレートを選び、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a292-128">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="2a292-129">空のテンプレートから始めるには、**[カスタム]** \> **[カスタム ポリシー]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-129">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="2a292-130">ポリシーの名前を設定し、**[次へ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-130">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="2a292-131">DLP ポリシーで保護する場所を選ぶには、次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="2a292-131">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
   - <span data-ttu-id="2a292-132">**[Office 365 のすべての場所]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-132">Choose **All locations in Office 365** \> **Next**.</span></span>
    
   - <span data-ttu-id="2a292-133">**[自分で特定の場所を選択する]** \> **[次へ]** と選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-133">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
   <span data-ttu-id="2a292-134">すべての Exchange メールやすべての OneDrive アカウントなど、特定の場所全体を含めたり除外したりするには、その場所の **[状態]** をオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="2a292-134">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
   <span data-ttu-id="2a292-135">特定の SharePoint サイトまたは OneDrive アカウントだけを含めるには、**[状態]** をオンに切り替えた後、**[含める]** の下のリンクをクリックして、特定のサイトまたはアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-135">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="2a292-136">**[詳細設定を使う]** \> **[次へ]** の順に選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-136">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="2a292-137">**[+ 新しいルール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="2a292-137">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="2a292-138">ルール エディターで、**[ユーザー通知]** の状態をオンにします。</span><span class="sxs-lookup"><span data-stu-id="2a292-138">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![ルール エディターのユーザー通知セクション](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> <span data-ttu-id="2a292-140">DLP ポリシーは、新しいドキュメントか既存のドキュメントかに関あれ、ポリシーに一致するすべてのドキュメントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-140">DLP policies apply to all documents that match the policy, whether those documents are new or existing.</span></span> <span data-ttu-id="2a292-141">ただし、電子メール通知は、新しいコンテンツが既存の DLP ポリシーと一致する場合にのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-141">However, an email notification is only generated when new content matches an existing DLP policy.</span></span> <span data-ttu-id="2a292-142">既存のコンテンツは保護されますが、電子メールによるユーザー通知は生成されません。</span><span class="sxs-lookup"><span data-stu-id="2a292-142">Existing content is protected, but will not generate a user notification via email.</span></span>
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="2a292-143">メール通知を設定するためのオプション</span><span class="sxs-lookup"><span data-stu-id="2a292-143">Options for configuring email notifications</span></span>

<span data-ttu-id="2a292-144">DLP ポリシーのそれぞれのルールで、次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="2a292-144">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="2a292-p107">選択したユーザーに通知を送信します。これらのユーザーとしては、コンテンツ所有者、コンテンツの最終変更者、コンテンツが格納されているサイトの所有者、または特定のユーザーなどが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p107">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="2a292-p108">HTML またはトークンを使用して、通知に含まれるテキストをカスタマイズできます。詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a292-p108">Customize the text that's included in the notification by using HTML or tokens. See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="2a292-149">電子メール通知は、グループや配布リストではなく、個々の受信者にのみ送信できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-149">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="2a292-150">電子メール通知をトリガーするのは新しいコンテンツだけです。</span><span class="sxs-lookup"><span data-stu-id="2a292-150">Only new content will trigger an email notification.</span></span> <span data-ttu-id="2a292-151">既存のコンテンツを編集すると、ポリシー ヒントがトリガーされますが、電子メール通知はトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="2a292-151">Editing existing content will trigger policy tips, but not an email notification.</span></span> 
  
![メール通知オプション](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="2a292-153">既定のメール通知</span><span class="sxs-lookup"><span data-stu-id="2a292-153">Default email notification</span></span>

<span data-ttu-id="2a292-p110">通知には、実行されるアクションから始まる件名行があります。たとえば、メールの場合は、“通知”、“メッセージがブロックされました” など、ドキュメントの場合は、“アクセスがブロックされました” などと表示されます。ドキュメントに関する通知の場合、通知メッセージの本文には、ドキュメントが保存されているサイトに移動し、ドキュメントのポリシー ヒントを表示するリンクが含まれています。ここで問題を解決できます (ポリシー ヒントについては、以下のセクションを参照)。メールに関する通知の場合、通知には DLP ポリシーと一致するメッセージが添付ファイルとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p110">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents. If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips). If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![通知メッセージ](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="2a292-p111">既定では、通知には、サイト上の項目に対して以下のようなテキストが表示されます。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p111">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="2a292-160">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="2a292-160">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="2a292-161">**SharePoint または OneDrive for Business のドキュメントの既定の通知内容**</span><span class="sxs-lookup"><span data-stu-id="2a292-161">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="2a292-162">**Outlook メッセージの既定の通知内容**</span><span class="sxs-lookup"><span data-stu-id="2a292-162">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a292-163">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="2a292-163">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="2a292-164">このアイテムは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="2a292-164">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="2a292-165">あなたのメール メッセージは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="2a292-165">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="2a292-166">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="2a292-166">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="2a292-p112">このアイテムは組織のポリシーと競合しています。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p112">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="2a292-p113">あなたのメール メッセージは、組織のポリシーと競合しています。メッセージは、すべての受信者には配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a292-p113">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="2a292-171">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="2a292-171">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="2a292-p114">このアイテムは組織内のポリシーと競合します。アイテムの所有者、最後に更新した人、プライマリ サイト コレクションの管理者を除くすべてのユーザーが、このアイテムへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p114">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="2a292-p115">あなたのメール メッセージは、組織のポリシーと競合しています。メッセージは、すべての受信者には配信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="2a292-p115">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="2a292-176">ユーザー設定のメール通知</span><span class="sxs-lookup"><span data-stu-id="2a292-176">Custom email notification</span></span>

<span data-ttu-id="2a292-p116">エンド ユーザーまたは管理者に既定のメール通知を送信する代わりに、カスタムのメール通知を作成することができます。ユーザー設定のメール通知は、HTML に対応しており、5,000 文字の制限があります。HTML を使用すると、通知に画像、書式、その他のブランド設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p116">You can create a custom email notification instead of sending the default email notification to your end users or admins. The custom email notification supports HTML and has a 5,000-character limit. You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="2a292-p117">また、次のトークンを使用して、メール通知をカスタマイズすることもできます。これらのトークンは、送信される通知の固有の情報によって置き換えられる変数です。</span><span class="sxs-lookup"><span data-stu-id="2a292-p117">You can also use the following tokens to help customize the email notification. These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="2a292-182">**トークン**</span><span class="sxs-lookup"><span data-stu-id="2a292-182">**Token**</span></span>|<span data-ttu-id="2a292-183">**説明**</span><span class="sxs-lookup"><span data-stu-id="2a292-183">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a292-184">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="2a292-184">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="2a292-185">アクションがコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-185">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="2a292-186">%%ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="2a292-186">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="2a292-187">SharePoint Online サイトまたは OneDrive for Business サイトのドキュメントの URL。</span><span class="sxs-lookup"><span data-stu-id="2a292-187">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="2a292-188">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="2a292-188">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="2a292-p118">コンテンツと一致した条件。コンテンツで想定される問題をユーザーに通知する場合にこのトークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a292-p118">The conditions that were matched by the content. Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![トークンがどこに表示されているかを示す通知メッセージ](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="2a292-192">ポリシー ヒントを構成するためのオプション</span><span class="sxs-lookup"><span data-stu-id="2a292-192">Options for configuring policy tips</span></span>

<span data-ttu-id="2a292-193">DLP ポリシー内の各ルールに関して、次の事柄を行うポリシー ヒントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-193">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="2a292-p119">コンテンツが DLP ポリシーと競合していることをユーザーに通知して、競合を解決するアクションを実行できるようにします。既定のテキスト (下記の表を参照) を使用するか、または組織の特定のポリシーに関するユーザー設定のテキストを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p119">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict. You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="2a292-p120">ユーザーによる DLP ポリシーの上書きを許可します。必要に応じて、次のことも行えます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p120">Allow the person to override the DLP policy. Optionally, you can:</span></span>
    
  - <span data-ttu-id="2a292-p121">ポリシーを無効にするための業務上の正当な理由の入力をユーザーに求めることができます。この情報はログに記録され、セキュリティ/コンプライアンス センターの **[レポート]** セクションの DLP レポートで確認できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p121">Require the person to enter a business justification for overriding the policy. This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="2a292-p122">ユーザーが誤検知を報告し、DLP ポリシーを上書きできるようにします。この情報はレポート用にも記録されるので、誤検知を使用してルールを微調整できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p122">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![ポリシー ヒント オプション](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="2a292-203">たとえば、個人を特定できる情報 (PII) を検出する DLP ポリシーを OneDrive for Business サイトに適用する場合、このポリシーに次の 3 つのルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2a292-203">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="2a292-p123">最初のルール:5 個以下の対象機密情報インスタンスがドキュメントで検出され、ドキュメントが組織内のユーザーと共有されている場合、[**通知を送信**] アクションによってポリシー ヒントが表示されます。ポリシー ヒントについては、上書きオプションは必要ありません。このルールは単にユーザーに通知を行うだけで、アクセスをブロックするわけではないからです。</span><span class="sxs-lookup"><span data-stu-id="2a292-p123">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="2a292-p124">2 番目のルール: 5 個を超える対象機密情報インスタンスがドキュメントで検出され、組織内のユーザーとドキュメントを共有する場合、**[コンテンツへのアクセスの禁止]** アクションによってファイルのアクセス許可が制限され、**[通知の送信]** アクションでは業務上の理由を提供することによってこのルールのアクションの上書きをユーザーに許可します。場合によっては、組織のビジネスにおいて内部ユーザーが PII データを共有する必要が生じ、DLP ポリシーによってその作業をブロックしたくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p124">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification. Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="2a292-p125">3 番目のルール:5 個を超える対象機密情報インスタンスがドキュメントで検出され、組織外のユーザーとドキュメントを共有する場合、[**コンテンツへのアクセスの禁止**] アクションによってファイルのアクセス許可が制限され、[**通知の送信**] アクションではこのルールのアクションの上書きをユーザーに許可しません。情報が外部共有されているためです。いかなる状況においても、組織内のユーザーが組織外で PII データを共有することを許可すべきではありません。</span><span class="sxs-lookup"><span data-stu-id="2a292-p125">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="2a292-210">ルールを上書きするポリシー ヒントを使用する際に把握しておくべきいくつかの点を以下に記します。</span><span class="sxs-lookup"><span data-stu-id="2a292-210">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="2a292-211">上書きオプションはルールごとのオプションで、対象ルール内のすべてのアクションを上書きします (ただし、上書きできない通知の送信は除きます)。</span><span class="sxs-lookup"><span data-stu-id="2a292-211">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="2a292-p126">コンテンツが 1 つの DLP ポリシー内の複数のルールに一致する可能性がありますが、その場合には最も制限的で優先順位の高いルールのポリシー ヒントのみが表示されます。たとえば、単に通知を送信するルールのポリシー ヒントよりも、コンテンツへのアクセスを禁止するルールのポリシー ヒントの方が優先して表示されます。これにより、ポリシー ヒントがカスケード表示されるのを防止します。</span><span class="sxs-lookup"><span data-stu-id="2a292-p126">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="2a292-215">	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="2a292-215">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="2a292-216">OneDrive for Business サイトおよび SharePoint Online サイトのポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="2a292-216">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="2a292-217">OneDrive for Business サイトまたは SharePoint Online サイト上のドキュメントが DLP ポリシー内のルールに一致し、そのルールがポリシー ヒントを使用する場合、ポリシー ヒントは特別なアイコンをドキュメント上に表示します。</span><span class="sxs-lookup"><span data-stu-id="2a292-217">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="2a292-218">ルールがファイルに関する通知を送信する場合、警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-218">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="2a292-219">ルールがドキュメントへのアクセスをブロックする場合、ブロックされたアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-219">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
   ![OneDrive アカウントのドキュメントのポリシー ヒント アイコン](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="2a292-221">ドキュメントに対してアクションを実行するには、ページの右上隅にある [情報] ウィンドウ アイコンを選択して、詳細ウィンドウの [ポリシー ヒントの表示] を \>  ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **開きます**。</span><span class="sxs-lookup"><span data-stu-id="2a292-221">To take action on a document, you can select an item \> choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="2a292-222">ポリシー ヒントにはコンテンツに関する問題が一覧表示され、ポリシー ヒントにオプションが構成されている場合には、[**解決**] を検索してから、ポリシー ヒントの [**上書き**] または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-222">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![ポリシー ヒントが表示されている情報ウィンドウ](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![上書きするオプションを使用するポリシーのヒント](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="2a292-p127">DLP ポリシーがサイトと同期され、コンテンツが定期的かつ非同期的に評価されます。それで、DLP ポリシーを作成してからポリシー ヒントが表示されるまで少しの遅延があります。ポリシーを解決または上書きしてから、サイトのドキュメントのアイコンが消えるまで同様の遅延が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p127">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="2a292-227">サイト上のポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="2a292-227">Default text for policy tips on sites</span></span>

<span data-ttu-id="2a292-p128">既定では、ポリシー ヒントは、サイト上の項目に対して以下のようなテキストを表示します。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p128">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="2a292-230">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="2a292-230">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="2a292-231">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="2a292-231">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a292-232">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="2a292-232">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="2a292-233">このアイテムは、組織のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="2a292-233">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="2a292-234">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="2a292-234">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="2a292-p129">このアイテムは組織のポリシーと競合しています。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p129">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="2a292-237">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="2a292-237">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="2a292-p130">このアイテムは組織内のポリシーと競合します。アイテムの所有者、最後に更新した人、プライマリ サイト コレクションの管理者を除くすべてのユーザーが、このアイテムへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p130">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="2a292-240">サイトのポリシー ヒントのユーザー設定テキスト</span><span class="sxs-lookup"><span data-stu-id="2a292-240">Custom text for policy tips on sites</span></span>

<span data-ttu-id="2a292-p131">メール通知とは別に、ポリシー ヒントのテキストをカスタマイズすることができます。メール通知のユーザー設定テキストとは異なり (上のセクションを参照)、ポリシー ヒントのユーザー設定テキストでは HTML もトークンも使用できません。代わりに、ポリシー ヒントのユーザー設定テキストは、プレーン テキストで、256 文字の制限があります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p131">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="2a292-244">Outlook on the web および Outlook 2013 以降におけるポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="2a292-244">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="2a292-p132">Outlook on the web および Outlook 2013 以降で新しいメールを作成するとき、DLP ポリシーのルールに一致するコンテンツを追加し、そのルールがポリシー ヒントを使用する場合、ポリシー ヒントが表示されます。ポリシー ヒントは、メッセージの作成中、受信者の上のメッセージの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-p132">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips. The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![作成中のメッセージの上部に表示されるポリシー ヒント](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="2a292-248">ポリシー ヒントは、次のように、機密情報がメッセージの本文、件名行、またはメッセージの添付ファイルに含まれる場合でも機能します。</span><span class="sxs-lookup"><span data-stu-id="2a292-248">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![添付ファイルが DLP ポリシーと競合していることを示すポリシー ヒント](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="2a292-250">ポリシー ヒントが上書きできるように構成されている場合は、**[詳細の表示]**、**[上書き]** を選択し、業務上の妥当性を入力するか、誤検知を報告し、**[上書き]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a292-250">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![展開されて上書きオプションを示す、メッセージ内のポリシー ヒント](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![ポリシー ヒントを上書きできるポリシー ヒント ダイアログ](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="2a292-253">メールに機密情報を追加すると、機密情報を追加してからポリシー ヒントが表示されるまでに遅延が生じる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2a292-253">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="2a292-254">Outlook 2013 以降では、一部の条件に対するポリシー ヒントのみが表示</span><span class="sxs-lookup"><span data-stu-id="2a292-254">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="2a292-255">現在、Outlook 2013 以降では、次の条件に対するポリシー ヒントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-255">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="2a292-256">コンテンツが含まれている</span><span class="sxs-lookup"><span data-stu-id="2a292-256">Content contains</span></span>
- <span data-ttu-id="2a292-257">コンテンツが共有されている</span><span class="sxs-lookup"><span data-stu-id="2a292-257">Content is shared</span></span>

<span data-ttu-id="2a292-258">例外は条件と見なされ、これらの条件はすべて Outlook で動作し、コンテンツと一致し、コンテンツに保護アクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="2a292-258">Note that Exceptions are considered conditions and all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="2a292-259">ただし、ユーザーにポリシー ヒントを表示する方法はまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a292-259">But showing policy tips to users is not yet supported.</span></span> 
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a><span data-ttu-id="2a292-260">Exchange 管理センターとセキュリティ コンプライアンス センターのポリシー &amp; ヒント</span><span class="sxs-lookup"><span data-stu-id="2a292-260">Policy tips in the Exchange admin center vs. the Security &amp; Compliance Center</span></span>

<span data-ttu-id="2a292-261">ポリシー ヒントは、Exchange 管理センターで作成された DLP ポリシーとメール フロー ルール、またはセキュリティ コンプライアンス センターで作成された DLP ポリシーで動作できますが、両方は使用 &amp; できません。</span><span class="sxs-lookup"><span data-stu-id="2a292-261">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="2a292-262">これは、これらのポリシーは異なる場所に保存されますが、ポリシー ヒントは 1 つの場所からのみ描画できるためです。</span><span class="sxs-lookup"><span data-stu-id="2a292-262">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="2a292-263">Exchange 管理センターでポリシー ヒントを構成した場合、Exchange 管理センターでヒントをオフにするまで、セキュリティ コンプライアンス センターで構成したポリシー ヒントは、Outlook on the web および Outlook 2013 以降のユーザーには表示されません。 &amp;</span><span class="sxs-lookup"><span data-stu-id="2a292-263">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="2a292-264">これにより、セキュリティ コンプライアンス センターに切り替えるまで、現在の Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) が引き続き &amp; 機能します。</span><span class="sxs-lookup"><span data-stu-id="2a292-264">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="2a292-265">ポリシー ヒントは 1 つの場所からしか描画されませんが、セキュリティ コンプライアンス センターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に &amp; 送信されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-265">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange admin center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="2a292-266">メールのポリシー ヒントの既定のテキスト</span><span class="sxs-lookup"><span data-stu-id="2a292-266">Default text for policy tips in email</span></span>

<span data-ttu-id="2a292-267">既定では、ポリシー ヒントは、次のようなテキストでメールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-267">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="2a292-268">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="2a292-268">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="2a292-269">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="2a292-269">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a292-270">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="2a292-270">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="2a292-271">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="2a292-271">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="2a292-272">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="2a292-272">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="2a292-273">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="2a292-273">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="2a292-274">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="2a292-274">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="2a292-275">メールは組織内のポリシーと競合しています。</span><span class="sxs-lookup"><span data-stu-id="2a292-275">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="2a292-276">Excel、PowerPoint、Word のポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="2a292-276">Policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="2a292-277">ユーザーがデスクトップ バージョンの Excel、PowerPoint、および Word で機密性の高いコンテンツを操作する場合、ポリシー ヒントは、コンテンツが DLP ポリシーと競合するリアルタイムで通知できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-277">When people work with sensitive content in the desktop versions of Excel, PowerPoint, and Word, policy tips can notify them in real time that the content conflicts with a DLP policy.</span></span> <span data-ttu-id="2a292-278">そのためには以下のことが必要となります。</span><span class="sxs-lookup"><span data-stu-id="2a292-278">This requires that:</span></span>
  
- <span data-ttu-id="2a292-279">Office ドキュメントが OneDrive for Business サイトまたは SharePoint Online サイトに保存されていること。</span><span class="sxs-lookup"><span data-stu-id="2a292-279">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="2a292-280">サイトが、ポリシー ヒントを使用するように構成された DLP ポリシーに含まれていること。</span><span class="sxs-lookup"><span data-stu-id="2a292-280">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="2a292-281">Office プログラムは、Office 365 から DLP ポリシーを自動的に直接同期し、ドキュメントをスキャンして、DLP ポリシーと競合し、リアルタイムでポリシー ヒントを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a292-281">Office desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>

> [!NOTE]
> <span data-ttu-id="2a292-282">Officeデスクトップ アプリはドキュメント自体をスキャンして、DLP ポリシー ヒントを表示する必要があるかどうかを判断します。SharePoint Online サイトまたは OneDrive for Business サイトがファイルに表示する必要が既に決定されているポリシー ヒントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2a292-282">Office desktop apps scan documents themselves to determine if DLP policy tips should be shown; they do not show policy tips that SharePoint Online sites or OneDrive for Business sites have already determined should be shown on a file.</span></span> <span data-ttu-id="2a292-283">そのため、SharePoint Online サイトまたは OneDrive for Business サイトに表示されるデスクトップ アプリに DLP ポリシー ヒントが常に表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a292-283">As a result, you may not always see a DLP policy tip in the desktop apps that you see in the SharePoint Online sites or OneDrive for Business sites.</span></span> <span data-ttu-id="2a292-284">これに対し、web 上Officeアプリケーションは、SharePoint Online サイトまたは OneDrive for Business サイトが既に決定している DLP ポリシー ヒントのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a292-284">In contrast, the Office applications on the web only show DLP policy tips that SharePoint Online sites or OneDrive for Business sites have already determined should be shown.</span></span>
  
<span data-ttu-id="2a292-285">DLP ポリシーにおけるポリシー ヒントの構成法によっては、ユーザーがポリシー ヒントを単に無視すること、業務上の理由を提供してまたは提供せずにポリシーを上書きすること、誤検知を報告することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-285">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="2a292-286">ポリシー ヒントは、メッセージ バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-286">Policy tips appear on the Message Bar.</span></span>
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="2a292-288">ポリシー ヒントは、(**[ファイル]** タブ上の) Backstage ビューにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a292-288">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Excel 2016 の Backstage にポリシー ヒントが表示される](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="2a292-290">DLP ポリシーのポリシー ヒントにこれらのオプションが設定されている場合、[**解決**] を選択した後、ポリシー ヒントの [**上書き**]、または誤検知の [**レポート**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2a292-290">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 の Backstage のポリシー ヒントに関するオプション](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="2a292-292">これらの各デスクトップ プログラムOffice、ユーザーはポリシー ヒントをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="2a292-292">In each of these Office desktop programs, people can choose to turn off policy tips.</span></span> <span data-ttu-id="2a292-293">無効にすると、通知を単に行うポリシー ヒントはメッセージ バーにも Backstage ビュー ([**ファイル**] タブ) にも表示されません。</span><span class="sxs-lookup"><span data-stu-id="2a292-293">If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab).</span></span> <span data-ttu-id="2a292-294">ただし、ブロックおよび上書きに関するポリシー ヒントは依然表示され、電子メール通知も引き続き受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2a292-294">However, policy tips about blocking and overriding will still appear, and they will still receive the email notification.</span></span> <span data-ttu-id="2a292-295">さらに、ポリシー ヒントを無効にしても、適用されている DLP ポリシーがドキュメントに対して無効になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2a292-295">In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="2a292-296">Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒントの既定テキスト</span><span class="sxs-lookup"><span data-stu-id="2a292-296">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="2a292-p139">既定では、ポリシー ヒントは、開いているドキュメントのメッセージ バーと Backstage ビューに次のようなテキストを表示します。通知テキストは、ルールごとに個別に構成されるため、表示されるテキストは、一致するルールによって異なります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p139">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="2a292-299">**構成されている DLP ポリシー ルール**</span><span class="sxs-lookup"><span data-stu-id="2a292-299">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="2a292-300">**既定のポリシー ヒント内容**</span><span class="sxs-lookup"><span data-stu-id="2a292-300">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a292-301">通知を送信するが、上書きは許可しない</span><span class="sxs-lookup"><span data-stu-id="2a292-301">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="2a292-p140">このファイルは組織内のポリシーと競合します。詳細については、**[ファイル]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a292-p140">This file conflicts with a policy in your organization. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="2a292-304">アクセスをブロックし、通知を送信し、上書きを許可する</span><span class="sxs-lookup"><span data-stu-id="2a292-304">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="2a292-p141">このファイルは組織内のポリシーと競合します。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。詳細については、**[ファイル]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a292-p141">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="2a292-308">アクセスをブロックして、通知を送信する</span><span class="sxs-lookup"><span data-stu-id="2a292-308">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="2a292-p142">このファイルは組織内のポリシーと競合します。この競合を解決しないと、このファイルへのアクセスがブロックされる可能性があります。詳細については、**[ファイル]** メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a292-p142">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="2a292-312">Excel、PowerPoint、Word のポリシー ヒントのカスタム テキスト</span><span class="sxs-lookup"><span data-stu-id="2a292-312">Custom text for policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="2a292-p143">メール通知とは別に、ポリシー ヒントのテキストをカスタマイズすることができます。メール通知のユーザー設定テキストとは異なり (上のセクションを参照)、ポリシー ヒントのユーザー設定テキストでは HTML もトークンも使用できません。代わりに、ポリシー ヒントのユーザー設定テキストは、プレーン テキストで、256 文字の制限があります。</span><span class="sxs-lookup"><span data-stu-id="2a292-p143">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="2a292-316">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2a292-316">More information</span></span>

- [<span data-ttu-id="2a292-317">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="2a292-317">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)    
- [<span data-ttu-id="2a292-318">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="2a292-318">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="2a292-319">DLP ポリシーの条件、例外、およびアクション (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2a292-319">DLP policy conditions, exceptions, and actions (preview)</span></span>](./dlp-microsoft-teams.md) 
- [<span data-ttu-id="2a292-320">FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2a292-320">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
- [<span data-ttu-id="2a292-321">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="2a292-321">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
- [<span data-ttu-id="2a292-322">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="2a292-322">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)