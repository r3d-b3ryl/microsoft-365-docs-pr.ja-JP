---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動化された調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威の防止、調査、アラート、保留、自動化、検出
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/01/2021
ms.openlocfilehash: d958f2787b9d66e42a32b8858139f7d13e83ddef
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199599"
---
# <a name="the-action-center"></a><span data-ttu-id="173a7-104">アクション センター</span><span class="sxs-lookup"><span data-stu-id="173a7-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="173a7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="173a7-105">**Applies to:**</span></span>
- <span data-ttu-id="173a7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="173a7-106">Microsoft 365 Defender</span></span>

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="173a7-107">「単一画面」エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="173a7-107">A "single pane of glass" experience</span></span>

<span data-ttu-id="173a7-108">アクション センターは、次のようなタスクに「単一画面」エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="173a7-108">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="173a7-109">保留中の修復アクションを承認する。</span><span class="sxs-lookup"><span data-stu-id="173a7-109">Approving pending remediation actions;</span></span>
- <span data-ttu-id="173a7-110">承認済みの修復アクションの監査ログを表示する。</span><span class="sxs-lookup"><span data-stu-id="173a7-110">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="173a7-111">完了した修復アクションを確認する。</span><span class="sxs-lookup"><span data-stu-id="173a7-111">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="173a7-112">アクション センターは、Microsoft 365 Defender の包括的なビューを提供しますので、セキュリティ運用チームは、より効果的かつ効率的に運用できます。</span><span class="sxs-lookup"><span data-stu-id="173a7-112">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.</span></span>

## <a name="a-new-unified-action-center"></a><span data-ttu-id="173a7-113">統合された新しいアクション センター</span><span class="sxs-lookup"><span data-stu-id="173a7-113">A new, unified Action center</span></span>

<span data-ttu-id="173a7-114">新しい統合アクション センター ( )を発表します [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。</span><span class="sxs-lookup"><span data-stu-id="173a7-114">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span> 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender の統合アクション センター":::

<span data-ttu-id="173a7-116">改善されたアクション センターには、デバイスの保留中および完了済み修復アクション、電子メール &コラボレーション コンテンツ、および ID が 1 つの場所に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="173a7-116">The improved Action center lists pending and completed remediation actions for your devices, email & collaboration content, and identities in one location.</span></span>
- <span data-ttu-id="173a7-117">以前に Office 365 セキュリティ & コンプライアンス センター ( ) を使用していた場合は、Microsoft 365 セキュリティ センター () の新しい統合アクション センターを [https://protection.office.com](https://protection.office.com) 試してください [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。</span><span class="sxs-lookup"><span data-stu-id="173a7-117">If you were previously using the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), try the new, unified Action center in the Microsoft 365 security center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)).</span></span>
- <span data-ttu-id="173a7-118">Microsoft Defender セキュリティ センター ( ) でアクション センターを使用している場合は、Microsoft 365 セキュリティ センター () の新しい統合アクション センター [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) を試してください [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。</span><span class="sxs-lookup"><span data-stu-id="173a7-118">If you were using the Action Center in the Microsoft Defender Security Center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)), try the new, unified Action center in the Microsoft 365 security center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)).</span></span>
- <span data-ttu-id="173a7-119">Microsoft 365 セキュリティ センター ( ) を既に使用していた場合は、アクション センター ( ) にいくつかの [https://security.microsoft.com](https://security.microsoft.com) 機能強化が表示されます [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。</span><span class="sxs-lookup"><span data-stu-id="173a7-119">If you were already using the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)), you'll see several improvements in the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)).</span></span>

<span data-ttu-id="173a7-120">統合アクション センターでは、365 用の Defender for Endpoint と Defender 全体で修復Officeされます。</span><span class="sxs-lookup"><span data-stu-id="173a7-120">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="173a7-121">すべての修復アクションの共通言語を定義し、統合された調査エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="173a7-121">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> <span data-ttu-id="173a7-122">アクション センターは、修復アクションを表示および管理するための"単一のガラス枠" エクスペリエンスをセキュリティ運用チームに提供します。</span><span class="sxs-lookup"><span data-stu-id="173a7-122">The Action center provides your security operations team with a "single pane of glass" experience to view and manage remediation actions.</span></span>  

<span data-ttu-id="173a7-123">適切なアクセス許可と次のサブスクリプションの 1 つ以上がある場合は、統合アクション センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="173a7-123">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>

- [<span data-ttu-id="173a7-124">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="173a7-124">Defender for Endpoint</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="173a7-125">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="173a7-125">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)
- [<span data-ttu-id="173a7-126">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="173a7-126">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)

> [!TIP]
> <span data-ttu-id="173a7-127">詳細については、「要件」 [を参照してください](./prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="173a7-127">To learn more, see [Requirements](./prerequisites.md).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="173a7-128">アクション センターの使用</span><span class="sxs-lookup"><span data-stu-id="173a7-128">Using the Action center</span></span>

1. <span data-ttu-id="173a7-129">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="173a7-129">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="173a7-130">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="173a7-130">In the navigation pane, choose **Action center**.</span></span> 

<span data-ttu-id="173a7-131">アクション センターにアクセスすると、[保留中のアクション] と [履歴] の 2 つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="173a7-131">When you visit the Action center, you see two tabs: Pending actions and History.</span></span> <span data-ttu-id="173a7-132">次の表に、各タブに表示される内容の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="173a7-132">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="173a7-133">タブ</span><span class="sxs-lookup"><span data-stu-id="173a7-133">Tab</span></span>  |<span data-ttu-id="173a7-134">説明</span><span class="sxs-lookup"><span data-stu-id="173a7-134">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="173a7-135">**Pending**</span><span class="sxs-lookup"><span data-stu-id="173a7-135">**Pending**</span></span>     | <span data-ttu-id="173a7-136">注意が必要なアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="173a7-136">Displays a list of actions that require attention.</span></span> <span data-ttu-id="173a7-137">アクションを一度に 1 つ承認または拒否するか、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="173a7-137">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as Quarantine file).</span></span> <p><span data-ttu-id="173a7-138">**ヒント**: 保留中のアクションをできるだけ早く確認し、承認 (または拒否) して、自動調査が正時に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="173a7-138">**TIP**: Make sure to review and approve (or reject) pending actions as soon as possible so that your automated investigations can complete in a timely manner.</span></span>       |
|<span data-ttu-id="173a7-139">**履歴**</span><span class="sxs-lookup"><span data-stu-id="173a7-139">**History**</span></span>     | <span data-ttu-id="173a7-140">次のようなアクションの監査ログとして機能します。</span><span class="sxs-lookup"><span data-stu-id="173a7-140">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="173a7-141">- 自動調査の結果として実行された修復アクション</span><span class="sxs-lookup"><span data-stu-id="173a7-141">- Remediation actions that were taken as a result of automated investigations</span></span> <br/><span data-ttu-id="173a7-142">- 疑わしいまたは悪意のある電子メール メッセージ、ファイル、または URL に対して実行された修復アクション</span><span class="sxs-lookup"><span data-stu-id="173a7-142">- Remediation actions that were taken on suspicious or malicious email messages, files, or URLs</span></span><br/><span data-ttu-id="173a7-143">- セキュリティ運用チームによって承認された修復アクション</span><span class="sxs-lookup"><span data-stu-id="173a7-143">- Remediation actions that were approved by your security operations team</span></span> <br/><span data-ttu-id="173a7-144">- Live Response セッション中に適用された、実行されたコマンドと修復アクション</span><span class="sxs-lookup"><span data-stu-id="173a7-144">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span><br/><span data-ttu-id="173a7-145">- ウイルス対策保護によって実行された修復アクション</span><span class="sxs-lookup"><span data-stu-id="173a7-145">- Remediation actions that were taken by your antivirus protection</span></span> <p><span data-ttu-id="173a7-146">特定のアクションを元に戻す方法を提供します (「完了した操作を元に戻[す」を参照)。](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="173a7-146">Provides a way to undo certain actions (see [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions)).</span></span>        |

<span data-ttu-id="173a7-147">アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="173a7-147">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="アクション センターを使用すると、アクションの一覧を並べ替え、フィルター処理、カスタマイズできます。":::

- <span data-ttu-id="173a7-149">列見出しを選択して、アイテムを昇順または降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="173a7-149">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="173a7-150">期間フィルターを使用して、過去の日、週、30 日、または 6 か月のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="173a7-150">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="173a7-151">表示する列を選択します。</span><span class="sxs-lookup"><span data-stu-id="173a7-151">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="173a7-152">データの各ページに含めるアイテムの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="173a7-152">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="173a7-153">フィルターを使用して、表示するアイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="173a7-153">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="173a7-154">[エクスポート **] を** 選択して、結果を .csv ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="173a7-154">Select **Export** to export results to a .csv file.</span></span>

## <a name="actions-tracked-in-the-action-center"></a><span data-ttu-id="173a7-155">アクション センターで追跡されるアクション</span><span class="sxs-lookup"><span data-stu-id="173a7-155">Actions tracked in the Action center</span></span>

<span data-ttu-id="173a7-156">承認待ちか既に実行済みかのアクションはすべて、アクション センターで追跡されます。</span><span class="sxs-lookup"><span data-stu-id="173a7-156">All actions, whether they're pending approval or were already taken, are tracked in the Action center.</span></span> <span data-ttu-id="173a7-157">使用可能なアクションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="173a7-157">Available actions include the following:</span></span>

- <span data-ttu-id="173a7-158">調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="173a7-158">Collect investigation package</span></span> 
- <span data-ttu-id="173a7-159">デバイスを分離する (この操作は元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="173a7-159">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="173a7-160">オフボード マシン</span><span class="sxs-lookup"><span data-stu-id="173a7-160">Offboard machine</span></span> 
- <span data-ttu-id="173a7-161">リリース コードの実行</span><span class="sxs-lookup"><span data-stu-id="173a7-161">Release code execution</span></span> 
- <span data-ttu-id="173a7-162">検疫からの解放</span><span class="sxs-lookup"><span data-stu-id="173a7-162">Release from quarantine</span></span> 
- <span data-ttu-id="173a7-163">要求サンプル</span><span class="sxs-lookup"><span data-stu-id="173a7-163">Request sample</span></span> 
- <span data-ttu-id="173a7-164">コードの実行を制限する (このアクションは元に戻すことができます)</span><span class="sxs-lookup"><span data-stu-id="173a7-164">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="173a7-165">ウイルス対策スキャンの実行</span><span class="sxs-lookup"><span data-stu-id="173a7-165">Run antivirus scan</span></span> 
- <span data-ttu-id="173a7-166">停止と検疫</span><span class="sxs-lookup"><span data-stu-id="173a7-166">Stop and quarantine</span></span> 

<span data-ttu-id="173a7-167">自動調査の結果として自動的に実行される修復アクションに加[](m365d-autoir.md)えて、アクション センターは、検出された脅威に対処するためにセキュリティ チームが実行したアクションと、Microsoft 365 Defender の脅威保護機能の結果として実行されたアクションも追跡します。</span><span class="sxs-lookup"><span data-stu-id="173a7-167">In addition to remediation actions that are taken automatically as a result of [automated investigations](m365d-autoir.md), the Action center also tracks actions your security team has taken to address detected threats, and actions that were taken as a result of threat protection features in Microsoft 365 Defender.</span></span> <span data-ttu-id="173a7-168">自動修復アクションと手動修復アクションの詳細については、「修復アクション」 [を参照してください](m365d-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="173a7-168">For more information about automatic and manual remediation actions, see [Remediation actions](m365d-remediation-actions.md).</span></span>

## <a name="viewing-action-source-details"></a><span data-ttu-id="173a7-169">アクション ソースの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="173a7-169">Viewing action source details</span></span>

<span data-ttu-id="173a7-170">(**NEW!**)改善されたアクション センターに、各 **アクションの** 送信元を示す [アクション ソース] 列が追加されました。</span><span class="sxs-lookup"><span data-stu-id="173a7-170">(**NEW!**) The improved Action center now includes an **Action source** column that tells you where each action came from.</span></span> <span data-ttu-id="173a7-171">次の表に、可能なアクション ソース **値について説明** します。</span><span class="sxs-lookup"><span data-stu-id="173a7-171">The following table describes possible **Action source** values:</span></span>

| <span data-ttu-id="173a7-172">アクション ソースの値</span><span class="sxs-lookup"><span data-stu-id="173a7-172">Action source value</span></span> | <span data-ttu-id="173a7-173">説明</span><span class="sxs-lookup"><span data-stu-id="173a7-173">Description</span></span> |
|:-----|:---|
| <span data-ttu-id="173a7-174">**デバイスの手動操作**</span><span class="sxs-lookup"><span data-stu-id="173a7-174">**Manual device action**</span></span> | <span data-ttu-id="173a7-175">デバイスで手動で実行される操作。</span><span class="sxs-lookup"><span data-stu-id="173a7-175">A manual action taken on a device.</span></span> <span data-ttu-id="173a7-176">たとえば、デバイスの[分離やファイル](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network)[の検疫が含まれます](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files)。</span><span class="sxs-lookup"><span data-stu-id="173a7-176">Examples include [device isolation](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) or [file quarantine](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files).</span></span> |
| <span data-ttu-id="173a7-177">**手動の電子メール 操作**</span><span class="sxs-lookup"><span data-stu-id="173a7-177">**Manual email action**</span></span> | <span data-ttu-id="173a7-178">電子メールに対して手動で実行される操作。</span><span class="sxs-lookup"><span data-stu-id="173a7-178">A manual action taken on email.</span></span> <span data-ttu-id="173a7-179">たとえば、電子メール メッセージをソフト削除したり、 [電子メール メッセージを修復したりします](../office-365-security/remediate-malicious-email-delivered-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="173a7-179">An example includes soft-deleting email messages or [remediating an email message](../office-365-security/remediate-malicious-email-delivered-office-365.md).</span></span> |
| <span data-ttu-id="173a7-180">**デバイスの自動操作**</span><span class="sxs-lookup"><span data-stu-id="173a7-180">**Automated device action**</span></span> | <span data-ttu-id="173a7-181">ファイルやプロセスなど、エンティティに対して実行される自動アクション。</span><span class="sxs-lookup"><span data-stu-id="173a7-181">An automated action taken on an entity, such as a file or process.</span></span> <span data-ttu-id="173a7-182">自動操作の例としては、ファイルを検疫に送信する、プロセスを停止する、レジストリ キーを削除するなどの操作があります。</span><span class="sxs-lookup"><span data-stu-id="173a7-182">Examples of automated actions include sending a file to quarantine, stopping a process, and removing a registry key.</span></span> <span data-ttu-id="173a7-183">[(「Microsoft Defender for Endpoint での修復アクション」を参照](../defender-endpoint/manage-auto-investigation.md#remediation-actions)してください。</span><span class="sxs-lookup"><span data-stu-id="173a7-183">(See [Remediation actions in Microsoft Defender for Endpoint](../defender-endpoint/manage-auto-investigation.md#remediation-actions).)</span></span> |
| <span data-ttu-id="173a7-184">**電子メールの自動操作**</span><span class="sxs-lookup"><span data-stu-id="173a7-184">**Automated email action**</span></span> | <span data-ttu-id="173a7-185">電子メール メッセージ、添付ファイル、URL などの電子メール コンテンツに対して実行される自動アクション。</span><span class="sxs-lookup"><span data-stu-id="173a7-185">An automated action taken on email content, such as an email message, attachment, or URL.</span></span> <span data-ttu-id="173a7-186">自動化されたアクションの例としては、電子メール メッセージのソフト削除、URL のブロック、外部メール転送のオフが含まれます。</span><span class="sxs-lookup"><span data-stu-id="173a7-186">Examples of automated actions include soft-deleting email messages, blocking URLs, and turning off external mail forwarding.</span></span> <span data-ttu-id="173a7-187">(「Microsoft [Defender の修復アクション」を参照Office 365.)](../office-365-security/air-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="173a7-187">(See [Remediation actions in Microsoft Defender for Office 365](../office-365-security/air-remediation-actions.md).)</span></span> |
| <span data-ttu-id="173a7-188">**高度なハンティング アクション**</span><span class="sxs-lookup"><span data-stu-id="173a7-188">**Advanced hunting action**</span></span> | <span data-ttu-id="173a7-189">高度な検索を使用してデバイスまたは電子メール [で実行されるアクション](./advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="173a7-189">Actions taken on devices or email with [advanced hunting](./advanced-hunting-overview.md).</span></span> |
| <span data-ttu-id="173a7-190">**エクスプローラー アクション**</span><span class="sxs-lookup"><span data-stu-id="173a7-190">**Explorer action**</span></span> | <span data-ttu-id="173a7-191">Explorer を使用して電子メール コンテンツに対して実行 [されるアクション](../office-365-security/threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="173a7-191">Actions taken on email content with [Explorer](../office-365-security/threat-explorer.md).</span></span> |
| <span data-ttu-id="173a7-192">**手動のライブ応答アクション**</span><span class="sxs-lookup"><span data-stu-id="173a7-192">**Manual live response action**</span></span> | <span data-ttu-id="173a7-193">ライブ応答を持つデバイスで [実行されるアクション](../defender-endpoint/live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="173a7-193">Actions taken on a device with [live response](../defender-endpoint/live-response.md).</span></span> <span data-ttu-id="173a7-194">たとえば、ファイルの削除、プロセスの停止、スケジュールされたタスクの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="173a7-194">Examples include deleting a file, stopping a process, and removing a scheduled task.</span></span> |
| <span data-ttu-id="173a7-195">**ライブ応答アクション**</span><span class="sxs-lookup"><span data-stu-id="173a7-195">**Live response action**</span></span> | <span data-ttu-id="173a7-196">Microsoft Defender for Endpoint API を使用して [デバイスで実行されるアクション](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)。</span><span class="sxs-lookup"><span data-stu-id="173a7-196">Actions taken on a device with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis).</span></span> <span data-ttu-id="173a7-197">アクションの例としては、デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得があります。</span><span class="sxs-lookup"><span data-stu-id="173a7-197">Examples of actions include isolating a device, running an antivirus scan, and getting information about a file.</span></span> |

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="173a7-198">アクション センター タスクに必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="173a7-198">Required permissions for Action center tasks</span></span>

<span data-ttu-id="173a7-199">アクション センターで保留中のアクションの承認や拒否などのタスクを実行するには、次の表に示すアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="173a7-199">To perform tasks, such as approving or rejecting pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="173a7-200">修復アクション</span><span class="sxs-lookup"><span data-stu-id="173a7-200">Remediation action</span></span> |<span data-ttu-id="173a7-201">必要な役割と権限</span><span class="sxs-lookup"><span data-stu-id="173a7-201">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="173a7-202">Microsoft Defender for Endpoint 修復 (デバイス)</span><span class="sxs-lookup"><span data-stu-id="173a7-202">Microsoft Defender for Endpoint remediation (devices)</span></span> |<span data-ttu-id="173a7-203">Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられた **セキュリティ管理者** の役割</span><span class="sxs-lookup"><span data-stu-id="173a7-203">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="173a7-204">--- または ---</span><span class="sxs-lookup"><span data-stu-id="173a7-204">--- or ---</span></span><br/><span data-ttu-id="173a7-205">Microsoft Defender for Endpoint **で割** り当てられたアクティブな修復アクションの役割</span><span class="sxs-lookup"><span data-stu-id="173a7-205">**Active remediation actions** role assigned in Microsoft Defender for Endpoint</span></span> <br/> <br/> <span data-ttu-id="173a7-206">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="173a7-206">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="173a7-207">- [Azure Active Directory での管理者役割のアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="173a7-207">- [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="173a7-208">- [役割ベースのアクセス制御の役割を作成および管理する (Microsoft Defender for Endpoint)](../defender-endpoint/user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="173a7-208">- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](../defender-endpoint/user-roles.md)</span></span>  |
|<span data-ttu-id="173a7-209">Microsoft Defender for Office 365 修復 (Officeメール)</span><span class="sxs-lookup"><span data-stu-id="173a7-209">Microsoft Defender for Office 365 remediation (Office content and email)</span></span>  |<span data-ttu-id="173a7-210">Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられた **セキュリティ管理者** の役割</span><span class="sxs-lookup"><span data-stu-id="173a7-210">**Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="173a7-211">--- さらに ---</span><span class="sxs-lookup"><span data-stu-id="173a7-211">--- and ---</span></span> <br/><span data-ttu-id="173a7-212">**セキュリティ コンプライアンス センターに** 割り当てられた検索&削除の役割 ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="173a7-212">**Search and Purge** role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="173a7-213">**重要**: Office 365 セキュリティ & コンプライアンス センター ( ) でのみセキュリティ管理者の役割が割り当てられている場合は、アクション センターまたは Microsoft  [https://protection.office.com](https://protection.office.com) 365 Defender の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="173a7-213">**IMPORTANT**: If you have the **Security Administrator** role assigned only in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), you will not be able to access the Action center or Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="173a7-214">Azure Active Directory **または** Microsoft 365 管理センターでセキュリティ管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="173a7-214">You must have the **Security Administrator** role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="173a7-215">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="173a7-215">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="173a7-216">- [Azure Active Directory での管理者役割のアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="173a7-216">- [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="173a7-217">- [セキュリティ コンプライアンス センター&アクセス許可](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="173a7-217">- [Permissions in the Security & Compliance Center](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!TIP]
> <span data-ttu-id="173a7-218">Azure Active Directory で **グローバル管理者** の役割が割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="173a7-218">Users who have the **Global Administrator** role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="173a7-219">ただし、ベスト プラクティスとして、組織はグローバル管理者の役割が割り当てられているユーザー **の数を制限する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="173a7-219">However, as a best practice, your organization should limit the number of people who have the **Global Administrator** role assigned.</span></span> <span data-ttu-id="173a7-220">アクション センターのアクセス許可 **については、** 前の表に記載されているセキュリティ管理者、アクティブな修復アクション、および検索と削除の役割を使用することをお勧めします。 </span><span class="sxs-lookup"><span data-stu-id="173a7-220">We recommend using the **Security Administrator**, **Active remediation actions**, and **Search and Purge** roles listed in the preceding table for Action center permissions.</span></span>

## <a name="next-step"></a><span data-ttu-id="173a7-221">次の手順</span><span class="sxs-lookup"><span data-stu-id="173a7-221">Next step</span></span> 

- [<span data-ttu-id="173a7-222">修復アクションの確認と管理</span><span class="sxs-lookup"><span data-stu-id="173a7-222">Review and manage remediation actions</span></span>](m365d-autoir-actions.md)