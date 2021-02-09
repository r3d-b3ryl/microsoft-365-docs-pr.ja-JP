---
title: Microsoft Defender での 365 年の自動調査に続き、誤検知または検出Officeする方法
description: Microsoft Defender for Office 365 で AIR によって検出された何かが見つからないか、誤って検出されましたか? 分析のために誤検知または検出検出を Microsoft に送信する方法について説明します。
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 誤検知, 検出検出
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142983"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="8d25e-105">自動調査および対応機能で誤検知/陰性を報告する方法</span><span class="sxs-lookup"><span data-stu-id="8d25e-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="8d25e-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8d25e-106">**Applies to:**</span></span>
- <span data-ttu-id="8d25e-107">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8d25e-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8d25e-108">[Office 365](automated-investigation-response-office.md)の自動調査および対応 (AIR) 機能で何かが見つからないか誤って検出された場合は、セキュリティ運用チームが問題を解決するために実行できる手順があります。</span><span class="sxs-lookup"><span data-stu-id="8d25e-108">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="8d25e-109">このようなアクションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d25e-109">Such actions include:</span></span>

- <span data-ttu-id="8d25e-110">[Microsoft に誤検知/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="8d25e-110">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="8d25e-111">[アラートの調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合)そして</span><span class="sxs-lookup"><span data-stu-id="8d25e-111">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="8d25e-112">[実行された修復アクションを元に戻す](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="8d25e-112">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="8d25e-113">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="8d25e-113">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="8d25e-114">誤検知/陰性を分析のために Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="8d25e-114">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="8d25e-115">Office 365 用 Microsoft Defender の AIR が電子メール メッセージ、電子メール添付ファイル、電子メール メッセージ内の URL、または Office ファイル内の URL を見逃した場合は、スパム、フィッシング、URL、ファイルの疑いがあるファイルを [Office 365](admin-submission.md)スキャンのために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="8d25e-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="8d25e-116">マルウェア分析のために [Microsoft にファイルを送信することができます](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="8d25e-116">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="8d25e-117">誤検知が繰り返されるのを防ぐためにアラートを調整する</span><span class="sxs-lookup"><span data-stu-id="8d25e-117">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="8d25e-118">警告が正当な使用によってトリガーされた場合、またはアラートが不正確な場合は、Cloud App Security ポータルでアラート [を管理できます](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="8d25e-118">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="8d25e-119">組織で Office 365 に加えて [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) を使用している場合、安全なデバイスでもファイル、IP アドレス、URL、またはドメインがマルウェアとして扱われる場合は、デバイスに対して "許可 ["](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)アクションを使用してカスタム インジケーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8d25e-119">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="8d25e-120">修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="8d25e-120">Undo a remediation action</span></span>

<span data-ttu-id="8d25e-121">ほとんどの場合、メール メッセージ、電子メールの添付ファイル、または URL に対して修復アクションが実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームは修復アクションを元に戻し、誤検知が繰り返し発生しなからなされるのを防ぐための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d25e-121">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="8d25e-122">脅威エクスプローラーまたは [ [操作]](#undo-an-action-using-threat-explorer) タブを使用して調査を [行](#undo-an-action-in-the-action-center) い、操作を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="8d25e-122">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d25e-123">次のタスクを実行する前に、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d25e-123">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="8d25e-124">脅威エクスプローラーを使用して操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="8d25e-124">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="8d25e-125">脅威エクスプローラーを使用すると、セキュリティ運用チームはアクションの影響を受ける電子メールを見つけ、操作を元に戻す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d25e-125">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="8d25e-126">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8d25e-126">Scenario</span></span>|<span data-ttu-id="8d25e-127">元に戻すオプション</span><span class="sxs-lookup"><span data-stu-id="8d25e-127">Undo Options</span></span>|<span data-ttu-id="8d25e-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8d25e-128">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="8d25e-129">電子メール メッセージがユーザーの迷惑メール フォルダーにルーティングされた</span><span class="sxs-lookup"><span data-stu-id="8d25e-129">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="8d25e-130">- メッセージをユーザーの [削除済みアイテム] フォルダーに移動する</span><span class="sxs-lookup"><span data-stu-id="8d25e-130">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="8d25e-131">- メッセージをユーザーの受信トレイに移動する</span><span class="sxs-lookup"><span data-stu-id="8d25e-131">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="8d25e-132">- メッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="8d25e-132">- Delete the message</span></span>|[<span data-ttu-id="8d25e-133">Office 365 で配信された悪意のあるメールを検索して調査する</span><span class="sxs-lookup"><span data-stu-id="8d25e-133">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="8d25e-134">メール メッセージまたはファイルが検疫された</span><span class="sxs-lookup"><span data-stu-id="8d25e-134">An email message or a file was quarantined</span></span>|<span data-ttu-id="8d25e-135">- 電子メールまたはファイルを解放する</span><span class="sxs-lookup"><span data-stu-id="8d25e-135">- Release the email or file</span></span><br/><span data-ttu-id="8d25e-136">- メールまたはファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="8d25e-136">- Delete the email or file</span></span>|[<span data-ttu-id="8d25e-137">管理者として検疫済みメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="8d25e-137">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="8d25e-138">アクション センターで操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="8d25e-138">Undo an action in the Action center</span></span>

<span data-ttu-id="8d25e-139">アクション センターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d25e-139">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="8d25e-140">Microsoft 365 セキュリティ センター ( ) に移動します [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="8d25e-140">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="8d25e-141">ナビゲーション ウィンドウで、アクション センターを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d25e-141">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="8d25e-142">完了したアクション **の** 一覧を表示するには、[履歴] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d25e-142">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="8d25e-143">アイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d25e-143">Select an item.</span></span> <span data-ttu-id="8d25e-144">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="8d25e-144">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="8d25e-145">フライアウト ウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d25e-145">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="8d25e-146">(元に戻す操作のみを元に戻すボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="8d25e-146">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="8d25e-147">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="8d25e-147">See also</span></span>

- [<span data-ttu-id="8d25e-148">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8d25e-148">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="8d25e-149">Microsoft Defender for Office 365 での自動調査</span><span class="sxs-lookup"><span data-stu-id="8d25e-149">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
