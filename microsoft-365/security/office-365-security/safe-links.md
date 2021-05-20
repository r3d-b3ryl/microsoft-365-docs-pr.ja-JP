---
title: 安全なリンク
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
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
description: この記事では、管理者は、フィッシングや悪意のある URL を使用する他の攻撃から組織を保護するために、Office 365 用 Defender の セーフ リンク保護について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fd5b92400996fa595b5953028e20fcecec976
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583582"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="40a10-103">セーフMicrosoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="40a10-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="40a10-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="40a10-104">**Applies to**</span></span>
- [<span data-ttu-id="40a10-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="40a10-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="40a10-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40a10-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="40a10-107">この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="40a10-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="40a10-108">Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用している場合に、Outlook の Safelinks に関する情報を探している場合は[、「Advanced Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)セキュリティ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="40a10-109">セーフ[リンクは、メール](defender-for-office-365.md)フロー内の受信電子メール メッセージの URL のスキャンと書き換え、および電子メール メッセージなどの URL とリンクのクリック時の検証を提供する Defender for Office 365 の機能です。</span><span class="sxs-lookup"><span data-stu-id="40a10-109">Safe Links is a feature in [Defender for Office 365](defender-for-office-365.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="40a10-110">セーフリンク のスキャンは、受信メール メッセージ[](anti-spam-and-anti-malware-protection.md)(EOP) の通常のスパム対策およびマルウェア対策保護に加えてExchange Online Protection発生します。</span><span class="sxs-lookup"><span data-stu-id="40a10-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="40a10-111">セーフリンクスキャンは、フィッシングなどの攻撃で使用される悪意のあるリンクから組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40a10-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="40a10-112">セーフリンク保護は、次の場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="40a10-113">**電子メール** メッセージ : セーフのリンク保護は、リンク ポリシーによって制御セーフされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="40a10-114">既定のリンク ポリシーセーフないので、電子メール メッセージで セーフ リンクの保護を取得するには、1 つ以上の セーフ **リンク ポリシーを作成する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="40a10-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="40a10-115">手順については、「Microsoft Defender for セーフのリンク ポリシーをセットアップする[」を参照Office 365。](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="40a10-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

  <span data-ttu-id="40a10-116">電子メール メッセージのリンク保護セーフ詳細については、この記事の「セーフのリンク[設定](#safe-links-settings-for-email-messages)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="40a10-117">メールが有効なパブリック フォルダーでは、販売リンクは機能しません。</span><span class="sxs-lookup"><span data-stu-id="40a10-117">Sale Links does not work on mail-enabled public folders.</span></span>

- <span data-ttu-id="40a10-118">**Microsoft Teams** (現在 TAP プレビュー): セーフ 会話、グループ チャット、またはチャネルからのリンクに対する Teams セーフ リンク保護は、セーフ リンク ポリシーによっても制御されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-118">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="40a10-119">既定の セーフ リンク ポリシーはないので、Teams で セーフ リンクの保護を取得するには、1 つ以上の セーフ **リンク ポリシーを作成する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="40a10-119">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="40a10-120">詳細については、セーフのリンク保護Teams後の「セーフのリンク[Microsoft Teams設定」](#safe-links-settings-for-microsoft-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-120">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="40a10-121">**Office 365 :** セーフアプリOffice 365のリンク保護は、サポートされているデスクトップ、モバイル、および Web アプリで利用できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-121">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web apps.</span></span> <span data-ttu-id="40a10-122">リンク **ポリシー** セーフ外Office 365グローバル設定で、アプリのリンク保護セーフ構成します。 </span><span class="sxs-lookup"><span data-stu-id="40a10-122">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="40a10-123">手順については、「Microsoft Defender for セーフリンクのグローバル設定を構成する」[を参照Office 365。](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="40a10-123">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="40a10-124">セーフOffice 365 アプリのリンク保護は、ユーザーがアクティブな セーフ Links ポリシーに含まれているかどうかに関係なく、Office 365 の Defender のライセンスを取得している組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-124">Safe Links protection for Office 365 apps is applied to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span>

  <span data-ttu-id="40a10-125">セーフ アプリの セーフ リンク保護の詳細Office 365、この記事の後半の[](#safe-links-settings-for-office-365-apps)「セーフ リンクの設定Office 365」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="40a10-126">この記事では、リンク設定の次の種類のセーフ説明します。</span><span class="sxs-lookup"><span data-stu-id="40a10-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="40a10-127">**設定リンク** セーフ : これらの設定は、特定のポリシーに含まれるユーザーにのみ適用され、ポリシー間で設定が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="40a10-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="40a10-128">これには、以下の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40a10-128">These settings include:</span></span>

  - [<span data-ttu-id="40a10-129">セーフ電子メール メッセージのリンク設定</span><span class="sxs-lookup"><span data-stu-id="40a10-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="40a10-130">セーフリンクの設定Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40a10-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="40a10-131">リンク ポリシーの 「次の URL を書き換セーフしない」</span><span class="sxs-lookup"><span data-stu-id="40a10-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="40a10-132">**グローバル セーフ リンクの設定**: これらの設定は、リンク ポリシーではなく、グローバルセーフ構成されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="40a10-133">ただし、この設定は、アクティブなリンク ポリシーに含まれるユーザーセーフ適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-133">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="40a10-134">これには、以下の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40a10-134">These settings include:</span></span>

  - [<span data-ttu-id="40a10-135">セーフアプリのリンクOffice 365設定</span><span class="sxs-lookup"><span data-stu-id="40a10-135">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - <span data-ttu-id="40a10-136">[[リンク] の [次の URL をブロックする] セーフします。](#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="40a10-136">["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links)</span></span>

<span data-ttu-id="40a10-137">次の表では、Office 365 の Defender を含む Microsoft 365 および Office 365 組織の セーフ リンクのシナリオについて説明します (つまり、ライセンスの不足は、この例では決して問題ではありません)。</span><span class="sxs-lookup"><span data-stu-id="40a10-137">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

<br>

****

|<span data-ttu-id="40a10-138">シナリオ</span><span class="sxs-lookup"><span data-stu-id="40a10-138">Scenario</span></span>|<span data-ttu-id="40a10-139">結果</span><span class="sxs-lookup"><span data-stu-id="40a10-139">Result</span></span>|
|---|---|
|<span data-ttu-id="40a10-140">Jean はマーケティング部門のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="40a10-140">Jean is a member of the marketing department.</span></span> <span data-ttu-id="40a10-141">セーフセーフ リンクのグローバル設定では、Office 365 アプリのリンク保護が有効にされ、マーケティング部門のメンバーに適用される セーフ リンク ポリシーが存在します。</span><span class="sxs-lookup"><span data-stu-id="40a10-141">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="40a10-142">Jean は、PowerPointメッセージでプレゼンテーションを開き、プレゼンテーション内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-142">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="40a10-143">Jean は、リンクによってセーフされています。</span><span class="sxs-lookup"><span data-stu-id="40a10-143">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="40a10-144">Jean はリンク ポリシーセーフ含まれており、セーフアプリのリンクOffice 365保護が有効です。</span><span class="sxs-lookup"><span data-stu-id="40a10-144">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="40a10-145">Office 365 アプリの セーフ Links 保護の要件の詳細については、この記事の後半の「セーフ リンク設定 for [Office 365 apps」](#safe-links-settings-for-office-365-apps)セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-145">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="40a10-146">Chris の組織Microsoft 365 E5リンク ポリシーセーフ構成されていません。</span><span class="sxs-lookup"><span data-stu-id="40a10-146">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="40a10-147">Chris は、最終的にクリックする悪意のある Web サイトへの URL を含む外部送信者からメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="40a10-147">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="40a10-148">Chris は、リンクによってセーフされません。</span><span class="sxs-lookup"><span data-stu-id="40a10-148">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="40a10-149">管理者は、受信電子メール メッセージで セーフリンク保護を取得するために、セーフリンク ポリシーを 1 つ以上作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40a10-149">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="40a10-150">Chris をポリシーの条件に含め、リンクの保護セーフ必要があります。</span><span class="sxs-lookup"><span data-stu-id="40a10-150">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="40a10-151">Pat の組織では、管理者は セーフ リンク ポリシーを作成したが、セーフアプリの Office 365保護が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="40a10-151">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="40a10-152">Pat は Word ドキュメントを開き、ファイル内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-152">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="40a10-153">Pat はリンクによってセーフされません。</span><span class="sxs-lookup"><span data-stu-id="40a10-153">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="40a10-154">セーフ Office 365 アプリのリンク保護はグローバルに有効になりますが、Pat はアクティブな セーフ リンク ポリシーには含まれていないので、保護を適用できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-154">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="40a10-155">Lee の組織では、リンクのグローバル設定の [次の URL をブロックする] セーフ `https://tailspintoys.com` されます。 </span><span class="sxs-lookup"><span data-stu-id="40a10-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="40a10-156">Lee セーフを含むリンク ポリシーが既に存在します。</span><span class="sxs-lookup"><span data-stu-id="40a10-156">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="40a10-157">Lee は URL を含む電子メール メッセージを受信します `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="40a10-157">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="40a10-158">Lee が URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-158">Lee clicks the URL.</span></span>|<span data-ttu-id="40a10-159">Lee の URL が自動的にブロックされる場合があります。リスト内の URL エントリと、使用するメール クライアント Lee によって異なります。</span><span class="sxs-lookup"><span data-stu-id="40a10-159">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="40a10-160">詳細については、この記事の[後半](#block-the-following-urls-list-for-safe-links)の「リンク」セクションの「セーフ URL をブロックする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-160">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="40a10-161">Jamie と Julia は両方とも、contoso.com。</span><span class="sxs-lookup"><span data-stu-id="40a10-161">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="40a10-162">一昔前に、管理者は Jamie と Julia の両方にセーフリンク ポリシーを構成していました。</span><span class="sxs-lookup"><span data-stu-id="40a10-162">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="40a10-163">Jamie は、電子メールに悪意のある URL が含まれていることを知らずに、電子メールを Julia に送信します。</span><span class="sxs-lookup"><span data-stu-id="40a10-163">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="40a10-164">Julia は、内部受信者セーフメッセージに適用セーフリンク ポリシーが構成されている場合は、セーフ リンクによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-164">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="40a10-165">詳細については、この記事の[「セーフのリンク設定](#safe-links-settings-for-email-messages)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-165">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|
|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="40a10-166">セーフ電子メール メッセージのリンク設定</span><span class="sxs-lookup"><span data-stu-id="40a10-166">Safe Links settings for email messages</span></span>

<span data-ttu-id="40a10-167">セーフリンクは、既知の悪意のあるハイパーリンクの受信メールをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="40a10-167">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="40a10-168">スキャンされた URL は、Microsoft 標準 URL プレフィックスを使用して書き `https://nam01.safelinks.protection.outlook.com` 換えされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-168">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="40a10-169">リンクの書き換え後、悪意のある可能性のあるコンテンツについて分析されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-169">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="40a10-170">[セーフリンクが URL を書き換えた後、メッセージが手動で転送または返信された場合でも、URL は書き換えたままです (内部受信者と外部受信者の両方)。</span><span class="sxs-lookup"><span data-stu-id="40a10-170">After Safe Links rewrites a URL, the URL remains rewritten even if the message is *manually* forwarded or replied to (both to internal and external recipients).</span></span> <span data-ttu-id="40a10-171">転送またはメッセージへの返信に追加される追加のリンクは書き換えされません。</span><span class="sxs-lookup"><span data-stu-id="40a10-171">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span> <span data-ttu-id="40a10-172">ただし、受信トレイ ルールまたは SMTP 転送による自動転送の場合、その受信者が セーフ リンクによって保護されている場合や、以前の通信で URL が既に書き換え済みである場合を含め、最終的な受信者を対象としたメッセージに URL は書き換えされません。</span><span class="sxs-lookup"><span data-stu-id="40a10-172">However, in the case of *automatic* forwarding by Inbox rules or SMTP forwarding, the URL will not be rewritten in the message that's intended for the final recipient *unless* that recipient is also protected by Safe Links or the URL had already been rewritten in a previous communication.</span></span> 

<span data-ttu-id="40a10-173">電子メール メッセージにセーフリンク ポリシーの設定については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="40a10-173">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="40a10-174">**メッセージ内の不明な潜在的に** 悪意のある URL のアクションを選択します:電子メール セーフのリンク スキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="40a10-174">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="40a10-175">推奨される値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="40a10-175">The recommended value is **On**.</span></span> <span data-ttu-id="40a10-176">この設定を有効にすると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-176">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="40a10-177">セーフリンク のスキャンは、Outlook (C2R) で有効Windows。</span><span class="sxs-lookup"><span data-stu-id="40a10-177">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="40a10-178">URL は書き換え、ユーザーはメッセージ内の URL をクリックセーフリンク保護を介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-178">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="40a10-179">クリックすると、既知の悪意のある URL の一覧と [次の URL をブロックする] リストに対して [URL がチェックされます](#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="40a10-179">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="40a10-180">有効な評価を持つ URL は、バックグラウンドで非同期的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="40a10-180">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="40a10-181">**ファイルを指** す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する: ダウンロード可能なコンテンツを指す電子メール メッセージ内のリンクを含む、リンクのリアルタイム スキャンを有効にする。</span><span class="sxs-lookup"><span data-stu-id="40a10-181">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="40a10-182">推奨される値は有効です。</span><span class="sxs-lookup"><span data-stu-id="40a10-182">The recommended value is enabled.</span></span>
  - <span data-ttu-id="40a10-183">**メッセージを配信する前に URL のスキャンが完了するのを待ちます**。</span><span class="sxs-lookup"><span data-stu-id="40a10-183">**Wait for URL scanning to complete before delivering the message**:</span></span>
    - <span data-ttu-id="40a10-184">有効: URL を含むメッセージは、スキャンが完了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-184">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="40a10-185">メッセージは、URL が安全と確認された後にのみ配信されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-185">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="40a10-186">これは推奨される値です。</span><span class="sxs-lookup"><span data-stu-id="40a10-186">This is the recommended value.</span></span>
    - <span data-ttu-id="40a10-187">無効: URL スキャンを完了できない場合は、メッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="40a10-187">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="40a10-188">**[セーフ** 組織内で送信された電子メール メッセージへのリンクの適用: 同じ組織内の内部送信者と内部受信者の間で送信されるメッセージに対する セーフ Exchange Online リンクのスキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="40a10-188">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="40a10-189">推奨される値は有効です。</span><span class="sxs-lookup"><span data-stu-id="40a10-189">The recommended value is enabled.</span></span>

- <span data-ttu-id="40a10-190">**ユーザーのクリックを追跡** しない : 電子メール メッセージでクリックされた URL セーフリンククリック データの保存を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="40a10-190">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="40a10-191">推奨値は、この設定を選択しないままにすることをお勧めします (ユーザーのクリックを追跡する場合)。</span><span class="sxs-lookup"><span data-stu-id="40a10-191">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="40a10-192">内部送信者と内部受信者の間で送信される電子メール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40a10-192">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="40a10-193">**ユーザーに元の URL** へのクリックを許可しない : 警告ページから元の [](#warning-pages-from-safe-links)URL へのクリックをユーザーに許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-193">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="40a10-194">推奨値が有効です。</span><span class="sxs-lookup"><span data-stu-id="40a10-194">The recommend value is enabled.</span></span>

- <span data-ttu-id="40a10-195">**通知ページと警告ページに組織** のブランド化を表示する: このオプションは、警告ページに組織のブランド化を表示します。</span><span class="sxs-lookup"><span data-stu-id="40a10-195">**Display the organization branding on notification and warning pages**: This option shows your organization's branding on warning pages.</span></span> <span data-ttu-id="40a10-196">ブランド化は、既定の Microsoft 警告ページが攻撃者によって頻繁に使用されるので、ユーザーが正当な警告を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40a10-196">Branding helps users identify legitimate warnings, because default Microsoft warning pages are often used by attackers.</span></span> <span data-ttu-id="40a10-197">カスタマイズされたブランド化の詳細については、「組織のカスタム Microsoft 365[テーマをカスタマイズする」を参照してください](../../admin/setup/customize-your-organization-theme.md)。</span><span class="sxs-lookup"><span data-stu-id="40a10-197">For more information about customized branding, see [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md).</span></span>

- <span data-ttu-id="40a10-198">**次の URL を書き換えない**: URL は変更しない。</span><span class="sxs-lookup"><span data-stu-id="40a10-198">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="40a10-199">スキャンを必要としない安全な URL のカスタム リストを保持します。</span><span class="sxs-lookup"><span data-stu-id="40a10-199">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="40a10-200">リストは、リンク ポリシーごとにセーフされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-200">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="40a10-201">[次の URLを書き換えない] リストの詳細については、この記事の[「セーフ Links](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)ポリシー」セクションの「次の URL を書き換えない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-201">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

  <span data-ttu-id="40a10-202">[リンク] ポリシーの Standard および Strict ポリシー設定の推奨値の詳細については、「セーフ セーフリンク ポリシー設定」を[参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="40a10-202">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="40a10-203">**受信者フィルター**: ポリシーが適用されるユーザーを決定する受信者の条件と例外を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40a10-203">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="40a10-204">条件や例外には次のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-204">You can use these properties for conditions and exceptions:</span></span>
  - <span data-ttu-id="40a10-205">**受信者が次の場合**</span><span class="sxs-lookup"><span data-stu-id="40a10-205">**The recipient is**</span></span>
  - <span data-ttu-id="40a10-206">**受信者ドメインは、**</span><span class="sxs-lookup"><span data-stu-id="40a10-206">**The recipient domain is**</span></span>
  - <span data-ttu-id="40a10-207">**受信者が次のメンバーの場合**</span><span class="sxs-lookup"><span data-stu-id="40a10-207">**The recipient is a member of**</span></span>

  <span data-ttu-id="40a10-208">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="40a10-208">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="40a10-209">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-209">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="40a10-210">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-210">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="40a10-211">**優先度**: 複数のポリシーを作成する場合は、適用する順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-211">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="40a10-212">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="40a10-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="40a10-213">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>
  
### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="40a10-214">電子メール セーフリンクの動作方法</span><span class="sxs-lookup"><span data-stu-id="40a10-214">How Safe Links works in email messages</span></span>

<span data-ttu-id="40a10-215">電子メール メッセージ内の URL に対するリンクセーフの仕組みについて、大まかに説明します。</span><span class="sxs-lookup"><span data-stu-id="40a10-215">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="40a10-216">メッセージが受信者のメールボックスに配信される前に、すべての電子メールは EOP を通過します。ここで、インターネット プロトコル (IP) およびエンベロープ フィルター、署名ベースのマルウェア保護、スパム対策およびマルウェア対策フィルター。</span><span class="sxs-lookup"><span data-stu-id="40a10-216">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="40a10-217">ユーザーは自分のメールボックスでメッセージを開き、メッセージ内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-217">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="40a10-218">セーフリンクは、Web サイトを開く前に URL をすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="40a10-218">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="40a10-219">URL が [次の URL をブロックする] リストに **含** まれている場合は、ブロックされた [URL 警告が開](#blocked-url-warning) きます。</span><span class="sxs-lookup"><span data-stu-id="40a10-219">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="40a10-220">URL が悪意のあると判断された Web サイトを参照している場合[](#malicious-website-warning)は、悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="40a10-220">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="40a10-221">URL がダウンロード可能なファイルを指し示し、[ファイルをポイントする疑わしいリンクとリンクのリアルタイム **URL** スキャンを適用する] 設定が、ユーザーに適用されるポリシーで有効になっている場合、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-221">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="40a10-222">URL が安全と判断された場合、Web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="40a10-222">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="40a10-223">セーフリンクの設定Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40a10-223">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40a10-224">2020 年 3 月現在、この機能はプレビューで、Microsoft Teams テクノロジ導入プログラム (TAP) のメンバーにのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-224">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="40a10-225">リリース スケジュールの詳細については、次のロードマップ[をMicrosoft 365してください](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="40a10-225">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="40a10-226">リンク ポリシーで、セーフのリンク保護を有効またはMicrosoft Teams無効セーフします。</span><span class="sxs-lookup"><span data-stu-id="40a10-226">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="40a10-227">具体的には、[不明な URL または潜在的に悪意のある URL に対してアクションを選択する **] Microsoft Teams** します。</span><span class="sxs-lookup"><span data-stu-id="40a10-227">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="40a10-228">推奨される値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="40a10-228">The recommended value is **On**.</span></span>

<span data-ttu-id="40a10-229">電子メール メッセージ内のリンクセーフ適用されるリンク ポリシーの次の設定は、メール メッセージ内のリンクにも適用Teams。</span><span class="sxs-lookup"><span data-stu-id="40a10-229">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="40a10-230">**ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する**</span><span class="sxs-lookup"><span data-stu-id="40a10-230">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="40a10-231">**ユーザーのクリックを追跡しない**</span><span class="sxs-lookup"><span data-stu-id="40a10-231">**Do not track user clicks**</span></span>
- <span data-ttu-id="40a10-232">**ユーザーに元の URL へのクリックを許可しない**</span><span class="sxs-lookup"><span data-stu-id="40a10-232">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="40a10-233">これらの設定については、「電子メール メッセージの[リンクセーフ」で説明しました](#safe-links-settings-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="40a10-233">These settings are explained previously in [Safe Links settings for email messages](#safe-links-settings-for-email-messages).</span></span>

<span data-ttu-id="40a10-234">Microsoft Teams の セーフ リンク保護を有効にすると、保護されたユーザーがリンクをクリックすると、Teams の URL が既知の悪意のあるリンクの一覧に対してチェックされます (クリック時の保護)。</span><span class="sxs-lookup"><span data-stu-id="40a10-234">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="40a10-235">URL は書き換え用ではありません。</span><span class="sxs-lookup"><span data-stu-id="40a10-235">URLs are not rewritten.</span></span> <span data-ttu-id="40a10-236">リンクが悪意のあると判明した場合、ユーザーには次のエクスペリエンスがあります。</span><span class="sxs-lookup"><span data-stu-id="40a10-236">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="40a10-237">Teams 会話、グループ チャット、またはチャネルからリンクがクリックされた場合、次のスクリーンショットに示すように警告ページが既定の Web ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-237">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="40a10-238">ピン留めされたタブからリンクがクリックされた場合、警告ページは、そのタブ内Teamsインターフェイスに表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由から無効になっています。</span><span class="sxs-lookup"><span data-stu-id="40a10-238">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="40a10-239">ポリシーの [ユーザーによる元の URL へのクリックを許可しない] 設定の構成方法に応じて、ユーザーは元の **URL** (スクリーンショットの [続行] (推奨しない **)** をクリックするか、または許可されません。</span><span class="sxs-lookup"><span data-stu-id="40a10-239">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="40a10-240">ユーザーが元の URL をクリックできない場合は、[ユーザーが元の **URL** をクリックすることを許可しない] 設定を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40a10-240">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="40a10-241">Teams 保護が有効になっている セーフ リンク ポリシーにリンクを送信したユーザーが含まれていない場合、ユーザーはコンピューターまたはデバイス上の元の URL を自由にクリックできます。</span><span class="sxs-lookup"><span data-stu-id="40a10-241">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![悪意セーフを報告Teamsページのリンク。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="40a10-243">警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。</span><span class="sxs-lookup"><span data-stu-id="40a10-243">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="40a10-244">ただし、元のリンクを再度クリックすると、セーフリンクが再スキャンされますので、警告ページが再表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-244">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="40a10-245">セーフリンクの動作Teams</span><span class="sxs-lookup"><span data-stu-id="40a10-245">How Safe Links works in Teams</span></span>

<span data-ttu-id="40a10-246">大まかには、次に示すのは、セーフリンクの保護が URL に対してどのように機能Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="40a10-246">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="40a10-247">ユーザーがアプリのTeamsします。</span><span class="sxs-lookup"><span data-stu-id="40a10-247">A user starts the Teams app.</span></span>

2. <span data-ttu-id="40a10-248">Microsoft 365は、ユーザーの組織に microsoft Defender for Office 365 が含まれており、ユーザーがアクティブな セーフ リンク ポリシーに含まれていて、Microsoft Teams の保護が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="40a10-248">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="40a10-249">URL は、チャット、グループ チャット、チャネル、およびタブ内のユーザーのクリック時に検証されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-249">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="40a10-250">セーフアプリのリンクOffice 365設定</span><span class="sxs-lookup"><span data-stu-id="40a10-250">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="40a10-251">セーフOffice 365 アプリのリンク保護は、電子メール メッセージ内のリンクではなく Office ドキュメント内のリンクをチェックします (ただし、ドキュメントを開いた後、添付された Office ドキュメント内のリンクを電子メール メッセージでチェックできます)。</span><span class="sxs-lookup"><span data-stu-id="40a10-251">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="40a10-252">セーフアプリのリンク保護Office 365クライアント要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40a10-252">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="40a10-253">Microsoft 365 AppsまたはMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="40a10-253">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="40a10-254">現在のバージョンの Word、Excel、PowerPoint、Windows Web ブラウザーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-254">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="40a10-255">Office iOS または Android デバイス上のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="40a10-255">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="40a10-256">VisioのWindows。</span><span class="sxs-lookup"><span data-stu-id="40a10-256">Visio on Windows.</span></span>
  - <span data-ttu-id="40a10-257">OneNoteブラウザーで使用します。</span><span class="sxs-lookup"><span data-stu-id="40a10-257">OneNote in a web browser.</span></span>

- <span data-ttu-id="40a10-258">Office 365は、モダン認証を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="40a10-258">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="40a10-259">詳細については[、「Office 2013、Office 2016、および Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md)クライアント アプリの最新の認証のしくみ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-259">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span>

- <span data-ttu-id="40a10-260">ユーザーは、自分の仕事または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="40a10-260">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="40a10-261">詳細については、「サインインしてサインイン[する」を参照Office。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)</span><span class="sxs-lookup"><span data-stu-id="40a10-261">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="40a10-262">リンクポリシーセーフではなく、Office 365 リンクのグローバル設定でセーフリンク保護セーフ構成します。</span><span class="sxs-lookup"><span data-stu-id="40a10-262">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="40a10-263">この保護は、アクティブな セーフ Links ポリシーにユーザーが含まれているかどうかに関係なく、Office 365 の Defender のライセンスを取得している組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-263">The protection is applied to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span>

<span data-ttu-id="40a10-264">[リンク] セーフは、アプリで使用できるOffice 365示します。</span><span class="sxs-lookup"><span data-stu-id="40a10-264">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="40a10-265">**Office 365アプリケーション**: サポートされているアプリでセーフリンクスキャンを有効またはOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="40a10-265">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="40a10-266">既定値と推奨値は On **です**。</span><span class="sxs-lookup"><span data-stu-id="40a10-266">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="40a10-267">**ユーザーが [セーフ** リンク] をクリックした場合は追跡しない : デスクトップ バージョンの Word、Excel、PowerPoint、および Visio でクリックされた URL の セーフ リンク クリック データの保存を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="40a10-267">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="40a10-268">推奨される値は **Off** です。つまり、ユーザーのクリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-268">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="40a10-269">ユーザーが元の **URL** への安全なリンクをクリックさせない : ユーザーが警告 [](#warning-pages-from-safe-links)ページをクリックして、デスクトップ バージョンの Word、Excel、PowerPoint、および Visio の元の URL をクリックVisio。</span><span class="sxs-lookup"><span data-stu-id="40a10-269">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="40a10-270">既定値と推奨値は On **です**。</span><span class="sxs-lookup"><span data-stu-id="40a10-270">The default and recommended value is **On**.</span></span>

<span data-ttu-id="40a10-271">アプリのリンクのセーフ設定を構成するには、「Office 365アプリのリンク保護セーフ[構成する」をOffice 365してください](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="40a10-271">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="40a10-272">Standard および Strict ポリシー設定の推奨値の詳細については、「グローバル設定 for セーフ[リンク」を参照してください](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="40a10-272">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="40a10-273">アプリセーフリンクの動作Office 365方法</span><span class="sxs-lookup"><span data-stu-id="40a10-273">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="40a10-274">大まかには、アプリ内の URL にセーフリンク保護がどのように機能Office 365します。</span><span class="sxs-lookup"><span data-stu-id="40a10-274">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="40a10-275">サポートされているアプリOffice 365前のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="40a10-275">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="40a10-276">ユーザーは、組織で自分の仕事または学校のアカウントを使用してサインインし、Microsoft 365 AppsまたはMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="40a10-276">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="40a10-277">ユーザーが開き、サポートされているドキュメント内OfficeリンクをクリックOffice アプリ。</span><span class="sxs-lookup"><span data-stu-id="40a10-277">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="40a10-278">セーフリンクは、ターゲット Web サイトを開く前に URL をすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="40a10-278">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="40a10-279">[リンクのスキャン] ([次の URL をブロックする] セーフ)をスキップする URL がリストに含まれている場合は、ブロックされた URL 警告[ページが開](#blocked-url-warning)きます。</span><span class="sxs-lookup"><span data-stu-id="40a10-279">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="40a10-280">URL が悪意のあると判断された Web サイトを参照している場合[](#malicious-website-warning)は、悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="40a10-280">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="40a10-281">URL がダウンロード可能なファイルを指し示し、ユーザーに適用される セーフ Links ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (ファイルを指す疑わしいリンクやリンクに対してリアルタイム **URL** スキャンを適用する) 場合、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-281">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="40a10-282">URL が安全であると見なされた場合、ユーザーは Web サイトにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-282">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="40a10-283">[リンクセーフスキャンを完了できない場合は、セーフの保護はトリガーされない。</span><span class="sxs-lookup"><span data-stu-id="40a10-283">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="40a10-284">デスクトップ Officeでは、ユーザーが移動先の Web サイトに進む前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-284">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="40a10-285">各セッションの開始時に、ユーザーが [リンク] を有効にセーフ数秒かかるOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="40a10-285">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="40a10-286">[リンク] の [次の URL をブロックする] セーフします。</span><span class="sxs-lookup"><span data-stu-id="40a10-286">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="40a10-287">[**次の URL をブロックする**] ボックスの一覧では、次の場所にある [リンクセーフスキャンによって常にブロックされるリンクを定義します。</span><span class="sxs-lookup"><span data-stu-id="40a10-287">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="40a10-288">電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="40a10-288">Email messages.</span></span>
- <span data-ttu-id="40a10-289">ドキュメントと Mac Office 365アプリWindowsドキュメント。</span><span class="sxs-lookup"><span data-stu-id="40a10-289">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="40a10-290">iOS Office Android 用のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="40a10-290">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="40a10-291">アクティブなリンク ポリシーのユーザーセーフサポートされているアプリのブロックされたリンクをクリックすると、[ブロックされた URL の警告][ページに移動](#blocked-url-warning)します。</span><span class="sxs-lookup"><span data-stu-id="40a10-291">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="40a10-292">[リンク] のグローバル設定で URL の一覧をセーフします。</span><span class="sxs-lookup"><span data-stu-id="40a10-292">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="40a10-293">手順については [、「Configure the Configure the following URL」リストを参照してください](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="40a10-293">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="40a10-294">**注**:</span><span class="sxs-lookup"><span data-stu-id="40a10-294">**Notes**:</span></span>

- <span data-ttu-id="40a10-295">あらゆる場所でブロックされている URL の本当に汎用的なリストについては、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="40a10-295">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>
- <span data-ttu-id="40a10-296">[次の URL を **ブロックする] リストの制限** 。</span><span class="sxs-lookup"><span data-stu-id="40a10-296">Limits for the **Block the following URLs** list:</span></span>
  - <span data-ttu-id="40a10-297">エントリの最大数は 500 です。</span><span class="sxs-lookup"><span data-stu-id="40a10-297">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="40a10-298">エントリの最大長は 128 文字です。</span><span class="sxs-lookup"><span data-stu-id="40a10-298">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="40a10-299">すべてのエントリは、10,000 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="40a10-299">All of the entries can't exceed 10,000 characters.</span></span>
- <span data-ttu-id="40a10-300">URL の末尾にスラッシュ ( ) を `/` 含めない。</span><span class="sxs-lookup"><span data-stu-id="40a10-300">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="40a10-301">たとえば、 を `https://www.contoso.com` 使用します `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="40a10-301">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>
- <span data-ttu-id="40a10-302">ドメイン専用 URL (たとえば、または) は、ドメインを含む `contoso.com` `tailspintoys.com` すべての URL をブロックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-302">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>
- <span data-ttu-id="40a10-303">完全なドメインをブロックせずにサブドメインをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="40a10-303">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="40a10-304">たとえば、サブドメインを含む URL をブロックしますが、完全なドメインを含む `toys.contoso.com*` URL はブロックしない `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="40a10-304">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>
- <span data-ttu-id="40a10-305">URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="40a10-305">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="40a10-306">"次の URL をブロックする" リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="40a10-306">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="40a10-307">入力できる値とその結果の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="40a10-307">Examples of the values that you can enter and their results are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="40a10-308">値</span><span class="sxs-lookup"><span data-stu-id="40a10-308">Value</span></span>|<span data-ttu-id="40a10-309">結果</span><span class="sxs-lookup"><span data-stu-id="40a10-309">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="40a10-310">または</span><span class="sxs-lookup"><span data-stu-id="40a10-310">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="40a10-311">ドメイン、サブドメイン、およびパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="40a10-311">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="40a10-312">たとえば `https://www.contoso.com` `https://sub.contoso.com` 、、、 `https://contoso.com/abc` およびブロックされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-312">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="40a10-313">ブロック `https://contoso.com/a` ですが、追加のサブパスはブロックしない `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="40a10-313">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="40a10-314">ブロック `https://contoso.com/a` や追加のサブパス `https://contoso.com/a/b` (.</span><span class="sxs-lookup"><span data-stu-id="40a10-314">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="40a10-315">サブドメイン (この例では) をブロックしますが、他のドメイン URL (など) へのクリック `toys` を `https://contoso.com` 許可 `https://home.contoso.com` します。</span><span class="sxs-lookup"><span data-stu-id="40a10-315">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="40a10-316">リンク ポリシーの 「次の URL を書き換セーフしない」</span><span class="sxs-lookup"><span data-stu-id="40a10-316">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="40a10-317">組織で [リンク] セーフ使用している場合は、サード パーティのフィッシング テストでサポートされている唯一の方法は、次の **URL** リストを書き換えない方法です。</span><span class="sxs-lookup"><span data-stu-id="40a10-317">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="40a10-318">各 セーフ リンク ポリシーには、リンクスキャンによって書き換えされない URL を指定するために使用できる次の URL リストを書き換セーフ含まれます。</span><span class="sxs-lookup"><span data-stu-id="40a10-318">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="40a10-319">つまり、ポリシーに含まれるユーザーは、ポリシーに含まれているユーザーが、リンクによってブロックされる指定された URL にアクセスセーフします。</span><span class="sxs-lookup"><span data-stu-id="40a10-319">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="40a10-320">リンク ポリシーごとに異なるリストセーフ構成できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-320">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="40a10-321">ポリシー処理は、最初の (優先度が最も高い) ポリシーがユーザーに適用された後に停止します。</span><span class="sxs-lookup"><span data-stu-id="40a10-321">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="40a10-322">そのため、1 つの **み次** の URL リストを書き換えないと、複数のアクティブ なリンク ポリシーに含まれるユーザーセーフ適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-322">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="40a10-323">新規または既存の セーフ リンク ポリシーのリストにエントリを追加するには、「Create[セーフ Links ポリシー](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) 」または「セーフ リンク ポリシーを変更する」[を参照してください](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="40a10-323">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="40a10-324">**注**:</span><span class="sxs-lookup"><span data-stu-id="40a10-324">**Notes**:</span></span>

- <span data-ttu-id="40a10-325">次のクライアントは、[リンク] ポリシーの [次の **URL** を書き換えセーフしません。</span><span class="sxs-lookup"><span data-stu-id="40a10-325">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="40a10-326">ポリシーに含まれるユーザーは、次のクライアントでのリンク スキャンの結果に基づいて URL へのアクセスをブロックセーフできます。</span><span class="sxs-lookup"><span data-stu-id="40a10-326">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>
  - <span data-ttu-id="40a10-327">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40a10-327">Microsoft Teams</span></span>
  - <span data-ttu-id="40a10-328">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="40a10-328">Office web apps</span></span>

  <span data-ttu-id="40a10-329">すべての場所で許可されている URL の本当に汎用的なリストについては [、「Manage the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="40a10-329">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="40a10-330">ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-330">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="40a10-331">たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="40a10-331">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>
- <span data-ttu-id="40a10-332">既に **[セーフ** リンク] ポリシーで次の URL エントリを書き換えない場合は、リストを確認し、必要に応じてワイルドカードを追加してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-332">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="40a10-333">たとえば、リストには次のようなエントリが含まれるので、後で次のような `https://contoso.com/a` サブパスを含めることにしました `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="40a10-333">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="40a10-334">新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、 `https://contoso.com/a/*` になります。</span><span class="sxs-lookup"><span data-stu-id="40a10-334">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>
- <span data-ttu-id="40a10-335">URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="40a10-335">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="40a10-336">ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="40a10-336">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="40a10-337">たとえば、指定したドメイン内のサブドメインとパスをユーザーがアクセスできるので、エントリは同 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` じではありません。</span><span class="sxs-lookup"><span data-stu-id="40a10-337">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>
- <span data-ttu-id="40a10-338">URL で HTTP から HTTPS への自動リダイレクト (302 リダイレクトなど) を使用し、同じ URL の HTTP エントリと HTTPS エントリの両方をリストに入力すると、2 番目の URL エントリが最初の URL エントリに置き換わる可能性があります。 `http://www.contoso.com` `https://www.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="40a10-338">If a URL uses automatic redirection for HTTP to HTTPS (for example, 302 redirection for `http://www.contoso.com` to `https://www.contoso.com`), and you try to enter both HTTP and HTTPS entries for the same URL to the list, you might notice that the second URL entry replaces the first URL entry.</span></span> <span data-ttu-id="40a10-339">この動作は、HTTP バージョンと HTTPS バージョンの URL が完全に分離されている場合は発生しません。</span><span class="sxs-lookup"><span data-stu-id="40a10-339">This behavior does not occur if the HTTP and HTTPS versions of the URL are completely separate.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="40a10-340">"次の URL を書き換えない" リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="40a10-340">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="40a10-341">入力できる値とその結果の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="40a10-341">Examples of the values that you can enter and their results are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="40a10-342">値</span><span class="sxs-lookup"><span data-stu-id="40a10-342">Value</span></span>|<span data-ttu-id="40a10-343">結果</span><span class="sxs-lookup"><span data-stu-id="40a10-343">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="40a10-344">サブドメインまたは `https://contoso.com` パスへのアクセスを許可しますが、アクセスを許可しない。</span><span class="sxs-lookup"><span data-stu-id="40a10-344">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="40a10-345">ドメイン、サブドメイン、およびパス (たとえば、) へのアクセス `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` を許可します `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="40a10-345">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="40a10-346">このエントリは、潜在的に詐欺的なサイトを許可しないので、本来よりも `*contoso.com*` 優れた方法 `https://www.falsecontoso.com` です。 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="40a10-346">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="40a10-347">サブパスへの `https://contoso.com/a` アクセスを許可しますが、サブパスは許可しない `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="40a10-347">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="40a10-348">次のようなアクセス `https://contoso.com/a` とサブパスを許可します `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="40a10-348">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="40a10-349">[リンク] からのセーフページ</span><span class="sxs-lookup"><span data-stu-id="40a10-349">Warning pages from Safe Links</span></span>

<span data-ttu-id="40a10-350">このセクションには、URL をクリックするときにリンク保護を実行セーフさまざまな警告ページの例を示します。</span><span class="sxs-lookup"><span data-stu-id="40a10-350">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="40a10-351">いくつかの警告ページが更新された点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="40a10-351">Note that several warning pages have been updated.</span></span> <span data-ttu-id="40a10-352">更新されたページがまだ表示されていない場合は、すぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-352">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="40a10-353">更新されたページには、新しい配色、詳細、および指定された警告と推奨事項にもかかわらずサイトに進む機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="40a10-353">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="40a10-354">進行中の通知をスキャンする</span><span class="sxs-lookup"><span data-stu-id="40a10-354">Scan in progress notification</span></span>

<span data-ttu-id="40a10-355">クリックした URL は、[リンク] でセーフされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-355">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="40a10-356">リンクを再度試す前に、しばらく待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="40a10-356">You might need to wait a few moments before trying the link again.</span></span>

!["リンクがスキャン中" 通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="40a10-358">元の通知ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-358">The original notification page looked like this:</span></span>

![元の "リンクがスキャン中" 通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="40a10-360">疑わしいメッセージの警告</span><span class="sxs-lookup"><span data-stu-id="40a10-360">Suspicious message warning</span></span>

<span data-ttu-id="40a10-361">クリックされた URL は、他の疑わしいメッセージに似た電子メール メッセージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="40a10-361">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="40a10-362">サイトに進む前に、電子メール メッセージをもう一度確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40a10-362">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["疑わしいメッセージからリンクがクリックされました" という警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="40a10-364">フィッシングの試行の警告</span><span class="sxs-lookup"><span data-stu-id="40a10-364">Phishing attempt warning</span></span>

<span data-ttu-id="40a10-365">クリックされた URL は、フィッシング攻撃として識別された電子メール メッセージに含めでした。</span><span class="sxs-lookup"><span data-stu-id="40a10-365">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="40a10-366">その結果、電子メール メッセージ内のすべての URL がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="40a10-366">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="40a10-367">サイトに進むのはやめすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40a10-367">We recommend that you do not proceed to the site.</span></span>

!["フィッシング メッセージからリンクがクリックされました" という警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="40a10-369">悪意のある Web サイトの警告</span><span class="sxs-lookup"><span data-stu-id="40a10-369">Malicious website warning</span></span>

<span data-ttu-id="40a10-370">クリックされた URL は、悪意のあるサイトをポイントします。</span><span class="sxs-lookup"><span data-stu-id="40a10-370">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="40a10-371">サイトに進むのはやめすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40a10-371">We recommend that you do not proceed to the site.</span></span>

![「この Web サイトは悪意のある Web サイトに分類されます」という警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="40a10-373">元の警告ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-373">The original warning page looked like this:</span></span>

![元の "この Web サイトは悪意のある Web サイトとして分類されています" という警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="40a10-375">ブロックされた URL の警告</span><span class="sxs-lookup"><span data-stu-id="40a10-375">Blocked URL warning</span></span>

<span data-ttu-id="40a10-376">クリックされた URL は、組織内の管理者によって手動でブロックされています ([リンク] のグローバル設定の [次の URL をブロックセーフします)。 </span><span class="sxs-lookup"><span data-stu-id="40a10-376">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="40a10-377">リンクは手動でブロックセーフリンクによってスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="40a10-377">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="40a10-378">管理者が特定の URL を手動でブロックする理由は複数あります。</span><span class="sxs-lookup"><span data-stu-id="40a10-378">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="40a10-379">サイトをブロックしない場合は、管理者に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="40a10-379">If you think the site should not be blocked, contact your admin.</span></span>

!["この Web サイトは管理者によってブロックされました" という警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="40a10-381">元の警告ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-381">The original warning page looked like this:</span></span>

![元の "この Web サイトは、組織の URL ポリシーごとにブロックされています" という警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="40a10-383">エラー警告</span><span class="sxs-lookup"><span data-stu-id="40a10-383">Error warning</span></span>

<span data-ttu-id="40a10-384">何らかのエラーが発生し、URL を開くことができません。</span><span class="sxs-lookup"><span data-stu-id="40a10-384">Some kind of error has occurred, and the URL can't be opened.</span></span>

![「アクセスしようとしているページを読み込め」という警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="40a10-386">元の警告ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="40a10-386">The original warning page looked like this:</span></span>

![元の "この Web ページを読み込めない" という警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
