---
title: Office 365 ATP のキャンペーン ビュー
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection のキャンペーン ビューについて説明します。
ms.openlocfilehash: 2d43b73a613ad6399a151a6bda39f236c7c913e8
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962762"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="fe91e-103">Office 365 ATP のキャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="fe91e-103">Campaign Views in Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="fe91e-104">このトピックで説明する機能は現在プレビュー中であるため、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe91e-104">The features described in this article are currently in preview and subject to change.</span></span>

<span data-ttu-id="fe91e-105">キャンペーン ビューは、サービスにおけるフィッシング攻撃を特定して分類する、Office 365 セキュリティ/コンプライアンス センターの Advanced Threat Protection (ATP) の機能です。</span><span class="sxs-lookup"><span data-stu-id="fe91e-105">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Office 365 Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="fe91e-106">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="fe91e-107">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="fe91e-107">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="fe91e-108">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="fe91e-108">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="fe91e-109">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="fe91e-109">Show value to decision makers.</span></span>

<span data-ttu-id="fe91e-110">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="fe91e-111">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="fe91e-111">What is a cursor?</span></span>

<span data-ttu-id="fe91e-112">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="fe91e-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="fe91e-113">今日、資格情報と企業データを盗み出すメールの攻撃は、収益性の高い大規模なビジネスとなりました。</span><span class="sxs-lookup"><span data-stu-id="fe91e-113">Today, email attacks that steal credentials and company data are a big and lucrative business.</span></span> <span data-ttu-id="fe91e-114">攻撃を阻止するための技術が向上すると、攻撃をする者は、効果的な攻撃を継続するために、攻撃方法を巧妙に変化させてきます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-114">As technologies increase in an effort to stop attacks, attackers are sophisticated enough to modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="fe91e-115">Microsoft では、世界中の Office 365 サービス全体におけるフィッシング詐欺対策、スパム対策、マルウェア対策に関する膨大な量のデータと経験を活かして、キャンペーンを特定します。</span><span class="sxs-lookup"><span data-stu-id="fe91e-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data and experience across the entire Office 365 service world-wide to identify campaigns.</span></span> <span data-ttu-id="fe91e-116">攻撃の情報は、いくつかの要素に基づいて分析、分類されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-116">The attack information is analyzed and classified according to several factors.</span></span> <span data-ttu-id="fe91e-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe91e-117">For example:</span></span>

- <span data-ttu-id="fe91e-118">**攻撃ソース**: ソース IP アドレスと送信者のメール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="fe91e-118">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="fe91e-119">**攻撃メッセージのプロパティ**: 攻撃メッセージのコンテンツ、スタイル、語調。</span><span class="sxs-lookup"><span data-stu-id="fe91e-119">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="fe91e-120">**攻撃の受信者**: 受信者のドメイン、受信者の職務 (管理者、役員など)、会社の種類 (大企業、中小企業、公的組織、民間組織など)、業界。</span><span class="sxs-lookup"><span data-stu-id="fe91e-120">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="fe91e-121">**攻撃ペイロード**: 悪意のあるリンク、添付ファイル、その他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="fe91e-121">**Attack payload**: Malicious links, attachments, or other payloads.</span></span>

## <a name="campaign-views-the-office-365-security--compliance-center"></a><span data-ttu-id="fe91e-122">Office 365 セキュリティ/コンプライアンス センターのキャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="fe91e-122">Reports in the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="fe91e-123">キャンペーン ビューは[セキュリティ/コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)から利用でき、次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="fe91e-123">Campaign Views is available in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) at the following locations:</span></span>

- <span data-ttu-id="fe91e-124">[**脅威の管理**] \> [**エクスプローラー**] \> [**表示**] \> [**フィッシング**] \> [**Top Campaign (Preview) (上位のキャンペーン (プレビュー)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-124">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Top campaign (Preview)**</span></span>

- <span data-ttu-id="fe91e-125">[**脅威の管理**] \> [**エクスプローラー**] \> [**表示**] \> [**すべてのメール**] \> [**Top Campaign (Preview) (上位のキャンペーン (プレビュー)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-125">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Top campaign (Preview)**</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../media/campaigns-overview.png)

> [!TIP]
> <span data-ttu-id="fe91e-127">現在、利用可能なフィルター処理は、日付範囲のみです。</span><span class="sxs-lookup"><span data-stu-id="fe91e-127">Currently, the only filtering that's available is the date range.</span></span> <span data-ttu-id="fe91e-128">キャンペーンのデータが何も表示されない場合は、日付範囲を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="fe91e-128">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="fe91e-129">概要ページには、次のキャンペーンの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-129">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="fe91e-130">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-130">**Name**</span></span>

- <span data-ttu-id="fe91e-131">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="fe91e-131">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="fe91e-132">キャンペーン内の_すべて_のメッセージの件名がこの件名と同じとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fe91e-132">Note that _all_ the messages in the campaign will not necessarily have this same subject line.</span></span>

- <span data-ttu-id="fe91e-133">[**Type (タイプ)**]: 現在、この値は [**Phish (フィッシング)**] に固定されています。</span><span class="sxs-lookup"><span data-stu-id="fe91e-133">**Type**: Currently, this value will always be **Phish**.</span></span>

- <span data-ttu-id="fe91e-134">[**Subtype (サブタイプ)**]: 提供される場合、このキャンペーンによるフィッシングの攻撃を受けているブランド。</span><span class="sxs-lookup"><span data-stu-id="fe91e-134">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="fe91e-135">ATP テクノロジによる検出の場合、プレフィックス "**ATP-**" が subtype 値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-135">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="fe91e-136">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="fe91e-136">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="fe91e-137">[**Delivered (配信済み)**]: このキャンペーンからのメッセージを受信トレイで受信したユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="fe91e-137">**Delivered**: The number of users that received messages from this campaign into their Inbox.</span></span>

- <span data-ttu-id="fe91e-138">[**ID**]: キャンペーンの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="fe91e-138">**ID**: A unique identifier for the campaign.</span></span>

<span data-ttu-id="fe91e-139">キャンペーンの名前をクリックすると、キャンペーンの詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-139">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="fe91e-140">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="fe91e-140">Campaign details</span></span>

<span data-ttu-id="fe91e-141">キャンペーンの詳細ビューでは、次のような、キャンペーンに関する多くの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-141">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="fe91e-142">キャンペーン情報:</span><span class="sxs-lookup"><span data-stu-id="fe91e-142">Campaign information:</span></span>

  - <span data-ttu-id="fe91e-143">[**ID**]: 概要画面にあるものと同じ、キャンペーンの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="fe91e-143">**ID**: The same unique identifier of the campaign from the overview screen.</span></span>

  - <span data-ttu-id="fe91e-144">[**Started (開始日)**] と [**Ended (終了日)]**: 選択した日付範囲のフィルター。</span><span class="sxs-lookup"><span data-stu-id="fe91e-144">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="fe91e-145">[**Impact (影響)**]: 選択した日付範囲内に送信されたメッセージの数、受信トレイに配信されたメッセージ数、およびフィッシング メッセージの URL ペイロードをクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="fe91e-145">**Impact**: the number of messages sent in the date range you selected, how many were "inboxed" (that is, delivered to the Inbox), and how many users clicked on the URL payload in the phishing message.</span></span>

  - <span data-ttu-id="fe91e-146">キャンペーン活動のタイムライン: キャンペーンの開始日と終了日、および時間の経過に伴うメッセージの数量。</span><span class="sxs-lookup"><span data-stu-id="fe91e-146">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="fe91e-147">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="fe91e-147">Campaign flow</span></span>

<span data-ttu-id="fe91e-148">キャンペーンについての重要な説明は、[**Flow**] セクションの水平方向のフロー図 (_Sankey_ ダイアグラムと呼ばれます) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-148">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="fe91e-149">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-149">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="fe91e-151">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="fe91e-151">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="fe91e-152">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-152">The entry contains the following information:</span></span>

- <span data-ttu-id="fe91e-153">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-153">**Sender IPs**</span></span>

- <span data-ttu-id="fe91e-154">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-154">**Sender domains**</span></span>

- <span data-ttu-id="fe91e-155">[**Filter verdicts (フィルターの判定)**]: [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)に記載される使用可能なフィッシング詐欺対策とスパム対策フィルターの判定に関連する値。</span><span class="sxs-lookup"><span data-stu-id="fe91e-155">**Filter verdicts**: The values here are related to the available anti-phishing and anti-spam filter verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="fe91e-156">[**Tenant Allow (テナントによる許可)**] の値に注目します。組織での構成設定により配信が許可されたメッセージのうち、本来はサービスによりブロックされたはずのメッセージのことを指します(例: [Allowed Senders (許可された送信者)] リストに含まれるドメイン)。</span><span class="sxs-lookup"><span data-stu-id="fe91e-156">Of great interest here are the values **Tenant Allow**, which means a configured setting in the organization allowed a message through that would have been otherwise blocked by the service (for example, a domain in the Allowed Senders list).</span></span>

  - <span data-ttu-id="fe91e-157">[**Tenant Block (テナントによるブロック)**]: この値は、組織の設定 (例: [[Blocked Senders list (受信拒否リスト)](create-block-sender-lists-in-office-365.md)] に含まれるドメイン エントリ) によりメッセージの検出と配信された場所の特定の両方が実行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fe91e-157">**Tenant Block**: This value indicates that a setting in your organization (for example, a domain entry in the [Blocked Senders list](create-block-sender-lists-in-office-365.md)) both detected the message and determined where it was delivered.</span></span> <span data-ttu-id="fe91e-158">検疫されなかったメッセージについては、受信拒否の設定を確認し、メッセージが配信された理由を特定します。</span><span class="sxs-lookup"><span data-stu-id="fe91e-158">For messages that weren't quarantined, review your blocked senders settings to determine why the message was delivered.</span></span>

  - <span data-ttu-id="fe91e-159">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-159">**Detected app**</span></span>

  - <span data-ttu-id="fe91e-160">[**Tenant Allow (テナントによる許可)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-160">**Tenant Allow**</span></span>

- <span data-ttu-id="fe91e-161">[**Delivery locations (配信場所)**]: 実際に受信者に (受信トレイまたは迷惑メールフォルダーに) 配信されたメッセージについては、メッセージに含まれるペイロード URL をユーザーがクリックしなかった場合でも調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe91e-161">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="fe91e-162">また、検疫されたメッセージは、[Office 365 で検疫されたメッセージ](quarantine-email-messages.md)から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-162">You can also remove the quarantined messages from [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="fe91e-163">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-163">**Junk folder**</span></span>

  - <span data-ttu-id="fe91e-164">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-164">**Quarantine**</span></span>

  - <span data-ttu-id="fe91e-165">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-165">**Inbox**</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="fe91e-166">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="fe91e-166">URL clicks</span></span>

<span data-ttu-id="fe91e-167">受信者の受信トレイまたは迷惑メールフォルダーに送信されたメッセージをユーザーが操作してしまう (つまり、メッセージ内の悪意のある URL をユーザーがクリックしてしまう) 危険はいつでもあります。</span><span class="sxs-lookup"><span data-stu-id="fe91e-167">There's always the chance that messages delivered to the recipient's Inbox or Junk Email folder can be acted upon by the user (that is, user will click on the malicious URL in the message).</span></span> <span data-ttu-id="fe91e-168">ユーザーがクリックしなかった場合はもちろん喜ばしいことですが、有害なメッセージがメールボックスに配信されたそもそもの理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe91e-168">If they haven't, that's a small measure of success, although you certainly need to determine why the harmful message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="fe91e-169">悪意のある URL をユーザーがクリックした場合、その操作は図の [**URL clicks (URL のクリック)**] 領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-169">If a user has clicked on the malicious URL, the actions are displayed in the **URL clicks** area of the diagram.</span></span>

![ユーザーの URL クリックを示すキャンペーンの詳細](../media/campaign-details-with-recipient-actions.png)

- <span data-ttu-id="fe91e-171">[**Safe Links Block (安全なリンクによるブロック)**]: この値は、メッセージ内のペイロード URL を受信者がクリックしたものの、組織の [ATP の安全なリンク](atp-safe-links.md) ポリシーにより操作がブロックされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fe91e-171">**Safe Links Block**: This value indicates the recipient clicked on the payload URL in the message, but it was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="fe91e-172">**Safe Links Block Override (安全なリンクによるブロックの無視)**: この値もまた、メッセージ内のペイロード URL を受信者がクリックし、ATP の安全なリンクにより操作の中止が試行されたことを示しますが、操作がブロックを無視することができたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fe91e-172">**Safe Links Block Override**: This value also indicates the recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="fe91e-173">[安全なリンクのポリシー](set-up-atp-safe-links-policies.md) を調査し、ユーザーが安全なリンクの判定を無視して悪意のある URL をクリックすることができた理由を突き止める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe91e-173">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and click on malicious URLs.</span></span>

### <a name="tabs"></a><span data-ttu-id="fe91e-174">タブ</span><span class="sxs-lookup"><span data-stu-id="fe91e-174">Tabs</span></span>

<span data-ttu-id="fe91e-175">キャンペーンの詳細ビューには複数のタブがあり、キャンペーンを詳しく調査するためにこれらのタブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-175">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="fe91e-176">[**URL Clicks**]: フィッシング メッセージのペイロード URL がクリックされなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="fe91e-176">**URL Clicks**: If the payload URL in the phishing message wasn't clicked, this section will be blank.</span></span> <span data-ttu-id="fe91e-177">ユーザーが URL をクリックできた場合は、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-177">If a user was able to click on the URL, you</span></span>

  - <span data-ttu-id="fe91e-178">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fe91e-178">User</span></span>

  - <span data-ttu-id="fe91e-179">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fe91e-179">URL</span></span>

  - <span data-ttu-id="fe91e-180">[**Click Time (クリックの日時)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-180">**Click Time**</span></span>

  - <span data-ttu-id="fe91e-181">[**Click Action (クリックの操作)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-181">Click **Action**.</span></span>

- <span data-ttu-id="fe91e-182">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-182">**Sender IPs**</span></span>

  - <span data-ttu-id="fe91e-183">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fe91e-183">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="fe91e-184">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-184">**Total count**</span></span>

  - <span data-ttu-id="fe91e-185">[**Inboxed Count (受信トレイに配信されたメッセージ数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-185">**Inboxed Count**</span></span>

  - <span data-ttu-id="fe91e-186">[**Blocked Count (ブロックされたメッセージ数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-186">**Blocked Count**</span></span>

  - <span data-ttu-id="fe91e-187">[**SPF Passed (SPF 合格)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-187">**SPF Passed**</span></span>

- <span data-ttu-id="fe91e-188">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-188">**Senders**</span></span>

  - <span data-ttu-id="fe91e-189">[**Sender (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-189">**Sender**</span></span>

  - <span data-ttu-id="fe91e-190">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-190">**Total count**</span></span>

  - <span data-ttu-id="fe91e-191">[**Inboxed Count (受信トレイに配信されたメッセージ数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-191">**Inboxed Count**</span></span>

  - <span data-ttu-id="fe91e-192">[**Blocked Count (ブロックされたメッセージ数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-192">**Blocked Count**</span></span>

  - <span data-ttu-id="fe91e-193">[**DKIM Passed (DKIM 合格)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-193">**DKIM Passed**</span></span>

  - <span data-ttu-id="fe91e-194">[**DMARC Passed (DMARC 合格)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-194">**DMARC Passed**</span></span>

- <span data-ttu-id="fe91e-195">[**Payloads (ペイロード)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-195">**Payloads**</span></span>

  - <span data-ttu-id="fe91e-196">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fe91e-196">URL</span></span>

  - <span data-ttu-id="fe91e-197">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="fe91e-197">**Total count**</span></span>

<span data-ttu-id="fe91e-198"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-198"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="fe91e-199">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe91e-199">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="fe91e-200">ボタン</span><span class="sxs-lookup"><span data-stu-id="fe91e-200">Buttons</span></span>

<span data-ttu-id="fe91e-201">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-201">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="fe91e-202">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-202">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="fe91e-203">[**Explore Inbox messages (受信トレイのメッセージを調査)**]: **Campaign ID (キャンペーンの ID)** および **Delivery location: Inbox (配信場所: 受信トレイ)** を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="fe91e-203">**Explore Inbox messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
