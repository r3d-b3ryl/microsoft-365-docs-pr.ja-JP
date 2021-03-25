---
title: Microsoft 365 Defender の修復アクション
description: Microsoft 365 Defender の自動調査に従う修復アクションの概要を確認する
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c81f824a0faaca1c228aa650c003576cce210a67
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199209"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="1e1ed-104">Microsoft 365 Defender の修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1e1ed-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1e1ed-105">**Applies to:**</span></span>
- <span data-ttu-id="1e1ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e1ed-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="1e1ed-107">修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-107">Remediation actions</span></span>

<span data-ttu-id="1e1ed-108">Microsoft 365 Defender での自動調査中および後に、悪意のあるアイテムや疑わしいアイテムに対する修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="1e1ed-109">一部の種類の修復アクションは、エンドポイントとも呼ばれるデバイスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="1e1ed-110">その他の修復アクションは、メール コンテンツに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="1e1ed-111">修復アクションを実行、承認、または拒否した後、自動調査が完了します。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e1ed-112">修復アクションが自動的に実行されるのか、承認時にのみ実行されるのかは、オートメーション レベルなどの特定の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="1e1ed-113">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="1e1ed-114">Microsoft 365 Defender で自動調査と対応機能を構成する</span><span class="sxs-lookup"><span data-stu-id="1e1ed-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="1e1ed-115">デバイスでの脅威の修復方法</span><span class="sxs-lookup"><span data-stu-id="1e1ed-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="1e1ed-116">コラボレーション コンテンツに対する電子メール&修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="1e1ed-117">次の表に、Microsoft 365 Defender で現在サポートされている修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="1e1ed-118">デバイス (エンドポイント) 修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="1e1ed-119">メールの修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="1e1ed-120">- 調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="1e1ed-120">- Collect investigation package</span></span> <br/><span data-ttu-id="1e1ed-121">- デバイスを分離する (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="1e1ed-122">- オフボード マシン</span><span class="sxs-lookup"><span data-stu-id="1e1ed-122">- Offboard machine</span></span> <br/><span data-ttu-id="1e1ed-123">- リリース コードの実行</span><span class="sxs-lookup"><span data-stu-id="1e1ed-123">- Release code execution</span></span> <br/><span data-ttu-id="1e1ed-124">- 検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="1e1ed-124">- Release from quarantine</span></span> <br/><span data-ttu-id="1e1ed-125">- 要求サンプル</span><span class="sxs-lookup"><span data-stu-id="1e1ed-125">- Request sample</span></span> <br/><span data-ttu-id="1e1ed-126">- コードの実行を制限する (このアクションは元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="1e1ed-127">- ウイルス対策スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="1e1ed-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="1e1ed-128">- 停止と検疫</span><span class="sxs-lookup"><span data-stu-id="1e1ed-128">- Stop and quarantine</span></span>      |<span data-ttu-id="1e1ed-129">- ブロック URL (クリック時)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="1e1ed-130">- 電子メール メッセージまたはクラスターを削除する</span><span class="sxs-lookup"><span data-stu-id="1e1ed-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="1e1ed-131">- 検疫メール</span><span class="sxs-lookup"><span data-stu-id="1e1ed-131">- Quarantine email</span></span><br/><span data-ttu-id="1e1ed-132">- メールの添付ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="1e1ed-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="1e1ed-133">- 外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="1e1ed-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="1e1ed-134">修復アクションは、保留中の承認または既に完了したかどうかに関して、アクション センターで [表示できます](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="1e1ed-135">自動調査に従う修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="1e1ed-136">自動調査が完了すると、関連するあらゆる証拠に対して評決が下されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="1e1ed-137">評決に応じて、修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="1e1ed-138">修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="1e1ed-139">すべては、自動調査 [と応答の構成方法によって異なります](m365d-configure-auto-investigation-response.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="1e1ed-140">考えられる判定と結果を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="1e1ed-141">判定</span><span class="sxs-lookup"><span data-stu-id="1e1ed-141">Verdict</span></span>    | <span data-ttu-id="1e1ed-142">分野</span><span class="sxs-lookup"><span data-stu-id="1e1ed-142">Area</span></span>    | <span data-ttu-id="1e1ed-143">結果</span><span class="sxs-lookup"><span data-stu-id="1e1ed-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="1e1ed-144">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-144">Malicious</span></span>    | <span data-ttu-id="1e1ed-145">デバイス (エンドポイント)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-145">Devices (endpoints)</span></span>    | <span data-ttu-id="1e1ed-146">修復アクションは自動的に実行されます (組織の [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)デバイス グループが完全に設定されている場合 - 脅威 **を自動的に修復する**)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="1e1ed-147">Malicious (悪意のある)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-147">Malicious</span></span>    | <span data-ttu-id="1e1ed-148">メールのコンテンツ (URL または添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="1e1ed-149">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="1e1ed-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="1e1ed-150">Suspicious (不審)</span><span class="sxs-lookup"><span data-stu-id="1e1ed-150">Suspicious</span></span>    | <span data-ttu-id="1e1ed-151">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="1e1ed-151">Devices or email content</span></span> | <span data-ttu-id="1e1ed-152">推奨される修復アクションが承認待ちになります</span><span class="sxs-lookup"><span data-stu-id="1e1ed-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="1e1ed-153">脅威は検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="1e1ed-153">No threats found</span></span>    | <span data-ttu-id="1e1ed-154">デバイスまたはメールのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="1e1ed-154">Devices or email content</span></span>    | <span data-ttu-id="1e1ed-155">必要な修復アクションはありません</span><span class="sxs-lookup"><span data-stu-id="1e1ed-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="1e1ed-156">手動で実行される修復アクション</span><span class="sxs-lookup"><span data-stu-id="1e1ed-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="1e1ed-157">自動調査に続く修復アクションに加えて、セキュリティ運用チームは特定の修復アクションを手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="1e1ed-158">これには、次のアクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-158">These include the following actions:</span></span>

- <span data-ttu-id="1e1ed-159">デバイスの分離やファイル検疫などのデバイスの手動操作。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="1e1ed-160">電子メール メッセージのソフト削除など、手動の電子メール アクション。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="1e1ed-161">[デバイスまたは電子メール](../defender-endpoint/advanced-hunting-overview.md) での高度なハンティング アクション。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="1e1ed-162">[迷惑](../office-365-security/threat-explorer.md) メールへのメールの移動、メールのソフト削除、メールのハード削除など、電子メール コンテンツに対するエクスプローラー アクション。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="1e1ed-163">ファイル [の削除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) 、プロセスの停止、スケジュールされたタスクの削除などの手動のライブ応答アクション。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="1e1ed-164">Microsoft Defender [for Endpoint API](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)を使用したライブ応答アクション (デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得など)。</span><span class="sxs-lookup"><span data-stu-id="1e1ed-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="1e1ed-165">次の手順</span><span class="sxs-lookup"><span data-stu-id="1e1ed-165">Next steps</span></span>

- [<span data-ttu-id="1e1ed-166">アクション センターにアクセスする</span><span class="sxs-lookup"><span data-stu-id="1e1ed-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="1e1ed-167">修復アクションの表示と管理</span><span class="sxs-lookup"><span data-stu-id="1e1ed-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="1e1ed-168">自動調査および応答機能で誤検知/負を処理する</span><span class="sxs-lookup"><span data-stu-id="1e1ed-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
