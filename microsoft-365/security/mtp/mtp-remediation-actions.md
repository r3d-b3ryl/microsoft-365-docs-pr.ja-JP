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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 205809bac14cc82e850ea1cbc0349256432bfe68
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962587"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="e2c32-104">Microsoft の脅威保護で自動調査を行った後の修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2c32-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="e2c32-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e2c32-105">**Applies to:**</span></span>
- <span data-ttu-id="e2c32-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e2c32-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="e2c32-107">修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2c32-107">Remediation actions</span></span>

<span data-ttu-id="e2c32-108">Microsoft の脅威保護の自動化された調査の最中および実行後に、修復アクションは悪意のあるアイテムまたは疑わしいアイテムに対して識別されます。</span><span class="sxs-lookup"><span data-stu-id="e2c32-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="e2c32-109">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2c32-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="e2c32-110">その他の修復アクションは、電子メールコンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2c32-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="e2c32-111">修復アクションが実行、承認、または拒否された後、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="e2c32-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="e2c32-112">次の表に、Microsoft の脅威保護で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e2c32-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="e2c32-113">デバイス (エンドポイント) の修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2c32-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="e2c32-114">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2c32-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="e2c32-115">-調査パッケージを収集する</span><span class="sxs-lookup"><span data-stu-id="e2c32-115">- Collect investigation package</span></span> <br/><span data-ttu-id="e2c32-116">-分離デバイス (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="e2c32-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="e2c32-117">-オフボードマシン</span><span class="sxs-lookup"><span data-stu-id="e2c32-117">- Offboard machine</span></span> <br/><span data-ttu-id="e2c32-118">-リリースコードの実行</span><span class="sxs-lookup"><span data-stu-id="e2c32-118">- Release code execution</span></span> <br/><span data-ttu-id="e2c32-119">-検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="e2c32-119">- Release from quarantine</span></span> <br/><span data-ttu-id="e2c32-120">-要求のサンプル</span><span class="sxs-lookup"><span data-stu-id="e2c32-120">- Request sample</span></span> <br/><span data-ttu-id="e2c32-121">-コード実行を制限する (このアクションは元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="e2c32-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="e2c32-122">-ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="e2c32-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="e2c32-123">-停止および検疫</span><span class="sxs-lookup"><span data-stu-id="e2c32-123">- Stop and quarantine</span></span>      |<span data-ttu-id="e2c32-124">-ブロック URL (クリック時)</span><span class="sxs-lookup"><span data-stu-id="e2c32-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="e2c32-125">-電子メールメッセージまたはクラスターのソフト削除</span><span class="sxs-lookup"><span data-stu-id="e2c32-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="e2c32-126">-検疫電子メール</span><span class="sxs-lookup"><span data-stu-id="e2c32-126">- Quarantine email</span></span><br/><span data-ttu-id="e2c32-127">-電子メールの添付ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="e2c32-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="e2c32-128">-外部メール転送をオフにする</span><span class="sxs-lookup"><span data-stu-id="e2c32-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="e2c32-129">修復アクションは、保留中の承認か、既に完了しているかにかかわらず、 [アクションセンター](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)に表示できます。</span><span class="sxs-lookup"><span data-stu-id="e2c32-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="e2c32-130">修復操作は自動調査に従います。</span><span class="sxs-lookup"><span data-stu-id="e2c32-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="e2c32-131">自動調査が完了すると、関連するすべての証拠に対して verdict が到達します。</span><span class="sxs-lookup"><span data-stu-id="e2c32-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="e2c32-132">Verdict に応じて、修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="e2c32-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="e2c32-133">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e2c32-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="e2c32-134">これ [は、自動化された調査と応答の構成](mtp-configure-auto-investigation-response.md)方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e2c32-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="e2c32-135">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e2c32-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="e2c32-136">判定</span><span class="sxs-lookup"><span data-stu-id="e2c32-136">Verdict</span></span>    |<span data-ttu-id="e2c32-137">分野</span><span class="sxs-lookup"><span data-stu-id="e2c32-137">Area</span></span>    |<span data-ttu-id="e2c32-138">結果</span><span class="sxs-lookup"><span data-stu-id="e2c32-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="e2c32-139">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="e2c32-139">Malicious</span></span>    |<span data-ttu-id="e2c32-140">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="e2c32-140">Devices (endpoints)</span></span>    |<span data-ttu-id="e2c32-141">修復処置は自動的に実行されます (組織の [デバイスグループ](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) が **完全に修復**される脅威に自動的に設定されることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="e2c32-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="e2c32-142">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="e2c32-142">Malicious</span></span>    |<span data-ttu-id="e2c32-143">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="e2c32-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="e2c32-144">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="e2c32-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="e2c32-145">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="e2c32-145">Suspicious</span></span>    |<span data-ttu-id="e2c32-146">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="e2c32-146">Devices or email content</span></span> |<span data-ttu-id="e2c32-147">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="e2c32-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="e2c32-148">脅威なし</span><span class="sxs-lookup"><span data-stu-id="e2c32-148">No threats found</span></span>    |<span data-ttu-id="e2c32-149">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="e2c32-149">Devices or email content</span></span>    |<span data-ttu-id="e2c32-150">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="e2c32-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="e2c32-151">修復アクションが自動的に実行されるか、承認のみになるかは、組織のデバイスグループポリシーなどの特定の設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="e2c32-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="e2c32-152">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2c32-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="e2c32-153">Microsoft の脅威保護で自動調査および応答機能を構成する</span><span class="sxs-lookup"><span data-stu-id="e2c32-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="e2c32-154">デバイスでの脅威の修復方法</span><span class="sxs-lookup"><span data-stu-id="e2c32-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="e2c32-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="e2c32-155">Next steps</span></span>

- [<span data-ttu-id="e2c32-156">アクションセンターにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e2c32-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="e2c32-157">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="e2c32-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="e2c32-158">自動調査と応答機能で誤検知/否定を処理する</span><span class="sxs-lookup"><span data-stu-id="e2c32-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
