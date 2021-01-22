---
title: Microsoft 365 Defender で AIR で誤検知または検出検出を処理する
description: Microsoft 365 Defender で AIR によって何かが見つからないか、誤って検出されましたか? 分析のために誤検知または検出検出を Microsoft に送信する方法について説明します。
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
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930356"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="59fe0-105">自動調査および対応機能で誤検知/陰性を処理する</span><span class="sxs-lookup"><span data-stu-id="59fe0-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59fe0-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="59fe0-106">**Applies to:**</span></span>
- <span data-ttu-id="59fe0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fe0-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="59fe0-108">Microsoft [](mtp-autoir.md) 365 Defender の自動調査および対応機能は、何かを検出したのか、間違って検出されましたか?</span><span class="sxs-lookup"><span data-stu-id="59fe0-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="59fe0-109">この問題を解決するには、次の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="59fe0-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="59fe0-110">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="59fe0-110">You can:</span></span>

- <span data-ttu-id="59fe0-111">[誤検知/陰性を Microsoft に報告します](#report-a-false-positivenegative-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="59fe0-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="59fe0-112">[アラートを調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) する (必要な場合)。そして</span><span class="sxs-lookup"><span data-stu-id="59fe0-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="59fe0-113">[デバイスで実行された修復操作を元に戻します](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="59fe0-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="59fe0-114">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="59fe0-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="59fe0-115">誤検知/陰性を分析のために Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="59fe0-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="59fe0-116">アイテムが見つからないか誤って検出された</span><span class="sxs-lookup"><span data-stu-id="59fe0-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="59fe0-117">サービス</span><span class="sxs-lookup"><span data-stu-id="59fe0-117">Service</span></span>  |<span data-ttu-id="59fe0-118">操作</span><span class="sxs-lookup"><span data-stu-id="59fe0-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="59fe0-119">- 電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="59fe0-119">- Email message</span></span> <br/><span data-ttu-id="59fe0-120">- 電子メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="59fe0-120">- Email attachment</span></span> <br/><span data-ttu-id="59fe0-121">- 電子メール メッセージの URL</span><span class="sxs-lookup"><span data-stu-id="59fe0-121">- URL in an email message</span></span><br/><span data-ttu-id="59fe0-122">- ファイル内Office URL</span><span class="sxs-lookup"><span data-stu-id="59fe0-122">- URL in an Office file</span></span>      |[<span data-ttu-id="59fe0-123">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="59fe0-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="59fe0-124">疑わしいスパム、フィッシング、URL、ファイルをスキャンのために Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="59fe0-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="59fe0-125">デバイス上のファイルまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="59fe0-125">File or app on a device</span></span>    |[<span data-ttu-id="59fe0-126">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="59fe0-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="59fe0-127">マルウェア分析のために Microsoft にファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="59fe0-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="59fe0-128">誤検知が繰り返されるのを防ぐためにアラートを調整する</span><span class="sxs-lookup"><span data-stu-id="59fe0-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="59fe0-129">シナリオ</span><span class="sxs-lookup"><span data-stu-id="59fe0-129">Scenario</span></span> |<span data-ttu-id="59fe0-130">サービス</span><span class="sxs-lookup"><span data-stu-id="59fe0-130">Service</span></span> |<span data-ttu-id="59fe0-131">操作</span><span class="sxs-lookup"><span data-stu-id="59fe0-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="59fe0-132">- アラートは正当な使用によってトリガーされます</span><span class="sxs-lookup"><span data-stu-id="59fe0-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="59fe0-133">- アラートが不正確</span><span class="sxs-lookup"><span data-stu-id="59fe0-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="59fe0-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="59fe0-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="59fe0-135">または</span><span class="sxs-lookup"><span data-stu-id="59fe0-135">or</span></span> <br/>[<span data-ttu-id="59fe0-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="59fe0-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="59fe0-137">Cloud App Security ポータルでアラートを管理する</span><span class="sxs-lookup"><span data-stu-id="59fe0-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="59fe0-138">ファイル、IP アドレス、URL、またはドメインは、安全なデバイスではマルウェアとして扱われる</span><span class="sxs-lookup"><span data-stu-id="59fe0-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="59fe0-139">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="59fe0-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="59fe0-140">"許可" アクションを使用してカスタム インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="59fe0-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="59fe0-141">デバイスで実行された修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="59fe0-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="59fe0-142">修復アクションがデバイス (Windows 10 デバイスなど) で実行され、アイテムが実際には脅威ではない場合、セキュリティ運用チームはアクション センターで修復アクションを元に戻[すことができます。](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="59fe0-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59fe0-143">次のタスクを実行 [する前に](mtp-action-center.md#required-permissions-for-action-center-tasks) 、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59fe0-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="59fe0-144">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="59fe0-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="59fe0-145">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="59fe0-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="59fe0-146">[履歴 **]** タブで、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="59fe0-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="59fe0-147">これにより、フライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="59fe0-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="59fe0-148">フィルターを使用して結果の一覧を絞り込む。</span><span class="sxs-lookup"><span data-stu-id="59fe0-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="59fe0-149">選択した項目のフライアウトで、[調査ページを開く] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59fe0-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="59fe0-150">調査の詳細ビューで、[操作] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="59fe0-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="59fe0-151">状態が [完了]のアイテムを選択し、[決定] 列で[承認済み] などのリンク **を探** します。</span><span class="sxs-lookup"><span data-stu-id="59fe0-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="59fe0-152">これにより、アクションの詳細を含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="59fe0-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="59fe0-153">操作を元に戻すには、[修復の削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59fe0-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="59fe0-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="59fe0-154">See also</span></span>

- [<span data-ttu-id="59fe0-155">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="59fe0-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="59fe0-156">Microsoft 365 Defender で高度な検索を使用して脅威を事前に探す</span><span class="sxs-lookup"><span data-stu-id="59fe0-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
