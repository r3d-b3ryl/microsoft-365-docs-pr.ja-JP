---
title: 個人情報の漏えいを監視する
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
description: 個人データの漏えいの監視に使用できる 3 つのツールについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05d31ac36fbdc687c60ec3c03efac9be43da9c39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878486"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="46461-103">個人情報の漏えいを監視する</span><span class="sxs-lookup"><span data-stu-id="46461-103">Monitor for leaks of personal data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="46461-p101">個人データの使用と転送を監視するために使用できるツールは数多くあります。このトピックでは、効果的な 3 つのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46461-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![個人データの使用と転送を監視するためのツール](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="46461-107">この図について:</span><span class="sxs-lookup"><span data-stu-id="46461-107">In the illustration:</span></span>

- <span data-ttu-id="46461-p102">まず、SharePoint Online、OneDrive for Business、転送中のメールの個人データを監視するための Microsoft 365 データ損失防止レポートから開始します。これらのレポートは、個人データを監視するための最も詳細なレベルの内容を提供します。ただし、このレポートには Office 365 のすべてのサービスが含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="46461-p102">Start with Microsoft 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These reports provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="46461-p103">次に、アラート ポリシーと監査ログを使用して、サービス全体のアクティビティを監視します。進行中の監視を設定するか、監査ログを検索してインシデントを調査します。監査ログは、Sway、Power BI、電子情報開示、Dynamics 365、Microsoft Flow、Microsoft Teams、管理アクティビティ、OneDrive for Business、SharePoint Online、転送中のメール、保管中のメールボックスなどのサービス全体で機能します。Skype の会話は保管中のメールボックスに含まれます。</span><span class="sxs-lookup"><span data-stu-id="46461-p103">Next, use alert policies and the audit log to monitor activity across services. Set up ongoing monitoring or search the audit log to investigate an incident. The audit log works across services—Sway, Power BI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="46461-p104">最後に、Microsoft Cloud App Security を使用して、他の SaaS プロバイダーの機密データを含むファイルを監視します。機密情報の種類と統合ラベルを Azure Information Protection と Cloud App Security が有効な Office で使用できる機能が近日公開予定です。すべての SaaS アプリまたは特定のアプリ (Box など) に適用するポリシーを設定できます。Cloud App Security では、メールに添付されたファイルを含め、Exchange Online のファイルは検出されません。</span><span class="sxs-lookup"><span data-stu-id="46461-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can set up policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="data-loss-prevention-reports"></a><span data-ttu-id="46461-119">データ損失防止レポート</span><span class="sxs-lookup"><span data-stu-id="46461-119">Data loss prevention reports</span></span>

<span data-ttu-id="46461-p105">データ損失防止 (DLP) ポリシーを作成したら、意図したとおりに動作し、コンプライアンスの遵守に役立っているかどうかを確認します。Office 365 の DLP レポートを使用すると、DLP ポリシーの一致項目、上書き、誤検知の数をすぐに確認したり、時間の経過とともに増加または減少する傾向があるかどうかを見極めたりできます。また、さまざまな方法でレポートをフィルター処理したり、グラフ上の線の特定のポイントを選択して詳細情報を表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="46461-p105">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view more details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="46461-122">DLP レポートを使用すると、以下のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="46461-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="46461-123">特定の期間に絞り込み、スパイクや傾向の理由を理解します。</span><span class="sxs-lookup"><span data-stu-id="46461-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
- <span data-ttu-id="46461-124">組織の DLP ポリシーに違反するビジネス プロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="46461-124">Discover business processes that violate your organization's DLP policies.</span></span>
- <span data-ttu-id="46461-125">DLP ポリシーのビジネスに及ぼす影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="46461-125">Understand any business impact of the DLP policies.</span></span>
- <span data-ttu-id="46461-126">ユーザーがポリシーを上書きしたり、誤検知を報告したりしてポリシーのヒントを解決するときに送信する正当な理由を表示します。</span><span class="sxs-lookup"><span data-stu-id="46461-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>
- <span data-ttu-id="46461-127">特定の DLP ポリシーに関する一致箇所を表示することによって、そのポリシーのコンプライアンス遵守を確認します。</span><span class="sxs-lookup"><span data-stu-id="46461-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
- <span data-ttu-id="46461-128">詳細ウィンドウで、DLP ポリシーに一致する機密データを含むファイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="46461-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="46461-129">さらに、テスト モードで実行するときに、DLP レポートを使用して DLP ポリシーを微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="46461-129">In addition, you can use the DLP reports to fine-tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="46461-130">DLP レポートは、Microsoft 365 コンプライアンス センターにあります。</span><span class="sxs-lookup"><span data-stu-id="46461-130">DLP reports are in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="46461-131">**[レポート]** \> **[組織データ]** セクションに移動して、**DLP ポリシーの一致**、**DLP インシデント**、および **DLP の誤検知と上書き** のレポートを検索します。</span><span class="sxs-lookup"><span data-stu-id="46461-131">Go to **Reports** \> **Organizational data** section to find the **DLP policy matches**, **DLP incidents**, and **DLP false positives and overrides** reports.</span></span>

<span data-ttu-id="46461-132">詳細については、「[データ損失防止のレポートの表示](../../compliance/view-the-dlp-reports.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46461-132">For more information, see [View the reports for data loss prevention](../../compliance/view-the-dlp-reports.md).</span></span>

![DLP ポリシーと一致することを示すレポート](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a><span data-ttu-id="46461-134">監査ログおよびアラートのポリシー</span><span class="sxs-lookup"><span data-stu-id="46461-134">Audit log and alert policies</span></span>

<span data-ttu-id="46461-135">監査ログには、Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft Teams、Power BI、Sway などの サービスからのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="46461-135">The audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other services.</span></span>

<span data-ttu-id="46461-136">Microsoft 365 Defender ポータルと Microsoft 365 コンプライアンス センターでは、監査ログを監視およびレポートする 2 つの方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="46461-136">The Microsoft 365 Defender portal and the Microsoft 365 compliance center provide two ways to monitor and report against the audit log:</span></span>

- <span data-ttu-id="46461-137">アラート ポリシーの設定、アラートの表示、トレンドの監視には、Microsoft 365 Defender ポータルまたは Microsoft 365 コンプライアンス センターのいずれかにあるアラート ポリシーやアラート ダッシュボード ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="46461-137">Set up alert policies, view alerts, and monitor trends—Use the alert policy and alert dashboard tools in either the Microsoft 365 Defender portal or the Microsoft 365 compliance center.</span></span>
- <span data-ttu-id="46461-p107">監査ログを直接検索するには、指定した日付の範囲ですべてのイベントを検索します。また、操作を実行したユーザー、操作、または対象オブジェクトなど、特定の条件に基づいて結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="46461-p107">Search the audit log directly: Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="46461-p108">情報コンプライアンスおよびセキュリティ チームは、これらのツールを使用して、エンド ユーザーと管理者の両方がサービスで実行したアクティビティを予防的に確認することができます。特定のアクティビティが特定のサイト コレクションで発生した場合に (たとえば、GDPR 関連情報が含まれていることがわかっているサイトからコンテンツを共有する場合など)、メール通知を送信するように自動アラートを設定できます。これによってチームは、ユーザーをフォローアップして、企業のセキュリティ ポリシーの遵守の徹底、追加のトレーニング提供などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="46461-p108">Information compliance and security teams can use these tools to proactively review activities performed by both end users and administrators across services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR-related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="46461-p109">情報セキュリティ チームは、監査ログを検索して疑いのあるデータ侵害を調査し、根本原因と違反の程度の両方を判断することもできます。この組み込みの機能は、GDPR の第 33 条および第 34 条の遵守を円滑にします。これらの条項では、データ違反について GDPR 監督当局およびデータ主体に、特定の期間内に通知することが求められています。監査ログ エントリは、サービス内で 90 日間のみ保持されます。多くの場合、これらのログをより長期間保持することが推奨され、多くの企業もそれを必要としています。</span><span class="sxs-lookup"><span data-stu-id="46461-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built-in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="46461-p110">Microsoft 管理アクティビティ API を使用して統一監査ログを購読し、必要に応じてログ エントリを保存し、高度なダッシュボードとアラートを提供することができるソリューションを活用できます。たとえば、[Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365) が例として挙げられます。</span><span class="sxs-lookup"><span data-stu-id="46461-p110">Solutions are available that subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="46461-148">アラート ポリシーと監査ログの検索については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46461-148">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="46461-149">Microsoft 365 のアラート ポリシー</span><span class="sxs-lookup"><span data-stu-id="46461-149">Alert policies in Microsoft 365</span></span>](../../compliance/alert-policies.md)
- <span data-ttu-id="46461-150">[Office 365 で監査ログを検索してユーザーと管理者のアクティビティを確認する](../../compliance/search-the-audit-log-in-security-and-compliance.md) (概要)</span><span class="sxs-lookup"><span data-stu-id="46461-150">[Search the audit log for user and admin activity in Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md) (introduction)</span></span>
- [<span data-ttu-id="46461-151">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="46461-151">Turn audit log search on or off</span></span>](../../compliance/turn-audit-log-search-on-or-off.md)
- [<span data-ttu-id="46461-152">監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="46461-152">Search the audit log</span></span>](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- <span data-ttu-id="46461-153">[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (コマンドレット)</span><span class="sxs-lookup"><span data-stu-id="46461-153">[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span></span>
- [<span data-ttu-id="46461-154">監査ログの詳細なプロパティ</span><span class="sxs-lookup"><span data-stu-id="46461-154">Detailed properties in the audit log</span></span>](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="46461-155">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="46461-155">Microsoft Cloud App Security</span></span>

<span data-ttu-id="46461-156">Microsoft Cloud App Security は、ネットワーク上で使用されている他の SaaS アプリや、これらのアプリとの間でやり取りされる機密データの検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="46461-156">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data sent to and from these apps.</span></span>

<span data-ttu-id="46461-p111">Microsoft Cloud App Security は、クラウド アプリのための詳細な可視化、きめ細やかな制御、高度な脅威の防止を提供する包括的なサービスです。ネットワーク上のすべてのデバイスから 15,000 以上のクラウド アプリケーションを識別し、リスク スコアリングや継続的なリスク評価と分析を提供します。ファイアウォールやプロキシから情報を収集して、クラウドの使用状況やシャドウ IT に関する完全な可視性とコンテキストを提供するため、エージェントは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="46461-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls, and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="46461-p112">クラウド環境をよりよく理解するために、Cloud App Security の調査機能は、承認および管理されているアプリのすべてのアクティビティ、ファイル、アカウントの詳細内容を可視化します。ファイル レベルの詳細な情報を取得し、クラウド アプリでのデータの移動を把握できます。</span><span class="sxs-lookup"><span data-stu-id="46461-p112">To better understand your cloud environment, the Cloud App Security investigate feature provides deep visibility into all activities, files, and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="46461-162">たとえば、次の図は GDPR に役立つ 2 つのクラウド アプリケーション セキュリティ ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="46461-162">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![クラウド アプリケーション セキュリティ ポリシーの例](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="46461-164">1 番目のポリシーは、選択した事前定義の PII 属性またはカスタム式を持つファイルが、選択した SaaS アプリから組織外で共有されると警告します。</span><span class="sxs-lookup"><span data-stu-id="46461-164">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="46461-p113">2 番目のポリシーは、管理対象外のデバイスへのファイル ダウンロードをブロックします。検索するファイル内の属性と、ポリシーを適用する SaaS アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="46461-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="46461-167">これらの属性タイプは、Cloud App Security に近日公開されます。</span><span class="sxs-lookup"><span data-stu-id="46461-167">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="46461-168">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="46461-168">Sensitive information types</span></span>
- <span data-ttu-id="46461-169">Microsoft 365 および Azure Information Protection での統一ラベル</span><span class="sxs-lookup"><span data-stu-id="46461-169">Unified labels across Microsoft 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="46461-170">Cloud App Security ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="46461-170">Cloud App Security dashboard</span></span>

<span data-ttu-id="46461-p114">まだ Cloud App Security の使用を開始していない場合は、まず開始してください。Cloud App Security には <https://portal.cloudappsecurity.com> からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="46461-p114">If you haven't yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

> [!NOTE]
> <span data-ttu-id="46461-p115">Cloud App Security の使用を開始するときやラベルを割り当てる前に、[一般設定] の [Azure Information Protection 分類ラベルについてファイルを自動的にスキャンする] を有効にしてください。設定後は、Cloud App Security は、変更されるまで既存ファイルを再スキャンしません。</span><span class="sxs-lookup"><span data-stu-id="46461-p115">Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![アラートに関する情報を表示するダッシュボード](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="46461-176">詳しくは、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46461-176">More information:</span></span>

- [<span data-ttu-id="46461-177">Cloud App Security を展開する</span><span class="sxs-lookup"><span data-stu-id="46461-177">Deploy Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security)
- [<span data-ttu-id="46461-178">Microsoft Cloud App Security の詳細情報</span><span class="sxs-lookup"><span data-stu-id="46461-178">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [<span data-ttu-id="46461-179">Microsoft Cloud App Security プロキシを使用して機密情報のダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="46461-179">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="46461-180">個人データの共有を検出するためのファイル ポリシーとアクティビティ ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="46461-180">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="46461-181">PII (クレジット カード番号) を含むファイルの共有を検出する</span><span class="sxs-lookup"><span data-stu-id="46461-181">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="46461-182">承認されたクラウド アプリから、クレジット カード番号を含むファイルが共有されたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="46461-182">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

<br>

****

|<span data-ttu-id="46461-183">コントロール</span><span class="sxs-lookup"><span data-stu-id="46461-183">Control</span></span>|<span data-ttu-id="46461-184">設定</span><span class="sxs-lookup"><span data-stu-id="46461-184">Settings</span></span>|
|---|---|
|<span data-ttu-id="46461-185">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="46461-185">Policy type</span></span>|<span data-ttu-id="46461-186">ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="46461-186">File policy</span></span>|
|<span data-ttu-id="46461-187">ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="46461-187">Policy template</span></span>|<span data-ttu-id="46461-188">テンプレートなし</span><span class="sxs-lookup"><span data-stu-id="46461-188">No template</span></span>|
|<span data-ttu-id="46461-189">ポリシーの重要度</span><span class="sxs-lookup"><span data-stu-id="46461-189">Policy severity</span></span>|<span data-ttu-id="46461-190">高</span><span class="sxs-lookup"><span data-stu-id="46461-190">High</span></span>|
|<span data-ttu-id="46461-191">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="46461-191">Category</span></span>|<span data-ttu-id="46461-192">DLP</span><span class="sxs-lookup"><span data-stu-id="46461-192">DLP</span></span>|
|<span data-ttu-id="46461-193">フィルター設定</span><span class="sxs-lookup"><span data-stu-id="46461-193">Filter settings</span></span>|<span data-ttu-id="46461-194">Access level = Public (Internet), Public, External</span><span class="sxs-lookup"><span data-stu-id="46461-194">Access level = Public (Internet), Public, External</span></span> <p> <span data-ttu-id="46461-195">App = \<select apps\> (特定の SaaS アプリに監視を制限する場合は、この設定を使用します)</span><span class="sxs-lookup"><span data-stu-id="46461-195">App = \<select apps\> (use this setting if you want to limit monitoring to specific SaaS apps)</span></span>|
|<span data-ttu-id="46461-196">適用先</span><span class="sxs-lookup"><span data-stu-id="46461-196">Apply to</span></span>|<span data-ttu-id="46461-197">すべてのファイル、すべての所有者</span><span class="sxs-lookup"><span data-stu-id="46461-197">All files, all owners</span></span>|
|<span data-ttu-id="46461-198">内容の検査</span><span class="sxs-lookup"><span data-stu-id="46461-198">Content inspection</span></span>|<span data-ttu-id="46461-199">現在の式に一致するファイルを含む: All countries: Finance: Credit card number</span><span class="sxs-lookup"><span data-stu-id="46461-199">Includes files that match a present expression: All countries: Finance: Credit card number</span></span> <p> <span data-ttu-id="46461-200">関連するコンテキストを必要としない: オフ (この設定は、キーワードと正規表現に一致します)</span><span class="sxs-lookup"><span data-stu-id="46461-200">Don't require relevant context: unchecked (this setting will match keywords as well as regex)</span></span> <p> <span data-ttu-id="46461-201">1 つでも一致するファイルを含む</span><span class="sxs-lookup"><span data-stu-id="46461-201">Includes files with at least 1 match</span></span> <p> <span data-ttu-id="46461-202">違反の最後の 4 文字をマスク解除する: オン</span><span class="sxs-lookup"><span data-stu-id="46461-202">Unmask the last 4 characters of the violation: checked</span></span>|
|<span data-ttu-id="46461-203">アラート</span><span class="sxs-lookup"><span data-stu-id="46461-203">Alerts</span></span>|<span data-ttu-id="46461-204">一致するファイルごとにアラートを作成する: オン</span><span class="sxs-lookup"><span data-stu-id="46461-204">Create an alert for each matching file: checked</span></span> <p> <span data-ttu-id="46461-205">1 日のアラート制限: 1000</span><span class="sxs-lookup"><span data-stu-id="46461-205">Daily alert limit: 1000</span></span> <p> <span data-ttu-id="46461-206">電子メールとしてアラートを選択する: オン</span><span class="sxs-lookup"><span data-stu-id="46461-206">Select an alert as email: checked</span></span> <p> <span data-ttu-id="46461-207">宛先: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="46461-207">To: infosec@contoso.com</span></span>|
|<span data-ttu-id="46461-208">ガバナンス</span><span class="sxs-lookup"><span data-stu-id="46461-208">Governance</span></span>|<span data-ttu-id="46461-209">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="46461-209">Microsoft OneDrive for Business</span></span> <p> <span data-ttu-id="46461-210">非公開にする: 外部ユーザーの削除をオン</span><span class="sxs-lookup"><span data-stu-id="46461-210">Make private: check Remove External Users</span></span> <p> <span data-ttu-id="46461-211">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="46461-211">All other settings: unchecked</span></span> <p> <span data-ttu-id="46461-212">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="46461-212">Microsoft SharePoint Online</span></span> <p> <span data-ttu-id="46461-213">非公開にする: 外部ユーザーの削除をオン</span><span class="sxs-lookup"><span data-stu-id="46461-213">Make private: check Remove External Users</span></span> <p> <span data-ttu-id="46461-214">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="46461-214">All other settings: unchecked</span></span>|
|

<span data-ttu-id="46461-215">類似のポリシー:</span><span class="sxs-lookup"><span data-stu-id="46461-215">Similar policies:</span></span>

- <span data-ttu-id="46461-216">PII (メール アドレス) を含むファイルの共有を検出する</span><span class="sxs-lookup"><span data-stu-id="46461-216">Detect sharing of Files containing PII - Email Address</span></span>
- <span data-ttu-id="46461-217">PII (パスポート番号) を含むファイルの共有を検出する</span><span class="sxs-lookup"><span data-stu-id="46461-217">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="46461-218">Box for Business または OneDrive for Business の顧客データや人事データを検出する</span><span class="sxs-lookup"><span data-stu-id="46461-218">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="46461-219">OneDrive for Business または Box for Business に Customer Data (顧客データ) または HR Data (人事データ) という名前のファイルがアップロードされたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="46461-219">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="46461-220">注:</span><span class="sxs-lookup"><span data-stu-id="46461-220">Notes:</span></span>

- <span data-ttu-id="46461-221">Box の監視では、API Connector SDK を使用してコネクタを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46461-221">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>
- <span data-ttu-id="46461-222">このポリシーには、現在プライベート プレビューになっている機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="46461-222">This policy requires capabilities that are currently in private preview.</span></span>

<br>

****

|<span data-ttu-id="46461-223">コントロール</span><span class="sxs-lookup"><span data-stu-id="46461-223">Control</span></span>|<span data-ttu-id="46461-224">設定</span><span class="sxs-lookup"><span data-stu-id="46461-224">Settings</span></span>|
|---|---|
|<span data-ttu-id="46461-225">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="46461-225">Policy type</span></span>|<span data-ttu-id="46461-226">アクティビティ ポリシー</span><span class="sxs-lookup"><span data-stu-id="46461-226">Activity policy</span></span>|
|<span data-ttu-id="46461-227">ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="46461-227">Policy template</span></span>|<span data-ttu-id="46461-228">テンプレートなし</span><span class="sxs-lookup"><span data-stu-id="46461-228">No template</span></span>|
|<span data-ttu-id="46461-229">ポリシーの重要度</span><span class="sxs-lookup"><span data-stu-id="46461-229">Policy severity</span></span>|<span data-ttu-id="46461-230">高</span><span class="sxs-lookup"><span data-stu-id="46461-230">High</span></span>|
|<span data-ttu-id="46461-231">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="46461-231">Category</span></span>|<span data-ttu-id="46461-232">制御を共有</span><span class="sxs-lookup"><span data-stu-id="46461-232">Sharing Control</span></span>|
|<span data-ttu-id="46461-233">操作対象</span><span class="sxs-lookup"><span data-stu-id="46461-233">Act on</span></span>|<span data-ttu-id="46461-234">1 つのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="46461-234">Single activity</span></span>|
|<span data-ttu-id="46461-235">フィルター設定</span><span class="sxs-lookup"><span data-stu-id="46461-235">Filter settings</span></span>|<span data-ttu-id="46461-236">アクティビティの種類 = ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="46461-236">Activity type = Upload File</span></span> <p> <span data-ttu-id="46461-237">アプリ = Microsoft OneDrive for Business および Box</span><span class="sxs-lookup"><span data-stu-id="46461-237">App = Microsoft OneDrive for Business and Box</span></span> <p> <span data-ttu-id="46461-238">分類ラベル (現在はプライベート プレビュー): Azure Information Protection = 顧客データ、人事—給与データ、人事—従業員データ</span><span class="sxs-lookup"><span data-stu-id="46461-238">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span>|
|<span data-ttu-id="46461-239">アラート</span><span class="sxs-lookup"><span data-stu-id="46461-239">Alerts</span></span>|<span data-ttu-id="46461-240">アラートを作成する: オン</span><span class="sxs-lookup"><span data-stu-id="46461-240">Create an alert: checked</span></span> <p> <span data-ttu-id="46461-241">1 日のアラート制限: 1000</span><span class="sxs-lookup"><span data-stu-id="46461-241">Daily alert limit: 1000</span></span> <p> <span data-ttu-id="46461-242">電子メールとしてアラートを選択する: オン</span><span class="sxs-lookup"><span data-stu-id="46461-242">Select an alert as email: checked</span></span> <p> <span data-ttu-id="46461-243">宛先: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="46461-243">To: infosec@contoso.com</span></span>|
|<span data-ttu-id="46461-244">ガバナンス</span><span class="sxs-lookup"><span data-stu-id="46461-244">Governance</span></span>|<span data-ttu-id="46461-245">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="46461-245">All apps</span></span> <p> <span data-ttu-id="46461-246">ユーザーを検疫に入れる: オン</span><span class="sxs-lookup"><span data-stu-id="46461-246">Put user in quarantine: check</span></span> <p> <span data-ttu-id="46461-247">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="46461-247">All other settings: unchecked</span></span> <p> <span data-ttu-id="46461-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="46461-248">Office 365</span></span> <p> <span data-ttu-id="46461-249">ユーザーを検疫に入れる: オン</span><span class="sxs-lookup"><span data-stu-id="46461-249">Put user in quarantine: check</span></span> <p> <span data-ttu-id="46461-250">その他のすべての設定: オフ</span><span class="sxs-lookup"><span data-stu-id="46461-250">All other settings: unchecked</span></span>|
|

<span data-ttu-id="46461-251">類似のポリシー:</span><span class="sxs-lookup"><span data-stu-id="46461-251">Similar policies:</span></span>

- <span data-ttu-id="46461-252">顧客データや人事データの大量ダウンロードを検出する—顧客データや人事データを含む多数のファイルが、単一ユーザーによって短時間にダウンロードされたことが検出されたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="46461-252">Detect large downloads of Customer data or HR Data—Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>
- <span data-ttu-id="46461-253">顧客および人事データの共有を検出する—顧客または人事データを含むファイルが共有されたときに警告します。</span><span class="sxs-lookup"><span data-stu-id="46461-253">Detect Sharing of Customer and HR Data—Alert when files containing Customer or HR Data are shared.</span></span>
