---
title: Microsoft 365 の高度な監査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の高度な監査では、組織におけるフォレンシックおよびコンプライアンスの調査に役立つ新しい監査機能を提供します。
ms.openlocfilehash: 51ec75cc8d8ae554ea9cbef3a9ea2aa18171e70a
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950996"
---
# <a name="advanced-audit-in-microsoft-365"></a><span data-ttu-id="38753-103">Microsoft 365 の高度な監査</span><span class="sxs-lookup"><span data-stu-id="38753-103">Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="38753-p101">Microsoft 365 の [統合監査機能](search-the-audit-log-in-security-and-compliance.md) を使用すると、組織は Microsoft 365 のさまざまなサービスにわたって、さまざまな種類の監査済みアクティビティを可視化できます。高度な監査は、侵害の範囲の決定に役立つ重要なイベントへのアクセスを提供し、Office 365 管理アクティビティ API への迅速なアクセスを提供することで、調査の実施に必要な監査ログの保持を高め、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。</span><span class="sxs-lookup"><span data-stu-id="38753-p101">The [unified auditing functionality](search-the-audit-log-in-security-and-compliance.md) in Microsoft 365 provides organizations with visibility into many types of audited activities across many different services in Microsoft 365. Advanced Audit helps organizations to conduct forensic and compliance investigations by increasing audit log retention required to conduct an investigation, providing access to crucial events that help determine scope of compromise, and faster access to Office 365 Management Activity API.</span></span>

> [!NOTE]
> <span data-ttu-id="38753-p102">高度な監査は、Office 365 E5 または Microsoft 365 Enterprise E5 サブスクリプションを持つ組織で利用できます。さらに、Microsoft 365 E5 コンプライアンス アドオン ライセンスや Microsoft 365 E5 eDiscovery and Audit アドオン ライセンスは、監査ログの長期保持や調査のための重要なイベントへのアクセスと同様に、高度な監査機能にユーザーごとのライセンスが必要な場合に、ユーザーに割り当てることができます。ライセンスの詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38753-p102">Advanced Audit is available for organizations with an Office 365 E5 or Microsoft 365 Enterprise E5 subscription. Additionally, a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license can be assigned to users when per-user licensing is required for Advanced Audit features as is the case for long-term retention of audit logs and access to crucial events for investigations. For more information about licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).</span></span>

<span data-ttu-id="38753-109">この記事では、高度な監査機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="38753-109">This article provides an overview of Advanced Audit capabilities.</span></span>

## <a name="long-term-retention-of-audit-logs"></a><span data-ttu-id="38753-110">監査ログの長期保持</span><span class="sxs-lookup"><span data-stu-id="38753-110">Long-term retention of audit logs</span></span>

<span data-ttu-id="38753-p103">高度な監査では、Exchange、SharePoint、Azure Active Directory のすべての監査レコードが 1 年間保持されます。これは、アクティビティが発生したサービスを示す **ワークロード** プロパティの **Exchange** 、 **SharePoint** 、または **AzureActiveDirectory** の値を含む任意の監査レコードを 1 年間保持する既定の監査ログの保持ポリシーによって実現されます。監査レコードの長期間にわたる保持は、継続的なフォレンジック調査やコンプライアンス調査に役立ちます。詳細については、「 [監査ログ保持ポリシーを管理する](audit-log-retention-policies.md#default-audit-log-retention-policy)」の「既定の監査ログ保持ポリシー」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38753-p103">Advanced Audit retains all Exchange, SharePoint, and Azure Active Directory audit records for one year. This is accomplished by a default audit log retention policy that retains any audit record that contains the value of **Exchange** , **SharePoint** , or **AzureActiveDirectory** for the **Workload** property (which indicates the service in which the activity occurred) for one year. Retaining audit records for longer periods can help with on-going forensic or compliance investigations. For more information, see the "Default audit log retention policy" section in [Manage audit log retention policies](audit-log-retention-policies.md#default-audit-log-retention-policy).</span></span>

<span data-ttu-id="38753-p104">また、監査ログを 10 年間保持する機能もリリースしています。監査ログを 10 年間保持することで、長期間にわたる調査や、規制、法律、社内の義務への対応をサポートします。</span><span class="sxs-lookup"><span data-stu-id="38753-p104">We're also releasing the capability to retain audit logs for 10 years. The 10-year retention of audit logs helps support long running investigations and respond to regulatory, legal, and internal obligations.</span></span>

> [!NOTE]
> <span data-ttu-id="38753-p105">監査ログを 10 年間保持するには、追加のアドオン ライセンスが必要です。この新しいライセンスは、2021 年初頭より利用可能になります。詳細については、この記事の「[高度な監査についてよく寄せられる質問](#faqs-for-advanced-audit)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38753-p105">Retaining audit logs for 10 years will require an additional add-on license. This new license will be available in early 2021. For more information, see the [FAQs for Advanced Audit](#faqs-for-advanced-audit) section in this article.</span></span>

### <a name="audit-log-retention-policies"></a><span data-ttu-id="38753-120">監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="38753-120">Audit log retention policies</span></span>

<span data-ttu-id="38753-p106">(前のセクションで説明した) 既定の監査ログの保持ポリシーが適用されていない他のサービスで生成されたすべての監査レコードは、90 日間保持されます。ただし、カスタマイズした監査ログの保持ポリシーを作成すれば、最大 10 年間、長期にわたって他の監査レコードを保持できます。次の 1 つ以上の基準に基づいて、監査レコードを保持するポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="38753-p106">All audit records generated in other services that aren't covered by the default audit log retention policy (described in the previous section) are retained for 90 days. But you can create customized audit log retention policies to retain other audit records for longer periods of time up to 10 years. You can create a policy to retain audit records based on one or more of the following criteria:</span></span>

- <span data-ttu-id="38753-124">監査されたアクティビティが発生する Microsoft 365 サービス。</span><span class="sxs-lookup"><span data-stu-id="38753-124">The Microsoft 365 service where the audited activities occur.</span></span>

- <span data-ttu-id="38753-125">特定の監査されたアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="38753-125">Specific audited activities.</span></span>

- <span data-ttu-id="38753-126">監査されたアクティビティを実行するユーザー。</span><span class="sxs-lookup"><span data-stu-id="38753-126">The user who performs an audited activity.</span></span>

<span data-ttu-id="38753-p107">特定のポリシーが他のポリシーよりも優先されるように、ポリシーおよび優先度のレベルに一致する監査レコードを保持する期間を指定することもできます。また、組織の一部またはすべてのユーザーに対して Exchange、SharePoint、Azure Active Directory 監査レコードを 1 年未満 (または 10 年間) で保持する必要がある場合は、カスタム監査ログの保持ポリシーが既定の監査保持ポリシーよりも優先されます。詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38753-p107">You can also specify how long to retain audit records that match the policy and a priority level so that specific policies will take priority over other policies. Also note that any custom audit log retention policy will take precedence over the default audit retention policy in case you need retain Exchange, SharePoint, or Azure Active Directory audit records for less than a year (or for 10 years) for some or all users in your organization. For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="access-to-crucial-events-for-investigations"></a><span data-ttu-id="38753-130">調査のための重要なイベントへのアクセス</span><span class="sxs-lookup"><span data-stu-id="38753-130">Access to crucial events for investigations</span></span>

<span data-ttu-id="38753-p108">高度な監査は、いつメール項目がアクセスされたか、いつメール項目が返信されたか、または転送されたか、ユーザーがいつ何を Exchange Online や SharePoint Online で検索したかなどの重要なイベントへのアクセスを提供することで、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。これらの重要なイベントは、起こりうる侵害を調査し、侵害の範囲を決定するのに役立ちます。高度な監査は、次の重要なイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="38753-p108">Advanced Audit helps organizations to conduct forensic and compliance investigations by providing access to crucial events such as when mail items were accessed, or when mail items were replied to and forwarded, and when and what a user searched for in Exchange Online and SharePoint Online. These crucial events can help you investigate possible breaches and determine the scope of compromise.  Advanced Auditing provides the following crucial events:</span></span>

- [<span data-ttu-id="38753-134">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="38753-134">MailItemsAccessed</span></span>](#mailitemsaccessed)

- [<span data-ttu-id="38753-135">Send</span><span class="sxs-lookup"><span data-stu-id="38753-135">Send</span></span>](#send)

- [<span data-ttu-id="38753-136">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="38753-136">SearchQueryInitiatedExchange</span></span>](#searchqueryinitiatedexchange)

- [<span data-ttu-id="38753-137">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="38753-137">SearchQueryInitiatedSharePoint</span></span>](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a><span data-ttu-id="38753-138">MailItemsAccessed</span><span class="sxs-lookup"><span data-stu-id="38753-138">MailItemsAccessed</span></span>

<span data-ttu-id="38753-p109">MailItemsAccessed イベントは、メールボックス監査アクションであり、メール データがメール プロトコルやメール クライアントによってアクセスされたときにトリガーされます。MailItemsAccessed アクションは、調査者がデータ違反を識別し、侵害された可能性があるメッセージの範囲を特定するのに役立ちます。攻撃者がメール メッセージにアクセスすると、MailItemsAccessed アクションは、メッセージが実際に読み取られたことを示す明示的な信号がない場合でもトリガーされます (つまり、バインドや同期などのアクセスの種類が監査レコードに記録されます)。</span><span class="sxs-lookup"><span data-stu-id="38753-p109">The MailItemsAccessed event is a mailbox auditing action and is triggered when mail data is accessed by mail protocols and mail clients. The MailItemsAccessed action can help investigators identify data breaches and determine the scope of messages that may have been compromised. If an attacker gained access to email messages, the MailItemsAccessed action will be triggered even if there is no explicit signal that messages were actually read (in other words, the type of access such as a bind or sync is recorded in the audit record).</span></span>

<span data-ttu-id="38753-142">MailItemsAccessed メールボックス アクションは、Exchange Online のメールボックスの監査ログの MessageBind を置き換え、次の改善点を提供します。</span><span class="sxs-lookup"><span data-stu-id="38753-142">The MailItemsAccessed mailbox action replaces MessageBind in mailbox auditing logging in Exchange Online and provides these improvements:</span></span>

- <span data-ttu-id="38753-p110">MessageBind は、AuditAdmin ユーザーのログインの種類に対してのみ構成でき、委任または所有者のアクションには適用されませんでした。MailItemsAccessed は、すべてのログインの種類に適用されます。</span><span class="sxs-lookup"><span data-stu-id="38753-p110">MessageBind was only configurable for AuditAdmin user logon type; it did not apply to delegate or owner actions. MailItemsAccessed applies to all logon types.</span></span>

- <span data-ttu-id="38753-p111">MessageBind は、メール クライアントによるアクセスのみを対象としています。同期アクティビティには適用されませんでした。MailItemsAccessed イベントは、バインド アクセスの種類と同期アクセスの種類の両方によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="38753-p111">MessageBind only covered access by a mail client. It didn't apply to sync activities. MailItemsAccessed events are triggered by both bind and sync access types.</span></span>

- <span data-ttu-id="38753-p112">MessageBind アクションによって、同じメール メッセージにアクセスしたときに複数の監査レコードが作成され、「ノイズ」が監査されます。一方、MailItemsAccessed イベントは、少数の監査レコードに集約されます。</span><span class="sxs-lookup"><span data-stu-id="38753-p112">MessageBind actions would trigger the creation of multiple audit records when the same email message was accessed, which resulted in auditing "noise". In contrast, MailItemsAccessed events are aggregated into fewer audit records.</span></span>

<span data-ttu-id="38753-150">MailItemsAccessed アクティビティの監査レコードの詳細については、「[高度な監査を使用して、侵害されたアカウントを調査する](mailitemsaccessed-forensics-investigations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38753-150">For information about audit records for MailItemsAccessed activities, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>

<span data-ttu-id="38753-151">MailItemsAccessed 監査レコードを検索するには、Microsoft 365 コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **Exchange メールボックス アクティビティ** ドロップダウン リストで **メールボックス アイテムへのアクセス** アクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="38753-151">To search for MailItemsAccessed audit records, you can search for the **Accessed mailbox items** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![監査ログ検索ツールで MailItemsAccessed アクションを検索する](../media/AdvAudit_MailItemsAccessed.png)

<span data-ttu-id="38753-153">Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="38753-153">You can also run the [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="send"></a><span data-ttu-id="38753-154">Send</span><span class="sxs-lookup"><span data-stu-id="38753-154">Send</span></span>

<span data-ttu-id="38753-155">Send イベントもメールボックス監査アクションであり、ユーザーが次のアクションのいずれかを実行したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="38753-155">The Send event is also a mailbox auditing action and is triggered when a user performs one of the following actions:</span></span>

- <span data-ttu-id="38753-156">メール メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="38753-156">Sends an email message</span></span>

- <span data-ttu-id="38753-157">メール メッセージへの返信</span><span class="sxs-lookup"><span data-stu-id="38753-157">Replies to an email message</span></span>

- <span data-ttu-id="38753-158">メール メッセージの転送</span><span class="sxs-lookup"><span data-stu-id="38753-158">Forwards an email message</span></span>

<span data-ttu-id="38753-p113">調査担当者は Send イベントを使用して、侵害されたアカウントから送信されたメールを特定することができます。Send イベントの監査レコードには、メッセージが送信された日時、InternetMessage ID、件名、メッセージに添付ファイルが含まれているかどうかなどのメッセージに関連する情報が含まれています。この監査情報は、調査担当者が侵害されたアカウントから送信された、または攻撃者によって送信されたメール メッセージに関連する情報を特定するのに役立ちます。さらに、調査担当者は Microsoft 365 の電子情報開示ツールを使用して (件名やメッセージ ID を使用して) メッセージを検索し、メッセージの送信先である受信者と送信されたメッセージの実際の内容を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="38753-p113">Investigators can use the Send event to identify email sent from a compromised account. The audit record for a Send event contains information about the message, such as when the message was sent, the InternetMessage ID, the subject line, and if the message contained attachments. This auditing information can help investigators identify information about email messages sent from a compromised account or sent by an attacker. Additionally, investigators can use a Microsoft 365 eDiscovery tool to search for the message (by using the subject line or message ID) to identify the recipients the message was sent to and the actual contents of the sent message.</span></span>

<span data-ttu-id="38753-163">Send 監査レコードを検索するには、Microsoft 365 コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md) の **Exchange メールボックス アクティビティ** ドロップダウン リストで **送信済みメッセージ** アクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="38753-163">To search for Send audit records, you can search for the **Sent message** activity in the **Exchange mailbox activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center.</span></span>

![監査ログ検索ツールでの送信済みメッセージ アクションの検索](../media/AdvAudit_SentMessage.png)

<span data-ttu-id="38753-165">Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="38753-165">You can also run the [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) or [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) commands in Exchange Online PowerShell.</span></span>

### <a name="searchqueryinitiatedexchange"></a><span data-ttu-id="38753-166">SearchQueryInitiatedExchange</span><span class="sxs-lookup"><span data-stu-id="38753-166">SearchQueryInitiatedExchange</span></span>

<span data-ttu-id="38753-p114">SearchQueryInitiatedExchange イベントは、ユーザーが Outlook on the web (OWA) の検索バーを使用してメールボックス内のアイテムを検索するときにトリガーされます。調査担当者は SearchQueryInitiatedExchange イベントを使用し、アカウントを侵害した可能性のある攻撃者がメールボックス内の機密情報を探したり、機密情報にアクセスしようとしたかどうかを判断することができます。SearchQueryInitiatedExchange イベントの監査レコードには、検索クエリの実際のテキストなどの情報が含まれています。攻撃者が実行した可能性のある検索クエリを調査することで、調査担当者は検索されたメール データの意図をより深く理解することができます。</span><span class="sxs-lookup"><span data-stu-id="38753-p114">The SearchQueryInitiatedExchange event is triggered when a person uses the Search bar in Outlook on the web (OWA) to search for items in a mailbox. Investigators can use the SearchQueryInitiatedExchange event to determine if an attacker who may have compromised an account looked for or tried to access sensitive information in the mailbox. The audit record for a SearchQueryInitiatedExchange event contains information such as the actual text of the search query. By looking at the search queries that an attacker may have performed, an investigator can better understand the intent of the email data that was searched for.</span></span>

<span data-ttu-id="38753-171">SearchQueryInitiatedExchange 監査レコードを検索するには、コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md) の **検索アクティビティ** ドロップダウン リストで **実行されたメール検索** アクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="38753-171">To search for SearchQueryInitiatedExchange audit records, you can search for the **Performed email search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![監査ログ検索ツールでの実行されたメール検索アクションの検索](../media/AdvAudit_SearchExchange.png)

<span data-ttu-id="38753-173">また、Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="38753-173">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="38753-174">(特定の E5 ユーザーによって実行された) SearchQueryInitiatedExchange イベントが監査ログの検索結果に含まれるように、Exchange Online PowerShell で次のコマンドを実行する必要があります: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="38753-174">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedExchange events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.</span></span>

### <a name="searchqueryinitiatedsharepoint"></a><span data-ttu-id="38753-175">SearchQueryInitiatedSharePoint</span><span class="sxs-lookup"><span data-stu-id="38753-175">SearchQueryInitiatedSharePoint</span></span>

<span data-ttu-id="38753-p115">メールボックス アイテムの検索と同様に、組織の SharePoint ホーム サイト内のアイテムをユーザーが検索すると、SearchQueryInitiatedSharePoint イベントがトリガーされます。調査担当者は SearchQueryInitiatedSharePoint イベントを使用し、攻撃者が SharePoint 内の機密情報を見つけようとした (そしてアクセスした可能性がある) かどうかを判断することができます。SearchQueryInitiatedSharePoint イベントの監査レコードには、検索クエリの実際のテキストも含まれています。攻撃者が実行した可能性のある検索クエリを調査することで、調査担当者は検索されたファイル データの意図や範囲をより深く理解することができます。</span><span class="sxs-lookup"><span data-stu-id="38753-p115">Similar to searching for mailbox items, the SearchQueryInitiatedSharePoint event is triggered when a person searches for items in the SharePoint home site for your organization. Investigators can use the SearchQueryInitiatedSharePoint event to determine if an attacker tried to find (and possibly accessed) sensitive information in SharePoint. The audit record for a SearchQueryInitiatedSharePoint event contains also contains the actual text of the search query. By looking at the search queries that an attacker may have performed, an investigator can better understand the intent and scope of the file data being searched for.</span></span>

<span data-ttu-id="38753-180">SearchQueryInitiatedSharePoint 監査レコードを検索するには、コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md) の **検索アクティビティ** ドロップダウン リストで **実行された SharePoint 検索** アクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="38753-180">To search for SearchQueryInitiatedSharePoint audit records, you can search for the **Performed SharePoint search** activity in the **Search activities** drop-down list in the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the compliance center.</span></span>

![監査ログ検索ツールでの実行された SharePoint 検索アクションの検索](../media/AdvAudit_SearchSharePoint.png)

<span data-ttu-id="38753-182">また、Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="38753-182">You can also run the [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="38753-183">(特定の E5 ユーザーによって実行された) SearchQueryInitiatedSharePoint イベントが監査ログの検索結果に含まれるように、Exchange Online PowerShell で次のコマンドを実行する必要があります: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。</span><span class="sxs-lookup"><span data-stu-id="38753-183">You must run the following command in Exchange Online PowerShell so that SearchQueryInitiatedSharePoint events (performed by the specified E5 user) are included in audit log search results: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.</span></span>

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a><span data-ttu-id="38753-184">Office 365 管理アクティビティ API への高帯域幅アクセス</span><span class="sxs-lookup"><span data-stu-id="38753-184">High-bandwidth access to the Office 365 Management Activity API</span></span>

<span data-ttu-id="38753-p116">Office 365 管理アクティビティ API を使用して監査ログにアクセスする組織は、発行者レベルの調整制限により制限されていました。つまり、発行者が複数のお客様に代わってデータをプルする場合、制限はそれらすべてのお客様で共有されていました。</span><span class="sxs-lookup"><span data-stu-id="38753-p116">Organizations that access auditing logs through the Office 365 Management Activity API were restricted by throttling limits at the publisher level. This means that for a publisher pulling data on behalf of multiple customers, the limit was shared by all those customers.</span></span>

<span data-ttu-id="38753-p117">高度な監査のリリースにより、発行者レベルの制限からテナント レベルの制限に移行します。その結果、各組織は、監査データにアクセスするために独自に完全に割り当てられた帯域幅を取得します。帯域幅は静的な定義済みの制限ではありませんが、組織内のシート数などの要因の組み合わせでモデル化され、E5 組織は E5 以外よりも多くの帯域幅を利用できます。</span><span class="sxs-lookup"><span data-stu-id="38753-p117">With the release of Advanced Audit, we're moving from a publisher-level limit to a tenant-level limit. The result is that each organization will get their own fully allocated bandwidth quota to access their auditing data. The bandwidth is not a static, predefined limit but is modeled on a combination of factors including the number of seats in the organization and that E5 organizations will get more bandwidth than non-E5 organizations.</span></span>

<span data-ttu-id="38753-p118">すべての組織には、最初に 1 分あたり 2,000 件の要求のベースラインが割り当てられます。この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。E5 組織は、E5 以外の組織の約 2 倍の帯域幅を利用できます。また、サービスの正常性を保護するために、最大帯域幅の上限も設定されます。</span><span class="sxs-lookup"><span data-stu-id="38753-p118">All organizations are initially allocated a baseline of 2,000 requests per minute. This limit will dynamically increase depending on an organization's seat count and their licensing subscription. E5 organizations will get about twice as much bandwidth as non-E5 organizations. There will also be cap on the maximum bandwidth to protect the health of the service.</span></span>

<span data-ttu-id="38753-194">詳細については、「[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)」の「API 調整」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38753-194">For more information, see the "API throttling" section in [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).</span></span>

## <a name="faqs-for-advanced-audit"></a><span data-ttu-id="38753-195">高度な監査についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="38753-195">FAQs for Advanced Audit</span></span>

<span data-ttu-id="38753-196">**高度な監査を利用するには、すべてのユーザーに E5 ライセンスが必要ですか ?**</span><span class="sxs-lookup"><span data-stu-id="38753-196">**Does every user need an E5 license to benefit from Advanced Audit?**</span></span>

<span data-ttu-id="38753-p119">ユーザーレベルの高度な監査機能を利用するには、ユーザーに E5 ライセンスを割り当てる必要があります。適切なライセンスをチェックして、ユーザーに機能を公開するための機能がいくつかあります。たとえば、90 日を超えて E5 ライセンスが割り当てられていないユーザーの監査レコードを保持しようとすると、システムはエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="38753-p119">To benefit from user-level Advanced Audit capabilities, a user needs to be assigned an E5 license. There are some capabilities that will check for the appropriate license to expose the feature for the user. For example, if you're trying to retain the audit records for a user who isn't assigned an E5 license for longer than 90 days, the system will return an error message.</span></span>

<span data-ttu-id="38753-200">**組織に E5 サブスクリプションがある場合、重要なイベントの監査レコードにアクセスするために何かをする必要はありますか?**</span><span class="sxs-lookup"><span data-stu-id="38753-200">**My organization has an E5 subscription, do I need to do anything to get access to audit records for crucial events?**</span></span>

<span data-ttu-id="38753-201">適切なライセンスが割り当てられている対象のお客様とユーザーには、重要な監査イベントにアクセスするためのアクションはありません。</span><span class="sxs-lookup"><span data-stu-id="38753-201">For eligible customers and users that are assigned the appropriate license, there is no action to get access to crucial auditing events.</span></span>

<span data-ttu-id="38753-202">**新しい 10 年間の監査ログ保持アドオン ライセンスはいつ利用できるようになりますか?**</span><span class="sxs-lookup"><span data-stu-id="38753-202">**When will the new 10-year audit log retention add-on license be available?**</span></span>

<span data-ttu-id="38753-203">新しい 10 年間の監査ログ保持アドオンは、E5 サブスクリプションをお持ちのお客様を対象に 2021 年初頭より購入できるようになります。</span><span class="sxs-lookup"><span data-stu-id="38753-203">The new 10-year audit log retention add-on will be available for purchase by customers with E5 subscriptions in early 2021.</span></span>

<span data-ttu-id="38753-204">**10 年間の監査ログ保持ポリシーを作成していて、必要なアドオン ライセンスが 2021 年初頭に利用可能となる前に一般提供された場合、組織の監査ログ データはどうなりますか?**</span><span class="sxs-lookup"><span data-stu-id="38753-204">**What happens to my organization's audit log data if I create 10-year audit log retention policy the feature is released to general availability but before the required add-on license is available in early 2021?**</span></span>

<span data-ttu-id="38753-205">一般提供された後に作成した 10 年間の監査ログ保持ポリシーの対象となる任意の監査ログ データについては、10 年間にわたって保持されます。</span><span class="sxs-lookup"><span data-stu-id="38753-205">Any audit log data covered by a 10-year audit log retention policy that you create after general availability will be retained for 10 years.</span></span> <span data-ttu-id="38753-206">2021 年初頭に 10 年間の監査ログ保持アドオン ライセンスが利用可能になったときには、既存の 10 年間の監査データ保持ポリシーによって監査データを保持しているユーザーのためのアドオン ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38753-206">When the 10-year audit log retention add-on license is available in early 2021, you will need to purchase add-on licenses for users who's audit data is being retained by an existing 10-year audit retention policy.</span></span> <span data-ttu-id="38753-207">また、2021 年初頭にアドオン ライセンスが利用可能になると、10 年間の監査ログ保持ポリシーを新たに作成するときに適切なライセンスが強制されるようになります。</span><span class="sxs-lookup"><span data-stu-id="38753-207">Also, once the add-on license is available in early 2021, the appropriate licensing will be enforced when you create new 10-year audit log retention policies.</span></span>

<span data-ttu-id="38753-208">**高度な監査の新しいイベントは、Office 365 管理アクティビティ API で利用できますか ?**</span><span class="sxs-lookup"><span data-stu-id="38753-208">**Are the new events in Advanced Audit available in the Office 365 Management Activity API?**</span></span>

<span data-ttu-id="38753-209">はい。</span><span class="sxs-lookup"><span data-stu-id="38753-209">Yes.</span></span> <span data-ttu-id="38753-210">適切なライセンスを持つユーザーの監査レコードが生成されている限り、Office 365 管理アクティビティ API を介してこれらのレコードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="38753-210">As long as audit records are generated for users with the appropriate license, you'll be able to access these records via the Office 365 Management Activity API.</span></span>

<span data-ttu-id="38753-211">**より高い帯域幅は、遅延の改善やより高い SLA を意味しますか ?**</span><span class="sxs-lookup"><span data-stu-id="38753-211">**Does higher bandwidth mean better latency or higher SLA?**</span></span>

<span data-ttu-id="38753-212">現時点では、高帯域幅は、特に大量の監査シグナルおよび重要な消費パターンを持つ組織に対して、より良いパイプラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="38753-212">At this time, high bandwidth provides a better pipeline, especially for organizations with a high volume of auditing signals and significant consumption patterns.</span></span> <span data-ttu-id="38753-213">より高い帯域幅により、遅延が改善される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38753-213">More bandwidth can lead to better latency.</span></span> <span data-ttu-id="38753-214">ただし、高帯域幅に関連する SLA はありません。</span><span class="sxs-lookup"><span data-stu-id="38753-214">But there isn't an SLA associated with high bandwidth.</span></span> <span data-ttu-id="38753-215">標準的な遅延はドキュメント化されており、これらの遅延は高度な監査のリリースでは変更されません。</span><span class="sxs-lookup"><span data-stu-id="38753-215">Standard latencies are documented, and these latencies don't change with the release of Advanced Audit.</span></span>
