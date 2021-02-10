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
description: この記事では、管理者は、フィッシングや悪意のある URL を使用するその他の攻撃から組織を保護するために、Office 365 の Defender の安全なリンク保護について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 251b3e71be30f90ac828abc8bf34877d65615336
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175777"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="919f0-103">Microsoft Defender for Office 365 の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="919f0-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="919f0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="919f0-104">**Applies to**</span></span>
- [<span data-ttu-id="919f0-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="919f0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="919f0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="919f0-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="919f0-107">この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="919f0-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="919f0-108">Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用している場合、Outlook のセーフリンクに関する情報を探している場合は [、「Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="919f0-109">「安全なリンク」は [、Defender for Office 365](office-365-atp.md) の機能で、メール フロー内の受信メール メッセージの URL のスキャンと書き換え、および電子メール メッセージや他の場所での URL とリンクのクリック時の検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="919f0-109">Safe Links is a feature in [Defender for Office 365](office-365-atp.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="919f0-110">安全なリンクのスキャンは、Exchange Online [](anti-spam-and-anti-malware-protection.md) Protection (EOP) の受信電子メール メッセージの通常のスパム対策およびマルウェア対策保護に加えて行われます。</span><span class="sxs-lookup"><span data-stu-id="919f0-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="919f0-111">安全なリンクのスキャンは、フィッシングなどの攻撃で使用される悪意のあるリンクから組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="919f0-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="919f0-112">安全なリンク保護は、次の場所で利用できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="919f0-113">**電子メール メッセージ**: 電子メール メッセージ内のリンクに対する安全なリンク保護は、安全なリンク ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="919f0-114">既定の安全なリンクポリシーはないので、電子メール メッセージ内の安全なリンクの保護を取得するには、1 つ以上の安全なリンク ポリシーを作成 **する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="919f0-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="919f0-115">手順については、「Microsoft Defender で安全なリンク ポリシーをセットアップする [(Office 365)」を参照](set-up-atp-safe-links-policies.md)してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

  <span data-ttu-id="919f0-116">電子メール メッセージの安全なリンク保護の詳細については、[](#safe-links-settings-for-email-messages)この記事の後半の「電子メール メッセージの安全なリンクの設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="919f0-117">**Microsoft Teams** (現在 TAP プレビュー): Teams の会話、グループ チャット、またはチャネルからのリンクに対する安全なリンク保護も、安全なリンク ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-117">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="919f0-118">既定の安全なリンクポリシーはないので、Teams の安全なリンクの保護を取得するには、1 つ以上の安全なリンク ポリシーを作成 **する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="919f0-118">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="919f0-119">Teams での安全なリンク保護の詳細については、この記事の後半にある [「Microsoft Teams](#safe-links-settings-for-microsoft-teams) の安全なリンク設定」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-119">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="919f0-120">**Office 365 アプリ**: Office 365 アプリの安全なリンク保護は、サポートされているデスクトップ、モバイル、および Web AP で利用できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-120">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="919f0-121">365 アプリの安全Office保護は、安全なリンク ポリシーの外部にあるグローバル設定で構成します。 </span><span class="sxs-lookup"><span data-stu-id="919f0-121">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="919f0-122">手順については [、「Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)での安全なリンク設定のグローバル設定を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-122">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="919f0-123">ただし、Office 365 アプリの安全なリンク保護は、アクティブな安全なリンク ポリシーに含まれているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-123">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="919f0-124">ユーザーがアクティブな安全なリンク ポリシーに含まれていない場合、ユーザーはサポートされている 365 アプリで安全なリンクOfficeされません。</span><span class="sxs-lookup"><span data-stu-id="919f0-124">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="919f0-125">Office 365 アプリの安全なリンク保護の詳細については、この記事の後半にある [「Office 365](#safe-links-settings-for-office-365-apps) アプリの安全なリンク設定」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="919f0-126">この記事では、次の種類の安全なリンク設定について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="919f0-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="919f0-127">**安全なリンク** ポリシーの設定 : これらの設定は、特定のポリシーに含まれるユーザーにのみ適用され、ポリシーによって設定が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="919f0-128">これらの設定には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="919f0-128">These settings include:</span></span>

  - [<span data-ttu-id="919f0-129">電子メール メッセージの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="919f0-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="919f0-130">Microsoft Teams の安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="919f0-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="919f0-131">「安全なリンク」ポリシーの「次の URL を書き換えない」</span><span class="sxs-lookup"><span data-stu-id="919f0-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="919f0-132">**グローバル な安全なリンク** の設定 : これらの設定は、安全なリンク ポリシーではなくグローバルに構成されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="919f0-133">ただし、この設定は、アクティブな安全なリンク ポリシーに含まれているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-133">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="919f0-134">これらの設定には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="919f0-134">These settings include:</span></span>

  - [<span data-ttu-id="919f0-135">365 アプリの安全Office設定</span><span class="sxs-lookup"><span data-stu-id="919f0-135">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="919f0-136">「安全なリンク」の「次の URL をブロックする」の一覧</span><span class="sxs-lookup"><span data-stu-id="919f0-136">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="919f0-137">次の表では、Defender for Office 365 を含む Microsoft 365 および Office 365 組織の安全なリンクのシナリオについて説明します (つまり、例ではライセンスの不足は決して問題ではありません)。</span><span class="sxs-lookup"><span data-stu-id="919f0-137">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="919f0-138">シナリオ</span><span class="sxs-lookup"><span data-stu-id="919f0-138">Scenario</span></span>|<span data-ttu-id="919f0-139">結果</span><span class="sxs-lookup"><span data-stu-id="919f0-139">Result</span></span>|
|---|---|
|<span data-ttu-id="919f0-140">マーケティング部門のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="919f0-140">Jean is a member of the marketing department.</span></span> <span data-ttu-id="919f0-141">Office 365 アプリの安全なリンク保護は、安全なリンクのグローバル設定で有効にされ、マーケティング部門のメンバーに適用される安全なリンク ポリシーが存在します。</span><span class="sxs-lookup"><span data-stu-id="919f0-141">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="919f0-142">電子メール メッセージで PowerPoint プレゼンテーションを開き、プレゼンテーションの URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-142">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="919f0-143">安全なリンクによって保護されています。</span><span class="sxs-lookup"><span data-stu-id="919f0-143">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="919f0-144">「安全なリンク」ポリシーには「安全なリンク」ポリシーが含まれており、365 Officeの安全なリンク保護が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="919f0-144">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="919f0-145">Office 365 アプリの安全なリンク保護の要件の詳細については、この記事の後半にある [「Office 365](#safe-links-settings-for-office-365-apps) アプリの安全なリンク設定」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-145">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="919f0-146">Chris の Microsoft 365 E5 組織には、安全なリンクポリシーが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="919f0-146">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="919f0-147">Chris は、最終的にクリックする悪意のある Web サイトへの URL を含むメールを外部送信者から受信します。</span><span class="sxs-lookup"><span data-stu-id="919f0-147">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="919f0-148">Chris は安全なリンクによって保護されません。</span><span class="sxs-lookup"><span data-stu-id="919f0-148">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="919f0-149">管理者は、受信電子メール メッセージで安全なリンク保護を取得するために、すべてのユーザーに対して少なくとも 1 つの安全なリンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-149">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="919f0-150">Chris は、安全なリンク保護を得るポリシーの条件に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-150">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="919f0-151">Pat の組織では、管理者は安全なリンク ポリシーを作成していなが、Office 365 アプリの安全なリンク保護が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="919f0-151">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="919f0-152">Pat は Word 文書を開き、ファイル内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-152">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="919f0-153">Pat は安全なリンクによって保護されません。</span><span class="sxs-lookup"><span data-stu-id="919f0-153">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="919f0-154">Office 365 アプリの安全なリンク保護はグローバルに有効になりますが、Pat はアクティブな安全なリンク ポリシーに含まれていないので、保護は適用されません。</span><span class="sxs-lookup"><span data-stu-id="919f0-154">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="919f0-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span><span class="sxs-lookup"><span data-stu-id="919f0-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="919f0-156">Lee を含む安全なリンク ポリシーは既に存在します。</span><span class="sxs-lookup"><span data-stu-id="919f0-156">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="919f0-157">Lee は URL を含む電子メール メッセージを受信します `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-157">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="919f0-158">Lee が URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-158">Lee clicks the URL.</span></span>|<span data-ttu-id="919f0-159">Url は自動的に Lee に対してブロックされる場合があります。リスト内の URL エントリと、使用される電子メール クライアントの Lee によって異なります。</span><span class="sxs-lookup"><span data-stu-id="919f0-159">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="919f0-160">詳細については、この記事の後半にある「安全なリンク [」](#block-the-following-urls-list-for-safe-links) の「次の URL をブロックする」の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-160">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="919f0-161">Jamie と Julia は、どちらも contoso.com。</span><span class="sxs-lookup"><span data-stu-id="919f0-161">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="919f0-162">長い間、管理者は Jamie と Julia の両方に適用される安全なリンク ポリシーを構成していました。</span><span class="sxs-lookup"><span data-stu-id="919f0-162">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="919f0-163">Jamie は、電子メールに悪意のある URL が含まれているのを知らずに、Julia にメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="919f0-163">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="919f0-164">Julia は、彼女に適用される安全なリンク ポリシーが内部受信者間のメッセージに適用するように構成されている場合、安全なリンクによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-164">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="919f0-165">詳細については、この記事の後半にある「電子メール メッセージの [安全なリンク](#safe-links-settings-for-email-messages) 設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-165">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="919f0-166">電子メール メッセージの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="919f0-166">Safe Links settings for email messages</span></span>

<span data-ttu-id="919f0-167">「安全なリンク」は、受信メールをスキャンして既知の悪意のあるハイパーリンクを検出します。</span><span class="sxs-lookup"><span data-stu-id="919f0-167">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="919f0-168">スキャンされた URL は、Microsoft 標準 URL プレフィックスを使用して書き換えされます `https://nam01.safelinks.protection.outlook.com` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-168">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="919f0-169">リンクの書き換え後、悪意のある可能性のあるコンテンツが分析されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-169">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="919f0-170">安全なリンクが URL を書き換えた後、メッセージが転送または返信された場合でも、URL は書き換えたままです。</span><span class="sxs-lookup"><span data-stu-id="919f0-170">After Safe Links rewrites a URL, the URL remains rewritten, even if the message is forwarded or replied to.</span></span> <span data-ttu-id="919f0-171">転送またはメッセージに返信される追加のリンクは書き換えされません。</span><span class="sxs-lookup"><span data-stu-id="919f0-171">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span>

<span data-ttu-id="919f0-172">電子メール メッセージに適用される安全なリンク ポリシーの設定について、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="919f0-172">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="919f0-173">**メッセージ内の悪意のある可能性** のある不明な URL に対するアクションを選択します。電子メール メッセージの安全なリンクのスキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="919f0-173">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="919f0-174">推奨される値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="919f0-174">The recommended value is **On**.</span></span> <span data-ttu-id="919f0-175">この設定を有効にすると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-175">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="919f0-176">安全なリンクのスキャンは、Windows の Outlook (C2R) で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="919f0-176">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="919f0-177">URL が書き換えされ、メッセージ内の URL をクリックすると、ユーザーは安全なリンク保護によってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="919f0-177">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="919f0-178">クリックすると、既知の悪意のある URL の一覧と "次の URL をブロックする" リストに対して [URL がチェックされます](#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="919f0-178">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="919f0-179">有効な評価を持たなかった URL は、バックグラウンドで非同期的にデトニトされます。</span><span class="sxs-lookup"><span data-stu-id="919f0-179">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="919f0-180">**疑わしいリンク** やファイルを指すリンクに対してリアルタイム URL スキャンを適用します。ダウンロード可能なコンテンツを指す電子メール メッセージ内のリンクなど、リンクをリアルタイムでスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-180">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="919f0-181">推奨値は有効です。</span><span class="sxs-lookup"><span data-stu-id="919f0-181">The recommended value is enabled.</span></span>

  - <span data-ttu-id="919f0-182">**メッセージを配信する前に URL のスキャンが完了するのを待ちます**。</span><span class="sxs-lookup"><span data-stu-id="919f0-182">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="919f0-183">有効: URL を含むメッセージは、スキャンが完了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-183">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="919f0-184">メッセージは、URL が安全だと確認された後にのみ配信されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-184">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="919f0-185">これは推奨値です。</span><span class="sxs-lookup"><span data-stu-id="919f0-185">This is the recommended value.</span></span>
    - <span data-ttu-id="919f0-186">無効: URL のスキャンを完了できない場合は、メッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="919f0-186">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="919f0-187">**組織内で** 送信される電子メール メッセージに安全なリンクを適用する : 内部送信者と同じ Exchange Online 組織内の内部受信者の間で送信されるメッセージに対する安全なリンクのスキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="919f0-187">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="919f0-188">推奨値は有効です。</span><span class="sxs-lookup"><span data-stu-id="919f0-188">The recommended value is enabled.</span></span>

- <span data-ttu-id="919f0-189">**ユーザーのクリックを** 追跡しない : 電子メール メッセージでクリックされた URL の安全なリンク のクリック データの保存を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="919f0-189">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="919f0-190">推奨値は、この設定を未選択のままにする (ユーザーのクリックを追跡する) 方法です。</span><span class="sxs-lookup"><span data-stu-id="919f0-190">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="919f0-191">内部送信者と内部受信者の間で送信される電子メール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="919f0-191">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="919f0-192">**ユーザーがクリックして元** の URL に移動できない: ユーザーが警告ページをクリックして元の URL [を](#warning-pages-from-safe-links) クリックできないかブロックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-192">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="919f0-193">推奨値は有効です。</span><span class="sxs-lookup"><span data-stu-id="919f0-193">The recommend value is enabled.</span></span>

- <span data-ttu-id="919f0-194">**次の URL は書き換え** ない : URL は変更しない。</span><span class="sxs-lookup"><span data-stu-id="919f0-194">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="919f0-195">スキャンを必要としない安全な URL のカスタム リストを保持します。</span><span class="sxs-lookup"><span data-stu-id="919f0-195">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="919f0-196">リストは、安全なリンク ポリシーごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="919f0-196">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="919f0-197">[次の URLを書き換えない] の一覧[](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)の詳細については、この記事の後半にある「安全なリンク ポリシー」の「次の URL を書き換えない」の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-197">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="919f0-198">安全なリンク ポリシーの標準および厳密なポリシー設定の推奨値の詳細については、「安全なリンクのポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="919f0-198">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="919f0-199">**受信者フィルター**: ポリシーを適用するユーザーを決定する受信者の条件と例外を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-199">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="919f0-200">条件や例外には次のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-200">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="919f0-201">**受信者が次の場合**</span><span class="sxs-lookup"><span data-stu-id="919f0-201">**The recipient is**</span></span>
  - <span data-ttu-id="919f0-202">**受信者のドメインが次の場合**</span><span class="sxs-lookup"><span data-stu-id="919f0-202">**The recipient domain is**</span></span>
  - <span data-ttu-id="919f0-203">**受信者が次のメンバーの場合**</span><span class="sxs-lookup"><span data-stu-id="919f0-203">**The recipient is a member of**</span></span>

  <span data-ttu-id="919f0-204">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="919f0-204">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="919f0-205">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-205">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="919f0-206">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-206">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="919f0-207">**優先度**: 複数のポリシーを作成する場合は、適用する順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-207">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="919f0-208">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="919f0-208">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="919f0-209">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-209">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="919f0-210">電子メール メッセージでの安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="919f0-210">How Safe Links works in email messages</span></span>

<span data-ttu-id="919f0-211">電子メール メッセージの URL で安全なリンク保護がどのように機能するのか、大まかには次のように説明します。</span><span class="sxs-lookup"><span data-stu-id="919f0-211">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="919f0-212">すべての電子メールは EOP を経由します。EOP では、メッセージが受信者のメールボックスに配信される前に、インターネット プロトコル (IP) およびエンベロープ フィルター、署名ベースのマルウェア保護、スパム対策およびマルウェア対策フィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-212">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="919f0-213">ユーザーは自分のメールボックスでメッセージを開き、メッセージ内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-213">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="919f0-214">安全なリンクは、Web サイトを開く前に URL をすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="919f0-214">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="919f0-215">URL が [次の URL **をブロックする** ] ボックスの一覧に含まれている場合は、ブロックされた [URL の警告が表示](#blocked-url-warning) されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-215">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="919f0-216">URL が悪意のあると判断された Web サイトをポイントすると、[](#malicious-website-warning)悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="919f0-216">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="919f0-217">URL がダウンロード可能なファイルを指し示し、ユーザーに適用されるポリシーで [疑わしいリンクとファイルを指すリンクのリアルタイム **URL** スキャンの適用] 設定が有効になっている場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="919f0-217">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="919f0-218">URL が安全だと判断された場合は、Web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="919f0-218">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="919f0-219">Microsoft Teams の安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="919f0-219">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="919f0-220">2020 年 3 月現在、この機能はプレビュー中であり、Microsoft Teams テクノロジ導入プログラム (TAP) のメンバーだけが利用できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-220">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="919f0-221">リリース スケジュールの詳細については [、Microsoft 365 ロードマップを参照してください](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="919f0-221">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="919f0-222">Microsoft Teams の安全なリンク保護は、安全なリンク ポリシーで有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="919f0-222">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="919f0-223">具体的には、[Microsoft Teams 内の不明な URL または悪意のある可能性のある URL に対してアクションを選択する **] 設定を使用** します。</span><span class="sxs-lookup"><span data-stu-id="919f0-223">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="919f0-224">推奨される値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="919f0-224">The recommended value is **On**.</span></span>

<span data-ttu-id="919f0-225">メール メッセージ内のリンクに適用される安全なリンク ポリシーの次の設定は、Teams のリンクにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-225">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="919f0-226">**ファイルを指す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する**</span><span class="sxs-lookup"><span data-stu-id="919f0-226">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="919f0-227">**ユーザーのクリックを追跡しない**</span><span class="sxs-lookup"><span data-stu-id="919f0-227">**Do not track user clicks**</span></span>
- <span data-ttu-id="919f0-228">**ユーザーがクリックして元の URL にアクセスできない**</span><span class="sxs-lookup"><span data-stu-id="919f0-228">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="919f0-229">これらの設定については、前の「電子メール メッセージの [安全なリンク設定」セクションで説明](#safe-links-settings-for-email-messages) されています。</span><span class="sxs-lookup"><span data-stu-id="919f0-229">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="919f0-230">Microsoft Teams の安全なリンク保護を有効にすると、保護されたユーザーがリンクをクリックすると、Teams の URL が既知の悪意のあるリンクの一覧に対してチェックされます (クリック時の保護)。</span><span class="sxs-lookup"><span data-stu-id="919f0-230">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="919f0-231">URL は書き換えではありません。</span><span class="sxs-lookup"><span data-stu-id="919f0-231">URLs are not rewritten.</span></span> <span data-ttu-id="919f0-232">悪意のあるリンクが見つかった場合、ユーザーは次のエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-232">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="919f0-233">Teams の会話、グループ チャット、またはチャネルからリンクがクリックされた場合、次のスクリーンショットに示すように警告ページが既定の Web ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-233">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="919f0-234">固定されたタブからリンクがクリックされた場合、そのタブ内の Teams インターフェイスに警告ページが表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由から無効になっています。</span><span class="sxs-lookup"><span data-stu-id="919f0-234">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="919f0-235">ポリシーの [ユーザーがクリックして元の URL に戻せない] 設定の構成方法に応じて、ユーザーはクリックして元の **URL** に進むか許可されません (スクリーンショットでは続行 **します (** 推奨されません)。</span><span class="sxs-lookup"><span data-stu-id="919f0-235">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="919f0-236">ユーザーがクリックして元の URL にアクセスすることを許可しない設定を有効にし、ユーザーがクリックして元の **URL** にアクセスすることを許可することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="919f0-236">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="919f0-237">リンクを送信したユーザーが、Teams の保護が有効になっている安全なリンク ポリシーに含まれていない場合、ユーザーは自分のコンピューターまたはデバイス上の元の URL まで自由にクリックスルーできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-237">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![悪意のあるリンクを報告する Teams の安全なリンク ページ。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="919f0-239">警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。</span><span class="sxs-lookup"><span data-stu-id="919f0-239">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="919f0-240">ただし、元のリンクを再度クリックすると、安全なリンクによって URL が再スキャンされます。そのため、警告ページが再表示されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-240">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="919f0-241">Teams での安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="919f0-241">How Safe Links works in Teams</span></span>

<span data-ttu-id="919f0-242">Microsoft Teams の URL に対する安全なリンク保護のしくみを大まかに次に示します。</span><span class="sxs-lookup"><span data-stu-id="919f0-242">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="919f0-243">ユーザーが Teams アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="919f0-243">A user starts the Teams app.</span></span>

2. <span data-ttu-id="919f0-244">Microsoft 365 は、ユーザーの組織に Office 365 用 Microsoft Defender が含まれており、Microsoft Teams の保護が有効になっているアクティブな安全なリンク ポリシーにユーザーが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="919f0-244">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="919f0-245">URL は、ユーザーがチャット、グループ チャット、チャネル、タブをクリックした時点で検証されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-245">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="919f0-246">365 アプリの安全Office設定</span><span class="sxs-lookup"><span data-stu-id="919f0-246">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="919f0-247">Office 365 アプリの安全なリンク保護は、電子メール メッセージ内のリンクではなく、Office ドキュメント内のリンクをチェックします (ただし、ドキュメントを開いた後、電子メール メッセージ内の添付された Office ドキュメント内のリンクをチェックできます)。</span><span class="sxs-lookup"><span data-stu-id="919f0-247">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="919f0-248">Office 365 アプリの安全なリンク保護には、次のクライアント要件があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-248">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="919f0-249">Microsoft 365 Apps または Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="919f0-249">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="919f0-250">Windows、Mac、または Web ブラウザーの Word、Excel、PowerPoint の現在のバージョン。</span><span class="sxs-lookup"><span data-stu-id="919f0-250">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="919f0-251">Office iOS または Android デバイス上のアプリをサポートします。</span><span class="sxs-lookup"><span data-stu-id="919f0-251">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="919f0-252">Windows 上の Visio。</span><span class="sxs-lookup"><span data-stu-id="919f0-252">Visio on Windows.</span></span>
  - <span data-ttu-id="919f0-253">Web ブラウザーの OneNote。</span><span class="sxs-lookup"><span data-stu-id="919f0-253">OneNote in a web browser.</span></span>

- <span data-ttu-id="919f0-254">Office 365 アプリは、最新の認証を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="919f0-254">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="919f0-255">詳細については、「Office 2013、Office [2016、および Office 2019](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)クライアント アプリでのOffice方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-255">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span>

- <span data-ttu-id="919f0-256">ユーザーは、自分の仕事用アカウントまたは学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="919f0-256">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="919f0-257">詳細については、「サインインしてサインイン[する」をOffice。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)</span><span class="sxs-lookup"><span data-stu-id="919f0-257">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="919f0-258">365 アプリの安全Office保護は、安全なリンク ポリシーではなく、安全なリンクのグローバル設定で構成します。</span><span class="sxs-lookup"><span data-stu-id="919f0-258">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="919f0-259">ただし、Office 365 アプリの安全なリンク保護を適用するには、Office ドキュメントを開いてリンクをクリックするユーザーをアクティブな安全なリンク ポリシーに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-259">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="919f0-260">365 アプリでは、次の安全Office設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-260">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="919f0-261">**Office 365** アプリケーション: サポートされている 365 アプリで安全なリンクOffice有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="919f0-261">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="919f0-262">既定値と推奨値はオン **です**。</span><span class="sxs-lookup"><span data-stu-id="919f0-262">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="919f0-263">**[** 安全なリンク] をクリックしても追跡しない : デスクトップ バージョンの Word、Excel、PowerPoint、および Visio でクリックされた URL の安全なリンク のクリック データの保存を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="919f0-263">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="919f0-264">推奨値は **[オフ]** です。つまり、ユーザーのクリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-264">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="919f0-265">**元** の URL への安全なリンクをユーザーがクリックで許可しない : ユーザーが [](#warning-pages-from-safe-links)警告ページをクリックして、デスクトップ バージョンの Word、Excel、PowerPoint、および Visio の元の URL に移動したりブロックしたりします。</span><span class="sxs-lookup"><span data-stu-id="919f0-265">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="919f0-266">既定値と推奨値はオン **です**。</span><span class="sxs-lookup"><span data-stu-id="919f0-266">The default and recommended value is **On**.</span></span>

<span data-ttu-id="919f0-267">Office 365 アプリの安全なリンクの設定を構成するには、「Office [365](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)アプリの安全なリンク保護を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-267">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="919f0-268">Standard および Strict ポリシー設定の推奨値の詳細については、「安全なリンクのグローバル設定」を [参照してください](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="919f0-268">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="919f0-269">Office 365 アプリでの安全なリンクのしくみ</span><span class="sxs-lookup"><span data-stu-id="919f0-269">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="919f0-270">大まかには、365 アプリの URL に対する安全なリンク保護Office示します。</span><span class="sxs-lookup"><span data-stu-id="919f0-270">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="919f0-271">サポートされている 365 Officeについては、前のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="919f0-271">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="919f0-272">ユーザーは、Microsoft 365 Apps または Microsoft 365 Business Premium を含む組織内の自分の仕事用アカウントまたは学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="919f0-272">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="919f0-273">ユーザーは、サポートされているアプリでドキュメントのリンクOffice開いてクリックOfficeします。</span><span class="sxs-lookup"><span data-stu-id="919f0-273">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="919f0-274">安全なリンクは、対象の Web サイトを開く前に URL をすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="919f0-274">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="919f0-275">安全なリンクのスキャンをスキップする URL がリストに含まれている場合([次の URL をブロックする] ボックスの一覧)、ブロックされた URL の警告ページ[が](#blocked-url-warning)開きます。</span><span class="sxs-lookup"><span data-stu-id="919f0-275">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="919f0-276">URL が悪意のあると判断された Web サイトをポイントすると、[](#malicious-website-warning)悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="919f0-276">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="919f0-277">URL がダウンロード可能なファイルを指し示し、ユーザーに適用される安全なリンク ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (疑わしいリンクやファイルを指すリンクをリアルタイムで **URL** スキャンを適用する)、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="919f0-277">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="919f0-278">URL が安全であると見なされた場合、ユーザーは Web サイトにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="919f0-278">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="919f0-279">安全なリンクのスキャンを完了できない場合、安全なリンクの保護はトリガーできません。</span><span class="sxs-lookup"><span data-stu-id="919f0-279">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="919f0-280">デスクトップ Officeでは、ユーザーは移動先の Web サイトに進む前に警告を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-280">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="919f0-281">各セッションの開始時に、ユーザーが安全なリンクを有効にOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="919f0-281">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="919f0-282">「安全なリンク」の「次の URL をブロックする」の一覧</span><span class="sxs-lookup"><span data-stu-id="919f0-282">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="919f0-283">[ **次の URL をブロック** する] ボックスの一覧では、次の場所にある安全なリンクのスキャンによって常にブロックされるリンクを定義します。</span><span class="sxs-lookup"><span data-stu-id="919f0-283">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="919f0-284">電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="919f0-284">Email messages.</span></span>
- <span data-ttu-id="919f0-285">Windows と Mac Office 365 アプリのドキュメント。</span><span class="sxs-lookup"><span data-stu-id="919f0-285">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="919f0-286">iOS および Android Officeのドキュメント。</span><span class="sxs-lookup"><span data-stu-id="919f0-286">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="919f0-287">アクティブな安全なリンク ポリシーのユーザーが、サポートされているアプリでブロックされたリンクをクリックすると、[ブロックする URL] 警告ページ [に移動](#blocked-url-warning) します。</span><span class="sxs-lookup"><span data-stu-id="919f0-287">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="919f0-288">安全なリンクのグローバル設定で URL の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="919f0-288">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="919f0-289">手順については、「次の URL [をブロックする」の一覧を構成するを参照してください](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="919f0-289">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="919f0-290">**注**:</span><span class="sxs-lookup"><span data-stu-id="919f0-290">**Notes**:</span></span>

- <span data-ttu-id="919f0-291">すべての場所でブロックされている URL の本当に汎用的なリストについては、「テナントの許可/ブロックリストの管理 [」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="919f0-291">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="919f0-292">制限:</span><span class="sxs-lookup"><span data-stu-id="919f0-292">Limits:</span></span>
  - <span data-ttu-id="919f0-293">エントリの最大数は 500 です。</span><span class="sxs-lookup"><span data-stu-id="919f0-293">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="919f0-294">エントリの最大長は 128 文字です。</span><span class="sxs-lookup"><span data-stu-id="919f0-294">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="919f0-295">すべてのエントリが 10,000 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="919f0-295">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="919f0-296">URL の末尾にスラッシュ ( `/` ) を含めない。</span><span class="sxs-lookup"><span data-stu-id="919f0-296">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="919f0-297">たとえば、使用します。 `https://www.contoso.com` 使用することはできません `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-297">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="919f0-298">ドメイン専用 URL (たとえば、または) は、ドメインを含む `contoso.com` `tailspintoys.com` URL をブロックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-298">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="919f0-299">完全なドメインをブロックすることなく、サブドメインをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-299">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="919f0-300">たとえば、サブドメインを含むすべての URL をブロックしますが、完全なドメインを含む `toys.contoso.com*` URL はブロックします `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-300">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="919f0-301">URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-301">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="919f0-302">[次の URL をブロックする] リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="919f0-302">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="919f0-303">入力できる値とその結果の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="919f0-303">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="919f0-304">値</span><span class="sxs-lookup"><span data-stu-id="919f0-304">Value</span></span>|<span data-ttu-id="919f0-305">結果</span><span class="sxs-lookup"><span data-stu-id="919f0-305">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="919f0-306">または</span><span class="sxs-lookup"><span data-stu-id="919f0-306">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="919f0-307">ドメイン、サブドメイン、およびパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="919f0-307">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="919f0-308">たとえば、ブロック `https://www.contoso.com` `https://sub.contoso.com` `https://contoso.com/abc` されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-308">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="919f0-309">ブロック `https://contoso.com/a` しますが、次のような追加のサブパスはブロックしない `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-309">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="919f0-310">ブロック `https://contoso.com/a` および追加のサブパス 。 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="919f0-310">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="919f0-311">サブドメイン (この例では) をブロックしますが、他のドメイン URL (たとえば) へのクリック `toys` を `https://contoso.com` 許可します `https://home.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-311">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="919f0-312">「安全なリンク」ポリシーの「次の URL を書き換えない」</span><span class="sxs-lookup"><span data-stu-id="919f0-312">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="919f0-313">組織で安全なリンク ポリシーを使用している場合、サード パーティ製のフィッシング テストでサポートされている唯一の方法は、次の **URL** リストを書き換えない方法です。</span><span class="sxs-lookup"><span data-stu-id="919f0-313">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="919f0-314">各安全なリンク ポリシーには、安全なリンクのスキャンによって書き換えされない URL を指定するために使用できる次の URL リストを書き換えないリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="919f0-314">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="919f0-315">つまり、ポリシーに含まれるユーザーは、安全なリンクによってブロックされる指定された URL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-315">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="919f0-316">安全なリンク ポリシーごとに異なるリストを構成できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-316">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="919f0-317">ポリシー処理は、最初の (最も高い優先度の) ポリシーがユーザーに適用された後に停止します。</span><span class="sxs-lookup"><span data-stu-id="919f0-317">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="919f0-318">したがって、次の URL **リストを** 書き換えないのは 1 つのみ、複数のアクティブな安全なリンク ポリシーに含まれるユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-318">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="919f0-319">新規または既存の安全なリンク ポリシーの一覧にエントリを追加するには、「[](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies)安全なリンク ポリシーを作成する」または「安全なリンク のポリシーを変更する[」を参照してください](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="919f0-319">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="919f0-320">**注**:</span><span class="sxs-lookup"><span data-stu-id="919f0-320">**Notes**:</span></span>

- <span data-ttu-id="919f0-321">次のクライアントは、安全なリンク ポリシー内の次の **URL** リストを書き換えないことを認識しません。</span><span class="sxs-lookup"><span data-stu-id="919f0-321">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="919f0-322">ポリシーに含まれるユーザーは、次のクライアントでの安全なリンクスキャンの結果に基づいて URL へのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-322">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="919f0-323">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="919f0-323">Microsoft Teams</span></span>
  - <span data-ttu-id="919f0-324">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="919f0-324">Office web apps</span></span>

  <span data-ttu-id="919f0-325">すべての場所で許可されている URL の本当に汎用的な一覧については、「テナントの許可/ブロックリストの管理 [」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="919f0-325">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="919f0-326">ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-326">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="919f0-327">たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="919f0-327">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="919f0-328">安全なリンク ポリシーで次の **URL** エントリを既に書き換えない場合は、リストを確認し、必要に応じてワイルドカードを追加してください。</span><span class="sxs-lookup"><span data-stu-id="919f0-328">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="919f0-329">たとえば、リストには次のようなエントリが含まれるので、後で次のような `https://contoso.com/a` サブパスを含めることにします `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-329">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="919f0-330">新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、新しいエントリが `https://contoso.com/a/*` 作成されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-330">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="919f0-331">URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="919f0-331">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="919f0-332">ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="919f0-332">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="919f0-333">たとえば、ユーザーが指定したドメイン内のサブドメインとパスにアクセスできるエントリは、同じ `contoso.com` `*.contoso.com/*` `*.contoso.com/*` ではありません。</span><span class="sxs-lookup"><span data-stu-id="919f0-333">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="919f0-334">"次の URL を書き換えない" リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="919f0-334">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="919f0-335">入力できる値とその結果の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="919f0-335">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="919f0-336">値</span><span class="sxs-lookup"><span data-stu-id="919f0-336">Value</span></span>|<span data-ttu-id="919f0-337">結果</span><span class="sxs-lookup"><span data-stu-id="919f0-337">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="919f0-338">サブドメインまたは `https://contoso.com` パスへのアクセスを許可しますが、アクセスは許可しない。</span><span class="sxs-lookup"><span data-stu-id="919f0-338">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="919f0-339">ドメイン、サブドメイン、およびパス (たとえば、, , , , ) へのアクセス `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` を許可します `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="919f0-339">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="919f0-340">このエントリは、不正な可能性のあるサイト (以下のように) を許可しないので、本質的に `*contoso.com*` 優れたエントリ `https://www.falsecontoso.com` です。 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="919f0-340">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="919f0-341">サブパスへの `https://contoso.com/a` アクセスを許可しますが、次のようなサブパスは許可しない `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="919f0-341">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="919f0-342">アクセスを許可 `https://contoso.com/a` し、次のようなサブパスを許可します。 `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="919f0-342">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="919f0-343">安全なリンクからの警告ページ</span><span class="sxs-lookup"><span data-stu-id="919f0-343">Warning pages from Safe Links</span></span>

<span data-ttu-id="919f0-344">このセクションでは、URL をクリックすると安全なリンク保護によってトリガーされるさまざまな警告ページの例を示します。</span><span class="sxs-lookup"><span data-stu-id="919f0-344">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="919f0-345">いくつかの警告ページが更新されています。</span><span class="sxs-lookup"><span data-stu-id="919f0-345">Note that several warning pages have been updated.</span></span> <span data-ttu-id="919f0-346">更新されたページが表示されていない場合は、間もなく表示されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-346">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="919f0-347">更新されたページには、新しい配色、詳細、および指定された警告や推奨事項にもかかわらずサイトに進む機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="919f0-347">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="919f0-348">進行中の通知をスキャンする</span><span class="sxs-lookup"><span data-stu-id="919f0-348">Scan in progress notification</span></span>

<span data-ttu-id="919f0-349">クリックされた URL は安全なリンクによってスキャンされています。</span><span class="sxs-lookup"><span data-stu-id="919f0-349">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="919f0-350">リンクを再び試す前に、しばらく待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="919f0-350">You might need to wait a few moments before trying the link again.</span></span>

!["リンクがスキャンされています" という通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="919f0-352">元の通知ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="919f0-352">The original notification page looked like this:</span></span>

![元の "リンクがスキャンされています" という通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="919f0-354">不審なメッセージの警告</span><span class="sxs-lookup"><span data-stu-id="919f0-354">Suspicious message warning</span></span>

<span data-ttu-id="919f0-355">クリックされた URL は、他の疑わしいメッセージに似た電子メール メッセージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="919f0-355">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="919f0-356">サイトに進む前に、電子メール メッセージをもう一度確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="919f0-356">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["疑わしいメッセージからリンクがクリックされました" という警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="919f0-358">フィッシングの試行に関する警告</span><span class="sxs-lookup"><span data-stu-id="919f0-358">Phishing attempt warning</span></span>

<span data-ttu-id="919f0-359">クリックされた URL は、フィッシング攻撃として識別された電子メール メッセージに含めでした。</span><span class="sxs-lookup"><span data-stu-id="919f0-359">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="919f0-360">その結果、電子メール メッセージ内のすべての URL がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="919f0-360">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="919f0-361">サイトに進めはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="919f0-361">We recommend that you do not proceed to the site.</span></span>

!["フィッシング メッセージからリンクがクリックされました" という警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="919f0-363">悪意のある Web サイトの警告</span><span class="sxs-lookup"><span data-stu-id="919f0-363">Malicious website warning</span></span>

<span data-ttu-id="919f0-364">クリックされた URL は、悪意のあるサイトとして識別されたサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="919f0-364">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="919f0-365">サイトに進めはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="919f0-365">We recommend that you do not proceed to the site.</span></span>

!["この Web サイトは悪意のある Web サイトとして分類されます" という警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="919f0-367">元の警告ページは次のように表示されました。</span><span class="sxs-lookup"><span data-stu-id="919f0-367">The original warning page looked like this:</span></span>

![元の "この Web サイトは悪意のある Web サイトとして分類されています" という警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="919f0-369">ブロックされた URL の警告</span><span class="sxs-lookup"><span data-stu-id="919f0-369">Blocked URL warning</span></span>

<span data-ttu-id="919f0-370">クリックされた URL は、組織内の管理者によって手動でブロックされています ([安全なリンク] のグローバル設定の [次の URL をブロックする] の一覧)。 </span><span class="sxs-lookup"><span data-stu-id="919f0-370">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="919f0-371">リンクは手動でブロックされたため、安全なリンクによってスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="919f0-371">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="919f0-372">管理者が特定の URL を手動でブロックする理由は複数あります。</span><span class="sxs-lookup"><span data-stu-id="919f0-372">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="919f0-373">サイトをブロックしない場合は、管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="919f0-373">If you think the site should not be blocked, contact your admin.</span></span>

!["この Web サイトは管理者によってブロックされました" という警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="919f0-375">元の警告ページは次のように表示されました。</span><span class="sxs-lookup"><span data-stu-id="919f0-375">The original warning page looked like this:</span></span>

![元の "この Web サイトは組織の URL ポリシーに対してブロックされました" という警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="919f0-377">エラー警告</span><span class="sxs-lookup"><span data-stu-id="919f0-377">Error warning</span></span>

<span data-ttu-id="919f0-378">何らかのエラーが発生し、URL を開くことができません。</span><span class="sxs-lookup"><span data-stu-id="919f0-378">Some kind of error has occurred, and the URL can't be opened.</span></span>

!["アクセスしようとしているページを読み込めそうにできません" という警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="919f0-380">元の警告ページは次のように表示されました。</span><span class="sxs-lookup"><span data-stu-id="919f0-380">The original warning page looked like this:</span></span>

![元の "この Web ページを読み込めそうにできません" という警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
