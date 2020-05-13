---
title: チュートリアル-スプーフィングインテリジェンスの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、どの送信者が認証されていない電子メールを正規に送信しているかをすばやく判断する方法を含め、スプーフィングインテリジェンスの理解のしくみを理解できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a71b885926d742f86a5a0c86443a5f5ba23b8a6
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208466"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a><span data-ttu-id="bcf28-103">チュートリアル-Microsoft 365 での ATP のスプーフに関する知識の理解</span><span class="sxs-lookup"><span data-stu-id="bcf28-103">Walkthrough - ATP Spoof intelligence insight in Microsoft 365</span></span>

<span data-ttu-id="bcf28-104">Advanced Threat Protection (ATP) を使用した Microsoft 365 の組織では、スプーフィングインテリジェンスの洞察を使用して、認証されていない電子メールを正当に送信している送信者をすばやく判断できます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-104">In Microsoft 365 organizations with Advanced Threat Protection (ATP), you can use the spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email.</span></span> <span data-ttu-id="bcf28-105">スプーフィングされたメッセージの送信を許可することにより、ユーザーが誤検知を行うリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-105">By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span> <span data-ttu-id="bcf28-106">また、スプーフィングインテリジェンスの洞察を使用して、許可されたドメインペアを監視および管理して、セキュリティの追加の層を提供したり、安全でないメッセージが組織に到着しないようにしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-106">You can also use the spoof intelligence insight to monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="bcf28-107">[セキュリティ & コンプライアンスセンターのレポートと分析](reports-and-insights-in-security-and-compliance.md)を初めて使用する場合は、ダッシュボードから洞察や推奨されるアクションに簡単に移動する方法を確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-107">If you're new to [reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>

<span data-ttu-id="bcf28-108">このチュートリアルは、セキュリティ & コンプライアンスセンターに対していくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-108">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="bcf28-109">レポートと分析情報の移動については、「関連項目」セクションのチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf28-109">To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bcf28-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="bcf28-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bcf28-111"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bcf28-112">[ **Security dashboard** ] ページに直接移動するには、を使用 <https://protection.office.com/searchandinvestigation/dashboard> します。</span><span class="sxs-lookup"><span data-stu-id="bcf28-112">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="bcf28-113">セキュリティ & コンプライアンスセンターでは、複数のダッシュボードからスプーフィングインテリジェンスの洞察を確認できます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-113">You can view the spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="bcf28-114">どのダッシュボードを使用しているかに関係なく、洞察は同じ情報を提供し、同じタスクをすばやく実行することができます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-114">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="bcf28-115">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-115">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="bcf28-116">スプーフィングインテリジェンスの洞察を使用するには、**組織の管理**、**セキュリティ管理者**、または**セキュリティリーダー**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-116">To use the spoof intelligence insight, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="bcf28-117">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bcf28-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="bcf28-118">ATP のフィッシング対策ポリシーのスプーフィングインテリジェンスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bcf28-118">You enable and disable spoof intelligence in ATP anti-phishing policies.</span></span> <span data-ttu-id="bcf28-119">詳細については、「 [Microsoft 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf28-119">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="bcf28-120">Exchange Online メールボックスを使用する Microsoft 365 組織と、Exchange Online メールボックスを含まないスタンドアロンの Exchange Online Protection (EOP) では、スプーフィングインテリジェンスを使用して、認証されていないメッセージを送信している送信者を監視および管理できます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-120">In Microsoft 365 organizations with Exchange Online mailboxes, and in standalone Exchange Online Protection (EOP) without Exchange Online mailboxes, you can use spoof intelligence to monitor and manage senders you are sending you unauthenticated messages.</span></span> <span data-ttu-id="bcf28-121">詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスを設定する](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcf28-121">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="bcf28-122">セキュリティ & コンプライアンスセンターでのスプーフィングインテリジェンスに関する洞察を開く</span><span class="sxs-lookup"><span data-stu-id="bcf28-122">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="bcf28-123">[セキュリティ & コンプライアンスセンター] で、[**脅威管理**] ダッシュボードに移動し \> **ます。**</span><span class="sxs-lookup"><span data-stu-id="bcf28-123">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="bcf28-124">[ **Insights** ] 行で、次のいずれかのアイテムを探します。</span><span class="sxs-lookup"><span data-stu-id="bcf28-124">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="bcf28-125">**スプーフィングインテリジェンスが有効になっ**ています。この洞察は、**過去30日間の認証に失敗したスプーフィングドメイン**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-125">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="bcf28-126">これが既定です。</span><span class="sxs-lookup"><span data-stu-id="bcf28-126">This is the default.</span></span>

   - <span data-ttu-id="bcf28-127">**スプーフィングインテリジェンスが無効になっ**ています。名前付きの**スプーフィング保護を有効**にし、それをクリックすると、スプーフィングインテリジェンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-127">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="bcf28-128">ダッシュボードの洞察には、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-128">The insight on the dashboard shows you information like this:</span></span>

   ![スプーフィングインテリジェンスの洞察のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="bcf28-130">この洞察には、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-130">This insight has two modes:</span></span>

   - <span data-ttu-id="bcf28-131">**洞察モード**。</span><span class="sxs-lookup"><span data-stu-id="bcf28-131">**Insight mode**.</span></span> <span data-ttu-id="bcf28-132">いずれかのスプーフィングポリシーを有効にしている場合は、過去30日間のスプーフィングインテリジェンス機能によって影響を受けたメールの数が洞察によって示されます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-132">If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="bcf28-133">**If モードについ**て</span><span class="sxs-lookup"><span data-stu-id="bcf28-133">**What if mode**.</span></span> <span data-ttu-id="bcf28-134">スプーフィングポリシーが有効になっていない場合は、過去30日間のスプーフィングインテリジェンス機能によって影響を*受けるメールの数が洞察*に示されています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-134">If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="bcf28-135">どちらの方法でも、洞察に表示される偽装されたドメインは、**疑わしいドメイン**の組と**不審でないドメインのペア**という2つのカテゴリに分かれています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-135">Either way, the spoofed domains displayed in the insight are separated into two categories: **suspicious domain pairs** and **non-suspicious domain pairs**.</span></span> <span data-ttu-id="bcf28-136">これらのカテゴリは、確認のために3つの異なるバケットにさらに細分化されています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-136">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="bcf28-137">**ドメインペア**は、From アドレスと送信元インフラストラクチャの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="bcf28-137">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="bcf28-138">From アドレスは、電子メールクライアントに表示される送信者の電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="bcf28-138">The From address is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="bcf28-139">このアドレスにより、電子メールの作成者を識別します。</span><span class="sxs-lookup"><span data-stu-id="bcf28-139">This address identifies the author of the email.</span></span> <span data-ttu-id="bcf28-140">つまり、メッセージを書いた個人またはシステムのメールボックスになります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-140">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="bcf28-141">このアドレスは、アドレスとも呼ばれ `5322.From` ます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="bcf28-142">送信元のインフラストラクチャまたは送信者は、送信元 IP アドレスの逆引き DNS 参照 (PTR レコード) の組織ドメインです。</span><span class="sxs-lookup"><span data-stu-id="bcf28-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="bcf28-143">送信元の IP アドレスに PTR レコードがない場合、送信元の IP アドレスは、CIDR 表記法 (/24) で255.255.255.0 サブネットマスクを使用して識別されます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="bcf28-144">たとえば、IP アドレスが192.168.100.100 の場合、送信者の完全な IP アドレスは 192.168.100.100/24 です。</span><span class="sxs-lookup"><span data-stu-id="bcf28-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="bcf28-145">**疑わしいドメインペア**は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bcf28-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="bcf28-146">**信頼度の高いスプーフィング**: Microsoft 365 では、これらのドメインが疑わしいという強力な信号を受信しました。これは、履歴の送信パターンおよびドメインの評価スコアに基づいています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-146">**High-confidence spoof**: Microsoft 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="bcf28-147">Microsoft 365 では、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当である可能性が低いと確信しています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-147">Microsoft 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span>

   - <span data-ttu-id="bcf28-148">**やや信頼度**の高いスプーフィング: Microsoft 365 受信した中で、これらのドメインが疑わしいものとなっています。これは、過去の送信パターンとドメインの評価スコアに基づいています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-148">**Moderate confidence spoof**: Microsoft 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains.</span></span> <span data-ttu-id="bcf28-149">Office 365 は、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当であることを適度に確信しています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-149">Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="bcf28-150">このバケットは、信頼度の高いスプーフィングバケットよりも誤検知 (FPs) を含む可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-150">This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span>

   - <span data-ttu-id="bcf28-151">**非疑わしいドメインペア**( **rescued スプーフィング**[を含む](use-dkim-to-validate-outbound-email.md)): rescued スプーフィングは、明示的な認証チェックの失敗した[ドメインである](use-dmarc-to-validate-email.md)ことを示しています[が、暗黙的](how-office-365-uses-spf-to-prevent-spoofing.md)な電子メール認証チェック ([複合認証](email-validation-and-authentication.md#composite-authentication)) に合格しています。</span><span class="sxs-lookup"><span data-stu-id="bcf28-151">**Non-suspicious domain pairs** (includes **rescued spoof**): Rescued spoof are domains that have failed the explicit authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) but passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="bcf28-152">その結果、Microsoft 365 では、ユーザーの代わりにメールが rescued され、メッセージに対するスプーフィング対策アクションは行われませんでした。</span><span class="sxs-lookup"><span data-stu-id="bcf28-152">As a result, Microsoft 365 rescued the mail on your behalf and no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="bcf28-153">スプーフィングインテリジェンスの洞察から、疑わしいドメインペアに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="bcf28-153">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="bcf28-154">スプーフィングインテリジェンスの洞察で、いずれかのドメインペア (high、中、または rescued) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcf28-154">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="bcf28-155">[**スプーフィングインテリジェンスの洞察**] ページに、認証されていないメールを組織に送信している送信者の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-155">The **Spoof Intelligence insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization.</span></span> <span data-ttu-id="bcf28-156">このページの情報は、スプーフィングされたメッセージを承認するかどうかを判断したり、さらにアクションを実行する必要があるかどうかを判断するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-156">The information on this page helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span> <span data-ttu-id="bcf28-157">メッセージ数、スプーフィングが最後に検出された日付などによって、情報を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span> <span data-ttu-id="bcf28-158">(たとえば、[**メッセージ件数**] や [**最後に表示**] など) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcf28-158">(Click column headings, such as **Message count** or **Last seen**, for example.)</span></span>

2. <span data-ttu-id="bcf28-159">このテーブル内の項目を選択すると、そのドメインのペアに関する豊富な情報が含まれる詳細ウィンドウが表示されます。これには、これをキャッチした理由、ドメインの概要、送信者に関する WhoIs データ、および同じ送信者からのテナントに表示された類似の電子メールなどがあります。</span><span class="sxs-lookup"><span data-stu-id="bcf28-159">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender.</span></span> <span data-ttu-id="bcf28-160">ここから、ドメインペアを**Allowedtospoof** safe sender リストから追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-160">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![スプーフィングインテリジェンスの詳細情報ウィンドウにあるドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="bcf28-162">AllowedToSpoof safe 送信者リストにドメインを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="bcf28-162">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="bcf28-163">ドメインを AllowedToSpoof safe sender リストから追加または削除すると、スプーフィングインテリジェンスの洞察の詳細ウィンドウでドメインペアを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-163">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight.</span></span> <span data-ttu-id="bcf28-164">それに応じてトグルを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="bcf28-164">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="bcf28-165">これにより、偽装されたドメインと送信元インフラストラクチャの一意のドメインペアの組み合わせが変更されます。また、分離されたドメインまたは送信元のインフラストラクチャ全体についても対応しません。</span><span class="sxs-lookup"><span data-stu-id="bcf28-165">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation.</span></span>

<span data-ttu-id="bcf28-166">たとえば、次のドメインの組を ' AllowedToSpoof ' 送信者の許可一覧に追加すると、*偽装ドメイン*"gmail.com" と、インフラストラクチャ " *Mx.com"* を*送信*します。そのドメインペアからのメールのみがスプーフィングに許可されます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-166">For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and *Sending Infrastructure* "tms *.mx.com",* then only mail from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="bcf28-167">"Gmail.com" のスプーフィングを試みる他の送信者、および "tms.mx.com" がスプーフィングしようとしている他のドメインは、スプーフィングインテリジェンスによって引き続き保護されます。</span><span class="sxs-lookup"><span data-stu-id="bcf28-167">Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcf28-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcf28-168">Related topics</span></span>

[<span data-ttu-id="bcf28-169">Microsoft 365 でのスプーフィング対策保護</span><span class="sxs-lookup"><span data-stu-id="bcf28-169">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="bcf28-170">チュートリアル - ダッシュボードからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="bcf28-170">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)

[<span data-ttu-id="bcf28-171">チュートリアル - 詳細レポートからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="bcf28-171">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)

[<span data-ttu-id="bcf28-172">チュートリアル - インサイトから詳細レポートへの移動</span><span class="sxs-lookup"><span data-stu-id="bcf28-172">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)