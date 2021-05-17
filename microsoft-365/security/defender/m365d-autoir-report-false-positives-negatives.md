---
title: Defender で誤検知または誤検知に対処Microsoft 365する
description: Defender の AIR で何かが見つからないか、誤Microsoft 365されましたか? 分析のために誤検知または誤検知を Microsoft に提出する方法について説明します。
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
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269580"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="451cd-105">Defender で誤検知または誤検知に対処Microsoft 365する</span><span class="sxs-lookup"><span data-stu-id="451cd-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="451cd-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="451cd-106">**Applies to:**</span></span>
- <span data-ttu-id="451cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="451cd-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="451cd-108">脅威保護ソリューションでは、誤検知や陰性が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="451cd-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="451cd-109">Defender[の自動調査と対応機能](m365d-autoir.md)がMicrosoft 365検出された場合、セキュリティ運用チームが実行できる手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="451cd-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="451cd-110">Microsoft に誤検知/陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="451cd-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="451cd-111">[アラートを調整](#adjust-an-alert-to-prevent-false-positives-from-recurring) する (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="451cd-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="451cd-112">デバイスで実行された修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="451cd-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="451cd-113">以下のセクションでは、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="451cd-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="451cd-114">分析のために Microsoft に誤検知/陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="451cd-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="451cd-115">アイテムが見つからないか、誤って検出された</span><span class="sxs-lookup"><span data-stu-id="451cd-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="451cd-116">サービス</span><span class="sxs-lookup"><span data-stu-id="451cd-116">Service</span></span>  |<span data-ttu-id="451cd-117">操作</span><span class="sxs-lookup"><span data-stu-id="451cd-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="451cd-118">- 電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="451cd-118">- Email message</span></span> <br/><span data-ttu-id="451cd-119">- メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="451cd-119">- Email attachment</span></span> <br/><span data-ttu-id="451cd-120">- 電子メール メッセージの URL</span><span class="sxs-lookup"><span data-stu-id="451cd-120">- URL in an email message</span></span><br/><span data-ttu-id="451cd-121">- ファイル内の URL Officeファイル</span><span class="sxs-lookup"><span data-stu-id="451cd-121">- URL in an Office file</span></span>      |[<span data-ttu-id="451cd-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="451cd-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="451cd-123">疑わしいスパム、フィッシング、URL、ファイルをスキャンのために Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="451cd-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="451cd-124">デバイス上のファイルまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="451cd-124">File or app on a device</span></span>    |[<span data-ttu-id="451cd-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="451cd-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="451cd-126">マルウェア分析のために Microsoft にファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="451cd-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="451cd-127">誤検知が繰り返されるのを防ぐためにアラートを調整する</span><span class="sxs-lookup"><span data-stu-id="451cd-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="451cd-128">シナリオ</span><span class="sxs-lookup"><span data-stu-id="451cd-128">Scenario</span></span> |<span data-ttu-id="451cd-129">サービス</span><span class="sxs-lookup"><span data-stu-id="451cd-129">Service</span></span> |<span data-ttu-id="451cd-130">操作</span><span class="sxs-lookup"><span data-stu-id="451cd-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="451cd-131">- アラートは正当な使用によってトリガーされます</span><span class="sxs-lookup"><span data-stu-id="451cd-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="451cd-132">- アラートが不正確</span><span class="sxs-lookup"><span data-stu-id="451cd-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="451cd-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="451cd-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="451cd-134">または</span><span class="sxs-lookup"><span data-stu-id="451cd-134">or</span></span> <br/>[<span data-ttu-id="451cd-135">Azure の脅威保護</span><span class="sxs-lookup"><span data-stu-id="451cd-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="451cd-136">ポータルでアラートをCloud App Securityする</span><span class="sxs-lookup"><span data-stu-id="451cd-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="451cd-137">ファイル、IP アドレス、URL、またはドメインは、安全なデバイス上のマルウェアとして扱われる</span><span class="sxs-lookup"><span data-stu-id="451cd-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="451cd-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="451cd-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="451cd-139">"許可" アクションを使用してカスタム インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="451cd-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="451cd-140">デバイスで実行された修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="451cd-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="451cd-141">エンティティ (デバイスや電子メール メッセージなど) に対して修復アクションが実行され、影響を受けるエンティティが実際には脅威ではない場合、セキュリティ運用チームはアクション センターで修復[](m365d-action-center.md)アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="451cd-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="451cd-142">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="451cd-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="451cd-143">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="451cd-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="451cd-144">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="451cd-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="451cd-145">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="451cd-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="451cd-146">フライアウト ウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="451cd-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="451cd-147">「完了 [した操作を元に戻す」を参照してください](m365d-autoir-actions.md#undo-completed-actions)。</span><span class="sxs-lookup"><span data-stu-id="451cd-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="451cd-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="451cd-148">See also</span></span>

- [<span data-ttu-id="451cd-149">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="451cd-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="451cd-150">Defender で高度な狩猟を行って脅威を積極的にMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="451cd-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="451cd-151">Microsoft Defender for Endpoint での誤検出/検出漏れに対処する</span><span class="sxs-lookup"><span data-stu-id="451cd-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)