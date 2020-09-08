---
title: ファイルプランを使用してコンテンツのライフサイクル全体の保持ラベルを管理する
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
description: ファイルプランでは、アイテム保持ラベルに高度な管理機能が提供されます。
ms.custom: seo-marvel-may2020
ms.openlocfilehash: eb35915861c08588fab309210a49585a49d1b9da
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399214"
---
# <a name="use-file-plan-to-manage-retention-labels"></a><span data-ttu-id="9b1b6-103">ファイルプランを使用して保持ラベルを管理する</span><span class="sxs-lookup"><span data-stu-id="9b1b6-103">Use file plan to manage retention labels</span></span>

><span data-ttu-id="9b1b6-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="9b1b6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9b1b6-105">Microsoft 365 コンプライアンスセンターで、保持ラベルの作成と管理は**情報ガバナンス** から出来ますが、**レコード管理** からのファイルプランには追加の管理機能があります。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-105">Although you can create and manage retention labels from **Information governance** in the Microsoft 365 compliance center, file plan from **Records management** has additional management capabilities:</span></span>

- <span data-ttu-id="9b1b6-106">スプレッドシートから関連情報をインポートして、保持ラベルを一括作成できます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-106">You can bulk-create retention labels by importing the relevant information from a spreadsheet.</span></span>

- <span data-ttu-id="9b1b6-107">分析およびオフラインでの共同作業、あるいは一括編集には、既存の保持ラベルから情報をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-107">You can export the information from existing retention labels for analysis and offline collaboration, or for bulk-editing.</span></span>

- <span data-ttu-id="9b1b6-108">保持ラベルの詳細については、情報を見やすいように１つのビューから全ての保持ラベルの設定全体を表示しています。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-108">More information about the retention labels is displayed to make it easier to see into and across the settings of all your retention labels from one view.</span></span>

- <span data-ttu-id="9b1b6-109">ファイルプラン記述子は、各ラベルの追加およびオプションの情報をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-109">File plan descriptors support additional and optional information for each label.</span></span>

<span data-ttu-id="9b1b6-110">ファイルプランは、コンテンツをレコードとしてマークしない場合でも、すべての保持ラベルに使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-110">File plan can be used for all retention labels, even if they don't mark content as a record.</span></span>

![[ファイル計画] ページ](../media/compliance-file-plan.png)

<span data-ttu-id="9b1b6-112">保持ラベルについて、そして使用方法の情報については、[保持ポリシーおよび保持ラベルについて詳しく見る](retention.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-112">For information about what retention labels are and how to use them, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="accessing-file-plan"></a><span data-ttu-id="9b1b6-113">ファイル計画にアクセスしています</span><span class="sxs-lookup"><span data-stu-id="9b1b6-113">Accessing file plan</span></span>

<span data-ttu-id="9b1b6-114">ファイル計画にアクセスするには、次のいずれかの管理者役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-114">To access file plan, you must have one of the following admin roles:</span></span>
    
- <span data-ttu-id="9b1b6-115">保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="9b1b6-115">Retention Manager</span></span>

- <span data-ttu-id="9b1b6-116">閲覧限定保持マネージャー</span><span class="sxs-lookup"><span data-stu-id="9b1b6-116">View-only Retention Manager</span></span>

<span data-ttu-id="9b1b6-117">Microsoft 365 コンプライアンスセンターで、**ソリューション** > **レコード管理** > **ファイル計画**の順で移動します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-117">In the Microsoft 365 compliance center, go to **Solutions** > **Records management** > **File plan**.</span></span> 

<span data-ttu-id="9b1b6-118">**[レコード管理]** がナビゲーション ウィンドウに表示されない場合は、下にスクロールして **[すべて表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-118">If **Records management** doesn't display in the navigation pane, first scroll down, and select **Show all**.</span></span>

![[ファイル計画] ページ](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a><span data-ttu-id="9b1b6-120">ファイル計画を移動中</span><span class="sxs-lookup"><span data-stu-id="9b1b6-120">Navigating your file plan</span></span>

<span data-ttu-id="9b1b6-121">Microsoft 365 コンプライアンスセンターで、もしも既に**情報ガバナンス**から保持ラベルを作成済みの場合は、これらのラベルは自動的にファイル計画に表示されます。 </span><span class="sxs-lookup"><span data-stu-id="9b1b6-121">If you've already created retention labels from **Information governance** in the Microsoft 365 compliance center, these labels automatically display in your file plan.</span></span> 

<span data-ttu-id="9b1b6-122">同様に、ファイル計画に保持ラベルを作成した場合、コンテンツをレコードとしてマークするようにラベルが構成されていない場合は、**情報ガバナンス**からも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-122">Similarly, if you now create retention labels in file plan, they are also available from **Information governance** if the labels aren't configured to mark content as a record.</span></span>

<span data-ttu-id="9b1b6-123">**ファイル計画** ページには、すべてのラベルの中に、状態や設定、オプションのファイル計画記述子、およびラベルのオフラインレビューを分析または有効にするエクスポートオプション、および保持ラベルを作成するインポートオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-123">On the **File plan** page, you see all your labels with their status and settings, optional file plan descriptors, an export option to analyze or enable offline reviews of your labels, and an import option to create retention labels.</span></span> 

### <a name="label-settings-columns"></a><span data-ttu-id="9b1b6-124">ラベル設定列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-124">Label settings columns</span></span>

<span data-ttu-id="9b1b6-125">**名前**ラベルを除くすべての列を表示、または非表示にするには、 **列のカスタマイズ** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-125">All columns except the label **Name** can be displayed or hidden by selecting the **Customize columns** option.</span></span> <span data-ttu-id="9b1b6-126">既定では、最初の幾つかの列にはラベルの状態とその設定に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-126">But by default, the first few columns display information about the label status and its settings:</span></span> 

- <span data-ttu-id="9b1b6-127">**状態** は、ラベルポリシーにラベルが含まれているかどうか、或いは自動適用ポリシー (**アクティブ**) もしくはそうではない(**非アクティブ**).かを識別します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-127">**Status** identifies whether the label is included in a label policy or auto-apply policy (**Active**) or not (**Inactive**).</span></span>

- <span data-ttu-id="9b1b6-128">**基づき**どのように、もしくはいつ保持期間が開始するのかを識別します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-128">**Based on** identifies how or when the retention period begins.</span></span> <span data-ttu-id="9b1b6-129">有効な値:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-129">Valid values:</span></span>
    - <span data-ttu-id="9b1b6-130">イベント</span><span class="sxs-lookup"><span data-stu-id="9b1b6-130">Event</span></span>
    - <span data-ttu-id="9b1b6-131">作成日時</span><span class="sxs-lookup"><span data-stu-id="9b1b6-131">When created</span></span>
    - <span data-ttu-id="9b1b6-132">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="9b1b6-132">Last modified</span></span>
    - <span data-ttu-id="9b1b6-133">ラベルが付けられた日時</span><span class="sxs-lookup"><span data-stu-id="9b1b6-133">When labeled</span></span>

- <span data-ttu-id="9b1b6-134">**レコード**は、ラベルが適用されたときに、アイテムがレコードとしてマークされているかどうかを識別します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-134">**Is record** identifies if the item is marked as a record when the label is applied.</span></span> <span data-ttu-id="9b1b6-135">有効な値:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-135">Valid values:</span></span>
    - <span data-ttu-id="9b1b6-136">不要</span><span class="sxs-lookup"><span data-stu-id="9b1b6-136">No</span></span>
    - <span data-ttu-id="9b1b6-137">はい</span><span class="sxs-lookup"><span data-stu-id="9b1b6-137">Yes</span></span>

- <span data-ttu-id="9b1b6-138">**保持期間** は、保持期間を識別します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-138">**Retention duration** identifies the retention period.</span></span> <span data-ttu-id="9b1b6-139">有効な値:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-139">Valid values:</span></span>
    - <span data-ttu-id="9b1b6-140">日数</span><span class="sxs-lookup"><span data-stu-id="9b1b6-140">Days</span></span>
    - <span data-ttu-id="9b1b6-141">月</span><span class="sxs-lookup"><span data-stu-id="9b1b6-141">Months</span></span>
    - <span data-ttu-id="9b1b6-142">年数</span><span class="sxs-lookup"><span data-stu-id="9b1b6-142">Years</span></span>
    - <span data-ttu-id="9b1b6-143">無期限</span><span class="sxs-lookup"><span data-stu-id="9b1b6-143">Forever</span></span>
    - <span data-ttu-id="9b1b6-144">なし</span><span class="sxs-lookup"><span data-stu-id="9b1b6-144">None</span></span>

- <span data-ttu-id="9b1b6-145">[**廃棄の種類**] は、保持期間終了時に何が起こるのかを識別します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-145">**Disposition type** identifies what happens to the content at the end of the retention period.</span></span> <span data-ttu-id="9b1b6-146">有効な値:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-146">Valid values:</span></span>
    - <span data-ttu-id="9b1b6-147">アクションなし</span><span class="sxs-lookup"><span data-stu-id="9b1b6-147">No action</span></span>
    - <span data-ttu-id="9b1b6-148">自動削除</span><span class="sxs-lookup"><span data-stu-id="9b1b6-148">Auto-delete</span></span>
    - <span data-ttu-id="9b1b6-149">確認が必要</span><span class="sxs-lookup"><span data-stu-id="9b1b6-149">Review required</span></span>

### <a name="file-plan-descriptors-columns"></a><span data-ttu-id="9b1b6-150">ファイル計画記述子列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-150">File plan descriptors columns</span></span>

<span data-ttu-id="9b1b6-151">ファイルプランでは、保持ラベルの一部として、より多くの情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-151">File plan lets you include more information as part of your retention labels.</span></span> <span data-ttu-id="9b1b6-152">これらのファイルプラン記述子には、ラベルを作成するのに必要なコンテンツの管理性と構成を改善するためのより多くのオプションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-152">These file plan descriptors provide more options to improve the manageability and organization of the content you need to label.</span></span>

<span data-ttu-id="9b1b6-153">既定では、 **参照 ID**から始めると、次のいくつかの列には、保持ラベルを作成するとき、または既存のラベルを編集するときに指定できるファイルプラン記述子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-153">By default, starting with **Reference ID**, the next few columns display these file plan descriptors that you can specify when you create a retention label, or edit an existing label.</span></span> 

<span data-ttu-id="9b1b6-154">この作業を開始するには、幾つかの既定値が次のファイルプラン記述子にあります。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-154">To get you started, there are some out-of-box values for the following file plan descriptors:</span></span> 
- <span data-ttu-id="9b1b6-155">ビジネス機能/部署</span><span class="sxs-lookup"><span data-stu-id="9b1b6-155">Business function/department</span></span>
- <span data-ttu-id="9b1b6-156">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9b1b6-156">Category</span></span>
- <span data-ttu-id="9b1b6-157">権限の種類</span><span class="sxs-lookup"><span data-stu-id="9b1b6-157">Authority type</span></span>
- <span data-ttu-id="9b1b6-158">プロビジョニング/引用</span><span class="sxs-lookup"><span data-stu-id="9b1b6-158">Provision/citation</span></span> 

<span data-ttu-id="9b1b6-159">保持ラベルを作成または編集する場合のファイルプラン記述子の例:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-159">Example of file plan descriptors when you create or edit a retention label:</span></span>

![保持ラベルを作成または編集する場合のファイル計画記述子](../media/file-plan-descriptors.png)

<span data-ttu-id="9b1b6-161">ファイル計画記述子列の例の表示</span><span class="sxs-lookup"><span data-stu-id="9b1b6-161">Example view of the file plan descriptors columns:</span></span>

![ファイル計画記述子列](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a><span data-ttu-id="9b1b6-163">すべての保持ラベルをエクスポートして、オフラインレビューを分析または有効にする</span><span class="sxs-lookup"><span data-stu-id="9b1b6-163">Export all retention labels to analyze or enable offline reviews</span></span>

<span data-ttu-id="9b1b6-164">組織内のデータ ガバナンス関係者との定期的なコンプライアンス レビューを促進するように、ファイル計画マネージャーではすべての保持ラベルの詳細を .csv ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-164">From your file plan, you can export the details of all retention labels into a .csv file to help you facilitate periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="9b1b6-165">すべての保持ラベルをエクスポートするには: [**ファイル計画**] ページで [**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-165">To export all retention labels: On the **File plan** page, click **Export**:</span></span>

![ファイル計画をエクスポートするオプション](../media/compliance-file-plan-export-labels.png)

<span data-ttu-id="9b1b6-167">A \*.csv ファイルは既存の全ての保持ラベルを開く、を含みます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-167">A \*.csv file that contains all existing retention labels opens.</span></span> <span data-ttu-id="9b1b6-168">例:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-168">For example:</span></span>

![すべての保持ラベルが表示された CSV ファイル](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="9b1b6-170">ファイル計画に保持ラベルをインポートする</span><span class="sxs-lookup"><span data-stu-id="9b1b6-170">Import retention labels into your file plan</span></span>

<span data-ttu-id="9b1b6-171">ファイル計画では新しい保持ラベルの一括インポート、そして同じ方法を使い既存の保持ラベルの一括変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-171">In file plan, you can bulk-import new retention labels, and use the same method to bulk-modify existing retention labels.</span></span>

<span data-ttu-id="9b1b6-172">新しい保持ラベルのインポートおよび既存の保持ラベルの変更を行うには:</span><span class="sxs-lookup"><span data-stu-id="9b1b6-172">To import new retention labels and modify existing retention labels:</span></span> 

1. <span data-ttu-id="9b1b6-173">**ファイル計画**ページで、[**インポート**をクリックし、**ファイル計画の記入とインポート**ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-173">On the **File plan** page, click **Import** to use the **Fill out and import your file plan** page:</span></span>

   ![ファイル計画のインポートのオプション](../media/compliance-file-plan-import-labels.png)

   ![空白のファイル計画テンプレートをダウンロードするオプション](../media/file-plan-blank-template-option.png)

2. <span data-ttu-id="9b1b6-176">空白のテンプレートをダウンロードして、新しい保持ラベルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-176">Download a blank template to import new retention labels.</span></span> <span data-ttu-id="9b1b6-177">または、組織の既存の保持ラベルをエクスポートするときにエクスポートされる .csv ファイルから開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-177">Alternatively, you can start with the .csv file that is exported when you export the existing retention labels in your organization.</span></span>

   ![Excel での開かれた空白のファイル計画テンプレート](../media/file-plan-blank-template.png)

3. <span data-ttu-id="9b1b6-179">プロパティと各プロパティへの有効な値を説明する次の情報を使用して、テンプレートに入力します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-179">Fill out the template, using the following information that describes the properties and valid values for each property.</span></span> <span data-ttu-id="9b1b6-180">インポートの場合、各値の長さは最大で 64 文字です。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-180">For import, each value has a maximum length of 64 characters.</span></span> <br/>

   |<span data-ttu-id="9b1b6-181">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9b1b6-181">Property</span></span>|<span data-ttu-id="9b1b6-182">種類</span><span class="sxs-lookup"><span data-stu-id="9b1b6-182">Type</span></span>|<span data-ttu-id="9b1b6-183">有効な値</span><span class="sxs-lookup"><span data-stu-id="9b1b6-183">Valid values</span></span>|
   |:-----|:-----|:-----|
   |<span data-ttu-id="9b1b6-184">LabelName</span><span class="sxs-lookup"><span data-stu-id="9b1b6-184">LabelName</span></span>|<span data-ttu-id="9b1b6-185">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-185">String</span></span>|<span data-ttu-id="9b1b6-186">このプロパティは、保持ラベルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-186">This property specifies the name of the retention label.</span></span>|
   |<span data-ttu-id="9b1b6-187">コメント</span><span class="sxs-lookup"><span data-stu-id="9b1b6-187">Comment</span></span>|<span data-ttu-id="9b1b6-188">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-188">String</span></span>|<span data-ttu-id="9b1b6-189">このプロパティを使用して、管理者の保持ラベルに関する説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-189">Use this property to add a description about the retention label for admins.</span></span> <span data-ttu-id="9b1b6-190">この説明は、コンプライアンス センターでラベルを管理する管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-190">This description appears only to admins who manage the retention label in the compliance center.</span></span>|
   |<span data-ttu-id="9b1b6-191">Notes</span><span class="sxs-lookup"><span data-stu-id="9b1b6-191">Notes</span></span>|<span data-ttu-id="9b1b6-192">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-192">String</span></span>|<span data-ttu-id="9b1b6-193">このプロパティを使用して、ユーザーの保持ラベルに関する説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-193">Use this property to add a description about the retention label for users.</span></span> <span data-ttu-id="9b1b6-194">この説明は、ユーザーが Outlook、SharePoint、OneDrive などのアプリでラベルにカーソルを置いたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-194">This description appears when users hover over the label in apps like Outlook, SharePoint, and OneDrive.</span></span> <span data-ttu-id="9b1b6-195">このプロパティを空白のままにすると、ラベルの保持設定を説明する既定の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-195">If you leave this property blank, a default description is displayed, which explains the label's retention settings.</span></span> |
   |<span data-ttu-id="9b1b6-196">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="9b1b6-196">IsRecordLabel</span></span>|<span data-ttu-id="9b1b6-197">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-197">String</span></span>|<span data-ttu-id="9b1b6-198">このプロパティでは、ラベルがコンテンツをレコードとしてマークするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-198">This property specifies whether the label marks the content as a record.</span></span> <span data-ttu-id="9b1b6-199">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-199">Valid values are:</span></span> </br><span data-ttu-id="9b1b6-200">**TRUE**: ラベルはアイテムをレコードとしてマークし、その結果としてアイテムを削除できません。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-200">**TRUE**: The label marks the item as a record and as a result, the item can't be deleted.</span></span> </br><span data-ttu-id="9b1b6-201">**FALSE**: ラベルは、コンテンツをレコードとしてマークしません。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-201">**FALSE**: The label doesn't mark the content as a record.</span></span> <span data-ttu-id="9b1b6-202">これは既定の値です。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-202">This is the default value.</span></span>|
   |<span data-ttu-id="9b1b6-203">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="9b1b6-203">RetentionAction</span></span>|<span data-ttu-id="9b1b6-204">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-204">String</span></span>|<span data-ttu-id="9b1b6-205">このプロパティは、RetentionDuration プロパティで指定された値の有効期限が切れた後に実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-205">This property specifies what action to take after the value specified by the RetentionDuration property expires.</span></span> <span data-ttu-id="9b1b6-206">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-206">Valid values are:</span></span> </br><span data-ttu-id="9b1b6-207">**Delete**: RetentionDuration プロパティで指定された値よりも古いアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-207">**Delete**: Items older than the value specified by the RetentionDuration property are deleted.</span></span></br><span data-ttu-id="9b1b6-208">**Keep**: RetentionDuration プロパティで指定された期間のアイテムを保持し、期間が終了しても何もしません。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-208">**Keep**: Retain items for the duration specified by the RetentionDuration property and then do nothing when the duration period expires.</span></span> </br><span data-ttu-id="9b1b6-209">**KeepAndDelete**: RetentionDuration プロパティで指定された期間のアイテムを保持し、期間が終了したらそれらを削除します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-209">**KeepAndDelete**: Retain items for the duration specified by the RetentionDuration property and then delete them when the duration period expires.</span></span>   |
   |<span data-ttu-id="9b1b6-210">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="9b1b6-210">RetentionDuration</span></span>|<span data-ttu-id="9b1b6-211">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-211">String</span></span>|<span data-ttu-id="9b1b6-212">プロパティは、コンテンツを保持する日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-212">This property specifies the number of days to retain the content.</span></span> <span data-ttu-id="9b1b6-213">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-213">Valid values are:</span></span> </br><span data-ttu-id="9b1b6-214">**Unlimited**: アイテムは無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-214">**Unlimited**: Items will be retained indefinitely.</span></span> </br><span data-ttu-id="9b1b6-215">***n***: 正の整数です。(例: **365**)</span><span class="sxs-lookup"><span data-stu-id="9b1b6-215">***n***: A positive integer; for example, **365**.</span></span> 
   |<span data-ttu-id="9b1b6-216">RetentionType</span><span class="sxs-lookup"><span data-stu-id="9b1b6-216">RetentionType</span></span>|<span data-ttu-id="9b1b6-217">String</span><span class="sxs-lookup"><span data-stu-id="9b1b6-217">String</span></span>|<span data-ttu-id="9b1b6-218">プロパティは、コンテンツ作成日、イベント日、ラベルが付けられた日、または最終変更日のいずれから保持期間を計算するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-218">This property specifies whether the retention duration is calculated from the content creation date, event date, when labeled date, or last modified date.</span></span> <span data-ttu-id="9b1b6-219">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-219">Valid values are:</span></span> </br><span data-ttu-id="9b1b6-220">**CreationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-220">**CreationAgeInDays**</span></span></br><span data-ttu-id="9b1b6-221">**EventAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-221">**EventAgeInDays**</span></span></br><span data-ttu-id="9b1b6-222">**TaggedAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-222">**TaggedAgeInDays**</span></span></br><span data-ttu-id="9b1b6-223">**ModificationAgeInDays**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-223">**ModificationAgeInDays**</span></span> |
   |<span data-ttu-id="9b1b6-224">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="9b1b6-224">ReviewerEmail</span></span>|<span data-ttu-id="9b1b6-225">SmtpAddress</span><span class="sxs-lookup"><span data-stu-id="9b1b6-225">SmtpAddress</span></span>|<span data-ttu-id="9b1b6-226">このプロパティが入力されている場合、保持期間が終了すると、廃棄のレビューがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-226">When this property is populated, a disposition review will be triggered when the retention duration expires.</span></span> <span data-ttu-id="9b1b6-227">プロパティは、**KeepAndDelete** の保持期間用アクションのレビュー担当者の電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-227">This property specifies the email address of a reviewer for the **KeepAndDelete** retention action.</span></span> <span data-ttu-id="9b1b6-228">個々のユーザー、配布グループまたはセキュリティ グループのメール アドレスを含めることが出来ます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-228">You can include the email address of individual users, distribution groups, or security groups.</span></span> <span data-ttu-id="9b1b6-229">複数のメール アドレスをセミコロンで区切って指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-229">You can specify multiple email addresses separated by semicolons.</span></span>|
   |<span data-ttu-id="9b1b6-230">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="9b1b6-230">ReferenceId</span></span>|<span data-ttu-id="9b1b6-231">String</span><span class="sxs-lookup"><span data-stu-id="9b1b6-231">String</span></span>|<span data-ttu-id="9b1b6-232">このプロパティは、**参照 ID** ファイル計画記述子に表示される値を指定します。そしてこれは組織の固有の値として使うことが出来ます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-232">This property specifies the value that's displayed in the **Reference Id** file plan descriptor, which you can use as a unique value to your organization.</span></span>| 
   |<span data-ttu-id="9b1b6-233">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="9b1b6-233">DepartmentName</span></span>|<span data-ttu-id="9b1b6-234">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-234">String</span></span>|<span data-ttu-id="9b1b6-235">このプロパティは、**業務/部署**ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-235">This property specifies the value that's displayed in the **Function/department** file plan descriptor.</span></span>|
   |<span data-ttu-id="9b1b6-236">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9b1b6-236">Category</span></span>|<span data-ttu-id="9b1b6-237">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-237">String</span></span>|<span data-ttu-id="9b1b6-238">このプロパティは、**カテゴリ** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-238">This property specifies the value that's displayed in the **Category** file plan descriptor.</span></span>|
   |<span data-ttu-id="9b1b6-239">下位カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9b1b6-239">SubCategory</span></span>|<span data-ttu-id="9b1b6-240">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-240">String</span></span>|<span data-ttu-id="9b1b6-241">このプロパティは、**サブカテゴリ** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-241">This property specifies the value that's displayed in the **Sub category** file plan descriptor.</span></span>|
   |<span data-ttu-id="9b1b6-242">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="9b1b6-242">AuthorityType</span></span>|<span data-ttu-id="9b1b6-243">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-243">String</span></span>|<span data-ttu-id="9b1b6-244">このプロパティは、**管理組織の種類** ファイル計画記述子に表示される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-244">This property specifies the value that's displayed in the **Authority type** file plan descriptor.</span></span>|
   |<span data-ttu-id="9b1b6-245">CitationName</span><span class="sxs-lookup"><span data-stu-id="9b1b6-245">CitationName</span></span>|<span data-ttu-id="9b1b6-246">String</span><span class="sxs-lookup"><span data-stu-id="9b1b6-246">String</span></span>|<span data-ttu-id="9b1b6-247">このプロパティは、**プロビジョニング/引用** ファイル計画記述子に表示される引用の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-247">This property specifies the name of the citation displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="9b1b6-248">例として、「2002 年米国企業改革法」。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-248">For example, "Sarbanes-Oxley Act of 2002".</span></span> |
   |<span data-ttu-id="9b1b6-249">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="9b1b6-249">CitationUrl</span></span>|<span data-ttu-id="9b1b6-250">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-250">String</span></span>|<span data-ttu-id="9b1b6-251">このプロパティは、**規定/引用** ファイル計画記述子に表示される URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-251">This property specifies the URL that's displayed in the **Provision/citation** file plan descriptor.</span></span>|
   |<span data-ttu-id="9b1b6-252">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="9b1b6-252">CitationJurisdiction</span></span>|<span data-ttu-id="9b1b6-253">String</span><span class="sxs-lookup"><span data-stu-id="9b1b6-253">String</span></span>|<span data-ttu-id="9b1b6-254">このプロパティは、**プロビジョニング/引用** ファイル計画記述子に表示される管轄または機関を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-254">This property specifies the jurisdiction or agency that's displayed in the **Provision/citation** file plan descriptor.</span></span> <span data-ttu-id="9b1b6-255">例として、「米国証券取引委員会 (SEC)」。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-255">For example, "U.S. Securities and Exchange Commission (SEC)".</span></span>|
   |<span data-ttu-id="9b1b6-256">規制</span><span class="sxs-lookup"><span data-stu-id="9b1b6-256">Regulatory</span></span>|<span data-ttu-id="9b1b6-257">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-257">String</span></span>|<span data-ttu-id="9b1b6-258">空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-258">Leave blank.</span></span> <span data-ttu-id="9b1b6-259">現時点では、このプロパティは使用されていません。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-259">This property isn't used at this time.</span></span>|
   |<span data-ttu-id="9b1b6-260">EventType</span><span class="sxs-lookup"><span data-stu-id="9b1b6-260">EventType</span></span>|<span data-ttu-id="9b1b6-261">文字列</span><span class="sxs-lookup"><span data-stu-id="9b1b6-261">String</span></span>|<span data-ttu-id="9b1b6-262">このプロパティは、ラベルに関連付けられている保持規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-262">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="9b1b6-263">ルールを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-263">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="9b1b6-264">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-264">For example:</span></span></br><span data-ttu-id="9b1b6-265">**名前**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-265">**Name**</span></span></br><span data-ttu-id="9b1b6-266">**識別名 (DN)**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-266">**Distinguished name (DN)**</span></span></br><span data-ttu-id="9b1b6-267">**GUID**</span><span class="sxs-lookup"><span data-stu-id="9b1b6-267">**GUID**</span></span> </br><span data-ttu-id="9b1b6-268">使用可能な保持規則を確認するには、[Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule?view=exchange-ps) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-268">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span> <span data-ttu-id="9b1b6-269">EventTypeの値は組織に固有であるからということに注意してください。1 つの組織からラベルをエクスポートする場合、別の組織にラベルをインポートするときに、その組織の EventType プロパティの値を使用できません。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-269">Note that because the EventType values are unique to an organization, if you export labels from one organization, you can't use the values for the EventType property from that organization to import labels into a different organization.</span></span>|
   |||

   <span data-ttu-id="9b1b6-270">保持ラベルに関する情報を含むテンプレートの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-270">Here's an example of the template containing the information about retention labels.</span></span>

   ![情報が入力されたファイル計画テンプレート](../media/file-plan-filled-out-template.png)

4. <span data-ttu-id="9b1b6-272">**ファイル計画を入力しインポートする**ページの手順 3 で、**ファイルの参照** をクリックして、入力済みのテンプレートをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-272">Under step 3 on the **Fill out and import your file plan** page, click **Browse for files** to upload the filled-out template.</span></span> 

   <span data-ttu-id="9b1b6-273">ファイル計画はエントリを検証し、インポートの統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-273">File plan validates the entries and displays the import statistics.</span></span>

   ![ファイル計画のインポートの統計情報](../media/file-plan-import-statistics.png)

   <span data-ttu-id="9b1b6-275">検証エラーがある場合、ファイル計画のインポートはインポートファイル内のすべてのエントリの検証を続け、インポートファイル内の行と行の番号を参照し全てのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-275">If there's a validation error, file plan import continues to validate every entry in the import file and displays all errors  referencing the line and row numbers in the import file.</span></span> <span data-ttu-id="9b1b6-276">インポートファイルに戻るときに修正できるように、表示されたエラー結果をコピーします。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-276">Copy the displayed error results so you can correct them when you return to the import file.</span></span>

<span data-ttu-id="9b1b6-277">インポートが完了したら、新しい保持ラベルポリシーに保持ラベルを追加したり、もしくは自動適用したりできます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-277">When the import is complete, you can now add the retention labels to a new retention label policy, or auto-apply them.</span></span> <span data-ttu-id="9b1b6-278">**File plan**ページのから ドロップダウンで **+ Create a label**を選択、次に **ラベル発行のポリシー**、もしくは**ラベル自動適用のポリシー**の手順でこの権利を行えます。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-278">You can do this right from the **File plan** page by selecting the dropdown from **+ Create a label** and then **Policy to publish labels**, or **Policy to auto-apply a label**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9b1b6-279">次の手順</span><span class="sxs-lookup"><span data-stu-id="9b1b6-279">Next steps</span></span>

<span data-ttu-id="9b1b6-280">保持ラベルの作成と編集、およびそのポリシーの詳細については以下のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b1b6-280">For more information about creating and editing retention labels and their policies, see the following guidance:</span></span>
- [<span data-ttu-id="9b1b6-281">アイテム保持ラベルを作成して、アプリに適用する</span><span class="sxs-lookup"><span data-stu-id="9b1b6-281">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="9b1b6-282">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="9b1b6-282">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)
