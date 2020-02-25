---
title: Microsoft の脅威保護で自動調査を行った後の修復アクション
description: Microsoft の脅威保護で自動化された調査に従う修復アクションの概要を理解する
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266053"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="3c3c2-104">Microsoft の脅威保護で自動調査を行った後の修復アクション</span><span class="sxs-lookup"><span data-stu-id="3c3c2-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="3c3c2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3c3c2-105">**Applies to:**</span></span>
- <span data-ttu-id="3c3c2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3c3c2-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="3c3c2-107">修復アクション</span><span class="sxs-lookup"><span data-stu-id="3c3c2-107">Remediation actions</span></span>

<span data-ttu-id="3c3c2-108">Microsoft の脅威保護の自動化された調査の最中および実行後に、修復アクションは悪意のあるアイテムまたは疑わしいアイテムに対して識別されます。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="3c3c2-109">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="3c3c2-110">その他の修復アクションは、電子メールコンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="3c3c2-111">修復アクションが実行、承認、または拒否された後、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="3c3c2-112">次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="3c3c2-113">デバイス (エンドポイント) の修復アクション</span><span class="sxs-lookup"><span data-stu-id="3c3c2-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="3c3c2-114">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="3c3c2-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="3c3c2-115">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="3c3c2-115">Quarantine file</span></span><br/><span data-ttu-id="3c3c2-116">レジストリ キーの削除</span><span class="sxs-lookup"><span data-stu-id="3c3c2-116">Remove registry key</span></span><br/><span data-ttu-id="3c3c2-117">プロセスの強制終了</span><span class="sxs-lookup"><span data-stu-id="3c3c2-117">Kill process</span></span> <br/><span data-ttu-id="3c3c2-118">サービスの停止</span><span class="sxs-lookup"><span data-stu-id="3c3c2-118">Stop service</span></span> <br/><span data-ttu-id="3c3c2-119">ドライバーの無効化</span><span class="sxs-lookup"><span data-stu-id="3c3c2-119">Disable driver</span></span> <br/><span data-ttu-id="3c3c2-120">スケジュールされたタスクの実行</span><span class="sxs-lookup"><span data-stu-id="3c3c2-120">Remove scheduled task</span></span>      |<span data-ttu-id="3c3c2-121">メール メッセージまたはクラスターの論理的な削除</span><span class="sxs-lookup"><span data-stu-id="3c3c2-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="3c3c2-122">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="3c3c2-123">外部メール転送の無効化</span><span class="sxs-lookup"><span data-stu-id="3c3c2-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="3c3c2-124">修復が保留になっているか、既に完了しているかにかかわらず、[アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="3c3c2-125">自動調査に続く Verdicts と結果</span><span class="sxs-lookup"><span data-stu-id="3c3c2-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="3c3c2-126">自動調査が完了すると、関係するすべての証拠について判定が行われ、修復アクションが特定されます。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="3c3c2-127">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="3c3c2-128">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="3c3c2-129">判定</span><span class="sxs-lookup"><span data-stu-id="3c3c2-129">Verdict</span></span>    |<span data-ttu-id="3c3c2-130">分野</span><span class="sxs-lookup"><span data-stu-id="3c3c2-130">Area</span></span>   |<span data-ttu-id="3c3c2-131">結果</span><span class="sxs-lookup"><span data-stu-id="3c3c2-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="3c3c2-132">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-132">Malicious</span></span>  |<span data-ttu-id="3c3c2-133">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-133">Devices (endpoints)</span></span>    |<span data-ttu-id="3c3c2-134">修復アクションが自動的に実行されます</span><span class="sxs-lookup"><span data-stu-id="3c3c2-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="3c3c2-135">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-135">Malicious</span></span>  |<span data-ttu-id="3c3c2-136">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="3c3c2-137">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="3c3c2-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="3c3c2-138">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-138">Suspicious</span></span> |<span data-ttu-id="3c3c2-139">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="3c3c2-139">Devices or email content</span></span> |<span data-ttu-id="3c3c2-140">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="3c3c2-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="3c3c2-141">Clean (クリーン)</span><span class="sxs-lookup"><span data-stu-id="3c3c2-141">Clean</span></span>  |<span data-ttu-id="3c3c2-142">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="3c3c2-142">Devices or email content</span></span>   |<span data-ttu-id="3c3c2-143">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="3c3c2-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="3c3c2-144">保留中のアクションをアクション センターで確認する</span><span class="sxs-lookup"><span data-stu-id="3c3c2-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="3c3c2-145">Microsoft の脅威保護の自動化された調査と応答機能によって何かが失敗したか、誤って検出されたと思われる場合は、お知らせください。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="3c3c2-146">[誤検知/ネガを報告](mtp-autoir-report-false-positives-negatives.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c3c2-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c3c2-147">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3c3c2-147">Next steps</span></span>

- [<span data-ttu-id="3c3c2-148">アクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="3c3c2-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="3c3c2-149">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="3c3c2-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
