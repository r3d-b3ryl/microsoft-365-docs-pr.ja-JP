---
title: ATP のキャンペーン ビュー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection のキャンペーン ビューについて説明します。
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825799"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="9918f-103">ATP のキャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="9918f-103">Campaign Views in ATP</span></span>

<span data-ttu-id="9918f-104">キャンペーン ビューは、セキュリティ/コンプライアンス センターの Advanced Threat Protection (ATP) & の機能で、サービスのフィッシング攻撃を特定して分類します。</span><span class="sxs-lookup"><span data-stu-id="9918f-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="9918f-105">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="9918f-106">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="9918f-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="9918f-107">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="9918f-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="9918f-108">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="9918f-108">Show value to decision makers.</span></span>

<span data-ttu-id="9918f-109">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="9918f-110">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="9918f-110">What is a campaign?</span></span>

<span data-ttu-id="9918f-111">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="9918f-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="9918f-112">資格情報と企業データを不用とするメール攻撃は、大きくて漏える多い情報です。</span><span class="sxs-lookup"><span data-stu-id="9918f-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="9918f-113">攻撃を停止するためのテクノロジが増加すると、攻撃者は攻撃を継続できるように取り上げ、方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="9918f-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="9918f-114">Microsoft では、サービス全体のフィッシング対策、スパム対策、マルウェア対策に関する大量のデータを活用してキャンペーンを特定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9918f-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="9918f-115">いくつかの要素に従って攻撃情報を分析し、分類します。</span><span class="sxs-lookup"><span data-stu-id="9918f-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="9918f-116">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9918f-116">For example:</span></span>

- <span data-ttu-id="9918f-117">**攻撃ソース**: ソース IP アドレスと送信者のメール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="9918f-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="9918f-118">**攻撃メッセージの**プロパティ: メッセージのコンテンツ、スタイル、トーン。</span><span class="sxs-lookup"><span data-stu-id="9918f-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="9918f-119">**攻撃の受信者**: 受信者のドメイン、受信者の職務 (管理者、役員など)、会社の種類 (大企業、中小企業、公的組織、民間組織など)、業界。</span><span class="sxs-lookup"><span data-stu-id="9918f-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="9918f-120">**攻撃の**ペイロード: 悪意のあるリンク、添付ファイル、またはメッセージ内のその他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="9918f-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="9918f-121">キャンペーンの有効期間は短くしたり、アクティブ期間およびアクティブ期間が無効な月間にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="9918f-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="9918f-122">キャンペーンは、特定の組織に応じて立てたり、組織が複数の企業にまたがって大規模なキャンペーンに参加してくる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9918f-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="9918f-123">セキュリティ センターのセキュリティ &キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="9918f-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="9918f-124">キャンペーン ビューは、セキュリティ/[コンプライアンス センターの脅 &威管理キャンペーン](https://protection.office.com)で、または直接**Threat management** \> **Campaigns**利用できます <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="9918f-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="9918f-126">次の方法でキャンペーン ビューを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="9918f-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="9918f-127">**脅威の管理** \>**エクスプローラー** \>**View** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="9918f-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="9918f-128">**脅威の管理** \>**エクスプローラー** \>**View** \>**すべての電子メール** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="9918f-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="9918f-129">**脅威の管理** \>**エクスプローラー** \>**View** \>**フィッシング語** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="9918f-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="9918f-130">**脅威の管理** \>**エクスプローラー** \>**View** \>**マルウェア** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="9918f-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="9918f-131">キャンペーン ビューにアクセスするには、セキュリティ/コンプライアンス **センターの組織管理**、 **セキュリティ管理者**、または **セキュリティ閲覧者** の役割グループのメンバー&必要があります。</span><span class="sxs-lookup"><span data-stu-id="9918f-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="9918f-132">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9918f-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="9918f-133">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="9918f-133">Campaigns overview</span></span>

<span data-ttu-id="9918f-134">概要ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="9918f-135">既定の [ **キャンペーン] タブ** では、 **キャンペーンの種類の** 領域には、1 日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="9918f-136">既定では、グラフにはフィッシ**ング データとマルウェア データの両方\*\*\*\*が表示**されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="9918f-137">キャンペーンのデータが表示されていない場合は、日付範囲またはフィルターを変更してみて [ください](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="9918f-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="9918f-138">概要ページの残りの部分では、キャンペーン タブに **次の情報を示** します。</span><span class="sxs-lookup"><span data-stu-id="9918f-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="9918f-139">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-139">**Name**</span></span>

- <span data-ttu-id="9918f-140">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="9918f-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="9918f-141">キャンペーン内のすべてのメッセージの件名が同じであるとはずです。</span><span class="sxs-lookup"><span data-stu-id="9918f-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="9918f-142">**Targeted**(対象指定): (組織内のキャンペーン受信者の数)/ (サービス内のすべての組織のキャンペーン内の受信者の合計数) によって計算された割合。</span><span class="sxs-lookup"><span data-stu-id="9918f-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="9918f-143">この値は、キャンペーンの特に、その広告を組織の (より高い価値) とサービス内の他の組織 (値を低い) に適用するかを示します。</span><span class="sxs-lookup"><span data-stu-id="9918f-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="9918f-144">**Type:** この値は、**フィッシングまたはマルウェア\*\*\*\*のいずれかです**。</span><span class="sxs-lookup"><span data-stu-id="9918f-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="9918f-145">**サブタイプ**: この値には、キャンペーンの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9918f-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="9918f-146">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9918f-146">For example:</span></span>

  - <span data-ttu-id="9918f-147">**フィッシング**: 使用可能な場合、このキャンペーンによってフィッシングされるブランド。</span><span class="sxs-lookup"><span data-stu-id="9918f-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="9918f-148">たとえば、、 `Microsoft` 、 、 , 、 、 `365` `Unknown` `Outlook` などです `DocuSign` 。</span><span class="sxs-lookup"><span data-stu-id="9918f-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="9918f-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="9918f-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="9918f-150">可能な場合、このキャンペーンによってフィッシングされるブランド。</span><span class="sxs-lookup"><span data-stu-id="9918f-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="9918f-151">ATP テクノロジによる検出の場合、プレフィックス **ATP- が** subtype 値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="9918f-152">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="9918f-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="9918f-153">**受信トレイ:** このキャンペーンからメッセージを受信したユーザーの数 ([迷惑メール] フォルダーには配信されません)。</span><span class="sxs-lookup"><span data-stu-id="9918f-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="9918f-154">**クリック済**み : URL をクリックしたか、フィッシングメッセージ内で添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="9918f-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="9918f-155">**クリック率**: "クリックされた受信トレイ"**によって計算される**  /  **割合。**</span><span class="sxs-lookup"><span data-stu-id="9918f-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="9918f-156">この値は、キャンペーンの有効性と、受信者がメッセージをフィッシングとして識別できて、ペイロード URL をクリックしないかどうかを示すインジケーターです。</span><span class="sxs-lookup"><span data-stu-id="9918f-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="9918f-157">この値は、マルウェア キャンペーンでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="9918f-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="9918f-158">**[訪問済**み]: ユーザー数をペイロード Web サイトに対して実際に行ったユーザー数。</span><span class="sxs-lookup"><span data-stu-id="9918f-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="9918f-159">クリックされた値 **はあっても** 、Web サイトへの安全なリンクによるアクセスがブロックされている場合、この値は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="9918f-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="9918f-160">キャ **ンペーンの元のタブ** には、世界地図にメッセージ ソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="9918f-161">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="9918f-161">Filters and settings</span></span>

<span data-ttu-id="9918f-162">[キャンペーン ビュー] ページの上部には、特定のキャンペーンの検索と分離に役立つフィルター設定とクエリ設定があります。</span><span class="sxs-lookup"><span data-stu-id="9918f-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーン フィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="9918f-164">最も基本的なフィルター処理として使用できるフィルターは、開始日時と終了日時です。</span><span class="sxs-lookup"><span data-stu-id="9918f-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="9918f-165">ビューをさらにフィルター処理するには、[キャンペーンの種類] ボタンをクリック**Campaign type**し、選択して、[更新] をクリックして、複数の値をフィルター処理で 1 つの**プロパティに対して実行します**。</span><span class="sxs-lookup"><span data-stu-id="9918f-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="9918f-166">利用可能なキャンペーンのプロパティを次の一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="9918f-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="9918f-167">基本</span><span class="sxs-lookup"><span data-stu-id="9918f-167">Basic</span></span>

  - <span data-ttu-id="9918f-168">**キャンペーンの種類**: マルウェア**またはフィ\*\*\*\*ッシングを選択します**。</span><span class="sxs-lookup"><span data-stu-id="9918f-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="9918f-169">選択範囲をクリアすると、両方を選択した場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="9918f-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="9918f-170">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="9918f-170">**Campaign name**</span></span>
  - <span data-ttu-id="9918f-171">**キャンペーン サブタイプ**</span><span class="sxs-lookup"><span data-stu-id="9918f-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="9918f-172">**送信者**</span><span class="sxs-lookup"><span data-stu-id="9918f-172">**Sender**</span></span>
  - <span data-ttu-id="9918f-173">**受信者**</span><span class="sxs-lookup"><span data-stu-id="9918f-173">**Recipients**</span></span>
  - <span data-ttu-id="9918f-174">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9918f-174">**Sender domain**</span></span>
  - <span data-ttu-id="9918f-175">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="9918f-175">**Subject**</span></span>
  - <span data-ttu-id="9918f-176">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="9918f-176">**Attachment filename**</span></span>
  - <span data-ttu-id="9918f-177">**マルウェア ファミリー**</span><span class="sxs-lookup"><span data-stu-id="9918f-177">**Malware family**</span></span>
  - <span data-ttu-id="9918f-178">**配信操作**</span><span class="sxs-lookup"><span data-stu-id="9918f-178">**Delivery action**</span></span>
  - <span data-ttu-id="9918f-179">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="9918f-179">**Detection technology**</span></span>
  - <span data-ttu-id="9918f-180">**Tags**</span><span class="sxs-lookup"><span data-stu-id="9918f-180">**Tags**</span></span>
  - <span data-ttu-id="9918f-181">**システムオーバーライド**</span><span class="sxs-lookup"><span data-stu-id="9918f-181">**System overrides**</span></span>

- <span data-ttu-id="9918f-182">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9918f-182">Advanced</span></span>

  - <span data-ttu-id="9918f-183">**インターネット メッセージ ID:** メッセージ ヘッダー **内の Message-ID** ヘッダー フィールドで使用可能です。</span><span class="sxs-lookup"><span data-stu-id="9918f-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="9918f-184">角かっ `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` こなどに注:</span><span class="sxs-lookup"><span data-stu-id="9918f-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="9918f-185">**ネットワーク メッセージ ID:** メッセージ ヘッダー内の **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー フィールドで使用可能な GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="9918f-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="9918f-186">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="9918f-187">**添付ファイルの SHA256:** Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="9918f-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="9918f-188">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="9918f-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="9918f-189">**アラート ポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="9918f-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="9918f-190">URL</span><span class="sxs-lookup"><span data-stu-id="9918f-190">URLs</span></span>

  - <span data-ttu-id="9918f-191">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9918f-191">**URL domain**</span></span>
  - <span data-ttu-id="9918f-192">**URL ドメインおよびパス**</span><span class="sxs-lookup"><span data-stu-id="9918f-192">**URL domain and path**</span></span>
  - <span data-ttu-id="9918f-193">**URL**</span><span class="sxs-lookup"><span data-stu-id="9918f-193">**URL**</span></span>
  - <span data-ttu-id="9918f-194">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="9918f-194">**URL path**</span></span>
  - <span data-ttu-id="9918f-195">**Click dict**</span><span class="sxs-lookup"><span data-stu-id="9918f-195">**Click verdict**</span></span>

<span data-ttu-id="9918f-196">複数のプロパティによるフィルター処理など、より高度なフィルター処理の場合は、[ **フィルターの設定] ボタン** をクリックしてクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9918f-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="9918f-197">同じキャンペーンのプロパティが利用できますが、次の機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9918f-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="9918f-198">[条件の追加 **] をクリックして、** 複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="9918f-199">条件の間に **、And** または **Or** 演算子を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="9918f-200">条件リストの **下部にある** 条件グループの項目を選択すると、複雑な複合条件を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="9918f-201">完了したら、[クエリ] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9918f-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="9918f-202">基本フィルターまたは高度なフィルターを作成した後は、[保存] クエリまたは [保存] のクエリを**使用して\*\*\*\*そのフィルターを保存できます**。</span><span class="sxs-lookup"><span data-stu-id="9918f-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="9918f-203">後でキャンペーン ビューに戻って、保存されたクエリ設定をクリックして、保存されたフィルター **を読み込むことができます**。</span><span class="sxs-lookup"><span data-stu-id="9918f-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="9918f-204">グラフまたはキャンペーンの一覧をエクスポートするには、[**エクスポート]** をクリックして [エクスポート] をクリックし **、[グラフ データ\*\*\*\*をエクスポート] または [キャンペーン リストのエクスポート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9918f-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="9918f-205">Microsoft Defender ATP サブスクリプションがある場合は **、WDATP をクリックして** 、Microsoft Defender ATP を使用してキャンペーン情報に接続または切断できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="9918f-206">詳しくは [、「Microsoft Defender ATP を使用して Office 365 ATP を統合する」をご覧ください](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)。</span><span class="sxs-lookup"><span data-stu-id="9918f-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="9918f-207">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="9918f-207">Campaign details</span></span>

<span data-ttu-id="9918f-208">キャンペーンの名前をクリックすると、キャンペーンの詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="9918f-209">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="9918f-209">Campaign information</span></span>

<span data-ttu-id="9918f-210">キャンペーンの詳細ビューの上部で、次のキャンペーン情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="9918f-211">**ID:** 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="9918f-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="9918f-212">**開始\*\*\*\*日:** キャンペーンの開始日と終了日。</span><span class="sxs-lookup"><span data-stu-id="9918f-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="9918f-213">これらの日付は、概要ページで選選したフィルター日付より多くの場合があります。</span><span class="sxs-lookup"><span data-stu-id="9918f-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="9918f-214">**影響**: このセクションには、選択した (またはタイムラインで選択した) 期間フィルターに関する次のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9918f-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="9918f-215">受信者の総数。</span><span class="sxs-lookup"><span data-stu-id="9918f-215">The total number of recipients.</span></span>
  - <span data-ttu-id="9918f-216">「受信トレイ」された (受信トレイに配信された、迷惑メール フォルダーに対してでない) メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="9918f-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="9918f-217">フィッシング メッセージの URL ペイロードをクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="9918f-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="9918f-218">URL のアクセス数の多いユーザー数。</span><span class="sxs-lookup"><span data-stu-id="9918f-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="9918f-219">**Targeted**(対象指定): (組織内のキャンペーン受信者の数)/ (サービス内のすべての組織のキャンペーン内の受信者の合計数) によって計算された割合。</span><span class="sxs-lookup"><span data-stu-id="9918f-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="9918f-220">この値はキャンペーンの有効期間全体をとって計算され、フィルターの日付は変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9918f-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="9918f-221">キャンペーン アクティビティの対話型タイムライン: タイムラインはキャンペーンの有効期間全体に発生したアクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="9918f-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="9918f-222">既定では、概要で選択した日付範囲フィルターがシェーダ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="9918f-223">クリックしてドラッグすると、特定のスタート ポイントとエンド ポイントを選択できます。この場合、次のセクションで説明するように、[影響] 領域とページの残りの<u>部分に表示されるデータが変更されます**Impact**</u>。</span><span class="sxs-lookup"><span data-stu-id="9918f-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="9918f-224">タイトル バーで、[ダウンロード キャンペー **ンの書き込** み] ボタン Download キャンペーンの書き込みアイコンをクリックすると、キャンペーンの詳細を Word 文書 ![ ](../../media/download-campaign-write-up-button.png) (既定では CampaignReport.docx という名前) にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9918f-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="9918f-225">このドキュメントには、キャンペーンの有効期間全体に関する詳細が含まれていることに注意してください (選したフィルターの日付を含むことも含む)。</span><span class="sxs-lookup"><span data-stu-id="9918f-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="9918f-227">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="9918f-227">Campaign flow</span></span>

<span data-ttu-id="9918f-228">キャンペーンの詳細ビューの中央に、キャンペーンに関する重要な詳細が、水 **平** 方向のフロー図 _(San キー_ の図) の [フロー] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="9918f-229">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9918f-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="9918f-230">Flow 図に表示される情報 **は、** 前のセクションで説明したように、タイムラインのシェーデン日付範囲によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="9918f-232">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="9918f-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="9918f-233">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9918f-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="9918f-234">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-234">**Sender IPs**</span></span>

- <span data-ttu-id="9918f-235">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-235">**Sender domains**</span></span>

- <span data-ttu-id="9918f-236">**フィルターの確認**: これらの値は、スパム対策メッセージ ヘッダーに記述されている利用可能なフィッシング [およびスパムフィルターの頂点に関連しています](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="9918f-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="9918f-237">次の表に使用可能な値を示します。</span><span class="sxs-lookup"><span data-stu-id="9918f-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="9918f-238">値</span><span class="sxs-lookup"><span data-stu-id="9918f-238">Value</span></span>|<span data-ttu-id="9918f-239">スパム フィルターの確認</span><span class="sxs-lookup"><span data-stu-id="9918f-239">Spam filter verdict</span></span>|<span data-ttu-id="9918f-240">説明</span><span class="sxs-lookup"><span data-stu-id="9918f-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="9918f-241">**可**</span><span class="sxs-lookup"><span data-stu-id="9918f-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="9918f-242">メッセージは、スパム フィルターによって評価される前に、スパム フィルターまたはスキップされていないフィルターとしてマークされました (たとえば、メール フロー ルールによって、トランスポート ルールとも呼ばれる)。</span><span class="sxs-lookup"><span data-stu-id="9918f-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="9918f-243">その他の理由でスパム フィルターがスキップされた場合 (たとえば、送信者と受信者が同じ組織内にあるように見える)。</span><span class="sxs-lookup"><span data-stu-id="9918f-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="9918f-244">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="9918f-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="9918f-245">メッセージは、スパム フィルターによって評価される前にスパムとしてマークされました (例: メール フロー ルールによって)。</span><span class="sxs-lookup"><span data-stu-id="9918f-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="9918f-246">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="9918f-247">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="9918f-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="9918f-248">**検出されません (Not Detected)**</span><span class="sxs-lookup"><span data-stu-id="9918f-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="9918f-249">スパム フィルタリングによって、メッセージは迷惑メールでないとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="9918f-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="9918f-250">**リリース済み**</span><span class="sxs-lookup"><span data-stu-id="9918f-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="9918f-251">メッセージは検疫から解放されたため、スパム フィルタリングがスキップされました。</span><span class="sxs-lookup"><span data-stu-id="9918f-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="9918f-252">**テナントによる許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9918f-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="9918f-253">メッセージがスパム対策ポリシーの設定 (送信者が許可された送信者リストまたは許可されたドメイン リストに含ていたなど) によってスキップされたスパム フィルタリングをスキップした。</span><span class="sxs-lookup"><span data-stu-id="9918f-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="9918f-254">**テナント ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9918f-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="9918f-255">メッセージはスパム対策ポリシー設定 (送信者が許可された送信者リストまたは許可されたドメイン リストに含ていたなど) によって、スパム フィルタリングによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="9918f-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="9918f-256">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9918f-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="9918f-257">送信者が Outlook の差出人セーフ リストに含ていたため、メッセージにスパム フィルタリングが省略されました。</span><span class="sxs-lookup"><span data-stu-id="9918f-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="9918f-258">**ユーザー ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9918f-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="9918f-259">送信者は Outlook のユーザーの受信拒否リストに含っていたため、スパム フィルタリングによってメッセージがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="9918f-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="9918f-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="9918f-260">**ZAP**</span></span>|<span data-ttu-id="9918f-261">該当なし</span><span class="sxs-lookup"><span data-stu-id="9918f-261">n/a</span></span>|<span data-ttu-id="9918f-262">[スパム対策ポリシー設定 ([迷惑メール] フォルダーまたは [検疫済み] に移動)](zero-hour-auto-purge.md) に従って、配信されたメッセージに対して、配信されたメッセージに対してゼロアオージ (ZAP) アクションが実行されたとき。</span><span class="sxs-lookup"><span data-stu-id="9918f-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="9918f-263"><sup>\*</sup> 許可されたメッセージがサービスによってブロックされる可能性が大きいため、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="9918f-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="9918f-264"><sup>\*\*</sup> これらのメッセージは検疫され、配信されないため、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="9918f-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="9918f-265">[**Delivery locations (配信場所)**]: 実際に受信者に (受信トレイまたは迷惑メールフォルダーに) 配信されたメッセージについては、メッセージに含まれるペイロード URL をユーザーがクリックしなかった場合でも調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9918f-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="9918f-266">検疫済みメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="9918f-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="9918f-267">詳細については [、EOP の検疫済み電子メール メッセージを参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9918f-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="9918f-268">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="9918f-268">**Deleted folder**</span></span>
  - <span data-ttu-id="9918f-269">**Dropped**</span><span class="sxs-lookup"><span data-stu-id="9918f-269">**Dropped**</span></span>
  - <span data-ttu-id="9918f-270">**External:** 受信者は、ハイブリッド環境の社内電子メール組織にあります。</span><span class="sxs-lookup"><span data-stu-id="9918f-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="9918f-271">**失敗**</span><span class="sxs-lookup"><span data-stu-id="9918f-271">**Failed**</span></span>
  - <span data-ttu-id="9918f-272">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="9918f-272">**Forwarded**</span></span>
  - <span data-ttu-id="9918f-273">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-273">**Inbox**</span></span>
  - <span data-ttu-id="9918f-274">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-274">**Junk folder**</span></span>
  - <span data-ttu-id="9918f-275">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-275">**Quarantine**</span></span>
  - <span data-ttu-id="9918f-276">**不明**</span><span class="sxs-lookup"><span data-stu-id="9918f-276">**Unknown**</span></span>

- <span data-ttu-id="9918f-277">**URL clicks:** These are described in the next section.</span><span class="sxs-lookup"><span data-stu-id="9918f-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="9918f-278">10 個を超えるアイテムを含むすべてのレイヤーでは、上位 10 個のアイテムが表示され、他の項目は他のアイテムにま **とめてバンドルされます**。</span><span class="sxs-lookup"><span data-stu-id="9918f-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="9918f-279">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="9918f-279">URL clicks</span></span>

<span data-ttu-id="9918f-280">フィッシング メッセージが受信者 (受信トレイまたは迷惑メール フォルダー) に配信される場合、ユーザーがペイロード URL をクリックする機ッスは常に存在します。</span><span class="sxs-lookup"><span data-stu-id="9918f-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="9918f-281">配信されたメッセージの URL をクリックしないと成功の小さい測定値になりますが、フィッシング メッセージがメールボックスに配信された最初の場所である理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9918f-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="9918f-282">ユーザーがフィッシング メッセージのペイロード URL をクリックすると、その操作はキャンペーンの詳細ビューの図 **の URL** クリックに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="9918f-283">**可**</span><span class="sxs-lookup"><span data-stu-id="9918f-283">**Allowed**</span></span>

- <span data-ttu-id="9918f-284">**BlockPage**: 受信者がペイロード URL をクリックしたが、悪意のある Web サイトへのアクセスは、組織 [の ATP](atp-safe-links.md) の安全なリンク ポリシーによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="9918f-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="9918f-285">**BlockPageOverride**: メッセージ内のペイロード URL を受信者がクリックしたが、ATP の安全なリンクによってその停止が試みましたが、ブロックの上書きは許可されました。</span><span class="sxs-lookup"><span data-stu-id="9918f-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="9918f-286">「安全なリンク」ポリシーを [調査して](set-up-atp-safe-links-policies.md) 、ユーザーが安全なリンクの詳細を上書きし、悪意のある Web サイトにアクセスし続けた理由を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9918f-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="9918f-287">**PendingDetonationPage**: ATP の安全な添付ファイルは、仮想コンピューター環境でペイロード URL を開いて、その結果を確認するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="9918f-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="9918f-288">**PendingDetonationPageOverride:** 受信者は、ペイロードの分析プロセスを上書きして、結果を待たずに URL を開くことを許可されていました。</span><span class="sxs-lookup"><span data-stu-id="9918f-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="9918f-289">タブ</span><span class="sxs-lookup"><span data-stu-id="9918f-289">Tabs</span></span>

<span data-ttu-id="9918f-290">キャンペーンの詳細ビューのタブを使用すると、キャンペーンをさらに詳しい情報にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9918f-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="9918f-291">タブに表示される情報は、[キャンペーン情報] セクションで説明されているとおりに、タイムライン内 [の日付範囲によって制御](#campaign-information) されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="9918f-292">**URL のクリック**:ユーザーがフィッシング メッセージのペイロード URL をクリックしなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="9918f-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="9918f-293">ユーザーが URL をクリックできる場合は、次の値が入力されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="9918f-294">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9918f-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="9918f-295">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9918f-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="9918f-296">**クリック時刻**</span><span class="sxs-lookup"><span data-stu-id="9918f-296">**Click time**</span></span>
  - <span data-ttu-id="9918f-297">**Click dict**</span><span class="sxs-lookup"><span data-stu-id="9918f-297">**Click verdict**</span></span>

- <span data-ttu-id="9918f-298">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-298">**Sender IPs**</span></span>

  - <span data-ttu-id="9918f-299">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9918f-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="9918f-300">**総数**</span><span class="sxs-lookup"><span data-stu-id="9918f-300">**Total count**</span></span>
  - <span data-ttu-id="9918f-301">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="9918f-301">**Inboxed**</span></span>
  - <span data-ttu-id="9918f-302">**受信トレイに出ない**</span><span class="sxs-lookup"><span data-stu-id="9918f-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="9918f-303">**SPF が渡**されました:送信者は [Sender Policy Framework (SPF) によって認証されました](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="9918f-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="9918f-304">SPF 検証に合格しない送信者は、送信者が認証されていないか、正当な送信者を偽装していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="9918f-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="9918f-305">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-305">**Senders**</span></span>

  - <span data-ttu-id="9918f-306">**Sender:** SMTP MAIL FROM コマンドの実際の送信者アドレスを指定しますが、メール クライアントでユーザーに表示される差出人: メール アドレスとは異なりません。</span><span class="sxs-lookup"><span data-stu-id="9918f-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="9918f-307">**総数**</span><span class="sxs-lookup"><span data-stu-id="9918f-307">**Total count**</span></span>
  - <span data-ttu-id="9918f-308">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="9918f-308">**Inboxed**</span></span>
  - <span data-ttu-id="9918f-309">**受信トレイに出ない**</span><span class="sxs-lookup"><span data-stu-id="9918f-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="9918f-310">**DKIM が渡**されました: 送信者は [Domain Keys Identified Mail (DKIM) によって認証されました](support-for-validation-of-dkim-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9918f-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="9918f-311">DKIM 検証にパスしない送信者は、送信者が認証されていない、または正当な送信者を偽装していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="9918f-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="9918f-312">**DMARC のパス**: 送信者はドメイン ベースのメッセージ認証、レポート、および一時的 [な Conformance (DMARC) によって認証されました](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="9918f-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="9918f-313">DMARC 検証にパスされない送信者は、送信者が認証されていないか、正当な送信者を偽装していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="9918f-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="9918f-314">**添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="9918f-314">**Attachments**</span></span>

  - <span data-ttu-id="9918f-315">**Filename**</span><span class="sxs-lookup"><span data-stu-id="9918f-315">**Filename**</span></span>
  - <span data-ttu-id="9918f-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="9918f-316">**SHA256**</span></span>
  - <span data-ttu-id="9918f-317">**マルウェア ファミリー**</span><span class="sxs-lookup"><span data-stu-id="9918f-317">**Malware family**</span></span>
  - <span data-ttu-id="9918f-318">**総数**</span><span class="sxs-lookup"><span data-stu-id="9918f-318">**Total count**</span></span>

- <span data-ttu-id="9918f-319">**URL**</span><span class="sxs-lookup"><span data-stu-id="9918f-319">**URL**</span></span>

  - <span data-ttu-id="9918f-320">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9918f-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="9918f-321">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="9918f-321">**Total Count**</span></span>

<span data-ttu-id="9918f-322"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="9918f-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="9918f-323">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9918f-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="9918f-324">ボタン</span><span class="sxs-lookup"><span data-stu-id="9918f-324">Buttons</span></span>

<span data-ttu-id="9918f-325">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="9918f-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="9918f-326">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="9918f-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="9918f-327">**受信トレイに置かれていたメッセージ**の確認: キャンペーン **ID** と配信場所を使用する新しい脅威エクスプローラーの **検索タブが開きます。[受信トレイ** ] は検索フィルターとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="9918f-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
