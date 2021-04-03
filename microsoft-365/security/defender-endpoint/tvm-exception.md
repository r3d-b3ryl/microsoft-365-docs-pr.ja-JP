---
title: セキュリティに関する推奨事項の例外を作成して表示する - 脅威と脆弱性の管理
description: 脅威と脆弱性管理のセキュリティに関する推奨事項の例外を作成および監視します。
keywords: microsoft Defender atp tvm 修復、mdatp tvm、脅威と脆弱性管理、脅威 & 脆弱性管理、脅威 & 脆弱性管理修復、tvm 修復 intune、tvm 修復 sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13ac09b1ad918ed945edec6167fd57ea02b616ea
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500181"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="73680-104">セキュリティに関する推奨事項の例外を作成して表示する - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="73680-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="73680-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="73680-105">**Applies to:**</span></span>

- [<span data-ttu-id="73680-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="73680-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="73680-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="73680-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="73680-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73680-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="73680-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="73680-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="73680-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="73680-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="73680-111">推奨事項が現時点では関連しない場合の修復要求の代わりに、推奨事項の例外を作成できます。</span><span class="sxs-lookup"><span data-stu-id="73680-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="73680-112">組織にデバイス グループがある場合は、例外の範囲を特定のデバイス グループに設定できます。</span><span class="sxs-lookup"><span data-stu-id="73680-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="73680-113">例外は、選択したデバイス グループに対して作成するか、過去と現在のすべてのデバイス グループに対して作成できます。</span><span class="sxs-lookup"><span data-stu-id="73680-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="73680-114">推奨事項に対して例外が作成されると、例外期間が終了するまで、推奨事項はアクティブにされません。</span><span class="sxs-lookup"><span data-stu-id="73680-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="73680-115">推奨事項の状態が [完全な例外] **または [部分的な** 例外] (デバイス **グループ** 別) に変更されます。</span><span class="sxs-lookup"><span data-stu-id="73680-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="73680-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="73680-116">Permissions</span></span>

<span data-ttu-id="73680-117">"例外処理" 権限を持つユーザーだけが例外を管理できます (作成またはキャンセルを含む)。</span><span class="sxs-lookup"><span data-stu-id="73680-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="73680-118">[RBAC の役割について詳しくは、次のページを参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="73680-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![例外処理のアクセス許可の表示。](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="73680-120">例外の作成</span><span class="sxs-lookup"><span data-stu-id="73680-120">Create an exception</span></span>

<span data-ttu-id="73680-121">例外を作成するセキュリティ推奨事項を選択し、[例外オプション] を選択してフォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="73680-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

!["例外オプション" のボタンがセキュリティ推奨事項のフライアウト内の場所である場所を表示します。](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="73680-123">デバイス グループ別の例外</span><span class="sxs-lookup"><span data-stu-id="73680-123">Exception by device group</span></span>

<span data-ttu-id="73680-124">現在のすべてのデバイス グループに例外を適用するか、特定のデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="73680-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="73680-125">今後のデバイス グループは例外に含まれません。</span><span class="sxs-lookup"><span data-stu-id="73680-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="73680-126">既に例外があるデバイス グループは、一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="73680-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="73680-127">特定のデバイス グループのみを選択した場合、推奨事項の状態は "アクティブ" から "部分的な例外" に変わります。</span><span class="sxs-lookup"><span data-stu-id="73680-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="73680-128">すべてのデバイス グループを選択すると、状態は "完全な例外" に変わります。</span><span class="sxs-lookup"><span data-stu-id="73680-128">The state will change to “full exception” if you select all the device groups.</span></span>

![デバイス グループのドロップダウンを表示する。](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="73680-130">フィルター処理されたビュー</span><span class="sxs-lookup"><span data-stu-id="73680-130">Filtered views</span></span>

<span data-ttu-id="73680-131">脅威と脆弱性の管理ページでデバイス グループでフィルター処理した場合、フィルター処理されたデバイス グループだけがオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="73680-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="73680-132">これは、脅威と脆弱性の管理ページでデバイス グループでフィルター処理するボタンです。</span><span class="sxs-lookup"><span data-stu-id="73680-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![選択したデバイス グループ フィルターを表示する。](images/tvm-selected-device-groups.png)

<span data-ttu-id="73680-134">フィルター処理されたデバイス グループを含む例外ビュー:</span><span class="sxs-lookup"><span data-stu-id="73680-134">Exception view with filtered device groups:</span></span>

![フィルター処理されたデバイス グループのドロップダウンを表示する。](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="73680-136">デバイス グループの数が多い</span><span class="sxs-lookup"><span data-stu-id="73680-136">Large number of device groups</span></span>

<span data-ttu-id="73680-137">組織に 20 を超えるデバイス グループがある場合は、フィルター処理されたデバイス グループ オプションの横にある **[** 編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="73680-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![多数のグループを編集する方法を示します。](images/tvm-exception-edit-groups.png)

<span data-ttu-id="73680-139">含めるデバイス グループを検索して選択できるフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73680-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="73680-140">[検索] の下にあるチェック マーク アイコンを選択して、すべてチェック/オフを解除します。</span><span class="sxs-lookup"><span data-stu-id="73680-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![大きなデバイス グループのフライアウトを表示する。](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="73680-142">グローバル例外</span><span class="sxs-lookup"><span data-stu-id="73680-142">Global exceptions</span></span>

<span data-ttu-id="73680-143">グローバル管理者のアクセス許可 (Microsoft Defender ATP 管理者と呼ばれる) がある場合は、グローバル例外を作成して取り消す事が可能です。</span><span class="sxs-lookup"><span data-stu-id="73680-143">If you have global administrator permissions (called Microsoft Defender ATP administrator), you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="73680-144">これは、 **組織内のすべての** 現在および将来のデバイス グループに影響を与え、同様のアクセス許可を持つユーザーだけが変更できます。</span><span class="sxs-lookup"><span data-stu-id="73680-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="73680-145">推奨事項の状態は、"active" から "完全な例外" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="73680-145">The recommendation state will change from “active” to “full exception.”</span></span>

![グローバル例外オプションの表示。](images/tvm-exception-global.png)

<span data-ttu-id="73680-147">次に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73680-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="73680-148">推奨事項がグローバル例外の下にある場合、新しく作成されたデバイス グループの例外は、グローバル例外の有効期限が切れるか取り消されるまで中断されます。</span><span class="sxs-lookup"><span data-stu-id="73680-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="73680-149">その後、新しいデバイス グループの例外は有効期限が切れるまで有効になります。</span><span class="sxs-lookup"><span data-stu-id="73680-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="73680-150">推奨事項に特定のデバイス グループの例外が既に存在し、グローバル例外が作成されている場合、デバイス グループの例外は有効期限が切れるか、グローバル例外が期限切れになる前に取り消されるまで中断されます。</span><span class="sxs-lookup"><span data-stu-id="73680-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="73680-151">妥当性</span><span class="sxs-lookup"><span data-stu-id="73680-151">Justification</span></span>

<span data-ttu-id="73680-152">問題のセキュリティ推奨事項を修復する代わりに、ファイルする必要がある例外の正当性を選択します。</span><span class="sxs-lookup"><span data-stu-id="73680-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="73680-153">位置合わせコンテキストに入力し、例外期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="73680-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="73680-154">次の一覧では、例外オプションの背後にある理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="73680-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="73680-155">**サード パーティ製** のコントロール - サード パーティ製品またはソフトウェアが既にこの推奨事項に対応している - この正当化の種類を選択すると、リスクが軽減され、露出スコアが下がり、セキュリティ スコアが向上します。</span><span class="sxs-lookup"><span data-stu-id="73680-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="73680-156">**代替軽減** - 内部ツールは既にこの推奨事項に対応しています - この位置合わせの種類を選択すると、リスクが軽減されたため、露出スコアが下がり、セキュリティスコアが向上します。</span><span class="sxs-lookup"><span data-stu-id="73680-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="73680-157">**リスクの受け** 入れ - リスクが低い、または推奨事項を実装するにはコストが高すぎます</span><span class="sxs-lookup"><span data-stu-id="73680-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="73680-158">**計画された修復 (猶予期間)** - 既に計画されているが、実行または承認を待っている</span><span class="sxs-lookup"><span data-stu-id="73680-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="73680-159">すべての例外を表示する</span><span class="sxs-lookup"><span data-stu-id="73680-159">View all exceptions</span></span>

<span data-ttu-id="73680-160">[修復] **ページの [** 例外] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="73680-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="73680-161">位置合わせ、種類、および状態でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="73680-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="73680-162">詳細を含むフライアウトを開く場合は、例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="73680-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="73680-163">デバイス グループごとの例外には、エクスポートできる例外が含むすべてのデバイス グループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73680-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="73680-164">関連する推奨事項を表示したり、例外を取り消したりできます。</span><span class="sxs-lookup"><span data-stu-id="73680-164">You can also view the related recommendation or cancel the exception.</span></span>

![[修復] ページに [例外] タブを表示します。](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="73680-166">例外を取り消す方法</span><span class="sxs-lookup"><span data-stu-id="73680-166">How to cancel an exception</span></span>

<span data-ttu-id="73680-167">例外を取り消す場合は、[修復] ページ **の [例外** ] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="73680-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="73680-168">例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="73680-168">Select the exception.</span></span>

<span data-ttu-id="73680-169">すべてのデバイス グループまたはグローバル例外の例外を取り消す場合は、[すべてのデバイス グループの例外をキャンセル **する] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="73680-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="73680-170">アクセス許可を持つデバイス グループの例外のみを取り消す事が可能です。</span><span class="sxs-lookup"><span data-stu-id="73680-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![[キャンセル] ボタン。](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="73680-172">特定のデバイス グループの例外をキャンセルする</span><span class="sxs-lookup"><span data-stu-id="73680-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="73680-173">特定のデバイス グループを選択して、例外を取り消します。</span><span class="sxs-lookup"><span data-stu-id="73680-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="73680-174">デバイス グループのフライアウトが表示され、[例外のキャンセル] **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="73680-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![特定のデバイス グループを選択する方法を示します。](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="73680-176">例外が適用された後の影響の表示</span><span class="sxs-lookup"><span data-stu-id="73680-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="73680-177">[セキュリティの推奨事項] ページで、[列のカスタマイズ] を選択し、(例外の後 **に)** 公開されているデバイスと影響 (例外の後) のチェック ボックス **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="73680-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![列のカスタマイズ オプションを表示する。](images/tvm-after-exceptions.png)

<span data-ttu-id="73680-179">[例外の後に公開されたデバイス] 列には、例外が適用された後も引き続き脆弱性にさらされている残りのデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73680-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="73680-180">露出に影響を与える例外の正当性には、'サード パーティコントロール' と '代替軽減' が含まれます。</span><span class="sxs-lookup"><span data-stu-id="73680-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="73680-181">その他の理由により、デバイスの露出は軽減されません。また、デバイスは引き続き公開されたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="73680-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="73680-182">影響 (例外の後) は、例外が適用された後の露出スコアまたはセキュリティで保護されたスコアへの影響が残ります。</span><span class="sxs-lookup"><span data-stu-id="73680-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="73680-183">スコアに影響を与える例外の正当性には、「サード パーティコントロール」と「代替軽減策」が含まれます。</span><span class="sxs-lookup"><span data-stu-id="73680-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="73680-184">その他の理由は、デバイスの露出を減らすことはないので、露出スコアと安全なスコアは変更されません。</span><span class="sxs-lookup"><span data-stu-id="73680-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![テーブル内の列を表示します。](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="73680-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="73680-186">Related topics</span></span>

- [<span data-ttu-id="73680-187">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="73680-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="73680-188">脆弱性を修復する</span><span class="sxs-lookup"><span data-stu-id="73680-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="73680-189">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="73680-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="73680-190">暴露スコア</span><span class="sxs-lookup"><span data-stu-id="73680-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="73680-191">デバイス向けの Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="73680-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
