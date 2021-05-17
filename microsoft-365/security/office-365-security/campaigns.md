---
title: Microsoft Defender のキャンペーン ビュー for Office 365プラン
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 詳細については、「Microsoft Defender for microsoft Defender for Office 365」を参照してください。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3c84b9e6253dd813ff930314fc2c1d0a947e94e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205086"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="82664-103">Microsoft Defender のキャンペーン ビュー (Office 365</span><span class="sxs-lookup"><span data-stu-id="82664-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="82664-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="82664-104">**Applies to**</span></span>
- [<span data-ttu-id="82664-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="82664-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="82664-106">キャンペーン ビューは、Microsoft Defender for Office 365 プラン 2 の機能です (たとえば、Microsoft 365 E5 プラン 2 アドオンの Defender を持つ組織Office 365など)。</span><span class="sxs-lookup"><span data-stu-id="82664-106">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="82664-107">セキュリティ コンプライアンス センターのキャンペーン ビュー&サービス内のフィッシング攻撃を識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="82664-107">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="82664-108">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="82664-108">Campaign Views can help you to:</span></span>

- <span data-ttu-id="82664-109">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="82664-109">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="82664-110">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="82664-110">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="82664-111">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="82664-111">Show value to decision makers.</span></span>

<span data-ttu-id="82664-112">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="82664-112">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="82664-113">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="82664-113">What is a campaign?</span></span>

<span data-ttu-id="82664-114">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="82664-114">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="82664-115">資格情報と会社のデータを盗む電子メール攻撃は、大規模で収益性の高い業界です。</span><span class="sxs-lookup"><span data-stu-id="82664-115">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="82664-116">攻撃を止めようとするテクノロジが増加する中、攻撃者は継続的な成功を確実に実現するためにメソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="82664-116">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="82664-117">Microsoft は、サービス全体で膨大な量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンの特定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82664-117">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="82664-118">攻撃情報を分析し、いくつかの要因に従って分類します。</span><span class="sxs-lookup"><span data-stu-id="82664-118">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="82664-119">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="82664-119">For example:</span></span>

- <span data-ttu-id="82664-120">**攻撃元**: 送信元 IP アドレスと送信者メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="82664-120">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="82664-121">**メッセージのプロパティ**: メッセージのコンテンツ、スタイル、トーン。</span><span class="sxs-lookup"><span data-stu-id="82664-121">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="82664-122">**メッセージ受信者**: 受信者の関連付け方法。</span><span class="sxs-lookup"><span data-stu-id="82664-122">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="82664-123">たとえば、受信者ドメイン、受信者のジョブ機能 (管理者、役員など)、会社の種類 (大、小規模、パブリック、プライベートなど)、業種などです。</span><span class="sxs-lookup"><span data-stu-id="82664-123">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="82664-124">**攻撃ペイロード**: メッセージ内の悪意のあるリンク、添付ファイル、または他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="82664-124">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="82664-125">キャンペーンの期間が短い場合や、アクティブな期間と非アクティブな期間がある数日、数週間、または数か月に及んでいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82664-125">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="82664-126">特定の組織に対してキャンペーンが開始される場合や、組織が複数の企業で大規模なキャンペーンに参加している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="82664-126">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="82664-127">セキュリティ コンプライアンス センターの&ビュー</span><span class="sxs-lookup"><span data-stu-id="82664-127">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="82664-128">キャンペーン ビューは、脅威管理キャンペーンのセキュリティ [&コンプライアンス](https://protection.office.com)**センターで**、またはで \> 直接使用できます <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="82664-128">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="82664-130">また、次の場所からキャンペーン ビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="82664-130">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="82664-131">**脅威の管理** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="82664-131">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="82664-132">**脅威の管理** \>**エクスプローラー** \>**表示** \>**すべてのメール** \>**[キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="82664-132">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="82664-133">**脅威の管理** \>**エクスプローラー** \>**表示** \>**フィッシング** \>**[キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="82664-133">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="82664-134">**脅威の管理** \>**エクスプローラー** \>**表示** \>**マルウェア** \>**[キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="82664-134">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="82664-135">キャンペーン ビューにアクセスするには、セキュリティ 管理者コンプライアンス センターの組織の管理、セキュリティ管理者、またはセキュリティ リーダーの役割グループの&必要があります。 </span><span class="sxs-lookup"><span data-stu-id="82664-135">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="82664-136">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82664-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="82664-137">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="82664-137">Campaigns overview</span></span>

<span data-ttu-id="82664-138">[概要] ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82664-138">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="82664-139">既定の [ **キャンペーン] タブ** の [ **キャンペーン** の種類] 領域には、1 日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82664-139">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="82664-140">既定では、グラフにはフィッシング データと **マルウェア データの\*\*\*\*両方が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="82664-140">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="82664-141">キャンペーン データが表示しない場合は、日付範囲またはフィルターを変更 [してみてください](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="82664-141">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="82664-142">残りの概要ページには、[キャンペーン] タブに次の情報 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="82664-142">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="82664-143">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="82664-143">**Name**</span></span>

- <span data-ttu-id="82664-144">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="82664-144">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="82664-145">キャンペーン内のすべてのメッセージに、必ずしも同じ件名が設定されているわけではない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="82664-145">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="82664-146">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算される割合。</span><span class="sxs-lookup"><span data-stu-id="82664-146">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="82664-147">この値は、キャンペーンが組織にのみ向けられる度合い (より高い値) と、サービス内の他の組織 (より低い値) に向けられる度合いを示します。</span><span class="sxs-lookup"><span data-stu-id="82664-147">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="82664-148">**種類**: この値は、**フィッシングまたはマルウェア\*\*\*\*のいずれかです**。</span><span class="sxs-lookup"><span data-stu-id="82664-148">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="82664-149">**サブ** タイプ : この値には、キャンペーンの詳細が含まれる。</span><span class="sxs-lookup"><span data-stu-id="82664-149">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="82664-150">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="82664-150">For example:</span></span>
  - <span data-ttu-id="82664-151">**フィッシング**: 利用可能な場合は、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="82664-151">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="82664-152">たとえば `Microsoft` `365` `Unknown` 、、、、、、、 `Outlook` `DocuSign` などです。</span><span class="sxs-lookup"><span data-stu-id="82664-152">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="82664-153">**マルウェア**: たとえば、 `HTML/PHISH` または `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="82664-153">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="82664-154">利用可能な場合、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="82664-154">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="82664-155">検出が Defender によって実行され、Office 365される場合は、プレフィックス **ATP-** がサブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="82664-155">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="82664-156">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="82664-156">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="82664-157">**受信トレイ**: 受信トレイでこのキャンペーンからメッセージを受信したユーザーの数 (迷惑メール フォルダーに配信されません)。</span><span class="sxs-lookup"><span data-stu-id="82664-157">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="82664-158">**クリック :** URL をクリックしたユーザーまたはフィッシング メッセージで添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="82664-158">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="82664-159">**クリック率**: " Clicked Inboxed " によって **計算された**  /  **割合**。</span><span class="sxs-lookup"><span data-stu-id="82664-159">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="82664-160">この値は、キャンペーンの効果を示す指標です。</span><span class="sxs-lookup"><span data-stu-id="82664-160">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="82664-161">つまり、受信者がメッセージをフィッシングとして識別できた場合、およびペイロード URL をクリックしなかった場合。</span><span class="sxs-lookup"><span data-stu-id="82664-161">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="82664-162">マルウェア キャンペーン **では** クリック率は使用されません。</span><span class="sxs-lookup"><span data-stu-id="82664-162">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="82664-163">**アクセス数**: ペイロード Web サイトに実際にアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="82664-163">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="82664-164">クリックされた値 **が含** まれるが、[リンクセーフ Web サイトへのアクセスがブロックされている場合、この値は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="82664-164">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="82664-165">[ **キャンペーンの発生元** ] タブには、世界の地図にメッセージ ソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82664-165">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="82664-166">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="82664-166">Filters and settings</span></span>

<span data-ttu-id="82664-167">[キャンペーン ビュー] ページの上部には、特定のキャンペーンを見つけて特定するのに役立つフィルター設定とクエリ設定がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="82664-167">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーン フィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="82664-169">最も基本的なフィルター処理は、開始日/時刻と終了日時です。</span><span class="sxs-lookup"><span data-stu-id="82664-169">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="82664-170">ビューをさらにフィルター処理するには、[キャンペーンの種類] ボタンをクリックして選択し、[更新]をクリックして、複数の値をフィルター処理する単一のプロパティを **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="82664-170">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="82664-171">[キャンペーンの種類] ボタンで使用できるフィルター可能なキャンペーン **プロパティについては** 、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="82664-171">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="82664-172">**基本**:</span><span class="sxs-lookup"><span data-stu-id="82664-172">**Basic**:</span></span>
  - <span data-ttu-id="82664-173">**キャンペーンの種類**: [マルウェア **] または [フィッシング]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="82664-173">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="82664-174">選択範囲をクリアすると、両方を選択した場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="82664-174">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="82664-175">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="82664-175">**Campaign name**</span></span>
  - <span data-ttu-id="82664-176">**キャンペーンのサブタイプ**</span><span class="sxs-lookup"><span data-stu-id="82664-176">**Campaign subtype**</span></span>
  - <span data-ttu-id="82664-177">**送信者**</span><span class="sxs-lookup"><span data-stu-id="82664-177">**Sender**</span></span>
  - <span data-ttu-id="82664-178">**受信者**</span><span class="sxs-lookup"><span data-stu-id="82664-178">**Recipients**</span></span>
  - <span data-ttu-id="82664-179">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="82664-179">**Sender domain**</span></span>
  - <span data-ttu-id="82664-180">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="82664-180">**Subject**</span></span>
  - <span data-ttu-id="82664-181">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="82664-181">**Attachment filename**</span></span>
  - <span data-ttu-id="82664-182">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="82664-182">**Malware family**</span></span>
  - <span data-ttu-id="82664-183">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む)。</span><span class="sxs-lookup"><span data-stu-id="82664-183">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="82664-184">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-184">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="82664-185">**システムオーバーライド**</span><span class="sxs-lookup"><span data-stu-id="82664-185">**System overrides**</span></span>
  - <span data-ttu-id="82664-186">**配信アクション**</span><span class="sxs-lookup"><span data-stu-id="82664-186">**Delivery action**</span></span>
  - <span data-ttu-id="82664-187">**その他のアクション**</span><span class="sxs-lookup"><span data-stu-id="82664-187">**Additional action**</span></span>
  - <span data-ttu-id="82664-188">**方向性**</span><span class="sxs-lookup"><span data-stu-id="82664-188">**Directionality**</span></span>
  - <span data-ttu-id="82664-189">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="82664-189">**Detection technology**</span></span>
  - <span data-ttu-id="82664-190">**元の配信場所**</span><span class="sxs-lookup"><span data-stu-id="82664-190">**Original delivery location**</span></span>
  - <span data-ttu-id="82664-191">**最新の配信場所**</span><span class="sxs-lookup"><span data-stu-id="82664-191">**Latest delivery location**</span></span>
  - <span data-ttu-id="82664-192">**システムオーバーライド**</span><span class="sxs-lookup"><span data-stu-id="82664-192">**System overrides**</span></span>

- <span data-ttu-id="82664-193">**Advanced**:</span><span class="sxs-lookup"><span data-stu-id="82664-193">**Advanced**:</span></span>
  - <span data-ttu-id="82664-194">**インターネット メッセージ ID**: メッセージ ヘッダー **の [Message-ID** ヘッダー] フィールドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="82664-194">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="82664-195">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="82664-195">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="82664-196">**ネットワーク メッセージ ID:** メッセージ ヘッダーの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー フィールドで使用できる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="82664-196">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="82664-197">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="82664-197">**Sender IP**</span></span>
  - <span data-ttu-id="82664-198">**添付ファイル SHA256**: ファイルの SHA256 ハッシュ値を Windows で検索するには、コマンド プロンプトで次のコマンドを実行します `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="82664-198">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="82664-199">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="82664-199">**Cluster ID**</span></span>
  - <span data-ttu-id="82664-200">**アラート ポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="82664-200">**Alert Policy ID**</span></span>
  - <span data-ttu-id="82664-201">**ZAP URL シグナル**</span><span class="sxs-lookup"><span data-stu-id="82664-201">**ZAP URL signal**</span></span>

- <span data-ttu-id="82664-202">**URL**:</span><span class="sxs-lookup"><span data-stu-id="82664-202">**URLs**:</span></span>
  - <span data-ttu-id="82664-203">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="82664-203">**URL domain**</span></span>
  - <span data-ttu-id="82664-204">**URL ドメインとパス**</span><span class="sxs-lookup"><span data-stu-id="82664-204">**URL domain and path**</span></span>
  - <span data-ttu-id="82664-205">**URL**</span><span class="sxs-lookup"><span data-stu-id="82664-205">**URL**</span></span>
  - <span data-ttu-id="82664-206">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="82664-206">**URL path**</span></span>
  - <span data-ttu-id="82664-207">**[評決] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="82664-207">**Click verdict**</span></span>

<span data-ttu-id="82664-208">複数のプロパティによるフィルター処理など、より高度なフィルター処理を行う場合は、[高度なフィルター] ボタンをクリックしてクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="82664-208">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="82664-209">同じキャンペーン プロパティを使用できますが、次の機能拡張が追加されています。</span><span class="sxs-lookup"><span data-stu-id="82664-209">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="82664-210">[条件の追加 **] をクリックして、** 複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="82664-210">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="82664-211">条件の間で **And** 演算子または **Or** 演算子を選択できます。</span><span class="sxs-lookup"><span data-stu-id="82664-211">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="82664-212">条件リストの下部 **にある条件グループ** 項目を選択して、複雑な複合条件を形成できます。</span><span class="sxs-lookup"><span data-stu-id="82664-212">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="82664-213">完了したら、[クエリ] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="82664-213">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="82664-214">基本フィルターまたは高度なフィルターを作成した後は、[クエリの保存] または [クエリを名前を付けて保存]**を使用して保存できます**。</span><span class="sxs-lookup"><span data-stu-id="82664-214">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="82664-215">後で、[キャンペーン ビュー] に戻った場合は、[保存済みクエリ設定] をクリックして、保存済 **みフィルターを読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="82664-215">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="82664-216">グラフまたはキャンペーンのリストをエクスポートするには、[エクスポート]をクリックし、[グラフ データのエクスポート] または [キャンペーン リスト **のエクスポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="82664-216">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="82664-217">Microsoft Defender for Endpoint サブスクリプションをお持ちの場合は **、[MDE** 設定] をクリックして、Microsoft Defender for Endpoint でキャンペーン情報を接続または切断できます。</span><span class="sxs-lookup"><span data-stu-id="82664-217">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="82664-218">詳細については[、「Integrate Microsoft Defender for Office 365 Microsoft Defender for Endpoint」を参照してください](integrate-office-365-ti-with-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-218">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="82664-219">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="82664-219">Campaign details</span></span>

<span data-ttu-id="82664-220">キャンペーンの名前をクリックすると、キャンペーンの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="82664-220">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="82664-221">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="82664-221">Campaign information</span></span>

<span data-ttu-id="82664-222">キャンペーンの詳細ビューの上部には、次のキャンペーン情報があります。</span><span class="sxs-lookup"><span data-stu-id="82664-222">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="82664-223">**ID**: 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="82664-223">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="82664-224">**開始** および **終了**: キャンペーンの開始日と終了日。</span><span class="sxs-lookup"><span data-stu-id="82664-224">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="82664-225">これらの日付は、概要ページで選択したフィルターの日付よりも長い場合があります。</span><span class="sxs-lookup"><span data-stu-id="82664-225">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="82664-226">**影響**: このセクションには、選択した (またはタイムラインで選択した) 日付範囲フィルターの次のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82664-226">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  - <span data-ttu-id="82664-227">受信者の総数。</span><span class="sxs-lookup"><span data-stu-id="82664-227">The total number of recipients.</span></span>
  - <span data-ttu-id="82664-228">"受信トレイ" (つまり、迷惑メール フォルダーではなく受信トレイに配信された) メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="82664-228">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="82664-229">フィッシング メッセージで URL ペイロードをクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="82664-229">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="82664-230">URL にアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="82664-230">Howe many users visited the URL.</span></span>

- <span data-ttu-id="82664-231">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算される割合。</span><span class="sxs-lookup"><span data-stu-id="82664-231">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="82664-232">この値はキャンペーンの有効期間全体で計算され、日付フィルターに基づいて変更されません。</span><span class="sxs-lookup"><span data-stu-id="82664-232">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="82664-233">キャンペーンアクティビティのインタラクティブなタイムライン: タイムラインには、キャンペーンの有効期間全体のアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82664-233">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="82664-234">既定では、網掛け領域には、概要で選択した日付範囲フィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82664-234">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="82664-235">クリックしてドラッグすると、特定の開始点と終了点を選択できます。これは、影響領域に表示されるデータを変更し、次のセクションで説明するようにページの残りの部分で<u>変更</u>します。</span><span class="sxs-lookup"><span data-stu-id="82664-235">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="82664-236">タイトル バーで、[キャンペーンの書き込みダウンロード] ボタン [キャンペーンの書き込み] アイコンをクリックして、キャンペーンの詳細を Word ドキュメント (既定では CampaignReport.docx という名前) ![ ](../../media/download-campaign-write-up-button.png) にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="82664-236">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="82664-237">ダウンロードには、キャンペーンの有効期間全体に関する詳細が含まれています (選択したフィルターの日付だけではありません)。</span><span class="sxs-lookup"><span data-stu-id="82664-237">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="82664-239">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="82664-239">Campaign flow</span></span>

<span data-ttu-id="82664-240">キャンペーンの詳細ビューの中央に、キャンペーンに関する重要な詳細は、水平フロー図 (サンキー図と呼ばれる) の **Flow** セクション _に表示_ されます。</span><span class="sxs-lookup"><span data-stu-id="82664-240">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="82664-241">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="82664-241">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="82664-242">グラフ図に表示される情報Flow前のセクションで説明したように、タイムラインの日陰の日付範囲によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="82664-242">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="82664-244">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="82664-244">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="82664-245">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="82664-245">The diagram contains the following information:</span></span>

- <span data-ttu-id="82664-246">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="82664-246">**Sender IPs**</span></span>
- <span data-ttu-id="82664-247">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="82664-247">**Sender domains**</span></span>
- <span data-ttu-id="82664-248">**フィルターの評決**: Verdict 値は、「スパム対策メッセージ ヘッダー」の説明に従って、使用可能なフィッシングおよびスパム フィルターの評決 [に関連しています](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-248">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="82664-249">使用可能な値については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="82664-249">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="82664-250">値</span><span class="sxs-lookup"><span data-stu-id="82664-250">Value</span></span>|<span data-ttu-id="82664-251">スパム フィルターの評決</span><span class="sxs-lookup"><span data-stu-id="82664-251">Spam filter verdict</span></span>|<span data-ttu-id="82664-252">説明</span><span class="sxs-lookup"><span data-stu-id="82664-252">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="82664-253">**可**</span><span class="sxs-lookup"><span data-stu-id="82664-253">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="82664-254">このメッセージは、スパム フィルターによって評価される前に、スパムではない、またはスキップされたフィルター処理としてマークされました。</span><span class="sxs-lookup"><span data-stu-id="82664-254">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="82664-255">たとえば、メッセージはメール フロー ルール (トランスポート ルールとも呼ばれる) によってスパムではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="82664-255">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="82664-256">メッセージは、他の理由でスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="82664-256">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="82664-257">たとえば、送信者と受信者は同じ組織内にあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="82664-257">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="82664-258">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="82664-258">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="82664-259">メッセージは、スパム フィルターによって評価される前にスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="82664-259">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="82664-260">たとえば、メール フロー ルールによって指定します。</span><span class="sxs-lookup"><span data-stu-id="82664-260">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="82664-261">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="82664-261">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="82664-262">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="82664-262">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="82664-263">**検出されない**</span><span class="sxs-lookup"><span data-stu-id="82664-263">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="82664-264">このメッセージは、スパム フィルターによってスパムではないとマークされています。</span><span class="sxs-lookup"><span data-stu-id="82664-264">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="82664-265">**リリース済み**</span><span class="sxs-lookup"><span data-stu-id="82664-265">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="82664-266">メッセージは検疫から解放されたため、スパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="82664-266">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="82664-267">**テナント許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="82664-267">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="82664-268">スパム対策ポリシーの設定のため、メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="82664-268">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="82664-269">たとえば、送信者が許可されている送信者リストまたは許可されたドメイン リストに含めらたとします。</span><span class="sxs-lookup"><span data-stu-id="82664-269">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="82664-270">**テナント ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="82664-270">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="82664-271">スパム対策ポリシーの設定により、スパム フィルターによってメッセージがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="82664-271">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="82664-272">たとえば、送信者が許可されている送信者リストまたは許可されたドメイン リストに含めらたとします。</span><span class="sxs-lookup"><span data-stu-id="82664-272">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="82664-273">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="82664-273">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="82664-274">送信者がユーザーの [送信者] リストに含セーフスキップされました。</span><span class="sxs-lookup"><span data-stu-id="82664-274">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="82664-275">**ユーザー ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="82664-275">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="82664-276">送信者がユーザーの [送信者のブロック] リストに含っていたため、メッセージはスパム フィルターによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="82664-276">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="82664-277">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="82664-277">**ZAP**</span></span>|<span data-ttu-id="82664-278">該当なし</span><span class="sxs-lookup"><span data-stu-id="82664-278">n/a</span></span>|<span data-ttu-id="82664-279">[ゼロ時間自動削除 (ZAP) は](zero-hour-auto-purge.md) 、配信されたメッセージを迷惑メール フォルダーまたは検疫に移動しました。</span><span class="sxs-lookup"><span data-stu-id="82664-279">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="82664-280">スパム対策ポリシーでアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="82664-280">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="82664-281"><sup>\*</sup> 許可されたメッセージがサービスによってブロックされている可能性が高いので、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="82664-281"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="82664-282"><sup>\*\*</sup> これらのメッセージは検疫され、配信されないので、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="82664-282"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="82664-283">**配信場所**: メッセージ内のペイロード URL をユーザーがクリックしなかった場合でも、受信者 (受信トレイまたは迷惑メール フォルダー) に配信されたメッセージを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82664-283">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="82664-284">検疫済みメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="82664-284">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="82664-285">詳細については [、「EOP の検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-285">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="82664-286">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="82664-286">**Deleted folder**</span></span>
  - <span data-ttu-id="82664-287">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="82664-287">**Dropped**</span></span>
  - <span data-ttu-id="82664-288">**外部**: 受信者は、ハイブリッド環境のオンプレミスの電子メール組織にあります。</span><span class="sxs-lookup"><span data-stu-id="82664-288">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="82664-289">**Failed**</span><span class="sxs-lookup"><span data-stu-id="82664-289">**Failed**</span></span>
  - <span data-ttu-id="82664-290">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="82664-290">**Forwarded**</span></span>
  - <span data-ttu-id="82664-291">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="82664-291">**Inbox**</span></span>
  - <span data-ttu-id="82664-292">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="82664-292">**Junk folder**</span></span>
  - <span data-ttu-id="82664-293">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="82664-293">**Quarantine**</span></span>
  - <span data-ttu-id="82664-294">**不明**</span><span class="sxs-lookup"><span data-stu-id="82664-294">**Unknown**</span></span>

- <span data-ttu-id="82664-295">**URL クリック**: これらの値については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="82664-295">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="82664-296">10 を超えるアイテムを含むすべてのレイヤーで、上位 10 のアイテムが表示され、残りは [その他] にまとめて表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="82664-296">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="82664-297">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="82664-297">URL clicks</span></span>

<span data-ttu-id="82664-298">フィッシング メッセージが受信者の受信トレイまたは迷惑メール フォルダーに配信される場合、ユーザーがペイロード URL をクリックする可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="82664-298">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="82664-299">URL をクリックしないのは成功の小さな手段ですが、フィッシング メッセージがメールボックスに配信された理由を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82664-299">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="82664-300">ユーザーがフィッシング メッセージのペイロード URL をクリックすると、アクションがキャンペーンの詳細ビューの図の **URL** クリック領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="82664-300">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="82664-301">**可**</span><span class="sxs-lookup"><span data-stu-id="82664-301">**Allowed**</span></span>
- <span data-ttu-id="82664-302">**BlockPage**: 受信者がペイロード URL をクリックしましたが、悪意のある Web サイトへのアクセスは、組織内の セーフ [リンク ポリシー](safe-links.md)によってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="82664-302">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="82664-303">**BlockPageOverride**: 受信者はメッセージ内のペイロード URL をクリックし、セーフ Links はブロックを停止しようとしましたが、ブロックを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="82664-303">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="82664-304">[リンク][セーフポリシー](set-up-safe-links-policies.md)を調して、ユーザーがリンクの評価を上書きして悪意のある web サイトに進セーフ許可される理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="82664-304">Inspect your [Safe Links policies](set-up-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="82664-305">**PendingDetonationPage**: セーフ Office 365 用 Microsoft Defender の添付ファイルは、仮想コンピューター環境でペイロード URL を開いて調査中です。</span><span class="sxs-lookup"><span data-stu-id="82664-305">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="82664-306">**PendingDetonationPageOverride**: 受信者は、ペイロードのデトレーション プロセスを上書きし、結果を待たずに URL を開く許可を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="82664-306">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="82664-307">タブ</span><span class="sxs-lookup"><span data-stu-id="82664-307">Tabs</span></span>

<span data-ttu-id="82664-308">キャンペーンの詳細ビューのタブを使用すると、キャンペーンをさらに調査できます。</span><span class="sxs-lookup"><span data-stu-id="82664-308">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="82664-309">タブに表示される情報は、[キャンペーン情報] セクションの説明に従って、タイムラインの日陰の日付範囲 [によって制御](#campaign-information) されます。</span><span class="sxs-lookup"><span data-stu-id="82664-309">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="82664-310">**URL クリック**: メッセージ内のペイロード URL をユーザーがクリックしなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="82664-310">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="82664-311">ユーザーが URL をクリックできた場合、次の値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="82664-311">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="82664-312">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="82664-312">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="82664-313">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="82664-313">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="82664-314">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="82664-314">**Click time**</span></span>
  - <span data-ttu-id="82664-315">**[評決] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="82664-315">**Click verdict**</span></span>

- <span data-ttu-id="82664-316">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="82664-316">**Sender IPs**</span></span>
  - <span data-ttu-id="82664-317">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="82664-317">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="82664-318">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="82664-318">**Total count**</span></span>
  - <span data-ttu-id="82664-319">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="82664-319">**Inboxed**</span></span>
  - <span data-ttu-id="82664-320">**受信トレイに入ってない**</span><span class="sxs-lookup"><span data-stu-id="82664-320">**Not Inboxed**</span></span>
  - <span data-ttu-id="82664-321">**SPF が渡** されました: 送信者は Sender [Policy Framework (SPF) によって認証されました](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-321">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="82664-322">SPF 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者をスプーフィングすることを示します。</span><span class="sxs-lookup"><span data-stu-id="82664-322">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="82664-323">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="82664-323">**Senders**</span></span>
  - <span data-ttu-id="82664-324">**Sender**: これは SMTP MAIL FROM コマンドの実際の送信者アドレスで、ユーザーが電子メール クライアントに表示する差出人: 電子メール アドレスとは限りません。</span><span class="sxs-lookup"><span data-stu-id="82664-324">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="82664-325">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="82664-325">**Total count**</span></span>
  - <span data-ttu-id="82664-326">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="82664-326">**Inboxed**</span></span>
  - <span data-ttu-id="82664-327">**受信トレイに入ってない**</span><span class="sxs-lookup"><span data-stu-id="82664-327">**Not Inboxed**</span></span>
  - <span data-ttu-id="82664-328">**DKIM が渡されました**: 送信者がドメイン キー識別 [メール (DKIM) によって認証されました](support-for-validation-of-dkim-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-328">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="82664-329">DKIM 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者をスプーフィングすることを示します。</span><span class="sxs-lookup"><span data-stu-id="82664-329">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="82664-330">**DMARC が渡** されました: 送信者は、ドメイン ベースのメッセージ認証、レポート、および [準拠 (DMARC) によって認証されました](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="82664-330">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="82664-331">DMARC 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者をスプーフィングすることを示します。</span><span class="sxs-lookup"><span data-stu-id="82664-331">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="82664-332">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="82664-332">**Attachments**</span></span>
  - <span data-ttu-id="82664-333">**Filename**</span><span class="sxs-lookup"><span data-stu-id="82664-333">**Filename**</span></span>
  - <span data-ttu-id="82664-334">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="82664-334">**SHA256**</span></span>
  - <span data-ttu-id="82664-335">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="82664-335">**Malware family**</span></span>
  - <span data-ttu-id="82664-336">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="82664-336">**Total count**</span></span>

- <span data-ttu-id="82664-337">**URL**</span><span class="sxs-lookup"><span data-stu-id="82664-337">**URL**</span></span>
  - <span data-ttu-id="82664-338">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="82664-338">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="82664-339">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="82664-339">**Total Count**</span></span>

<span data-ttu-id="82664-340"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="82664-340"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="82664-341">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82664-341">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="82664-342">ボタン</span><span class="sxs-lookup"><span data-stu-id="82664-342">Buttons</span></span>

<span data-ttu-id="82664-343">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="82664-343">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="82664-344">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="82664-344">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
- <span data-ttu-id="82664-345">**受信トレイメッセージの検索**: [キャンペーン **ID]** と [配信場所 **: 受信** トレイ] を検索フィルターとして使用して、新しい [脅威エクスプローラー] 検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="82664-345">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
