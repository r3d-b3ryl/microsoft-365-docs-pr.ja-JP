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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 のキャンペーン ビューについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7742b26eb901bc9dfe79d01a9f3414adf524dd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286899"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="3e54b-103">Microsoft Defender for Office 365 のキャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="3e54b-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3e54b-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3e54b-104">**Applies to**</span></span>
- [<span data-ttu-id="3e54b-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="3e54b-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="3e54b-106">キャンペーン ビューは、Office 365 プラン 2 用の Microsoft Defender の機能です (たとえば、Microsoft 365 E5、または Office 365 プラン 2 アドオンの Defender を持つ組織)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-106">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="3e54b-107">セキュリティ/コンプライアンス センターの&ビューは、サービス内のフィッシング攻撃を識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-107">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="3e54b-108">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-108">Campaign Views can help you to:</span></span>

- <span data-ttu-id="3e54b-109">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="3e54b-109">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="3e54b-110">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="3e54b-110">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="3e54b-111">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="3e54b-111">Show value to decision makers.</span></span>

<span data-ttu-id="3e54b-112">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-112">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="3e54b-113">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="3e54b-113">What is a campaign?</span></span>

<span data-ttu-id="3e54b-114">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="3e54b-114">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="3e54b-115">資格情報と会社のデータを盗む電子メール攻撃は、大規模で収益性の高い業界です。</span><span class="sxs-lookup"><span data-stu-id="3e54b-115">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="3e54b-116">攻撃を止める取り組みのテクノロジが増えるに応じて、攻撃者は継続的な成功を保証するために方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-116">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="3e54b-117">Microsoft は、サービス全体にわたって膨大な量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンを特定します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-117">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="3e54b-118">攻撃情報を分析し、いくつかの要因に従って分類します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-118">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="3e54b-119">例:</span><span class="sxs-lookup"><span data-stu-id="3e54b-119">For example:</span></span>

- <span data-ttu-id="3e54b-120">**攻撃元**: 送信元 IP アドレスと送信者の電子メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="3e54b-120">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="3e54b-121">**メッセージの** プロパティ : メッセージのコンテンツ、スタイル、およびトーン。</span><span class="sxs-lookup"><span data-stu-id="3e54b-121">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="3e54b-122">**メッセージ受信者**: 受信者の関連付け。</span><span class="sxs-lookup"><span data-stu-id="3e54b-122">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="3e54b-123">たとえば、受信者ドメイン、受信者の仕事の機能 (管理者、役員など)、会社の種類 (大規模、小規模、パブリック、プライベートなど)、業界などです。</span><span class="sxs-lookup"><span data-stu-id="3e54b-123">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="3e54b-124">**攻撃ペイロード**: メッセージ内の悪意のあるリンク、添付ファイル、または他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="3e54b-124">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="3e54b-125">キャンペーンの期間が短い場合や、アクティブ期間と非アクティブ期間がある数日、数週間、または月に及んでいる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-125">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="3e54b-126">特定の組織に対してキャンペーンが開始される場合や、組織が複数の企業で大規模なキャンペーンの一部である場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-126">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="3e54b-127">セキュリティ/コンプライアンス センター&ビュー</span><span class="sxs-lookup"><span data-stu-id="3e54b-127">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="3e54b-128">キャンペーン ビューは、セキュリティ/コンプライアンス [センターの&](https://protection.office.com)**管理キャンペーンで**、または直接 \> 利用できます <https://protection.office.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="3e54b-128">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="3e54b-130">次の場所からキャンペーン ビューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-130">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="3e54b-131">**脅威の管理** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="3e54b-131">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="3e54b-132">**脅威の管理** \>**エクスプローラー** \>**表示** \>**すべてのメール** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="3e54b-132">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="3e54b-133">**脅威の管理** \>**エクスプローラー** \>**表示** \>**フィッシング** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="3e54b-133">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="3e54b-134">**脅威の管理** \>**エクスプローラー** \>**表示** \>**マルウェア** \>**[キャンペーン]** タブ</span><span class="sxs-lookup"><span data-stu-id="3e54b-134">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="3e54b-135">キャンペーン ビューにアクセスするには、セキュリティ/コンプライアンス センターの組織の管理、セキュリティ管理者、またはセキュリティ閲覧者の役割グループの&必要があります。 </span><span class="sxs-lookup"><span data-stu-id="3e54b-135">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="3e54b-136">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e54b-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="3e54b-137">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="3e54b-137">Campaigns overview</span></span>

<span data-ttu-id="3e54b-138">概要ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-138">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="3e54b-139">既定の [ **キャンペーン]** タブの [ **キャンペーンの種類** ] 領域には、1 日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-139">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="3e54b-140">既定では、グラフにはフィッシングデータと **マルウェア データの両方\*\*\*\*が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-140">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="3e54b-141">キャンペーン データが表示しない場合は、日付範囲またはフィルターを変更 [してみてください](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-141">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="3e54b-142">概要ページの残りの部分では、[キャンペーン] タブに次の情報 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-142">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="3e54b-143">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-143">**Name**</span></span>

- <span data-ttu-id="3e54b-144">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="3e54b-144">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="3e54b-145">キャンペーン内のすべてのメッセージの件名が同じとは限りません。</span><span class="sxs-lookup"><span data-stu-id="3e54b-145">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="3e54b-146">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算された割合。</span><span class="sxs-lookup"><span data-stu-id="3e54b-146">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="3e54b-147">この値は、キャンペーンが組織に対してどの程度向けられるか (より高い値) か、サービス内の他の組織 (より低い値) に向けられているかを示します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-147">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="3e54b-148">**型**: この値は **、Phish** または **Malware です**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-148">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="3e54b-149">**サブ** タイプ : この値には、キャンペーンに関する詳細が含まれる。</span><span class="sxs-lookup"><span data-stu-id="3e54b-149">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="3e54b-150">例:</span><span class="sxs-lookup"><span data-stu-id="3e54b-150">For example:</span></span>
  - <span data-ttu-id="3e54b-151">**フィッシング**: 利用可能な場合、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="3e54b-151">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="3e54b-152">たとえば、, `Microsoft` `365` , , , or `Unknown` `Outlook` `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="3e54b-152">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="3e54b-153">**マルウェア**: たとえば `HTML/PHISH` 、または `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="3e54b-153">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="3e54b-154">利用可能な場合、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="3e54b-154">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="3e54b-155">検出が Defender によって Office 365 テクノロジに対して実行される場合、プレフィックス **ATP が** サブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-155">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="3e54b-156">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-156">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="3e54b-157">**受信トレイ**: 受信トレイでこのキャンペーンからメッセージを受信したユーザーの数 (迷惑メール フォルダーには配信されません)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-157">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="3e54b-158">**Clicked**: URL をクリックしたユーザー数、またはフィッシング メッセージで添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-158">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="3e54b-159">**クリックレート**: [受信トレイのクリック数]**で計算された**  /  **パーセンテージ。**</span><span class="sxs-lookup"><span data-stu-id="3e54b-159">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="3e54b-160">この値は、キャンペーンの効果を示す指標です。</span><span class="sxs-lookup"><span data-stu-id="3e54b-160">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="3e54b-161">つまり、受信者がメッセージをフィッシングとして識別できた場合、および受信者がペイロード URL をクリックしなかった場合。</span><span class="sxs-lookup"><span data-stu-id="3e54b-161">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="3e54b-162">クリック率 **は** マルウェア キャンペーンでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="3e54b-162">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="3e54b-163">**アクセス:** 実際にペイロード Web サイトにアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-163">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="3e54b-164">クリックされた値 **がある** が、安全なリンクが Web サイトへのアクセスをブロックしている場合、この値はゼロになります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-164">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="3e54b-165">[ **キャンペーンの発生** 元] タブには、世界の地図にメッセージ ソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-165">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="3e54b-166">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="3e54b-166">Filters and settings</span></span>

<span data-ttu-id="3e54b-167">[キャンペーン ビュー] ページの上部には、特定のキャンペーンを見つけて切り離すのに役立つフィルターとクエリの設定がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-167">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーン フィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="3e54b-169">最も基本的なフィルター処理は、開始日時と終了日時です。</span><span class="sxs-lookup"><span data-stu-id="3e54b-169">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="3e54b-170">ビューをさらにフィルター処理するには、[キャンペーンの種類] ボタンをクリックして選択し、[更新]をクリックして、複数の値をフィルター処理する単一のプロパティを **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-170">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="3e54b-171">[キャンペーンの種類] ボタンで利用できるフィルター処理可能な **キャンペーン** のプロパティについて、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-171">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="3e54b-172">**基本**:</span><span class="sxs-lookup"><span data-stu-id="3e54b-172">**Basic**:</span></span>
  - <span data-ttu-id="3e54b-173">**キャンペーンの種類**: [ **マルウェアまたはフィッシング]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-173">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="3e54b-174">選択をクリアすると、両方を選択した場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-174">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="3e54b-175">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="3e54b-175">**Campaign name**</span></span>
  - <span data-ttu-id="3e54b-176">**キャンペーンのサブタイプ**</span><span class="sxs-lookup"><span data-stu-id="3e54b-176">**Campaign subtype**</span></span>
  - <span data-ttu-id="3e54b-177">**送信者**</span><span class="sxs-lookup"><span data-stu-id="3e54b-177">**Sender**</span></span>
  - <span data-ttu-id="3e54b-178">**受信者**</span><span class="sxs-lookup"><span data-stu-id="3e54b-178">**Recipients**</span></span>
  - <span data-ttu-id="3e54b-179">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="3e54b-179">**Sender domain**</span></span>
  - <span data-ttu-id="3e54b-180">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="3e54b-180">**Subject**</span></span>
  - <span data-ttu-id="3e54b-181">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="3e54b-181">**Attachment filename**</span></span>
  - <span data-ttu-id="3e54b-182">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="3e54b-182">**Malware family**</span></span>
  - <span data-ttu-id="3e54b-183">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-183">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="3e54b-184">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-184">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="3e54b-185">**システム オーバーライド**</span><span class="sxs-lookup"><span data-stu-id="3e54b-185">**System overrides**</span></span>
  - <span data-ttu-id="3e54b-186">**配信アクション**</span><span class="sxs-lookup"><span data-stu-id="3e54b-186">**Delivery action**</span></span>
  - <span data-ttu-id="3e54b-187">**追加アクション**</span><span class="sxs-lookup"><span data-stu-id="3e54b-187">**Additional action**</span></span>
  - <span data-ttu-id="3e54b-188">**方向性**</span><span class="sxs-lookup"><span data-stu-id="3e54b-188">**Directionality**</span></span>
  - <span data-ttu-id="3e54b-189">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="3e54b-189">**Detection technology**</span></span>
  - <span data-ttu-id="3e54b-190">**元の配信場所**</span><span class="sxs-lookup"><span data-stu-id="3e54b-190">**Original delivery location**</span></span>
  - <span data-ttu-id="3e54b-191">**最新の配信場所**</span><span class="sxs-lookup"><span data-stu-id="3e54b-191">**Latest delivery location**</span></span>
  - <span data-ttu-id="3e54b-192">**システム オーバーライド**</span><span class="sxs-lookup"><span data-stu-id="3e54b-192">**System overrides**</span></span>

- <span data-ttu-id="3e54b-193">**詳細設定**:</span><span class="sxs-lookup"><span data-stu-id="3e54b-193">**Advanced**:</span></span>
  - <span data-ttu-id="3e54b-194">**インターネット メッセージ ID**: メッセージ ヘッダーの **Message-ID** ヘッダー フィールドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-194">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="3e54b-195">値の例を `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次に示します (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-195">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="3e54b-196">**ネットワーク メッセージ ID**: メッセージ ヘッダーの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー フィールドで使用できる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="3e54b-196">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="3e54b-197">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-197">**Sender IP**</span></span>
  - <span data-ttu-id="3e54b-198">**添付ファイル SHA256**: Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="3e54b-198">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="3e54b-199">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="3e54b-199">**Cluster ID**</span></span>
  - <span data-ttu-id="3e54b-200">**アラート ポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="3e54b-200">**Alert Policy ID**</span></span>
  - <span data-ttu-id="3e54b-201">**ZAP URL シグナル**</span><span class="sxs-lookup"><span data-stu-id="3e54b-201">**ZAP URL signal**</span></span>

- <span data-ttu-id="3e54b-202">**URL**:</span><span class="sxs-lookup"><span data-stu-id="3e54b-202">**URLs**:</span></span>
  - <span data-ttu-id="3e54b-203">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="3e54b-203">**URL domain**</span></span>
  - <span data-ttu-id="3e54b-204">**URL ドメインとパス**</span><span class="sxs-lookup"><span data-stu-id="3e54b-204">**URL domain and path**</span></span>
  - <span data-ttu-id="3e54b-205">**URL**</span><span class="sxs-lookup"><span data-stu-id="3e54b-205">**URL**</span></span>
  - <span data-ttu-id="3e54b-206">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="3e54b-206">**URL path**</span></span>
  - <span data-ttu-id="3e54b-207">**[Verdict] をクリックする**</span><span class="sxs-lookup"><span data-stu-id="3e54b-207">**Click verdict**</span></span>

<span data-ttu-id="3e54b-208">複数のプロパティによるフィルター処理など、より高度なフィルター処理を行う場合は、[詳細フィルター] ボタンをクリックしてクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-208">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="3e54b-209">同じキャンペーン プロパティを使用できますが、次の拡張機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="3e54b-209">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="3e54b-210">[条件の追加 **] をクリックすると、** 複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-210">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="3e54b-211">条件の間で **And** 演算子 **または Or 演算子** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-211">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="3e54b-212">条件リストの下部 **にある条件グループ** 項目を選択すると、複雑な複合条件を形成できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-212">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="3e54b-213">完了したら、[クエリ] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-213">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="3e54b-214">基本フィルターまたは高度なフィルターを作成した後は、[クエリの保存] または [名前を付けて保存] を **使用して保存できます**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-214">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="3e54b-215">後で、キャンペーン ビューに戻る際に、[保存済み] クエリ設定をクリックして、保存済み **フィルターを読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-215">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="3e54b-216">グラフまたはキャンペーンの一覧をエクスポートするには、[エクスポート]をクリックし、[グラフ データのエクスポート] または [キャンペーン 一覧のエクスポート]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-216">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="3e54b-217">Microsoft Defender for Endpoint サブスクリプションをお持ちのお客様は **、MDE** 設定をクリックして、Microsoft Defender for Endpoint にキャンペーン情報を接続または切断できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-217">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3e54b-218">詳しくは、「Microsoft [Defender for Office 365](integrate-office-365-ti-with-wdatp.md)と Microsoft Defender for Endpoint の統合」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e54b-218">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="3e54b-219">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="3e54b-219">Campaign details</span></span>

<span data-ttu-id="3e54b-220">キャンペーンの名前をクリックすると、キャンペーンの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-220">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="3e54b-221">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="3e54b-221">Campaign information</span></span>

<span data-ttu-id="3e54b-222">キャンペーンの詳細ビューの上部に、次のキャンペーン情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-222">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="3e54b-223">**ID**: 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="3e54b-223">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="3e54b-224">**開始** および **終了**: キャンペーンの開始日と終了日。</span><span class="sxs-lookup"><span data-stu-id="3e54b-224">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="3e54b-225">これらの日付は、概要ページで選択したフィルター日付よりも延長される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-225">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="3e54b-226">**影響**: このセクションには、選択した日付範囲フィルター (またはタイムラインで選択した) に関する次のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-226">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  - <span data-ttu-id="3e54b-227">受信者の総数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-227">The total number of recipients.</span></span>
  - <span data-ttu-id="3e54b-228">"受信トレイ" (迷惑メール フォルダーではなく受信トレイに配信された) メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-228">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="3e54b-229">フィッシング メッセージの URL ペイロードをクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-229">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="3e54b-230">URL にアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="3e54b-230">Howe many users visited the URL.</span></span>

- <span data-ttu-id="3e54b-231">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算された割合。</span><span class="sxs-lookup"><span data-stu-id="3e54b-231">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="3e54b-232">この値はキャンペーンの有効期間全体で計算され、日付フィルターに基づいて変化しない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e54b-232">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="3e54b-233">キャンペーン アクティビティの対話型のタイムライン: タイムラインには、キャンペーンの全期間のアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-233">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="3e54b-234">既定では、網掛け領域には、概要で選択した日付範囲フィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-234">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="3e54b-235">クリックしてドラッグすると、特定の開始ポイントと終了ポイントを選択できます。この場合、次のセクションで説明するように、影響領域とページの残りの部分に表示されるデータが<u>変更</u>されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-235">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="3e54b-236">タイトル バー ![ で、[キャンペーンの書き込みダウンロード] ボタン [キャンペーンの書き込みダウンロード] アイコンをクリックして、キャンペーンの詳細を Word ドキュメント (既定では CampaignReport.docx) にダウンロードできます ](../../media/download-campaign-write-up-button.png) 。</span><span class="sxs-lookup"><span data-stu-id="3e54b-236">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="3e54b-237">ダウンロードには、キャンペーンの有効期間全体に関する詳細が含まれています (選択したフィルター日付も含め)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-237">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="3e54b-239">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="3e54b-239">Campaign flow</span></span>

<span data-ttu-id="3e54b-240">キャンペーンの詳細ビューの中央に、キャンペーンに関する重要な詳細が、水平方向のフロー図 (サンキー図と呼ばれる) の [フロー] セクション _に表示_ されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-240">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="3e54b-241">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-241">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="3e54b-242">フロー図に表示される情報は、前のセクションで説明したように、タイムラインの日付範囲の網掛けによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-242">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="3e54b-244">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-244">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="3e54b-245">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-245">The diagram contains the following information:</span></span>

- <span data-ttu-id="3e54b-246">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-246">**Sender IPs**</span></span>
- <span data-ttu-id="3e54b-247">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-247">**Sender domains**</span></span>
- <span data-ttu-id="3e54b-248">**フィルターの条件**: Verdict の値は、「スパム対策メッセージ ヘッダー」で説明されている利用可能なフィッシングおよびスパム フィルターの条件 [に関連しています](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-248">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="3e54b-249">使用可能な値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-249">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="3e54b-250">値</span><span class="sxs-lookup"><span data-stu-id="3e54b-250">Value</span></span>|<span data-ttu-id="3e54b-251">スパム フィルターの確認</span><span class="sxs-lookup"><span data-stu-id="3e54b-251">Spam filter verdict</span></span>|<span data-ttu-id="3e54b-252">説明</span><span class="sxs-lookup"><span data-stu-id="3e54b-252">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="3e54b-253">**可**</span><span class="sxs-lookup"><span data-stu-id="3e54b-253">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="3e54b-254">スパム フィルターによって評価される前に、メッセージがスパムではないとマークされ、フィルター処理がスキップされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-254">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="3e54b-255">たとえば、メッセージはメール フロー ルール (トランスポート ルールとも呼ばれる) によってスパムではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-255">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="3e54b-256">メッセージは、その他の理由でスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-256">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="3e54b-257">たとえば、送信者と受信者は同じ組織内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-257">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="3e54b-258">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="3e54b-258">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="3e54b-259">スパム フィルターによって評価される前に、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-259">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="3e54b-260">たとえば、メール フロー ルールで指定します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-260">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="3e54b-261">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-261">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="3e54b-262">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-262">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="3e54b-263">**検出されない**</span><span class="sxs-lookup"><span data-stu-id="3e54b-263">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="3e54b-264">スパム フィルタリングによって、メッセージはスパムではないとマークされています。</span><span class="sxs-lookup"><span data-stu-id="3e54b-264">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="3e54b-265">**リリース済み**</span><span class="sxs-lookup"><span data-stu-id="3e54b-265">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="3e54b-266">メッセージは検疫から解放されたため、スパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-266">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="3e54b-267">**テナントの許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e54b-267">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="3e54b-268">スパム対策ポリシーの設定のために、メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-268">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="3e54b-269">たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧に含っていたとします。</span><span class="sxs-lookup"><span data-stu-id="3e54b-269">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="3e54b-270">**テナントブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e54b-270">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="3e54b-271">スパム対策ポリシーの設定により、メッセージはスパム フィルターによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-271">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="3e54b-272">たとえば、送信者が許可された送信者の一覧または許可されたドメインの一覧に含っていたとします。</span><span class="sxs-lookup"><span data-stu-id="3e54b-272">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="3e54b-273">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e54b-273">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="3e54b-274">送信者がユーザーの差出人セーフ リストに含っていたため、メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-274">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="3e54b-275">**ユーザー ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e54b-275">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="3e54b-276">送信者がユーザーの受信拒否リストに含っていたため、メッセージはスパム フィルターによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-276">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="3e54b-277">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="3e54b-277">**ZAP**</span></span>|<span data-ttu-id="3e54b-278">該当なし</span><span class="sxs-lookup"><span data-stu-id="3e54b-278">n/a</span></span>|<span data-ttu-id="3e54b-279">[ゼロアワー自動消去 (ZAP)](zero-hour-auto-purge.md) は、配信されたメッセージを [迷惑メール] フォルダーまたは検疫に移動しました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-279">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="3e54b-280">アクションはスパム対策ポリシーで構成します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-280">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="3e54b-281"><sup>\*</sup> 許可されたメッセージがサービスによってブロックされている可能性が高いので、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-281"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="3e54b-282"><sup>\*\*</sup> スパム対策ポリシーを確認します。これらのメッセージは検疫され、配信されない必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-282"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="3e54b-283">**配信場所**: ユーザーがメッセージのペイロード URL をクリックしなかった場合でも、受信者 (受信トレイまたは迷惑メール フォルダー) に配信されたメッセージを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-283">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="3e54b-284">検疫済みメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-284">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="3e54b-285">詳細については [、「EOP での検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-285">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="3e54b-286">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="3e54b-286">**Deleted folder**</span></span>
  - <span data-ttu-id="3e54b-287">**破棄**</span><span class="sxs-lookup"><span data-stu-id="3e54b-287">**Dropped**</span></span>
  - <span data-ttu-id="3e54b-288">**外部**: 受信者は、ハイブリッド環境のオンプレミスの電子メール組織にあります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-288">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="3e54b-289">**Failed**</span><span class="sxs-lookup"><span data-stu-id="3e54b-289">**Failed**</span></span>
  - <span data-ttu-id="3e54b-290">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="3e54b-290">**Forwarded**</span></span>
  - <span data-ttu-id="3e54b-291">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-291">**Inbox**</span></span>
  - <span data-ttu-id="3e54b-292">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-292">**Junk folder**</span></span>
  - <span data-ttu-id="3e54b-293">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-293">**Quarantine**</span></span>
  - <span data-ttu-id="3e54b-294">**不明**</span><span class="sxs-lookup"><span data-stu-id="3e54b-294">**Unknown**</span></span>

- <span data-ttu-id="3e54b-295">**URL クリック**: これらの値については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-295">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="3e54b-296">10 を超えるアイテムを含むすべてのレイヤーでは、上位 10 項目が表示され、残りは [その他] にまとめて **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="3e54b-296">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="3e54b-297">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="3e54b-297">URL clicks</span></span>

<span data-ttu-id="3e54b-298">フィッシング メッセージが受信者の受信トレイまたは迷惑メール フォルダーに配信される場合、ユーザーがペイロード URL をクリックする可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-298">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="3e54b-299">URL をクリックしないのは成功の小さな測定方法ですが、フィッシング メッセージがメールボックスに配信された理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-299">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="3e54b-300">ユーザーがフィッシング メッセージのペイロード URL をクリックすると、アクションがキャンペーンの詳細ビューの図の **URL** クリック領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-300">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="3e54b-301">**可**</span><span class="sxs-lookup"><span data-stu-id="3e54b-301">**Allowed**</span></span>
- <span data-ttu-id="3e54b-302">**BlockPage**: 受信者がペイロード URL をクリックしましたが、悪意のある Web サイトへのアクセスが [](atp-safe-links.md)組織内の安全なリンク ポリシーによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-302">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="3e54b-303">**BlockPageOverride**: 受信者がメッセージ内のペイロード URL をクリックし、安全なリンクでブロックを停止しようとしたが、ブロックを上書きする許可が与えらた。</span><span class="sxs-lookup"><span data-stu-id="3e54b-303">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="3e54b-304">「安全 [なリンク」ポリシー](set-up-atp-safe-links-policies.md) を検査して、ユーザーが安全なリンクの評価を上書きして悪意のある Web サイトに進む理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="3e54b-304">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="3e54b-305">**PendingDetonationPage**: Office 365 の Microsoft Defender の安全な添付ファイルは、仮想コンピューター環境でペイロード URL を開いて調査中です。</span><span class="sxs-lookup"><span data-stu-id="3e54b-305">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="3e54b-306">**PendingDetonationPageOverride**: 受信者はペイロード分析プロセスを上書きし、結果を待たずに URL を開く許可を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="3e54b-306">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="3e54b-307">タブ</span><span class="sxs-lookup"><span data-stu-id="3e54b-307">Tabs</span></span>

<span data-ttu-id="3e54b-308">キャンペーンの詳細ビューのタブを使用すると、キャンペーンをさらに調査できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-308">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="3e54b-309">タブに表示される情報は、「キャンペーン情報」セクションの説明に従って、タイムラインの日付範囲の網掛け [によって制御](#campaign-information) されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-309">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="3e54b-310">**URL クリック**: ユーザーがメッセージ内のペイロード URL をクリックしなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="3e54b-310">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="3e54b-311">ユーザーが URL をクリックできた場合は、次の値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-311">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="3e54b-312">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="3e54b-312">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="3e54b-313">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="3e54b-313">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="3e54b-314">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="3e54b-314">**Click time**</span></span>
  - <span data-ttu-id="3e54b-315">**[Verdict] をクリックする**</span><span class="sxs-lookup"><span data-stu-id="3e54b-315">**Click verdict**</span></span>

- <span data-ttu-id="3e54b-316">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-316">**Sender IPs**</span></span>
  - <span data-ttu-id="3e54b-317">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="3e54b-317">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="3e54b-318">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="3e54b-318">**Total count**</span></span>
  - <span data-ttu-id="3e54b-319">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="3e54b-319">**Inboxed**</span></span>
  - <span data-ttu-id="3e54b-320">**受信トレイに含めない**</span><span class="sxs-lookup"><span data-stu-id="3e54b-320">**Not Inboxed**</span></span>
  - <span data-ttu-id="3e54b-321">**SPF 渡** し : 送信者は [Sender Policy Framework (SPF) によって認証されました](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-321">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="3e54b-322">SPF 検証に合格しない送信者は、認証されていない送信者を示します。または、メッセージが正当な送信者をスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="3e54b-322">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="3e54b-323">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-323">**Senders**</span></span>
  - <span data-ttu-id="3e54b-324">**Sender**: これは SMTP MAIL FROM コマンドの実際の送信者アドレスで、必ずしもユーザーの電子メール クライアントに表示される From: 電子メール アドレスではありません。</span><span class="sxs-lookup"><span data-stu-id="3e54b-324">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="3e54b-325">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="3e54b-325">**Total count**</span></span>
  - <span data-ttu-id="3e54b-326">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="3e54b-326">**Inboxed**</span></span>
  - <span data-ttu-id="3e54b-327">**受信トレイに含めない**</span><span class="sxs-lookup"><span data-stu-id="3e54b-327">**Not Inboxed**</span></span>
  - <span data-ttu-id="3e54b-328">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="3e54b-328">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="3e54b-329">DKIM 検証に合格しない送信者は、認証されていない送信者を示します。または、メッセージが正当な送信者をスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="3e54b-329">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="3e54b-330">**DMARC 渡** し : 送信者は、ドメイン ベースのメッセージ認証、レポート、 [および適合 (DMARC) によって認証されました](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="3e54b-330">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="3e54b-331">DMARC 検証に合格しない送信者は、認証されていない送信者を示します。または、メッセージが正当な送信者をスプーフィングしています。</span><span class="sxs-lookup"><span data-stu-id="3e54b-331">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="3e54b-332">**添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="3e54b-332">**Attachments**</span></span>
  - <span data-ttu-id="3e54b-333">**Filename**</span><span class="sxs-lookup"><span data-stu-id="3e54b-333">**Filename**</span></span>
  - <span data-ttu-id="3e54b-334">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="3e54b-334">**SHA256**</span></span>
  - <span data-ttu-id="3e54b-335">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="3e54b-335">**Malware family**</span></span>
  - <span data-ttu-id="3e54b-336">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="3e54b-336">**Total count**</span></span>

- <span data-ttu-id="3e54b-337">**URL**</span><span class="sxs-lookup"><span data-stu-id="3e54b-337">**URL**</span></span>
  - <span data-ttu-id="3e54b-338">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="3e54b-338">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="3e54b-339">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="3e54b-339">**Total Count**</span></span>

<span data-ttu-id="3e54b-340"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-340"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="3e54b-341">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e54b-341">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="3e54b-342">ボタン</span><span class="sxs-lookup"><span data-stu-id="3e54b-342">Buttons</span></span>

<span data-ttu-id="3e54b-343">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-343">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="3e54b-344">[**Explore campaign (キャンペーンの調査)**]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-344">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
- <span data-ttu-id="3e54b-345">**受信トレイメッセージの確認**: キャンペーン **ID** と配信場所: 受信トレイを検索フィルターとして使用して、新しい脅威エクスプローラーの **検索タブを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="3e54b-345">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
