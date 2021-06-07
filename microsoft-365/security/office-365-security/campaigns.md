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
ms.openlocfilehash: 04e3d76271e95d36d73dd473076029cb60c06900
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779473"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c7d20-103">Microsoft Defender のキャンペーン ビュー (Office 365</span><span class="sxs-lookup"><span data-stu-id="c7d20-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c7d20-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c7d20-104">**Applies to**</span></span>
- [<span data-ttu-id="c7d20-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="c7d20-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="c7d20-106">キャンペーン ビューは、Microsoft Defender for Office 365 プラン 2 の機能です (たとえば、Microsoft 365 E5 または Office 365 プラン 2 アドオンの Defender を持つ組織)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-106">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example, Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="c7d20-107">セキュリティ センターのキャンペーン ビュー Microsoft 365、サービス内のフィッシング攻撃を識別して分類します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-107">Campaign Views in the Microsoft 365 security center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="c7d20-108">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-108">Campaign Views can help you to:</span></span>

- <span data-ttu-id="c7d20-109">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="c7d20-109">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="c7d20-110">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="c7d20-110">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="c7d20-111">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="c7d20-111">Show value to decision makers.</span></span>

<span data-ttu-id="c7d20-112">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-112">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="c7d20-113">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="c7d20-113">What is a campaign?</span></span>

<span data-ttu-id="c7d20-114">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="c7d20-114">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="c7d20-115">資格情報と会社のデータを盗む電子メール攻撃は、大規模で収益性の高い業界です。</span><span class="sxs-lookup"><span data-stu-id="c7d20-115">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="c7d20-116">攻撃を止めようとするテクノロジが増加する中、攻撃者は継続的な成功を確実に実現するためにメソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-116">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="c7d20-117">Microsoft は、サービス全体で膨大な量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンの特定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-117">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="c7d20-118">攻撃情報を分析し、いくつかの要因に従って分類します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-118">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="c7d20-119">例:</span><span class="sxs-lookup"><span data-stu-id="c7d20-119">For example:</span></span>

- <span data-ttu-id="c7d20-120">**攻撃元**: 送信元 IP アドレスと送信者メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="c7d20-120">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="c7d20-121">**メッセージのプロパティ**: メッセージのコンテンツ、スタイル、トーン。</span><span class="sxs-lookup"><span data-stu-id="c7d20-121">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="c7d20-122">**メッセージ受信者**: 受信者の関連付け方法。</span><span class="sxs-lookup"><span data-stu-id="c7d20-122">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="c7d20-123">たとえば、受信者ドメイン、受信者のジョブ機能 (管理者、役員など)、会社の種類 (大、小規模、パブリック、プライベートなど)、業種などです。</span><span class="sxs-lookup"><span data-stu-id="c7d20-123">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="c7d20-124">**攻撃ペイロード**: メッセージ内の悪意のあるリンク、添付ファイル、または他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="c7d20-124">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="c7d20-125">キャンペーンの期間が短い場合や、アクティブな期間と非アクティブな期間がある数日、数週間、または数か月に及んでいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-125">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="c7d20-126">特定の組織に対してキャンペーンが開始される場合や、組織が複数の企業で大規模なキャンペーンに参加している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-126">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security-center"></a><span data-ttu-id="c7d20-127">セキュリティ センターのキャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="c7d20-127">Campaign Views in the security center</span></span>

<span data-ttu-id="c7d20-128">キャンペーン ビューは、メール[Microsoft 365コラボレーション](https://security.microsoft.com)キャンペーンの&で直接 \> 使用できます <https://security.microsoft.com/campaigns> 。</span><span class="sxs-lookup"><span data-stu-id="c7d20-128">Campaign Views is available in the [Microsoft 365 security center](https://security.microsoft.com) at **Email & collaboration** \> **Campaigns**, or directly at <https://security.microsoft.com/campaigns>.</span></span>

![セキュリティ センターのMicrosoft 365概要](../../media/campaigns-overview.png)

<span data-ttu-id="c7d20-130">また、次の場所からキャンペーン ビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-130">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="c7d20-131">**メール&コラボレーション** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="c7d20-131">**Email & collaboration** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="c7d20-132">**メール&コラボレーション** \>**エクスプローラー** \>**表示** \>**すべてのメール** \>**[キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="c7d20-132">**Email & collaboration** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="c7d20-133">**メール&コラボレーション** \>**エクスプローラー** \>**表示** \>**フィッシング** \>**[キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="c7d20-133">**Email & collaboration** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="c7d20-134">**メール&コラボレーション** \>**エクスプローラー** \>**表示** \>**マルウェア** \>**[キャンペーン**] タブ</span><span class="sxs-lookup"><span data-stu-id="c7d20-134">**Email & collaboration** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="c7d20-135">キャンペーン ビューにアクセスするには、セキュリティ センターの組織の管理、セキュリティ管理者、または **セキュリティ** リーダーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-135">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the security center.</span></span> <span data-ttu-id="c7d20-136">詳細については、「コンプライアンス センターとセキュリティ センターの[Microsoft 365アクセス許可Microsoft 365参照してください](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-136">For more information, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="c7d20-137">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="c7d20-137">Campaigns overview</span></span>

<span data-ttu-id="c7d20-138">[概要] ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-138">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="c7d20-139">既定の [ **キャンペーン] タブ** の [ **キャンペーン** の種類] 領域には、1 日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-139">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="c7d20-140">既定では、グラフにはフィッシング データと **マルウェア データの\*\*\*\*両方が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-140">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="c7d20-141">キャンペーン データが表示しない場合は、日付範囲またはフィルターを変更 [してみてください](#filters-and-settings)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-141">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="c7d20-142">概要ページのグラフの下の表に、[キャンペーン] タブに次の情報 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-142">The table below the graph on the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="c7d20-143">[**Name (名前)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-143">**Name**</span></span>

- <span data-ttu-id="c7d20-144">[**Sample subject (件名のサンプル)**]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="c7d20-144">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="c7d20-145">キャンペーン内のすべてのメッセージに、必ずしも同じ件名が設定されているわけではない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7d20-145">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="c7d20-146">**対象**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算される割合。</span><span class="sxs-lookup"><span data-stu-id="c7d20-146">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="c7d20-147">この値は、キャンペーンが組織にのみ向けられる度合い (より高い値) と、サービス内の他の組織 (より低い値) に向けられる度合いを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-147">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="c7d20-148">**種類**: この値は、**フィッシングまたはマルウェア\*\*\*\*のいずれかです**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-148">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="c7d20-149">**サブ** タイプ : この値には、キャンペーンの詳細が含まれる。</span><span class="sxs-lookup"><span data-stu-id="c7d20-149">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="c7d20-150">例:</span><span class="sxs-lookup"><span data-stu-id="c7d20-150">For example:</span></span>
  - <span data-ttu-id="c7d20-151">**フィッシング**: 利用可能な場合は、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="c7d20-151">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="c7d20-152">たとえば `Microsoft` `365` `Unknown` 、、、、、、、 `Outlook` `DocuSign` などです。</span><span class="sxs-lookup"><span data-stu-id="c7d20-152">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="c7d20-153">**マルウェア**: たとえば、 `HTML/PHISH` または `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="c7d20-153">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="c7d20-154">利用可能な場合、このキャンペーンによってフィッシングされているブランド。</span><span class="sxs-lookup"><span data-stu-id="c7d20-154">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="c7d20-155">検出が Defender によって実行され、Office 365される場合は、プレフィックス **ATP-** がサブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-155">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="c7d20-156">[**Recipients (受信者)**]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-156">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="c7d20-157">**受信トレイ**: 受信トレイでこのキャンペーンからメッセージを受信したユーザーの数 (迷惑メール フォルダーに配信されません)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-157">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="c7d20-158">**クリック :** URL をクリックしたユーザーまたはフィッシング メッセージで添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-158">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="c7d20-159">**クリック率**: " Clicked Inboxed " によって **計算された**  /  **割合**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-159">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="c7d20-160">この値は、キャンペーンの効果を示す指標です。</span><span class="sxs-lookup"><span data-stu-id="c7d20-160">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="c7d20-161">つまり、受信者がメッセージをフィッシングとして識別できた場合、およびペイロード URL をクリックしなかった場合。</span><span class="sxs-lookup"><span data-stu-id="c7d20-161">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="c7d20-162">マルウェア キャンペーン **では** クリック率は使用されません。</span><span class="sxs-lookup"><span data-stu-id="c7d20-162">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="c7d20-163">**アクセス数**: ペイロード Web サイトに実際にアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-163">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="c7d20-164">クリックされた値 **が含** まれるが、[リンクセーフ Web サイトへのアクセスがブロックされている場合、この値は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-164">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="c7d20-165">[ **キャンペーンの発生元** ] タブには、世界の地図にメッセージ ソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-165">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="c7d20-166">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="c7d20-166">Filters and settings</span></span>

<span data-ttu-id="c7d20-167">[キャンペーン] ページ **の上部** には、特定のキャンペーンを見つけて特定するのに役立つフィルターとクエリの設定がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-167">At the top of the **Campaign** page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーン フィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="c7d20-169">最も基本的なフィルター処理は、開始日/時刻と終了日時です。</span><span class="sxs-lookup"><span data-stu-id="c7d20-169">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="c7d20-170">ビューをさらにフィルター処理するには、[キャンペーンの種類] ボタンをクリックして選択し、[更新]をクリックして、複数の値をフィルター処理する単一のプロパティを **実行できます**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-170">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="c7d20-171">[キャンペーンの種類] ボタンで使用できるフィルター可能なキャンペーン **プロパティについては** 、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-171">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="c7d20-172">**基本**:</span><span class="sxs-lookup"><span data-stu-id="c7d20-172">**Basic**:</span></span>
  - <span data-ttu-id="c7d20-173">**キャンペーンの種類**: [マルウェア **] または [フィッシング]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-173">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="c7d20-174">選択範囲をクリアすると、両方を選択した場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-174">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="c7d20-175">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="c7d20-175">**Campaign name**</span></span>
  - <span data-ttu-id="c7d20-176">**キャンペーンのサブタイプ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-176">**Campaign subtype**</span></span>
  - <span data-ttu-id="c7d20-177">**送信者**</span><span class="sxs-lookup"><span data-stu-id="c7d20-177">**Sender**</span></span>
  - <span data-ttu-id="c7d20-178">**受信者**</span><span class="sxs-lookup"><span data-stu-id="c7d20-178">**Recipients**</span></span>
  - <span data-ttu-id="c7d20-179">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="c7d20-179">**Sender domain**</span></span>
  - <span data-ttu-id="c7d20-180">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="c7d20-180">**Subject**</span></span>
  - <span data-ttu-id="c7d20-181">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="c7d20-181">**Attachment filename**</span></span>
  - <span data-ttu-id="c7d20-182">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-182">**Malware family**</span></span>
  - <span data-ttu-id="c7d20-183">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-183">**Tags**: Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="c7d20-184">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-184">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="c7d20-185">**配信アクション**</span><span class="sxs-lookup"><span data-stu-id="c7d20-185">**Delivery action**</span></span>
  - <span data-ttu-id="c7d20-186">**その他のアクション**</span><span class="sxs-lookup"><span data-stu-id="c7d20-186">**Additional action**</span></span>
  - <span data-ttu-id="c7d20-187">**方向性**</span><span class="sxs-lookup"><span data-stu-id="c7d20-187">**Directionality**</span></span>
  - <span data-ttu-id="c7d20-188">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-188">**Detection technology**</span></span>
  - <span data-ttu-id="c7d20-189">**元の配信場所**</span><span class="sxs-lookup"><span data-stu-id="c7d20-189">**Original delivery location**</span></span>
  - <span data-ttu-id="c7d20-190">**最新の配信場所**</span><span class="sxs-lookup"><span data-stu-id="c7d20-190">**Latest delivery location**</span></span>
  - <span data-ttu-id="c7d20-191">**システムオーバーライド**</span><span class="sxs-lookup"><span data-stu-id="c7d20-191">**System overrides**</span></span>

- <span data-ttu-id="c7d20-192">**Advanced**:</span><span class="sxs-lookup"><span data-stu-id="c7d20-192">**Advanced**:</span></span>
  - <span data-ttu-id="c7d20-193">**インターネット メッセージ ID**: メッセージ ヘッダー **の [Message-ID** ヘッダー] フィールドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-193">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="c7d20-194">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-194">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="c7d20-195">**ネットワーク メッセージ ID:** メッセージ ヘッダーの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー フィールドで使用できる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="c7d20-195">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="c7d20-196">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-196">**Sender IP**</span></span>
  - <span data-ttu-id="c7d20-197">**添付ファイル SHA256**: ファイルの SHA256 ハッシュ値を Windows で検索するには、コマンド プロンプトで次のコマンドを実行します `certutil.exe -hashfile "<Path>\<Filename>" SHA256` 。</span><span class="sxs-lookup"><span data-stu-id="c7d20-197">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="c7d20-198">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="c7d20-198">**Cluster ID**</span></span>
  - <span data-ttu-id="c7d20-199">**アラート ID**</span><span class="sxs-lookup"><span data-stu-id="c7d20-199">**Alert ID**</span></span>
  - <span data-ttu-id="c7d20-200">**アラート ポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="c7d20-200">**Alert Policy ID**</span></span>
  - <span data-ttu-id="c7d20-201">**キャンペーン ID**</span><span class="sxs-lookup"><span data-stu-id="c7d20-201">**Campaign ID**</span></span>
  - <span data-ttu-id="c7d20-202">**ZAP URL シグナル**</span><span class="sxs-lookup"><span data-stu-id="c7d20-202">**ZAP URL signal**</span></span>

- <span data-ttu-id="c7d20-203">**URL**:</span><span class="sxs-lookup"><span data-stu-id="c7d20-203">**URLs**:</span></span>
  - <span data-ttu-id="c7d20-204">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="c7d20-204">**URL domain**</span></span>
  - <span data-ttu-id="c7d20-205">**URL ドメインとパス**</span><span class="sxs-lookup"><span data-stu-id="c7d20-205">**URL domain and path**</span></span>
  - <span data-ttu-id="c7d20-206">**URL**</span><span class="sxs-lookup"><span data-stu-id="c7d20-206">**URL**</span></span>
  - <span data-ttu-id="c7d20-207">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="c7d20-207">**URL path**</span></span>
  - <span data-ttu-id="c7d20-208">**[評決] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="c7d20-208">**Click verdict**</span></span>

<span data-ttu-id="c7d20-209">複数のプロパティによるフィルター処理など、より高度なフィルター処理を行う場合は、[高度なフィルター] ボタンをクリックしてクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-209">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="c7d20-210">同じキャンペーン プロパティを使用できますが、次の機能拡張が追加されています。</span><span class="sxs-lookup"><span data-stu-id="c7d20-210">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="c7d20-211">[条件の追加 **] をクリックして、** 複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-211">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="c7d20-212">条件の間で **And** 演算子または **Or** 演算子を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-212">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="c7d20-213">条件リストの下部 **にある条件グループ** 項目を選択して、複雑な複合条件を形成できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-213">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="c7d20-214">完了したら、[クエリ] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-214">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="c7d20-215">基本フィルターまたは高度なフィルターを作成した後は、[クエリの保存] または [クエリを名前を付けて保存]**を使用して保存できます**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-215">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="c7d20-216">その後、[キャンペーン] ページに戻 **った** 場合は、[保存済みクエリ設定] をクリックして、保存済みフィルター **を読み込みできます**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-216">Later, when you return to the **Campaigns** page, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="c7d20-217">グラフまたはキャンペーンのリストをエクスポートするには、[エクスポート]をクリックし、[グラフ データのエクスポート] または [キャンペーン リスト **のエクスポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-217">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="c7d20-218">Microsoft Defender for Endpoint サブスクリプションをお持ちの場合は **、[MDE** 設定] をクリックして、Microsoft Defender for Endpoint でキャンペーン情報を接続または切断できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-218">If you have a Microsoft Defender for Endpoint subscription, you can click **MDE Settings** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c7d20-219">詳細については[、「Integrate Microsoft Defender for Office 365 Microsoft Defender for Endpoint」を参照してください](integrate-office-365-ti-with-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-219">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="c7d20-220">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="c7d20-220">Campaign details</span></span>

<span data-ttu-id="c7d20-221">キャンペーンの名前をクリックすると、キャンペーンの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-221">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="c7d20-222">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="c7d20-222">Campaign information</span></span>

<span data-ttu-id="c7d20-223">キャンペーンの詳細ビューの上部には、次のキャンペーン情報があります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-223">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="c7d20-224">**キャンペーン ID**: 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="c7d20-224">**Campaign ID**: The unique campaign identifier.</span></span>
- <span data-ttu-id="c7d20-225">**アクティビティ**: キャンペーンの期間とアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="c7d20-225">**Activity**: The duration and activity of the campaign.</span></span>
- <span data-ttu-id="c7d20-226">選択した (またはタイムラインで選択した) 日付範囲フィルターの次のデータ。</span><span class="sxs-lookup"><span data-stu-id="c7d20-226">The following data for the date range filter you selected (or that you select in the timeline):</span></span>
- <span data-ttu-id="c7d20-227">**影響**</span><span class="sxs-lookup"><span data-stu-id="c7d20-227">**Impact**</span></span>
- <span data-ttu-id="c7d20-228">**メッセージ**: 受信者の総数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-228">**Messages**: The total number of recipients.</span></span>
- <span data-ttu-id="c7d20-229">**受信トレイ**: 迷惑メール フォルダーではなく、受信トレイに配信されたメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-229">**Inboxed**: The number of messages that were delivered to the Inbox, not to the Junk Email folder.</span></span>
- <span data-ttu-id="c7d20-230">**クリックされたリンク**: フィッシング メッセージ内の URL ペイロードをクリックしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-230">**Clicked link**: How many users clicked on the URL payload in the phishing message.</span></span>
- <span data-ttu-id="c7d20-231">**アクセスしたリンク**: URL にアクセスしたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="c7d20-231">**Visited link**: How many users visited the URL.</span></span>
- <span data-ttu-id="c7d20-232">**Targeted(%)**: (組織内のキャンペーン受信者の数) / (サービス内のすべての組織のキャンペーン内の受信者の総数) で計算される割合。</span><span class="sxs-lookup"><span data-stu-id="c7d20-232">**Targeted(%)**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="c7d20-233">この値はキャンペーンの有効期間全体で計算され、日付フィルターに基づいて変更されません。</span><span class="sxs-lookup"><span data-stu-id="c7d20-233">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>
- <span data-ttu-id="c7d20-234">次のセクションで説明するように、キャンペーン フローの開始日時および終了データ/時刻フィルター。</span><span class="sxs-lookup"><span data-stu-id="c7d20-234">Start date/time and end data/time filters for the campaign flow as described in the next section.</span></span>
- <span data-ttu-id="c7d20-235">キャンペーンアクティビティのインタラクティブなタイムライン: タイムラインには、キャンペーンの有効期間全体のアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-235">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="c7d20-236">グラフ内のデータ ポイントにカーソルを合わせると、検出されたメッセージの量を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-236">You can hover over the data points in the graph to see the amount of detected messages.</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="c7d20-238">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="c7d20-238">Campaign flow</span></span>

<span data-ttu-id="c7d20-239">キャンペーンの詳細ビューの中央に、キャンペーンに関する重要な詳細が水平方向のフロー図 (サンキー図と呼ばれる) _に表示_ されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-239">In the middle of the campaign details view, important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="c7d20-240">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-240">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="c7d20-241">フロー図に表示される情報は、前のセクションで説明したように、タイムラインの日付範囲フィルターによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-241">The information that's displayed in the flow diagram is controlled by the date range filter in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="c7d20-243">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-243">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="c7d20-244">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-244">The diagram contains the following information:</span></span>

- <span data-ttu-id="c7d20-245">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-245">**Sender IPs**</span></span>
- <span data-ttu-id="c7d20-246">[**Sender domains (送信者のドメイン)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-246">**Sender domains**</span></span>
- <span data-ttu-id="c7d20-247">**フィルターの評決**: Verdict 値は、「スパム対策メッセージ ヘッダー」の説明に従って、使用可能なフィッシングおよびスパム フィルターの評決 [に関連しています](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-247">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="c7d20-248">使用可能な値については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-248">The available values are described in the following table:</span></span>

  <br>

  ****

  |<span data-ttu-id="c7d20-249">値</span><span class="sxs-lookup"><span data-stu-id="c7d20-249">Value</span></span>|<span data-ttu-id="c7d20-250">スパム フィルターの評決</span><span class="sxs-lookup"><span data-stu-id="c7d20-250">Spam filter verdict</span></span>|<span data-ttu-id="c7d20-251">説明</span><span class="sxs-lookup"><span data-stu-id="c7d20-251">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="c7d20-252">**可**</span><span class="sxs-lookup"><span data-stu-id="c7d20-252">**Allowed**</span></span>|`SFV:SKN` <p> `SFV:SKI`|<span data-ttu-id="c7d20-253">このメッセージは、スパム フィルターによって評価される前に、スパムではない、またはスキップされたフィルター処理としてマークされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-253">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="c7d20-254">たとえば、メッセージはメール フロー ルール (トランスポート ルールとも呼ばれる) によってスパムではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-254">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span> <p> <span data-ttu-id="c7d20-255">メッセージは、他の理由でスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-255">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="c7d20-256">たとえば、送信者と受信者は同じ組織内にあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-256">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="c7d20-257">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="c7d20-257">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="c7d20-258">メッセージは、スパム フィルターによって評価される前にスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-258">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="c7d20-259">たとえば、メール フロー ルールによって指定します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-259">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="c7d20-260">[**Detected (検出済み)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-260">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="c7d20-261">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-261">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="c7d20-262">**検出されない**</span><span class="sxs-lookup"><span data-stu-id="c7d20-262">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="c7d20-263">このメッセージは、スパム フィルターによってスパムではないとマークされています。</span><span class="sxs-lookup"><span data-stu-id="c7d20-263">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="c7d20-264">**リリース済み**</span><span class="sxs-lookup"><span data-stu-id="c7d20-264">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="c7d20-265">メッセージは検疫から解放されたため、スパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-265">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="c7d20-266">**テナント許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7d20-266">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="c7d20-267">スパム対策ポリシーの設定のため、メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-267">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="c7d20-268">たとえば、送信者が許可されている送信者リストまたは許可されたドメイン リストに含めらたとします。</span><span class="sxs-lookup"><span data-stu-id="c7d20-268">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="c7d20-269">**テナント ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7d20-269">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="c7d20-270">スパム対策ポリシーの設定により、スパム フィルターによってメッセージがブロックされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-270">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="c7d20-271">たとえば、送信者が許可されている送信者リストまたは許可されたドメイン リストに含めらたとします。</span><span class="sxs-lookup"><span data-stu-id="c7d20-271">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="c7d20-272">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7d20-272">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="c7d20-273">送信者がユーザーの [送信者] リストに含セーフスキップされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-273">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="c7d20-274">**ユーザー ブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="c7d20-274">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="c7d20-275">送信者がユーザーの [送信者のブロック] リストに含っていたため、メッセージはスパム フィルターによってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-275">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="c7d20-276">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="c7d20-276">**ZAP**</span></span>|<span data-ttu-id="c7d20-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="c7d20-277">n/a</span></span>|<span data-ttu-id="c7d20-278">[ゼロ時間自動削除 (ZAP) は](zero-hour-auto-purge.md) 、配信されたメッセージを迷惑メール フォルダーまたは検疫に移動しました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-278">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="c7d20-279">スパム対策ポリシーでアクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-279">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="c7d20-280"><sup>\*</sup> 許可されたメッセージがサービスによってブロックされている可能性が高いので、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-280"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="c7d20-281"><sup>\*\*</sup> これらのメッセージは検疫され、配信されないので、スパム対策ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-281"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="c7d20-282">**メッセージの** 宛先 : メッセージ内のペイロード URL をユーザーがクリックしなかった場合でも、受信者 (受信トレイまたは迷惑メール フォルダー) に配信されたメッセージを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-282">**Message destinations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="c7d20-283">検疫済みメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-283">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="c7d20-284">詳細については [、「EOP の検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-284">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="c7d20-285">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="c7d20-285">**Deleted folder**</span></span>
  - <span data-ttu-id="c7d20-286">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-286">**Dropped**</span></span>
  - <span data-ttu-id="c7d20-287">**外部**: 受信者は、ハイブリッド環境のオンプレミスの電子メール組織にあります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-287">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="c7d20-288">**Failed**</span><span class="sxs-lookup"><span data-stu-id="c7d20-288">**Failed**</span></span>
  - <span data-ttu-id="c7d20-289">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="c7d20-289">**Forwarded**</span></span>
  - <span data-ttu-id="c7d20-290">[**Inbox (受信トレイ)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-290">**Inbox**</span></span>
  - <span data-ttu-id="c7d20-291">[**Junk folder (迷惑メール フォルダー)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-291">**Junk folder**</span></span>
  - <span data-ttu-id="c7d20-292">[**Quarantine (検疫)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-292">**Quarantine**</span></span>
  - <span data-ttu-id="c7d20-293">**不明**</span><span class="sxs-lookup"><span data-stu-id="c7d20-293">**Unknown**</span></span>

- <span data-ttu-id="c7d20-294">**URL クリック**: これらの値については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-294">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="c7d20-295">10 を超えるアイテムを含むすべてのレイヤーで、上位 10 のアイテムが表示され、残りは [その他] にまとめて表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="c7d20-295">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="c7d20-296">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="c7d20-296">URL clicks</span></span>

<span data-ttu-id="c7d20-297">フィッシング メッセージが受信者の受信トレイまたは迷惑メール フォルダーに配信される場合、ユーザーがペイロード URL をクリックする可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-297">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="c7d20-298">URL をクリックしないのは成功の小さな手段ですが、フィッシング メッセージがメールボックスに配信された理由を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-298">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="c7d20-299">ユーザーがフィッシング メッセージのペイロード URL をクリックすると、アクションがキャンペーンの詳細ビューの図の **URL** クリック領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-299">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="c7d20-300">**可**</span><span class="sxs-lookup"><span data-stu-id="c7d20-300">**Allowed**</span></span>
- <span data-ttu-id="c7d20-301">**BlockPage**: 受信者がペイロード URL をクリックしましたが、悪意のある Web サイトへのアクセスは、組織内の セーフ [リンク ポリシー](safe-links.md)によってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-301">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="c7d20-302">**BlockPageOverride**: 受信者はメッセージ内のペイロード URL をクリックし、セーフ Links はブロックを停止しようとしましたが、ブロックを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-302">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="c7d20-303">[リンク][セーフポリシー](set-up-safe-links-policies.md)を調して、ユーザーがリンクの評価を上書きして悪意のある web サイトに進セーフ許可される理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-303">Inspect your [Safe Links policies](set-up-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="c7d20-304">**PendingDetonationPage**: セーフ Office 365 用 Microsoft Defender の添付ファイルは、仮想コンピューター環境でペイロード URL を開いて調査中です。</span><span class="sxs-lookup"><span data-stu-id="c7d20-304">**PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="c7d20-305">**PendingDetonationPageOverride**: 受信者は、ペイロードのデトレーション プロセスを上書きし、結果を待たずに URL を開く許可を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="c7d20-305">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="c7d20-306">タブ</span><span class="sxs-lookup"><span data-stu-id="c7d20-306">Tabs</span></span>

<span data-ttu-id="c7d20-307">キャンペーンの詳細ビューのタブを使用すると、キャンペーンをさらに調査できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-307">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="c7d20-308">タブに表示される情報は、[キャンペーン情報] セクションの説明に従って、タイムラインの日付範囲フィルター [によって制御](#campaign-information) されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-308">The information that's displayed on the tabs is controlled by the date range filter in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="c7d20-309">**URL クリック**: メッセージ内のペイロード URL をユーザーがクリックしなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="c7d20-309">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="c7d20-310">ユーザーが URL をクリックできた場合、次の値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-310">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="c7d20-311">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="c7d20-311">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="c7d20-312">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="c7d20-312">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="c7d20-313">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="c7d20-313">**Click time**</span></span>
  - <span data-ttu-id="c7d20-314">**[評決] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="c7d20-314">**Click verdict**</span></span>

- <span data-ttu-id="c7d20-315">[**Sender IPs (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-315">**Sender IPs**</span></span>
  - <span data-ttu-id="c7d20-316">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="c7d20-316">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="c7d20-317">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="c7d20-317">**Total count**</span></span>
  - <span data-ttu-id="c7d20-318">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-318">**Inboxed**</span></span>
  - <span data-ttu-id="c7d20-319">**受信トレイに入ってない**</span><span class="sxs-lookup"><span data-stu-id="c7d20-319">**Not Inboxed**</span></span>
  - <span data-ttu-id="c7d20-320">**SPF が渡** されました: 送信者は Sender [Policy Framework (SPF) によって認証されました](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-320">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="c7d20-321">SPF 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者をスプーフィングすることを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-321">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="c7d20-322">[**Senders (送信者)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-322">**Senders**</span></span>
  - <span data-ttu-id="c7d20-323">**Sender**: これは SMTP MAIL FROM コマンドの実際の送信者アドレスで、ユーザーが電子メール クライアントに表示する差出人: 電子メール アドレスとは限りません。</span><span class="sxs-lookup"><span data-stu-id="c7d20-323">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="c7d20-324">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="c7d20-324">**Total count**</span></span>
  - <span data-ttu-id="c7d20-325">**受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-325">**Inboxed**</span></span>
  - <span data-ttu-id="c7d20-326">**受信トレイに入ってない**</span><span class="sxs-lookup"><span data-stu-id="c7d20-326">**Not Inboxed**</span></span>
  - <span data-ttu-id="c7d20-327">**DKIM が渡されました**: 送信者がドメイン キー識別 [メール (DKIM) によって認証されました](support-for-validation-of-dkim-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-327">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="c7d20-328">DKIM 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者をスプーフィングすることを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-328">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="c7d20-329">**DMARC が渡** されました: 送信者は、ドメイン ベースのメッセージ認証、レポート、および [準拠 (DMARC) によって認証されました](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-329">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="c7d20-330">DMARC 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者をスプーフィングすることを示します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-330">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="c7d20-331">**Attachments**</span><span class="sxs-lookup"><span data-stu-id="c7d20-331">**Attachments**</span></span>
  - <span data-ttu-id="c7d20-332">**Filename**</span><span class="sxs-lookup"><span data-stu-id="c7d20-332">**Filename**</span></span>
  - <span data-ttu-id="c7d20-333">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="c7d20-333">**SHA256**</span></span>
  - <span data-ttu-id="c7d20-334">**マルウェア ファミリ**</span><span class="sxs-lookup"><span data-stu-id="c7d20-334">**Malware family**</span></span>
  - <span data-ttu-id="c7d20-335">**合計カウント**</span><span class="sxs-lookup"><span data-stu-id="c7d20-335">**Total count**</span></span>

- <span data-ttu-id="c7d20-336">**URL**</span><span class="sxs-lookup"><span data-stu-id="c7d20-336">**URL**</span></span>
  - <span data-ttu-id="c7d20-337">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="c7d20-337">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="c7d20-338">[**Total Count (総数)**]</span><span class="sxs-lookup"><span data-stu-id="c7d20-338">**Total Count**</span></span>

<span data-ttu-id="c7d20-339"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-339"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="c7d20-340">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [**Done (完了)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7d20-340">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="c7d20-341">ボタン</span><span class="sxs-lookup"><span data-stu-id="c7d20-341">Buttons</span></span>

<span data-ttu-id="c7d20-342">キャンペーンの詳細ビューの下部にあるボタンを使用すると、キャンペーンの詳細を調査して記録できます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-342">The buttons at the bottom the campaign details view allow you to investigate and record details about the campaign:</span></span>

- <span data-ttu-id="c7d20-343">**メッセージの検索**: 脅威エクスプローラーの機能を使用して、キャンペーンをさらに調査します。</span><span class="sxs-lookup"><span data-stu-id="c7d20-343">**Explore messages**: Use the power of Threat Explorer to further investigate the campaign:</span></span>
  - <span data-ttu-id="c7d20-344">**すべてのメッセージ**: キャンペーン ID の値を検索フィルターとして使用して、新しい **[脅威** エクスプローラー] 検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-344">**All messages**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
  - <span data-ttu-id="c7d20-345">**受信トレイメッセージ**: [キャンペーン **ID]** と [配信場所 **: 受信** トレイ] を検索フィルターとして使用して、新しい [脅威エクスプローラー] 検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-345">**Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
  - <span data-ttu-id="c7d20-346">**内部メッセージ**: [キャンペーン **ID]** と [方向性 **:** 組織内] を検索フィルターとして使用して、新しい [脅威エクスプローラー] 検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7d20-346">**Internal messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Directionality: Intra-org** as the search filter.</span></span>

- <span data-ttu-id="c7d20-347">**脅威レポートをダウンロード** する: キャンペーンの詳細を Word ドキュメントにダウンロードします (既定では、名前は CampaignReport.docx)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-347">**Download threat report**: Download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="c7d20-348">ダウンロードには、キャンペーンの有効期間全体に関する詳細が含まれています (選択したフィルターの日付だけではありません)。</span><span class="sxs-lookup"><span data-stu-id="c7d20-348">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>
