---
title: Defender での修復Microsoft 365操作
description: Defender の自動調査に従う修復アクションの概要をMicrosoft 365する
keywords: 自動化、調査、警告、トリガー、アクション、修復
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 80546d44bc1ba222c736b397a272f9f1f1a01d4a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269470"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="59fe9-104">Defender での修復Microsoft 365操作</span><span class="sxs-lookup"><span data-stu-id="59fe9-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59fe9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="59fe9-105">**Applies to:**</span></span>
- <span data-ttu-id="59fe9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fe9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="59fe9-107">Defender での自動調査中およびMicrosoft 365、悪意のあるアイテムまたは不審なアイテムに対する修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="59fe9-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="59fe9-108">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="59fe9-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="59fe9-109">その他の修復アクションは、メール コンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="59fe9-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="59fe9-110">修復アクションを実行、承認、または拒否した後、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="59fe9-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59fe9-111">修復アクションが自動的に実行されるのか、承認時にのみ実行されるのかは、オートメーション レベルなどの特定の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="59fe9-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="59fe9-112">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59fe9-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="59fe9-113">Defender で自動調査と応答機能をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="59fe9-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="59fe9-114">デバイスでの脅威の修復方法</span><span class="sxs-lookup"><span data-stu-id="59fe9-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="59fe9-115">コラボレーション コンテンツに対する電子メール&修復アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="59fe9-116">次の表に、Defender で現在サポートされている修復Microsoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="59fe9-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="59fe9-117">デバイス (エンドポイント) 修復アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="59fe9-118">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="59fe9-119">- 調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="59fe9-119">- Collect investigation package</span></span> <br/><span data-ttu-id="59fe9-120">- デバイスを分離する (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="59fe9-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="59fe9-121">- オフボード マシン</span><span class="sxs-lookup"><span data-stu-id="59fe9-121">- Offboard machine</span></span> <br/><span data-ttu-id="59fe9-122">- リリース コードの実行</span><span class="sxs-lookup"><span data-stu-id="59fe9-122">- Release code execution</span></span> <br/><span data-ttu-id="59fe9-123">- 検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="59fe9-123">- Release from quarantine</span></span> <br/><span data-ttu-id="59fe9-124">- 要求サンプル</span><span class="sxs-lookup"><span data-stu-id="59fe9-124">- Request sample</span></span> <br/><span data-ttu-id="59fe9-125">- コードの実行を制限する (このアクションは元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="59fe9-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="59fe9-126">- ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="59fe9-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="59fe9-127">- 停止と検疫</span><span class="sxs-lookup"><span data-stu-id="59fe9-127">- Stop and quarantine</span></span>      |<span data-ttu-id="59fe9-128">- ブロック URL (クリック時)</span><span class="sxs-lookup"><span data-stu-id="59fe9-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="59fe9-129">- 電子メール メッセージまたはクラスターを削除する</span><span class="sxs-lookup"><span data-stu-id="59fe9-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="59fe9-130">- 検疫メール</span><span class="sxs-lookup"><span data-stu-id="59fe9-130">- Quarantine email</span></span><br/><span data-ttu-id="59fe9-131">- メールの添付ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="59fe9-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="59fe9-132">- 外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="59fe9-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="59fe9-133">修復アクションは、保留中の承認または既に完了したかどうかに関して、アクション センターで [表示できます](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="59fe9-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="59fe9-134">自動調査に従う修復アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="59fe9-135">自動調査が完了すると、関連するあらゆる証拠に対して評決が下されます。</span><span class="sxs-lookup"><span data-stu-id="59fe9-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="59fe9-136">評決に応じて、修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="59fe9-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="59fe9-137">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="59fe9-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="59fe9-138">すべては、自動調査 [と応答の構成方法によって異なります](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="59fe9-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="59fe9-139">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="59fe9-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="59fe9-140">判定</span><span class="sxs-lookup"><span data-stu-id="59fe9-140">Verdict</span></span>    | <span data-ttu-id="59fe9-141">影響を受けるエンティティ</span><span class="sxs-lookup"><span data-stu-id="59fe9-141">Affected entities</span></span>    | <span data-ttu-id="59fe9-142">結果</span><span class="sxs-lookup"><span data-stu-id="59fe9-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="59fe9-143">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="59fe9-143">Malicious</span></span>    | <span data-ttu-id="59fe9-144">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="59fe9-144">Devices (endpoints)</span></span>    | <span data-ttu-id="59fe9-145">修復アクションは自動的に実行されます (組織の [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)デバイス グループが完全に設定されている場合 - 脅威 **を自動的に修復する**)</span><span class="sxs-lookup"><span data-stu-id="59fe9-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="59fe9-146">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="59fe9-146">Malicious</span></span>    | <span data-ttu-id="59fe9-147">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="59fe9-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="59fe9-148">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="59fe9-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="59fe9-149">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="59fe9-149">Suspicious</span></span>    | <span data-ttu-id="59fe9-150">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="59fe9-150">Devices or email content</span></span> | <span data-ttu-id="59fe9-151">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="59fe9-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="59fe9-152">脅威は検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="59fe9-152">No threats found</span></span>    | <span data-ttu-id="59fe9-153">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="59fe9-153">Devices or email content</span></span>    | <span data-ttu-id="59fe9-154">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="59fe9-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="59fe9-155">手動で実行される修復アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="59fe9-156">自動調査に続く修復アクションに加えて、セキュリティ運用チームは特定の修復アクションを手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="59fe9-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="59fe9-157">これらには次のコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="59fe9-157">These include the following:</span></span>

- <span data-ttu-id="59fe9-158">デバイスの分離やファイル検疫などのデバイスの手動操作</span><span class="sxs-lookup"><span data-stu-id="59fe9-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="59fe9-159">電子メール メッセージのソフト削除などの手動の電子メール アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="59fe9-160">[デバイスまたは電子](../defender-endpoint/advanced-hunting-overview.md) メールでの高度なハンティング アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="59fe9-161">[迷惑](../office-365-security/threat-explorer.md) メールへのメールの移動、メールのソフト削除、メールのハード削除など、電子メール コンテンツに対するエクスプローラー アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="59fe9-162">ファイル [の削除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 、プロセスの停止、スケジュールされたタスクの削除などの手動のライブ応答アクション</span><span class="sxs-lookup"><span data-stu-id="59fe9-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="59fe9-163">Microsoft Defender [for Endpoint API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)を使用したライブ応答アクション (デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得など)</span><span class="sxs-lookup"><span data-stu-id="59fe9-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="59fe9-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="59fe9-164">Next steps</span></span>

- [<span data-ttu-id="59fe9-165">アクション センターにアクセスする</span><span class="sxs-lookup"><span data-stu-id="59fe9-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="59fe9-166">修復アクションの表示と管理</span><span class="sxs-lookup"><span data-stu-id="59fe9-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="59fe9-167">誤検知または誤検知に対処する</span><span class="sxs-lookup"><span data-stu-id="59fe9-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
