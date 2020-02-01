---
title: Microsoft の脅威保護で、空軍の誤検知または誤検知を報告する方法
description: Microsoft の脅威保護で、何らかの問題があるか、またはエアで誤って検出されましたか? 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
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
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 44c90c6c9394b1f9fee34b8eb068bb7c232c4d78
ms.sourcegitcommit: a6686a68b068adec29b72f998ac9bc95992981df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41627973"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="53937-105">自動調査および応答機能の誤検知/ネガを報告する方法</span><span class="sxs-lookup"><span data-stu-id="53937-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="53937-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="53937-106">**Applies to:**</span></span>
- <span data-ttu-id="53937-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="53937-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="53937-108">Microsoft の脅威保護ミスの自動化された[調査と応答機能](mtp-autoir.md)を、誤って検出しましたか?</span><span class="sxs-lookup"><span data-stu-id="53937-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="53937-109">この問題を解決するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="53937-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="53937-110">以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="53937-110">You can:</span></span>
- <span data-ttu-id="53937-111">[False 正/負の値を Microsoft に報告し](#report-a-false-positivenegative-to-microsoft-for-analysis)ます。</span><span class="sxs-lookup"><span data-stu-id="53937-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="53937-112">[通知を調整し](#adjust-an-alert-to-prevent-false-positives-from-recurring)ます (必要な場合)。そして</span><span class="sxs-lookup"><span data-stu-id="53937-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="53937-113">[デバイスに対して実行された修復操作を元に戻し](#undo-a-remediation-action-that-was-taken-on-a-device)ます。</span><span class="sxs-lookup"><span data-stu-id="53937-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="53937-114">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="53937-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="53937-115">False 正/負の値を分析のために Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="53937-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="53937-116">不在時または誤って検出されたアイテム</span><span class="sxs-lookup"><span data-stu-id="53937-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="53937-117">サービス</span><span class="sxs-lookup"><span data-stu-id="53937-117">Service</span></span>  |<span data-ttu-id="53937-118">行うこと</span><span class="sxs-lookup"><span data-stu-id="53937-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="53937-119">-電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="53937-119">- Email message</span></span> <br/><span data-ttu-id="53937-120">-電子メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="53937-120">- Email attachment</span></span> <br/><span data-ttu-id="53937-121">-電子メールメッセージ内の URL</span><span class="sxs-lookup"><span data-stu-id="53937-121">- URL in an email message</span></span><br/><span data-ttu-id="53937-122">-Office ファイル内の URL</span><span class="sxs-lookup"><span data-stu-id="53937-122">- URL in an Office file</span></span>      |[<span data-ttu-id="53937-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="53937-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="53937-124">迷惑メールの疑いのあるスパム、フィッシング、Url、およびファイルを Office 365 スキャン用に Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="53937-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="53937-125">デバイス上のファイルまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="53937-125">File or app on a device</span></span>    |[<span data-ttu-id="53937-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="53937-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="53937-127">マルウェア分析のために Microsoft にファイルを提出する</span><span class="sxs-lookup"><span data-stu-id="53937-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="53937-128">警告を調整して誤検知が繰り返されないようにする</span><span class="sxs-lookup"><span data-stu-id="53937-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="53937-129">シナリオ</span><span class="sxs-lookup"><span data-stu-id="53937-129">Scenario</span></span> |<span data-ttu-id="53937-130">サービス</span><span class="sxs-lookup"><span data-stu-id="53937-130">Service</span></span> |<span data-ttu-id="53937-131">行うこと</span><span class="sxs-lookup"><span data-stu-id="53937-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="53937-132">-警告が正規の使用によってトリガーされる</span><span class="sxs-lookup"><span data-stu-id="53937-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="53937-133">-警告が正確でない</span><span class="sxs-lookup"><span data-stu-id="53937-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="53937-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="53937-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="53937-135">または</span><span class="sxs-lookup"><span data-stu-id="53937-135">or</span></span> <br/>[<span data-ttu-id="53937-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="53937-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="53937-137">Cloud App Security ポータルで通知を管理する</span><span class="sxs-lookup"><span data-stu-id="53937-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="53937-138">ファイル、IP アドレス、URL、またはドメインが安全であっても、デバイスのマルウェアとして扱われる</span><span class="sxs-lookup"><span data-stu-id="53937-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="53937-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="53937-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="53937-140">"許可" アクションを含むカスタムインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="53937-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="53937-141">デバイスで実行された修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="53937-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="53937-142">修復アクションがデバイス (Windows 10 デバイスなど) に対して実行され、実際にクリーンな状態になっている場合、セキュリティ運用チームは[アクションセンター](mtp-action-center.md)で修復処理を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="53937-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item that is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53937-143">次のタスクを実行する前に、[必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="53937-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="53937-144">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="53937-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="53937-145">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53937-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="53937-146">[**履歴**] タブで、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="53937-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="53937-147">これにより、フライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="53937-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="53937-148">フィルターを使用して、結果の一覧を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="53937-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="53937-149">選択したアイテムのポップアップで、[**調査ページを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53937-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="53937-150">調査の詳細ビューで、[**操作**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="53937-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="53937-151">状態が [**完了**] であるアイテムを選択し、[**判断**] 列に [**承認済み**] などのリンクを探します。</span><span class="sxs-lookup"><span data-stu-id="53937-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="53937-152">これにより、アクションの詳細を含むフライアウトが開きます。</span><span class="sxs-lookup"><span data-stu-id="53937-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="53937-153">アクションを元に戻すには、[**修復の削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53937-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="53937-154">関連記事</span><span class="sxs-lookup"><span data-stu-id="53937-154">Related articles</span></span>

- [<span data-ttu-id="53937-155">自動調査と対応に関連するアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="53937-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="53937-156">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="53937-156">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="53937-157">Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する</span><span class="sxs-lookup"><span data-stu-id="53937-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
