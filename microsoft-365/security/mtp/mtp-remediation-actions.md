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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502939"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="2c213-104">Microsoft の脅威保護で自動調査を行った後の修復アクション</span><span class="sxs-lookup"><span data-stu-id="2c213-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="2c213-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2c213-105">**Applies to:**</span></span>
- <span data-ttu-id="2c213-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2c213-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="2c213-107">修復アクション</span><span class="sxs-lookup"><span data-stu-id="2c213-107">Remediation actions</span></span>

<span data-ttu-id="2c213-108">Microsoft の脅威保護の自動化された調査の最中および実行後に、修復アクションは悪意のあるアイテムまたは疑わしいアイテムに対して識別されます。</span><span class="sxs-lookup"><span data-stu-id="2c213-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="2c213-109">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2c213-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="2c213-110">その他の修復アクションは、電子メールコンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="2c213-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="2c213-111">修復アクションが実行、承認、または拒否された後、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="2c213-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="2c213-112">次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2c213-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="2c213-113">デバイス (エンドポイント) の修復アクション</span><span class="sxs-lookup"><span data-stu-id="2c213-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="2c213-114">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="2c213-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="2c213-115">-調査パッケージを収集する</span><span class="sxs-lookup"><span data-stu-id="2c213-115">- Collect investigation package</span></span> <br/><span data-ttu-id="2c213-116">-分離デバイス (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="2c213-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="2c213-117">-オフボードマシン</span><span class="sxs-lookup"><span data-stu-id="2c213-117">- Offboard machine</span></span> <br/><span data-ttu-id="2c213-118">-リリースコードの実行</span><span class="sxs-lookup"><span data-stu-id="2c213-118">- Release code execution</span></span> <br/><span data-ttu-id="2c213-119">-検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="2c213-119">- Release from quarantine</span></span> <br/><span data-ttu-id="2c213-120">-要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="2c213-120">- Request sample</span></span> <br/><span data-ttu-id="2c213-121">-コード実行を制限する (このアクションは元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="2c213-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="2c213-122">-ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="2c213-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="2c213-123">-停止および検疫</span><span class="sxs-lookup"><span data-stu-id="2c213-123">- Stop and quarantine</span></span>      |<span data-ttu-id="2c213-124">-ブロック URL (クリック時)</span><span class="sxs-lookup"><span data-stu-id="2c213-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="2c213-125">-電子メールメッセージまたはクラスターのソフト削除</span><span class="sxs-lookup"><span data-stu-id="2c213-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="2c213-126">-検疫電子メール</span><span class="sxs-lookup"><span data-stu-id="2c213-126">- Quarantine email</span></span><br/><span data-ttu-id="2c213-127">-電子メールの添付ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="2c213-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="2c213-128">-外部メール転送をオフにする</span><span class="sxs-lookup"><span data-stu-id="2c213-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="2c213-129">修復が保留になっているか、既に完了しているかにかかわらず、[アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="2c213-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="2c213-130">修復操作は自動調査に従います。</span><span class="sxs-lookup"><span data-stu-id="2c213-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="2c213-131">自動調査が完了すると、関係するすべての証拠について判定が行われ、修復アクションが特定されます。</span><span class="sxs-lookup"><span data-stu-id="2c213-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="2c213-132">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2c213-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="2c213-133">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2c213-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="2c213-134">判定</span><span class="sxs-lookup"><span data-stu-id="2c213-134">Verdict</span></span>    |<span data-ttu-id="2c213-135">分野</span><span class="sxs-lookup"><span data-stu-id="2c213-135">Area</span></span>    |<span data-ttu-id="2c213-136">結果</span><span class="sxs-lookup"><span data-stu-id="2c213-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="2c213-137">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="2c213-137">Malicious</span></span>    |<span data-ttu-id="2c213-138">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="2c213-138">Devices (endpoints)</span></span>    |<span data-ttu-id="2c213-139">修復アクションが自動的に実行されます</span><span class="sxs-lookup"><span data-stu-id="2c213-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="2c213-140">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="2c213-140">Malicious</span></span>    |<span data-ttu-id="2c213-141">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="2c213-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="2c213-142">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="2c213-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="2c213-143">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="2c213-143">Suspicious</span></span>    |<span data-ttu-id="2c213-144">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="2c213-144">Devices or email content</span></span> |<span data-ttu-id="2c213-145">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="2c213-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="2c213-146">脅威なし</span><span class="sxs-lookup"><span data-stu-id="2c213-146">No threats found</span></span>    |<span data-ttu-id="2c213-147">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="2c213-147">Devices or email content</span></span>    |<span data-ttu-id="2c213-148">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="2c213-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="2c213-149">保留中のアクションをアクション センターで確認する</span><span class="sxs-lookup"><span data-stu-id="2c213-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="2c213-150">Microsoft の脅威保護の自動化された調査と応答機能によって何かが失敗したか、誤って検出されたと思われる場合は、お知らせください。</span><span class="sxs-lookup"><span data-stu-id="2c213-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="2c213-151">[誤検知/ネガを報告](mtp-autoir-report-false-positives-negatives.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c213-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c213-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="2c213-152">Next steps</span></span>

- [<span data-ttu-id="2c213-153">アクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="2c213-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="2c213-154">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="2c213-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
