---
title: ユーザーの誤検知または誤検知に対処Microsoft 365 Defender
description: AIR によって検出された、または誤って検出されたMicrosoft 365 Defender? 分析のために誤検知または誤検知を Microsoft に提出する方法について説明します。
keywords: 自動化、調査、アラート、修復、誤検知、偽陰性
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022536"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="1bde8-105">ユーザーの誤検知または誤検知に対処Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bde8-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1bde8-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1bde8-106">**Applies to:**</span></span>
- <span data-ttu-id="1bde8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bde8-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="1bde8-108">脅威保護ソリューションでは、誤検知や陰性が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1bde8-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="1bde8-109">自動[調査および応答](m365d-autoir.md)機能がMicrosoft 365 Defenderまたは誤って検出された場合、セキュリティ運用チームが実行できる手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1bde8-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="1bde8-110">Microsoft に誤検知/陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="1bde8-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="1bde8-111">[アラートを調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) する (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="1bde8-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="1bde8-112">デバイスで実行された修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="1bde8-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="1bde8-113">以下のセクションでは、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bde8-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="1bde8-114">分析のために Microsoft に誤検知/陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="1bde8-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="1bde8-115">アイテムが見つからないか、誤って検出された</span><span class="sxs-lookup"><span data-stu-id="1bde8-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="1bde8-116">サービス</span><span class="sxs-lookup"><span data-stu-id="1bde8-116">Service</span></span>  |<span data-ttu-id="1bde8-117">操作</span><span class="sxs-lookup"><span data-stu-id="1bde8-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="1bde8-118">- 電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="1bde8-118">- Email message</span></span> <br/><span data-ttu-id="1bde8-119">- メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="1bde8-119">- Email attachment</span></span> <br/><span data-ttu-id="1bde8-120">- 電子メール メッセージの URL</span><span class="sxs-lookup"><span data-stu-id="1bde8-120">- URL in an email message</span></span><br/><span data-ttu-id="1bde8-121">- ファイル内の URL Officeファイル</span><span class="sxs-lookup"><span data-stu-id="1bde8-121">- URL in an Office file</span></span>      |[<span data-ttu-id="1bde8-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="1bde8-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="1bde8-123">疑わしいスパム、フィッシング、URL、ファイルをスキャンのために Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="1bde8-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="1bde8-124">デバイス上のファイルまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="1bde8-124">File or app on a device</span></span>    |[<span data-ttu-id="1bde8-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1bde8-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="1bde8-126">マルウェア分析のために Microsoft にファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="1bde8-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="1bde8-127">誤検知が繰り返されるのを防ぐためにアラートを調整する</span><span class="sxs-lookup"><span data-stu-id="1bde8-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="1bde8-128">シナリオ</span><span class="sxs-lookup"><span data-stu-id="1bde8-128">Scenario</span></span> |<span data-ttu-id="1bde8-129">サービス</span><span class="sxs-lookup"><span data-stu-id="1bde8-129">Service</span></span> |<span data-ttu-id="1bde8-130">操作</span><span class="sxs-lookup"><span data-stu-id="1bde8-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="1bde8-131">- アラートは正当な使用によってトリガーされます</span><span class="sxs-lookup"><span data-stu-id="1bde8-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="1bde8-132">- アラートが不正確</span><span class="sxs-lookup"><span data-stu-id="1bde8-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="1bde8-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1bde8-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="1bde8-134">または</span><span class="sxs-lookup"><span data-stu-id="1bde8-134">or</span></span> <br/>[<span data-ttu-id="1bde8-135">Azure の脅威保護</span><span class="sxs-lookup"><span data-stu-id="1bde8-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="1bde8-136">ポータルでアラートをCloud App Securityする</span><span class="sxs-lookup"><span data-stu-id="1bde8-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="1bde8-137">ファイル、IP アドレス、URL、またはドメインは、安全なデバイス上のマルウェアとして扱われる</span><span class="sxs-lookup"><span data-stu-id="1bde8-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="1bde8-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1bde8-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="1bde8-139">"許可" アクションを使用してカスタム インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="1bde8-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="1bde8-140">デバイスで実行された修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="1bde8-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="1bde8-141">エンティティ (デバイスや電子メール メッセージなど) に対して修復アクションが実行され、影響を受けるエンティティが実際には脅威ではない場合、セキュリティ運用チームはアクション センターで修復[](m365d-action-center.md)アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="1bde8-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="1bde8-142">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="1bde8-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="1bde8-143">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bde8-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="1bde8-144">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="1bde8-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="1bde8-145">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="1bde8-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="1bde8-146">フライアウト ウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1bde8-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="1bde8-147">「完了 [した操作を元に戻す」を参照してください](m365d-autoir-actions.md#undo-completed-actions)。</span><span class="sxs-lookup"><span data-stu-id="1bde8-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="1bde8-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bde8-148">See also</span></span>

- [<span data-ttu-id="1bde8-149">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="1bde8-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="1bde8-150">高度な検索機能を使用して、脅威を事前に検出Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bde8-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
