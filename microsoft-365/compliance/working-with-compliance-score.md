---
title: Microsoft コンプライアンススコアの使用
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
description: Microsoft コンプライアンススコアのワークフローツールを使用して、組織のコンプライアンスの管理に役立つ方法について説明します。
ms.openlocfilehash: 9c3871db720666319eb8a0523ff8150efd753f91
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802137"
---
# <a name="working-with-microsoft-compliance-score-preview"></a><span data-ttu-id="afa28-103">Microsoft コンプライアンススコアの処理 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="afa28-103">Working with Microsoft Compliance Score (Preview)</span></span>

## <a name="managing-your-workflow-with-improvement-actions"></a><span data-ttu-id="afa28-104">改善アクションを使用してワークフローを管理する</span><span class="sxs-lookup"><span data-stu-id="afa28-104">Managing your workflow with improvement actions</span></span>

<span data-ttu-id="afa28-105">コンプライアンススコアの向上アクションを使用すると、コンプライアンスワークフローを一元化できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-105">Using improvement actions in Compliance Score centralizes your compliance workflows.</span></span> <span data-ttu-id="afa28-106">向上処置は、データ保護の規則と標準に合わせて推奨されるアクションを提案し、実装に関する詳細なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="afa28-106">Improvement actions suggest recommended actions to align with data protection regulations and standards, and provide detailed implementation guidance.</span></span> <span data-ttu-id="afa28-107">必要な実装とテスト作業を実行するために、ユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-107">You can assign them to users to perform the necessary implementation and testing work.</span></span> <span data-ttu-id="afa28-108">また、ドキュメントとメモを保存して、[改善] アクション自体の [進捗の更新] を直接記録することもできます。</span><span class="sxs-lookup"><span data-stu-id="afa28-108">You can also store documentation and notes, and record status updates right in the improvement action itself.</span></span>

## <a name="view-your-improvement-actions"></a><span data-ttu-id="afa28-109">改善アクションを表示する</span><span class="sxs-lookup"><span data-stu-id="afa28-109">View your improvement actions</span></span>

<span data-ttu-id="afa28-110">コンプライアンススコアのダッシュボードには、**主要な改善アクション**が表示されます。これには、最も重要な問題を解決するための最も多くのポイントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="afa28-110">The Compliance Score dashboard shows your **key improvement actions**—the ones with the most available points which address the most important issues.</span></span>

<span data-ttu-id="afa28-111">すべての改善アクションを表示するには、ダッシュボードの [**改善アクション**] タブを選択するか、ダッシュボードの主な改善アクションの一覧の下にある [**すべての改善アクションの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-111">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard, or select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span> <span data-ttu-id="afa28-112">これにより、[向上した**アクション**] ページが表示されます。このページでは、組織のすべての改善アクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-112">This brings you to the the **Improvement actions** page, where you can see all of your organization’s improvement actions.</span></span>

<span data-ttu-id="afa28-113">アクションのリストが長い場合は、ビューをフィルター処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="afa28-113">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="afa28-114">これを行うには、アクションリストの右上隅にある [**フィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-114">To do this, select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="afa28-115">[**フィルター**の選択] ウィンドウが表示されたら、規制と基準、ソリューション、およびグループに基づいて、目的の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-115">When the **Filters** flyout pane appears, then select your desired criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="afa28-116">右上隅の [**グループ**] を選択してビューをカスタマイズすることもできます。また、ドロップダウンメニューから、グループ、ソリューション、カテゴリ、アクションの種類、または状態別に表示するように選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-116">You can also customize your view by selecting **Group** in the upper-right corner and, from the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="afa28-117">このページの既定のビューには、向上したアクションが [**成功**] テストの状態として表示されません。</span><span class="sxs-lookup"><span data-stu-id="afa28-117">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="afa28-118">テストに合格したアクションを表示するには、[**フィルター** ] ポップアップウィンドウの [**成功**] ボックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="afa28-118">To view actions that have passed testing, check the **Passed** box in the **Filters** flyout pane.</span></span> <span data-ttu-id="afa28-119">スコアに対して**通過**したカウントがテスト状態であるアクションのみ。</span><span class="sxs-lookup"><span data-stu-id="afa28-119">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="afa28-120">[改善アクション] ページには、改善アクションごとに次のデータポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-120">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="afa28-121">**スコアの影響**: アクションを完了すると、全体的なスコアが増加するポイント</span><span class="sxs-lookup"><span data-stu-id="afa28-121">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="afa28-122">**規制**: アクションに関連する規制または標準</span><span class="sxs-lookup"><span data-stu-id="afa28-122">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="afa28-123">**グループ**: アクションを割り当てたグループ。</span><span class="sxs-lookup"><span data-stu-id="afa28-123">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="afa28-124">**解決策**: アクションを実行するために使用できるソリューション</span><span class="sxs-lookup"><span data-stu-id="afa28-124">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="afa28-125">**評価**: アクションが存在する評価 (特定のコンプライアンスの目標を達成するために統制したもの)</span><span class="sxs-lookup"><span data-stu-id="afa28-125">**Assessments**: the assessment  (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="afa28-126">**カテゴリ**: 関連データ保護カテゴリ (情報の保護、デバイスの管理など)</span><span class="sxs-lookup"><span data-stu-id="afa28-126">**Categories**: the related data protection category (i.e., protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="afa28-127">**テストの状態**:</span><span class="sxs-lookup"><span data-stu-id="afa28-127">**Test status**:</span></span>
    - <span data-ttu-id="afa28-128">**なし**-進捗状況の更新は記録されません</span><span class="sxs-lookup"><span data-stu-id="afa28-128">**None** - no status update recorded</span></span>
    - <span data-ttu-id="afa28-129">**評価されて**いません-テストが開始されていません</span><span class="sxs-lookup"><span data-stu-id="afa28-129">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="afa28-130">**スコープ**外-コンプライアンススコアの計算から除外され、スコアが増加しない。</span><span class="sxs-lookup"><span data-stu-id="afa28-130">**Not in scope** - is excluded from Compliance Score calculation and does not increase your score</span></span>
    - <span data-ttu-id="afa28-131">**部分的にテスト**されたテストはまだ完了していません</span><span class="sxs-lookup"><span data-stu-id="afa28-131">**Partially tested** - testing is not yet complete</span></span>
    - <span data-ttu-id="afa28-132">**高リスクの失敗**-実装のテストが失敗し、該当する標準に準拠していない場合のリスクが高い</span><span class="sxs-lookup"><span data-stu-id="afa28-132">**Failed high risk** - testing of implementation has failed, and the risk of non-compliance with the applicable standard is high</span></span>
    - <span data-ttu-id="afa28-133">**成功した実装のテスト**が成功した</span><span class="sxs-lookup"><span data-stu-id="afa28-133">**Passed** - implementation successfully tested</span></span>
- <span data-ttu-id="afa28-134">**ポイント**されたポイント: 獲得できる最大数に達したことを示します。</span><span class="sxs-lookup"><span data-stu-id="afa28-134">**Pointed achieved**: shows points achieved out of the maximum that could be earned</span></span>

### <a name="improvement-actions-details"></a><span data-ttu-id="afa28-135">向上アクションの詳細</span><span class="sxs-lookup"><span data-stu-id="afa28-135">Improvement actions details</span></span>

<span data-ttu-id="afa28-136">各改善アクションには、詳細ページがあります。</span><span class="sxs-lookup"><span data-stu-id="afa28-136">Each improvement action has a details page.</span></span> <span data-ttu-id="afa28-137">このページには、詳細な実装手順が記載されています。ここでは、推奨されるアクションを実行し**て、関連**する標準および規制要件に対応する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afa28-137">This page contains detailed implementation instructions, which explain how to take the recommended actions to address the related standards and regulatory requirements listed under the **At a glance** header.</span></span>

<span data-ttu-id="afa28-138">[詳細] ページでは、推奨されるアクションを開始したり、他のユーザーに作業を割り当てたり、状態を更新したり、メモやドキュメントを添付したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-138">The details page is where you can launch the recommended action or assign the work to another user, update status, and attach notes and documentation.</span></span>

<span data-ttu-id="afa28-139">向上アクションの詳細ページを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="afa28-139">To view an improvement action's details page:</span></span>

1. <span data-ttu-id="afa28-140">向上したアクションのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="afa28-140">Go to your improvement actions page.</span></span>
2. <span data-ttu-id="afa28-141">目的の改善アクションの行の任意の場所をクリックまたはタップして、[詳細] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="afa28-141">Click or tap anywhere in the row of your intended improvement action, which opens its details page.</span></span>

<span data-ttu-id="afa28-142">画面の右上隅にある上下矢印を選択すると、リスト内の次または前の改善アクションを簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-142">You can easily view the next or previous improvement action in the list by selecting the up or down arrow in the upper-right corner of the screen.</span></span> <span data-ttu-id="afa28-143">[改善アクション] ページでリストをフィルター処理した場合、上または下に移動すると、そのフィルターされたリスト内の次のアイテムに移動します。</span><span class="sxs-lookup"><span data-stu-id="afa28-143">If you filtered your list on the improvement actions page, moving up or down will take you to the next item within that filtered list.</span></span>

## <a name="assign-improvement-actions"></a><span data-ttu-id="afa28-144">改善アクションを割り当てる</span><span class="sxs-lookup"><span data-stu-id="afa28-144">Assign improvement actions</span></span>

<span data-ttu-id="afa28-145">改善アクションで実装を開始するには、自分で作業を行ったり、別のユーザーに割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-145">To begin implementation work on an improvement action, you can do the work yourself or assign it to another user.</span></span> <span data-ttu-id="afa28-146">割り当てられた人物は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="afa28-146">The assigned person could be:</span></span>

- <span data-ttu-id="afa28-147">ビジネス ポリシーの所有者</span><span class="sxs-lookup"><span data-stu-id="afa28-147">A business policy owner</span></span>
- <span data-ttu-id="afa28-148">IT 担当者</span><span class="sxs-lookup"><span data-stu-id="afa28-148">An IT implementer</span></span>
- <span data-ttu-id="afa28-149">タスクを実行する責任を持つ別の従業員</span><span class="sxs-lookup"><span data-stu-id="afa28-149">Another employee with responsibility to perform the task</span></span> 

<span data-ttu-id="afa28-150">適切な人物が特定されたら、コンプライアンススコア (コンプライアンス管理者、コンプライアンスデータ管理者、セキュリティ管理者、または全体管理者) に十分な[役割](compliance-score-setup.md#set-user-permissions-and-assign-roles)を持ち、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="afa28-150">Once the proper person is identified, be sure they hold a sufficient [role](compliance-score-setup.md#set-user-permissions-and-assign-roles) in Compliance Score (compliance administrator, compliance data administrator, security administrator, or global administrator) to perform the work, then take the following steps:</span></span> 

1. <span data-ttu-id="afa28-151">[改善アクションの詳細] ページで、画面の左上のセクション付近にある [**状態の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-151">From the improvement actions details page, select **Edit status** near the upper-left section of the screen.</span></span> 

2. <span data-ttu-id="afa28-152">[状態の編集] ウィンドウで、[**担当**者] ボックスをクリックまたはタップします。これにより、ユーザーリストが**提案**されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-152">In the edit status flyout pane, click or tap in the **Assigned to** box, which populates a **Suggested people** list of users.</span></span> <span data-ttu-id="afa28-153">リストからユーザーを選択することも、アクションを割り当てる人物の電子メールアドレスを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="afa28-153">You can select the user from the list, or type the email address of the person to whom you want to assign the action.</span></span>

3. <span data-ttu-id="afa28-154">[**保存して閉じる**] を選択して、割り当てを完了します。</span><span class="sxs-lookup"><span data-stu-id="afa28-154">Select **Save and close** to complete the assignment.</span></span> <span data-ttu-id="afa28-155">割り当てられたユーザーには、向上アクションが割り当てられたことを示す電子メールが送信され、ダッシュボードから向上アクションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-155">The assigned user will receive an email that the improvement action has been assigned to them, and they can then open the improvement action from their dashboard.</span></span>

<span data-ttu-id="afa28-156">割り当てられたユーザーは、実装手順に記載されている推奨されるアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-156">The assigned user can then perform the recommended actions outlined in the implementation instructions.</span></span>

## <a name="perform-work-and-store-documentation"></a><span data-ttu-id="afa28-157">作業およびストアのドキュメントを実行する</span><span class="sxs-lookup"><span data-stu-id="afa28-157">Perform work and store documentation</span></span>

<span data-ttu-id="afa28-158">実装作業を実行するときは、「**メモとドキュメント**」のセクションの「改善策」アクションに直接ファイルとメモをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="afa28-158">When you perform implementation work, you can upload files and notes directly to the improvement action in the **Notes and documentation** section.</span></span> <span data-ttu-id="afa28-159">これにより、セキュリティで保護された一元的なリポジトリが提供され、コンプライアンスの標準および規制を満たすための制御の満足度を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-159">This provides a secure, centralized repository to help you demonstrate satisfaction of controls to meet compliance standards and regulations.</span></span> <span data-ttu-id="afa28-160">読み取り専用アクセス権を持つユーザーは、このセクションの内容を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-160">Any user with read-only access can read content in this section.</span></span> <span data-ttu-id="afa28-161">フィールドをアップロード、ダウンロード、または削除したり、メモを入力または編集したりする機能は、編集権限を持つロールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-161">The ability to upload, download, or delete fields, or to enter or edit notes, is restricted to roles with editing rights.</span></span>

<span data-ttu-id="afa28-162">「**メモとドキュメント**」セクションのフィールドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="afa28-162">Fields in the **Notes and documentation** section include:</span></span>

<span data-ttu-id="afa28-163">**アップロードされたドキュメント**</span><span class="sxs-lookup"><span data-stu-id="afa28-163">**Uploaded documents**</span></span>

- <span data-ttu-id="afa28-164">[**ドキュメントの管理**] を選択して、関連するファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="afa28-164">Select **Manage documents** to upload any relevant files.</span></span>
- <span data-ttu-id="afa28-165">[ドキュメントの管理] ポップアップウィンドウが開いたら、[**ドキュメントの追加**] を選択し、システムからファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-165">When the manage documents flyout pane opens, select **Add document**, then select your file from your system.</span></span> <span data-ttu-id="afa28-166">許可されるファイルの種類:</span><span class="sxs-lookup"><span data-stu-id="afa28-166">Accepted file types:</span></span> 
  - <span data-ttu-id="afa28-167">ドキュメント (.doc、.xls、.ppt、.pdf、.pdf)</span><span class="sxs-lookup"><span data-stu-id="afa28-167">Documents (.doc, .xls, .ppt, .txt, .pdf)</span></span>
  - <span data-ttu-id="afa28-168">画像 (.jpg、.png)</span><span class="sxs-lookup"><span data-stu-id="afa28-168">Images (.jpg, .png)</span></span>
  - <span data-ttu-id="afa28-169">ビデオ (mkv)</span><span class="sxs-lookup"><span data-stu-id="afa28-169">Video (.mkv)</span></span>
  - <span data-ttu-id="afa28-170">圧縮ファイル (.zip、rar)</span><span class="sxs-lookup"><span data-stu-id="afa28-170">Compressed files (.zip, .rar)</span></span>
- <span data-ttu-id="afa28-171">ウィンドウでファイルを解決したら、[**閉じる**] を選択します。これにより、添付ファイルが自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-171">Once your file resolves in the pane, select **Close,** which automatically saves the file attachment.</span></span> <span data-ttu-id="afa28-172">アップロードされたドキュメントの下にファイルが表示され**ます。**</span><span class="sxs-lookup"><span data-stu-id="afa28-172">You will then see the file listed underneath **Uploaded documents.**</span></span> 
- <span data-ttu-id="afa28-173">ドキュメントをダウンロードまたは削除するには、ドキュメントのリストの下にある [**ドキュメントの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-173">To download or delete the document, select **Manage documents** from  underneath the list of documents.</span></span> <span data-ttu-id="afa28-174">フライアウトウィンドウで、ドキュメントの行をクリックまたはタップして強調表示にし、[**ダウンロード**] または [削除] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="afa28-174">On the flyout pane, click or tap on the document row to highlight it, then select **Download** or **Delete.**</span></span>

<span data-ttu-id="afa28-175">**実装、テスト、および追加のメモ**</span><span class="sxs-lookup"><span data-stu-id="afa28-175">**Implementation, Test, and Additional notes**</span></span>

- <span data-ttu-id="afa28-176">これら3つのフィールドのいずれかでメモを追加するには、任意のフィールドの下にある [**実装メモの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-176">To add notes in any of these three fields, select **Edit implementation notes** underneath any of thse fields.</span></span>
- <span data-ttu-id="afa28-177">フライアウトウィンドウが開いたら、テキストフィールドに「notes」と入力し、[**保存して閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-177">When the flyout pane opens, enter notes in the text field, then select **Save and close**.</span></span>
- <span data-ttu-id="afa28-178">メモを編集するには、[**実装メモの編集**] を選択して編集を行ってから、[**保存して閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-178">To edit notes, select **Edit implementation notes**, make your edits, then select **Save and close**.</span></span>

<span data-ttu-id="afa28-179">メモフィールドに文字数の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="afa28-179">There is no character limit in the notes fields.</span></span> <span data-ttu-id="afa28-180">[改善アクションの詳細] ページで簡単に表示および編集できるように、ノートを短くすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="afa28-180">We recommend keeping notes brief so that you can easily view and edit them from the improvement actions details page.</span></span>

## <a name="change-improvement-action-status"></a><span data-ttu-id="afa28-181">改善アクションの状態の変更</span><span class="sxs-lookup"><span data-stu-id="afa28-181">Change improvement action status</span></span>

<span data-ttu-id="afa28-182">各改善アクションの実装の状態と日付、およびテストの状態と日付を記録することができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-182">You can record the implementation status and date, and the test status and date, for each improvement action.</span></span> <span data-ttu-id="afa28-183">利用可能なフィールドとステータスのオプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="afa28-183">Below are the available fields and status options:</span></span>

- <span data-ttu-id="afa28-184">[**実装の状態**]: 次の状態オプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-184">**Implementation status**: select from these status options:</span></span>
    - <span data-ttu-id="afa28-185">**実装されて**いません-アクションはまだ実装されていません</span><span class="sxs-lookup"><span data-stu-id="afa28-185">**Not implemented** - action not yet implemented</span></span>
    - <span data-ttu-id="afa28-186">**実装**済み-アクションの実装</span><span class="sxs-lookup"><span data-stu-id="afa28-186">**Implemented** - action implemented</span></span>
    - <span data-ttu-id="afa28-187">**代替実装**-他のサードパーティ製ツールを使用した場合や、Microsoft の推奨事項に含まれていないその他のアクションを実行した場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-187">**Alternative implementation** - select this option if you used other third-party tools or took other actions not included in Microsoft recommendations</span></span>
    - <span data-ttu-id="afa28-188">**計画**済み-実装に対して計画されたアクション</span><span class="sxs-lookup"><span data-stu-id="afa28-188">**Planned** - action is planned for implementation</span></span>
    - <span data-ttu-id="afa28-189">**範囲内にない**-組織に関連しないアクションのオプション。この状態を選択すると、得点からのアクションは除外されます。この操作を行うと、スコアの処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="afa28-189">**Not in scope** - an option for actions not relevant to your organization; selecting this status excludes the action from scoring; unselecting it will include the action in scoring</span></span>
- <span data-ttu-id="afa28-190">**実装日**: 実装の状態が "実装済み"**または**"**代替実装**" に設定されている場合は、利用可能なフィールド。予定表ポップアップを切り替えて日付を選択する</span><span class="sxs-lookup"><span data-stu-id="afa28-190">**Implementation date**: available field when implementation status is set to **Implemented** or **Alternative implementation**; toggle through the calendar pop-up to select the date</span></span>
- <span data-ttu-id="afa28-191">**テストの状態**: 次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-191">**Test status**: select from these options:</span></span>
    - <span data-ttu-id="afa28-192">**評価されて**いません-テストが開始されていません</span><span class="sxs-lookup"><span data-stu-id="afa28-192">**Not assessed** - testing has not started</span></span>
    - <span data-ttu-id="afa28-193">**成功した実装のテスト**が成功した</span><span class="sxs-lookup"><span data-stu-id="afa28-193">**Passed**- implementation successfully tested</span></span>
    - <span data-ttu-id="afa28-194">**失敗したリスクが低い**-テスト失敗、低リスク</span><span class="sxs-lookup"><span data-stu-id="afa28-194">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="afa28-195">**失敗中の危険度**-テスト失敗、中程度のリスク</span><span class="sxs-lookup"><span data-stu-id="afa28-195">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="afa28-196">**高リスクの失敗**-テスト失敗、高リスク</span><span class="sxs-lookup"><span data-stu-id="afa28-196">**Failed high risk** - testing failed, high risk</span></span>
- <span data-ttu-id="afa28-197">**テスト日**: 予定表ポップアップを切り替えて日付を選択する</span><span class="sxs-lookup"><span data-stu-id="afa28-197">**Test date**: toggle through the calendar pop-up to select the date</span></span>

> [!NOTE]
> <span data-ttu-id="afa28-198">実装およびテスト状態フィールドは、**割り当てられ**ているユーザーだけでなく、編集アクセス許可を持つすべてのユーザーが編集できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-198">Implementation and test status fields can be edited by any user with editing permissions, not just the **Assigned to** user.</span></span>

## <a name="assign-improvement-action-to-assessor-for-completion"></a><span data-ttu-id="afa28-199">完了の評価を査定活動に割り当てる</span><span class="sxs-lookup"><span data-stu-id="afa28-199">Assign improvement action to assessor for completion</span></span>

<span data-ttu-id="afa28-200">作業を完了し、証拠をアップロードしたら、次の手順として、実装の状態と日付を設定し、改善アクションを検証の評価に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afa28-200">After you complete the work and upload evidence, the next step is to set the implementation status and date, and assign the improvement action to an assessor for validation.</span></span>

<span data-ttu-id="afa28-201">一環の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="afa28-201">Types of assessors include:</span></span>

- <span data-ttu-id="afa28-202">組織内のコントロールの検証を実行する内部一環</span><span class="sxs-lookup"><span data-stu-id="afa28-202">Internal assessors who perform validation of controls within your organization</span></span>
- <span data-ttu-id="afa28-203">Microsoft cloud services を監査するサードパーティの独立した組織など、コンプライアンスを調査、検証、および認定する外部一環</span><span class="sxs-lookup"><span data-stu-id="afa28-203">External assessors who examine, verify, and certify compliance—such as third-party independent organizations that audit Microsoft cloud services</span></span>

<span data-ttu-id="afa28-204">査定官は、作業を検証し、ドキュメントを調べて、適切なテスト状態を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-204">The assessor validates the work and examines the documentation, and selects the appropriate test status.</span></span>

<span data-ttu-id="afa28-205">**テストの状態が "成功" になっている場合**は、処理が完了し、すべての使用可能なポイント**が表示され、** コンプライアンスの全体的なスコアに対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="afa28-205">**If the test status is "Passed"**: the action is complete, and the **points achieved** shows the full number of possible points achieved and counted toward your overall compliance score.</span></span>

<span data-ttu-id="afa28-206">**テストの状態が "Failed" のいずれかの程度の場合**は、アクションが要件を満たしていないので、その操作は追加の作業のために適切なユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-206">**If the test status is any degree of "Failed"**: the action does not meet the requirements, and the assessor can assign it back to the appropriate user for additional work.</span></span>

## <a name="solutions-page"></a><span data-ttu-id="afa28-207">ソリューションページ</span><span class="sxs-lookup"><span data-stu-id="afa28-207">Solutions page</span></span>

<span data-ttu-id="afa28-208">[**ソリューション] ページ**は、改善アクションを作業してスコアを拡大する開始点です。</span><span class="sxs-lookup"><span data-stu-id="afa28-208">The **Solutions page** is another starting point for working on improvement actions to increase your score.</span></span> 

<span data-ttu-id="afa28-209">ソリューションページに移動するには、ダッシュボードの [**ソリューション**] タブを選択するか、ダッシュボードの右上のセクションにある [**スコアに影響するソリューション**の下にある**すべてのソリューションを表示**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-209">To get to your solutions page, select the **Solutions** tab on your dashboard, or select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

<span data-ttu-id="afa28-210">[ソリューション] ページには、ソリューションごとに構成された、獲得されたポイントと潜在的なポイントの比率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-210">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="afa28-211">このビューで残っているポイントと改善アクションを表示することで、より迅速に対処する必要があるソリューションを理解できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-211">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="afa28-212">ソリューションビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="afa28-212">Filtering your solutions view</span></span>

<span data-ttu-id="afa28-213">ソリューションの表示をフィルター処理するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="afa28-213">To filter you view of solutions:</span></span> 

1. <span data-ttu-id="afa28-214">評価リストの左上隅にある [ **Filter** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-214">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="afa28-215">[フライアウト**フィルター** ] ウィンドウで、必要な条件 (標準と規制、ソリューション、アクションの種類、コンプライアンスマネージャーグループ、カテゴリ) の横にチェックマークを入れます。</span><span class="sxs-lookup"><span data-stu-id="afa28-215">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="afa28-216">[**適用**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-216">Select the **Apply** button.</span></span> <span data-ttu-id="afa28-217">フィルターウィンドウが閉じ、フィルター処理されたビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-217">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="afa28-218">また、評価リストの上にある [**グループ**] ドロップダウンメニューからグループ化の種類を選択することによって、グループ、製品、または規制によって評価を表示するようにビューを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="afa28-218">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solutions-page"></a><span data-ttu-id="afa28-219">[ソリューション] ページからアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="afa28-219">Taking actions from the solutions page</span></span>

<span data-ttu-id="afa28-220">[ソリューション] ページには、改善アクションに接続されている組織のソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-220">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="afa28-221">この表には、全体的なスコアに対する各ソリューションの貢献度、そのソリューション内で達成されているスコア向上ポイント、およびそのソリューションでグループ化された、スコアを増やすことができる改善アクションの残りの数が一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="afa28-221">The table lists each solution's contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span> 

<span data-ttu-id="afa28-222">この画面からアクションを実行するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="afa28-222">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="afa28-223">目的のソリューションの行の [**残りの操作**] 列で、ハイパーリンクされた番号をクリックまたはタップします。</span><span class="sxs-lookup"><span data-stu-id="afa28-223">On the row of your intended solution, under the **Remaining actions** column, click or tap on the hyperlinked number.</span></span> <span data-ttu-id="afa28-224">これにより、そのソリューションに対してテストされていない改善アクションが表示されている [機能向上のアクション] 画面のフィルタービューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-224">This takes you to a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="afa28-225">目的のソリューションの行の [**ソリューションを開く**] 列で、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-225">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="afa28-226">これにより、Microsoft 365 および Office 365 のセキュリティセンターとコンプライアンスセンターのソリューションまたは場所に対して、推奨されるアクションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="afa28-226">This takes you to the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="afa28-227">評価ページ</span><span class="sxs-lookup"><span data-stu-id="afa28-227">Assessments page</span></span>

<span data-ttu-id="afa28-228">[評価] ページには、組織で追跡するために選択した評価が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-228">The assessments page lists the assessments you select to track for your organization.</span></span> <span data-ttu-id="afa28-229">コンプライアンススコアの分母は、追跡対象の評価すべてによって決まります。</span><span class="sxs-lookup"><span data-stu-id="afa28-229">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="afa28-230">評価の数が多いほど、向上したアクションのページに表示される改善アクションが増え、スコアの分母が高くなります。</span><span class="sxs-lookup"><span data-stu-id="afa28-230">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="afa28-231">評価ページを表示するには、ダッシュボードの [**評価**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-231">To get to your assessments page, select the **Assessments** tab on your dashboard.</span></span>

<span data-ttu-id="afa28-232">このページでは、各評価に関する重要な情報をすばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="afa28-232">On this page you can quickly view important information about each assessment:</span></span>

- <span data-ttu-id="afa28-233">**状態**: 評価のすべての改善アクションの完了の状態は、次のいずれかとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-233">**Status**: the status toward completion of all the improvement actions in the assessment will be listed as either:</span></span>
    - <span data-ttu-id="afa28-234">**準拠**していません: 評価の改善アクションは実装されており、正常にテストされていません。作業はまだ開始していません</span><span class="sxs-lookup"><span data-stu-id="afa28-234">**Non-compliant**: the improvement actions in the assessment have not been implemented and successfully tested; work has not yet begun</span></span>
    - <span data-ttu-id="afa28-235">**進行**中: 改善アクションの実装またはテストで作業を進めています。これは、たとえば、評価の改善アクションが作業に割り当てられていること、つまり、実装とテストのプロセス中であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="afa28-235">**In progress**: work is underway in implementing or testing the improvement actions; this could mean, for example, that an improvement action in the assessment has been assigned for work, is in the process of being implemented and tested</span></span>
- <span data-ttu-id="afa28-236">**評価の進行状況**: 評価に成功したコントロールの数によって測定された、評価の最終完了までに行われた作業のパーセンテージ。</span><span class="sxs-lookup"><span data-stu-id="afa28-236">**Assessment progress**: the percentage of the work done towards final completion of the assessment, as measured by the number of controls successfully tested.</span></span>
- <span data-ttu-id="afa28-237">**顧客管理のアクション**: 顧客管理コントロールの実装に対応するために完了したアクションの数</span><span class="sxs-lookup"><span data-stu-id="afa28-237">**Customer-managed actions**: the number of completed actions to satisfy implementation of  your customer-managed controls</span></span>
- <span data-ttu-id="afa28-238">**Microsoft が管理するアクション**: microsoft 管理コントロールの実装を満たすために完了したアクションの数</span><span class="sxs-lookup"><span data-stu-id="afa28-238">**Microsoft-managed actions**: the number of completed actions to satisfy implementation of Microsoft-managed controls</span></span>
- <span data-ttu-id="afa28-239">**評価グループ**: 作成したグループの名前 (評価が存在するもの)</span><span class="sxs-lookup"><span data-stu-id="afa28-239">**Assessment group**: name of the group you created, in which the assessment resides</span></span>
- <span data-ttu-id="afa28-240">**関連サービス**: 関連付けられている Microsoft 365 サービス</span><span class="sxs-lookup"><span data-stu-id="afa28-240">**Related services**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="afa28-241">**関連する規制**: 評価で満たすべき規制基準、ポリシー、または法律</span><span class="sxs-lookup"><span data-stu-id="afa28-241">**Related regulations**: the regulatory standard, policy, or law which the assessment seeks to satisfy</span></span>

### <a name="default-assessments"></a><span data-ttu-id="afa28-242">既定の評価</span><span class="sxs-lookup"><span data-stu-id="afa28-242">Default assessments</span></span>

<span data-ttu-id="afa28-243">既定では、[評価] ページに Microsoft 365 データ保護のベースライン評価が表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-243">By default, you will see the Microsoft 365 data protection baseline assessment on the assessments page.</span></span> <span data-ttu-id="afa28-244">また、コンプライアンススコアには、いくつかの標準の評価が用意されています ([完全な一覧を表示](compliance-score.md#templates))。</span><span class="sxs-lookup"><span data-stu-id="afa28-244">Compliance Score also provides several out-of-box assessments ([view the full list](compliance-score.md#templates)).</span></span> <span data-ttu-id="afa28-245">他の規制や基準をカバーする評価を追加する場合は、コンプライアンスマネージャーでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-245">If you want to add more assessments to cover additional regulations and standards, you can do this in Compliance Manager.</span></span>

### <a name="managing-assessments"></a><span data-ttu-id="afa28-246">評価の管理</span><span class="sxs-lookup"><span data-stu-id="afa28-246">Managing assessments</span></span>

<span data-ttu-id="afa28-247">パブリックプレビューでは、評価の表示、作成、エクスポート、およびアーカイブの機能はコンプライアンスマネージャーツールに残ります。</span><span class="sxs-lookup"><span data-stu-id="afa28-247">During public preview, functionality for viewing, creating, exporting, and archiving assessments remains in the Compliance Manager tool.</span></span> 

<span data-ttu-id="afa28-248">評価を管理するには、[評価] の一覧の上部にある [**コンプライアンスマネージャーで評価を管理**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-248">To manage your assessments, select **Manage Assessments in Compliance Manager** at the top of the assessments list.</span></span>

<span data-ttu-id="afa28-249">[評価] の一覧の一番上にある [その他] のリンクは、コンプライアンス**マネージャーの microsoft のアクション**であり、コンプライアンスマネージャーのページに移動します。このページには、コンプライアンススコアに寄与する microsoft のコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-249">The other link at the top of the assessments list, **Microsoft actions in Compliance Manager**, takes you to the page in Compliance Manager showing Microsoft controls that contribute to your compliance score.</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="afa28-250">評価ビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="afa28-250">Filtering your assessments view</span></span>

<span data-ttu-id="afa28-251">評価の表示をフィルター処理するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="afa28-251">To filter you view of assessments:</span></span>

1. <span data-ttu-id="afa28-252">評価リストの左上隅にある [ **Filter** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-252">Select **Filter** at the top left corner of your assessments list.</span></span>
2. <span data-ttu-id="afa28-253">[フライアウト**フィルター** ] ウィンドウで、必要な条件 (標準および規制、コンプライアンスマネージャーグループ) の横にチェックマークを入れます。</span><span class="sxs-lookup"><span data-stu-id="afa28-253">On the flyout **Filters** pane, place a check next to the desired criteria (standards and regulations, Compliance Manager group).</span></span>
3. <span data-ttu-id="afa28-254">[**適用**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-254">Select the **Apply** button.</span></span> <span data-ttu-id="afa28-255">フィルターウィンドウが閉じ、フィルター処理されたビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-255">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="afa28-256">また、評価リストの上にある [**グループ**] ドロップダウンメニューからグループ化の種類を選択することによって、グループ、製品、または規制によって評価を表示するようにビューを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="afa28-256">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="managing-improvement-actions-within-an-assessment"></a><span data-ttu-id="afa28-257">評価内の改善アクションを管理する</span><span class="sxs-lookup"><span data-stu-id="afa28-257">Managing improvement actions within an assessment</span></span>

<span data-ttu-id="afa28-258">[評価] の一覧の [**お客様が管理するアクション**] 列で、リンクされたテキストを目的の評価の行に選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-258">From the assessment list, under the **Customer-managed actions** column, select the linked text on the row of the intended assessment.</span></span> <span data-ttu-id="afa28-259">これにより、[改善アクション] ページがフィルター処理され、その評価内のアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-259">This takes you a filtered view of the improvement actions page showing the actions within that assessment.</span></span>

## <a name="reporting"></a><span data-ttu-id="afa28-260">Reporting</span><span class="sxs-lookup"><span data-stu-id="afa28-260">Reporting</span></span>

<span data-ttu-id="afa28-261">コンプライアンススコアに含まれるすべての改善アクションのレポートをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-261">You can export a report of all your improvement actions in Compliance Score.</span></span> <span data-ttu-id="afa28-262">[向上した**アクション**] ページで、操作のリストの上にある画面の左上隅にある [**エクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-262">From the **Improvement actions** page, select **Export** in the upper-left corner of your screen, above your list of actions.</span></span> <span data-ttu-id="afa28-263">これにより、すべての改善アクションと、[**改善アクション**] ページに表示されるフィルターカテゴリを備えた Excel ワークシートが作成されます。このページでは、ローカルコンピューターを表示して保存することができます。</span><span class="sxs-lookup"><span data-stu-id="afa28-263">This will produce an Excel worksheet with all your improvement actions and the filter categories shown on the **Improvement actions** page, which you can view and save to your local machine.</span></span>

<span data-ttu-id="afa28-264">また、コンプライアンスマネージャーからレポートをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="afa28-264">You can also export a report from Compliance Manager.</span></span> <span data-ttu-id="afa28-265">[コンプライアンスマネージャー] で、[**コントロールの情報**] タブに移動し、画面の右上のセクションにある [**エクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="afa28-265">In Compliance Manager, go to the **Controls Info** tab and select **Export** in the upper-right section of the screen.</span></span> <span data-ttu-id="afa28-266">これにより、表示および保存できる Excel ワークシートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="afa28-266">This produces an Excel worksheet you can view and save.</span></span>
