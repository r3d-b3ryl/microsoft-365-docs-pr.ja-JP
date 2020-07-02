---
title: Microsoft コンプライアンススコアの改善アクションを操作する (プレビュー)
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
description: 改善アクションを使用して、Microsoft コンプライアンススコアでコンプライアンスアクティビティを管理する方法について説明します。
ms.openlocfilehash: d10e04f144595e1976f4b20e894ccbc299aade7b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016598"
---
# <a name="work-with-improvement-actions-in-compliance-score-preview"></a><span data-ttu-id="85a56-103">コンプライアンススコアの向上アクションを操作する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="85a56-103">Work with improvement actions in Compliance Score (preview)</span></span>

<span data-ttu-id="85a56-104">**この記事の内容**この記事では、改善アクションを伴う**コンプライアンスワークフローを管理**する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85a56-104">**In this article:** This article explains how to **manage your compliance workflow** with improvement actions.</span></span> <span data-ttu-id="85a56-105">実装とテストのための**改善アクションを割り当て**、完了のために一環に割り当て、**レポート**をエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85a56-105">Learn how to **assign improvement actions** for implementation and testing, assign them to assessors for completion, and export **reports**.</span></span>

## <a name="manage-compliance-workflows-with-improvement-actions"></a><span data-ttu-id="85a56-106">向上アクションを伴うコンプライアンスワークフローを管理する</span><span class="sxs-lookup"><span data-stu-id="85a56-106">Manage compliance workflows with improvement actions</span></span>

<span data-ttu-id="85a56-107">改善アクションにより、コンプライアンスアクティビティを集中管理できます。</span><span class="sxs-lookup"><span data-stu-id="85a56-107">Improvement actions centralize your compliance activities.</span></span> <span data-ttu-id="85a56-108">各改善アクションには、データ保護の規則および標準に沿った統合に役立つ詳細な実装ガイダンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="85a56-108">Each improvement action gives detailed implementation guidance to help you align with data protection regulations and standards.</span></span> <span data-ttu-id="85a56-109">実装とテストの作業を実行するために、組織内のユーザーにアクションを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-109">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="85a56-110">また、ドキュメント、メモ、およびレコードの状態の更新を、改善アクションの中に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="85a56-110">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

<span data-ttu-id="85a56-111">向上した機能はすべて、[改善アクション] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a56-111">All of your improvement are listed on the improvement actions page.</span></span> <span data-ttu-id="85a56-112">[向上したアクションの表示をフィルター処理し、状態を解釈する方法](compliance-score-setup.md#improvement-actions-page)について説明します。</span><span class="sxs-lookup"><span data-stu-id="85a56-112">Learn more about [how to filter your view of your improvement actions and interpret status states](compliance-score-setup.md#improvement-actions-page).</span></span>

## <a name="improvement-actions-details-page"></a><span data-ttu-id="85a56-113">向上アクションの詳細ページ</span><span class="sxs-lookup"><span data-stu-id="85a56-113">Improvement actions details page</span></span>

<span data-ttu-id="85a56-114">各改善アクションには、現在の状態と関連する標準および規制要件を示す詳細ページがあります。</span><span class="sxs-lookup"><span data-stu-id="85a56-114">Each improvement action has a details page showing its current status and the related standards and regulatory requirements.</span></span> <span data-ttu-id="85a56-115">詳細な実装ガイダンスには、実装のための適切なソリューションにアクセスするための [**今すぐ**開始」リンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85a56-115">Detailed implementation guidance includes a **Launch now** link taking you into the appropriate solution for implementation.</span></span> <span data-ttu-id="85a56-116">実装とテストのドキュメントは、改善アクションの詳細ページに直接添付できます。</span><span class="sxs-lookup"><span data-stu-id="85a56-116">You can attach implementation and testing documentation directly into an improvement action's details page.</span></span>

<span data-ttu-id="85a56-117">向上アクションの詳細ページを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="85a56-117">To view an improvement action’s details page:</span></span>

1. <span data-ttu-id="85a56-118">向上したアクションのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="85a56-118">Go to your improvement actions page.</span></span>
2. <span data-ttu-id="85a56-119">目的の改善アクションの行を選択すると、[詳細] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="85a56-119">Select the row of your intended improvement action, which opens its details page.</span></span>

<span data-ttu-id="85a56-120">画面の右上隅にある上下矢印を選択すると、リスト内の次または前の改善アクションを簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="85a56-120">You can easily view the next or previous improvement action in the list by selecting the up or down arrow in the upper-right corner of the screen.</span></span> <span data-ttu-id="85a56-121">[改善アクション] ページでリストをフィルター処理した場合は、上または下に移動して、そのフィルター処理されたリスト内の次のアイテムに移動します。</span><span class="sxs-lookup"><span data-stu-id="85a56-121">If you filtered your list on the improvement actions page, moving up or down takes you to the next item within that filtered list.</span></span>

## <a name="assign-improvement-actions"></a><span data-ttu-id="85a56-122">改善アクションを割り当てる</span><span class="sxs-lookup"><span data-stu-id="85a56-122">Assign improvement actions</span></span>

<span data-ttu-id="85a56-123">改善アクションで実装を開始するには、自分で作業を行ったり、別のユーザーに割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-123">To begin implementation work on an improvement action, you can do the work yourself or assign it to another user.</span></span> <span data-ttu-id="85a56-124">割り当てられた人物は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="85a56-124">The assigned person could be:</span></span>

- <span data-ttu-id="85a56-125">ビジネス ポリシーの所有者</span><span class="sxs-lookup"><span data-stu-id="85a56-125">A business policy owner</span></span>
- <span data-ttu-id="85a56-126">IT 担当者</span><span class="sxs-lookup"><span data-stu-id="85a56-126">An IT implementer</span></span>
- <span data-ttu-id="85a56-127">タスクを実行する責任を持つ別の従業員</span><span class="sxs-lookup"><span data-stu-id="85a56-127">Another employee with responsibility to perform the task</span></span>

<span data-ttu-id="85a56-128">適切な担当者を特定したら、[コンプライアンススコア](compliance-score-setup.md#set-user-permissions-and-assign-roles)(コンプライアンス管理者、コンプライアンスデータ管理者、セキュリティ管理者、または全体管理者) に十分な役割を持ち、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="85a56-128">Once you identify the appropriate assignee, be sure they hold a sufficient [role in Compliance Score](compliance-score-setup.md#set-user-permissions-and-assign-roles) (compliance administrator, compliance data administrator, security administrator, or global administrator) to perform the work, then take the following steps:</span></span>

1. <span data-ttu-id="85a56-129">[改善アクションの詳細] ページで、画面の左上のセクション付近にある [**状態の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-129">From the improvement actions details page, select **Edit status** near the upper-left section of the screen.</span></span>

2. <span data-ttu-id="85a56-130">[状態の編集] ウィンドウで、[**担当者] ボックスを**選択して、ユーザーの**候補**リストを表示します。</span><span class="sxs-lookup"><span data-stu-id="85a56-130">In the edit status flyout pane, select the **Assigned to** box to show a **Suggested people** list of users.</span></span> <span data-ttu-id="85a56-131">リストからユーザーを選択することも、そのユーザーの電子メールアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="85a56-131">You can select the user from the list, or type the email address of the person you want to assign it to.</span></span>

3. <span data-ttu-id="85a56-132">[**保存して閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-132">Select **Save and close**.</span></span> <span data-ttu-id="85a56-133">割り当てられたユーザーには、向上アクションが割り当てられたことを示す電子メールが送信され、ダッシュボードから向上アクションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-133">The assigned user will receive an email that the improvement action has been assigned to them, and they can then open the improvement action from their dashboard.</span></span>

<span data-ttu-id="85a56-134">割り当てられたユーザーは、推奨されるアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="85a56-134">The assigned user can then perform the recommended actions.</span></span>

## <a name="perform-work-and-store-documentation"></a><span data-ttu-id="85a56-135">作業およびストアのドキュメントを実行する</span><span class="sxs-lookup"><span data-stu-id="85a56-135">Perform work and store documentation</span></span>

<span data-ttu-id="85a56-136">実装とテストに関連するファイルやメモは、「**メモとドキュメント**」のセクションに直接アップロードできます。</span><span class="sxs-lookup"><span data-stu-id="85a56-136">You can upload files and notes related to implementation and testing work directly to the **Notes and documentation** section.</span></span> <span data-ttu-id="85a56-137">この環境は、セキュリティで保護された一元的なリポジトリで、コンプライアンスの標準および規制を満たすための制御の満足度を示すのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85a56-137">This environment is a secure, centralized repository to help you demonstrate satisfaction of controls to meet compliance standards and regulations.</span></span> <span data-ttu-id="85a56-138">読み取り専用アクセス権を持つユーザーは、このセクションの内容を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-138">Any user with read-only access can read content in this section.</span></span> <span data-ttu-id="85a56-139">編集権限を持つユーザーのみが、ファイルのアップロードとダウンロード、およびメモの入力や編集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-139">Only users with editing rights can upload and download files and enter or edit notes.</span></span>

<span data-ttu-id="85a56-140">「**メモとドキュメント**」セクションのフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a56-140">Fields in the **Notes and documentation** section include:</span></span>

### <a name="uploaded-documents"></a><span data-ttu-id="85a56-141">アップロードされたドキュメント</span><span class="sxs-lookup"><span data-stu-id="85a56-141">Uploaded documents</span></span>

- <span data-ttu-id="85a56-142">[**ドキュメントの管理**] を選択して、関連するファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="85a56-142">Select **Manage documents** to upload any relevant files.</span></span>
- <span data-ttu-id="85a56-143">[ドキュメントの管理] ポップアップウィンドウが開いたら、[**ドキュメントの追加**] を選択し、システムからファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-143">When the manage documents flyout pane opens, select **Add document**, then select your file from your system.</span></span> <span data-ttu-id="85a56-144">許可されるファイルの種類:</span><span class="sxs-lookup"><span data-stu-id="85a56-144">Accepted file types:</span></span>
    - <span data-ttu-id="85a56-145">ドキュメント (.doc、.xls、.ppt、.pdf、.pdf)</span><span class="sxs-lookup"><span data-stu-id="85a56-145">Documents (.doc, .xls, .ppt, .txt, .pdf)</span></span>
    - <span data-ttu-id="85a56-146">画像 (.jpg、.png)</span><span class="sxs-lookup"><span data-stu-id="85a56-146">Images (.jpg, .png)</span></span>
    - <span data-ttu-id="85a56-147">ビデオ (mkv)</span><span class="sxs-lookup"><span data-stu-id="85a56-147">Video (.mkv)</span></span>
    - <span data-ttu-id="85a56-148">圧縮ファイル (.zip、rar)</span><span class="sxs-lookup"><span data-stu-id="85a56-148">Compressed files (.zip, .rar)</span></span>
- <span data-ttu-id="85a56-149">ウィンドウでファイルを解決したら、[**閉じる**] を選択すると、添付ファイルが自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="85a56-149">Once your file resolves in the pane select **Close**, which automatically saves the file attachment.</span></span> <span data-ttu-id="85a56-150">アップロードした**ドキュメント**の下にファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85a56-150">You'll then see the file listed underneath **Uploaded documents**.</span></span>
- <span data-ttu-id="85a56-151">ドキュメントをダウンロードまたは削除するには、ドキュメントのリストの下にある [**ドキュメントの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-151">To download or delete the document, select **Manage documents** from underneath the list of documents.</span></span> <span data-ttu-id="85a56-152">フライアウトウィンドウで、ドキュメントの行をクリックまたはタップして強調表示にし、[**ダウンロード**] または [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-152">On the flyout pane, click or tap on the document row to highlight it, then select **Download** or **Delete**.</span></span>

### <a name="implementation-notes-test-notes-and-additional-notes"></a><span data-ttu-id="85a56-153">実装に関する注意事項、テストメモ、および追加メモ</span><span class="sxs-lookup"><span data-stu-id="85a56-153">Implementation notes, test notes, and additional notes</span></span>

- <span data-ttu-id="85a56-154">これら3つのフィールドのいずれかでメモを追加するには、これらのフィールドの下にある [**実装メモの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-154">To add notes in any of these three fields, select **Edit implementation notes** underneath any of these fields.</span></span>
- <span data-ttu-id="85a56-155">フライアウトウィンドウが開いたら、テキストフィールドに「notes」と入力し、[**保存して閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-155">When the flyout pane opens, enter notes in the text field, then select **Save and close**.</span></span>
- <span data-ttu-id="85a56-156">メモを編集するには、[**実装メモの編集**] を選択して編集を行ってから、[**保存して閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-156">To edit notes, select **Edit implementation notes**, make your edits, then select **Save and close**.</span></span>

<span data-ttu-id="85a56-157">メモフィールドに文字数の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="85a56-157">There's no character limit in the notes fields.</span></span> <span data-ttu-id="85a56-158">[改善アクションの詳細] ページで簡単に表示および編集できるように、ノートを短くすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85a56-158">We recommend keeping notes brief so that you can easily view and edit them from the improvement actions details page.</span></span>

## <a name="change-improvement-action-status"></a><span data-ttu-id="85a56-159">改善アクションの状態の変更</span><span class="sxs-lookup"><span data-stu-id="85a56-159">Change improvement action status</span></span>

<span data-ttu-id="85a56-160">各改善アクションの実装の状態と日付、およびテストの状態と日付を記録することができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-160">You can record the implementation status and date, and the test status and date, for each improvement action.</span></span> <span data-ttu-id="85a56-161">[**実装**] および [**テスト状態**] フィールドは、割り当てられた人物だけでなく、編集権限を持つすべてのユーザーが編集できます。</span><span class="sxs-lookup"><span data-stu-id="85a56-161">The **implementation** and **test status** fields can be edited by any user with editing permissions, not just by the assigned person.</span></span>

<span data-ttu-id="85a56-162">改善アクションの状態を編集するには、詳細ページの左上のセクションで [**状態の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-162">To edit an improvement action’s status, select **Edit status** on the upper-left section of the details page.</span></span> <span data-ttu-id="85a56-163">利用可能なフィールドとステータスのオプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="85a56-163">Below are the available fields and status options:</span></span>

- <span data-ttu-id="85a56-164">**実装の状態**</span><span class="sxs-lookup"><span data-stu-id="85a56-164">**Implementation status**</span></span>
    - <span data-ttu-id="85a56-165">**実装されて**いません-アクションはまだ実装されていません</span><span class="sxs-lookup"><span data-stu-id="85a56-165">**Not implemented** - action not yet implemented</span></span>
    - <span data-ttu-id="85a56-166">**実装**済み-アクションの実装</span><span class="sxs-lookup"><span data-stu-id="85a56-166">**Implemented** - action implemented</span></span>
    - <span data-ttu-id="85a56-167">**代替実装**-他のサードパーティ製ツールを使用した場合や、Microsoft の推奨事項に含まれていないその他のアクションを実行した場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-167">**Alternative implementation** - select this option if you used other third-party tools or took other actions not included in Microsoft recommendations</span></span>
    - <span data-ttu-id="85a56-168">**計画**済み-実装に対して計画されたアクション</span><span class="sxs-lookup"><span data-stu-id="85a56-168">**Planned** - action is planned for implementation</span></span>
    - <span data-ttu-id="85a56-169">**範囲内にない**-アクションは組織に関連せず、スコアに寄与しない</span><span class="sxs-lookup"><span data-stu-id="85a56-169">**Not in scope** – action isn’t relevant to your organization and doesn’t contribute to your score</span></span>
- <span data-ttu-id="85a56-170">**実装日**: 実装の状態が "実装" または "代替実装" の場合に選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="85a56-170">**Implementation date**: available to select when implementation status is "implemented" or "alternative implementation"</span></span>
- <span data-ttu-id="85a56-171">**テストの状態**: 実装状態が "実装" または "代替実装" の場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="85a56-171">**Test status**: available to select when implementation status is "implemented" or "alternative implementation":</span></span>
    - <span data-ttu-id="85a56-172">**未評価**-アクションはテストされていません</span><span class="sxs-lookup"><span data-stu-id="85a56-172">**Not assessed** – action has not been tested</span></span>
    - <span data-ttu-id="85a56-173">**成功**した実装は、査定官によって確認されています。</span><span class="sxs-lookup"><span data-stu-id="85a56-173">**Passed**- implementation has been verified by an assessor</span></span>
    - <span data-ttu-id="85a56-174">**失敗したリスクが低い**-テスト失敗、低リスク</span><span class="sxs-lookup"><span data-stu-id="85a56-174">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="85a56-175">**失敗中の危険度**-テスト失敗、中程度のリスク</span><span class="sxs-lookup"><span data-stu-id="85a56-175">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="85a56-176">**高リスクの失敗**–テスト失敗、高リスク</span><span class="sxs-lookup"><span data-stu-id="85a56-176">**Failed high risk** – testing failed, high risk</span></span>
    - <span data-ttu-id="85a56-177">**範囲内にない**–アクションは評価の対象外で、スコアに投稿されません</span><span class="sxs-lookup"><span data-stu-id="85a56-177">**Not in scope** – the action is out of scope for the assessment and doesn’t contribute to your score</span></span>
- <span data-ttu-id="85a56-178">**テスト日**: 予定表ポップアップを切り替えて日付を選択する</span><span class="sxs-lookup"><span data-stu-id="85a56-178">**Test date**: toggle through the calendar pop-up to select the date</span></span>

<span data-ttu-id="85a56-179">グループ間で共通のアクションを同期します。</span><span class="sxs-lookup"><span data-stu-id="85a56-179">Common actions synch across groups.</span></span> <span data-ttu-id="85a56-180">同じグループ内の2つの異なる評価が、自分が管理する改善アクションを共有する場合、アクションの実装の詳細またはステータスに対して行ったすべての更新は、グループ内の他の評価でも同じアクションに自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="85a56-180">When two different assessments in the same group share improvement actions that are managed by you, any updates you make to an action's implementation details or status will automatically synchronize to the same action in any other assessment in the group.</span></span> <span data-ttu-id="85a56-181">この同期によって、1つの改善アクションを実装し、複数の規制間でいくつかの要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-181">This synchronization allows you to implement one improvement action and meet several requirements across multiple regulations.</span></span>

## <a name="assign-improvement-action-to-assessor-for-completion"></a><span data-ttu-id="85a56-182">完了の評価を査定活動に割り当てる</span><span class="sxs-lookup"><span data-stu-id="85a56-182">Assign improvement action to assessor for completion</span></span>

<span data-ttu-id="85a56-183">作業を完了し、テストを実施して、証拠をアップロードした後、次の手順では、評価の評価に対する改善アクションを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="85a56-183">After you complete the work, conduct testing, and upload evidence, the next step is to assign the improvement action to an assessor for validation.</span></span>

<span data-ttu-id="85a56-184">一環の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85a56-184">Types of assessors include:</span></span>

- <span data-ttu-id="85a56-185">組織内のコントロールの検証を実行する内部一環</span><span class="sxs-lookup"><span data-stu-id="85a56-185">Internal assessors who perform validation of controls within your organization</span></span>
- <span data-ttu-id="85a56-186">Microsoft cloud services を監査するサードパーティの独立した組織など、コンプライアンスを調査、検証、および認定する外部一環</span><span class="sxs-lookup"><span data-stu-id="85a56-186">External assessors who examine, verify, and certify compliance, such as third-party independent organizations that audit Microsoft cloud services</span></span>

<span data-ttu-id="85a56-187">査定官は、作業を検証し、ドキュメントを調べて、適切なテスト状態を選択します。</span><span class="sxs-lookup"><span data-stu-id="85a56-187">The assessor validates the work and examines the documentation, and selects the appropriate test status.</span></span>

<span data-ttu-id="85a56-188">**テストの状態が "成功" に設定されている場合**は、処理が完了し、達成されたポイントが達成された数を示します。</span><span class="sxs-lookup"><span data-stu-id="85a56-188">**If test status is set to “Passed”**: the action is complete and the points achieved shows the maximum points achieved.</span></span> <span data-ttu-id="85a56-189">次に、これらのポイントは、全体的なコンプライアンススコアの方向に数えられます。</span><span class="sxs-lookup"><span data-stu-id="85a56-189">The points are then counted toward your overall compliance score.</span></span>

<span data-ttu-id="85a56-190">**[テストの状態] が [失敗] に設定されている場合**: アクションは要件を満たしていないため、査定官はそれを適切なユーザーに割り当てて、追加の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="85a56-190">**If test status is  set to “Failed”**: the action does not meet the requirements, and the assessor can assign it back to the appropriate user for additional work.</span></span>

## <a name="export-a-report"></a><span data-ttu-id="85a56-191">レポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="85a56-191">Export a report</span></span>

<span data-ttu-id="85a56-192">画面の左上隅にある [**エクスポート**] を選択して、すべての改善アクションと、[改善アクション] ページに表示されるフィルターカテゴリを含む Excel ワークシートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="85a56-192">Select **Export** in the upper-left corner of your screen to download an Excel worksheet containing all your improvement actions and the filter categories shown on the improvement actions page.</span></span>