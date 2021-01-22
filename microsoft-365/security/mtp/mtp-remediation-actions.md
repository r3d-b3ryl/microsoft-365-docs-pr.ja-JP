---
title: Microsoft 365 Defender での修復アクション
description: Microsoft 365 Defender での自動調査に従った修復アクションの概要を取得する
keywords: 自動化、調査、警告、トリガー、アクション、修復
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932852"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="e2d76-104">Microsoft 365 Defender での修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e2d76-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e2d76-105">**Applies to:**</span></span>
- <span data-ttu-id="e2d76-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2d76-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="e2d76-107">修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-107">Remediation actions</span></span>

<span data-ttu-id="e2d76-108">Microsoft 365 Defender での自動調査の最中および後に、悪意のあるアイテムや疑わしいアイテムに対する修復アクションが特定されます。</span><span class="sxs-lookup"><span data-stu-id="e2d76-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="e2d76-109">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2d76-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="e2d76-110">その他の修復アクションは、メール コンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2d76-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="e2d76-111">修復アクションが実行、承認、または拒否された後、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="e2d76-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2d76-112">修復アクションが自動的に実行されるのか、承認によってのみ実行されるのかは、オートメーション レベルなどの特定の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e2d76-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="e2d76-113">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d76-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="e2d76-114">Microsoft 365 Defender で自動調査および対応機能を構成する</span><span class="sxs-lookup"><span data-stu-id="e2d76-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="e2d76-115">デバイスでの脅威の修復方法</span><span class="sxs-lookup"><span data-stu-id="e2d76-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="e2d76-116">コラボレーション コンテンツを含む電子メールに対&と修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="e2d76-117">次の表に、Microsoft 365 Defender で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e2d76-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="e2d76-118">デバイス (エンドポイント) の修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="e2d76-119">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="e2d76-120">- 調査パッケージを収集する</span><span class="sxs-lookup"><span data-stu-id="e2d76-120">- Collect investigation package</span></span> <br/><span data-ttu-id="e2d76-121">- デバイスを分離する (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="e2d76-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="e2d76-122">- オフボード コンピューター</span><span class="sxs-lookup"><span data-stu-id="e2d76-122">- Offboard machine</span></span> <br/><span data-ttu-id="e2d76-123">- リリース コードの実行</span><span class="sxs-lookup"><span data-stu-id="e2d76-123">- Release code execution</span></span> <br/><span data-ttu-id="e2d76-124">- 検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="e2d76-124">- Release from quarantine</span></span> <br/><span data-ttu-id="e2d76-125">- 要求サンプル</span><span class="sxs-lookup"><span data-stu-id="e2d76-125">- Request sample</span></span> <br/><span data-ttu-id="e2d76-126">- コードの実行を制限する (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="e2d76-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="e2d76-127">- ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="e2d76-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="e2d76-128">- 停止と検疫</span><span class="sxs-lookup"><span data-stu-id="e2d76-128">- Stop and quarantine</span></span>      |<span data-ttu-id="e2d76-129">- URL をブロックする (クリック時)</span><span class="sxs-lookup"><span data-stu-id="e2d76-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="e2d76-130">- メール メッセージまたはクラスターの削除 (回復可能)</span><span class="sxs-lookup"><span data-stu-id="e2d76-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="e2d76-131">- メールを検疫する</span><span class="sxs-lookup"><span data-stu-id="e2d76-131">- Quarantine email</span></span><br/><span data-ttu-id="e2d76-132">- メールの添付ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="e2d76-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="e2d76-133">- 外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="e2d76-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="e2d76-134">修復アクションは、承認待ちでも完了済みでも、アクション センターで [表示できます](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)。</span><span class="sxs-lookup"><span data-stu-id="e2d76-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="e2d76-135">自動調査に従う修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="e2d76-136">自動調査が完了すると、関係する証拠の一部ごとに 1 つの確認が求めらた。</span><span class="sxs-lookup"><span data-stu-id="e2d76-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="e2d76-137">状況に応じて、修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="e2d76-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="e2d76-138">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e2d76-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="e2d76-139">すべては、自動調査 [と対応の構成方法によって異なります](mtp-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d76-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="e2d76-140">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e2d76-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="e2d76-141">判定</span><span class="sxs-lookup"><span data-stu-id="e2d76-141">Verdict</span></span>    | <span data-ttu-id="e2d76-142">分野</span><span class="sxs-lookup"><span data-stu-id="e2d76-142">Area</span></span>    | <span data-ttu-id="e2d76-143">結果</span><span class="sxs-lookup"><span data-stu-id="e2d76-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="e2d76-144">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="e2d76-144">Malicious</span></span>    | <span data-ttu-id="e2d76-145">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="e2d76-145">Devices (endpoints)</span></span>    | <span data-ttu-id="e2d76-146">修復アクションが自動的に実行されます (組織の [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)デバイス グループが [完全] に設定されている場合 **- 脅威を自動的に修復する**)</span><span class="sxs-lookup"><span data-stu-id="e2d76-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="e2d76-147">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="e2d76-147">Malicious</span></span>    | <span data-ttu-id="e2d76-148">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="e2d76-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="e2d76-149">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="e2d76-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="e2d76-150">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="e2d76-150">Suspicious</span></span>    | <span data-ttu-id="e2d76-151">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="e2d76-151">Devices or email content</span></span> | <span data-ttu-id="e2d76-152">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="e2d76-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="e2d76-153">脅威は検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="e2d76-153">No threats found</span></span>    | <span data-ttu-id="e2d76-154">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="e2d76-154">Devices or email content</span></span>    | <span data-ttu-id="e2d76-155">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="e2d76-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="e2d76-156">手動で実行される修復アクション</span><span class="sxs-lookup"><span data-stu-id="e2d76-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="e2d76-157">自動調査に従う修復アクションに加えて、セキュリティ運用チームは特定の修復アクションを手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2d76-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="e2d76-158">これには、次のアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2d76-158">These include the following actions:</span></span>

- <span data-ttu-id="e2d76-159">デバイスの手動による操作 (デバイスの分離やファイル検疫など)。</span><span class="sxs-lookup"><span data-stu-id="e2d76-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="e2d76-160">電子メール メッセージのソフト削除など、手動の電子メール アクション。</span><span class="sxs-lookup"><span data-stu-id="e2d76-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="e2d76-161">[デバイスまたは電子メール](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) での高度な検索アクション。</span><span class="sxs-lookup"><span data-stu-id="e2d76-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="e2d76-162">[迷惑](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) メールへのメールの移動、メールのソフト削除、メールのハード削除など、メール コンテンツに対するエクスプローラー アクション。</span><span class="sxs-lookup"><span data-stu-id="e2d76-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="e2d76-163">ファイル [の削除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 、プロセスの停止、スケジュールされたタスクの削除など、手動のライブ応答アクション。</span><span class="sxs-lookup"><span data-stu-id="e2d76-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="e2d76-164">デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得など [、Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)API を使用したライブ応答アクション。</span><span class="sxs-lookup"><span data-stu-id="e2d76-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="e2d76-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="e2d76-165">Next steps</span></span>

- [<span data-ttu-id="e2d76-166">アクション センターにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e2d76-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="e2d76-167">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="e2d76-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="e2d76-168">自動調査および対応機能で誤検知/陰性を処理する</span><span class="sxs-lookup"><span data-stu-id="e2d76-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
