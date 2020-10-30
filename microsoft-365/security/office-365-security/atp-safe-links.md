---
title: 安全なリンク
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: この記事では、管理者は、Office 365 Advanced Threat Protection (ATP) の安全なリンク保護について学習し、悪意のある Url を使用するフィッシングやその他の攻撃から組織を保護することができます。
ms.openlocfilehash: 45936cabf012c5f40080f3bbfee224aec9593d30
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806728"
---
# <a name="safe-links-in-office-365-atp"></a><span data-ttu-id="efb67-103">Office 365 ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="efb67-103">Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="efb67-104">この記事は、 [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md)を使用しているビジネスお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="efb67-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="efb67-105">Outlook.com、Microsoft 365 ファミリ、または Microsoft 365 Personal を使用していて、Outlook で Safelinks に関する情報を探している場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-105">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="efb67-106">「安全なリンク」とは、 [Office 365 Advanced Threat Protection](office-365-atp.md) の機能の1つで、メールフローでの受信電子メールメッセージのスキャンとリライト、および電子メールメッセージやその他の場所での url とリンクのクリック時間の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="efb67-106">Safe Links is a feature in [Office 365 Advanced Threat Protection](office-365-atp.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="efb67-107">[安全なリンク] スキャンは、Exchange Online Protection (EOP) の受信電子メールメッセージでの通常の [スパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md) に加えて実行されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-107">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="efb67-108">安全なリンクスキャンは、フィッシングやその他の攻撃で使用されている悪意のあるリンクから組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="efb67-108">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="efb67-109">安全なリンク保護は、次の場所で利用できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-109">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="efb67-110">**電子メールメッセージ** : 「安全なリンク」電子メールメッセージ内のリンクの保護は、安全なリンクのポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-110">**Email messages** : Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="efb67-111">既定の安全なリンクポリシーはありません。 **そのため、電子メールメッセージ内の安全なリンクを保護するには、1つ以上の安全なリンクポリシーを作成する必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-111">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies** .</span></span> <span data-ttu-id="efb67-112">手順については、「 [ATP で安全なリンクポリシーを設定](set-up-atp-safe-links-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-112">For instructions, see [Set up Safe Links policies in ATP](set-up-atp-safe-links-policies.md).</span></span>

  <span data-ttu-id="efb67-113">電子メールメッセージの安全なリンク保護の詳細については、この記事で後述する「 [電子メールメッセージの安全なリンクの設定](#safe-links-settings-for-email-messages) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-113">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="efb67-114">**Microsoft Teams** (現在はタッププレビュー): Teams 会話、グループチャット、またはチャネル内のリンクに対する安全なリンク保護も、「安全なリンク」ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-114">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="efb67-115">既定の安全なリンクポリシーはありません。 **そのため、Teams での安全なリンクを保護するには、1つ以上の安全なリンクポリシーを作成する必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-115">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies** .</span></span>

  <span data-ttu-id="efb67-116">Teams での安全なリンク保護の詳細については、このトピックで後述する「 [Microsoft Teams の安全なリンクの設定](#safe-links-settings-for-microsoft-teams) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-116">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this topic.</span></span>

- <span data-ttu-id="efb67-117">**Office 365 apps** : office 365 アプリの安全なリンク保護は、サポートされているデスクトップ、モバイル、および web aps で利用できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-117">**Office 365 apps** : Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="efb67-118">「安全なリンクの保護」を、「安全なリンク」ポリシーの **外部** にあるグローバル設定の Office 365 アプリに対して **構成** します。</span><span class="sxs-lookup"><span data-stu-id="efb67-118">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="efb67-119">手順については、「 [Office 365 ATP の安全なリンクのグローバル設定を構成する](configure-global-settings-for-safe-links.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-119">For instructions, see [Configure global settings for Safe Links settings in Office 365 ATP](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="efb67-120">ただし、Office 365 アプリの安全なリンク保護は、アクティブな安全リンクポリシーに含まれているユーザーにのみ **適用** されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-120">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="efb67-121">ユーザーがアクティブな安全リンクポリシーに含まれていない場合、ユーザーはサポートされている Office 365 アプリで安全なリンク保護を受けられません。</span><span class="sxs-lookup"><span data-stu-id="efb67-121">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="efb67-122">Office 365 アプリでの安全なリンク保護の詳細については、この記事で後述する「 [office 365 アプリの安全なリンクの設定](#safe-links-settings-for-office-365-apps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-122">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="efb67-123">この記事には、次の種類の安全なリンク設定についての詳細な説明が記載されています。</span><span class="sxs-lookup"><span data-stu-id="efb67-123">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="efb67-124">**安全なリンクポリシーの設定** : これらの設定は、特定のポリシーに含まれるユーザーにのみ適用され、ポリシーによって設定が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-124">**Settings in Safe Links policies** : These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="efb67-125">これらの設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="efb67-125">These settings include:</span></span>

  - [<span data-ttu-id="efb67-126">電子メールメッセージの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="efb67-126">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="efb67-127">Microsoft Teams の安全なリンクの設定</span><span class="sxs-lookup"><span data-stu-id="efb67-127">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="efb67-128">「安全なリンクポリシー」の「次の Url を書き換えない」の一覧</span><span class="sxs-lookup"><span data-stu-id="efb67-128">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="efb67-129">**グローバルな安全リンク設定** : これらの設定は、安全なリンクポリシーではなく、グローバルに構成されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-129">**Global Safe Links settings** : These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="efb67-130">ただし、この設定は、アクティブな安全なリンクポリシーに含まれるユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-130">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="efb67-131">これらの設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="efb67-131">These settings include:</span></span>

  - [<span data-ttu-id="efb67-132">Office 365 アプリの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="efb67-132">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="efb67-133">「安全なリンク」の「次の Url をブロックする」リスト</span><span class="sxs-lookup"><span data-stu-id="efb67-133">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="efb67-134">次の表では、ATP を含む Microsoft 365 と Office 365 組織の安全なリンクのシナリオについて説明します (つまり、ライセンスの不足が例では問題になることはありません)。</span><span class="sxs-lookup"><span data-stu-id="efb67-134">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include ATP (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="efb67-135">シナリオ</span><span class="sxs-lookup"><span data-stu-id="efb67-135">Scenario</span></span>|<span data-ttu-id="efb67-136">結果</span><span class="sxs-lookup"><span data-stu-id="efb67-136">Result</span></span>|
|---|---|
|<span data-ttu-id="efb67-137">田中はマーケティング部門のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="efb67-137">Jean is a member of the marketing department.</span></span> <span data-ttu-id="efb67-138">安全なリンク保護 Office 365 アプリは、安全なリンクのためのグローバル設定で有効になっており、マーケティング部門のメンバーに適用される安全なリンクポリシーが存在しています。</span><span class="sxs-lookup"><span data-stu-id="efb67-138">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="efb67-139">田中は、電子メールメッセージで PowerPoint プレゼンテーションを開き、プレゼンテーション内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-139">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="efb67-140">田中は、安全なリンクで保護されています。</span><span class="sxs-lookup"><span data-stu-id="efb67-140">Jean is protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="efb67-141">田中は安全なリンクポリシーに含まれており、安全なリンクによる Office 365 アプリの保護が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-141">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <br/><br/> <span data-ttu-id="efb67-142">Office 365 アプリでの安全なリンク保護の要件の詳細については、この記事で後述する「 [office 365 アプリの安全なリンクの設定](#safe-links-settings-for-office-365-apps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-142">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="efb67-143">Chris の Microsoft 365 E5 組織には、安全なリンクポリシーが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="efb67-143">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="efb67-144">Chris は、最終的にクリックした悪意のある web サイトへの URL が含まれている外部の送信者からの電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="efb67-144">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="efb67-145">Chris は、安全なリンクによって保護されていません。</span><span class="sxs-lookup"><span data-stu-id="efb67-145">Chris is not protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="efb67-146">管理者は、受信メールメッセージの安全なリンク保護を取得するために、少なくとも1つの安全なリンクポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-146">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="efb67-147">安全なリンク保護を得るには、小川をポリシーの条件に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-147">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="efb67-148">Pat の組織では、管理者は安全なリンクポリシーを作成していませんが、Office 365 アプリの安全なリンク保護は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-148">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="efb67-149">[Pat] Word 文書を開き、ファイル内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-149">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="efb67-150">Pat は、安全なリンクによって保護されていません。</span><span class="sxs-lookup"><span data-stu-id="efb67-150">Pat is not protected by Safe Links.</span></span> <br/><br/> <span data-ttu-id="efb67-151">Office 365 アプリの安全なリンク保護はグローバルに有効になっていますが、Pat はアクティブな安全リンクポリシーに含まれていないため、保護を適用できません。</span><span class="sxs-lookup"><span data-stu-id="efb67-151">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="efb67-152">Lee の組織では、[ `https://tailspintoys.com` 安全なリンク] のグローバル設定の [ **次の Url をブロック** する] の一覧に構成されています。</span><span class="sxs-lookup"><span data-stu-id="efb67-152">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="efb67-153">Lee を含む安全なリンクポリシーが既に存在しています。</span><span class="sxs-lookup"><span data-stu-id="efb67-153">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="efb67-154">Lee は、URL を含む電子メールメッセージを受信 `https://tailspintoys.com/aboutus/trythispage` します。</span><span class="sxs-lookup"><span data-stu-id="efb67-154">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="efb67-155">Lee が URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-155">Lee clicks the URL.</span></span>|<span data-ttu-id="efb67-156">URL は Lee に対して自動的にブロックされることがあります。これは、リストの URL エントリと、電子メールクライアント Lee が使用されることによって決まります。</span><span class="sxs-lookup"><span data-stu-id="efb67-156">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="efb67-157">詳細については、このトピックで後述する「 [安全なリンクのための次の url をブロック](#block-the-following-urls-list-for-safe-links) する」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-157">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this topic.</span></span>|
|<span data-ttu-id="efb67-158">森さんと佐々木課長の両方が contoso.com に対応します。</span><span class="sxs-lookup"><span data-stu-id="efb67-158">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="efb67-159">以前は、青木俊之と佐々木課長の両方に適用される安全なリンクポリシーを管理者が構成していました。</span><span class="sxs-lookup"><span data-stu-id="efb67-159">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="efb67-160">久保田さんは、電子メールに悪意のある URL が含まれていることを知らずに、佐々木課長に電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="efb67-160">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="efb67-161">佐々木課長は、自分に適用する安全なリンクポリシーが内部の受信者間のメッセージに適用されるように構成されて **いる場合** は、安全なリンクによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-161">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="efb67-162">詳細については、このトピックで後述する「 [電子メールメッセージの安全なリンクの設定](#safe-links-settings-for-email-messages) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-162">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this topic.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="efb67-163">電子メールメッセージの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="efb67-163">Safe Links settings for email messages</span></span>

<span data-ttu-id="efb67-164">「安全なリンク」は、既知の悪意のあるハイパーリンクを受信する電子メールをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="efb67-164">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="efb67-165">スキャンした Url は、Microsoft 標準 URL プレフィックス: を使用して書き換えられ `https://nam01.safelinks.protection.outlook.com` ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-165">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="efb67-166">リンクが書き換えられた後、潜在的な悪意のあるコンテンツを分析します。</span><span class="sxs-lookup"><span data-stu-id="efb67-166">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="efb67-167">安全なリンクによって URL が書き換えられると、メッセージが転送または返信された場合でも、URL は書き換えられたままになります。</span><span class="sxs-lookup"><span data-stu-id="efb67-167">After Safe Links rewrites a URL, the URL remains rewritten, even if the message is forwarded or replied to.</span></span> <span data-ttu-id="efb67-168">転送または返信するメッセージに追加されたリンクは書き換えられません。</span><span class="sxs-lookup"><span data-stu-id="efb67-168">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span>

<span data-ttu-id="efb67-169">電子メールメッセージに適用される「安全なリンク」ポリシーの設定については、次のリストで説明します。</span><span class="sxs-lookup"><span data-stu-id="efb67-169">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="efb67-170">**メッセージ内の不明な悪意のある url に対するアクションを選択し** ます。電子メールメッセージでの安全なリンクスキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="efb67-170">**Select the action for unknown potentially malicious URLs in messages** : Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="efb67-171">推奨値は **On** です。</span><span class="sxs-lookup"><span data-stu-id="efb67-171">The recommended value is **On** .</span></span> <span data-ttu-id="efb67-172">この設定を有効にすると、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-172">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="efb67-173">安全なリンクのスキャンは、Windows の Outlook (C2R) で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-173">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="efb67-174">Url は書き換えられ、ユーザーがメッセージ内の Url をクリックしたときに安全なリンク保護によってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-174">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="efb67-175">クリックすると、既知の悪意のある Url の一覧と、 [[次の url をブロックする] の一覧](#block-the-following-urls-list-for-safe-links)に対して url がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-175">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="efb67-176">有効な評価を持たない Url は、バックグラウンドで非同期的に分析れます。</span><span class="sxs-lookup"><span data-stu-id="efb67-176">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="efb67-177">**疑わしいリンクおよびファイルを指しているリンクに対してリアルタイム URL スキャンを適用する** : ダウンロード可能なコンテンツを参照する電子メールメッセージ内のリンクを含む、リンクのリアルタイムスキャンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="efb67-177">**Apply real-time URL scanning for suspicious links and links that point to files** : Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="efb67-178">推奨値は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-178">The recommended value is enabled.</span></span>

  - <span data-ttu-id="efb67-179">**メッセージを配信する前に、URL のスキャンが完了するのを待機し** ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-179">**Wait for URL scanning to complete before delivering the message** :</span></span>

    - <span data-ttu-id="efb67-180">Enabled: Url を含むメッセージは、スキャンが完了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-180">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="efb67-181">メッセージは、Url が安全であることが確認された後にのみ配信されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-181">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="efb67-182">この値を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efb67-182">This is the recommended value.</span></span>
    - <span data-ttu-id="efb67-183">Disabled: URL スキャンを完了できなかった場合は、そのままメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="efb67-183">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="efb67-184">**組織内で送信される電子メールメッセージへの安全なリンクの適用** : 内部送信者と同じ Exchange Online 組織内の内部受信者との間で送信されたメッセージに対する安全なリンクスキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="efb67-184">**Apply Safe Links to email messages sent within the organization** : Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="efb67-185">推奨値は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-185">The recommended value is enabled.</span></span>

- <span data-ttu-id="efb67-186">[ **ユーザーのクリックを追跡しない** ]: 安全なリンクの保存を有効または無効にする電子メールメッセージ内でクリックされた url のデータをクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-186">**Do not track user clicks** : Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="efb67-187">推奨値は、この設定をオフのままにします (ユーザーのクリックを追跡するため)。</span><span class="sxs-lookup"><span data-stu-id="efb67-187">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="efb67-188">URL 内部送信者と内部受信者との間で送信される電子メールメッセージ内のリンクの [追跡] をクリックします。現在はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efb67-188">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="efb67-189">**[ユーザーが元の url に** 移動できないようにする]: ユーザーが [警告ページ](#warning-pages-from-safe-links) で元の url にクリックすることを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="efb67-189">**Do not allow users to click through to original URL** : Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="efb67-190">推奨値は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-190">The recommend value is enabled.</span></span>

- <span data-ttu-id="efb67-191">**次の url を書き換えないで** ください。 url をそのまま残します。</span><span class="sxs-lookup"><span data-stu-id="efb67-191">**Do not rewrite the following URLs** : Leaves URLs as they are.</span></span> <span data-ttu-id="efb67-192">スキャンを必要としない安全な Url のカスタムリストを保持します。</span><span class="sxs-lookup"><span data-stu-id="efb67-192">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="efb67-193">このリストは、安全なリンクポリシーごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="efb67-193">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="efb67-194">[次の Url を **書き換え** ない] の一覧の詳細については、この記事の後半の「 [安全なリンクポリシー」の「次の url を書き換えない](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 」の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-194">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="efb67-195">「安全なリンク」ポリシーの標準および厳密なポリシー設定に推奨される値の詳細については、「 [安全なリンクポリシー設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-195">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="efb67-196">**受信者フィルター** : ポリシーの適用先を決定する受信者の条件と例外を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-196">**Recipient filters** : You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="efb67-197">条件や例外には次のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-197">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="efb67-198">**受信者が次の場合**</span><span class="sxs-lookup"><span data-stu-id="efb67-198">**The recipient is**</span></span>
  - <span data-ttu-id="efb67-199">**受信者のドメインが**</span><span class="sxs-lookup"><span data-stu-id="efb67-199">**The recipient domain is**</span></span>
  - <span data-ttu-id="efb67-200">**受信者が次のメンバーの場合**</span><span class="sxs-lookup"><span data-stu-id="efb67-200">**The recipient is a member of**</span></span>

  <span data-ttu-id="efb67-201">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="efb67-201">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="efb67-202">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、 _\<recipient1\>_ または _\<recipient2\>_ ) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-202">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="efb67-203">a別の条件や例外がある場合は AND ロジック (たとえば、 _\<recipient1\>_ かつ _\<member of group 1\>_ ) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-203">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

- <span data-ttu-id="efb67-204">**優先度** : 複数のポリシーを作成する場合は、適用する順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-204">**Priority** : If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="efb67-205">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="efb67-205">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="efb67-206">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-206">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="efb67-207">電子メールメッセージの安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="efb67-207">How Safe Links works in email messages</span></span>

<span data-ttu-id="efb67-208">電子メールメッセージ内の Url に対して安全なリンク保護がどのように機能するかについては、概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efb67-208">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="efb67-209">すべての電子メールは、メッセージが受信者のメールボックスに配信される前に、インターネットプロトコル (IP) フィルター、エンベロープフィルター、署名ベースのマルウェア対策、スパム対策およびマルウェア対策フィルターを使用した EOP を通過します。</span><span class="sxs-lookup"><span data-stu-id="efb67-209">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="efb67-210">ユーザーは、自分のメールボックスでメッセージを開き、メッセージの URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-210">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="efb67-211">安全なリンクは、web サイトを開く前に、すぐに URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-211">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="efb67-212">[ **次の url をブロック** する] の一覧に url が含まれている場合は、ブロックされた [url の警告](#blocked-url-warning) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-212">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="efb67-213">URL が悪意があると判断された web サイトを指している場合は、悪意のある [web サイトの警告](#malicious-website-warning) ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="efb67-213">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="efb67-214">URL がダウンロード可能なファイルを指しており、[ **不審なリンクに対してリアルタイムの url スキャンを適用** する] 設定が有効になっている場合、ユーザーに適用されるポリシーでは、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-214">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="efb67-215">URL が安全であると判断された場合は、web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="efb67-215">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="efb67-216">Microsoft Teams の安全なリンクの設定</span><span class="sxs-lookup"><span data-stu-id="efb67-216">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efb67-217">この機能は2020年3月に公開されており、Microsoft Teams テクノロジ導入プログラム (タップ) のメンバーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-217">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="efb67-218">リリーススケジュールの詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efb67-218">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="efb67-219">「安全なリンク」ポリシーで、Microsoft Teams の安全なリンク保護を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="efb67-219">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="efb67-220">具体的には、 **[Microsoft Teams 内の不明または悪意のある url に対し** て、このアクションを選択する] 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="efb67-220">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="efb67-221">推奨値は **On** です。</span><span class="sxs-lookup"><span data-stu-id="efb67-221">The recommended value is **On** .</span></span>

<span data-ttu-id="efb67-222">電子メールメッセージ内のリンクに適用される「安全なリンク」ポリシーの次の設定は、Teams のリンクにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-222">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="efb67-223">**疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用する**</span><span class="sxs-lookup"><span data-stu-id="efb67-223">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="efb67-224">**ユーザーのクリックを追跡しない**</span><span class="sxs-lookup"><span data-stu-id="efb67-224">**Do not track user clicks**</span></span>
- <span data-ttu-id="efb67-225">**ユーザーが元の URL にクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="efb67-225">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="efb67-226">これらの設定については、「 [電子メールメッセージの以前の安全なリンクの設定](#safe-links-settings-for-email-messages) 」セクションで説明されています。</span><span class="sxs-lookup"><span data-stu-id="efb67-226">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="efb67-227">Microsoft Teams に対して安全なリンク保護を有効にした後、保護されたユーザーがリンクをクリックしたときに、既知の悪意のあるリンクの一覧に対して Teams の Url がチェックされます (クリック時の保護)。</span><span class="sxs-lookup"><span data-stu-id="efb67-227">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="efb67-228">Url は書き換えられません。</span><span class="sxs-lookup"><span data-stu-id="efb67-228">URLs are not rewritten.</span></span> <span data-ttu-id="efb67-229">悪意のあるリンクが見つかった場合、ユーザーは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-229">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="efb67-230">Teams 会話、グループチャット、またはチャネルでリンクがクリックされた場合、次のスクリーンショットに示されているような警告ページが既定の web ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-230">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="efb67-231">固定されたタブからリンクがクリックされた場合は、そのタブ内の Teams インターフェイスに警告ページが表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-231">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="efb67-232">ポリシーの [ **ユーザーが元の url に** 移動できないようにする] 設定が構成されているかどうかによって、ユーザーはクリックして元の url に移動することはできません (この **まま (非推奨)** 、スクリーンショットでは続行します)。</span><span class="sxs-lookup"><span data-stu-id="efb67-232">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL ( **Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="efb67-233">**[ユーザーが元の url** に移動できないようにする] 設定を有効にして、ユーザーが元の url にクリックできないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efb67-233">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="efb67-234">リンクを送信したユーザーが、Teams の保護が有効になっている安全なリンクポリシーに含まれていない場合、ユーザーは自分のコンピューターまたはデバイスで元の URL をクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="efb67-234">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![悪意のあるリンクを報告する Teams ページの安全なリンク。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="efb67-236">[警告] ページの [ **戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。</span><span class="sxs-lookup"><span data-stu-id="efb67-236">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="efb67-237">ただし、元のリンクをもう一度クリックすると、URL が再スキャンされ、警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-237">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="efb67-238">Teams での安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="efb67-238">How Safe Links works in Teams</span></span>

<span data-ttu-id="efb67-239">Microsoft Teams 内の Url に対して安全なリンク保護がどのように機能するかについては、概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="efb67-239">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="efb67-240">ユーザーが Teams アプリを開始します。</span><span class="sxs-lookup"><span data-stu-id="efb67-240">A user starts the Teams app.</span></span>

2. <span data-ttu-id="efb67-241">Microsoft 365 は、ユーザーの組織に Office 365 ATP が含まれていることと、Microsoft Teams の保護が有効になっているアクティブな安全なリンクポリシーにユーザーが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efb67-241">Microsoft 365 verifies that the user's organization includes Office 365 ATP, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="efb67-242">Url は、チャット、グループチャット、チャネル、およびタブ内のユーザーのクリック時に検証されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-242">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="efb67-243">Office 365 アプリの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="efb67-243">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="efb67-244">安全なリンク保護 Office 365 アプリは、電子メールメッセージ内のリンクではなく、Office ドキュメントのリンクをチェックします (ただし、添付された Office ドキュメントのリンクは、ドキュメントを開いた後に電子メールメッセージでチェックできます)。</span><span class="sxs-lookup"><span data-stu-id="efb67-244">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="efb67-245">Office 365 アプリの安全なリンク保護には、次のクライアント要件があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-245">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="efb67-246">Microsoft 365 アプリまたは Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="efb67-246">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="efb67-247">Windows、Mac、または web ブラウザー上の現在のバージョンの Word、Excel、および PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="efb67-247">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="efb67-248">IOS または Android デバイス上の Office アプリ。</span><span class="sxs-lookup"><span data-stu-id="efb67-248">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="efb67-249">Visio on Windows</span><span class="sxs-lookup"><span data-stu-id="efb67-249">Visio on Windows.</span></span>
  - <span data-ttu-id="efb67-250">Web ブラウザー内の OneNote。</span><span class="sxs-lookup"><span data-stu-id="efb67-250">OneNote in a web browser.</span></span>

- <span data-ttu-id="efb67-251">Office 365 アプリは先進認証を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="efb67-251">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="efb67-252">詳細については、「 [office 2013、office 2016、および office 2019 クライアントアプリの先進認証のしくみ](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-252">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>

- <span data-ttu-id="efb67-253">ユーザーは職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="efb67-253">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="efb67-254">詳細については、「 [Office にサインインする](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-254">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="efb67-255">「安全なリンクのポリシー」ではなく、「安全なリンクのためのグローバル設定」で Office 365 アプリの安全なリンク保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="efb67-255">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="efb67-256">ただし、Office 365 アプリに対して安全なリンク保護を適用するには、Office ドキュメントを開き、リンクをクリックするユーザーは、アクティブな安全リンクポリシーに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-256">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="efb67-257">Office 365 アプリでは、次の安全なリンクの設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-257">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="efb67-258">**Office 365 アプリケーション** : サポートされている office 365 アプリでの安全なリンクスキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="efb67-258">**Office 365 applications** : Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="efb67-259">既定値および推奨値は **On** です。</span><span class="sxs-lookup"><span data-stu-id="efb67-259">The default and recommended value is **On** .</span></span>

- <span data-ttu-id="efb67-260">**ユーザーが [安全なリンク] をクリックしたときに追跡しない** : 安全なリンクの保存を有効または無効にするデスクトップバージョンの Word、Excel、PowerPoint、および Visio でクリックされた url のデータをクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-260">**Do not track when users click Safe Links** : Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="efb67-261">推奨値は **Off** で、ユーザークリックが追跡されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="efb67-261">The recommended value is **Off** , which means user clicks are tracked.</span></span>

- <span data-ttu-id="efb67-262">**ユーザーが元の url への安全なリンクをクリックできない** ようにします。デスクトップ版の Word、Excel、PowerPoint、および Visio で、ユーザーが [警告ページ](#warning-pages-from-safe-links) から元の url に移動することを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-262">**Do not let users click through safe links to original URL** : Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="efb67-263">既定値および推奨値は **On** です。</span><span class="sxs-lookup"><span data-stu-id="efb67-263">The default and recommended value is **On** .</span></span>

<span data-ttu-id="efb67-264">Office 365 アプリの安全なリンク設定を構成するには、「 [office 365 アプリの安全なリンク保護を構成](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-264">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="efb67-265">標準および厳密なポリシー設定に推奨される値の詳細については、「 [安全なリンクのためのグローバル設定](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-265">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="efb67-266">Office 365 アプリでの安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="efb67-266">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="efb67-267">Office 365 アプリの Url に対して安全なリンク保護がどのように機能するかについては、大まかに説明します。</span><span class="sxs-lookup"><span data-stu-id="efb67-267">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="efb67-268">サポートされている Office 365 アプリについては、前のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="efb67-268">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="efb67-269">Microsoft 365 アプリまたは Microsoft 365 Business Premium を含む組織で、ユーザーが職場または学校のアカウントを使用してサインインしている。</span><span class="sxs-lookup"><span data-stu-id="efb67-269">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="efb67-270">ユーザーが、サポートされている Office アプリの Office ドキュメントを開いてクリックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-270">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="efb67-271">安全なリンクは、ターゲット web サイトを開く前に、すぐに URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-271">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="efb67-272">[安全なリンクのスキャンをスキップする ( **次の url の** リストをブロックする)] の一覧に url が含まれている場合は、[ブロックされる [url の警告](#blocked-url-warning) ] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="efb67-272">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="efb67-273">URL が悪意があると判断された web サイトを指している場合は、悪意のある [web サイトの警告](#malicious-website-warning) ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="efb67-273">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="efb67-274">URL がダウンロード可能なファイルを指しており、ユーザーに適用される安全なリンクポリシーが、ダウンロード可能なコンテンツ ( **疑わしいリンクおよびファイルを指すリンクのリアルタイム URL スキャンを適用** ) へのリンクをスキャンするように構成されている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-274">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content ( **Apply real-time URL scanning for suspicious links and links that point to files** ), the downloadable file is checked.</span></span>

   - <span data-ttu-id="efb67-275">URL が安全であると判断された場合は、ユーザーが web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="efb67-275">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="efb67-276">安全なリンクスキャンが完了できない場合は、安全なリンク保護はトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="efb67-276">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="efb67-277">Office デスクトップクライアントでは、ユーザーは宛先の web サイトに移動する前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-277">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="efb67-278">各セッションの開始時に数秒間かかることがあり、ユーザーが Office の安全なリンクを有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efb67-278">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="efb67-279">「安全なリンク」の「次の Url をブロックする」リスト</span><span class="sxs-lookup"><span data-stu-id="efb67-279">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="efb67-280">[ **次の url をブロック** する] の一覧では、次の場所にある安全リンクスキャンによって常にブロックされるリンクを定義します。</span><span class="sxs-lookup"><span data-stu-id="efb67-280">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="efb67-281">電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="efb67-281">Email messages.</span></span>
- <span data-ttu-id="efb67-282">Windows および Mac の Office 365 アプリのドキュメント。</span><span class="sxs-lookup"><span data-stu-id="efb67-282">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="efb67-283">IOS および Android 用の Office のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="efb67-283">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="efb67-284">アクティブな安全なリンクポリシーのユーザーが、サポートされているアプリでブロックされているリンクをクリックすると、[ブロックされた [URL] 警告](#blocked-url-warning) ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="efb67-284">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="efb67-285">「安全なリンク」のグローバル設定で、Url の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="efb67-285">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="efb67-286">手順については、 [「[次の url をブロック](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)する] の一覧を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-286">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="efb67-287">**注** :</span><span class="sxs-lookup"><span data-stu-id="efb67-287">**Notes** :</span></span>

- <span data-ttu-id="efb67-288">すべての場所でブロックされる Url の完全なユニバーサルリストについては、「 [テナントの許可/ブロック」リスト](tenant-allow-block-list.md)の「Url を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-288">For a truly universal list of URLs that are blocked everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="efb67-289">数</span><span class="sxs-lookup"><span data-stu-id="efb67-289">Limits:</span></span>
  - <span data-ttu-id="efb67-290">エントリの最大数は500です。</span><span class="sxs-lookup"><span data-stu-id="efb67-290">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="efb67-291">エントリの最大長は128文字です。</span><span class="sxs-lookup"><span data-stu-id="efb67-291">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="efb67-292">すべてのエントリは、1万文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="efb67-292">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="efb67-293">`/`URL の末尾にスラッシュ () を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="efb67-293">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="efb67-294">たとえば、を使用し `https://www.contoso.com` `https://www.contoso.com/` ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-294">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="efb67-295">ドメインのみの URL (たとえば、など `contoso.com` `tailspintoys.com` ) によって、ドメインを含む url がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-295">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="efb67-296">完全なドメインをブロックせずにサブドメインをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="efb67-296">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="efb67-297">たとえば、は `toys.contoso.com*` サブドメインを含む url をブロックしますが、完全なドメインを含む url はブロックしません `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="efb67-297">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="efb67-298">最大3つのワイルドカード () を URL エントリごとに含めることができ `*` ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-298">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="efb67-299">[次の Url をブロックする] リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="efb67-299">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="efb67-300">次の表に、入力できる値とその結果の例を示します。</span><span class="sxs-lookup"><span data-stu-id="efb67-300">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="efb67-301">値</span><span class="sxs-lookup"><span data-stu-id="efb67-301">Value</span></span>|<span data-ttu-id="efb67-302">結果</span><span class="sxs-lookup"><span data-stu-id="efb67-302">Result</span></span>|
|---|---|
|`contoso.com` <br/> <span data-ttu-id="efb67-303">または</span><span class="sxs-lookup"><span data-stu-id="efb67-303">or</span></span> <br/> `*contoso.com*`|<span data-ttu-id="efb67-304">ドメイン、サブドメイン、およびパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="efb67-304">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="efb67-305">たとえば、、、など `https://www.contoso.com` `https://sub.contoso.com` `https://contoso.com/abc` がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-305">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="efb67-306">ブロックする `https://contoso.com/a` が、のような追加のサブパスは含まれません `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="efb67-306">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="efb67-307">ブロック `https://contoso.com/a` とその他のサブパスなど `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="efb67-307">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="efb67-308">サブドメインをブロック `toys` しますが (この例では)、他のドメインの url (またはなど) へのクリックを許可 `https://contoso.com` `https://home.contoso.com` します。</span><span class="sxs-lookup"><span data-stu-id="efb67-308">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="efb67-309">「安全なリンクポリシー」の「次の Url を書き換えない」の一覧</span><span class="sxs-lookup"><span data-stu-id="efb67-309">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="efb67-310">組織が安全なリンクポリシーを使用している場合は、サードパーティのフィッシングテストでサポートされている唯一の方法は、 **次の url のリストを書き換えることはできません** 。</span><span class="sxs-lookup"><span data-stu-id="efb67-310">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="efb67-311">各「安全なリンク」ポリシーには、安全なリンクのスキャンによって書き換えられていない Url を指定するために使用できる、次の Url リストを **書き換えないでください** 。</span><span class="sxs-lookup"><span data-stu-id="efb67-311">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="efb67-312">つまり、リストでは、ポリシーに含まれているユーザーが、安全なリンクによってブロックされる、指定された Url にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="efb67-312">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="efb67-313">異なる安全なリンクポリシーで、さまざまなリストを構成できます。</span><span class="sxs-lookup"><span data-stu-id="efb67-313">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="efb67-314">最初の (最も優先度の高い) ポリシーがユーザーに適用された後に、ポリシーの処理が停止します。</span><span class="sxs-lookup"><span data-stu-id="efb67-314">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="efb67-315">そのため、1つの [ **次の url を書き換えない** ] リストは、複数のアクティブな安全リンクポリシーに含まれるユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-315">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="efb67-316">新規または既存の安全なリンクポリシーのリストにエントリを追加するには、「 [安全なリンクポリシーを作成](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) する」または「 [安全なリンク](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)のポリシーを変更する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-316">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="efb67-317">**注** :</span><span class="sxs-lookup"><span data-stu-id="efb67-317">**Notes** :</span></span>

- <span data-ttu-id="efb67-318">次のクライアントは、安全なリンクポリシーで、 **次の url の一覧を書き換えないこと** を認識していません。</span><span class="sxs-lookup"><span data-stu-id="efb67-318">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="efb67-319">ポリシーに含まれているユーザーは、これらのクライアントでの安全なリンクのスキャン結果に基づいて、Url へのアクセスをブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="efb67-319">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="efb67-320">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efb67-320">Microsoft Teams</span></span>
  - <span data-ttu-id="efb67-321">Office web apps</span><span class="sxs-lookup"><span data-stu-id="efb67-321">Office web apps</span></span>

  <span data-ttu-id="efb67-322">すべての場所で許可されている Url の完全なユニバーサルリストについては、「 [テナントの許可/禁止リストの url を管理](tenant-allow-block-list.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-322">For a truly universal list of URLs that are allowed everywhere, see [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="efb67-323">一般的に使用される内部 Url をリストに追加して、ユーザーの利便性を高めることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-323">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="efb67-324">たとえば、Skype for Business や SharePoint などのオンプレミスのサービスがある場合は、それらの Url を追加してスキャンから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="efb67-324">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="efb67-325">「安全なリンク」ポリシーで、次の Url エントリをすでに **書き直してい** ない場合は、必ず、リストを確認し、必要に応じてワイルドカードを追加してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-325">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="efb67-326">たとえば、リストにそのようなエントリがあり、 `https://contoso.com/a` 後で、のようなサブパスを含めるように決定したとし `https://contoso.com/a/b` ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-326">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="efb67-327">新しいエントリを追加するのではなく、既存のエントリにワイルドカードを追加して、になり `https://contoso.com/a/*` ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-327">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="efb67-328">最大3つのワイルドカード () を URL エントリごとに含めることができ `*` ます。</span><span class="sxs-lookup"><span data-stu-id="efb67-328">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="efb67-329">ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="efb67-329">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="efb67-330">たとえば、エントリ `contoso.com` はと同じではありません `*.contoso.com/*` 。これに `*.contoso.com/*` より、ユーザーは指定したドメインのサブドメインとパスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="efb67-330">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="efb67-331">[次の Url を書き換えない] の一覧のエントリの構文</span><span class="sxs-lookup"><span data-stu-id="efb67-331">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="efb67-332">次の表に、入力できる値とその結果の例を示します。</span><span class="sxs-lookup"><span data-stu-id="efb67-332">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="efb67-333">値</span><span class="sxs-lookup"><span data-stu-id="efb67-333">Value</span></span>|<span data-ttu-id="efb67-334">結果</span><span class="sxs-lookup"><span data-stu-id="efb67-334">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="efb67-335">サブドメインまたはパスへのアクセスを許可 `https://contoso.com` しません。</span><span class="sxs-lookup"><span data-stu-id="efb67-335">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="efb67-336">ドメイン、サブドメイン、パスへのアクセスを許可します (たとえば、、、、など `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` `https://www.contoso.com/a` )。</span><span class="sxs-lookup"><span data-stu-id="efb67-336">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <br/><br/> <span data-ttu-id="efb67-337">このエントリは、次の `*contoso.com*` ように、偽装している可能性のあるサイトを許可しないため、またはのようになります。 `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="efb67-337">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="efb67-338">にはアクセスでき `https://contoso.com/a` ますが、次のようなサブパスは使用できません。 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="efb67-338">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="efb67-339">次のようなサブパスへのアクセスを許可します。 `https://contoso.com/a``https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="efb67-339">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="efb67-340">安全なリンクからの警告ページ</span><span class="sxs-lookup"><span data-stu-id="efb67-340">Warning pages from Safe Links</span></span>

<span data-ttu-id="efb67-341">このセクションには、URL をクリックしたときに安全なリンク保護によってトリガーされるさまざまな警告ページの例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="efb67-341">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="efb67-342">いくつかの警告ページが更新されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="efb67-342">Note that several warning pages have been updated.</span></span> <span data-ttu-id="efb67-343">更新されたページがまだ表示されていない場合は、間もなく表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb67-343">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="efb67-344">更新されたページには、新しい配色、詳細、および指定された警告と推奨事項にかかわらずサイトに進む機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="efb67-344">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="efb67-345">スキャンの進行状況の通知</span><span class="sxs-lookup"><span data-stu-id="efb67-345">Scan in progress notification</span></span>

<span data-ttu-id="efb67-346">クリックした URL は、安全なリンクによってスキャンされています。</span><span class="sxs-lookup"><span data-stu-id="efb67-346">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="efb67-347">リンクをもう一度試す前に、しばらく待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="efb67-347">You might need to wait a few moments before trying the link again.</span></span>

!["リンクがスキャンされています" という通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="efb67-349">元の通知ページは次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-349">The original notification page looked like this:</span></span>

![元の "リンクがスキャンされています" という通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="efb67-351">疑わしいメッセージの警告</span><span class="sxs-lookup"><span data-stu-id="efb67-351">Suspicious message warning</span></span>

<span data-ttu-id="efb67-352">クリックされた URL は、他の疑わしいメッセージに似た電子メールメッセージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="efb67-352">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="efb67-353">サイトに進む前に、電子メールメッセージをもう一度確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efb67-353">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["疑わしいメッセージからリンクがクリックされました" という警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="efb67-355">フィッシングの試行に関する警告</span><span class="sxs-lookup"><span data-stu-id="efb67-355">Phishing attempt warning</span></span>

<span data-ttu-id="efb67-356">クリックされた URL は、フィッシング攻撃として識別された電子メールメッセージに含まれています。</span><span class="sxs-lookup"><span data-stu-id="efb67-356">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="efb67-357">その結果、電子メールメッセージ内のすべての Url がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="efb67-357">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="efb67-358">サイトに進まないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efb67-358">We recommend that you do not proceed to the site.</span></span>

!["リンクは、フィッシングメッセージからクリックされました" という警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="efb67-360">悪意のある web サイトの警告</span><span class="sxs-lookup"><span data-stu-id="efb67-360">Malicious website warning</span></span>

<span data-ttu-id="efb67-361">クリックされた URL は、悪意があると識別されたサイトを指しています。</span><span class="sxs-lookup"><span data-stu-id="efb67-361">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="efb67-362">サイトに進まないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efb67-362">We recommend that you do not proceed to the site.</span></span>

!["この web サイトは悪意のあるものとして分類されています" という警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="efb67-364">元の警告ページは次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-364">The original warning page looked like this:</span></span>

![元の "この web サイトは、悪意のあるものとして分類されています" という警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="efb67-366">ブロックされた URL の警告</span><span class="sxs-lookup"><span data-stu-id="efb67-366">Blocked URL warning</span></span>

<span data-ttu-id="efb67-367">クリックした URL は、組織内の管理者によって手動でブロックされています (「安全なリンクのためのグローバル設定」の「 **次の url をブロック** する」の一覧)。</span><span class="sxs-lookup"><span data-stu-id="efb67-367">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="efb67-368">このリンクは手動でブロックされていたため、安全なリンクによってスキャンされませんでした。</span><span class="sxs-lookup"><span data-stu-id="efb67-368">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="efb67-369">管理者が特定の Url を手動でブロックする理由はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="efb67-369">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="efb67-370">サイトがブロックされないようにする場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="efb67-370">If you think the site should not be blocked, contact your admin.</span></span>

!["この web サイトは管理者によってブロックされました" という警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="efb67-372">元の警告ページは次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-372">The original warning page looked like this:</span></span>

![元の "この web サイトは、組織の URL ポリシーに従ってブロックされています" という警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="efb67-374">エラー警告</span><span class="sxs-lookup"><span data-stu-id="efb67-374">Error warning</span></span>

<span data-ttu-id="efb67-375">何らかのエラーが発生し、URL を開くことができません。</span><span class="sxs-lookup"><span data-stu-id="efb67-375">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["アクセスしようとしているページは読み込めません" という警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="efb67-377">元の警告ページは次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="efb67-377">The original warning page looked like this:</span></span>

![元の "この web ページは読み込めませんでした" という警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
