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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039479"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="df03c-103">ATP のキャンペーンビュー</span><span class="sxs-lookup"><span data-stu-id="df03c-103">Campaign Views in ATP</span></span>

<span data-ttu-id="df03c-104">キャンペーンビューは、セキュリティ & コンプライアンスセンターの高度な脅威保護 (ATP) の機能であり、サービスのフィッシング攻撃を識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="df03c-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="df03c-105">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="df03c-106">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="df03c-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="df03c-107">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="df03c-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="df03c-108">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="df03c-108">Show value to decision makers.</span></span>

<span data-ttu-id="df03c-109">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="df03c-110">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="df03c-110">What is a campaign?</span></span>

<span data-ttu-id="df03c-111">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="df03c-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="df03c-112">資格情報と会社のデータを盗む電子メール攻撃は、ビッグおよび lucrative 業界です。</span><span class="sxs-lookup"><span data-stu-id="df03c-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="df03c-113">攻撃を阻止するためのテクノロジが増加するにつれて、攻撃者はその方法を変更して、成功を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="df03c-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="df03c-114">Microsoft は、サービス全体にわたる大量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンを特定します。</span><span class="sxs-lookup"><span data-stu-id="df03c-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="df03c-115">いくつかの要因によって、攻撃の情報を分析し、分類します。</span><span class="sxs-lookup"><span data-stu-id="df03c-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="df03c-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-116">For example:</span></span>

- <span data-ttu-id="df03c-117">[**アタックソース**]: 送信元 IP アドレスと送信者の電子メールドメイン。</span><span class="sxs-lookup"><span data-stu-id="df03c-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="df03c-118">**アタックメッセージのプロパティ**: メッセージのコンテンツ、スタイル、および雰囲気。</span><span class="sxs-lookup"><span data-stu-id="df03c-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="df03c-119">**攻撃の受信者**: 受信者のドメイン、受信者の職務 (管理者、役員など)、会社の種類 (大企業、中小企業、公的組織、民間組織など)、業界。</span><span class="sxs-lookup"><span data-stu-id="df03c-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="df03c-120">**アタックペイロード**: 悪意のあるリンク、添付ファイル、またはメッセージ内の他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="df03c-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="df03c-121">キャンペーンは、期間が短い場合や、複数の日、週、または月でアクティブで非アクティブな期間がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="df03c-122">特定の組織に対してキャンペーンが開始された場合や、組織が複数の企業にわたるより大きなキャンペーンの一部になっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="df03c-123">[キャンペーンビューセキュリティ & コンプライアンスセンター</span><span class="sxs-lookup"><span data-stu-id="df03c-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="df03c-124">キャンペーンビューは、[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [**脅威管理** \> ]**キャンペーン**で、またはに直接アクセスでき <https://protection.office.com/campaigns> ます。</span><span class="sxs-lookup"><span data-stu-id="df03c-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="df03c-126">次の方法でキャンペーンビューにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="df03c-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="df03c-127">**脅威の管理** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="df03c-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="df03c-128">**脅威の管理** \>**エクスプローラー** \>**表示** \>**すべての電子メール** \>[**キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="df03c-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="df03c-129">**脅威の管理** \>**エクスプローラー** \>**表示** \>**フィッシング** \>[**キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="df03c-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="df03c-130">**脅威の管理** \>**エクスプローラー** \>**表示** \>**マルウェア** \>[**キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="df03c-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="df03c-131">[キャンペーン] ビューにアクセスするには、セキュリティ & コンプライアンスセンターで、[**組織の管理**]、[**セキュリティ管理者**]、または [**セキュリティリーダー** ] の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="df03c-132">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="df03c-133">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="df03c-133">Campaigns overview</span></span>

<span data-ttu-id="df03c-134">概要ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="df03c-135">[既定の**キャンペーン**] タブの [**キャンペーンの種類**] 領域には、1日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="df03c-136">既定では、グラフには**フィッシング**と**マルウェア**のデータの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="df03c-137">キャンペーンデータが表示されない場合は、日付範囲または[フィルター](#filters-and-settings)を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="df03c-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="df03c-138">その他の概要ページには、[**キャンペーン**] タブに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="df03c-139">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-139">**Name**</span></span>

- <span data-ttu-id="df03c-140">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="df03c-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="df03c-141">キャンペーン内のすべてのメッセージには、必ずしも同じ件名が含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="df03c-142">**対象**: ([組織内のキャンペーン受信者の数])/(サービス内のすべての組織にわたるキャンペーンの受信者の合計数) の計算結果の割合。</span><span class="sxs-lookup"><span data-stu-id="df03c-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="df03c-143">この値は、キャンペーンが明示的に組織に向けられている程度を示します (高い値)。または、サービス内の他の組織 (低い値) に対して指示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="df03c-144">**型**: この値は、**フィッシング**または**マルウェア**です。</span><span class="sxs-lookup"><span data-stu-id="df03c-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="df03c-145">**Subtype**: この値には、キャンペーンの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df03c-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="df03c-146">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-146">For example:</span></span>

  - <span data-ttu-id="df03c-147">**フィッシング**: 使用可能な場合は、このキャンペーンによって phished されているブランド。</span><span class="sxs-lookup"><span data-stu-id="df03c-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="df03c-148">たとえば、、、、、 `Microsoft` `365` 、など `Unknown` `Outlook` `DocuSign` です。</span><span class="sxs-lookup"><span data-stu-id="df03c-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="df03c-149">**マルウェア**: たとえば、 `HTML/PHISH` またはのように `HTML/<MalwareFamilyName>` なります。</span><span class="sxs-lookup"><span data-stu-id="df03c-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="df03c-150">利用可能な場合、このキャンペーンで phished されているブランド。</span><span class="sxs-lookup"><span data-stu-id="df03c-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="df03c-151">ATP テクノロジによって検出が行われると、プレフィックス**atp-** がサブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="df03c-152">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="df03c-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="df03c-153">**Inboxed**: このキャンペーンからのメッセージを受信トレイで受信したユーザーの数 (迷惑メールフォルダーに配信されません)。</span><span class="sxs-lookup"><span data-stu-id="df03c-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="df03c-154">**クリック**した場合: URL をクリックしたユーザーの数、またはフィッシングメッセージで添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="df03c-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="df03c-155">**[利率**] をクリックします **。 "**  /  **ボックスにボックス**化" をクリックして計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="df03c-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="df03c-156">この値は、キャンペーンの有効性を示す指標で、受信者がメッセージをフィッシングとして識別できたかどうかを示し、ペイロード URL をクリックすることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="df03c-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="df03c-157">この値は、マルウェアキャンペーンでは使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="df03c-158">**訪問**済み: ペイロード web サイトに実際にアクセスしたユーザー数。</span><span class="sxs-lookup"><span data-stu-id="df03c-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="df03c-159">[値] が**クリック**されているが、安全なリンクによって web サイトへのアクセスがブロックされている場合、この値は0になります。</span><span class="sxs-lookup"><span data-stu-id="df03c-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="df03c-160">[**キャンペーン送信元**] タブには、世界の地図上のメッセージソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="df03c-161">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="df03c-161">Filters and settings</span></span>

<span data-ttu-id="df03c-162">[キャンペーンビュー] ページの上部には、フィルターとクエリの設定がいくつか用意されているため、特定のキャンペーンを検索して分離することができます。</span><span class="sxs-lookup"><span data-stu-id="df03c-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーンフィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="df03c-164">最も基本的なフィルターは、開始日/時刻と終了日/時刻です。</span><span class="sxs-lookup"><span data-stu-id="df03c-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="df03c-165">ビューをさらにフィルター処理するには、[**キャンペーンの種類**] ボタンをクリックして、選択を行い、[最新の情報に**更新**] をクリックすることで、複数の値を設定した単一のプロパティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="df03c-166">次の一覧では、使用可能なキャンペーンプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df03c-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="df03c-167">基本</span><span class="sxs-lookup"><span data-stu-id="df03c-167">Basic</span></span>

  - <span data-ttu-id="df03c-168">**キャンペーンの種類**:**マルウェア**または**フィッシング**を選択します。</span><span class="sxs-lookup"><span data-stu-id="df03c-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="df03c-169">選択範囲をクリアすると、両方を選択したときと同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="df03c-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="df03c-170">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="df03c-170">**Campaign name**</span></span>
  - <span data-ttu-id="df03c-171">**キャンペーンサブタイプ**</span><span class="sxs-lookup"><span data-stu-id="df03c-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="df03c-172">**送信者**</span><span class="sxs-lookup"><span data-stu-id="df03c-172">**Sender**</span></span>
  - <span data-ttu-id="df03c-173">**受信者**</span><span class="sxs-lookup"><span data-stu-id="df03c-173">**Recipients**</span></span>
  - <span data-ttu-id="df03c-174">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="df03c-174">**Sender domain**</span></span>
  - <span data-ttu-id="df03c-175">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="df03c-175">**Subject**</span></span>
  - <span data-ttu-id="df03c-176">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="df03c-176">**Attachment filename**</span></span>
  - <span data-ttu-id="df03c-177">**マルウェアファミリ**</span><span class="sxs-lookup"><span data-stu-id="df03c-177">**Malware family**</span></span>
  - <span data-ttu-id="df03c-178">**配信アクション**</span><span class="sxs-lookup"><span data-stu-id="df03c-178">**Delivery action**</span></span>
  - <span data-ttu-id="df03c-179">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="df03c-179">**Detection technology**</span></span>
  - <span data-ttu-id="df03c-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="df03c-180">**Tags**</span></span>
  - <span data-ttu-id="df03c-181">**システムの上書き**</span><span class="sxs-lookup"><span data-stu-id="df03c-181">**System overrides**</span></span>

- <span data-ttu-id="df03c-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="df03c-182">Advanced</span></span>

  - <span data-ttu-id="df03c-183">**インターネットメッセージ id**: メッセージヘッダーの**メッセージ id**ヘッダーフィールドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="df03c-184">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="df03c-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="df03c-185">[**ネットワークメッセージ id**]: メッセージヘッダーの [-- **Exchange 組織-ネットワークメッセージ id** ] ヘッダーフィールドで使用可能な GUID 値。</span><span class="sxs-lookup"><span data-stu-id="df03c-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="df03c-186">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="df03c-187">**ATTACHMENT SHA256**: Windows でファイルの SHA256 ハッシュ値を検索するには、コマンドプロンプトで次のコマンドを実行 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` します。</span><span class="sxs-lookup"><span data-stu-id="df03c-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="df03c-188">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="df03c-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="df03c-189">**アラートポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="df03c-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="df03c-190">URL</span><span class="sxs-lookup"><span data-stu-id="df03c-190">URLs</span></span>

  - <span data-ttu-id="df03c-191">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="df03c-191">**URL domain**</span></span>
  - <span data-ttu-id="df03c-192">**URL のドメインとパス**</span><span class="sxs-lookup"><span data-stu-id="df03c-192">**URL domain and path**</span></span>
  - <span data-ttu-id="df03c-193">\*\* URL \*\*</span><span class="sxs-lookup"><span data-stu-id="df03c-193">**URL**</span></span>
  - <span data-ttu-id="df03c-194">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="df03c-194">**URL path**</span></span>
  - <span data-ttu-id="df03c-195">**[Verdict] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="df03c-195">**Click verdict**</span></span>

<span data-ttu-id="df03c-196">複数のプロパティによるフィルター処理を含む、高度なフィルター処理を行うには、[**フィルターの詳細設定**] ボタンをクリックしてクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="df03c-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="df03c-197">同じキャンペーンプロパティを使用できますが、以下の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="df03c-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="df03c-198">[**条件の追加**] をクリックすると、複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="df03c-199">**And**また**は or**演算子は、条件間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="df03c-200">[条件] ボックスの一覧の下部にある [**条件] グループ**項目を選択して、複雑な複合条件を形成できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="df03c-201">完了したら、[**クエリ**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df03c-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="df03c-202">基本フィルターまたは詳細フィルターを作成した後で、[**クエリの保存**] または [**クエリ**に名前を付けて保存] を使用して保存できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="df03c-203">後でキャンペーンビューに戻るときに、保存したフィルターを読み込むには、[**保存さ**れたクエリの設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df03c-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="df03c-204">グラフまたはキャンペーンの一覧をエクスポートするには、[**エクスポート**] をクリックし、[**グラフデータのエクスポート**] または [**キャンペーンリストのエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df03c-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="df03c-205">Microsoft Defender ATP サブスクリプションをお持ちの場合は、[ **Wdatp** ] をクリックして、MICROSOFT defender atp を使用してキャンペーン情報を接続または切断することができます。</span><span class="sxs-lookup"><span data-stu-id="df03c-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="df03c-206">詳細については、「 [Microsoft DEFENDER atp で Office 365 ATP を統合](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="df03c-207">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="df03c-207">Campaign details</span></span>

<span data-ttu-id="df03c-208">キャンペーンの名前をクリックすると、そのキャンペーンの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="df03c-209">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="df03c-209">Campaign information</span></span>

<span data-ttu-id="df03c-210">キャンペーンの詳細ビューの一番上に、次のキャンペーン情報があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="df03c-211">**ID**: 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="df03c-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="df03c-212">[**開始**および**終了**]: キャンペーンの開始日と終了日。</span><span class="sxs-lookup"><span data-stu-id="df03c-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="df03c-213">これらの日付は、[概要] ページで選択したフィルター日付よりも長く延長される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="df03c-214">**影響**: このセクションには、選択した日付範囲フィルター (またはタイムラインで選択する) について、次のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df03c-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="df03c-215">受信者の合計数。</span><span class="sxs-lookup"><span data-stu-id="df03c-215">The total number of recipients.</span></span>
  - <span data-ttu-id="df03c-216">"Inboxed" (つまり、受信トレイに配信され、迷惑メールフォルダーに配信されなかったメッセージ) の数。</span><span class="sxs-lookup"><span data-stu-id="df03c-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="df03c-217">フィッシングメッセージの URL ペイロードでユーザーがクリックした回数。</span><span class="sxs-lookup"><span data-stu-id="df03c-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="df03c-218">ハウ多くのユーザーが URL を訪れた。</span><span class="sxs-lookup"><span data-stu-id="df03c-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="df03c-219">**対象**: ([組織内のキャンペーン受信者の数])/(サービス内のすべての組織にわたるキャンペーンの受信者の合計数) の計算結果の割合。</span><span class="sxs-lookup"><span data-stu-id="df03c-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="df03c-220">この値は、キャンペーンのすべての期間にわたって計算されるため、フィルター日付を変更しません。</span><span class="sxs-lookup"><span data-stu-id="df03c-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="df03c-221">対話的なキャンペーンアクティビティのタイムライン: タイムラインは、キャンペーンの有効期間全体にわたるアクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="df03c-222">既定では、影付き領域には概要で選択した日付範囲フィルターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df03c-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="df03c-223">次のセクションで説明されているように、をクリックしてドラッグすると、特定の開始点と終了点を選択し<u>て、**影響**領域に表示されるデータとその他のページの残りの部分</u>を選択できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="df03c-224">タイトルバーで [キャンペーンの**作成**] ボタンをクリックすると、キャンペーンの ![ 詳細が ](../../media/download-campaign-write-up-button.png) Word 文書 (既定では、CampaignReport.docx) にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="df03c-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="df03c-225">このドキュメントには、(選択したフィルター日付だけでなく) キャンペーンの有効期間全体に関する詳細が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="df03c-227">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="df03c-227">Campaign flow</span></span>

<span data-ttu-id="df03c-228">キャンペーン詳細ビューの中央に、キャンペーンに関する重要な詳細が、水平方向のフロー図 ( _Sankey_図) の [ **flow** ] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="df03c-229">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df03c-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="df03c-230">**フロー**図に表示される情報は、前のセクションで説明したように、タイムラインの網かけの日付範囲によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="df03c-232">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="df03c-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="df03c-233">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df03c-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="df03c-234">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-234">**Sender IPs**</span></span>

- <span data-ttu-id="df03c-235">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-235">**Sender domains**</span></span>

- <span data-ttu-id="df03c-236">**Filter verdicts**: これらの値は、「[スパム対策メッセージヘッダー](anti-spam-message-headers.md)」で説明されているように、使用可能なフィッシングおよびスパムフィルター verdicts に関連しています。</span><span class="sxs-lookup"><span data-stu-id="df03c-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="df03c-237">次の表では、使用可能な値について説明します。</span><span class="sxs-lookup"><span data-stu-id="df03c-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="df03c-238">**値**</span><span class="sxs-lookup"><span data-stu-id="df03c-238">**Value**</span></span>|<span data-ttu-id="df03c-239">**スパムフィルターの verdict**</span><span class="sxs-lookup"><span data-stu-id="df03c-239">**Spam filter verdict**</span></span>|<span data-ttu-id="df03c-240">**説明**</span><span class="sxs-lookup"><span data-stu-id="df03c-240">**Description**</span></span>|
  |<span data-ttu-id="df03c-241">**可**</span><span class="sxs-lookup"><span data-stu-id="df03c-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="df03c-242">スパムフィルターで評価される前に、メッセージがスパムではないとマークされているか、またはスキップされたフィルター処理 (たとえば、メールフロールール (トランスポートルールとも呼ばれる))。</span><span class="sxs-lookup"><span data-stu-id="df03c-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="df03c-243">その他の理由により、メッセージはスパムフィルター処理をスキップしました (たとえば、送信者と受信者が同じ組織内にいるように見えます)。</span><span class="sxs-lookup"><span data-stu-id="df03c-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="df03c-244">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="df03c-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="df03c-245">スパムフィルターによって評価される前に、メッセージがスパムとしてマークされました (たとえば、メールフロールールによって)。</span><span class="sxs-lookup"><span data-stu-id="df03c-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="df03c-246">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="df03c-247">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="df03c-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="df03c-248">**検出されません**</span><span class="sxs-lookup"><span data-stu-id="df03c-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="df03c-249">メッセージがスパムフィルター処理によって迷惑メールではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="df03c-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="df03c-250">**時点**</span><span class="sxs-lookup"><span data-stu-id="df03c-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="df03c-251">メッセージは検疫から解放されたため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="df03c-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="df03c-252">**テナント許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="df03c-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="df03c-253">スパム対策ポリシーの設定 (たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧に含まれています) のため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="df03c-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="df03c-254">**テナントブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="df03c-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="df03c-255">スパム対策ポリシーの設定 (たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧にあるなど) によって、スパムフィルター処理によってメッセージがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="df03c-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="df03c-256">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="df03c-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="df03c-257">メッセージは、送信者が Outlook の差出人セーフリストに含まれていたため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="df03c-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="df03c-258">**ユーザーブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="df03c-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="df03c-259">このメッセージは、送信者が Outlook の受信拒否リストに含まれていたため、スパムフィルター処理によってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="df03c-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="df03c-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="df03c-260">**ZAP**</span></span>|<span data-ttu-id="df03c-261">該当なし</span><span class="sxs-lookup"><span data-stu-id="df03c-261">n/a</span></span>|<span data-ttu-id="df03c-262">[ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)は、スパム対策ポリシー設定 (迷惑メールフォルダーに移動または検疫済み) に従って、配信されたメッセージに対してアクションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="df03c-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="df03c-263"><sup>\*</sup>許可されたメッセージがサービスによってブロックされている可能性があるので、スパム対策ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="df03c-264"><sup>\*\*</sup>スパム対策ポリシーを確認してください。これらのメッセージは配信されないため、検疫される必要があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="df03c-265">[**Delivery locations (配信場所)**]: 実際に受信者に (受信トレイまたは迷惑メールフォルダーに) 配信されたメッセージについては、メッセージに含まれるペイロード URL をユーザーがクリックしなかった場合でも調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df03c-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="df03c-266">検疫されたメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="df03c-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="df03c-267">詳細については、「EOP での検疫された[電子メールメッセージ](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df03c-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="df03c-268">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="df03c-268">**Deleted folder**</span></span>
  - <span data-ttu-id="df03c-269">**落下**</span><span class="sxs-lookup"><span data-stu-id="df03c-269">**Dropped**</span></span>
  - <span data-ttu-id="df03c-270">**外部**: 受信者は、ハイブリッド環境でオンプレミスの電子メール組織に配置されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="df03c-271">**失敗**</span><span class="sxs-lookup"><span data-stu-id="df03c-271">**Failed**</span></span>
  - <span data-ttu-id="df03c-272">**転送**</span><span class="sxs-lookup"><span data-stu-id="df03c-272">**Forwarded**</span></span>
  - <span data-ttu-id="df03c-273">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-273">**Inbox**</span></span>
  - <span data-ttu-id="df03c-274">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-274">**Junk folder**</span></span>
  - <span data-ttu-id="df03c-275">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-275">**Quarantine**</span></span>
  - <span data-ttu-id="df03c-276">**不明**</span><span class="sxs-lookup"><span data-stu-id="df03c-276">**Unknown**</span></span>

- <span data-ttu-id="df03c-277">**URL のクリック**: 次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="df03c-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="df03c-278">10個を超えるアイテムが含まれるすべてのレイヤーでは、上位10個のアイテムが表示され、残りのアイテムは**他のユーザー**にバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="df03c-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="df03c-279">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="df03c-279">URL clicks</span></span>

<span data-ttu-id="df03c-280">フィッシングメッセージが受信者 (受信トレイまたは迷惑メールフォルダー) に配信される場合、常に、ユーザーがペイロード URL をクリックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="df03c-281">配信されたメッセージの URL をクリックしても成功することはありませんが、最初にメールボックスにフィッシングメッセージが配信された理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="df03c-282">ユーザーがフィッシングメッセージ内のペイロード URL をクリックすると、アクションがキャンペーン詳細ビューのダイアグラムの [ **URL** ] 領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="df03c-283">**可**</span><span class="sxs-lookup"><span data-stu-id="df03c-283">**Allowed**</span></span>

- <span data-ttu-id="df03c-284">**Blockpage**: 受信者がペイロード URL をクリックしたが、悪意のある web サイトへのアクセスが組織内の[ATP Safe Links](atp-safe-links.md)ポリシーによってブロックされた。</span><span class="sxs-lookup"><span data-stu-id="df03c-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="df03c-285">**Blockpageoverride**: 受信者がメッセージ内のペイロード URL をクリックしました。 ATP Safe Links は停止しようとしましたが、そのブロックを上書きすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="df03c-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="df03c-286">「安全なリンク」[ポリシー](set-up-atp-safe-links-policies.md)を調査して、ユーザーが安全なリンク verdict を上書きし、悪意のある web サイトに進むことができる理由を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df03c-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="df03c-287">**PendingDetonationPage**: ATP の安全な添付ファイルは、仮想コンピューター環境でペイロード URL を開いて、何が起きるかを確認する処理になります。</span><span class="sxs-lookup"><span data-stu-id="df03c-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="df03c-288">**PendingDetonationPageOverride**: 受信者は、ペイロード分析プロセスを上書きすることを許可され、結果を待たずに URL を開くことができました。</span><span class="sxs-lookup"><span data-stu-id="df03c-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="df03c-289">タブ</span><span class="sxs-lookup"><span data-stu-id="df03c-289">Tabs</span></span>

<span data-ttu-id="df03c-290">[キャンペーンの詳細] ビューのタブでは、キャンペーンの詳細を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="df03c-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="df03c-291">タブに表示される情報は、タイムラインの [[キャンペーン情報](#campaign-information)] セクションで示されているように、網かけの日付範囲によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="df03c-292">**URL クリック**: ユーザーがフィッシングメッセージのペイロード URL をクリックしていない場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="df03c-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="df03c-293">ユーザーが URL をクリックできた場合は、次の値が入力されます。</span><span class="sxs-lookup"><span data-stu-id="df03c-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="df03c-294">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="df03c-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="df03c-295">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="df03c-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="df03c-296">**[時刻] をクリック**</span><span class="sxs-lookup"><span data-stu-id="df03c-296">**Click time**</span></span>
  - <span data-ttu-id="df03c-297">**[Verdict] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="df03c-297">**Click verdict**</span></span>

- <span data-ttu-id="df03c-298">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-298">**Sender IPs**</span></span>

  - <span data-ttu-id="df03c-299">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="df03c-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="df03c-300">**合計数**</span><span class="sxs-lookup"><span data-stu-id="df03c-300">**Total count**</span></span>
  - <span data-ttu-id="df03c-301">**ボックス (内側)**</span><span class="sxs-lookup"><span data-stu-id="df03c-301">**Inboxed**</span></span>
  - <span data-ttu-id="df03c-302">**ボックスなし**</span><span class="sxs-lookup"><span data-stu-id="df03c-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="df03c-303">**Spf が渡さ**れました。送信者は[sender POLICY Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)によって認証されました。</span><span class="sxs-lookup"><span data-stu-id="df03c-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="df03c-304">SPF 検証に合格しない送信者が、送信者が認証されていないこと、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="df03c-305">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-305">**Senders**</span></span>

  - <span data-ttu-id="df03c-306">**Sender**: これは、SMTP MAIL FROM コマンドの実際の送信者アドレスです。これは、必ずしも、ユーザーが電子メールクライアントに表示する from: 電子メールアドレスであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="df03c-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="df03c-307">**合計数**</span><span class="sxs-lookup"><span data-stu-id="df03c-307">**Total count**</span></span>
  - <span data-ttu-id="df03c-308">**ボックス (内側)**</span><span class="sxs-lookup"><span data-stu-id="df03c-308">**Inboxed**</span></span>
  - <span data-ttu-id="df03c-309">**ボックスなし**</span><span class="sxs-lookup"><span data-stu-id="df03c-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="df03c-310">**Dkim が渡さ**れました: 送信者はドメインキーで識別された[メール (dkim)](support-for-validation-of-dkim-signed-messages.md)によって認証されました。</span><span class="sxs-lookup"><span data-stu-id="df03c-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="df03c-311">DKIM validation に合格しない送信者は、送信者が認証されていないこと、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="df03c-312">**DMARC が渡さ**れました。送信者は、[ドメインベースのメッセージ認証、レポート、および準拠 (DMARC)](use-dmarc-to-validate-email.md)によって認証されています。</span><span class="sxs-lookup"><span data-stu-id="df03c-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="df03c-313">送信者が DMARC の検証に合格しない場合は、送信者が認証されていないか、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="df03c-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="df03c-314">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="df03c-314">**Attachments**</span></span>

  - <span data-ttu-id="df03c-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="df03c-315">**Filename**</span></span>
  - <span data-ttu-id="df03c-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="df03c-316">**SHA256**</span></span>
  - <span data-ttu-id="df03c-317">**マルウェアファミリ**</span><span class="sxs-lookup"><span data-stu-id="df03c-317">**Malware family**</span></span>
  - <span data-ttu-id="df03c-318">**合計数**</span><span class="sxs-lookup"><span data-stu-id="df03c-318">**Total count**</span></span>

- <span data-ttu-id="df03c-319">\*\* URL \*\*</span><span class="sxs-lookup"><span data-stu-id="df03c-319">**URL**</span></span>

  - <span data-ttu-id="df03c-320">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="df03c-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="df03c-321">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="df03c-321">**Total Count**</span></span>

<span data-ttu-id="df03c-322"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="df03c-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="df03c-323">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df03c-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="df03c-324">ボタン</span><span class="sxs-lookup"><span data-stu-id="df03c-324">Buttons</span></span>

<span data-ttu-id="df03c-325">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="df03c-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="df03c-326">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="df03c-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="df03c-327">[検索] ボックス内の**メッセージ**:**キャンペーン ID**と**配信場所: 受信トレイ**を検索フィルターとして使用して、新しい脅威エクスプローラー検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="df03c-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
