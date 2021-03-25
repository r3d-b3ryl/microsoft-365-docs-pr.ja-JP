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
description: この記事では、管理者は、フィッシングや悪意のある URL を使用する他の攻撃から組織を保護するために、Office 365 の Defender のセーフ リンク保護について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ec3ab1a255e9eaa8c190ed5c248c9587273e03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206560"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="105ef-103">Microsoft Defender for Office 365 の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="105ef-103">Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="105ef-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="105ef-104">**Applies to**</span></span>
- [<span data-ttu-id="105ef-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="105ef-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="105ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="105ef-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="105ef-107">この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="105ef-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="105ef-108">Outlook.com、Microsoft 365 ファミリ、または Microsoft 365 Personal を使用している場合、Outlook で Safelinks に関する情報を探している場合は、「Advanced Outlook.com security 」 [を参照](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-108">If you're using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="105ef-109">セーフ リンクは、メール フロー内の受信メール メッセージの URL のスキャンと書き換え、および電子メール メッセージなどの URL とリンクのクリック時の検証を提供する [、Defender for Office 365](defender-for-office-365.md) の機能です。</span><span class="sxs-lookup"><span data-stu-id="105ef-109">Safe Links is a feature in [Defender for Office 365](defender-for-office-365.md) that provides URL scanning and rewriting of inbound email messages in mail flow, and time-of-click verification of URLs and links in email messages and other locations.</span></span> <span data-ttu-id="105ef-110">安全なリンクのスキャンは、Exchange Online [](anti-spam-and-anti-malware-protection.md) Protection (EOP) の受信電子メール メッセージの通常のスパム対策およびマルウェア対策保護に加えて行われます。</span><span class="sxs-lookup"><span data-stu-id="105ef-110">Safe Links scanning occurs in addition to the regular [anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md) in inbound email messages in Exchange Online Protection (EOP).</span></span> <span data-ttu-id="105ef-111">安全なリンクスキャンは、フィッシングなどの攻撃で使用される悪意のあるリンクから組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="105ef-111">Safe Links scanning can help protect your organization from malicious links that are used in phishing and other attacks.</span></span>

<span data-ttu-id="105ef-112">安全なリンク保護は、次の場所で利用できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-112">Safe Links protection is available in the following locations:</span></span>

- <span data-ttu-id="105ef-113">**電子メール メッセージ**: 電子メール メッセージ内のリンクに対するセーフ リンク保護は、セーフ リンク ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-113">**Email messages**: Safe Links protection for links in email messages is controlled by Safe Links policies.</span></span> <span data-ttu-id="105ef-114">既定のセーフ リンク ポリシーはないので、電子メール メッセージでセーフ リンクの保護を取得するには、1 つ以上のセーフ リンク ポリシーを **作成する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="105ef-114">There is no default Safe Links policy, **so to get the protection of Safe Links in email messages, you need to create one or more Safe Links policies**.</span></span> <span data-ttu-id="105ef-115">手順については [、「Set up Safe Links policies in Microsoft Defender for Office 365」を参照してください](set-up-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="105ef-115">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

  <span data-ttu-id="105ef-116">電子メール メッセージのセーフ リンク保護の詳細については、この記事の後半の「電子メール メッセージのセーフ リンク [設定」セクション](#safe-links-settings-for-email-messages) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-116">For more information about Safe Links protection for email messages, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>

- <span data-ttu-id="105ef-117">**Microsoft Teams** (現在 TAP プレビュー): Teams の会話、グループ チャット、またはチャネルからのリンクに対するセーフ リンク保護は、セーフ リンク ポリシーによっても制御されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-117">**Microsoft Teams** (currently in TAP Preview): Safe Links protection for links in Teams conversations, group chats, or from channels is also controlled by Safe Links policies.</span></span> <span data-ttu-id="105ef-118">既定のセーフ リンク ポリシーはないので、Teams でセーフ リンクの保護を取得するには、1 つ以上のセーフ リンク ポリシーを **作成する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="105ef-118">There is no default Safe Links policy, **so to get the protection of Safe Links in Teams, you need to create one or more Safe Links policies**.</span></span>

  <span data-ttu-id="105ef-119">Teams のセーフ リンク保護の詳細については、この記事の後半の [「Microsoft Teams](#safe-links-settings-for-microsoft-teams) の安全なリンク設定」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-119">For more information about Safe Links protection in Teams, see the [Safe Links settings for Microsoft Teams](#safe-links-settings-for-microsoft-teams) section later in this article.</span></span>

- <span data-ttu-id="105ef-120">**Office 365** アプリ : 365 アプリOfficeセーフ リンク保護は、サポートされているデスクトップ、モバイル、および Web aps で利用できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-120">**Office 365 apps**: Safe Links protection for Office 365 apps is available in supported desktop, mobile, and web aps.</span></span> <span data-ttu-id="105ef-121">セーフ **リンク** ポリシーの外部にあるグローバルOffice 365 アプリに対してセーフ リンク保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="105ef-121">You **configure** Safe Links protection for Office 365 apps in the global setting that are **outside** of Safe Links policies.</span></span> <span data-ttu-id="105ef-122">手順については、「Configure global settings for Safe Links settings [in Microsoft Defender for microsoft Defender for Office 365」 を参照してください](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="105ef-122">For instructions, see [Configure global settings for Safe Links settings in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

  <span data-ttu-id="105ef-123">ただし、365 のアプリOfficeリンク保護は、アクティブなセーフリンク ポリシーに含まれるユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-123">But, Safe Links protection for Office 365 apps is only **applied** to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="105ef-124">ユーザーがアクティブなセーフ リンク ポリシーに含まれていない場合、ユーザーはサポートされている 365 アプリでセーフ リンクOfficeされません。</span><span class="sxs-lookup"><span data-stu-id="105ef-124">If a user isn't included in an active Safe Links policy, the user doesn't get Safe Links protection in supported Office 365 apps.</span></span>

  <span data-ttu-id="105ef-125">Office 365 アプリのセーフ リンク保護の詳細については、この記事の「Office [365](#safe-links-settings-for-office-365-apps) アプリのセーフ リンク設定」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-125">For more information about Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>

<span data-ttu-id="105ef-126">この記事では、次の種類のセーフ リンク設定の詳細な説明について説明します。</span><span class="sxs-lookup"><span data-stu-id="105ef-126">This article includes detailed descriptions of the following types of Safe Links settings:</span></span>

- <span data-ttu-id="105ef-127">**セーフ リンク ポリシーの設定**: これらの設定は、特定のポリシーに含まれるユーザーにのみ適用され、ポリシー間で設定が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-127">**Settings in Safe Links policies**: These settings apply only to the users who are included in the specific policies, and the settings might be different between policies.</span></span> <span data-ttu-id="105ef-128">これらの設定には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="105ef-128">These settings include:</span></span>

  - [<span data-ttu-id="105ef-129">電子メール メッセージの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="105ef-129">Safe Links settings for email messages</span></span>](#safe-links-settings-for-email-messages)
  - [<span data-ttu-id="105ef-130">Microsoft Teams の安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="105ef-130">Safe Links settings for Microsoft Teams</span></span>](#safe-links-settings-for-microsoft-teams)
  - [<span data-ttu-id="105ef-131">セーフ リンク ポリシーの "次の URL を書き換えない" リスト</span><span class="sxs-lookup"><span data-stu-id="105ef-131">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- <span data-ttu-id="105ef-132">**グローバル セーフ リンクの設定**: これらの設定は、セーフ リンク ポリシーではなく、グローバルに構成されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-132">**Global Safe Links settings**: These settings are configured globally, not in Safe Links policies.</span></span> <span data-ttu-id="105ef-133">ただし、この設定は、アクティブなセーフ リンク ポリシーに含まれているユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-133">But, the settings apply only to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="105ef-134">これらの設定には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="105ef-134">These settings include:</span></span>

  - [<span data-ttu-id="105ef-135">365 アプリの安全Office設定</span><span class="sxs-lookup"><span data-stu-id="105ef-135">Safe Links settings for Office 365 apps</span></span>](#safe-links-settings-for-office-365-apps)
  - [<span data-ttu-id="105ef-136">セーフ リンクの "次の URL をブロックする" リスト</span><span class="sxs-lookup"><span data-stu-id="105ef-136">"Block the following URLs" list for Safe Links</span></span>](#block-the-following-urls-list-for-safe-links)

<span data-ttu-id="105ef-137">次の表では、Microsoft 365 および Office 365 の Defender for Office 365 を含む組織のセーフ リンクのシナリオについて説明します (つまり、ライセンスの不足は、例では決して問題ではありません)。</span><span class="sxs-lookup"><span data-stu-id="105ef-137">The following table describes scenarios for Safe Links in Microsoft 365 and Office 365 organizations that include Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="105ef-138">シナリオ</span><span class="sxs-lookup"><span data-stu-id="105ef-138">Scenario</span></span>|<span data-ttu-id="105ef-139">結果</span><span class="sxs-lookup"><span data-stu-id="105ef-139">Result</span></span>|
|---|---|
|<span data-ttu-id="105ef-140">Jean はマーケティング部門のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="105ef-140">Jean is a member of the marketing department.</span></span> <span data-ttu-id="105ef-141">Office 365 アプリのセーフ リンク保護は、セーフ リンクのグローバル設定で有効にされ、マーケティング部門のメンバーに適用されるセーフ リンク ポリシーが存在します。</span><span class="sxs-lookup"><span data-stu-id="105ef-141">Safe Links protection for Office 365 apps is turned on in the global settings for Safe Links, and a Safe Links policy that applies to members of the marketing department exists.</span></span> <span data-ttu-id="105ef-142">Jean は、電子メール メッセージで PowerPoint プレゼンテーションを開き、プレゼンテーション内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-142">Jean opens a PowerPoint presentation in an email message, and then clicks a URL in the presentation.</span></span>|<span data-ttu-id="105ef-143">Jean はセーフ リンクによって保護されています。</span><span class="sxs-lookup"><span data-stu-id="105ef-143">Jean is protected by Safe Links.</span></span> <p> <span data-ttu-id="105ef-144">Jean はセーフ リンク ポリシーに含まれており、365 アプリの安全Office保護が有効です。</span><span class="sxs-lookup"><span data-stu-id="105ef-144">Jean is included in a Safe Links policy, and Safe Links protection for Office 365 apps is turned on.</span></span> <p> <span data-ttu-id="105ef-145">Office 365 アプリのセーフ リンク保護の要件の詳細については、この記事の後半の [「Office 365](#safe-links-settings-for-office-365-apps) アプリのセーフ リンク設定」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-145">For more information about the requirements for Safe Links protection in Office 365 apps, see the [Safe Links settings for Office 365 apps](#safe-links-settings-for-office-365-apps) section later in this article.</span></span>|
|<span data-ttu-id="105ef-146">Chris の Microsoft 365 E5 組織には、セーフ リンク ポリシーが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="105ef-146">Chris's Microsoft 365 E5 organization has no Safe Links policies configured.</span></span> <span data-ttu-id="105ef-147">Chris は、最終的にクリックする悪意のある Web サイトへの URL を含む外部送信者からメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="105ef-147">Chris receives an email from an external sender that contains a URL to a malicious website that he ultimately clicks.</span></span>|<span data-ttu-id="105ef-148">Chris はセーフ リンクによって保護されません。</span><span class="sxs-lookup"><span data-stu-id="105ef-148">Chris is not protected by Safe Links.</span></span> <p> <span data-ttu-id="105ef-149">管理者は、受信電子メール メッセージでセーフ リンク保護を取得するために、すべてのユーザーに対して少なくとも 1 つのセーフ リンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-149">An admin must create at least one Safe Links policy for anyone to get Safe Links protection in inbound email messages.</span></span> <span data-ttu-id="105ef-150">安全なリンク保護を取得するには、ポリシーの条件に Chris を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-150">Chris must be included in the conditions of policy to get Safe Links protection.</span></span>|
|<span data-ttu-id="105ef-151">Pat の組織では、管理者はセーフ リンク ポリシーを作成していなかっていますが、365 アプリのセーフ Office保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="105ef-151">In Pat's organization, no admins have created any Safe Links policies, but Safe Links protection for Office 365 apps is turned on.</span></span> <span data-ttu-id="105ef-152">Pat は Word ドキュメントを開き、ファイル内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-152">Pat opens a Word document and clicks a URL in the file.</span></span>|<span data-ttu-id="105ef-153">Pat はセーフ リンクで保護されません。</span><span class="sxs-lookup"><span data-stu-id="105ef-153">Pat is not protected by Safe Links.</span></span> <p> <span data-ttu-id="105ef-154">Office 365 アプリの安全なリンク保護はグローバルに有効になりますが、Pat はアクティブなセーフ リンク ポリシーには含まれていないので、保護を適用できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-154">Although Safe Links protection for Office 365 apps is turned on globally, Pat is not included in any active Safe Links policies, so the protection can't be applied.</span></span>|
|<span data-ttu-id="105ef-155">Lee の組織では、セーフ リンクのグローバル設定の [次の URL をブロックする] `https://tailspintoys.com` リストで構成されます。 </span><span class="sxs-lookup"><span data-stu-id="105ef-155">In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links.</span></span> <span data-ttu-id="105ef-156">Lee を含むセーフ リンク ポリシーが既に存在します。</span><span class="sxs-lookup"><span data-stu-id="105ef-156">A Safe Links policy that includes Lee already exists.</span></span> <span data-ttu-id="105ef-157">Lee は URL を含む電子メール メッセージを受信します `https://tailspintoys.com/aboutus/trythispage` 。</span><span class="sxs-lookup"><span data-stu-id="105ef-157">Lee receives an email message that contains the URL `https://tailspintoys.com/aboutus/trythispage`.</span></span> <span data-ttu-id="105ef-158">Lee が URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-158">Lee clicks the URL.</span></span>|<span data-ttu-id="105ef-159">Lee の URL が自動的にブロックされる場合があります。リスト内の URL エントリと、使用するメール クライアント Lee によって異なります。</span><span class="sxs-lookup"><span data-stu-id="105ef-159">The URL might be automatically blocked for Lee; it depends on the URL entry in the list and the email client Lee used.</span></span> <span data-ttu-id="105ef-160">詳細については、この記事の [後半](#block-the-following-urls-list-for-safe-links) の「安全なリンク」セクションの「次の URL をブロックする」の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-160">For more information, see the ["Block the following URLs" list for Safe Links](#block-the-following-urls-list-for-safe-links) section later in this article.</span></span>|
|<span data-ttu-id="105ef-161">Jamie と Julia は両方とも、contoso.com。</span><span class="sxs-lookup"><span data-stu-id="105ef-161">Jamie and Julia both work for contoso.com.</span></span> <span data-ttu-id="105ef-162">長い時間前、管理者は Jamie と Julia の両方に適用されるセーフ リンク ポリシーを構成しました。</span><span class="sxs-lookup"><span data-stu-id="105ef-162">A long time ago, admins configured Safe Links policies that apply to both of Jamie and Julia.</span></span> <span data-ttu-id="105ef-163">Jamie は、電子メールに悪意のある URL が含まれていることを知らずに、電子メールを Julia に送信します。</span><span class="sxs-lookup"><span data-stu-id="105ef-163">Jamie sends an email to Julia, not knowing that the email contains a malicious URL.</span></span>|<span data-ttu-id="105ef-164">Julia は、内部受信者間のメッセージに適用するセーフ リンク ポリシーが構成されている場合、セーフ リンクによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-164">Julia is protected by Safe Links **if** the Safe Links policy that applies to her is configured to apply to messages between internal recipients.</span></span> <span data-ttu-id="105ef-165">詳細については、この記事の後半の「電子メール メッセージの安全 [なリンク設定](#safe-links-settings-for-email-messages) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-165">For more information, see the [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section later in this article.</span></span>|

## <a name="safe-links-settings-for-email-messages"></a><span data-ttu-id="105ef-166">電子メール メッセージの安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="105ef-166">Safe Links settings for email messages</span></span>

<span data-ttu-id="105ef-167">セーフ リンクは、既知の悪意のあるハイパーリンクの受信メールをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="105ef-167">Safe Links scans incoming email for known malicious hyperlinks.</span></span> <span data-ttu-id="105ef-168">スキャンされた URL は、Microsoft 標準 URL プレフィックスを使用して書き `https://nam01.safelinks.protection.outlook.com` 換えされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-168">Scanned URLs are rewritten using the Microsoft standard URL prefix: `https://nam01.safelinks.protection.outlook.com`.</span></span> <span data-ttu-id="105ef-169">リンクの書き換え後、悪意のある可能性のあるコンテンツについて分析されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-169">After the link is rewritten, it's analyzed for potentially malicious content.</span></span>

<span data-ttu-id="105ef-170">セーフ リンクが URL を書き換えた後、メッセージが手動で転送または返信された (内部受信者と外部受信者の両方) 場合でも、URL は書き換えたままです。</span><span class="sxs-lookup"><span data-stu-id="105ef-170">After Safe Links rewrites a URL, the URL remains rewritten even if the message is *manually* forwarded or replied to (both to internal and external recipients).</span></span> <span data-ttu-id="105ef-171">転送またはメッセージへの返信に追加される追加のリンクは書き換えされません。</span><span class="sxs-lookup"><span data-stu-id="105ef-171">Additional links that are added to the forwarded or replied to message are not rewritten.</span></span> <span data-ttu-id="105ef-172">ただし、受信トレイ ルールまたは SMTP 転送による自動転送の場合、その受信者がセーフ リンクによって保護されている場合や、以前の通信でURL が既に書き換え済みである場合を限り、最終的な受信者を対象としたメッセージに URL は書き換えされません。</span><span class="sxs-lookup"><span data-stu-id="105ef-172">However, in the case of *automatic* forwarding by Inbox rules or SMTP forwarding, the URL will not be rewritten in the message that's intended for the final recipient *unless* that recipient is also protected by Safe Links or the URL had already been rewritten in a previous communication.</span></span> 

<span data-ttu-id="105ef-173">電子メール メッセージに適用されるセーフ リンク ポリシーの設定については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="105ef-173">The settings in Safe Links policies that apply to email messages are described in the following list:</span></span>

- <span data-ttu-id="105ef-174">**メッセージ内の不明な潜在的に悪意** のある URL のアクションを選択します。電子メール メッセージのセーフ リンク スキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="105ef-174">**Select the action for unknown potentially malicious URLs in messages**: Enables or disables Safe Links scanning in email messages.</span></span> <span data-ttu-id="105ef-175">推奨される値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="105ef-175">The recommended value is **On**.</span></span> <span data-ttu-id="105ef-176">この設定を有効にすると、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-176">Turning on this setting results in the following actions.</span></span>

  - <span data-ttu-id="105ef-177">Windows の Outlook (C2R) で安全なリンクのスキャンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="105ef-177">Safe Links scanning is enabled in Outlook (C2R) on Windows.</span></span>
  - <span data-ttu-id="105ef-178">URL が書き換えされ、メッセージ内の URL をクリックすると、ユーザーはセーフ リンク保護を介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-178">URLs are rewritten and users are routed through Safe Links protection when they click URLs in messages.</span></span>
  - <span data-ttu-id="105ef-179">クリックすると、既知の悪意のある URL の一覧と [次の URL をブロックする] リストに対して [URL がチェックされます](#block-the-following-urls-list-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="105ef-179">When clicked, URLs are checked against a list of known malicious URLs and the ["Block the following URLs" list](#block-the-following-urls-list-for-safe-links).</span></span>
  - <span data-ttu-id="105ef-180">有効な評価を持つ URL は、バックグラウンドで非同期的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="105ef-180">URLs that don't have a valid reputation are detonated asynchronously in the background.</span></span>

- <span data-ttu-id="105ef-181">**ファイルを指** す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する: ダウンロード可能なコンテンツを指す電子メール メッセージ内のリンクを含む、リンクのリアルタイム スキャンを有効にする。</span><span class="sxs-lookup"><span data-stu-id="105ef-181">**Apply real-time URL scanning for suspicious links and links that point to files**: Enables real-time scanning of links, including links in email messages that point to downloadable content.</span></span> <span data-ttu-id="105ef-182">推奨される値は有効です。</span><span class="sxs-lookup"><span data-stu-id="105ef-182">The recommended value is enabled.</span></span>

  - <span data-ttu-id="105ef-183">**メッセージを配信する前に URL のスキャンが完了するのを待ちます**。</span><span class="sxs-lookup"><span data-stu-id="105ef-183">**Wait for URL scanning to complete before delivering the message**:</span></span>

    - <span data-ttu-id="105ef-184">有効: URL を含むメッセージは、スキャンが完了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-184">Enabled: Messages that contain URLs are held until scanning is finished.</span></span> <span data-ttu-id="105ef-185">メッセージは、URL が安全と確認された後にのみ配信されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-185">Messages are delivered only after the URLs are confirmed to be safe.</span></span> <span data-ttu-id="105ef-186">これは推奨される値です。</span><span class="sxs-lookup"><span data-stu-id="105ef-186">This is the recommended value.</span></span>
    - <span data-ttu-id="105ef-187">無効: URL スキャンを完了できない場合は、メッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="105ef-187">Disabled: If URL scanning can't complete, deliver the message anyway.</span></span>

- <span data-ttu-id="105ef-188">**組織内で送信** される電子メール メッセージに安全なリンクを適用する: 内部送信者と同じ Exchange Online 組織内の内部受信者間で送信されるメッセージに対するセーフ リンク スキャンを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="105ef-188">**Apply Safe Links to email messages sent within the organization**: Enables or disables Safe Links scanning on messages sent between internal senders and internal recipients within the same Exchange Online organization.</span></span> <span data-ttu-id="105ef-189">推奨される値は有効です。</span><span class="sxs-lookup"><span data-stu-id="105ef-189">The recommended value is enabled.</span></span>

- <span data-ttu-id="105ef-190">**ユーザーのクリックを追跡しない**: 電子メール メッセージでクリックされた URL のセーフ リンク クリック データの保存を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="105ef-190">**Do not track user clicks**: Enables or disables storing Safe Links click data for URLs clicked in email messages.</span></span> <span data-ttu-id="105ef-191">推奨値は、この設定を選択しないままにすることをお勧めします (ユーザーのクリックを追跡する場合)。</span><span class="sxs-lookup"><span data-stu-id="105ef-191">The recommend value is to leave this setting unselected (to track user clicks).</span></span>

  <span data-ttu-id="105ef-192">内部送信者と内部受信者の間で送信される電子メール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="105ef-192">URL click tracking for links in email messages sent between internal senders and internal recipients is currently not supported.</span></span>

- <span data-ttu-id="105ef-193">**ユーザーに元の URL** へのクリックを許可しない : 警告ページから元の [](#warning-pages-from-safe-links)URL へのクリックをユーザーに許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-193">**Do not allow users to click through to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL.</span></span> <span data-ttu-id="105ef-194">推奨値が有効です。</span><span class="sxs-lookup"><span data-stu-id="105ef-194">The recommend value is enabled.</span></span>

- <span data-ttu-id="105ef-195">**通知ページと警告ページに組織** のブランド化を表示する: このオプションは、警告ページに組織のブランド化を表示します。</span><span class="sxs-lookup"><span data-stu-id="105ef-195">**Display the organization branding on notification and warning pages**: This option shows your organization's branding on warning pages.</span></span> <span data-ttu-id="105ef-196">ブランド化は、既定の Microsoft 警告ページが攻撃者によって頻繁に使用されるので、ユーザーが正当な警告を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="105ef-196">Branding helps users identify legitimate warnings, because default Microsoft warning pages are often used by attackers.</span></span> <span data-ttu-id="105ef-197">カスタマイズされたブランド化の詳細については、「組織の Azure Active Directory サインイン ページにブランド化を追加する [」を参照してください](/azure/active-directory/fundamentals/customize-branding)。</span><span class="sxs-lookup"><span data-stu-id="105ef-197">For more information about customized branding, see [Add branding to your organization's Azure Active Directory sign-in page](/azure/active-directory/fundamentals/customize-branding).</span></span>

- <span data-ttu-id="105ef-198">**次の URL を書き換えない**: URL は変更しない。</span><span class="sxs-lookup"><span data-stu-id="105ef-198">**Do not rewrite the following URLs**: Leaves URLs as they are.</span></span> <span data-ttu-id="105ef-199">スキャンを必要としない安全な URL のカスタム リストを保持します。</span><span class="sxs-lookup"><span data-stu-id="105ef-199">Keeps a custom list of safe URLs that don't need scanning.</span></span> <span data-ttu-id="105ef-200">リストは、各セーフ リンク ポリシーで一意です。</span><span class="sxs-lookup"><span data-stu-id="105ef-200">The list is unique for each Safe Links policy.</span></span> <span data-ttu-id="105ef-201">[次の URLを書き換えない] リストの詳細[](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)については、この記事の後半の「セーフ リンク ポリシー」の「次の URL を書き換えない」リストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-201">For more information about the **Do not rewrite the following URLs** list, see the ["Do not rewrite the following URLs" lists in Safe Links policies](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="105ef-202">安全なリンク ポリシーの Standard および Strict ポリシー設定の推奨値の詳細については、「セーフ リンク ポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="105ef-202">For more information about the recommended values for Standard and Strict policy settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="105ef-203">**受信者フィルター**: ポリシーが適用されるユーザーを決定する受信者の条件と例外を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-203">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="105ef-204">条件や例外には次のプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-204">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="105ef-205">**受信者が次の場合**</span><span class="sxs-lookup"><span data-stu-id="105ef-205">**The recipient is**</span></span>
  - <span data-ttu-id="105ef-206">**受信者ドメインは、**</span><span class="sxs-lookup"><span data-stu-id="105ef-206">**The recipient domain is**</span></span>
  - <span data-ttu-id="105ef-207">**受信者が次のメンバーの場合**</span><span class="sxs-lookup"><span data-stu-id="105ef-207">**The recipient is a member of**</span></span>

  <span data-ttu-id="105ef-208">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="105ef-208">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="105ef-209">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-209">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="105ef-210">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-210">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="105ef-211">**優先度**: 複数のポリシーを作成する場合は、適用する順序を指定できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-211">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="105ef-212">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="105ef-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="105ef-213">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="how-safe-links-works-in-email-messages"></a><span data-ttu-id="105ef-214">電子メール メッセージでのセーフ リンクの動作</span><span class="sxs-lookup"><span data-stu-id="105ef-214">How Safe Links works in email messages</span></span>

<span data-ttu-id="105ef-215">電子メール メッセージ内の URL に対するセーフ リンク保護の仕組みについて、大まかに説明します。</span><span class="sxs-lookup"><span data-stu-id="105ef-215">At a high level, here's how Safe Links protection works on URLs in email messages:</span></span>

1. <span data-ttu-id="105ef-216">メッセージが受信者のメールボックスに配信される前に、すべての電子メールは EOP を通過します。ここで、インターネット プロトコル (IP) およびエンベロープ フィルター、署名ベースのマルウェア保護、スパム対策およびマルウェア対策フィルター。</span><span class="sxs-lookup"><span data-stu-id="105ef-216">All email goes through EOP, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters before the message is delivered to the recipient's mailbox.</span></span>

2. <span data-ttu-id="105ef-217">ユーザーは自分のメールボックスでメッセージを開き、メッセージ内の URL をクリックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-217">The user opens the message in their mailbox and clicks on a URL in the message.</span></span>

3. <span data-ttu-id="105ef-218">セーフ リンクは、Web サイトを開く前に URL をすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="105ef-218">Safe Links immediately checks the URL before opening the website:</span></span>

   - <span data-ttu-id="105ef-219">URL が [次の URL をブロックする] リストに **含** まれている場合は、ブロックされた [URL 警告が開](#blocked-url-warning) きます。</span><span class="sxs-lookup"><span data-stu-id="105ef-219">If the URL is included in the **Block the following URLs** list, a [blocked URL warning](#blocked-url-warning) opens.</span></span>

   - <span data-ttu-id="105ef-220">URL が悪意のあると判断された Web サイトを参照している場合[](#malicious-website-warning)は、悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="105ef-220">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="105ef-221">URL がダウンロード可能なファイルを指し示し、[ファイルをポイントする疑わしいリンクとリンクのリアルタイム **URL** スキャンを適用する] 設定が、ユーザーに適用されるポリシーで有効になっている場合、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-221">If the URL points to a downloadable file, and the **Apply real-time URL scanning for suspicious links and links that point to files** setting is enabled in the policy that applies to the user, the downloadable file is checked.</span></span>

   - <span data-ttu-id="105ef-222">URL が安全と判断された場合、Web サイトが開きます。</span><span class="sxs-lookup"><span data-stu-id="105ef-222">If the URL is determined to be safe, the website opens.</span></span>

## <a name="safe-links-settings-for-microsoft-teams"></a><span data-ttu-id="105ef-223">Microsoft Teams の安全なリンク設定</span><span class="sxs-lookup"><span data-stu-id="105ef-223">Safe Links settings for Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="105ef-224">2020 年 3 月現在、この機能はプレビューで、Microsoft Teams テクノロジ導入プログラム (TAP) のメンバーにのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-224">As of March 2020, this feature is in Preview and is available only to members of the Microsoft Teams Technology Adoption Program (TAP).</span></span> <span data-ttu-id="105ef-225">リリース スケジュールの詳細については [、「Microsoft 365 ロードマップ」を参照してください](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。</span><span class="sxs-lookup"><span data-stu-id="105ef-225">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams).</span></span>

<span data-ttu-id="105ef-226">セーフ リンク ポリシーで Microsoft Teams のセーフ リンク保護を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="105ef-226">You enable or disable Safe Links protection for Microsoft Teams in Safe Links policies.</span></span> <span data-ttu-id="105ef-227">具体的には、[Microsoft Teams 内の不明な URL または潜在的に悪意のある URL のアクションを選択する] **設定を使用** します。</span><span class="sxs-lookup"><span data-stu-id="105ef-227">Specifically, you use the **Select the action for unknown or potentially malicious URLs within Microsoft Teams** setting.</span></span> <span data-ttu-id="105ef-228">推奨される値は **On です**。</span><span class="sxs-lookup"><span data-stu-id="105ef-228">The recommended value is **On**.</span></span>

<span data-ttu-id="105ef-229">電子メール メッセージ内のリンクに適用されるセーフ リンク ポリシーの次の設定は、Teams のリンクにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-229">The following settings in Safe Links policies that apply to links in email messages also apply to links in Teams:</span></span>

- <span data-ttu-id="105ef-230">**ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する**</span><span class="sxs-lookup"><span data-stu-id="105ef-230">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>
- <span data-ttu-id="105ef-231">**ユーザーのクリックを追跡しない**</span><span class="sxs-lookup"><span data-stu-id="105ef-231">**Do not track user clicks**</span></span>
- <span data-ttu-id="105ef-232">**ユーザーに元の URL へのクリックを許可しない**</span><span class="sxs-lookup"><span data-stu-id="105ef-232">**Do not allow users to click through to original URL**</span></span>

<span data-ttu-id="105ef-233">これらの設定については、「電子メール メッセージの安全 [なリンクの設定」セクションで説明](#safe-links-settings-for-email-messages) します。</span><span class="sxs-lookup"><span data-stu-id="105ef-233">These settings are explained in the previous [Safe Links settings for email messages](#safe-links-settings-for-email-messages) section.</span></span>

<span data-ttu-id="105ef-234">Microsoft Teams の安全なリンク保護を有効にすると、保護されたユーザーがリンクをクリックすると、Teams の URL が既知の悪意のあるリンクの一覧に対してチェックされます (クリック時の保護)。</span><span class="sxs-lookup"><span data-stu-id="105ef-234">After you turn on Safe Links protection for Microsoft Teams, URLs in Teams are checked against a list of known malicious links when the protected user clicks the link (time-of-click protection).</span></span> <span data-ttu-id="105ef-235">URL は書き換え用ではありません。</span><span class="sxs-lookup"><span data-stu-id="105ef-235">URLs are not rewritten.</span></span> <span data-ttu-id="105ef-236">リンクが悪意のあると判明した場合、ユーザーには次のエクスペリエンスがあります。</span><span class="sxs-lookup"><span data-stu-id="105ef-236">If a link is found to be malicious, users will have the following experiences:</span></span>

- <span data-ttu-id="105ef-237">Teams の会話、グループ チャット、またはチャネルでリンクがクリックされた場合、次のスクリーンショットに示すように警告ページが既定の Web ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-237">If the link was clicked in a Teams conversation, group chat, or from channels, the warning page as shown in the screenshot below will appear in the default web browser.</span></span>
- <span data-ttu-id="105ef-238">ピン留めされたタブからリンクがクリックされた場合、警告ページはタブ内の Teams インターフェイスに表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由から無効になっています。</span><span class="sxs-lookup"><span data-stu-id="105ef-238">If the link was clicked from a pinned tab, the warning page will appear in the Teams interface within that tab. The option to open the link in a web browser is disabled for security reasons.</span></span>
- <span data-ttu-id="105ef-239">ポリシーの [ユーザーによる元の URL へのクリックを許可しない] 設定の構成方法に応じて、ユーザーは元の **URL** (スクリーンショットの [続行] (推奨しない **)** をクリックするか、または許可されません。</span><span class="sxs-lookup"><span data-stu-id="105ef-239">Depending on how the **Do not allow users to click through to original URL** setting in the policy is configured, the user will or will not be allowed to click through to the original URL (**Continue anyway (not recommended)** in the screenshot).</span></span> <span data-ttu-id="105ef-240">ユーザーが元の URL をクリックできない場合は、[ユーザーが元の **URL** をクリックすることを許可しない] 設定を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="105ef-240">We recommend that you enable the **Do not allow users to click through to original URL** setting so users can't click through to the original URL.</span></span>

<span data-ttu-id="105ef-241">リンクを送信したユーザーが Teams 保護が有効になっているセーフ リンク ポリシーに含まれていない場合、ユーザーはコンピューターまたはデバイス上の元の URL を自由にクリックできます。</span><span class="sxs-lookup"><span data-stu-id="105ef-241">If the user who sent the link isn't included in a Safe Links policy where Teams protection is enabled, the user is free to click through to the original URL on their computer or device.</span></span>

![悪意のあるリンクを報告する Teams の安全なリンク ページ。](../../media/tp-safe-links-for-teams-malicious.png)

<span data-ttu-id="105ef-243">警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。</span><span class="sxs-lookup"><span data-stu-id="105ef-243">Clicking the **Go Back** button on the warning page will return the user to their original context or URL location.</span></span> <span data-ttu-id="105ef-244">ただし、元のリンクを再度クリックすると、セーフ リンクが URL を再スキャンし、警告ページが再表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-244">However, clicking on the original link again will cause Safe Links to rescan the URL, so the warning page will reappear.</span></span>

### <a name="how-safe-links-works-in-teams"></a><span data-ttu-id="105ef-245">Teams での安全なリンクの動作</span><span class="sxs-lookup"><span data-stu-id="105ef-245">How Safe Links works in Teams</span></span>

<span data-ttu-id="105ef-246">Microsoft Teams の URL に対するセーフ リンク保護の仕組みは、大まかです。</span><span class="sxs-lookup"><span data-stu-id="105ef-246">At a high level, here's how Safe Links protection works for URLs in Microsoft Teams:</span></span>

1. <span data-ttu-id="105ef-247">ユーザーが Teams アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="105ef-247">A user starts the Teams app.</span></span>

2. <span data-ttu-id="105ef-248">Microsoft 365 は、ユーザーの組織に Office 365 用 Microsoft Defender が含まれており、Microsoft Teams の保護が有効になっているアクティブなセーフ リンク ポリシーにユーザーが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="105ef-248">Microsoft 365 verifies that the user's organization includes Microsoft Defender for Office 365, and that the user is included in an active Safe Links policy where protection for Microsoft Teams is enabled.</span></span>

3. <span data-ttu-id="105ef-249">URL は、チャット、グループ チャット、チャネル、およびタブ内のユーザーのクリック時に検証されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-249">URLs are validated at the time of click for the user in chats, group chats, channels, and tabs.</span></span>

## <a name="safe-links-settings-for-office-365-apps"></a><span data-ttu-id="105ef-250">365 アプリの安全Office設定</span><span class="sxs-lookup"><span data-stu-id="105ef-250">Safe Links settings for Office 365 apps</span></span>

<span data-ttu-id="105ef-251">Office 365 アプリの安全なリンク保護は、電子メール メッセージ内のリンクではなく Office ドキュメント内のリンクをチェックします (ただし、ドキュメントを開いた後、電子メール メッセージ内の添付 Office ドキュメントのリンクをチェックできます)。</span><span class="sxs-lookup"><span data-stu-id="105ef-251">Safe Links protection for Office 365 apps checks links in Office documents, not links in email messages (but it can check links in attached Office documents in email messages after the document is opened).</span></span>

<span data-ttu-id="105ef-252">365 のアプリOfficeの安全なリンク保護には、次のクライアント要件があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-252">Safe Links protection for Office 365 apps has the following client requirements:</span></span>

- <span data-ttu-id="105ef-253">Microsoft 365 Apps または Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="105ef-253">Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="105ef-254">Windows、Mac、または Web ブラウザーの Word、Excel、PowerPoint の現在のバージョン。</span><span class="sxs-lookup"><span data-stu-id="105ef-254">Current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a web browser.</span></span>
  - <span data-ttu-id="105ef-255">Office Android デバイス上のアプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="105ef-255">Office apps on iOS or Android devices.</span></span>
  - <span data-ttu-id="105ef-256">Visio on Windows。</span><span class="sxs-lookup"><span data-stu-id="105ef-256">Visio on Windows.</span></span>
  - <span data-ttu-id="105ef-257">Web ブラウザーの OneNote。</span><span class="sxs-lookup"><span data-stu-id="105ef-257">OneNote in a web browser.</span></span>

- <span data-ttu-id="105ef-258">Office 365 アプリは、最新の認証を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="105ef-258">Office 365 apps are configured to use modern authentication.</span></span> <span data-ttu-id="105ef-259">詳細については、「最新の認証が [2016、Office 2013 2016、Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md)クライアント アプリでどのように機能Officeか」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-259">For more information, see [How modern authentication works for Office 2013, Office 2016, and Office 2019 client apps](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span>

- <span data-ttu-id="105ef-260">ユーザーは、自分の仕事または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="105ef-260">Users are signed in using their work or school accounts.</span></span> <span data-ttu-id="105ef-261">詳細については、「サインインしてサインイン[する」を参照Office。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)</span><span class="sxs-lookup"><span data-stu-id="105ef-261">For more information, see [Sign in to Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).</span></span>

<span data-ttu-id="105ef-262">セーフ リンクポリシーではなく、Officeリンクのグローバル設定で、365 アプリのセーフ リンク保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="105ef-262">You configure Safe Links protection for Office 365 apps in the global settings for Safe Links, not in Safe Links policies.</span></span> <span data-ttu-id="105ef-263">ただし、Office 365 アプリのセーフ リンク保護を適用するには、Office ドキュメントを開いてリンクをクリックするユーザーは、アクティブなセーフ リンク ポリシーに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-263">But, in order for Safe Links protection for Office 365 apps to be applied, the user who opens the Office document and clicks the link must be included in an active Safe Links policy.</span></span>

<span data-ttu-id="105ef-264">次のセーフ リンク設定は、365 アプリOffice使用できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-264">The following Safe Links settings are available for Office 365 apps:</span></span>

- <span data-ttu-id="105ef-265">**Office 365 アプリケーション**: サポートされている 365 アプリでセーフ リンク スキャンOfficeまたは無効にします。</span><span class="sxs-lookup"><span data-stu-id="105ef-265">**Office 365 applications**: Enables or disables Safe Links scanning in supported Office 365 apps.</span></span> <span data-ttu-id="105ef-266">既定値と推奨値は On **です**。</span><span class="sxs-lookup"><span data-stu-id="105ef-266">The default and recommended value is **On**.</span></span>

- <span data-ttu-id="105ef-267">**ユーザーが**[安全なリンク] をクリックしても追跡しない : デスクトップ バージョンの Word、Excel、PowerPoint、Visio でクリックされた URL のセーフ リンク クリック データの保存を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="105ef-267">**Do not track when users click Safe Links**: Enables or disables storing Safe Links click data for URLs clicked in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="105ef-268">推奨される値は **Off** です。つまり、ユーザーのクリックが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-268">The recommended value is **Off**, which means user clicks are tracked.</span></span>

- <span data-ttu-id="105ef-269">**ユーザー** が元の URL への安全なリンクをクリックさせない : ユーザーが警告 [](#warning-pages-from-safe-links)ページをクリックして、デスクトップ バージョンの Word、Excel、PowerPoint、Visio の元の URL に対してクリックを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-269">**Do not let users click through safe links to original URL**: Allows or blocks users from clicking through the [warning page](#warning-pages-from-safe-links) to the original URL in in the desktop versions Word, Excel, PowerPoint, and Visio.</span></span> <span data-ttu-id="105ef-270">既定値と推奨値は On **です**。</span><span class="sxs-lookup"><span data-stu-id="105ef-270">The default and recommended value is **On**.</span></span>

<span data-ttu-id="105ef-271">365 アプリのセーフ リンクOffice構成するには、「Configure Safe Links protection for Office [365 アプリ」を参照してください](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="105ef-271">To configure the Safe Links settings for Office 365 apps, see [Configure Safe Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).</span></span>

<span data-ttu-id="105ef-272">Standard および Strict ポリシー設定の推奨値の詳細については、「セーフ リンクの [グローバル設定」を参照してください](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="105ef-272">For more information about the recommended values for Standard and Strict policy settings, see [Global settings for Safe Links](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links).</span></span>

### <a name="how-safe-links-works-in-office-365-apps"></a><span data-ttu-id="105ef-273">365 アプリでセーフ リンクOffice動作する方法</span><span class="sxs-lookup"><span data-stu-id="105ef-273">How Safe Links works in Office 365 apps</span></span>

<span data-ttu-id="105ef-274">365 アプリの URL に対するセーフ リンク保護の仕組Office示します。</span><span class="sxs-lookup"><span data-stu-id="105ef-274">At a high level, here's how Safe Links protection works for URLs in Office 365 apps.</span></span> <span data-ttu-id="105ef-275">365 Officeサポートされているアプリについては、前のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="105ef-275">The supported Office 365 apps are described in the previous section.</span></span>

1. <span data-ttu-id="105ef-276">ユーザーは、Microsoft 365 Apps または Microsoft 365 Business Premium を含む組織内の仕事または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="105ef-276">A user signs in using their work or school account in an organization that includes Microsoft 365 Apps or Microsoft 365 Business Premium.</span></span>

2. <span data-ttu-id="105ef-277">ユーザーが開き、サポートされているアプリ内OfficeドキュメントのリンクをOfficeします。</span><span class="sxs-lookup"><span data-stu-id="105ef-277">The user opens and clicks on a link an Office document in a supported Office app.</span></span>

3. <span data-ttu-id="105ef-278">セーフ リンクは、ターゲット Web サイトを開く前に URL をすぐに確認します。</span><span class="sxs-lookup"><span data-stu-id="105ef-278">Safe Links immediately checks the URL before opening the target website:</span></span>

   - <span data-ttu-id="105ef-279">安全なリンクのスキャンをスキップする URL がリストに含まれている場合([次の URL をブロックする] ボックスの一覧)、ブロックされた URL 警告[ページが開](#blocked-url-warning)きます。</span><span class="sxs-lookup"><span data-stu-id="105ef-279">If the URL is included in the list that skips Safe Links scanning (the **Block the following URLs** list) a [blocked URL warning](#blocked-url-warning) page opens.</span></span>

   - <span data-ttu-id="105ef-280">URL が悪意のあると判断された Web サイトを参照している場合[](#malicious-website-warning)は、悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。</span><span class="sxs-lookup"><span data-stu-id="105ef-280">If the URL points to a website that has been determined to be malicious, a [malicious website warning](#malicious-website-warning) page (or a different warning page) opens.</span></span>

   - <span data-ttu-id="105ef-281">URL がダウンロード可能なファイルを指し示し、ユーザーに適用されるセーフ リンク ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (ファイルを指す疑わしいリンクやリンクに対してリアルタイム **URL** スキャンを適用する) 場合は、ダウンロード可能なファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-281">If the URL points to a downloadable file, and the Safe Links policy that applies to the user is configured to scan links to downloadable content (**Apply real-time URL scanning for suspicious links and links that point to files**), the downloadable file is checked.</span></span>

   - <span data-ttu-id="105ef-282">URL が安全であると見なされた場合、ユーザーは Web サイトにアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-282">If the URL is considered safe, the user is taken to the website.</span></span>

   - <span data-ttu-id="105ef-283">セーフ リンクのスキャンを完了できない場合、セーフ リンク保護はトリガーされない。</span><span class="sxs-lookup"><span data-stu-id="105ef-283">If Safe Links scanning is unable to complete, Safe Links protection does not trigger.</span></span> <span data-ttu-id="105ef-284">デスクトップ Officeでは、ユーザーが宛先 Web サイトに進む前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-284">In Office desktop clients, the user will be warned before they proceed to the destination website.</span></span>

> [!NOTE]
> <span data-ttu-id="105ef-285">各セッションの開始時に、ユーザーが安全なリンクを有効にOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="105ef-285">It may take several seconds at the beginning of each session to verify that the user has Safe Links for Office enabled.</span></span>

## <a name="block-the-following-urls-list-for-safe-links"></a><span data-ttu-id="105ef-286">セーフ リンクの "次の URL をブロックする" リスト</span><span class="sxs-lookup"><span data-stu-id="105ef-286">"Block the following URLs" list for Safe Links</span></span>

<span data-ttu-id="105ef-287">[ **次の URL をブロックする** ] ボックスの一覧では、次の場所でセーフ リンク スキャンによって常にブロックされるリンクを定義します。</span><span class="sxs-lookup"><span data-stu-id="105ef-287">The **Block the following URLs** list defines the links that are always blocked by Safe Links scanning in the following locations:</span></span>

- <span data-ttu-id="105ef-288">電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="105ef-288">Email messages.</span></span>
- <span data-ttu-id="105ef-289">Windows と Mac Office 365 アプリ内のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="105ef-289">Documents in Office 365 apps in Windows and Mac.</span></span>
- <span data-ttu-id="105ef-290">iOS Office Android 用のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="105ef-290">Documents in Office for iOS and Android.</span></span>

<span data-ttu-id="105ef-291">アクティブなセーフ リンク ポリシーのユーザーが、サポートされているアプリ内のブロックされたリンクをクリックすると、[ブロックされた URL 警告] [ページに移動](#blocked-url-warning) します。</span><span class="sxs-lookup"><span data-stu-id="105ef-291">When a user in an active Safe Links policy clicks a blocked link in a supported app, they're taken to the [Blocked URL warning](#blocked-url-warning) page.</span></span>

<span data-ttu-id="105ef-292">セーフ リンクのグローバル設定で URL の一覧を構成します。</span><span class="sxs-lookup"><span data-stu-id="105ef-292">You configure the list of URLs in the global settings for Safe Links.</span></span> <span data-ttu-id="105ef-293">手順については [、「Configure the Configure the following URL」リストを参照してください](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="105ef-293">For instructions, see [Configure the "Block the following URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).</span></span>

<span data-ttu-id="105ef-294">**注**:</span><span class="sxs-lookup"><span data-stu-id="105ef-294">**Notes**:</span></span>

- <span data-ttu-id="105ef-295">あらゆる場所でブロックされている URL の本当に汎用的なリストについては、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="105ef-295">For a truly universal list of URLs that are blocked everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="105ef-296">制限:</span><span class="sxs-lookup"><span data-stu-id="105ef-296">Limits:</span></span>
  - <span data-ttu-id="105ef-297">エントリの最大数は 500 です。</span><span class="sxs-lookup"><span data-stu-id="105ef-297">The maximum number of entries is 500.</span></span>
  - <span data-ttu-id="105ef-298">エントリの最大長は 128 文字です。</span><span class="sxs-lookup"><span data-stu-id="105ef-298">The maximum length of an entry is 128 characters.</span></span>
  - <span data-ttu-id="105ef-299">すべてのエントリは、10,000 文字を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="105ef-299">All of the entries can't exceed 10,000 characters.</span></span>

- <span data-ttu-id="105ef-300">URL の末尾にスラッシュ ( ) を `/` 含めない。</span><span class="sxs-lookup"><span data-stu-id="105ef-300">Don't include a forward slash (`/`) at the end of the URL.</span></span> <span data-ttu-id="105ef-301">たとえば、 を `https://www.contoso.com` 使用します `https://www.contoso.com/` 。</span><span class="sxs-lookup"><span data-stu-id="105ef-301">For example, use `https://www.contoso.com`, not `https://www.contoso.com/`.</span></span>

- <span data-ttu-id="105ef-302">ドメイン専用 URL (たとえば、または) は、ドメインを含む `contoso.com` `tailspintoys.com` すべての URL をブロックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-302">A domain only-URL (for example `contoso.com` or `tailspintoys.com`) will block any URL that contains the domain.</span></span>

- <span data-ttu-id="105ef-303">完全なドメインをブロックせずにサブドメインをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="105ef-303">You can block a subdomain without blocking the full domain.</span></span> <span data-ttu-id="105ef-304">たとえば、サブドメインを含む URL をブロックしますが、完全なドメインを含む `toys.contoso.com*` URL はブロックしない `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="105ef-304">For example, `toys.contoso.com*` blocks any URL that contains the subdomain, but it doesn't block URLs that contain the full domain `contoso.com`.</span></span>

- <span data-ttu-id="105ef-305">URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="105ef-305">You can include up to three wildcards (`*`) per URL entry.</span></span>

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a><span data-ttu-id="105ef-306">"次の URL をブロックする" リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="105ef-306">Entry syntax for the "Block the following URLs" list</span></span>

<span data-ttu-id="105ef-307">入力できる値とその結果の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="105ef-307">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="105ef-308">値</span><span class="sxs-lookup"><span data-stu-id="105ef-308">Value</span></span>|<span data-ttu-id="105ef-309">結果</span><span class="sxs-lookup"><span data-stu-id="105ef-309">Result</span></span>|
|---|---|
|`contoso.com` <p> <span data-ttu-id="105ef-310">または</span><span class="sxs-lookup"><span data-stu-id="105ef-310">or</span></span> <p> `*contoso.com*`|<span data-ttu-id="105ef-311">ドメイン、サブドメイン、およびパスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="105ef-311">Blocks the domain, subdomains, and paths.</span></span> <span data-ttu-id="105ef-312">たとえば `https://www.contoso.com` `https://sub.contoso.com` 、、、 `https://contoso.com/abc` およびブロックされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-312">For example, `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc` are blocked.</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="105ef-313">ブロック `https://contoso.com/a` ですが、追加のサブパスはブロックしない `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="105ef-313">Blocks `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="105ef-314">ブロック `https://contoso.com/a` や追加のサブパス `https://contoso.com/a/b` (.</span><span class="sxs-lookup"><span data-stu-id="105ef-314">Blocks `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`.</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="105ef-315">サブドメイン (この例では) をブロックしますが、他のドメイン URL (など) へのクリック `toys` を `https://contoso.com` 許可 `https://home.contoso.com` します。</span><span class="sxs-lookup"><span data-stu-id="105ef-315">Blocks a subdomain (`toys` in this example) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a><span data-ttu-id="105ef-316">セーフ リンク ポリシーの "次の URL を書き換えない" リスト</span><span class="sxs-lookup"><span data-stu-id="105ef-316">"Do not rewrite the following URLs" lists in Safe Links policies</span></span>

> [!NOTE]
> <span data-ttu-id="105ef-317">組織でセーフ リンク ポリシーを使用している場合は、サードパーティのフィッシング テストでサポートされている唯一の方法は、次の **URL** リストを書き換えない方法です。</span><span class="sxs-lookup"><span data-stu-id="105ef-317">If your organization use Safe Links policies, the **Do not rewrite the following URLs** lists are the only supported method for third party phishing tests.</span></span>

<span data-ttu-id="105ef-318">各セーフ リンク ポリシーには、セーフ リンク スキャンによって書き換えされない URL を指定するために使用できる次の URL リストを書き換えないが含まれます。</span><span class="sxs-lookup"><span data-stu-id="105ef-318">Each Safe Links policy contains a **Do not rewrite the following URLs** list that you can use to specify URLs that are not rewritten by Safe Links scanning.</span></span> <span data-ttu-id="105ef-319">つまり、ポリシーに含まれるユーザーは、セーフ リンクによってブロックされる指定された URL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="105ef-319">In other words, the list allows users who are included in the policy to access the specified URLs that would otherwise be blocked by Safe Links.</span></span> <span data-ttu-id="105ef-320">さまざまなセーフ リンク ポリシーでさまざまなリストを構成できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-320">You can configure different lists in different Safe Links policies.</span></span> <span data-ttu-id="105ef-321">ポリシー処理は、最初の (優先度が最も高い) ポリシーがユーザーに適用された後に停止します。</span><span class="sxs-lookup"><span data-stu-id="105ef-321">Policy processing stops after the first (likely, the highest priority) policy is applied to the user.</span></span> <span data-ttu-id="105ef-322">したがって **、1 つのみ次の URL** リストを書き換えないと、複数のアクティブなセーフ リンク ポリシーに含まれるユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-322">So, only one **Do not rewrite the following URLs** list is applied to a user who is included in multiple active Safe Links policies.</span></span>

<span data-ttu-id="105ef-323">新規または既存のセーフ リンク ポリシーのリストにエントリを追加するには、「Create Safe [Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies」を参照してください](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="105ef-323">To add entries to the list in new or existing Safe Links policies, see [Create Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).</span></span>

<span data-ttu-id="105ef-324">**注**:</span><span class="sxs-lookup"><span data-stu-id="105ef-324">**Notes**:</span></span>

- <span data-ttu-id="105ef-325">次のクライアントは、セーフ リンク ポリシーの [次の URL を書き **換** えない] リストを認識しません。</span><span class="sxs-lookup"><span data-stu-id="105ef-325">The following clients don't recognize the **Do not rewrite the following URLs** lists in Safe Links policies.</span></span> <span data-ttu-id="105ef-326">ポリシーに含まれるユーザーは、次のクライアントでのセーフ リンク スキャンの結果に基づいて URL へのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="105ef-326">Users included in the polices can be blocked from accessing the URLs based on the results of Safe Links scanning in these clients:</span></span>

  - <span data-ttu-id="105ef-327">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="105ef-327">Microsoft Teams</span></span>
  - <span data-ttu-id="105ef-328">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="105ef-328">Office web apps</span></span>

  <span data-ttu-id="105ef-329">すべての場所で許可されている URL の本当に汎用的なリストについては [、「Manage the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="105ef-329">For a truly universal list of URLs that are allowed everywhere, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="105ef-330">ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-330">Consider adding commonly used internal URLs to the list to improve the user experience.</span></span> <span data-ttu-id="105ef-331">たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="105ef-331">For example, if you have on-premises services, such as Skype for Business or SharePoint, you can add those URLs to exclude them from scanning.</span></span>

- <span data-ttu-id="105ef-332">[セーフ リンク] ポリシーで次の **URL** エントリを書き換えない場合は、リストを確認し、必要に応じてワイルドカードを追加してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-332">If you already have **Do not rewrite the following URLs** entries in your Safe Links policies, be sure to review the lists and add wildcards as required.</span></span> <span data-ttu-id="105ef-333">たとえば、リストには次のようなエントリが含まれるので、後で次のような `https://contoso.com/a` サブパスを含めることにしました `https://contoso.com/a/b` 。</span><span class="sxs-lookup"><span data-stu-id="105ef-333">For example, your list has an entry like `https://contoso.com/a` and you later decide to include subpaths like `https://contoso.com/a/b`.</span></span> <span data-ttu-id="105ef-334">新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、 `https://contoso.com/a/*` になります。</span><span class="sxs-lookup"><span data-stu-id="105ef-334">Instead of adding a new entry, add a wildcard to the existing entry so it becomes `https://contoso.com/a/*`.</span></span>

- <span data-ttu-id="105ef-335">URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="105ef-335">You can include up to three wildcards (`*`) per URL entry.</span></span> <span data-ttu-id="105ef-336">ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="105ef-336">Wildcards explicitly include prefixes or subdomains.</span></span> <span data-ttu-id="105ef-337">たとえば、指定したドメイン内のサブドメインとパスをユーザーがアクセスできるので、エントリは同 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` じではありません。</span><span class="sxs-lookup"><span data-stu-id="105ef-337">For example, the entry `contoso.com` is not the same as `*.contoso.com/*`, because `*.contoso.com/*` allows people to visit subdomains and paths in the specified domain.</span></span>

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a><span data-ttu-id="105ef-338">"次の URL を書き換えない" リストのエントリ構文</span><span class="sxs-lookup"><span data-stu-id="105ef-338">Entry syntax for the "Do not rewrite the following URLs" list</span></span>

<span data-ttu-id="105ef-339">入力できる値とその結果の例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="105ef-339">Examples of the values that you can enter and their results are described in the following table:</span></span>

****

|<span data-ttu-id="105ef-340">値</span><span class="sxs-lookup"><span data-stu-id="105ef-340">Value</span></span>|<span data-ttu-id="105ef-341">結果</span><span class="sxs-lookup"><span data-stu-id="105ef-341">Result</span></span>|
|---|---|
|`contoso.com`|<span data-ttu-id="105ef-342">サブドメインまたは `https://contoso.com` パスへのアクセスを許可しますが、アクセスを許可しない。</span><span class="sxs-lookup"><span data-stu-id="105ef-342">Allows access to `https://contoso.com` but not subdomains or paths.</span></span>|
|`*.contoso.com/*`|<span data-ttu-id="105ef-343">ドメイン、サブドメイン、およびパス (たとえば、) へのアクセス `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` を許可します `https://www.contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="105ef-343">Allows access to a domain, subdomains, and paths (for example, `https://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `https://www.contoso.com/a`).</span></span> <p> <span data-ttu-id="105ef-344">このエントリは、潜在的に詐欺的なサイトを許可しないので、本来よりも `*contoso.com*` 優れた方法 `https://www.falsecontoso.com` です。 `https://www.false.contoso.completelyfalse.com`</span><span class="sxs-lookup"><span data-stu-id="105ef-344">This entry is inherently better than `*contoso.com*`, because it doesn't allow potentially fraudulent sites, like `https://www.falsecontoso.com` or `https://www.false.contoso.completelyfalse.com`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="105ef-345">サブパスへの `https://contoso.com/a` アクセスを許可しますが、サブパスは許可しない `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="105ef-345">Allows access to `https://contoso.com/a`, but not subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a/*`|<span data-ttu-id="105ef-346">次のようなアクセス `https://contoso.com/a` とサブパスを許可します `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="105ef-346">Allows access to `https://contoso.com/a` and subpaths like `https://contoso.com/a/b`</span></span>|
|

## <a name="warning-pages-from-safe-links"></a><span data-ttu-id="105ef-347">セーフ リンクからの警告ページ</span><span class="sxs-lookup"><span data-stu-id="105ef-347">Warning pages from Safe Links</span></span>

<span data-ttu-id="105ef-348">このセクションでは、URL をクリックするとセーフ リンク保護によってトリガーされるさまざまな警告ページの例を示します。</span><span class="sxs-lookup"><span data-stu-id="105ef-348">This section contains examples of the various warning pages that are triggered by Safe Links protection when you click a URL.</span></span>

<span data-ttu-id="105ef-349">いくつかの警告ページが更新された点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="105ef-349">Note that several warning pages have been updated.</span></span> <span data-ttu-id="105ef-350">更新されたページがまだ表示されていない場合は、すぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-350">If you're not already seeing the updated pages, you will soon.</span></span> <span data-ttu-id="105ef-351">更新されたページには、新しい配色、詳細、および指定された警告と推奨事項にもかかわらずサイトに進む機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="105ef-351">The updated pages include a new color scheme, more detail, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="scan-in-progress-notification"></a><span data-ttu-id="105ef-352">進行中の通知をスキャンする</span><span class="sxs-lookup"><span data-stu-id="105ef-352">Scan in progress notification</span></span>

<span data-ttu-id="105ef-353">クリックされた URL は、セーフ リンクによってスキャンされています。</span><span class="sxs-lookup"><span data-stu-id="105ef-353">The clicked URL is being scanned by Safe Links.</span></span> <span data-ttu-id="105ef-354">リンクを再度試す前に、しばらく待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="105ef-354">You might need to wait a few moments before trying the link again.</span></span>

!["リンクがスキャン中" 通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="105ef-356">元の通知ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-356">The original notification page looked like this:</span></span>

![元の "リンクがスキャン中" 通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a><span data-ttu-id="105ef-358">疑わしいメッセージの警告</span><span class="sxs-lookup"><span data-stu-id="105ef-358">Suspicious message warning</span></span>

<span data-ttu-id="105ef-359">クリックされた URL は、他の疑わしいメッセージに似た電子メール メッセージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="105ef-359">The clicked URL was in an email message that's similar to other suspicious messages.</span></span> <span data-ttu-id="105ef-360">サイトに進む前に、電子メール メッセージをもう一度確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="105ef-360">We recommend that you double-check the email message before proceeding to the site.</span></span>

!["疑わしいメッセージからリンクがクリックされました" という警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a><span data-ttu-id="105ef-362">フィッシングの試行の警告</span><span class="sxs-lookup"><span data-stu-id="105ef-362">Phishing attempt warning</span></span>

<span data-ttu-id="105ef-363">クリックされた URL は、フィッシング攻撃として識別された電子メール メッセージに含めでした。</span><span class="sxs-lookup"><span data-stu-id="105ef-363">The clicked URL was in an email message that has been identified as a phishing attack.</span></span> <span data-ttu-id="105ef-364">その結果、電子メール メッセージ内のすべての URL がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="105ef-364">As a result, all URLs in the email message are blocked.</span></span> <span data-ttu-id="105ef-365">サイトに進むのはやめすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="105ef-365">We recommend that you do not proceed to the site.</span></span>

!["フィッシング メッセージからリンクがクリックされました" という警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a><span data-ttu-id="105ef-367">悪意のある Web サイトの警告</span><span class="sxs-lookup"><span data-stu-id="105ef-367">Malicious website warning</span></span>

<span data-ttu-id="105ef-368">クリックされた URL は、悪意のあるサイトをポイントします。</span><span class="sxs-lookup"><span data-stu-id="105ef-368">The clicked URL points to a site that has been identified as malicious.</span></span> <span data-ttu-id="105ef-369">サイトに進むのはやめすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="105ef-369">We recommend that you do not proceed to the site.</span></span>

![「この Web サイトは悪意のある Web サイトに分類されます」という警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="105ef-371">元の警告ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-371">The original warning page looked like this:</span></span>

![元の "この Web サイトは悪意のある Web サイトとして分類されています" という警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="105ef-373">ブロックされた URL の警告</span><span class="sxs-lookup"><span data-stu-id="105ef-373">Blocked URL warning</span></span>

<span data-ttu-id="105ef-374">クリックされた URL は、組織内の管理者によって手動でブロックされています (セーフ リンクのグローバル設定の [次の **URL** をブロックする] リスト)。</span><span class="sxs-lookup"><span data-stu-id="105ef-374">The clicked URL has been manually blocked by an admin in your organization (the **Block the following URLs** list in the global settings for Safe Links).</span></span> <span data-ttu-id="105ef-375">リンクは手動でブロックされたため、セーフ リンクによってスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="105ef-375">The link was not scanned by Safe Links because it was manually blocked.</span></span>

<span data-ttu-id="105ef-376">管理者が特定の URL を手動でブロックする理由は複数あります。</span><span class="sxs-lookup"><span data-stu-id="105ef-376">There are several reasons why an admin would manually block specific URLs.</span></span> <span data-ttu-id="105ef-377">サイトをブロックしない場合は、管理者に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="105ef-377">If you think the site should not be blocked, contact your admin.</span></span>

!["この Web サイトは管理者によってブロックされました" という警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="105ef-379">元の警告ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-379">The original warning page looked like this:</span></span>

![元の "この Web サイトは、組織の URL ポリシーごとにブロックされています" という警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a><span data-ttu-id="105ef-381">エラー警告</span><span class="sxs-lookup"><span data-stu-id="105ef-381">Error warning</span></span>

<span data-ttu-id="105ef-382">何らかのエラーが発生し、URL を開くことができません。</span><span class="sxs-lookup"><span data-stu-id="105ef-382">Some kind of error has occurred, and the URL can't be opened.</span></span>

![「アクセスしようとしているページを読み込め」という警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="105ef-384">元の警告ページは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="105ef-384">The original warning page looked like this:</span></span>

![元の "この Web ページを読み込めない" という警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
