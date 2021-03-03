---
title: 365 の Microsoft Defender での自動調査に続き、誤検知または誤Officeする方法
description: Microsoft Defender の AIR が 365 で検出した、または誤って検出Officeしましたか? 分析のために誤検知または誤検知を Microsoft に提出する方法について説明します。
keywords: 自動化, 調査, アラート, トリガー, アクション, 修復, 誤検知, 偽陰性
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
ms.openlocfilehash: 8a91a55d9598b5e780474315ddf1f7019e593fed
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406164"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="c0321-105">自動調査および応答機能で誤検知/陰性を報告する方法</span><span class="sxs-lookup"><span data-stu-id="c0321-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c0321-106">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c0321-106">**Applies to**</span></span>
- [<span data-ttu-id="c0321-107">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="c0321-107">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c0321-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0321-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c0321-109">[Office 365](automated-investigation-response-office.md)の自動調査と応答 (AIR) 機能が何かを見逃した、または誤って検出した場合は、セキュリティ運用チームがそれを修正するために実行できる手順があります。</span><span class="sxs-lookup"><span data-stu-id="c0321-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="c0321-110">このようなアクションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0321-110">Such actions include:</span></span>

- <span data-ttu-id="c0321-111">[Microsoft に誤検知/陰性を報告する](#report-a-false-positivenegative-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="c0321-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="c0321-112">[アラートの調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (必要な場合)。そして</span><span class="sxs-lookup"><span data-stu-id="c0321-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="c0321-113">[実行された修復アクションの元に戻す](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="c0321-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="c0321-114">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c0321-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="c0321-115">分析のために Microsoft に誤検知/陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="c0321-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="c0321-116">microsoft Defender for Office 365 の AIR が電子メール メッセージ、電子メール添付ファイル、電子メール メッセージ内の URL、または Office ファイル内の URL を見逃した場合は、疑わしいスパム、フィッシング、URL、ファイルを microsoft に送信して、Office [365](admin-submission.md)スキャンを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c0321-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="c0321-117">また、マルウェア [分析のためにファイルを Microsoft に送信できます](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="c0321-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="c0321-118">誤検知が繰り返されるのを防ぐためにアラートを調整する</span><span class="sxs-lookup"><span data-stu-id="c0321-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="c0321-119">アラートが正当な使用によってトリガーされた場合、またはアラートが不正確な場合は、Cloud App Security ポータルでアラート [を管理できます](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="c0321-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="c0321-120">組織で Office 365 に加えて [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) を使用している場合、ファイル、IP アドレス、URL、またはドメインが安全なデバイス上でマルウェアとして扱われる場合は、デバイスの "許可 ["](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)アクションを使用してカスタム インジケーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c0321-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="c0321-121">修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="c0321-121">Undo a remediation action</span></span>

<span data-ttu-id="c0321-122">ほとんどの場合、電子メール メッセージ、電子メール添付ファイル、または URL に対して修復アクションが実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームは修復アクションを元に戻し、誤検知が繰り返されるのを防ぐための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c0321-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="c0321-123">調査に脅威エクスプローラー [または [](#undo-an-action-using-threat-explorer) アクション] タブ [を使用して、アクション](#undo-an-action-in-the-action-center) を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="c0321-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0321-124">次のタスクを実行する前に、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0321-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="c0321-125">Threat Explorer を使用してアクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="c0321-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="c0321-126">Threat Explorer を使用すると、セキュリティ運用チームは、アクションの影響を受ける電子メールを見つけ、アクションを元に戻す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0321-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="c0321-127">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c0321-127">Scenario</span></span>|<span data-ttu-id="c0321-128">元に戻すオプション</span><span class="sxs-lookup"><span data-stu-id="c0321-128">Undo Options</span></span>|<span data-ttu-id="c0321-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c0321-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="c0321-130">電子メール メッセージがユーザーの迷惑メール フォルダーにルーティングされた</span><span class="sxs-lookup"><span data-stu-id="c0321-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="c0321-131">- メッセージをユーザーの [削除済みアイテム] フォルダーに移動する</span><span class="sxs-lookup"><span data-stu-id="c0321-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="c0321-132">- メッセージをユーザーの受信トレイに移動する</span><span class="sxs-lookup"><span data-stu-id="c0321-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="c0321-133">- メッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="c0321-133">- Delete the message</span></span>|[<span data-ttu-id="c0321-134">365 で配信された悪意のある電子メールをOfficeする</span><span class="sxs-lookup"><span data-stu-id="c0321-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="c0321-135">電子メール メッセージまたはファイルが検疫された</span><span class="sxs-lookup"><span data-stu-id="c0321-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="c0321-136">- 電子メールまたはファイルを解放する</span><span class="sxs-lookup"><span data-stu-id="c0321-136">- Release the email or file</span></span><br/><span data-ttu-id="c0321-137">- 電子メールまたはファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="c0321-137">- Delete the email or file</span></span>|[<span data-ttu-id="c0321-138">検疫済みメッセージを管理者として管理する</span><span class="sxs-lookup"><span data-stu-id="c0321-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="c0321-139">アクション センターで操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="c0321-139">Undo an action in the Action center</span></span>

<span data-ttu-id="c0321-140">アクション センターでは、実行された修復アクションを確認し、アクションを元に戻す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0321-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="c0321-141">Microsoft 365 セキュリティ センター ( ) に移動します <https://security.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c0321-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="c0321-142">ナビゲーション ウィンドウで、[アクション センター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c0321-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="c0321-143">[履歴] **タブを** 選択して、完了したアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0321-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="c0321-144">アイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0321-144">Select an item.</span></span> <span data-ttu-id="c0321-145">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c0321-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="c0321-146">フライアウト ウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c0321-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="c0321-147">(元に戻す操作のみ[元に戻 **す]** ボタンがあります)。</span><span class="sxs-lookup"><span data-stu-id="c0321-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="c0321-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0321-148">See also</span></span>

- [<span data-ttu-id="c0321-149">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c0321-149">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="c0321-150">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="c0321-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
