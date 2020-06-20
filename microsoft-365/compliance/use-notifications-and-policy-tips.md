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
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>メール通知を送信して、DLP ポリシーのポリシーのヒントを表示する

You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365. You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done. This is where email notifications and policy tips can help.
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
ポリシー ヒントは、誰かがコンテンツを使用していて、それが DLP ポリシーと競合している場合に表示される通知または警告です。たとえば、個人情報 (PII) が含まれ、外部ユーザーと共有されている OneDrive for Business サイト上の Excel ブックなどのコンテンツがこれに該当します。
  
You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies. You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.
  
セキュリティ &amp; /コンプライアンスセンターでは、DLP ポリシーを作成するときに、ユーザー通知を次のように構成できます。
  
- 選択したユーザーに、問題を説明するメール通知を送信します。
    
- DLP ポリシーと競合しているコンテンツのポリシー ヒントを表示します。
    
  - Outlook on the web および Outlook 2013 以降のメールの場合は、メッセージの作成中、受信者の上のメッセージの上部にポリシー ヒントが表示されます。
    
  - OneDrive for Business アカウントまたは SharePoint Online サイトのドキュメントの場合、ポリシーヒントには、アイテムに表示される警告アイコンが示されます。 詳細情報を表示するには、アイテムを選択して**Information**から、 ![ ページの右上隅にある [情報情報] ウィンドウのアイコンを選択し ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) て、詳細ウィンドウを開きます。 
    
  - DLP ポリシーに含まれている OneDrive for Business サイトまたは SharePoint Online サイトに格納されている Excel、PowerPoint、および Word ドキュメントでは、ポリシーヒントがメッセージバーおよび Backstage ビュー ([**ファイル**] メニュー情報) に表示され \> **Info**ます。
    
## <a name="add-user-notifications-to-a-dlp-policy"></a>ユーザー通知を DLP ポリシーに追加する

DLP ポリシーを作成するときに、**ユーザー通知**を有効にすることができます。 ユーザー通知が有効になっている場合、Microsoft 365 は電子メール通知とポリシーヒントの両方を送信します。 通知メールを送信するユーザー、電子メールテキスト、ポリシーヒントテキストをカスタマイズできます。
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 職場または学校のアカウントを使用してサインインします。 これで、セキュリティ/コンプライアンスセンターになってい &amp; ます。
    
3. セキュリティ/コンプライアンス センターの左側のナビゲーションで、**[データ損失防止]** \> **[ポリシー]** \> **[+ ポリシーの作成]** の順に移動します。
    
    ![[ポリシーの作成] ボタン](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. 必要な種類の機密情報を保護する DLP ポリシー テンプレートを選び、**[次へ]** を選択します。
    
    空のテンプレートから始めるには、**[カスタム]** \> **[カスタム ポリシー]** \> **[次へ]** の順に選びます。
    
5. ポリシーの名前を設定し、**[次へ]** を選びます。
    
6. DLP ポリシーで保護する場所を選ぶには、次のいずれかを行います。
    
   - **[Office 365 のすべての場所]** \> **[次へ]** と選びます。
    
   - **[自分で特定の場所を選択する]** \> **[次へ]** と選びます。
    
   すべての Exchange メールやすべての OneDrive アカウントなど、特定の場所全体を含めたり除外したりするには、その場所の **[状態]** をオンまたはオフに切り替えます。 
    
   特定の SharePoint サイトまたは OneDrive アカウントだけを含めるには、**[状態]** をオンに切り替えた後、**[含める]** の下のリンクをクリックして、特定のサイトまたはアカウントを選びます。 
    
7. **[詳細設定を使う]** \> **[次へ]** の順に選びます。
    
8. **[+ 新しいルール]** を選びます。
    
9. ルール エディターで、**[ユーザー通知]** の状態をオンにします。
    
    ![ルール エディターのユーザー通知セクション](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> DLP ポリシーは、それらのドキュメントが新規か既存かにかかわらず、ポリシーに一致するすべてのドキュメントに適用されます。 ただし、電子メール通知は、新しいコンテンツが既存の DLP ポリシーと一致する場合にのみ生成されます。 既存のコンテンツは保護されますが、電子メールによるユーザー通知は生成されません。
  
## <a name="options-for-configuring-email-notifications"></a>メール通知を設定するためのオプション

DLP ポリシーのそれぞれのルールで、次のことを行えます。
  
- Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.
    
- Customize the text that's included in the notification by using HTML or tokens. See the section below for more information.
    
> [!NOTE]
>  電子メール通知は、グループまたは配布リストではなく、個々の受信者にのみ送信できます。 電子メール通知をトリガーするのは新しいコンテンツだけです。 既存のコンテンツを編集すると、ポリシーヒントが表示されますが、電子メール通知はトリガーされません。 
  
![メール通知オプション](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a>既定のメール通知

Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents. If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips). If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.
  
![通知メッセージ](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.

|**構成されている DLP ポリシー ルール**|**SharePoint または OneDrive for Business のドキュメントの既定の通知内容**|**Outlook メッセージの既定の通知内容**|
|:-----|:-----|:-----|
|通知を送信するが、上書きは許可しない  <br/> |このアイテムは、組織のポリシーと競合しています。  <br/> |あなたのメール メッセージは、組織のポリシーと競合しています。  <br/> |
|アクセスをブロックし、通知を送信し、上書きを許可する  <br/> |This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.  <br/> |あなたのメール メッセージは、組織のポリシーと競合しています。 メッセージはすべての受信者に配信されませんでした。  <br/> |
|アクセスをブロックして、通知を送信する  <br/> |This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.  <br/> |Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.  <br/> |
   
### <a name="custom-email-notification"></a>ユーザー設定のメール通知

You can create a custom email notification instead of sending the default email notification to your end users or admins. The custom email notification supports HTML and has a 5,000-character limit. You can use HTML to include images, formatting, and other branding in the notification.
  
You can also use the following tokens to help customize the email notification. These tokens are variables that are replaced by specific information in the notification that's sent.

|**トークン**|**説明**|
|:-----|:-----|
|%%AppliedActions%%  <br/> |アクションがコンテンツに適用されます。  <br/> |
|%%ContentURL%%  <br/> |SharePoint Online サイトまたは OneDrive for Business サイトのドキュメントの URL。  <br/> |
|%%MatchedConditions%%  <br/> |The conditions that were matched by the content. Use this token to inform people of possible issues with the content.  <br/> |
   
![トークンがどこに表示されているかを示す通知メッセージ](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a>ポリシー ヒントを構成するためのオプション

DLP ポリシー内の各ルールに関して、次の事柄を行うポリシー ヒントを構成できます。
  
- Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict. You can use the default text (see the tables below) or enter custom text about your organization's specific policies.
    
- Allow the person to override the DLP policy. Optionally, you can:
    
  - Require the person to enter a business justification for overriding the policy. This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center. 
    
  - Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.
    
![ポリシー ヒント オプション](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
たとえば、個人を特定できる情報 (PII) を検出する DLP ポリシーを OneDrive for Business サイトに適用する場合、このポリシーに次の 3 つのルールを含めることができます。
  
1. First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access. 
    
2. Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification. Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work. 
    
3. Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization. 
    
ルールを上書きするポリシー ヒントを使用する際に把握しておくべきいくつかの点を以下に記します。
  
- 上書きオプションはルールごとのオプションで、対象ルール内のすべてのアクションを上書きします (ただし、上書きできない通知の送信は除きます)。
    
- It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.
    
- 	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>OneDrive for Business サイトおよび SharePoint Online サイトのポリシー ヒント

OneDrive for Business サイトまたは SharePoint Online サイト上のドキュメントが DLP ポリシー内のルールに一致し、そのルールがポリシー ヒントを使用する場合、ポリシー ヒントは特別なアイコンをドキュメント上に表示します。
  
1. ルールがファイルに関する通知を送信する場合、警告アイコンが表示されます。
    
2. ルールがドキュメントへのアクセスをブロックする場合、ブロックされたアイコンが表示されます。
    
   ![OneDrive アカウントのドキュメントのポリシー ヒント アイコン](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
ドキュメントに対してアクションを実行するには、 \> **Information** ![ ページの右上隅にある [情報情報の選択] ウィンドウのアイコンを選択し ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) て、[詳細] ウィンドウの [ \> **ポリシーヒント] ヒント**を開きます。
  
ポリシー ヒントにはコンテンツに関する問題が一覧表示され、ポリシー ヒントにオプションが構成されている場合には、[**解決**] を検索してから、ポリシー ヒントの [**上書き**] または誤検知の [**レポート**] を選択できます。 
  
![ポリシー ヒントが表示されている情報ウィンドウ](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![上書きするオプションを使用するポリシーのヒント](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.
  
### <a name="default-text-for-policy-tips-on-sites"></a>サイト上のポリシー ヒントの既定テキスト

By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.

|**構成されている DLP ポリシー ルール**|**既定のポリシー ヒント内容**|
|:-----|:-----|
|通知を送信するが、上書きは許可しない  <br/> |このアイテムは、組織のポリシーと競合しています。  <br/> |
|アクセスをブロックし、通知を送信し、上書きを許可する  <br/> |This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.  <br/> |
|アクセスをブロックして、通知を送信する  <br/> |This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a>サイトのポリシー ヒントのユーザー設定テキスト

You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Outlook on the web および Outlook 2013 以降におけるポリシー ヒント

When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips. The policy tip appears at the top of the message, above the recipients, while the message is being composed.
  
![作成中のメッセージの上部に表示されるポリシー ヒント](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
ポリシー ヒントは、次のように、機密情報がメッセージの本文、件名行、またはメッセージの添付ファイルに含まれる場合でも機能します。
  
![添付ファイルが DLP ポリシーと競合していることを示すポリシー ヒント](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
ポリシー ヒントが上書きできるように構成されている場合は、**[詳細の表示]**、**[上書き]** を選択し、業務上の妥当性を入力するか、誤検知を報告し、**[上書き]** を選択します。
  
![展開されて上書きオプションを示す、メッセージ内のポリシー ヒント](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![ポリシー ヒントを上書きできるポリシー ヒント ダイアログ](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
メールに機密情報を追加すると、機密情報を追加してからポリシー ヒントが表示されるまでに遅延が生じる場合があることに注意してください。

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>Outlook 2013 以降では、一部の条件に対するポリシー ヒントのみが表示

現在、Outlook 2013 以降では、次の条件に対するポリシー ヒントのみが表示されます。

- コンテンツが含まれている
- コンテンツが共有されている

Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content. But showing policy tips to users is not yet supported.
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a>Exchange 管理センターおよびセキュリティ/コンプライアンスセンターのポリシーヒント &amp;

ポリシーヒントは、Exchange 管理センターで作成された DLP ポリシーとメールフロールール、またはセキュリティ/コンプライアンスセンターで作成された DLP ポリシーによって機能しますが、両方を使用することはでき &amp; ません。 これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。
  
Exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ/コンプライアンスセンターで設定したポリシーヒントは、 &amp; outlook on the web および outlook 2013 以降のユーザーには表示されません。そのためには、exchange 管理センターのヒントをオフにします。 これにより、現在の Exchange メールフロールール (トランスポートルールとも呼ばれます) は、セキュリティコンプライアンスセンターへの切り替えを選択するまで引き続き機能し &amp; ます。
  
ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ &amp; コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。
  
### <a name="default-text-for-policy-tips-in-email"></a>メールのポリシー ヒントの既定のテキスト

既定では、ポリシー ヒントは、次のようなテキストでメールに表示されます。

|**構成されている DLP ポリシー ルール**|**既定のポリシー ヒント内容**|
|:-----|:-----|
|通知を送信するが、上書きは許可しない  <br/> |メールは組織内のポリシーと競合しています。  <br/> |
|アクセスをブロックし、通知を送信し、上書きを許可する  <br/> |メールは組織内のポリシーと競合しています。  <br/> |
|アクセスをブロックして、通知を送信する  <br/> |メールは組織内のポリシーと競合しています。  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a>Excel、PowerPoint、Word のポリシーヒント

ユーザーがデスクトップバージョンの Excel、PowerPoint、および Word の機密コンテンツを操作する場合、ポリシーヒントは、コンテンツが DLP ポリシーと競合することをリアルタイムで通知できます。 そのためには以下のことが必要となります。
  
- Office ドキュメントが OneDrive for Business サイトまたは SharePoint Online サイトに保存されていること。
    
- サイトが、ポリシー ヒントを使用するように構成された DLP ポリシーに含まれていること。
    
Office デスクトッププログラムは、自動的に Office 365 から DLP ポリシーを同期し、ドキュメントをスキャンして DLP ポリシーと競合しないことを確認し、リアルタイムでポリシーヒントを表示します。
  
DLP ポリシーにおけるポリシー ヒントの構成法によっては、ユーザーがポリシー ヒントを単に無視すること、業務上の理由を提供してまたは提供せずにポリシーを上書きすること、誤検知を報告することを選択できます。
  
ポリシー ヒントは、メッセージ バーに表示されます。
  
![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
ポリシー ヒントは、(**[ファイル]** タブ上の) Backstage ビューにも表示されます。 
  
![Excel 2016 の Backstage にポリシー ヒントが表示される](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
DLP ポリシーのポリシー ヒントにこれらのオプションが設定されている場合、[**解決**] を選択した後、ポリシー ヒントの [**上書き**]、または誤検知の [**レポート**] を選択できます。 
  
![Excel 2016 の Backstage のポリシー ヒントに関するオプション](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
これらの各 Office デスクトッププログラムでは、ユーザーがポリシーヒントをオフにすることを選択できます。 無効にすると、通知を単に行うポリシー ヒントはメッセージ バーにも Backstage ビュー ([**ファイル**] タブ) にも表示されません。 ただし、ブロックおよび上書きに関するポリシー ヒントは依然表示され、電子メール通知も引き続き受け取ります。 さらに、ポリシー ヒントを無効にしても、適用されている DLP ポリシーがドキュメントに対して無効になるわけではありません。 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Excel 2016、PowerPoint 2016、Word 2016 におけるポリシー ヒントの既定テキスト

By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.

|**構成されている DLP ポリシー ルール**|**既定のポリシー ヒント内容**|
|:-----|:-----|
|通知を送信するが、上書きは許可しない  <br/> |This file conflicts with a policy in your organization. Go to the **File** menu for more information.  <br/> |
|アクセスをブロックし、通知を送信し、上書きを許可する  <br/> |This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  <br/> |
|アクセスをブロックして、通知を送信する  <br/> |This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a>Excel、PowerPoint、および Word のポリシーヒントのカスタムテキスト

You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.
  
## <a name="more-information"></a>詳細情報

- [データ損失防止ポリシーの概要](data-loss-prevention-policies.md)
    
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
    
- [FCI または他のプロパティを含むドキュメントを保護するために DLP ポリシーを作成する](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP ポリシー テンプレートに含まれるもの](what-the-dlp-policy-templates-include.md)
    
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
