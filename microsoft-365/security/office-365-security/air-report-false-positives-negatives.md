---
title: Microsoft Defender for Office 365 で自動調査を行った後の誤検知または誤否定を報告する方法
description: Office 365 の Microsoft Defender で、何らかの問題があるか、空軍によって誤って検出されましたか? 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
keywords: 自動化、調査、警告、トリガー、アクション、修復、誤検知、false 負
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: fa6b4ae03a3cf62398a270d65a29e6b4c955173a
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308934"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="fab36-105">自動調査および応答機能の誤検知/ネガを報告する方法</span><span class="sxs-lookup"><span data-stu-id="fab36-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fab36-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fab36-106">**Applies to:**</span></span>
- <span data-ttu-id="fab36-107">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="fab36-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="fab36-108">[Office 365 ミスの自動化された調査と応答 (AIR) 機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)が、誤って検出されたのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="fab36-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="fab36-109">この問題を解決するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fab36-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="fab36-110">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fab36-110">You can:</span></span>
- <span data-ttu-id="fab36-111">[False 正/負の値を Microsoft に報告し](#report-a-false-positivenegative-to-microsoft-for-analysis)ます。</span><span class="sxs-lookup"><span data-stu-id="fab36-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="fab36-112">[通知を調整し](#adjust-an-alert-to-prevent-false-positives-from-recurring) ます (必要な場合)。そして</span><span class="sxs-lookup"><span data-stu-id="fab36-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="fab36-113">[実行された修復操作を元に戻し](#undo-a-remediation-action)ます。</span><span class="sxs-lookup"><span data-stu-id="fab36-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="fab36-114">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="fab36-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="fab36-115">False 正/負の値を分析のために Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="fab36-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="fab36-116">Microsoft Defender for Office 365 で、電子メールメッセージ、電子メールの添付ファイル、電子メールメッセージ内の URL、または Office ファイルの URL のいずれかが失われた場合は、 [フィッシング、url、およびファイルを microsoft For office 365 のスキャンに送信](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)できます。</span><span class="sxs-lookup"><span data-stu-id="fab36-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="fab36-117">また [、マルウェア分析のために Microsoft にファイルを送信](https://www.microsoft.com/wdsi/filesubmission)することもできます。</span><span class="sxs-lookup"><span data-stu-id="fab36-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="fab36-118">警告を調整して誤検知が繰り返されないようにする</span><span class="sxs-lookup"><span data-stu-id="fab36-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="fab36-119">正当な使用によって警告がトリガーされた場合、または警告が不正確な場合は、 [Cloud App Security ポータルで通知を管理](https://docs.microsoft.com/cloud-app-security/managing-alerts)できます。</span><span class="sxs-lookup"><span data-stu-id="fab36-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="fab36-120">Office 365 に加えて、 [エンドポイントに Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) を使用している組織で、ファイル、IP アドレス、URL、またはドメインがデバイスでマルウェアとして扱われている場合は、そのデバイス [の "許可" アクションを使用してカスタムインジケーターを作成](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)できます。</span><span class="sxs-lookup"><span data-stu-id="fab36-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="fab36-121">修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="fab36-121">Undo a remediation action</span></span>

<span data-ttu-id="fab36-122">ほとんどの場合、ウイルス対策アクションが電子メールメッセージ、電子メールの添付ファイル、または URL に対して実行され、そのアイテムが実際には脅威ではない場合、セキュリティ操作チームは修復アクションを取り消すことができ、誤検知が定期的に行われないようにするための手順を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fab36-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="fab36-123">操作を取り消すには、 [脅威エクスプローラー](#undo-an-action-using-threat-explorer) または [ [操作] タブ](#undo-an-action-using-the-actions-tab-for-an-investigation) を使用して調査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fab36-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="fab36-124">次のタスクを実行する前に、必要なアクセス許可があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fab36-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="fab36-125">脅威エクスプローラーを使用してアクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="fab36-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="fab36-126">脅威エクスプローラーを使用すると、セキュリティ運用チームは、アクションによって影響を受ける電子メールを検索し、アクションを元に戻す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fab36-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="fab36-127">シナリオ</span><span class="sxs-lookup"><span data-stu-id="fab36-127">Scenario</span></span>|<span data-ttu-id="fab36-128">元に戻すオプション</span><span class="sxs-lookup"><span data-stu-id="fab36-128">Undo Options</span></span>|<span data-ttu-id="fab36-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fab36-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="fab36-130">電子メールメッセージがユーザーの迷惑メールフォルダーにルーティングされた</span><span class="sxs-lookup"><span data-stu-id="fab36-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="fab36-131">-ユーザーの削除済みアイテムフォルダーにメッセージを移動する</span><span class="sxs-lookup"><span data-stu-id="fab36-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="fab36-132">-ユーザーの受信トレイにメッセージを移動する</span><span class="sxs-lookup"><span data-stu-id="fab36-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="fab36-133">-メッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="fab36-133">- Delete the message</span></span>|[<span data-ttu-id="fab36-134">Office 365 で配信された悪意のある電子メールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="fab36-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="fab36-135">電子メールメッセージまたはファイルが検疫された</span><span class="sxs-lookup"><span data-stu-id="fab36-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="fab36-136">-電子メールまたはファイルを解放します。</span><span class="sxs-lookup"><span data-stu-id="fab36-136">- Release the email or file</span></span> <br/><span data-ttu-id="fab36-137">-電子メールまたはファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="fab36-137">- Delete the email or file</span></span>|[<span data-ttu-id="fab36-138">Office 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="fab36-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="fab36-139">[操作] タブを使用して、調査を行うアクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="fab36-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="fab36-140">アクションセンターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fab36-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="fab36-141">[https://protection.office.com](https://protection.office.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="fab36-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="fab36-142">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fab36-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="fab36-143">[**脅威管理**  >  の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fab36-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="fab36-144">調査の一覧で、アイテムの ID の横にある [ **新しいウィンドウで開く** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="fab36-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="fab36-145">[ **操作** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="fab36-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="fab36-146">状態が [**完了**] であるアイテムを選択し、[**判断**] 列で [**承認済み**] などのリンクを探します。</span><span class="sxs-lookup"><span data-stu-id="fab36-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="fab36-147">これにより、アクションの詳細を含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="fab36-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="fab36-148">アクションを元に戻すには、[ **修復の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fab36-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fab36-149">関連記事</span><span class="sxs-lookup"><span data-stu-id="fab36-149">Related articles</span></span>

[<span data-ttu-id="fab36-150">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="fab36-150">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="fab36-151">Microsoft Defender for Office 365 の空気</span><span class="sxs-lookup"><span data-stu-id="fab36-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
