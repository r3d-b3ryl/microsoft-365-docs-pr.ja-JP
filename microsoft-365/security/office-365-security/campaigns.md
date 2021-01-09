---
title: Microsoft Defender for Office 365 プランのキャンペーン ビュー
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
- m365initiative-m365-defender
description: Microsoft Defender for Office 365 のキャンペーン ビューについて説明します。
ms.openlocfilehash: 8e5c49c9a45d1578da1eea33a560da611fb74155
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2021
ms.locfileid: "49788017"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="45c47-103">Microsoft Defender for Office 365 のキャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="45c47-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="45c47-104">キャンペーン ビューは、Office 365 プラン 2 用の Microsoft Defender の機能です (たとえば、Microsoft 365 E5、または Office 365 プラン 2 アドオンの Defender を持つ組織)。</span><span class="sxs-lookup"><span data-stu-id="45c47-104">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="45c47-105">セキュリティ/コンプライアンス センターの&ビューは、サービス内のフィッシング攻撃を識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="45c47-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="45c47-106">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="45c47-107">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="45c47-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="45c47-108">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="45c47-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="45c47-109">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="45c47-109">Show value to decision makers.</span></span>

<span data-ttu-id="45c47-110">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="45c47-111">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="45c47-111">What is a campaign?</span></span>

<span data-ttu-id="45c47-112">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="45c47-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="45c47-113">資格情報と会社のデータを盗む電子メール攻撃は、大規模で収益性の高い業界です。</span><span class="sxs-lookup"><span data-stu-id="45c47-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="45c47-114">攻撃を止める取り組みのテクノロジが増えるに応じて、攻撃者は継続的な成功を保証するために方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="45c47-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="45c47-115">Microsoft は、サービス全体にわたって膨大な量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンを特定します。</span><span class="sxs-lookup"><span data-stu-id="45c47-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="45c47-116">攻撃情報を分析し、いくつかの要因に従って分類します。</span><span class="sxs-lookup"><span data-stu-id="45c47-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="45c47-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="45c47-117">For example:</span></span>

- <span data-ttu-id="45c47-118">**攻撃元**: 送信元 IP アドレスと送信者の電子メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="45c47-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="45c47-119">**メッセージの** プロパティ : メッセージのコンテンツ、スタイル、およびトーン。</span><span class="sxs-lookup"><span data-stu-id="45c47-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="45c47-120">**メッセージ受信者**: 受信者の関連付け。</span><span class="sxs-lookup"><span data-stu-id="45c47-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="45c47-121">たとえば、受信者ドメイン、受信者の仕事の機能 (管理者、役員など)、会社の種類 (大規模、小規模、パブリック、プライベートなど)、業界などです。</span><span class="sxs-lookup"><span data-stu-id="45c47-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="45c47-122">**攻撃ペイロード**: メッセージ内の悪意のあるリンク、添付ファイル、または他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="45c47-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="45c47-123">キャンペーンの期間が短い場合や、アクティブ期間と非アクティブ期間がある数日、数週間、または月に及んでいる場合があります。</span><span class="sxs-lookup"><span data-stu-id="45c47-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="45c47-124">特定の組織に対してキャンペーンが開始される場合や、組織が複数の企業で大規模なキャンペーンの一部である場合があります。</span><span class="sxs-lookup"><span data-stu-id="45c47-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="45c47-125">セキュリティ/コンプライアンス センター&ビュー</span><span class="sxs-lookup"><span data-stu-id="45c47-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="45c47-126">キャンペーン ビューは、セキュリティ/コンプライアンス [センターの&](https://protection.office.com)**管理キャンペーンで**、または直接 \> 利用できます <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="45c47-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="45c47-128">次の場所からキャンペーン ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="45c47-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="45c47-129">**脅威の管理** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="45c47-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="45c47-130">**脅威の管理** \>**エクスプローラー** \>**表示** \>**すべてのメール** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="45c47-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="45c47-131">**脅威の管理** \>**エクスプローラー** \>**表示** \>**フィッシング** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="45c47-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="45c47-132">**脅威の管理** \>**エクスプローラー** \>**表示** \>**マルウェア** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="45c47-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="45c47-133">キャンペーン ビューにアクセスするには、セキュリティ/コンプライアンス センターの組織の管理、セキュリティ管理者、またはセキュリティ閲覧者の役割グループの&必要があります。 </span><span class="sxs-lookup"><span data-stu-id="45c47-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="45c47-134">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45c47-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="45c47-135">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="45c47-135">Campaigns overview</span></span>

<span data-ttu-id="45c47-136">概要ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="45c47-137">既定の [ **キャンペーン]** タブの [ **キャンペーンの種類** ] 領域には、1 日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="45c47-138">既定では、グラフにはフィッシングデータと **マルウェア データの両方\*\*\*\*が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="45c47-139">キャンペーン データが表示しない場合は、日付範囲またはフィルターを変更 [してみてください](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="45c47-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="45c47-140">概要ページの残りの部分では、[キャンペーン] タブに次の情報 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="45c47-141">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-141">**Name**</span></span>

- <span data-ttu-id="45c47-142">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="45c47-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="45c47-143">キャンペーン内のすべてのメッセージの件名が同じとは限りません。</span><span class="sxs-lookup"><span data-stu-id="45c47-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="45c47-144">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算された割合。</span><span class="sxs-lookup"><span data-stu-id="45c47-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="45c47-145">この値は、キャンペーンが組織に対してどの程度向けられるか (より高い値) か、サービス内の他の組織 (より低い値) に向けられているかを示します。</span><span class="sxs-lookup"><span data-stu-id="45c47-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="45c47-146">**型**: この値は **、Phish** または **Malware です**。</span><span class="sxs-lookup"><span data-stu-id="45c47-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="45c47-147">**サブ** タイプ : この値には、キャンペーンに関する詳細が含まれる。</span><span class="sxs-lookup"><span data-stu-id="45c47-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="45c47-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="45c47-148">For example:</span></span>
  - <span data-ttu-id="45c47-149">**フィッシング**: 利用可能な場合、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="45c47-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="45c47-150">たとえば、, `Microsoft` `365` , , , or `Unknown` `Outlook` `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="45c47-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="45c47-151">**マルウェア**: たとえば `HTML/PHISH` 、または `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="45c47-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="45c47-152">利用可能な場合、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="45c47-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="45c47-153">検出が Defender によって Office 365 テクノロジに対して実行される場合、プレフィックス **ATP が** サブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-153">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="45c47-154">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="45c47-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="45c47-155">**受信トレイ**: 受信トレイでこのキャンペーンからメッセージを受信したユーザーの数 (迷惑メール フォルダーには配信されません)。</span><span class="sxs-lookup"><span data-stu-id="45c47-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="45c47-156">**Clicked**: URL をクリックしたユーザー数、またはフィッシング メッセージで添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="45c47-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="45c47-157">**クリックレート**: [受信トレイのクリック数]**で計算された**  /  **パーセンテージ。**</span><span class="sxs-lookup"><span data-stu-id="45c47-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="45c47-158">この値は、キャンペーンの効果を示す指標です。</span><span class="sxs-lookup"><span data-stu-id="45c47-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="45c47-159">つまり、受信者がメッセージをフィッシングとして識別できた場合、および受信者がペイロード URL をクリックしなかった場合。</span><span class="sxs-lookup"><span data-stu-id="45c47-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="45c47-160">クリック率 **は** マルウェア キャンペーンでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="45c47-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="45c47-161">**アクセス:** 実際にペイロード Web サイトにアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="45c47-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="45c47-162">クリックされた値 **がある** が、安全なリンクが Web サイトへのアクセスをブロックしている場合、この値はゼロになります。</span><span class="sxs-lookup"><span data-stu-id="45c47-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="45c47-163">[ **キャンペーンの発生** 元] タブには、世界の地図にメッセージ ソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="45c47-164">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="45c47-164">Filters and settings</span></span>

<span data-ttu-id="45c47-165">[キャンペーン ビュー] ページの上部には、特定のキャンペーンを見つけて切り離すのに役立つフィルターとクエリの設定がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="45c47-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーン フィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="45c47-167">最も基本的なフィルター処理は、開始日時と終了日時です。</span><span class="sxs-lookup"><span data-stu-id="45c47-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="45c47-168">ビューをさらにフィルター処理するには、[キャンペーンの種類] ボタンをクリックして選択し、[更新]をクリックして、複数の値をフィルター処理する単一のプロパティを **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="45c47-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="45c47-169">[キャンペーンの種類] ボタンで利用できるフィルター処理可能な **キャンペーン** のプロパティについて、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="45c47-169">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="45c47-170">**基本**:</span><span class="sxs-lookup"><span data-stu-id="45c47-170">**Basic**:</span></span>
  - <span data-ttu-id="45c47-171">**キャンペーンの種類**: [ **マルウェアまたはフィッシング]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="45c47-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="45c47-172">選択をクリアすると、両方を選択した場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="45c47-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="45c47-173">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="45c47-173">**Campaign name**</span></span>
  - <span data-ttu-id="45c47-174">**キャンペーンのサブタイプ**</span><span class="sxs-lookup"><span data-stu-id="45c47-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="45c47-175">**送信者**</span><span class="sxs-lookup"><span data-stu-id="45c47-175">**Sender**</span></span>
  - <span data-ttu-id="45c47-176">**受信者**</span><span class="sxs-lookup"><span data-stu-id="45c47-176">**Recipients**</span></span>
  - <span data-ttu-id="45c47-177">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="45c47-177">**Sender domain**</span></span>
  - <span data-ttu-id="45c47-178">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="45c47-178">**Subject**</span></span>
  - <span data-ttu-id="45c47-179">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="45c47-179">**Attachment filename**</span></span>
  - <span data-ttu-id="45c47-180">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="45c47-180">**Malware family**</span></span>
  - <span data-ttu-id="45c47-181">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む)。</span><span class="sxs-lookup"><span data-stu-id="45c47-181">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="45c47-182">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="45c47-182">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="45c47-183">**システム オーバーライド**</span><span class="sxs-lookup"><span data-stu-id="45c47-183">**System overrides**</span></span>
  - <span data-ttu-id="45c47-184">**配信アクション**</span><span class="sxs-lookup"><span data-stu-id="45c47-184">**Delivery action**</span></span>
  - <span data-ttu-id="45c47-185">**追加アクション**</span><span class="sxs-lookup"><span data-stu-id="45c47-185">**Additional action**</span></span>
  - <span data-ttu-id="45c47-186">**方向性**</span><span class="sxs-lookup"><span data-stu-id="45c47-186">**Directionality**</span></span>
  - <span data-ttu-id="45c47-187">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="45c47-187">**Detection technology**</span></span>
  - <span data-ttu-id="45c47-188">**元の配信場所**</span><span class="sxs-lookup"><span data-stu-id="45c47-188">**Original delivery location**</span></span>
  - <span data-ttu-id="45c47-189">**最新の配信場所**</span><span class="sxs-lookup"><span data-stu-id="45c47-189">**Latest delivery location**</span></span>
  - <span data-ttu-id="45c47-190">**システム オーバーライド**</span><span class="sxs-lookup"><span data-stu-id="45c47-190">**System overrides**</span></span>

- <span data-ttu-id="45c47-191">**詳細設定**:</span><span class="sxs-lookup"><span data-stu-id="45c47-191">**Advanced**:</span></span>
  - <span data-ttu-id="45c47-192">**インターネット メッセージ ID**: メッセージ ヘッダーの **Message-ID** ヘッダー フィールドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-192">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="45c47-193">値の例を `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次に示します (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="45c47-193">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="45c47-194">**ネットワーク メッセージ ID**: メッセージ ヘッダーの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー フィールドで使用できる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="45c47-194">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="45c47-195">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-195">**Sender IP**</span></span>
  - <span data-ttu-id="45c47-196">**添付ファイル SHA256**: Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="45c47-196">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="45c47-197">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="45c47-197">**Cluster ID**</span></span>
  - <span data-ttu-id="45c47-198">**アラート ポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="45c47-198">**Alert Policy ID**</span></span>
  - <span data-ttu-id="45c47-199">**ZAP URL シグナル**</span><span class="sxs-lookup"><span data-stu-id="45c47-199">**ZAP URL signal**</span></span>

- <span data-ttu-id="45c47-200">**URL**:</span><span class="sxs-lookup"><span data-stu-id="45c47-200">**URLs**:</span></span>
  - <span data-ttu-id="45c47-201">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="45c47-201">**URL domain**</span></span>
  - <span data-ttu-id="45c47-202">**URL ドメインとパス**</span><span class="sxs-lookup"><span data-stu-id="45c47-202">**URL domain and path**</span></span>
  - <span data-ttu-id="45c47-203">**URL**</span><span class="sxs-lookup"><span data-stu-id="45c47-203">**URL**</span></span>
  - <span data-ttu-id="45c47-204">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="45c47-204">**URL path**</span></span>
  - <span data-ttu-id="45c47-205">**[Verdict] をクリックする**</span><span class="sxs-lookup"><span data-stu-id="45c47-205">**Click verdict**</span></span>

<span data-ttu-id="45c47-206">複数のプロパティによるフィルター処理など、より高度なフィルター処理を行う場合は、[詳細フィルター] ボタンをクリックしてクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-206">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="45c47-207">同じキャンペーン プロパティを使用できますが、次の拡張機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="45c47-207">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="45c47-208">[条件の追加 **] をクリックすると、** 複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-208">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="45c47-209">条件の間で **And** 演算子 **または Or 演算子** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-209">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="45c47-210">条件リストの下部 **にある条件グループ** 項目を選択すると、複雑な複合条件を形成できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-210">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="45c47-211">完了したら、[クエリ] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="45c47-211">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="45c47-212">基本フィルターまたは高度なフィルターを作成した後は、[クエリの保存] または [名前を付けて保存] を **使用して保存できます**。</span><span class="sxs-lookup"><span data-stu-id="45c47-212">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="45c47-213">後で、キャンペーン ビューに戻る際に、[保存済み] クエリ設定をクリックして、保存済み **フィルターを読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="45c47-213">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="45c47-214">グラフまたはキャンペーンの一覧をエクスポートするには、[エクスポート]をクリックし、[グラフ データのエクスポート] または [キャンペーン 一覧のエクスポート]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="45c47-214">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="45c47-215">Microsoft Defender for Endpoint サブスクリプションをお持ちのお客様は **、MDE** 設定をクリックして、Microsoft Defender for Endpoint にキャンペーン情報を接続または切断できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-215">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="45c47-216">詳しくは、「Microsoft [Defender for Office 365](integrate-office-365-ti-with-wdatp.md)と Microsoft Defender for Endpoint の統合」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45c47-216">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="45c47-217">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="45c47-217">Campaign details</span></span>

<span data-ttu-id="45c47-218">キャンペーンの名前をクリックすると、キャンペーンの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-218">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="45c47-219">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="45c47-219">Campaign information</span></span>

<span data-ttu-id="45c47-220">キャンペーンの詳細ビューの上部に、次のキャンペーン情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-220">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="45c47-221">**ID**: 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="45c47-221">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="45c47-222">**開始** および **終了**: キャンペーンの開始日と終了日。</span><span class="sxs-lookup"><span data-stu-id="45c47-222">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="45c47-223">これらの日付は、概要ページで選択したフィルター日付よりも延長される場合があります。</span><span class="sxs-lookup"><span data-stu-id="45c47-223">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="45c47-224">**影響**: このセクションには、選択した日付範囲フィルター (またはタイムラインで選択した) に関する次のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="45c47-224">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  - <span data-ttu-id="45c47-225">受信者の総数。</span><span class="sxs-lookup"><span data-stu-id="45c47-225">The total number of recipients.</span></span>
  - <span data-ttu-id="45c47-226">"受信トレイ" (迷惑メール フォルダーではなく受信トレイに配信された) メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="45c47-226">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="45c47-227">フィッシング メッセージの URL ペイロードをクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="45c47-227">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="45c47-228">URL にアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="45c47-228">Howe many users visited the URL.</span></span>

- <span data-ttu-id="45c47-229">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算された割合。</span><span class="sxs-lookup"><span data-stu-id="45c47-229">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="45c47-230">この値はキャンペーンの有効期間全体で計算され、日付フィルターに基づいて変化しない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="45c47-230">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="45c47-231">キャンペーン アクティビティの対話型のタイムライン: タイムラインには、キャンペーンの全期間のアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-231">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="45c47-232">既定では、網掛け領域には、概要で選択した日付範囲フィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="45c47-232">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="45c47-233">クリックしてドラッグすると、特定の開始ポイントと終了ポイントを選択できます。この場合、次のセクションで説明するように、影響領域とページの残りの部分に表示されるデータが<u>変更</u>されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-233">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="45c47-234">タイトル バー ![ で、[キャンペーンの書き込みダウンロード] ボタン [キャンペーンの書き込みダウンロード] アイコンをクリックして、キャンペーンの詳細を Word ドキュメント (既定では CampaignReport.docx) にダウンロードできます ](../../media/download-campaign-write-up-button.png) 。</span><span class="sxs-lookup"><span data-stu-id="45c47-234">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="45c47-235">ダウンロードには、キャンペーンの有効期間全体に関する詳細が含まれています (選択したフィルター日付も含め)。</span><span class="sxs-lookup"><span data-stu-id="45c47-235">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="45c47-237">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="45c47-237">Campaign flow</span></span>

<span data-ttu-id="45c47-238">キャンペーンの詳細ビューの中央に、キャンペーンに関する重要な詳細が、水平方向のフロー図 (サンキー図と呼ばれる) の [フロー] セクション _に表示_ されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-238">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="45c47-239">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="45c47-239">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="45c47-240">フロー図に表示される情報は、前のセクションで説明したように、タイムラインの日付範囲の網掛けによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-240">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="45c47-242">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="45c47-242">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="45c47-243">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="45c47-243">The diagram contains the following information:</span></span>

- <span data-ttu-id="45c47-244">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-244">**Sender IPs**</span></span>
- <span data-ttu-id="45c47-245">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-245">**Sender domains**</span></span>
- <span data-ttu-id="45c47-246">**フィルターの条件**: Verdict の値は、「スパム対策メッセージ ヘッダー」で説明されている利用可能なフィッシングおよびスパム フィルターの条件 [に関連しています](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="45c47-246">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="45c47-247">使用可能な値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="45c47-247">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="45c47-248">値</span><span class="sxs-lookup"><span data-stu-id="45c47-248">Value</span></span>|<span data-ttu-id="45c47-249">スパム フィルターの確認</span><span class="sxs-lookup"><span data-stu-id="45c47-249">Spam filter verdict</span></span>|<span data-ttu-id="45c47-250">説明</span><span class="sxs-lookup"><span data-stu-id="45c47-250">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="45c47-251">**可**</span><span class="sxs-lookup"><span data-stu-id="45c47-251">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="45c47-252">スパム フィルターによって評価される前に、メッセージがスパムではないとマークされ、フィルター処理がスキップされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-252">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="45c47-253">たとえば、メッセージはメール フロー ルール (トランスポート ルールとも呼ばれる) によってスパムではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-253">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="45c47-254">メッセージは、その他の理由でスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="45c47-254">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="45c47-255">たとえば、送信者と受信者は同じ組織内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-255">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="45c47-256">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="45c47-256">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="45c47-257">スパム フィルターによって評価される前に、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-257">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="45c47-258">たとえば、メール フロー ルールで指定します。</span><span class="sxs-lookup"><span data-stu-id="45c47-258">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="45c47-259">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-259">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="45c47-260">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-260">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="45c47-261">**検出されない**</span><span class="sxs-lookup"><span data-stu-id="45c47-261">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="45c47-262">スパム フィルタリングによって、メッセージはスパムではないとマークされています。</span><span class="sxs-lookup"><span data-stu-id="45c47-262">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="45c47-263">**リリース済み**</span><span class="sxs-lookup"><span data-stu-id="45c47-263">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="45c47-264">メッセージは検疫から解放されたため、スパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="45c47-264">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="45c47-265">**テナントの許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="45c47-265">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="45c47-266">スパム対策ポリシーの設定のために、メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="45c47-266">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="45c47-267">たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧に含っていたとします。</span><span class="sxs-lookup"><span data-stu-id="45c47-267">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="45c47-268">**テナントブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="45c47-268">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="45c47-269">スパム対策ポリシーの設定により、メッセージはスパム フィルターによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-269">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="45c47-270">たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧に含っていたとします。</span><span class="sxs-lookup"><span data-stu-id="45c47-270">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="45c47-271">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="45c47-271">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="45c47-272">送信者がユーザーの差出人セーフ リストに含っていたため、メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="45c47-272">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="45c47-273">**ユーザー ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="45c47-273">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="45c47-274">送信者がユーザーの受信拒否リストに含っていたため、メッセージはスパム フィルターによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-274">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="45c47-275">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="45c47-275">**ZAP**</span></span>|<span data-ttu-id="45c47-276">該当なし</span><span class="sxs-lookup"><span data-stu-id="45c47-276">n/a</span></span>|<span data-ttu-id="45c47-277">[ゼロアワー自動消去 (ZAP)](zero-hour-auto-purge.md) は、配信されたメッセージを [迷惑メール] フォルダーまたは検疫に移動しました。</span><span class="sxs-lookup"><span data-stu-id="45c47-277">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="45c47-278">アクションはスパム対策ポリシーで構成します。</span><span class="sxs-lookup"><span data-stu-id="45c47-278">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="45c47-279"><sup>\*</sup> 許可されたメッセージがサービスによってブロックされている可能性が高いので、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="45c47-279"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="45c47-280"><sup>\*\*</sup> スパム対策ポリシーを確認します。これらのメッセージは検疫され、配信されない必要があります。</span><span class="sxs-lookup"><span data-stu-id="45c47-280"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="45c47-281">**配信場所**: ユーザーがメッセージのペイロード URL をクリックしなかった場合でも、受信者 (受信トレイまたは迷惑メール フォルダー) に配信されたメッセージを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45c47-281">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="45c47-282">検疫済みメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="45c47-282">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="45c47-283">詳細については [、「EOP での検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="45c47-283">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="45c47-284">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="45c47-284">**Deleted folder**</span></span>
  - <span data-ttu-id="45c47-285">**破棄**</span><span class="sxs-lookup"><span data-stu-id="45c47-285">**Dropped**</span></span>
  - <span data-ttu-id="45c47-286">**外部**: 受信者は、ハイブリッド環境のオンプレミスの電子メール組織にあります。</span><span class="sxs-lookup"><span data-stu-id="45c47-286">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="45c47-287">**Failed**</span><span class="sxs-lookup"><span data-stu-id="45c47-287">**Failed**</span></span>
  - <span data-ttu-id="45c47-288">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="45c47-288">**Forwarded**</span></span>
  - <span data-ttu-id="45c47-289">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-289">**Inbox**</span></span>
  - <span data-ttu-id="45c47-290">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-290">**Junk folder**</span></span>
  - <span data-ttu-id="45c47-291">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-291">**Quarantine**</span></span>
  - <span data-ttu-id="45c47-292">**不明**</span><span class="sxs-lookup"><span data-stu-id="45c47-292">**Unknown**</span></span>

- <span data-ttu-id="45c47-293">**URL クリック**: これらの値については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="45c47-293">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="45c47-294">10 を超えるアイテムを含むすべてのレイヤーでは、上位 10 項目が表示され、残りは [その他] にまとめて **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="45c47-294">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="45c47-295">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="45c47-295">URL clicks</span></span>

<span data-ttu-id="45c47-296">フィッシング メッセージが受信者の受信トレイまたは迷惑メール フォルダーに配信される場合、ユーザーがペイロード URL をクリックする可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="45c47-296">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="45c47-297">URL をクリックしないのは成功の小さな測定方法ですが、フィッシング メッセージがメールボックスに配信された理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45c47-297">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="45c47-298">ユーザーがフィッシング メッセージ内のペイロード URL をクリックすると、アクションがキャンペーンの詳細ビューの図の **URL** クリック領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-298">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="45c47-299">**可**</span><span class="sxs-lookup"><span data-stu-id="45c47-299">**Allowed**</span></span>
- <span data-ttu-id="45c47-300">**BlockPage**: 受信者がペイロード URL をクリックしましたが、悪意のある Web サイトへのアクセスが [](atp-safe-links.md)組織内の安全なリンク ポリシーによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="45c47-300">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="45c47-301">**BlockPageOverride**: 受信者がメッセージ内のペイロード URL をクリックし、安全なリンクでブロックを停止しようとしたが、ブロックを上書きする許可が与えらた。</span><span class="sxs-lookup"><span data-stu-id="45c47-301">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="45c47-302">安全な [リンクポリシーを](set-up-atp-safe-links-policies.md) 調して、ユーザーが安全なリンクの評価を上書きして悪意のある Web サイトに進む理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="45c47-302">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="45c47-303">**PendingDetonationPage**: Office 365 用の Microsoft Defender の安全な添付ファイルは、仮想コンピューター環境でペイロード URL を開いて調査中です。</span><span class="sxs-lookup"><span data-stu-id="45c47-303">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="45c47-304">**PendingDetonationPageOverride**: 受信者はペイロード分析プロセスを上書きし、結果を待たずに URL を開く許可を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="45c47-304">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="45c47-305">タブ</span><span class="sxs-lookup"><span data-stu-id="45c47-305">Tabs</span></span>

<span data-ttu-id="45c47-306">キャンペーンの詳細ビューのタブを使用すると、キャンペーンをさらに調査できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-306">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="45c47-307">タブに表示される情報は、「キャンペーン情報」セクションの説明に従って、タイムラインの日付範囲の網掛け [によって制御](#campaign-information) されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-307">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="45c47-308">**URL クリック**: ユーザーがメッセージ内のペイロード URL をクリックしなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="45c47-308">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="45c47-309">ユーザーが URL をクリックできた場合は、次の値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="45c47-309">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="45c47-310">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="45c47-310">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="45c47-311">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="45c47-311">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="45c47-312">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="45c47-312">**Click time**</span></span>
  - <span data-ttu-id="45c47-313">**[Verdict] をクリックする**</span><span class="sxs-lookup"><span data-stu-id="45c47-313">**Click verdict**</span></span>

- <span data-ttu-id="45c47-314">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-314">**Sender IPs**</span></span>
  - <span data-ttu-id="45c47-315">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="45c47-315">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="45c47-316">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="45c47-316">**Total count**</span></span>
  - <span data-ttu-id="45c47-317">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="45c47-317">**Inboxed**</span></span>
  - <span data-ttu-id="45c47-318">**受信トレイではない**</span><span class="sxs-lookup"><span data-stu-id="45c47-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="45c47-319">**SPF 渡** し : 送信者は [Sender Policy Framework (SPF) によって認証されました](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="45c47-319">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="45c47-320">SPF 検証に合格しない送信者は、認証されていない送信者を示します。または、メッセージが正当な送信者をスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="45c47-320">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="45c47-321">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-321">**Senders**</span></span>
  - <span data-ttu-id="45c47-322">**Sender**: これは SMTP MAIL FROM コマンドの実際の送信者アドレスで、ユーザーが電子メール クライアントに表示する From: 電子メール アドレスとは限りません。</span><span class="sxs-lookup"><span data-stu-id="45c47-322">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="45c47-323">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="45c47-323">**Total count**</span></span>
  - <span data-ttu-id="45c47-324">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="45c47-324">**Inboxed**</span></span>
  - <span data-ttu-id="45c47-325">**受信トレイではない**</span><span class="sxs-lookup"><span data-stu-id="45c47-325">**Not Inboxed**</span></span>
  - <span data-ttu-id="45c47-326">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="45c47-326">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="45c47-327">DKIM 検証に合格しない送信者は、認証されていない送信者を示します。または、メッセージが正当な送信者をスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="45c47-327">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="45c47-328">**DMARC 渡** し : 送信者は、ドメイン ベースのメッセージ認証、レポート、 [および適合 (DMARC) によって認証されました](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="45c47-328">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="45c47-329">DMARC 検証に合格しない送信者は、認証されていない送信者を示します。または、メッセージが正当な送信者をスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="45c47-329">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="45c47-330">**添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="45c47-330">**Attachments**</span></span>
  - <span data-ttu-id="45c47-331">**Filename**</span><span class="sxs-lookup"><span data-stu-id="45c47-331">**Filename**</span></span>
  - <span data-ttu-id="45c47-332">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="45c47-332">**SHA256**</span></span>
  - <span data-ttu-id="45c47-333">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="45c47-333">**Malware family**</span></span>
  - <span data-ttu-id="45c47-334">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="45c47-334">**Total count**</span></span>

- <span data-ttu-id="45c47-335">**URL**</span><span class="sxs-lookup"><span data-stu-id="45c47-335">**URL**</span></span>
  - <span data-ttu-id="45c47-336">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="45c47-336">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="45c47-337">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="45c47-337">**Total Count**</span></span>

<span data-ttu-id="45c47-338"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="45c47-338"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="45c47-339">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45c47-339">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="45c47-340">ボタン</span><span class="sxs-lookup"><span data-stu-id="45c47-340">Buttons</span></span>

<span data-ttu-id="45c47-341">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="45c47-341">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="45c47-342">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="45c47-342">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
- <span data-ttu-id="45c47-343">**受信トレイメッセージの確認**: キャンペーン **ID** と配信場所: 受信トレイを検索フィルターとして使用して、新しい脅威エクスプローラーの **検索タブを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="45c47-343">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
