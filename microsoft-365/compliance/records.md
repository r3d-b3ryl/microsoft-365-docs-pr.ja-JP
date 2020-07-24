---
title: レコードについての詳細
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Microsoft 365 でのレコード管理ソリューションの実装に役立つレコードについて説明します。
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372522"
---
# <a name="learn-about-records"></a><span data-ttu-id="76a21-103">レコードについての詳細</span><span class="sxs-lookup"><span data-stu-id="76a21-103">Learn about records</span></span>

><span data-ttu-id="76a21-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="76a21-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="76a21-105">Microsoft 365 でレコードを管理することで、組織は企業のポリシー、法的および規制上の義務を順守し、リスクや法的責任を軽減することもできます。</span><span class="sxs-lookup"><span data-stu-id="76a21-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="76a21-106">コンテンツがレコードとしてマークされているときには:</span><span class="sxs-lookup"><span data-stu-id="76a21-106">When content is marked as a record:</span></span>

- <span data-ttu-id="76a21-107">[アクションが許可またはブロックされている](#compare-restrictions-for-what-actions-are-allowed-or-blocked) という観点から、アイテムに制限がかけられています。</span><span class="sxs-lookup"><span data-stu-id="76a21-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="76a21-108">アイテムに関する追加のアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="76a21-109">アイテムが保持期間の終了時に削除された時点で、廃棄の証明を取得します。</span><span class="sxs-lookup"><span data-stu-id="76a21-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="76a21-110">[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="76a21-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="76a21-111">それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="76a21-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="76a21-112">保持ラベルを使用してコンテンツをレコードとして宣言することで、Microsoft 365 環境全体で単一かつ一貫したレコード管理戦略を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="76a21-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="76a21-113">許可またはブロックするアクションの制限を比較する</span><span class="sxs-lookup"><span data-stu-id="76a21-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="76a21-114">次の表を使用して、標準の保持ラベルを適用した結果、コンテンツに適用される制限事項、およびコンテンツをレコードとしてマークする保持ラベルを特定します。</span><span class="sxs-lookup"><span data-stu-id="76a21-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="76a21-115">標準的な保持ラベルには、コンテンツをレコードとしてマークすることなくデータを保持する構成があります。</span><span class="sxs-lookup"><span data-stu-id="76a21-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="76a21-116">完全性を期すために、テーブルにはロックされたレコードの列とロック解除されたレコードの列が含まれています。これは、SharePoint と OneDrive には適用できますが、Exchange には適用されません。</span><span class="sxs-lookup"><span data-stu-id="76a21-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="76a21-117">レコードをロックまたはロック解除する機能は、Exchange アイテムでサポートされていない [レコード バージョン管理](#record-versioning) を使用します。</span><span class="sxs-lookup"><span data-stu-id="76a21-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="76a21-118">そのため、レコードとしてマークされているすべての Exchange アイテムについて、[**レコード - ロック済み**] 列に動作がマップされ、[**レコード - ロック解除**] は関連がありません。</span><span class="sxs-lookup"><span data-stu-id="76a21-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="76a21-119">アクション</span><span class="sxs-lookup"><span data-stu-id="76a21-119">Action</span></span>| <span data-ttu-id="76a21-120">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="76a21-120">Retention label</span></span> |<span data-ttu-id="76a21-121">レコード - ロック済み</span><span class="sxs-lookup"><span data-stu-id="76a21-121">Record - locked</span></span>| <span data-ttu-id="76a21-122">レコード - ロック解除</span><span class="sxs-lookup"><span data-stu-id="76a21-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76a21-123">コンテンツを編集する</span><span class="sxs-lookup"><span data-stu-id="76a21-123">Edit contents</span></span>|<span data-ttu-id="76a21-124">可</span><span class="sxs-lookup"><span data-stu-id="76a21-124">Allowed</span></span> | <span data-ttu-id="76a21-125">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="76a21-125">**Blocked**</span></span> | <span data-ttu-id="76a21-126">可</span><span class="sxs-lookup"><span data-stu-id="76a21-126">Allowed</span></span>|
|<span data-ttu-id="76a21-127">名前の変更など、プロパティを編集する</span><span class="sxs-lookup"><span data-stu-id="76a21-127">Edit properties, including rename</span></span>|<span data-ttu-id="76a21-128">可</span><span class="sxs-lookup"><span data-stu-id="76a21-128">Allowed</span></span> |<span data-ttu-id="76a21-129">可</span><span class="sxs-lookup"><span data-stu-id="76a21-129">Allowed</span></span> | <span data-ttu-id="76a21-130">可</span><span class="sxs-lookup"><span data-stu-id="76a21-130">Allowed</span></span>|
|<span data-ttu-id="76a21-131">削除</span><span class="sxs-lookup"><span data-stu-id="76a21-131">Delete</span></span>|<span data-ttu-id="76a21-132">許可 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="76a21-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="76a21-133">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="76a21-133">**Blocked**</span></span> | <span data-ttu-id="76a21-134">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="76a21-134">**Blocked**</span></span>|
|<span data-ttu-id="76a21-135">コピー</span><span class="sxs-lookup"><span data-stu-id="76a21-135">Copy</span></span>|<span data-ttu-id="76a21-136">可</span><span class="sxs-lookup"><span data-stu-id="76a21-136">Allowed</span></span> |<span data-ttu-id="76a21-137">可</span><span class="sxs-lookup"><span data-stu-id="76a21-137">Allowed</span></span> | <span data-ttu-id="76a21-138">可</span><span class="sxs-lookup"><span data-stu-id="76a21-138">Allowed</span></span>|
|<span data-ttu-id="76a21-139">コンテナー内の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="76a21-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="76a21-140">可</span><span class="sxs-lookup"><span data-stu-id="76a21-140">Allowed</span></span> |<span data-ttu-id="76a21-141">可</span><span class="sxs-lookup"><span data-stu-id="76a21-141">Allowed</span></span> | <span data-ttu-id="76a21-142">可</span><span class="sxs-lookup"><span data-stu-id="76a21-142">Allowed</span></span>|
|<span data-ttu-id="76a21-143">コンテナー間の移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="76a21-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="76a21-144">可</span><span class="sxs-lookup"><span data-stu-id="76a21-144">Allowed</span></span> |<span data-ttu-id="76a21-145">ロック解除されていない場合は許可</span><span class="sxs-lookup"><span data-stu-id="76a21-145">Allowed if never unlocked</span></span> | <span data-ttu-id="76a21-146">可</span><span class="sxs-lookup"><span data-stu-id="76a21-146">Allowed</span></span>|
|<span data-ttu-id="76a21-147">開く/読み取り</span><span class="sxs-lookup"><span data-stu-id="76a21-147">Open/Read</span></span>|<span data-ttu-id="76a21-148">可</span><span class="sxs-lookup"><span data-stu-id="76a21-148">Allowed</span></span> |<span data-ttu-id="76a21-149">可</span><span class="sxs-lookup"><span data-stu-id="76a21-149">Allowed</span></span> | <span data-ttu-id="76a21-150">可</span><span class="sxs-lookup"><span data-stu-id="76a21-150">Allowed</span></span>|
|<span data-ttu-id="76a21-151">ラベルを変更する</span><span class="sxs-lookup"><span data-stu-id="76a21-151">Change label</span></span>|<span data-ttu-id="76a21-152">可</span><span class="sxs-lookup"><span data-stu-id="76a21-152">Allowed</span></span> |<span data-ttu-id="76a21-153">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="76a21-153">Allowed - container admin only</span></span> | <span data-ttu-id="76a21-154">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="76a21-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="76a21-155">ラベルを削除する</span><span class="sxs-lookup"><span data-stu-id="76a21-155">Remove label</span></span>|<span data-ttu-id="76a21-156">可</span><span class="sxs-lookup"><span data-stu-id="76a21-156">Allowed</span></span> |<span data-ttu-id="76a21-157">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="76a21-157">Allowed - container admin only</span></span> | <span data-ttu-id="76a21-158">許可-コンテナー管理のみ</span><span class="sxs-lookup"><span data-stu-id="76a21-158">Allowed - container admin only</span></span>|

<span data-ttu-id="76a21-159">脚注:</span><span class="sxs-lookup"><span data-stu-id="76a21-159">Footnotes:</span></span>

<span data-ttu-id="76a21-160"><sup>1</sup> セキュリティ保護された場所にコピーを保持することによって、OneDrive と Exchange ではサポートされますが、SharePoint ではブロックされます。</span><span class="sxs-lookup"><span data-stu-id="76a21-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="76a21-161">ユーザーが SharePoint のラベル付きドキュメントを削除しようとしたときに表示されるメッセージは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76a21-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![SharePoint の「アイテムが削除されませんでした」というメッセージ](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="76a21-163"><sup>2</sup> コンテナーには、SharePoint ドキュメント ライブラリと Exchange メールボックスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76a21-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="76a21-164">保持ラベルを使用してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="76a21-164">Using retention labels to declare records</span></span>

<span data-ttu-id="76a21-165">保持ラベルを作成するときに、保持ラベルを使用してコンテンツをレコードとしてマークするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="76a21-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="76a21-166">Microsoft 365 コンプライアンス センターで、[**レコードの管理**] [\>ファイル プラン\*\*] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76a21-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="76a21-167">[**ファイルプラン**] ページで、[**ラベルの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="76a21-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="76a21-168">ウィザードの [**ラベルの設定**] ページで、コンテンツをレコードとして分類するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="76a21-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![[このラベルを使用して、コンテンツをレコードに分類する] チェックボックスをクリックします](../media/recordversioning6.png)

3. <span data-ttu-id="76a21-170">必要に応じて、SharePoint や OneDrive のドキュメントと Exchange メールに保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="76a21-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="76a21-171">手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76a21-171">For instructions:</span></span>
    
    - [<span data-ttu-id="76a21-172">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="76a21-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="76a21-173">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="76a21-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="76a21-174">コンテンツに構成した保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="76a21-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="76a21-175">保持ラベルは、コンテンツをレコードとしてマークする場合、ユーザーが以下のようにアプリ内でそれを適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="76a21-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="76a21-176">Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、これらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="76a21-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="76a21-177">SharePoint および OneDrive の場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがこれらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="76a21-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="76a21-178">保持ラベルを使用してレコードとしてマークされたドキュメントの例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76a21-178">Example of a document marked as record by using a retention label:</span></span>

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="76a21-180">レコードのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="76a21-180">Record versioning</span></span>

<span data-ttu-id="76a21-181">ドキュメントをレコードとしてマークし、レコードに対して実行できるアクションを制限する機能は、あらゆるレコード管理ソリューションに不可欠な目標です。</span><span class="sxs-lookup"><span data-stu-id="76a21-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="76a21-182">ただし、後進のバージョンを作成するためには、他のユーザーと共同作業を行うことも必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="76a21-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="76a21-183">たとえば、販売契約をレコードとしてマークする場合、新しい条件で契約を更新し、そして前のレコード バージョンを保持したまま最新バージョンを新しいレコードとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76a21-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="76a21-184">これらのタイプのシナリオでは、SharePoint と OneDrive が*レコードのバージョン管理*をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="76a21-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="76a21-185">OneNote ノートブックのフォルダーは、レコードのバージョン管理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="76a21-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="76a21-186">レコードのバージョン管理を使用するには、最初にドキュメントにラベルを付けて、レコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="76a21-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="76a21-187">この時点で、*レコード ステータス* と呼ばれるドキュメント プロパティが保持ラベルの横に表示され、初期レコード ステータスは **ロック済み** になります。</span><span class="sxs-lookup"><span data-stu-id="76a21-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="76a21-188">次のことができます。</span><span class="sxs-lookup"><span data-stu-id="76a21-188">You can now do the following things:</span></span>

  - <span data-ttu-id="76a21-189">**レコード ステータス プロパティをロック解除およびロックすることにより、ドキュメントの個々のバージョンをレコードとして継続的に編集および保持します。**</span><span class="sxs-lookup"><span data-stu-id="76a21-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="76a21-190">**レコード ステータス** プロパティが **ロックされています** に設定されている場合のみ、新しいバージョンのレコードが保持されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="76a21-191">このロックとロック解除の切り替えにより、ドキュメントの不要なバージョンおよびコピーを保持するリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="76a21-192">**サイト コレクション内にあるインプレース レコード リポジトリにレコードを自動的に保存します。**</span><span class="sxs-lookup"><span data-stu-id="76a21-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="76a21-193">SharePoint および OneDrive の各サイト コレクションは、アイテム保管ライブラリのコンテンツを保持します。</span><span class="sxs-lookup"><span data-stu-id="76a21-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="76a21-194">レコード バージョンは、このライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="76a21-195">**すべてのバージョンを含むエバーグリーン ドキュメントを維持します。**</span><span class="sxs-lookup"><span data-stu-id="76a21-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="76a21-196">既定では、各 SharePoint および OneDrive ドキュメントには、アイテム メニューで利用可能なバージョン履歴があります。</span><span class="sxs-lookup"><span data-stu-id="76a21-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="76a21-197">このバージョン履歴ではどのバージョンがレコードであるかを簡単に確認し、それらのドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="76a21-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="76a21-198">レコードのバージョン管理は、アイテムをレコードとしてマークする保持ラベルを持つすべてのドキュメントで自動的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="76a21-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="76a21-199">ユーザーが詳細ウィンドウでドキュメントのプロパティを表示すると、**レコード ステータス** が **ロック済み** から **ロック解除** に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="76a21-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="76a21-200">このアクションにより、アイテム保管ライブラリの [レコード] フォルダーにレコードが作成され、保存期間の残りの期間はそこに保存されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="76a21-201">ドキュメントのロックが解除されている間、標準の編集権限を持つすべてのユーザーがファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="76a21-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="76a21-202">ただし、これはまだレコードであるため、ユーザーはファイルを削除することができません。</span><span class="sxs-lookup"><span data-stu-id="76a21-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="76a21-203">編集が完了すると、**レコードの状態** を **ロック解除** から **ロック済み** に切り替えることができ、この状態の間はそれ以上の編集ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="76a21-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![レコードとしてタグ付けされたドキュメントのレコード ステータス プロパティ](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="76a21-205">レコードのロックおよびロック解除</span><span class="sxs-lookup"><span data-stu-id="76a21-205">Locking and unlocking a record</span></span>

<span data-ttu-id="76a21-206">コンテンツをレコードとしてマークする保持ラベルがドキュメントに適用された後、投稿権限またはより狭い権限レベルを持つユーザーは、レコードをロック解除したり、ロック解除されたレコードをロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="76a21-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![レコード ステータスは、レコード ドキュメントがロック解除されていることを示しています](../media/recordversioning9.png)

<span data-ttu-id="76a21-208">ユーザーがレコードのロックを解除すると、以下のアクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="76a21-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="76a21-209">現在のサイト コレクションにアイテム保管ライブラリがない場合は、それが作成されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="76a21-210">アイテム保管ライブラリに [レコード] フォルダーがない場合は、[レコード] フォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="76a21-211">[**コピー先**] アクションは、ドキュメントの最新バージョンを [レコード] フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="76a21-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="76a21-212">[**コピー先**] アクションには最新バージョンのみが含まれ、以前のバージョンは含まれません。</span><span class="sxs-lookup"><span data-stu-id="76a21-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="76a21-213">このコピーされたドキュメントはドキュメントのレコード バージョンと見なされ、ファイル名の形式は以下のようになります: \[タイトル GUID バージョン\#\]</span><span class="sxs-lookup"><span data-stu-id="76a21-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="76a21-214">[レコード] フォルダーに作成されたコピーは元のドキュメントのバージョン履歴に追加され、このバージョンでは、[コメント] フィールドに**レコード**という単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="76a21-215">元のドキュメントは、編集可能ですが削除はされない、新しいバージョンです。</span><span class="sxs-lookup"><span data-stu-id="76a21-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="76a21-216">ドキュメントが編集可能になった場合でもドキュメントはまだレコードであるため、ドキュメント ライブラリの [**アイテムはレコードです**] 列には引き続き [**はい**] の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="76a21-217">ユーザーがレコードをロックすると、元のドキュメントは再び編集ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="76a21-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="76a21-218">ただしこれは、バージョンをアイテム保管ライブラリの [レコード] フォルダーにコピーするレコードのロックを解除するアクションです。</span><span class="sxs-lookup"><span data-stu-id="76a21-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="76a21-219">レコードのバージョン</span><span class="sxs-lookup"><span data-stu-id="76a21-219">Record versions</span></span>

<span data-ttu-id="76a21-220">ユーザーがレコードのロックを解除するたびに、最新バージョンがアイテム保管ライブラリの [レコード] フォルダーにコピーされ、そのバージョンには**レコード**の値がバージョン履歴の [**コメント**] フィールドに含まれます。</span><span class="sxs-lookup"><span data-stu-id="76a21-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![アイテム保管ライブラリに表示されるレコード](../media/recordversioning10.png)

<span data-ttu-id="76a21-222">バージョン履歴を表示するには、ドキュメント ライブラリでドキュメントを選択し、[アイテム] メニューの [**バージョン履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76a21-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="76a21-223">レコードが保存される場所</span><span class="sxs-lookup"><span data-stu-id="76a21-223">Where records are stored</span></span>

<span data-ttu-id="76a21-224">レコードは、サイト コレクションのトップレベル サイトにあるアイテム保管ライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="76a21-225">トップレベル サイトの左側のナビゲーションで、[**サイト コンテンツ**] \> [**アイテム保管ライブラリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="76a21-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![アイテム保管ライブラリ](../media/recordversioning11.png)

<br/><br/>

![アイテム保管ライブラリの [レコード] フォルダー](../media/recordversioning12.png)

<span data-ttu-id="76a21-228">アイテム保管ライブラリは、サイト コレクション管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="76a21-229">また、アイテム保管ライブラリは規定では存在しません。</span><span class="sxs-lookup"><span data-stu-id="76a21-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="76a21-230">保持ラベルまたは保持ポリシーの対象となるコンテンツがサイト コレクション内で初めて削除された場合にのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="76a21-231">レコードのバージョン管理イベントの監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="76a21-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="76a21-232">レコードのロックおよびロック解除のアクションは、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="76a21-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="76a21-233">**レコード ステータスがロックに変更されました**および**レコード ステータスがロック解除に変更されました**の特定のアクティビティを検索できます。これらのアクティビティはセキュリティ/コンプライアンス センター内にあり、[**ファイルとページのアクティビティ**] セクションは [**アクティビティ**] ドロップダウン リストに、そしてこのドロップダウン リストは [**監査ログの検索**] ページ にあります。</span><span class="sxs-lookup"><span data-stu-id="76a21-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![レコードのバージョン管理イベントの監査ログを検索する](../media/recordversioning13.png)

<span data-ttu-id="76a21-235">これらのイベントの検索に関する詳細情報については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)」の "ファイルとページのアクティビティ" セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76a21-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="76a21-236">次の手順</span><span class="sxs-lookup"><span data-stu-id="76a21-236">Next steps</span></span>

<span data-ttu-id="76a21-237">レコード管理に使用する保持ラベルをまだ作成していない場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76a21-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="76a21-238">レコードの廃棄の詳細については、「[コンテンツの廃棄](disposition.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76a21-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
