---
title: ファイル計画マネージャーの概要
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: ファイル計画マネージャーは、保持ラベルおよび保持ラベル ポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。
ms.openlocfilehash: bad2e592359cb3e1f63e3fa020914ad49a65a471
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074215"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="cff57-103">ファイル計画マネージャーの概要</span><span class="sxs-lookup"><span data-stu-id="cff57-103">Overview of file plan manager</span></span>

<span data-ttu-id="cff57-104">ファイル計画マネージャーは、保持ラベルおよび保持ラベル ポリシーのための高度な管理機能を提供します。作成に始まり、コラボレーション、レコード宣言、保持、そして廃棄に至るまでのコンテンツのライフ サイクル全体におけるラベルとコンテンツのラベリングを網羅する統合的な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cff57-104">File plan manager provides advanced management capabilities for retention labels, retention label policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span> 

<span data-ttu-id="cff57-105">セキュリティおよびコンプライアンス センターのファイル計画マネージャーにアクセスするには、**[レコードの管理]** > **[ファイル計画]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="cff57-105">To access file plan manager in the security and compliance center, go to **Records management** > **File plan**.</span></span>

![[ファイル計画] ページ](../media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="cff57-107">ファイル計画マネージャーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="cff57-107">Accessing file plan manager</span></span>

<span data-ttu-id="cff57-108">ファイル計画マネージャーにアクセスするには次の 2 つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="cff57-108">There are two requirements to access file plan manager, they are:</span></span>

- <span data-ttu-id="cff57-109">Office 365 Enterprise E5 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="cff57-109">An Office 365 Enterprise E5 subscription.</span></span>

- <span data-ttu-id="cff57-110">次のいずれかのセキュリティおよびコンプライアンス センターの役割がユーザーに割り当てられている状態。</span><span class="sxs-lookup"><span data-stu-id="cff57-110">The user has been in assigned one of the following roles in the security and compliance center:</span></span>
    
    - <span data-ttu-id="cff57-111">保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="cff57-111">Retention Manager</span></span>
    
    - <span data-ttu-id="cff57-112">閲覧限定保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="cff57-112">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="cff57-113">デフォルトの保持ラベルとラベルポリシー</span><span class="sxs-lookup"><span data-stu-id="cff57-113">Default retention labels and label policy</span></span>

<span data-ttu-id="cff57-114">セキュリティ＆コンプライアンスセンターに保持ラベルがない場合、左ナビゲーションで**ファイルプラン**を最初に選択すると、**デフォルトデータガバナンス公開ポリシー**というラベルポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-114">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="cff57-115">このラベルポリシーには、3つの保持ラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cff57-115">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="cff57-116">**運用手順**</span><span class="sxs-lookup"><span data-stu-id="cff57-116">**Operational procedure**</span></span>
- <span data-ttu-id="cff57-117">**企業一般**</span><span class="sxs-lookup"><span data-stu-id="cff57-117">**Business general**</span></span>
- <span data-ttu-id="cff57-118">**契約規定**</span><span class="sxs-lookup"><span data-stu-id="cff57-118">**Contract agreement**</span></span>

<span data-ttu-id="cff57-119">これらの保持ラベルは、コンテンツを保持するためだけに構成され、コンテンツを削除するためには構成されていません。</span><span class="sxs-lookup"><span data-stu-id="cff57-119">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="cff57-120">このラベルポリシーは組織全体に公開され、無効にすることも削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="cff57-120">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="cff57-121">アクティビティ**作成済み保持ポリシー**および**作成済み保持ポリシーの保持設定**の監査ログを確認することで、ファイルプランマネージャを開いて初めて実行環境を構築したユーザを特定できます。</span><span class="sxs-lookup"><span data-stu-id="cff57-121">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="cff57-122">お客様からのフィードバックにより、デフォルトの保持ラベルと保持ラベル ラベルポリシーを作成する上記のこの機能は削除されました。</span><span class="sxs-lookup"><span data-stu-id="cff57-122">Due to customer feedback, we have removed this feature that creates the default retention labels and retention label policy mentioned above.</span></span> <span data-ttu-id="cff57-123">これらの保持ラベルと保持ラベル ラベルポリシーは、ファイル計画マネージャーを 2019 年 4 月 11 日より前に開いたことがある場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-123">You will only see these retention labels and retention label policy if you opened file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="cff57-124">ファイル計画の中の移動</span><span class="sxs-lookup"><span data-stu-id="cff57-124">Navigating your file plan</span></span>

<span data-ttu-id="cff57-125">ファイル計画マネージャーでは、すべての保持ラベルとポリシーの設定を 1 つのビューから簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="cff57-125">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="cff57-126">ファイル計画の外で作成された保持ラベルはファイル計画上で利用可能で、また、その逆も同様であることに注意します。</span><span class="sxs-lookup"><span data-stu-id="cff57-126">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="cff57-127">ファイル計画 [**ラベル**] タブで、次の追加の情報と機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-127">On the file plan **Labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="cff57-128">ラベル設定列</span><span class="sxs-lookup"><span data-stu-id="cff57-128">Label settings columns</span></span>

- <span data-ttu-id="cff57-p103">[**分類方法**] は保持期間を起動するトリガーの種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="cff57-131">イベント</span><span class="sxs-lookup"><span data-stu-id="cff57-131">Event</span></span>
    - <span data-ttu-id="cff57-132">作成日時</span><span class="sxs-lookup"><span data-stu-id="cff57-132">When created</span></span>
    - <span data-ttu-id="cff57-133">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="cff57-133">When last modified</span></span>
    - <span data-ttu-id="cff57-134">ラベルが付けられた日時</span><span class="sxs-lookup"><span data-stu-id="cff57-134">When labeled</span></span>
- <span data-ttu-id="cff57-p104">[**レコード**] は、ラベルが適用されときにアイテムが宣言されたレコードが宣言されたレコードになるかどうかを識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="cff57-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="cff57-137">No</span></span>
    - <span data-ttu-id="cff57-138">はい</span><span class="sxs-lookup"><span data-stu-id="cff57-138">Yes</span></span>
    - <span data-ttu-id="cff57-139">はい (法的)</span><span class="sxs-lookup"><span data-stu-id="cff57-139">Yes(Regulatory)</span></span>
- <span data-ttu-id="cff57-p105">[**保持**] は保持の種類を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="cff57-142">保持</span><span class="sxs-lookup"><span data-stu-id="cff57-142">Keep</span></span>
    - <span data-ttu-id="cff57-143">保持および削除</span><span class="sxs-lookup"><span data-stu-id="cff57-143">Keep and delete</span></span>
    - <span data-ttu-id="cff57-144">削除</span><span class="sxs-lookup"><span data-stu-id="cff57-144">Delete</span></span>
- <span data-ttu-id="cff57-p106">[**廃棄**] は保持期間終了時のコンテンツの取り扱い方法を識別します。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="cff57-147">null</span><span class="sxs-lookup"><span data-stu-id="cff57-147">null</span></span>
    - <span data-ttu-id="cff57-148">アクションなし</span><span class="sxs-lookup"><span data-stu-id="cff57-148">No action</span></span>
    - <span data-ttu-id="cff57-149">自動削除</span><span class="sxs-lookup"><span data-stu-id="cff57-149">Auto-delete</span></span>
    - <span data-ttu-id="cff57-150">要確認 (廃棄レビューとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="cff57-150">Review required (aka Disposition review)</span></span>

![ファイル計画でのラベル設定](../media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="cff57-152">保持ラベル ファイル計画記述子列</span><span class="sxs-lookup"><span data-stu-id="cff57-152">Retention label file plan descriptors columns</span></span>

<span data-ttu-id="cff57-153">保持ラベルの構成により多くの情報を含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cff57-153">You can now include more information in the configuration of your retention labels.</span></span> <span data-ttu-id="cff57-154">ファイル計画記述子を保持ラベルに挿入すると、ファイル計画の管理性と編成が向上します。</span><span class="sxs-lookup"><span data-stu-id="cff57-154">Inserting file plan descriptors into retention  labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="cff57-155">すぐに利用開始できるように、ファイル計画マネージャーでは次の既定値が提供されています: 役割/部門、カテゴリ、権限の種類、規定/引用。</span><span class="sxs-lookup"><span data-stu-id="cff57-155">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation.</span></span> <span data-ttu-id="cff57-156">保持ラベルを作成または編集するときに、ファイル計画記述子の値を新たに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cff57-156">You can add new file plan descriptor values when creating or editing a retention label.</span></span> <span data-ttu-id="cff57-157">保持ラベルをファイル計画にインポートするときに、ファイル計画記述子を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cff57-157">You can also specify file plan descriptors when importing retention labels into your file plan.</span></span> 

<span data-ttu-id="cff57-158">保持ラベルを作成または編集時のファイル計画記述子に関する手順の画面です。</span><span class="sxs-lookup"><span data-stu-id="cff57-158">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![ファイル計画記述子](../media/file-plan-descriptors.png)

<span data-ttu-id="cff57-160">ファイル計画マネージャーの [**ラベル**] タブのファイル計画記述子列の画面です。</span><span class="sxs-lookup"><span data-stu-id="cff57-160">Here's a view of the file plan descriptors columns on the **Labels** tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="cff57-162">分析したりオフライン レビューを実行したりするために、すべての既存の保持ラベルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="cff57-162">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="cff57-163">組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューが円滑に行えるように、ファイル計画マネージャーではすべての保持ラベルの詳細を .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="cff57-163">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="cff57-164">すべての保持ラベルをエクスポートするには: [**ファイル計画**] ページで [**ファイル計画の操作**] \> [**ラベルをエクスポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cff57-164">To export all retention labels: On the **File plan** page, **File plan actions** \> **Export labels**.</span></span>

![ファイル計画をエクスポートするオプション](../media/file-plan-export-labels-option.png)

<span data-ttu-id="cff57-166">既存のすべての保持ラベルを含む \*.csv ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="cff57-166">A \*.csv file containing all existing retention labels will open.</span></span>

![すべての保持ラベルが表示された CSV ファイル](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="cff57-168">ファイル計画に保持ラベルをインポートする</span><span class="sxs-lookup"><span data-stu-id="cff57-168">Import retention labels into your file plan</span></span>

<span data-ttu-id="cff57-169">ファイル計画マネージャーでは新しい保持ラベルの一括インポートおよび既存の保持ラベルの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cff57-169">In the File plan manager, you can bulk import new retention labels and modify existing retention labels.</span></span>

<span data-ttu-id="cff57-170">新しい保持ラベルのインポートおよび既存の保持ラベルの変更を行うには:</span><span class="sxs-lookup"><span data-stu-id="cff57-170">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="cff57-171">[**ファイル計画**] ページで [**ファイル計画の操作**]  >  [**ラベルをインポート**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cff57-171">On the **File plan** page, go to **File plan actions** > **Import labels**.</span></span>

   ![ファイル計画のインポートのオプション](../media/file-plan-import-labels-option.png)

   ![空白のファイル計画テンプレートをダウンロードするオプション](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="cff57-174">空白のテンプレートをダウンロードして、新しい保持ラベルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cff57-174">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="cff57-175">または、組織の既存の保持ラベルをエクスポートするときにエクスポートされる .csv ファイルから開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="cff57-175">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![Excel で開かれた空白のファイル計画テンプレート](../media/file-plan-blank-template.png)

3. <span data-ttu-id="cff57-177">テンプレートに入力します。</span><span class="sxs-lookup"><span data-stu-id="cff57-177">Fill-out the template.</span></span> <span data-ttu-id="cff57-178">次に、ファイル計画テンプレートのプロパティと各プロパティの有効な値について説明します。</span><span class="sxs-lookup"><span data-stu-id="cff57-178">The following describes the properties and valid values for each property in the file plan template.</span></span><br/>

   |<span data-ttu-id="cff57-179">**Property**</span><span class="sxs-lookup"><span data-stu-id="cff57-179">**Property**</span></span>|<span data-ttu-id="cff57-180">**種類**</span><span class="sxs-lookup"><span data-stu-id="cff57-180">**Type**</span></span>|<span data-ttu-id="cff57-181">**有効な値**</span><span class="sxs-lookup"><span data-stu-id="cff57-181">**Valid values**</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="cff57-182">LabelName</span><span class="sxs-lookup"><span data-stu-id="cff57-182">LabelName</span></span>|<span data-ttu-id="cff57-183">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-183">String</span></span>|<span data-ttu-id="cff57-184">このプロパティは、保持ラベルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-184">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="cff57-185">コメント</span><span class="sxs-lookup"><span data-stu-id="cff57-185">Comment</span></span>|<span data-ttu-id="cff57-186">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-186">String</span></span>|<span data-ttu-id="cff57-187">このプロパティを使用して、管理者の保持ラベルに関する説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="cff57-187">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="cff57-188">この説明は、セキュリティおよびコンプライアンス センターでラベルを管理する管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-188">This description appears only to admins who manage the label in the security and compliance center.</span></span>|
   |<span data-ttu-id="cff57-189">メモ</span><span class="sxs-lookup"><span data-stu-id="cff57-189">Notes</span></span>|<span data-ttu-id="cff57-190">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-190">String</span></span>|<span data-ttu-id="cff57-191">このプロパティを使用して、ユーザーの保持ラベルに関する説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="cff57-191">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="cff57-192">この説明は、ユーザーが Outlook、SharePoint、OneDrive などのアプリでラベルにカーソルを置いたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-192">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="cff57-193">このプロパティを空白のままにすると、ラベルの保持設定を説明する既定の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-193">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="cff57-194">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="cff57-194">IsRecordLabel</span></span>|<span data-ttu-id="cff57-195">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-195">String</span></span>|<span data-ttu-id="cff57-196">このプロパティは、ラベルがレコード ラベルであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-196">This property specifies whether the label is a record label.</span></span> <span data-ttu-id="cff57-197">レコード ラベルでタグ付けされたアイテムは、レコードとして宣言されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-197">Items tagged with a record label are declared as records.</span></span> <span data-ttu-id="cff57-198">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-198">Valid values are:</span></span></br><span data-ttu-id="cff57-199">**TRUE**: ラベルはレコード ラベルです。</span><span class="sxs-lookup"><span data-stu-id="cff57-199">**TRUE**: The label is a record label.</span></span> <span data-ttu-id="cff57-200">レコードとして宣言されているアイテムは削除できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cff57-200">Note that items that are declared as a record can't be deleted.</span></span> </br><span data-ttu-id="cff57-201">**FALSE**: ラベルはレコード ラベルではありません。</span><span class="sxs-lookup"><span data-stu-id="cff57-201">**FALSE**: The label isn't a record label.</span></span> <span data-ttu-id="cff57-202">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="cff57-202">This is the default value.</span></span>|
   |<span data-ttu-id="cff57-203">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="cff57-203">RetentionAction</span></span>|<span data-ttu-id="cff57-204">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-204">String</span></span>|<span data-ttu-id="cff57-205">このプロパティは、RetentionDuration プロパティで指定された値の有効期限が切れた後に実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-205">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="cff57-206">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-206">Valid values are:</span></span></br><span data-ttu-id="cff57-207">**Delete**: RetentionDuration プロパティで指定された値よりも古いアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-207">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="cff57-208">**Keep**: RetentionDuration プロパティで指定された期間のアイテムを保持し、期間が終了しても何もしません。</span><span class="sxs-lookup"><span data-stu-id="cff57-208">**Keep**: Retain items for the duration specified by the RetentionDuration property and then doing nothing when the duration period expires.</span></span> </br><span data-ttu-id="cff57-209">**KeepAndDelete**: RetentionDuration プロパティで指定された期間のアイテムを保持し、期間が終了したらそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="cff57-209">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="cff57-210">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="cff57-210">RetentionDuration</span></span>|<span data-ttu-id="cff57-211">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-211">String</span></span>|<span data-ttu-id="cff57-212">プロパティは、コンテンツを保持する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-212">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="cff57-213">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-213">Valid values are:</span></span></br><span data-ttu-id="cff57-214">**Unlimited**: アイテムは無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-214">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="cff57-215">***n***: 正の整数です。(例: **365**)</span><span class="sxs-lookup"><span data-stu-id="cff57-215">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="cff57-216">RetentionType</span><span class="sxs-lookup"><span data-stu-id="cff57-216">RetentionType</span></span>|<span data-ttu-id="cff57-217">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-217">String</span></span>|<span data-ttu-id="cff57-218">プロパティは、コンテンツ作成日、イベント日、ラベルが付けられた (タグが付けされた) 日、または最終変更日のいずれから保持期間を計算するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-218">This property specifies whether the retention duration is calculated from the content creation date, event date, labeled (tagged) date, or last modified date.</span></span> <span data-ttu-id="cff57-219">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cff57-219">Valid values are:</span></span></br><span data-ttu-id="cff57-220">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="cff57-220">**CreationAgeInDays**</span></span></br><span data-ttu-id="cff57-221">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="cff57-221">**EventAgeInDays**</span></span></br><span data-ttu-id="cff57-222">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="cff57-222">**TaggedAgeInDays**</span></span></br><span data-ttu-id="cff57-223">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="cff57-223">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="cff57-224">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="cff57-224">ReviewerEmail</span></span>|<span data-ttu-id="cff57-225">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="cff57-225">SmtpAddress</span></span>|<span data-ttu-id="cff57-226">このプロパティが入力されている場合、保持期間が終了すると、廃棄のレビューがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="cff57-226">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="cff57-227">プロパティは、**Delete** および **KeepAndDelete** の保持期間用アクションのレビュー担当者の電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-227">This property specifies the email address of a reviewer for **Delete** and **KeepAndDelete** retention actions.</span></span> <span data-ttu-id="cff57-228">個々のユーザー、配布グループまたはセキュリティ グループ、または Office 365 グループの電子メール アドレスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cff57-228">You can include the email address of individual users, distribution or security groups, or Office 365 groups.</span></span> <span data-ttu-id="cff57-229">複数のメール アドレスをコンマで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="cff57-229">You can specify multiple email addresses separated by commas.</span></span>|
   |<span data-ttu-id="cff57-230">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="cff57-230">ReferenceId</span></span>|<span data-ttu-id="cff57-231">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-231">String</span></span>|<span data-ttu-id="cff57-232">このプロパティは、**参照 ID** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-232">This property specifies the value that's displayed in the **Reference Id** file plan descriptor.</span></span>| 
   |<span data-ttu-id="cff57-233">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="cff57-233">DepartmentName</span></span>|<span data-ttu-id="cff57-234">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-234">String</span></span>|<span data-ttu-id="cff57-235">このプロパティは、**業務/部署**ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-235">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="cff57-236">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cff57-236">Category</span></span>|<span data-ttu-id="cff57-237">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-237">String</span></span>|<span data-ttu-id="cff57-238">このプロパティは、**カテゴリ** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-238">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="cff57-239">下位カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cff57-239">SubCategory</span></span>|<span data-ttu-id="cff57-240">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-240">String</span></span>|<span data-ttu-id="cff57-241">このプロパティは、**サブカテゴリ** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-241">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="cff57-242">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="cff57-242">AuthorityType</span></span>|<span data-ttu-id="cff57-243">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-243">String</span></span>|<span data-ttu-id="cff57-244">このプロパティは、**管理組織の種類** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-244">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="cff57-245">CitationName</span><span class="sxs-lookup"><span data-stu-id="cff57-245">CitationName</span></span>|<span data-ttu-id="cff57-246">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-246">String</span></span>|<span data-ttu-id="cff57-247">このプロパティは、**規定/引用**ファイル計画記述子に表示される引用の名前を指定します。(例: 「Sarbanes-Oxley Act or 2002」)</span><span class="sxs-lookup"><span data-stu-id="cff57-247">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor; for example "Sarbanes-Oxley Act or 2002".</span></span> |
   |<span data-ttu-id="cff57-248">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="cff57-248">CitationUrl</span></span>|<span data-ttu-id="cff57-249">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-249">String</span></span>|<span data-ttu-id="cff57-250">このプロパティは、**規定/引用** ファイル計画記述子に表示される URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-250">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="cff57-251">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="cff57-251">CitationJurisdiction</span></span>|<span data-ttu-id="cff57-252">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-252">String</span></span>|<span data-ttu-id="cff57-253">このプロパティは、**規定/引用**ファイル計画記述子に表示される管理規則または機関を指定します。(例: 「米国証券取引委員会 (SEC)」)</span><span class="sxs-lookup"><span data-stu-id="cff57-253">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor; for example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="cff57-254">Regulatory</span><span class="sxs-lookup"><span data-stu-id="cff57-254">Regulatory</span></span>|<span data-ttu-id="cff57-255">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-255">String</span></span>|<span data-ttu-id="cff57-256">空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="cff57-256">Leave blank.</span></span> <span data-ttu-id="cff57-257">現時点では、このプロパティは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="cff57-257">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="cff57-258">EventType</span><span class="sxs-lookup"><span data-stu-id="cff57-258">EventType</span></span>|<span data-ttu-id="cff57-259">文字列</span><span class="sxs-lookup"><span data-stu-id="cff57-259">String</span></span>|<span data-ttu-id="cff57-260">このプロパティは、ラベルに関連付けられている保持規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="cff57-260">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="cff57-261">ルールを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cff57-261">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="cff57-262">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cff57-262">For example:</span></span></br><span data-ttu-id="cff57-263">**名前**</span><span class="sxs-lookup"><span data-stu-id="cff57-263">**Name**</span></span></br><span data-ttu-id="cff57-264">**識別名 (DN)**</span><span class="sxs-lookup"><span data-stu-id="cff57-264">**Distinguished name (DN)**</span></span></br><span data-ttu-id="cff57-265">**GUID**</span><span class="sxs-lookup"><span data-stu-id="cff57-265">**GUID**</span></span> </br><span data-ttu-id="cff57-266">使用可能な保持規則を確認するには、[Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cff57-266">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="cff57-267">1 つの Office 365 組織からラベルをエクスポートする場合、別の Office 365 組織にラベルをインポートするときに、その組織の EventType プロパティの値を使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cff57-267">Note that if you export labels from one Office 365 organization, you can't use the values for the EventType  property from that organization when importing labels to a different Office 365 organization.</span></span> <span data-ttu-id="cff57-268">これは、EventType 値が組織に固有であるためです。</span><span class="sxs-lookup"><span data-stu-id="cff57-268">That because the EventType values are unique to an organization.</span></span> |
   |||

   <span data-ttu-id="cff57-269">保持ラベルに関する情報を含むテンプレートの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cff57-269">Here's an example the template containing the information about retention labels.</span></span>

   ![情報が入力されたファイル計画テンプレート](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="cff57-271">ファイル計画のインポート ウィザード ページの手順 3 で、[**ファイルの参照**] をクリックして、入力済みのテンプレートをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="cff57-271">Under step 3 on the import file plan wizard page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="cff57-272">ファイル計画マネージャーでエントリが検証され、インポートの統計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cff57-272">File plan manager will validate the entries and display the import statistics.</span></span>

   ![ファイル計画のインポートの統計情報](../media/file-plan-import-statistics.png)

   <span data-ttu-id="cff57-274">検証エラーが発生した場合、ファイル計画のインポートはインポート ファイル内のすべてのエントリを引き続き検証し、インポート ファイル内でエラーを参照するラインまたは行の番号を表示し、表示されたエラー結果をコピーます。これにより、簡単にインポート ファイルに戻り、エラーを修正することができます。</span><span class="sxs-lookup"><span data-stu-id="cff57-274">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easily return to the import file and correct the errors.</span></span>

5. <span data-ttu-id="cff57-275">インポートが完了したらファイル計画マネージャーに戻り、新しい保持ラベルを新規または既存の保持ポリシーと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="cff57-275">When the import is complete, return to file plan manager to associate the new retention labels to new or existing retention label policies.</span></span>

   ![ラベルを公開するオプション](../media/file-plan-publish-labels-option.png)
