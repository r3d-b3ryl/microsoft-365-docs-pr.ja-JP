---
title: Microsoft Defender for Office 365 プランのキャンペーンビュー
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
description: Microsoft Defender for Office 365 のキャンペーンビューについて説明します。
ms.openlocfilehash: 1e5754e077d4c1b8f685b5dea1f8a59985e08a13
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948483"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1d598-103">Microsoft Defender for Office 365 のキャンペーンビュー</span><span class="sxs-lookup"><span data-stu-id="1d598-103">Campaign Views in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1d598-104">[キャンペーンビュー] は、Microsoft Defender for Office 365 プラン2の機能です (たとえば、Microsoft 365 E5 や、Defender for Office 365 Plan 2 アドオンの組織の場合)。</span><span class="sxs-lookup"><span data-stu-id="1d598-104">Campaign Views is a feature in Microsoft Defender for Office 365 Plan 2 (for example Microsoft 365 E5 or organizations with an Defender for Office 365 Plan 2 add-on).</span></span> <span data-ttu-id="1d598-105">セキュリティ & コンプライアンスセンターの [キャンペーン] ビューサービスのフィッシング攻撃を特定して分類します。</span><span class="sxs-lookup"><span data-stu-id="1d598-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="1d598-106">キャンペーン ビューは、次の目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="1d598-107">フィッシング攻撃を効率的に調査し、対処する。</span><span class="sxs-lookup"><span data-stu-id="1d598-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="1d598-108">攻撃対象を正確に理解する。</span><span class="sxs-lookup"><span data-stu-id="1d598-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="1d598-109">意思決定者に価値を示す。</span><span class="sxs-lookup"><span data-stu-id="1d598-109">Show value to decision makers.</span></span>

<span data-ttu-id="1d598-110">キャンペーン ビューを使用すると、人間には真似できない速さと完全さで攻撃の全体像を把握できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="1d598-111">キャンペーンとは</span><span class="sxs-lookup"><span data-stu-id="1d598-111">What is a campaign?</span></span>

<span data-ttu-id="1d598-112">キャンペーンとは、1 つまたは複数の組織に対する組織的なメール攻撃のことです。</span><span class="sxs-lookup"><span data-stu-id="1d598-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="1d598-113">資格情報と会社のデータを盗む電子メール攻撃は、大規模で lucrative 業界です。</span><span class="sxs-lookup"><span data-stu-id="1d598-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="1d598-114">攻撃を阻止するためのテクノロジが増加するにつれて、攻撃者はその方法を変更して、成功を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="1d598-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="1d598-115">Microsoft は、サービス全体にわたる大量のフィッシング対策、スパム対策、マルウェア対策データを活用して、キャンペーンを特定します。</span><span class="sxs-lookup"><span data-stu-id="1d598-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="1d598-116">いくつかの要因によって、攻撃の情報を分析し、分類します。</span><span class="sxs-lookup"><span data-stu-id="1d598-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="1d598-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-117">For example:</span></span>

- <span data-ttu-id="1d598-118">[ **アタックソース** ]: 送信元 IP アドレスと送信者の電子メールドメイン。</span><span class="sxs-lookup"><span data-stu-id="1d598-118">**Attack source** : The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="1d598-119">**メッセージプロパティ** : メッセージのコンテンツ、スタイル、およびトーン。</span><span class="sxs-lookup"><span data-stu-id="1d598-119">**Message properties** : The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="1d598-120">**メッセージ受信者** : 受信者がどのように関係していますか。</span><span class="sxs-lookup"><span data-stu-id="1d598-120">**Message recipients** : How recipients are related.</span></span> <span data-ttu-id="1d598-121">たとえば、[受信者] ドメイン、[受信者ジョブ] 機能 (管理者、役員など)、企業の種類 (大、小、パブリック、プライベートなど)、業種。</span><span class="sxs-lookup"><span data-stu-id="1d598-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="1d598-122">**アタックペイロード** : 悪意のあるリンク、添付ファイル、またはメッセージ内の他のペイロード。</span><span class="sxs-lookup"><span data-stu-id="1d598-122">**Attack payload** : Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="1d598-123">キャンペーンは、期間が短い場合や、複数の日、週、または月でアクティブで非アクティブな期間がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="1d598-124">特定の組織に対してキャンペーンが開始された場合や、組織が複数の企業にわたるより大きなキャンペーンの一部になっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="1d598-125">セキュリティ & コンプライアンスセンターのキャンペーンビュー</span><span class="sxs-lookup"><span data-stu-id="1d598-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="1d598-126">キャンペーンビューは、 [セキュリティ & コンプライアンスセンター](https://protection.office.com) の [ **脅威管理** \> ] **キャンペーン** で、またはに直接アクセスでき <https://protection.office.com/campaigns> ます。</span><span class="sxs-lookup"><span data-stu-id="1d598-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns** , or directly at <https://protection.office.com/campaigns>.</span></span>

![セキュリティ/コンプライアンス センターのキャンペーンの概要](../../media/campaigns-overview.png)

<span data-ttu-id="1d598-128">次の方法でキャンペーンビューにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1d598-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="1d598-129">**脅威の管理** \>**エクスプローラー** \>**表示** \>**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="1d598-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>
- <span data-ttu-id="1d598-130">**脅威の管理** \>**エクスプローラー** \>**表示** \>**すべての電子メール** \>[ **キャンペーン** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1d598-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>
- <span data-ttu-id="1d598-131">**脅威の管理** \>**エクスプローラー** \>**表示** \>**フィッシング** \>[ **キャンペーン** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1d598-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>
- <span data-ttu-id="1d598-132">**脅威の管理** \>**エクスプローラー** \>**表示** \>**マルウェア** \>[ **キャンペーン** ] タブ</span><span class="sxs-lookup"><span data-stu-id="1d598-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="1d598-133">[キャンペーン] ビューにアクセスするには、セキュリティ & コンプライアンスセンターで、[ **組織の管理** ]、[ **セキュリティ管理者** ]、または [ **セキュリティリーダー** ] の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-133">To access Campaign Views, you need to be a member of the **Organization Management** , **Security Administrator** , or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="1d598-134">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="1d598-135">キャンペーンの概要</span><span class="sxs-lookup"><span data-stu-id="1d598-135">Campaigns overview</span></span>

<span data-ttu-id="1d598-136">概要ページには、すべてのキャンペーンに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="1d598-137">[既定の **キャンペーン** ] タブの [ **キャンペーンの種類** ] 領域には、1日あたりの受信者数を示す棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="1d598-138">既定では、グラフには **フィッシング** と **マルウェア** のデータの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="1d598-139">キャンペーンデータが表示されない場合は、日付範囲または [フィルター](#filters-and-settings)を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="1d598-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="1d598-140">その他の概要ページには、[ **キャンペーン** ] タブに次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="1d598-141">[ **Name (名前)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-141">**Name**</span></span>

- <span data-ttu-id="1d598-142">[ **Sample subject (件名のサンプル)** ]: キャンペーンのいずれかのメッセージの件名行。</span><span class="sxs-lookup"><span data-stu-id="1d598-142">**Sample subject** : The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="1d598-143">キャンペーン内のすべてのメッセージには、必ずしも同じ件名が含まれないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="1d598-144">**対象** : ([組織内のキャンペーン受信者の数])/(サービス内のすべての組織にわたるキャンペーンの受信者の合計数) の計算結果の割合。</span><span class="sxs-lookup"><span data-stu-id="1d598-144">**Targeted** : The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="1d598-145">この値は、組織でのみキャンペーンが指示される度合い (高い値) と、サービス内の他の組織 (低い値) のどちらにするかを示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="1d598-146">**型** : この値は、 **フィッシング** または **マルウェア** です。</span><span class="sxs-lookup"><span data-stu-id="1d598-146">**Type** : This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="1d598-147">**Subtype** : この値には、キャンペーンの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d598-147">**Subtype** : This value contains more details about the campaign.</span></span> <span data-ttu-id="1d598-148">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-148">For example:</span></span>
  - <span data-ttu-id="1d598-149">**フィッシング** : 使用可能な場合は、このキャンペーンによって phished されているブランド。</span><span class="sxs-lookup"><span data-stu-id="1d598-149">**Phish** : Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="1d598-150">たとえば、、、、、 `Microsoft` `365` 、など `Unknown` `Outlook` `DocuSign` です。</span><span class="sxs-lookup"><span data-stu-id="1d598-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>
  - <span data-ttu-id="1d598-151">**マルウェア** : たとえば、 `HTML/PHISH` またはのように `HTML/<MalwareFamilyName>` なります。</span><span class="sxs-lookup"><span data-stu-id="1d598-151">**Malware** : For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

  <span data-ttu-id="1d598-152">利用可能な場合、このキャンペーンで phished されているブランド。</span><span class="sxs-lookup"><span data-stu-id="1d598-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="1d598-153">検出が Office 365 テクノロジの Defender によって駆動される場合、プレフィックス **ATP-** がサブタイプ値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-153">When the detection is driven by Defender for Office 365 technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="1d598-154">[ **Recipients (受信者)** ]: このキャンペーンの攻撃対象となったユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="1d598-154">**Recipients** : The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="1d598-155">**Inboxed** : このキャンペーンからのメッセージを受信トレイで受信したユーザーの数 (迷惑メールフォルダーに配信されません)。</span><span class="sxs-lookup"><span data-stu-id="1d598-155">**Inboxed** : The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="1d598-156">**クリック** した場合: URL をクリックしたユーザーの数、またはフィッシングメッセージで添付ファイルを開いたユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="1d598-156">**Clicked** : The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="1d598-157">**[利率** ] をクリックします **。 "**  /  **ボックスにボックス** 化" をクリックして計算されたパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="1d598-157">**Click rate** : The percentage as calculated by " **Clicked** / **Inboxed** ".</span></span> <span data-ttu-id="1d598-158">この値は、キャンペーンの有効性を示す指標です。</span><span class="sxs-lookup"><span data-stu-id="1d598-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="1d598-159">言い換えると、受信者がメッセージをフィッシングとして識別でき、ペイロード URL をクリックしていない場合です。</span><span class="sxs-lookup"><span data-stu-id="1d598-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="1d598-160">**[] クリックレート** は、マルウェアキャンペーンでは使用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="1d598-161">**訪問** 済み: ペイロード web サイトに実際にアクセスしたユーザー数。</span><span class="sxs-lookup"><span data-stu-id="1d598-161">**Visited** : How many users actually made it through to the payload website.</span></span> <span data-ttu-id="1d598-162">[値] が **クリック** されているが、安全なリンクによって web サイトへのアクセスがブロックされている場合、この値は0になります。</span><span class="sxs-lookup"><span data-stu-id="1d598-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="1d598-163">[ **キャンペーン送信元** ] タブには、世界の地図上のメッセージソースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="1d598-164">フィルターと設定</span><span class="sxs-lookup"><span data-stu-id="1d598-164">Filters and settings</span></span>

<span data-ttu-id="1d598-165">[キャンペーンビュー] ページの上部には、フィルターとクエリの設定がいくつか用意されているため、特定のキャンペーンを検索して分離することができます。</span><span class="sxs-lookup"><span data-stu-id="1d598-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![キャンペーンフィルター](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="1d598-167">最も基本的なフィルターは、開始日/時刻と終了日/時刻です。</span><span class="sxs-lookup"><span data-stu-id="1d598-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="1d598-168">ビューをさらにフィルター処理するには、[ **キャンペーンの種類** ] ボタンをクリックして、選択を行い、[最新の情報に **更新** ] をクリックすることで、複数の値を設定した単一のプロパティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="1d598-169">[ **キャンペーンの種類** ] ボタンに表示されるフィルター処理可能なキャンペーンプロパティについては、次のリストで説明します。</span><span class="sxs-lookup"><span data-stu-id="1d598-169">The filterable campaign properties that are available in the **Campaign type** button are described in the following list:</span></span>

- <span data-ttu-id="1d598-170">**Basic** :</span><span class="sxs-lookup"><span data-stu-id="1d598-170">**Basic** :</span></span>
  - <span data-ttu-id="1d598-171">**キャンペーンの種類** : **マルウェア** または **フィッシング** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d598-171">**Campaign type** : Select **Malware** or **Phish**.</span></span> <span data-ttu-id="1d598-172">選択範囲をクリアすると、両方を選択したときと同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="1d598-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="1d598-173">**キャンペーン名**</span><span class="sxs-lookup"><span data-stu-id="1d598-173">**Campaign name**</span></span>
  - <span data-ttu-id="1d598-174">**キャンペーンサブタイプ**</span><span class="sxs-lookup"><span data-stu-id="1d598-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="1d598-175">**送信者**</span><span class="sxs-lookup"><span data-stu-id="1d598-175">**Sender**</span></span>
  - <span data-ttu-id="1d598-176">**受信者**</span><span class="sxs-lookup"><span data-stu-id="1d598-176">**Recipients**</span></span>
  - <span data-ttu-id="1d598-177">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="1d598-177">**Sender domain**</span></span>
  - <span data-ttu-id="1d598-178">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="1d598-178">**Subject**</span></span>
  - <span data-ttu-id="1d598-179">**添付ファイルの名前**</span><span class="sxs-lookup"><span data-stu-id="1d598-179">**Attachment filename**</span></span>
  - <span data-ttu-id="1d598-180">**マルウェアファミリ**</span><span class="sxs-lookup"><span data-stu-id="1d598-180">**Malware family**</span></span>
  - <span data-ttu-id="1d598-181">**タグ** : 指定したユーザータグ (優先度アカウントを含む) が適用されたユーザーまたはグループ。</span><span class="sxs-lookup"><span data-stu-id="1d598-181">**Tags** : Users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="1d598-182">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-182">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="1d598-183">**システムの上書き**</span><span class="sxs-lookup"><span data-stu-id="1d598-183">**System overrides**</span></span>
  - <span data-ttu-id="1d598-184">**配信アクション**</span><span class="sxs-lookup"><span data-stu-id="1d598-184">**Delivery action**</span></span>
  - <span data-ttu-id="1d598-185">**追加のアクション**</span><span class="sxs-lookup"><span data-stu-id="1d598-185">**Additional action**</span></span>
  - <span data-ttu-id="1d598-186">**方向性**</span><span class="sxs-lookup"><span data-stu-id="1d598-186">**Directionality**</span></span>
  - <span data-ttu-id="1d598-187">**検出テクノロジ**</span><span class="sxs-lookup"><span data-stu-id="1d598-187">**Detection technology**</span></span>
  - <span data-ttu-id="1d598-188">**元の配信場所**</span><span class="sxs-lookup"><span data-stu-id="1d598-188">**Original delivery location**</span></span>
  - <span data-ttu-id="1d598-189">**最新の配信場所**</span><span class="sxs-lookup"><span data-stu-id="1d598-189">**Latest delivery location**</span></span>
  - <span data-ttu-id="1d598-190">**システムの上書き**</span><span class="sxs-lookup"><span data-stu-id="1d598-190">**System overrides**</span></span>

- <span data-ttu-id="1d598-191">**詳細** :</span><span class="sxs-lookup"><span data-stu-id="1d598-191">**Advanced** :</span></span>
  - <span data-ttu-id="1d598-192">**インターネットメッセージ id** : メッセージヘッダーの **メッセージ id** ヘッダーフィールドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-192">**Internet message ID** : Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="1d598-193">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="1d598-193">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="1d598-194">[ **ネットワークメッセージ id** ]: メッセージヘッダーの [-- **Exchange 組織-ネットワークメッセージ id** ] ヘッダーフィールドで使用可能な GUID 値。</span><span class="sxs-lookup"><span data-stu-id="1d598-194">**Network message ID** : A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  - <span data-ttu-id="1d598-195">[ **Sender IP (送信者の IP)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-195">**Sender IP**</span></span>
  - <span data-ttu-id="1d598-196">**ATTACHMENT SHA256** : Windows でファイルの SHA256 ハッシュ値を検索するには、コマンドプロンプトで次のコマンドを実行 `certutil.exe -hashfile "<Path>\<Filename>" SHA256` します。</span><span class="sxs-lookup"><span data-stu-id="1d598-196">**Attachment SHA256** : To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  - <span data-ttu-id="1d598-197">**クラスター ID**</span><span class="sxs-lookup"><span data-stu-id="1d598-197">**Cluster ID**</span></span>
  - <span data-ttu-id="1d598-198">**アラートポリシー ID**</span><span class="sxs-lookup"><span data-stu-id="1d598-198">**Alert Policy ID**</span></span>
  - <span data-ttu-id="1d598-199">**ZAP URL 信号**</span><span class="sxs-lookup"><span data-stu-id="1d598-199">**ZAP URL signal**</span></span>

- <span data-ttu-id="1d598-200">**Url** :</span><span class="sxs-lookup"><span data-stu-id="1d598-200">**URLs** :</span></span>
  - <span data-ttu-id="1d598-201">**URL ドメイン**</span><span class="sxs-lookup"><span data-stu-id="1d598-201">**URL domain**</span></span>
  - <span data-ttu-id="1d598-202">**URL のドメインとパス**</span><span class="sxs-lookup"><span data-stu-id="1d598-202">**URL domain and path**</span></span>
  - <span data-ttu-id="1d598-203">**URL**</span><span class="sxs-lookup"><span data-stu-id="1d598-203">**URL**</span></span>
  - <span data-ttu-id="1d598-204">**URL パス**</span><span class="sxs-lookup"><span data-stu-id="1d598-204">**URL path**</span></span>
  - <span data-ttu-id="1d598-205">**[Verdict] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="1d598-205">**Click verdict**</span></span>

<span data-ttu-id="1d598-206">複数のプロパティによるフィルター処理を含む、高度なフィルター処理を行うには、[ **フィルターの詳細設定** ] ボタンをクリックしてクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d598-206">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="1d598-207">同じキャンペーンプロパティを使用できますが、以下の機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="1d598-207">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="1d598-208">[ **条件の追加** ] をクリックすると、複数の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-208">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="1d598-209">**And** また **は or** 演算子は、条件間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-209">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="1d598-210">[条件] ボックスの一覧の下部にある [ **条件] グループ** 項目を選択して、複雑な複合条件を形成できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-210">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="1d598-211">完了したら、[ **クエリ** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d598-211">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="1d598-212">基本フィルターまたは詳細フィルターを作成した後で、[ **クエリの保存** ] または [ **クエリ** に名前を付けて保存] を使用して保存できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-212">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="1d598-213">後でキャンペーンビューに戻るときに、保存したフィルターを読み込むには、[ **保存さ** れたクエリの設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d598-213">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="1d598-214">グラフまたはキャンペーンの一覧をエクスポートするには、[ **エクスポート** ] をクリックし、[ **グラフデータのエクスポート** ] または [ **キャンペーンリストのエクスポート** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d598-214">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="1d598-215">エンドポイントサブスクリプションの Microsoft Defender を所有している場合は、[ **Wdatp** ] をクリックして、エンドポイントの microsoft defender とキャンペーン情報を接続または切断することができます。</span><span class="sxs-lookup"><span data-stu-id="1d598-215">If you have a Microsoft Defender for Endpoint subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1d598-216">詳細については、「microsoft defender [For Office 365 をエンドポイントの Microsoft defender に統合](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-216">For more information, see [Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="1d598-217">キャンペーンの詳細</span><span class="sxs-lookup"><span data-stu-id="1d598-217">Campaign details</span></span>

<span data-ttu-id="1d598-218">キャンペーンの名前をクリックすると、そのキャンペーンの詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-218">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="1d598-219">キャンペーン情報</span><span class="sxs-lookup"><span data-stu-id="1d598-219">Campaign information</span></span>

<span data-ttu-id="1d598-220">キャンペーンの詳細ビューの一番上に、次のキャンペーン情報があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-220">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="1d598-221">**ID** : 一意のキャンペーン識別子。</span><span class="sxs-lookup"><span data-stu-id="1d598-221">**ID** : The unique campaign identifier.</span></span>

- <span data-ttu-id="1d598-222">[ **開始** および **終了** ]: キャンペーンの開始日と終了日。</span><span class="sxs-lookup"><span data-stu-id="1d598-222">**Started** and **Ended** : The start date and end date of the campaign.</span></span> <span data-ttu-id="1d598-223">これらの日付は、[概要] ページで選択したフィルター日付よりも長く延長される可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-223">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="1d598-224">**影響** : このセクションには、選択した日付範囲フィルター (またはタイムラインで選択する) について、次のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d598-224">**Impact** : This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  - <span data-ttu-id="1d598-225">受信者の合計数。</span><span class="sxs-lookup"><span data-stu-id="1d598-225">The total number of recipients.</span></span>
  - <span data-ttu-id="1d598-226">"Inboxed" (つまり、受信トレイに配信され、迷惑メールフォルダーに配信されなかったメッセージ) の数。</span><span class="sxs-lookup"><span data-stu-id="1d598-226">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="1d598-227">フィッシングメッセージの URL ペイロードでユーザーがクリックした回数。</span><span class="sxs-lookup"><span data-stu-id="1d598-227">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="1d598-228">ハウ多くのユーザーが URL を訪れた。</span><span class="sxs-lookup"><span data-stu-id="1d598-228">Howe many users visited the URL.</span></span>

- <span data-ttu-id="1d598-229">**対象** : ([組織内のキャンペーン受信者の数])/(サービス内のすべての組織にわたるキャンペーンの受信者の合計数) の計算結果の割合。</span><span class="sxs-lookup"><span data-stu-id="1d598-229">**Targeted** : The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="1d598-230">この値は、キャンペーンのすべての期間にわたって計算され、日付フィルターに基づいて変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-230">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="1d598-231">対話的なキャンペーンアクティビティのタイムライン: タイムラインは、キャンペーンの有効期間全体にわたるアクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-231">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="1d598-232">既定では、影付き領域には概要で選択した日付範囲フィルターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d598-232">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="1d598-233">次のセクションで説明されているように、をクリックしてドラッグすると、特定の開始点と終了点を選択し <u>て、 **影響** 領域に表示されるデータとその他のページの残りの部分</u>を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-233">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="1d598-234">タイトルバーで [キャンペーンの **作成** ] ボタンをクリックすると、キャンペーンの ![ 詳細が ](../../media/download-campaign-write-up-button.png) Word 文書 (既定では、CampaignReport.docx) にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="1d598-234">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="1d598-235">ダウンロードには、(選択したフィルター日付だけでなく) キャンペーンの有効期間全体に関する詳細が含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-235">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![キャンペーン情報](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="1d598-237">キャンペーン フロー</span><span class="sxs-lookup"><span data-stu-id="1d598-237">Campaign flow</span></span>

<span data-ttu-id="1d598-238">キャンペーン詳細ビューの中央に、キャンペーンに関する重要な詳細が、水平方向のフロー図 ( _Sankey_ 図) の [ **flow** ] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-238">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="1d598-239">これらの詳細情報は、キャンペーンの要素および組織に与えている可能性のある影響を理解する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d598-239">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="1d598-240">**フロー** 図に表示される情報は、前のセクションで説明したように、タイムラインの網かけの日付範囲によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-240">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![ユーザーによる URL のクリックがなかったキャンペーンの詳細](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="1d598-242">図内の横方向の帯にマウスのポインターを合わせると、関連するさまざまなメッセージが表示されます (特定のソース IP からのメッセージ、指定した送信者ドメインを使用した、特定のソース IP からのメッセージなど)。</span><span class="sxs-lookup"><span data-stu-id="1d598-242">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="1d598-243">図には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d598-243">The diagram contains the following information:</span></span>

- <span data-ttu-id="1d598-244">[ **Sender IPs (送信者の IP)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-244">**Sender IPs**</span></span>
- <span data-ttu-id="1d598-245">[ **Sender domains (送信者のドメイン)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-245">**Sender domains**</span></span>
- <span data-ttu-id="1d598-246">**Filter verdicts** : Verdict の値は、「 [スパム対策メッセージヘッダー](anti-spam-message-headers.md)」で説明されているように、使用可能なフィッシングおよびスパムフィルタリング verdicts に関連しています。</span><span class="sxs-lookup"><span data-stu-id="1d598-246">**Filter verdicts** : Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="1d598-247">次の表では、使用可能な値について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d598-247">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="1d598-248">値</span><span class="sxs-lookup"><span data-stu-id="1d598-248">Value</span></span>|<span data-ttu-id="1d598-249">スパムフィルターの verdict</span><span class="sxs-lookup"><span data-stu-id="1d598-249">Spam filter verdict</span></span>|<span data-ttu-id="1d598-250">説明</span><span class="sxs-lookup"><span data-stu-id="1d598-250">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="1d598-251">**可**</span><span class="sxs-lookup"><span data-stu-id="1d598-251">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="1d598-252">スパムフィルターによって評価される前に、メッセージがスパムではないとマークされた、またはスキップされたフィルター処理。</span><span class="sxs-lookup"><span data-stu-id="1d598-252">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="1d598-253">たとえば、メールフロールール (トランスポートルールとも呼ばれる) によって、メッセージがスパムではないとマークされた場合などです。</span><span class="sxs-lookup"><span data-stu-id="1d598-253">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="1d598-254">その他の理由により、メッセージはスパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="1d598-254">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="1d598-255">たとえば、送信者と受信者が同じ組織内にあるように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-255">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="1d598-256">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="1d598-256">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="1d598-257">スパムフィルターによって評価される前に、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="1d598-257">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="1d598-258">たとえば、メールフロールールによって。</span><span class="sxs-lookup"><span data-stu-id="1d598-258">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="1d598-259">[ **Detected (検出済み)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-259">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="1d598-260">スパム フィルタリングによって、メッセージがスパムとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="1d598-260">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="1d598-261">**検出されません**</span><span class="sxs-lookup"><span data-stu-id="1d598-261">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="1d598-262">メッセージがスパムフィルター処理によって迷惑メールではないとマークされました。</span><span class="sxs-lookup"><span data-stu-id="1d598-262">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="1d598-263">**時点**</span><span class="sxs-lookup"><span data-stu-id="1d598-263">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="1d598-264">メッセージは検疫から解放されたため、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="1d598-264">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="1d598-265">**テナント許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d598-265">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="1d598-266">スパム対策ポリシーの設定により、メッセージはスパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="1d598-266">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="1d598-267">たとえば、送信者が許可された送信者の一覧または許可されたドメインリストに含まれていた場合です。</span><span class="sxs-lookup"><span data-stu-id="1d598-267">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="1d598-268">**テナントブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d598-268">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="1d598-269">スパム対策ポリシーの設定により、メッセージはスパムフィルター処理によってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="1d598-269">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="1d598-270">たとえば、送信者が許可された送信者の一覧または許可されたドメインリストに含まれていた場合です。</span><span class="sxs-lookup"><span data-stu-id="1d598-270">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="1d598-271">**ユーザー許可**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d598-271">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="1d598-272">送信者がユーザーの差出人セーフリストに含まれていたため、メッセージはスパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="1d598-272">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="1d598-273">**ユーザーブロック**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="1d598-273">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="1d598-274">送信者がユーザーの受信拒否リストに含まれていたため、メッセージはスパムフィルター処理によってブロックされました。</span><span class="sxs-lookup"><span data-stu-id="1d598-274">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="1d598-275">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="1d598-275">**ZAP**</span></span>|<span data-ttu-id="1d598-276">該当なし</span><span class="sxs-lookup"><span data-stu-id="1d598-276">n/a</span></span>|<span data-ttu-id="1d598-277">[ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md) は、配信されたメッセージを迷惑メールフォルダーまたは検疫に移動しました。</span><span class="sxs-lookup"><span data-stu-id="1d598-277">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="1d598-278">このアクションは、スパム対策ポリシーで構成します。</span><span class="sxs-lookup"><span data-stu-id="1d598-278">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="1d598-279"><sup>\*</sup> 許可されたメッセージがサービスによってブロックされている可能性があるので、スパム対策ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-279"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="1d598-280"><sup>\*\*</sup> スパム対策ポリシーを確認してください。これらのメッセージは配信されないため、検疫される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-280"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="1d598-281">**配信場所** : ユーザーがメッセージ内のペイロード URL をクリックしていない場合でも、受信者に配信されたメッセージ (受信トレイまたは迷惑メールフォルダー) を調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-281">**Delivery locations** : You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="1d598-282">検疫されたメッセージを検疫から削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="1d598-282">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="1d598-283">詳細については、「EOP での検疫された [電子メールメッセージ](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d598-283">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>
  - <span data-ttu-id="1d598-284">**フォルダーの削除**</span><span class="sxs-lookup"><span data-stu-id="1d598-284">**Deleted folder**</span></span>
  - <span data-ttu-id="1d598-285">**落下**</span><span class="sxs-lookup"><span data-stu-id="1d598-285">**Dropped**</span></span>
  - <span data-ttu-id="1d598-286">**外部** : 受信者は、ハイブリッド環境でオンプレミスの電子メール組織に配置されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-286">**External** : The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="1d598-287">**Failed**</span><span class="sxs-lookup"><span data-stu-id="1d598-287">**Failed**</span></span>
  - <span data-ttu-id="1d598-288">**転送**</span><span class="sxs-lookup"><span data-stu-id="1d598-288">**Forwarded**</span></span>
  - <span data-ttu-id="1d598-289">[ **Inbox (受信トレイ)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-289">**Inbox**</span></span>
  - <span data-ttu-id="1d598-290">[ **Junk folder (迷惑メール フォルダー)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-290">**Junk folder**</span></span>
  - <span data-ttu-id="1d598-291">[ **Quarantine (検疫)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-291">**Quarantine**</span></span>
  - <span data-ttu-id="1d598-292">**不明**</span><span class="sxs-lookup"><span data-stu-id="1d598-292">**Unknown**</span></span>

- <span data-ttu-id="1d598-293">**URL のクリック** : これらの値については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="1d598-293">**URL clicks** : These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="1d598-294">10個を超えるアイテムが含まれるすべてのレイヤーでは、上位10個のアイテムが表示され、残りのアイテムは **他のユーザー** にバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="1d598-294">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="1d598-295">URL のクリック</span><span class="sxs-lookup"><span data-stu-id="1d598-295">URL clicks</span></span>

<span data-ttu-id="1d598-296">フィッシングメッセージが受信者の受信トレイまたは迷惑メールフォルダーに配信される場合、常に、ユーザーがペイロード URL をクリックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-296">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="1d598-297">URL をクリックしても成功することはありませんが、フィッシングメッセージがメールボックスに配信された理由を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d598-297">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="1d598-298">ユーザーがフィッシングメッセージ内のペイロード URL をクリックすると、アクションがキャンペーン詳細ビューのダイアグラムの [ **URL** ] 領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-298">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="1d598-299">**可**</span><span class="sxs-lookup"><span data-stu-id="1d598-299">**Allowed**</span></span>
- <span data-ttu-id="1d598-300">**Blockpage** : 受信者がペイロード URL をクリックしたが、悪意のある web サイトへのアクセスが組織内の [安全なリンク](atp-safe-links.md) ポリシーによってブロックされた。</span><span class="sxs-lookup"><span data-stu-id="1d598-300">**BlockPage** : The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>
- <span data-ttu-id="1d598-301">**Blockpageoverride** : 受信者がメッセージ内のペイロード URL をクリックしました。安全なリンクは停止しようとしましたが、ブロックを上書きすることが許可されていました。</span><span class="sxs-lookup"><span data-stu-id="1d598-301">**BlockPageOverride** : The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="1d598-302">「 [安全なリンク」ポリシー](set-up-atp-safe-links-policies.md) を調べて、ユーザーが安全なリンクの verdict を上書きできる理由を確認し、悪意のある web サイトを続行します。</span><span class="sxs-lookup"><span data-stu-id="1d598-302">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>
- <span data-ttu-id="1d598-303">**PendingDetonationPage** : Microsoft Defender for Office 365 の安全な添付ファイルは、仮想コンピューター環境でペイロード URL を開いて調査する処理を行っています。</span><span class="sxs-lookup"><span data-stu-id="1d598-303">**PendingDetonationPage** : Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>
- <span data-ttu-id="1d598-304">**PendingDetonationPageOverride** : 受信者は、ペイロード分析プロセスを上書きすることを許可され、結果を待たずに URL を開くことができました。</span><span class="sxs-lookup"><span data-stu-id="1d598-304">**PendingDetonationPageOverride** : The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="1d598-305">タブ</span><span class="sxs-lookup"><span data-stu-id="1d598-305">Tabs</span></span>

<span data-ttu-id="1d598-306">[キャンペーンの詳細] ビューのタブでは、キャンペーンの詳細を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="1d598-306">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="1d598-307">タブに表示される情報は、タイムラインの [ [キャンペーン情報](#campaign-information) ] セクションで示されているように、網かけの日付範囲によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-307">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="1d598-308">**URL クリック** : ユーザーがメッセージ内のペイロード URL をクリックしなかった場合、このセクションは空白になります。</span><span class="sxs-lookup"><span data-stu-id="1d598-308">**URL clicks** : If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="1d598-309">ユーザーが URL をクリックできた場合は、次の値が入力されます。</span><span class="sxs-lookup"><span data-stu-id="1d598-309">If a user was able to click on the URL, the following values will be populated:</span></span>
  - <span data-ttu-id="1d598-310">[ **User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="1d598-310">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="1d598-311">[ **URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="1d598-311">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="1d598-312">**[時刻] をクリック**</span><span class="sxs-lookup"><span data-stu-id="1d598-312">**Click time**</span></span>
  - <span data-ttu-id="1d598-313">**[Verdict] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="1d598-313">**Click verdict**</span></span>

- <span data-ttu-id="1d598-314">[ **Sender IPs (送信者の IP)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-314">**Sender IPs**</span></span>
  - <span data-ttu-id="1d598-315">[ **Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="1d598-315">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="1d598-316">**合計数**</span><span class="sxs-lookup"><span data-stu-id="1d598-316">**Total count**</span></span>
  - <span data-ttu-id="1d598-317">**ボックス (内側)**</span><span class="sxs-lookup"><span data-stu-id="1d598-317">**Inboxed**</span></span>
  - <span data-ttu-id="1d598-318">**ボックスなし**</span><span class="sxs-lookup"><span data-stu-id="1d598-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="1d598-319">**Spf が渡さ** れました。送信者は [sender POLICY Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)によって認証されました。</span><span class="sxs-lookup"><span data-stu-id="1d598-319">**SPF passed** : The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="1d598-320">SPF 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-320">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="1d598-321">[ **Senders (送信者)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-321">**Senders**</span></span>
  - <span data-ttu-id="1d598-322">**Sender** : これは、SMTP MAIL FROM コマンドの実際の送信者アドレスです。これは、必ずしも、ユーザーが電子メールクライアントに表示する from: 電子メールアドレスであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1d598-322">**Sender** : This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="1d598-323">**合計数**</span><span class="sxs-lookup"><span data-stu-id="1d598-323">**Total count**</span></span>
  - <span data-ttu-id="1d598-324">**ボックス (内側)**</span><span class="sxs-lookup"><span data-stu-id="1d598-324">**Inboxed**</span></span>
  - <span data-ttu-id="1d598-325">**ボックスなし**</span><span class="sxs-lookup"><span data-stu-id="1d598-325">**Not Inboxed**</span></span>
  - <span data-ttu-id="1d598-326">**Dkim が渡さ** れました: 送信者はドメインキーで識別された [メール (dkim)](support-for-validation-of-dkim-signed-messages.md)によって認証されました。</span><span class="sxs-lookup"><span data-stu-id="1d598-326">**DKIM passed** : The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="1d598-327">DKIM 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-327">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="1d598-328">**DMARC が渡さ** れました。送信者は、 [ドメインベースのメッセージ認証、レポート、および準拠 (DMARC)](use-dmarc-to-validate-email.md)によって認証されています。</span><span class="sxs-lookup"><span data-stu-id="1d598-328">**DMARC passed** : The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="1d598-329">DMARC 検証に合格しない送信者は、認証されていない送信者、またはメッセージが正当な送信者を偽装していることを示します。</span><span class="sxs-lookup"><span data-stu-id="1d598-329">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="1d598-330">**添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1d598-330">**Attachments**</span></span>
  - <span data-ttu-id="1d598-331">**Filename**</span><span class="sxs-lookup"><span data-stu-id="1d598-331">**Filename**</span></span>
  - <span data-ttu-id="1d598-332">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="1d598-332">**SHA256**</span></span>
  - <span data-ttu-id="1d598-333">**マルウェアファミリ**</span><span class="sxs-lookup"><span data-stu-id="1d598-333">**Malware family**</span></span>
  - <span data-ttu-id="1d598-334">**合計数**</span><span class="sxs-lookup"><span data-stu-id="1d598-334">**Total count**</span></span>

- <span data-ttu-id="1d598-335">**URL**</span><span class="sxs-lookup"><span data-stu-id="1d598-335">**URL**</span></span>
  - <span data-ttu-id="1d598-336">[ **URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="1d598-336">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="1d598-337">[ **Total Count (総数)** ]</span><span class="sxs-lookup"><span data-stu-id="1d598-337">**Total Count**</span></span>

<span data-ttu-id="1d598-338"><sup>\*</sup> この値をクリックすると、指定したアイテム (ユーザー、URL など) についての詳細情報を含む新しいポップアップがキャンペーンの詳細ビューの上に開きます。</span><span class="sxs-lookup"><span data-stu-id="1d598-338"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="1d598-339">キャンペーンの詳細ビューに戻るには、表示されたフライアウトで [ **Done (完了)** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d598-339">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="1d598-340">ボタン</span><span class="sxs-lookup"><span data-stu-id="1d598-340">Buttons</span></span>

<span data-ttu-id="1d598-341">キャンペーンの詳細ビューのボタンを使用すると、脅威エクスプローラーを使用してキャンペーンを詳しく調査できます。</span><span class="sxs-lookup"><span data-stu-id="1d598-341">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="1d598-342">[ **Explore campaign (キャンペーンの調査)** ]: **Campaign ID (キャンペーンの ID)** 値を検索フィルターとして使用する新しい脅威エクスプローラーの検索タブが開かれます。</span><span class="sxs-lookup"><span data-stu-id="1d598-342">**Explore campaign** : Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>
- <span data-ttu-id="1d598-343">[検索] ボックス内の **メッセージ** : **キャンペーン ID** と **配信場所: 受信トレイ** を検索フィルターとして使用して、新しい脅威エクスプローラー検索タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d598-343">**Explore Inboxed messages** : Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
