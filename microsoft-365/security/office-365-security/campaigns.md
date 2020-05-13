---
title: ATP のキャンペーンビュー
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 5441c877dac70330bf1e5653983494be5b1b3293
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209597"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="5a185-103">ATP のキャンペーンビュー</span><span class="sxs-lookup"><span data-stu-id="5a185-103">Campaign Views in ATP</span></span>

<span data-ttu-id="5a185-104">キャンペーンビューは、セキュリティ & コンプライアンスセンターの高度な脅威保護 (ATP) の機能であり、サービスのフィッシング攻撃を識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="5a185-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="5a185-105">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a185-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="5a185-106">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="5a185-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="5a185-107">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="5a185-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="5a185-108">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="5a185-108">Show value to decision makers.</span></span>

<span data-ttu-id="5a185-109">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="5a185-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="5a185-110">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="5a185-110">What is a campaign?</span></span>

<span data-ttu-id="5a185-111">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="5a185-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="5a185-112">資格情報と会社のデータを盗む電子メール攻撃は、ビッグおよび lucrative 業界です。</span><span class="sxs-lookup"><span data-stu-id="5a185-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="5a185-113">攻撃を阻止するためのテクノロジが増加するにつれて、攻撃者はその方法を変更して、成功を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="5a185-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="5a185-114">Microsoft は、サービス全体にわたる大量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンを特定します。</span><span class="sxs-lookup"><span data-stu-id="5a185-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="5a185-115">いくつかの要因によって、攻撃の情報を分析し、分類します。</span><span class="sxs-lookup"><span data-stu-id="5a185-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="5a185-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5a185-116">For example:</span></span>

- <span data-ttu-id="5a185-117">**攻撃ソース**: ソース IP アドレスと送信者のメール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="5a185-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="5a185-118">**攻撃メッセージのプロパティ**: 攻撃メッセージのコンテンツ、スタイル、語調。</span><span class="sxs-lookup"><span data-stu-id="5a185-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="5a185-119">**攻撃の受信者**: 受信者のドメイン、受信者の職務 (管理者、役員など)、会社の種類 (大企業、中小企業、公的組織、民間組織など)、業界。</span><span class="sxs-lookup"><span data-stu-id="5a185-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="5a185-120">**アタックペイロード**: 悪意のあるリンク、添付ファイル、または攻撃メッセージ内の他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="5a185-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="5a185-121">キャンペーンは、期間が短い場合や、複数の日、週、または月でアクティブで非アクティブな期間がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a185-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="5a185-122">特定の組織に対してキャンペーンが開始された場合や、組織が複数の企業にわたるより大きなキャンペーンの一部になっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a185-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="5a185-123">[キャンペーンビューセキュリティ & コンプライアンスセンター</span><span class="sxs-lookup"><span data-stu-id="5a185-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="5a185-124">[キャンペーンビューの[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、**脅威管理** \> **キャンペーン**で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5a185-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="5a185-126">次の方法でキャンペーンビューに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a185-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="5a185-127">**脅威の管理** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="5a185-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="5a185-128">**脅威の管理** \>**エクスプローラー** \>**表示** \>**すべての電子メール** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="5a185-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="5a185-129">キャンペーンのデータが何も表示されない場合は、日付範囲を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="5a185-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="5a185-130">概要ページには、次のキャンペーンの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="5a185-131">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-131">**Name**</span></span>

- <span data-ttu-id="5a185-132">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="5a185-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="5a185-133">キャンペーン内のすべてのメッセージには、必ずしも同じ件名が含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5a185-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="5a185-134">**型**: 現時点では、この値は常に**フィッシング**です。</span><span class="sxs-lookup"><span data-stu-id="5a185-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="5a185-135">[**Subtype (サブタイプ)**]: 提供される場合、このキャンペーンによるフィッシングの攻撃を受けているブランド。</span><span class="sxs-lookup"><span data-stu-id="5a185-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="5a185-136">ATP テクノロジによって検出が行われると、プレフィックス**atp-** がサブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="5a185-137">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="5a185-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="5a185-138">**Inboxed**: このキャンペーンからのメッセージを受信トレイで受信したユーザーの数 (迷惑メールに配信されません)。</span><span class="sxs-lookup"><span data-stu-id="5a185-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="5a185-139">**クリック**された: フィッシングメッセージの URL をクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="5a185-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="5a185-140">**[利率**] をクリックします **。 "**  /  **ボックスにボックス**化" をクリックして計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="5a185-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="5a185-141">この値は、キャンペーンの有効性を示す指標で、受信者がメッセージをフィッシングとして識別できたかどうかを示し、ペイロード URL をクリックすることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="5a185-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="5a185-142">**訪問**済み: ペイロード web サイトに実際にアクセスしたユーザー数。</span><span class="sxs-lookup"><span data-stu-id="5a185-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="5a185-143">[値] が**クリック**されているが、安全なリンクによって web サイトへのアクセスがブロックされている場合、この値は0になります。</span><span class="sxs-lookup"><span data-stu-id="5a185-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="5a185-144">キャンペーンの名前をクリックすると、キャンペーンの詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="5a185-145">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="5a185-145">Campaign details</span></span>

<span data-ttu-id="5a185-146">キャンペーンの詳細ビューでは、次のような、キャンペーンに関する多くの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="5a185-147">キャンペーン情報:</span><span class="sxs-lookup"><span data-stu-id="5a185-147">Campaign information:</span></span>

  - <span data-ttu-id="5a185-148">**ID**: 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="5a185-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="5a185-149">[**Started (開始日)**] と [**Ended (終了日)]**: 選択した日付範囲のフィルター。</span><span class="sxs-lookup"><span data-stu-id="5a185-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="5a185-150">**影響**: 選択した日付範囲フィルターの次のデータがあります。</span><span class="sxs-lookup"><span data-stu-id="5a185-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="5a185-151">受信者の合計数。</span><span class="sxs-lookup"><span data-stu-id="5a185-151">The total number of recipients.</span></span>

    - <span data-ttu-id="5a185-152">"Inboxed" (つまり、受信トレイに配信され、迷惑メールではない) だったメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="5a185-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="5a185-153">フィッシングメッセージの URL ペイロードでユーザーがクリックした回数。</span><span class="sxs-lookup"><span data-stu-id="5a185-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="5a185-154">ハウ多くのユーザーが URL を訪れた。</span><span class="sxs-lookup"><span data-stu-id="5a185-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="5a185-155">キャンペーン活動のタイムライン: キャンペーンの開始日と終了日、および時間の経過に伴うメッセージの数量。</span><span class="sxs-lookup"><span data-stu-id="5a185-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="5a185-156">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="5a185-156">Campaign flow</span></span>

<span data-ttu-id="5a185-157">キャンペーンについての重要な説明は、[**Flow**] セクションの水平方向のフロー図 (_Sankey_ ダイアグラムと呼ばれます) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="5a185-158">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a185-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="5a185-160">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="5a185-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="5a185-161">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a185-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="5a185-162">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-162">**Sender IPs**</span></span>

- <span data-ttu-id="5a185-163">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-163">**Sender domains**</span></span>

- <span data-ttu-id="5a185-164">**Filter verdicts**: ここで指定する値は、「[スパム対策メッセージヘッダー](anti-spam-message-headers.md)」で説明されているように、使用可能なフィッシングおよびスパムフィルター verdicts に関連しています。</span><span class="sxs-lookup"><span data-stu-id="5a185-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="5a185-165">次の表では、使用可能な値について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a185-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="5a185-166">Value</span><span class="sxs-lookup"><span data-stu-id="5a185-166">Value</span></span>|<span data-ttu-id="5a185-167">スパムフィルターの verdict</span><span class="sxs-lookup"><span data-stu-id="5a185-167">Spam filter verdict</span></span>|<span data-ttu-id="5a185-168">説明</span><span class="sxs-lookup"><span data-stu-id="5a185-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="5a185-169">**可**</span><span class="sxs-lookup"><span data-stu-id="5a185-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="5a185-170">スパムフィルターで評価される前に、メッセージがスパムではないとマークされているか、またはスキップされたフィルター処理 (たとえば、メールフロールール (トランスポートルールとも呼ばれる))。</span><span class="sxs-lookup"><span data-stu-id="5a185-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="5a185-171">その他の理由により、メッセージはスパムフィルター処理をスキップしました (たとえば、送信者と受信者が同じ組織内にいるように見えます)。</span><span class="sxs-lookup"><span data-stu-id="5a185-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="5a185-172">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="5a185-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="5a185-173">スパムフィルターによって評価される前に、メッセージがスパムとしてマークされました (たとえば、メールフロールールによって)。</span><span class="sxs-lookup"><span data-stu-id="5a185-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="5a185-174">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="5a185-175">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="5a185-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="5a185-176">**検出されません**</span><span class="sxs-lookup"><span data-stu-id="5a185-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="5a185-177">メッセージがスパムフィルター処理によって迷惑メールではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="5a185-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="5a185-178">**時点**</span><span class="sxs-lookup"><span data-stu-id="5a185-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="5a185-179">メッセージは検疫から解放されたため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="5a185-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="5a185-180">**テナント許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5a185-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="5a185-181">スパム対策ポリシーの設定 (たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧に含まれています) のため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="5a185-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="5a185-182">**テナントブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="5a185-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="5a185-183">スパム対策ポリシーの設定 (たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧にあるなど) によって、スパムフィルター処理によってメッセージがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="5a185-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="5a185-184">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5a185-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="5a185-185">メッセージは、送信者が Outlook の差出人セーフリストに含まれていたため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="5a185-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="5a185-186">**ユーザーブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="5a185-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="5a185-187">このメッセージは、送信者が Outlook の受信拒否リストに含まれていたため、スパムフィルター処理によってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="5a185-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="5a185-188">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="5a185-188">**ZAP**</span></span>|<span data-ttu-id="5a185-189">該当なし</span><span class="sxs-lookup"><span data-stu-id="5a185-189">n/a</span></span>|<span data-ttu-id="5a185-190">[ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)は、スパム対策ポリシー設定 (迷惑メールフォルダーに移動または検疫済み) に従って、配信されたメッセージに対してアクションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="5a185-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="5a185-191"><sup>\*</sup>許可されたメッセージがサービスによってブロックされている可能性があるので、スパム対策ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a185-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="5a185-192"><sup>\*\*</sup>スパム対策ポリシーを確認してください。これらのメッセージは配信されないため、検疫される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a185-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="5a185-193">[**Delivery locations (配信場所)**]: 実際に受信者に (受信トレイまたは迷惑メールフォルダーに) 配信されたメッセージについては、メッセージに含まれるペイロード URL をユーザーがクリックしなかった場合でも調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a185-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="5a185-194">検疫されたメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a185-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="5a185-195">詳細については、「EOP での検疫された[電子メールメッセージ](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a185-195">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="5a185-196">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="5a185-196">**Deleted folder**</span></span>

  - <span data-ttu-id="5a185-197">**落下**</span><span class="sxs-lookup"><span data-stu-id="5a185-197">**Dropped**</span></span>

  - <span data-ttu-id="5a185-198">**外部**: 受信者はオンプレミスの電子メール組織に配置されています。</span><span class="sxs-lookup"><span data-stu-id="5a185-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="5a185-199">**失敗**</span><span class="sxs-lookup"><span data-stu-id="5a185-199">**Failed**</span></span>

  - <span data-ttu-id="5a185-200">**転送**</span><span class="sxs-lookup"><span data-stu-id="5a185-200">**Forwarded**</span></span>

  - <span data-ttu-id="5a185-201">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-201">**Inbox**</span></span>

  - <span data-ttu-id="5a185-202">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-202">**Junk folder**</span></span>

  - <span data-ttu-id="5a185-203">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-203">**Quarantine**</span></span>

  - <span data-ttu-id="5a185-204">**不明**</span><span class="sxs-lookup"><span data-stu-id="5a185-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="5a185-205">10個を超えるアイテムが含まれるすべてのレイヤーでは、上位10個のアイテムが表示され、残りのアイテムは**他のユーザー**にバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="5a185-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="5a185-206">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="5a185-206">URL clicks</span></span>

<span data-ttu-id="5a185-207">フィッシングメッセージが受信者 (受信トレイまたは迷惑メールフォルダー) に配信される場合、常に、ユーザーがペイロード URL をクリックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a185-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="5a185-208">配信されたメッセージの URL をクリックしても成功することはありませんが、最初にメールボックスにフィッシングメッセージが配信された理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a185-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="5a185-209">ユーザーがフィッシングメッセージ内のペイロード URL をクリックすると、アクションがキャンペーン詳細ビューのダイアグラムの [ **URL** ] 領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="5a185-210">**可**</span><span class="sxs-lookup"><span data-stu-id="5a185-210">**Allowed**</span></span>

- <span data-ttu-id="5a185-211">**Blockpage**: 受信者がペイロード URL をクリックしたが、悪意のある web サイトへのアクセスが組織内の[ATP Safe Links](atp-safe-links.md)ポリシーによってブロックされた。</span><span class="sxs-lookup"><span data-stu-id="5a185-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="5a185-212">**Blockpageoverride**: 受信者がメッセージ内のペイロード URL をクリックしました。 ATP Safe Links は停止しようとしましたが、そのブロックを上書きすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="5a185-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="5a185-213">「安全なリンク」[ポリシー](set-up-atp-safe-links-policies.md)を調査して、ユーザーが安全なリンク verdict を上書きし、悪意のある web サイトに進むことができる理由を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a185-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="5a185-214">**PendingDetonationPage**: ATP の安全な添付ファイルは、仮想コンピューター環境でペイロード URL を開いて、何が起きるかを確認する処理になります。</span><span class="sxs-lookup"><span data-stu-id="5a185-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="5a185-215">**PendingDetonationPageOverride**: 受信者は、ペイロード分析プロセスを上書きすることを許可され、結果を待たずに URL を開くことができました。</span><span class="sxs-lookup"><span data-stu-id="5a185-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="5a185-216">タブ</span><span class="sxs-lookup"><span data-stu-id="5a185-216">Tabs</span></span>

<span data-ttu-id="5a185-217">キャンペーンの詳細ビューには複数のタブがあり、キャンペーンを詳しく調査するためにこれらのタブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a185-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="5a185-218">**URL クリック**: ユーザーがフィッシングメッセージのペイロード URL をクリックしていない場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="5a185-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="5a185-219">ユーザーが URL をクリックできた場合は、次の値が入力されます。</span><span class="sxs-lookup"><span data-stu-id="5a185-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="5a185-220">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5a185-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="5a185-221">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5a185-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="5a185-222">[**Click Time (クリックの日時)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-222">**Click Time**</span></span>

  - <span data-ttu-id="5a185-223">[**Click Action (クリックの操作)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-223">**Click Action**</span></span>

- <span data-ttu-id="5a185-224">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-224">**Sender IPs**</span></span>

  - <span data-ttu-id="5a185-225">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5a185-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="5a185-226">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-226">**Total Count**</span></span>

  - <span data-ttu-id="5a185-227">[**Inboxed Count (受信トレイに配信されたメッセージ数)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="5a185-228">[**Blocked Count (ブロックされたメッセージ数)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-228">**Blocked Count**</span></span>

  - <span data-ttu-id="5a185-229">**Spf が渡さ**れました。送信者は[sender POLICY Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)によって認証されました。</span><span class="sxs-lookup"><span data-stu-id="5a185-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="5a185-230">SPF 検証に合格しない送信者が、送信者が認証されていないこと、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a185-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="5a185-231">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-231">**Senders**</span></span>

  - <span data-ttu-id="5a185-232">**Sender**: これは、SMTP MAIL FROM コマンドの実際の送信者アドレスです。これは、必ずしも、ユーザーが電子メールクライアントに表示する from: 電子メールアドレスであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="5a185-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="5a185-233">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-233">**Total Count**</span></span>

  - <span data-ttu-id="5a185-234">**ボックス (内側)**</span><span class="sxs-lookup"><span data-stu-id="5a185-234">**Inboxed**</span></span>

  - <span data-ttu-id="5a185-235">**ボックスなし**</span><span class="sxs-lookup"><span data-stu-id="5a185-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="5a185-236">**Dkim が渡さ**れました: 送信者はドメインキーで識別された[メール (dkim)](support-for-validation-of-dkim-signed-messages.md)によって認証されました。</span><span class="sxs-lookup"><span data-stu-id="5a185-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="5a185-237">DKIM validation に合格しない送信者は、送信者が認証されていないこと、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a185-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="5a185-238">**DMARC が渡さ**れました。送信者は、[ドメインベースのメッセージ認証、レポート、および準拠 (DMARC)](use-dmarc-to-validate-email.md)によって認証されています。</span><span class="sxs-lookup"><span data-stu-id="5a185-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="5a185-239">送信者が DMARC の検証に合格しない場合は、送信者が認証されていないか、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="5a185-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="5a185-240">[**Payloads (ペイロード)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-240">**Payloads**</span></span>

  - <span data-ttu-id="5a185-241">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5a185-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="5a185-242">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="5a185-242">**Total Count**</span></span>

<span data-ttu-id="5a185-243"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="5a185-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="5a185-244">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a185-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="5a185-245">ボタン</span><span class="sxs-lookup"><span data-stu-id="5a185-245">Buttons</span></span>

<span data-ttu-id="5a185-246">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="5a185-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="5a185-247">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="5a185-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="5a185-248">[検索] ボックス内の**メッセージ**:**キャンペーン ID**と**配信場所: 受信トレイ**を検索フィルターとして使用して、新しい脅威エクスプローラー検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="5a185-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
