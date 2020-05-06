---
title: Microsoft コンプライアンスマネージャーリリースノート
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-mar2020
description: Microsoft コンプライアンスマネージャーで、新機能および既知の問題に関する情報を含むリリースノートを表示します (今後のリリースで解決されます)。
ms.openlocfilehash: fb462939ef1b1bf0c6f7f4552359d50645b528f3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033707"
---
# <a name="microsoft-compliance-manager-preview-release-notes"></a><span data-ttu-id="75c2b-103">Microsoft コンプライアンスマネージャー (プレビュー) リリースノート</span><span class="sxs-lookup"><span data-stu-id="75c2b-103">Microsoft Compliance Manager (preview) release notes</span></span>

<span data-ttu-id="75c2b-104">コンプライアンスマネージャーの公開プレビューでは、今後の機能と更新プログラムに早期にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-104">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="75c2b-105">このページには、新機能、強化された機能、および現在のリリースの既知の問題に関する更新プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75c2b-105">This page contains updates on new features, improved functionality, and known issues with the current release.</span></span>

<span data-ttu-id="75c2b-106">[Service Trust Portal](https://servicetrust.microsoft.com)の[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager)ツールを使用して、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-106">You can use the [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="improved-template-creation-and-update-process"></a><span data-ttu-id="75c2b-107">テンプレートの作成および更新プロセスの向上</span><span class="sxs-lookup"><span data-stu-id="75c2b-107">Improved template creation and update process</span></span>

<span data-ttu-id="75c2b-108">評価用にテンプレートをインポート、エクスポート、変更するプロセスが更新されました。</span><span class="sxs-lookup"><span data-stu-id="75c2b-108">We've updated the process for importing, exporting, and modifying templates for assessments.</span></span> <span data-ttu-id="75c2b-109">新しい単純化された操作により、独自の評価をワークフローに取り込むことが容易になり、更新を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-109">The new, simplified experience will make it easier for you to bring your own assessments into your workflow and keep them updated.</span></span>

### <a name="the-old-process"></a><span data-ttu-id="75c2b-110">古いプロセス</span><span class="sxs-lookup"><span data-stu-id="75c2b-110">The old process</span></span>

<span data-ttu-id="75c2b-111">コンプライアンスマネージャーでテンプレートを作成するには、2つの方法がありました。</span><span class="sxs-lookup"><span data-stu-id="75c2b-111">There were two ways of creating a template in Compliance Manager.</span></span> <span data-ttu-id="75c2b-112">既存のテンプレートをコピーしたり、Excel スプレッドシートからテンプレートデータを新しいテンプレートにインポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-112">You could copy an existing template, or import template data from an Excel spreadsheet into a new template.</span></span> <span data-ttu-id="75c2b-113">[**テンプレート**] ページで、[ **+ テンプレートの追加**] を選択して、名前を入力し、ディメンションを選択し、Excel ファイルを特定の形式とスキーマでアップロードすることによって、新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-113">From your **Templates** page, you'd select **+ Add template** to create a brand new template by entering a name, selecting dimensions, and uploading an Excel file with a specific format and schema.</span></span> <span data-ttu-id="75c2b-114">または、[**既存のテンプレートからコピー**する] ボックスをオンにし、コピーするテンプレートを選択して、ディメンションを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-114">Or you could check the **Copy from an existing template** box, select a template to copy, and verify dimensions.</span></span> <span data-ttu-id="75c2b-115">デザインのカスタマイズテンプレートを作成した後、[**カスタムコントロールの追加**] を選択することによって、複数ステップのプロセスが必要になりました。</span><span class="sxs-lookup"><span data-stu-id="75c2b-115">Design customization your template required a multi-step process that began by selecting **Add custom control** after creating your template.</span></span>

### <a name="the-new-process"></a><span data-ttu-id="75c2b-116">新しいプロセス</span><span class="sxs-lookup"><span data-stu-id="75c2b-116">The new process</span></span>

<span data-ttu-id="75c2b-117">新しいテンプレートを簡単に作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="75c2b-117">We made it easier for you to create new templates.</span></span> <span data-ttu-id="75c2b-118">ワンステップの**拡張**処理では、自分のアクションとコントロールを含むスプレッドシートを既存の Microsoft テンプレートに追加して、独自のカスタマイズされたバージョンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-118">In a one-step **extension** process, you can add a spreadsheet with your actions and controls to an existing Microsoft template to make your own customized version.</span></span> <span data-ttu-id="75c2b-119">[コンプライアンスマネージャー] の [**テンプレート**] ページで、[ **+ テンプレートの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-119">At your **Templates** page in Compliance Manager, select **+ Add template**.</span></span> <span data-ttu-id="75c2b-120">**テンプレート**のポップアップウィンドウで、[**グローバルテンプレートからの拡張機能を作成**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="75c2b-120">On the **Template** flyout pane, select the **Create extension from global template** checkbox.</span></span> <span data-ttu-id="75c2b-121">以前のバージョンよりも複雑な Excel の新しい形式を使用して、カスタマイズを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-121">You can add customizations with a new Excel format that is less complex than the previous one.</span></span> <span data-ttu-id="75c2b-122">この新しいプロセスにより、**既存のテンプレートの**以前のコピーが置き換えられ、**カスタムコントロール**関数が追加されます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-122">This new process replaces the former **Copy from an existing template** and **Add custom control** functions.</span></span>

<span data-ttu-id="75c2b-123">以下に示すバージョン管理プロセスによって元の評価が更新されるたびに、カスタマイズされた評価はそれらの更新を継承し、カスタムコントロールを保持します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-123">Each time the original assessment is updated through the versioning process outlined below, your customized assessment will inherit those updates and keep your custom controls.</span></span>

<span data-ttu-id="75c2b-124">また、既存のテンプレートを変更することも簡単です。</span><span class="sxs-lookup"><span data-stu-id="75c2b-124">It's also easier to modify your own existing templates.</span></span> <span data-ttu-id="75c2b-125">テンプレートをエクスポートし、同じブックで変更を加えてから、編集内容を保存してインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-125">You can export your template, make changes in the same workbook, then import it with your edits saved.</span></span>

<span data-ttu-id="75c2b-126">この新しいプロセスを使用して[テンプレートを作成する](working-with-compliance-manager.md#templates)詳細な手順を表示します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-126">View detailed instructions on [creating templates](working-with-compliance-manager.md#templates) with this new process.</span></span>

## <a name="versioning-notice-and-control"></a><span data-ttu-id="75c2b-127">バージョン管理の通知と制御</span><span class="sxs-lookup"><span data-stu-id="75c2b-127">Versioning notice and control</span></span>

<span data-ttu-id="75c2b-128">組織は、コンプライアンスマネージャーの2020年4月リリースで更新された評価を受け取って、認定および規制の更新に対応できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="75c2b-128">Your organization received updated assessments in the April 2020 release of Compliance Manager to help you align with certification and regulation updates.</span></span> <span data-ttu-id="75c2b-129">進む前に、**バージョン管理警告**を使用して、今後のすべての更新を理解し、承諾するための明確な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-129">Moving forward, we'll provide a clear way for you to understand and accept all future updates through **versioning alerts**.</span></span>

<span data-ttu-id="75c2b-130">評価のテンプレートまたは改善アクションの更新が可能になると、更新が準備できたことを通知する警告アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-130">Whenever an update is available for an assessment's template or an improvement action, an alert icon notifies you that an update is ready.</span></span> <span data-ttu-id="75c2b-131">このアイコンをクリックすると、更新プログラムについて説明するポップアップウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-131">When you click on that icon, a pop-up window explains the update and prompts you to accept.</span></span> <span data-ttu-id="75c2b-132">通知アイコンを選択すると、更新プログラムの説明を示すフライアウトウィンドウが表示され、承諾を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-132">Selecting the alert icon reveals a flyout pane explaining the update and prompting you to accept.</span></span> <span data-ttu-id="75c2b-133">[評価の更新の受け入れ](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-133">Learn more about [accepting updates to assessments](working-with-compliance-manager.md#versioning-alerts-for-assessment-updates).</span></span>

## <a name="common-actions-will-synch-status-across-groups"></a><span data-ttu-id="75c2b-134">共通のアクションにより、グループ間で状態が同期されます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-134">Common actions will synch status across groups</span></span>

<span data-ttu-id="75c2b-135">組織が複数の評価グループを使用している場合、**技術的**な操作 (つまり、組織全体に影響を与えるアクション) の動作が変更されています。</span><span class="sxs-lookup"><span data-stu-id="75c2b-135">If your organization has multiple groups of assessments, the behavior of **Technical** actions (that is, actions affecting your entire organization) has changed.</span></span> <span data-ttu-id="75c2b-136">グループ間で重複するアクションは、1つのアクションにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="75c2b-136">Any duplicate actions across groups have been combined into one single action.</span></span> <span data-ttu-id="75c2b-137">この1つのアクションには、複製されたすべてのメモと証拠が重複バージョンから含まれています。</span><span class="sxs-lookup"><span data-stu-id="75c2b-137">That single action contains all uploaded notes and evidence from the duplicate versions.</span></span> <span data-ttu-id="75c2b-138">この変更により、技術的なアクションは同じグループに属していた場合と同じように動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-138">With this change, technical actions will now behave as they did when they belonged to the same group.</span></span> <span data-ttu-id="75c2b-139">あるグループまたは評価のアクションに加えられた変更は、すべてのインスタンスに反映されるようになります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-139">Any change made to the action in one group or assessment will now be reflected in all instances.</span></span> <span data-ttu-id="75c2b-140">**実装の状態**、**実装日**、**テストの状態**、およびテストの**日付**は、最新の更新プログラムを反映しています。</span><span class="sxs-lookup"><span data-stu-id="75c2b-140">The **Implementation Status**, **Implementation Date**, **Test Status**, and **Test Date** will reflect the most recent updates.</span></span>

## <a name="language-support"></a><span data-ttu-id="75c2b-141">言語サポート</span><span class="sxs-lookup"><span data-stu-id="75c2b-141">Language support</span></span>

<span data-ttu-id="75c2b-142">コンプライアンスマネージャーは、英語 (簡体字)、中国語 (繁体字)、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語 (ブラジル)、ロシア語、スペイン語に加えて、次の言語で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="75c2b-142">Compliance Manager is now available in the following languages in addition to English: Chinese (Simplified), Chinese (Traditional), French, German, Italian, Japanese, Korean, Portuguese (Brazil), Russian, and Spanish.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="75c2b-143">コンプライアンスマネージャーの既知の問題 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="75c2b-143">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="75c2b-144">次のセクションでは、現在のリリースのコンプライアンスマネージャーの既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-144">The following section covers known issues in the current release of Compliance Manager.</span></span>

### <a name="dimension-values"></a><span data-ttu-id="75c2b-145">次元の値</span><span class="sxs-lookup"><span data-stu-id="75c2b-145">Dimension values</span></span>

<span data-ttu-id="75c2b-146">2020年4月リリースの間のデータ移行の結果として、組織によっては評価とテンプレートに "custom" という**製品**または**証明書**の値が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-146">As a result of data migration during the April 2020 release, some organizations may see a **Product** or **Certification** value of "custom" in their assessments and templates.</span></span> <span data-ttu-id="75c2b-147">この値は、**製品**または**証明書**のフィールドが空白の場合に自動的に挿入され、データワークフローには影響しません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-147">This value was inserted automatically if the **Product** or **Certification** fields were blank, and there won't be an effect on data workflows.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="75c2b-148">コンプライアンス スコア</span><span class="sxs-lookup"><span data-stu-id="75c2b-148">Compliance Score</span></span>

- <span data-ttu-id="75c2b-149">**スコープ内にない**とマークされたアクションアイテムの場合、アクションアイテムに割り当てられているスコアは、コンプライアンススコアの計算から除外されません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-149">For Action Items marked as **Not in Scope**, the score assigned to the Action Item isn't excluded from the compliance score calculation.</span></span> <span data-ttu-id="75c2b-150">**スコープにない**アクションアイテムは、コンプライアンススコアを増加しません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-150">Action Items marked **Not in Scope** don't increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="75c2b-151">セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="75c2b-151">Secure Score</span></span>

- <span data-ttu-id="75c2b-152">セキュリティで保護されたスコアの結果は、一部の Microsoft 365 および Office 365 サブスクリプションの一部のアクションアイテムでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-152">Secure Score results aren't available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="75c2b-153">このような場合は、セキュリティで保護されたスコアの結果を検出できません**でした**。</span><span class="sxs-lookup"><span data-stu-id="75c2b-153">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="75c2b-154">セキュリティで保護されたスコアの結果が、対応するポリシーおよび完了していないアクションアイテムに対して返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-154">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="75c2b-155">新しいテナントでは、すべてのアクションのセキュリティで保護されたスコアの更新が自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-155">For new tenants, Secure Score updates for all actions are automatically turned on.</span></span> <span data-ttu-id="75c2b-156">全体管理者は、セキュリティで保護されたスコア継続的更新スイッチを off に設定して、すべてのアクションの更新をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-156">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
  - <span data-ttu-id="75c2b-157">**注**: 組織が最初に Microsoft 365 または Office 365 を展開するときは、セキュリティで保護されたスコアがデータを完全に収集してスコアになるまでに約7日かかります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-157">**Note**: when organizations first deploy Microsoft 365 or Office 365, it takes approximately seven days for Secure Score to fully collect data and factor it into your score.</span></span> <span data-ttu-id="75c2b-158">その間、「Secure Score continuous update」スイッチを [**オフ**] に設定し、**実装**するアクションを手動で設定すると、スコアに対する処理がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-158">During that time, setting the Secure Score continuous update switch to **Off** and manually setting an action to **implemented** will count that action toward your score.</span></span> <span data-ttu-id="75c2b-159">最初の7日より後に、セキュリティで保護されたスコア継続的更新をオンにすると、それ以降の継続的な監視が有効になります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-159">After the initial seven days, turning Secure Score continuous update back on will enable continuous monitoring from that point forward.</span></span>
- <span data-ttu-id="75c2b-160">セキュリティで保護されたスコアの更新が有効になっている場合、アクションはセキュリティで保護されたスコアでアクティブに監視されますが、アクションのテスト日は監視を反映するように更新されません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-160">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action's test date won't be updated to reflect monitoring.</span></span>
- <span data-ttu-id="75c2b-161">新しい評価が作成されると、スコアは自動的に Microsoft 管理の制御スコアとセキュリティで保護されたスコアの統合を含みます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-161">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>
- <span data-ttu-id="75c2b-162">セキュリティで保護されたスコア統合でサポートされていないアクションは、手動で実装できます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-162">Any actions that are not supported by Secure Score integration can be manually implemented.</span></span> <span data-ttu-id="75c2b-163">手動による実装では、そのアクションのグループのスコアが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="75c2b-163">A manual implementation will factor into the score for that action's group.</span></span>

### <a name="export"></a><span data-ttu-id="75c2b-164">Export</span><span class="sxs-lookup"><span data-stu-id="75c2b-164">Export</span></span>

- <span data-ttu-id="75c2b-165">テンプレートの状態が [**インポート**済みまたは**保留中の承認**] に設定されている場合、JSON へのテンプレートのエクスポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="75c2b-165">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="75c2b-166">サポート対象ブラウザー</span><span class="sxs-lookup"><span data-stu-id="75c2b-166">Supported browsers</span></span>

- <span data-ttu-id="75c2b-167">Microsoft Edge、Chrome、および Safari の最新バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="75c2b-167">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="75c2b-168">ブラウザーを更新するまで、更新されたデータが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-168">There may be instances where updated data doesn't appear until your browser is refreshed.</span></span>
- <span data-ttu-id="75c2b-169">Microsoft Edge のプレビューバージョンはサポートされていませんが、既知の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-169">The preview version of Microsoft Edge isn't supported but has no known issues.</span></span>
- <span data-ttu-id="75c2b-170">Internet Explorer はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="75c2b-170">Internet Explorer isn't supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="75c2b-171">セッションのタイムアウト</span><span class="sxs-lookup"><span data-stu-id="75c2b-171">Session timeout</span></span>

- <span data-ttu-id="75c2b-172">セッションがタイムアウトになると、"問題が発生しました" というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="75c2b-172">When a session times out, a "Something went wrong" error may appear.</span></span> <span data-ttu-id="75c2b-173">解決するには、[[コンプライアンスマネージャー](https://servicetrust.microsoft.com/ComplianceManager) ] に移動して、再度ログインします。</span><span class="sxs-lookup"><span data-stu-id="75c2b-173">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
