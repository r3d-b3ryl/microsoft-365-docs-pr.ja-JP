---
title: SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する
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
ms.openlocfilehash: 943bf3949ab57eb4603695495d7a8ca0c4b90db7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695261"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="259bd-103">SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する</span><span class="sxs-lookup"><span data-stu-id="259bd-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="259bd-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="259bd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="259bd-105">ドキュメントを [レコード](records.md)としてマークし、レコードに対して実行できるアクションを制限する機能は、あらゆるレコード管理ソリューションに不可欠な目標です。</span><span class="sxs-lookup"><span data-stu-id="259bd-105">The ability to mark a document as a [record](records.md) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="259bd-106">ただし、後進のバージョンを作成するためには、他のユーザーと共同作業を行うことも必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="259bd-106">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="259bd-107">たとえば、販売契約をレコードとしてマークする場合、新しい条件で契約を更新し、そして前のレコード バージョンを保持したまま最新バージョンを新しいレコードとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="259bd-107">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="259bd-108">これらのタイプのシナリオでは、SharePoint と OneDrive が*レコードのバージョン管理*をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="259bd-108">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="259bd-109">OneNote ノートブックのフォルダーは、レコードのバージョン管理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="259bd-109">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="259bd-110">レコードのバージョン管理を使用するには、最初に[ドキュメントにラベルを付けて、レコードとしてマークします](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="259bd-110">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="259bd-111">この時点で、*レコード ステータス* と呼ばれるドキュメント プロパティが保持ラベルの横に表示され、初期レコード ステータスは **ロック済み** になります。</span><span class="sxs-lookup"><span data-stu-id="259bd-111">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="259bd-112">次のことができます。</span><span class="sxs-lookup"><span data-stu-id="259bd-112">You can now do the following things:</span></span>

  - <span data-ttu-id="259bd-113">**レコード ステータス プロパティをロック解除およびロックすることにより、ドキュメントの個々のバージョンをレコードとして継続的に編集および保持します。**</span><span class="sxs-lookup"><span data-stu-id="259bd-113">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="259bd-114">**レコード ステータス** プロパティが **ロックされています** に設定されている場合のみ、新しいバージョンのレコードが保持されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-114">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="259bd-115">このロックとロック解除の切り替えにより、ドキュメントの不要なバージョンおよびコピーを保持するリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-115">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="259bd-116">**サイト コレクション内にあるインプレース レコード リポジトリにレコードを自動的に保存します。**</span><span class="sxs-lookup"><span data-stu-id="259bd-116">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="259bd-117">SharePoint および OneDrive の各サイト コレクションは、アイテム保管ライブラリのコンテンツを保持します。</span><span class="sxs-lookup"><span data-stu-id="259bd-117">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="259bd-118">レコード バージョンは、このライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-118">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="259bd-119">**すべてのバージョンを含むエバーグリーン ドキュメントを維持します。**</span><span class="sxs-lookup"><span data-stu-id="259bd-119">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="259bd-120">既定では、各 SharePoint および OneDrive ドキュメントには、アイテム メニューで利用可能なバージョン履歴があります。</span><span class="sxs-lookup"><span data-stu-id="259bd-120">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="259bd-121">このバージョン履歴ではどのバージョンがレコードであるかを簡単に確認し、それらのドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="259bd-121">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="259bd-122">レコードのバージョン管理は、アイテムをレコードとしてマークする保持ラベルを持つすべてのドキュメントで自動的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="259bd-122">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="259bd-123">ユーザーが詳細ウィンドウでドキュメントのプロパティを表示すると、**レコード ステータス** が **ロック済み** から **ロック解除** に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="259bd-123">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="259bd-124">このアクションにより、アイテム保管ライブラリの [レコード] フォルダーにレコードが作成され、保存期間の残りの期間はそこに保存されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-124">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="259bd-125">ドキュメントのロックが解除されている間、標準の編集権限を持つすべてのユーザーがファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="259bd-125">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="259bd-126">ただし、これはまだレコードであるため、ユーザーはファイルを削除することができません。</span><span class="sxs-lookup"><span data-stu-id="259bd-126">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="259bd-127">編集が完了すると、**レコードの状態** を **ロック解除** から **ロック済み** に切り替えることができ、この状態の間はそれ以上の編集ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="259bd-127">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![レコードとしてタグ付けされたドキュメントのレコード ステータス プロパティ](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="259bd-129">レコードのロックおよびロック解除</span><span class="sxs-lookup"><span data-stu-id="259bd-129">Locking and unlocking a record</span></span>

<span data-ttu-id="259bd-130">コンテンツをレコードとしてマークする保持ラベルがドキュメントに適用された後、投稿権限またはより狭い権限レベルを持つユーザーは、レコードをロック解除したり、ロック解除されたレコードをロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="259bd-130">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![レコード ステータスは、レコード ドキュメントがロック解除されていることを示しています](../media/recordversioning9.png)

<span data-ttu-id="259bd-132">ユーザーがレコードのロックを解除すると、以下のアクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="259bd-132">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="259bd-133">現在のサイト コレクションにアイテム保管ライブラリがない場合は、それが作成されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-133">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="259bd-134">アイテム保管ライブラリに [レコード] フォルダーがない場合は、[レコード] フォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-134">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="259bd-135">[**コピー先**] アクションは、ドキュメントの最新バージョンを [レコード] フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="259bd-135">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="259bd-136">[**コピー先**] アクションには最新バージョンのみが含まれ、以前のバージョンは含まれません。</span><span class="sxs-lookup"><span data-stu-id="259bd-136">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="259bd-137">このコピーされたドキュメントはドキュメントのレコード バージョンと見なされ、ファイル名の形式は以下のようになります: \[タイトル GUID バージョン\#\]</span><span class="sxs-lookup"><span data-stu-id="259bd-137">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="259bd-138">[レコード] フォルダーに作成されたコピーは元のドキュメントのバージョン履歴に追加され、このバージョンでは、[コメント] フィールドに**レコード**という単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-138">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="259bd-139">元のドキュメントは、編集可能ですが削除はされない、新しいバージョンです。</span><span class="sxs-lookup"><span data-stu-id="259bd-139">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="259bd-140">ドキュメントが編集可能になった場合でもドキュメントはまだレコードであるため、ドキュメント ライブラリの [**アイテムはレコードです**] 列には引き続き [**はい**] の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-140">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="259bd-141">ユーザーがレコードをロックすると、元のドキュメントは再び編集ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="259bd-141">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="259bd-142">ただしこれは、バージョンをアイテム保管ライブラリの [レコード] フォルダーにコピーするレコードのロックを解除するアクションです。</span><span class="sxs-lookup"><span data-stu-id="259bd-142">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="259bd-143">レコードのバージョン</span><span class="sxs-lookup"><span data-stu-id="259bd-143">Record versions</span></span>

<span data-ttu-id="259bd-144">ユーザーがレコードのロックを解除するたびに、最新バージョンがアイテム保管ライブラリの [レコード] フォルダーにコピーされ、そのバージョンには**レコード**の値がバージョン履歴の [**コメント**] フィールドに含まれます。</span><span class="sxs-lookup"><span data-stu-id="259bd-144">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![アイテム保管ライブラリに表示されるレコード](../media/recordversioning10.png)

<span data-ttu-id="259bd-146">バージョン履歴を表示するには、ドキュメント ライブラリでドキュメントを選択し、[アイテム] メニューの [**バージョン履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="259bd-146">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="259bd-147">レコードが保存される場所</span><span class="sxs-lookup"><span data-stu-id="259bd-147">Where records are stored</span></span>

<span data-ttu-id="259bd-148">レコードは、サイト コレクションのトップレベル サイトにあるアイテム保管ライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-148">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="259bd-149">トップレベル サイトの左側のナビゲーションで、[**サイト コンテンツ**] \> [**アイテム保管ライブラリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="259bd-149">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![アイテム保管ライブラリ](../media/recordversioning11.png)

<br/><br/>

![アイテム保管ライブラリの [レコード] フォルダー](../media/recordversioning12.png)

<span data-ttu-id="259bd-152">アイテム保管ライブラリは、サイト コレクション管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-152">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="259bd-153">また、アイテム保管ライブラリは規定では存在しません。</span><span class="sxs-lookup"><span data-stu-id="259bd-153">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="259bd-154">保持ラベルまたは保持ポリシーの対象となるコンテンツがサイト コレクション内で初めて削除された場合にのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-154">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="259bd-155">レコードのバージョン管理イベントの監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="259bd-155">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="259bd-156">レコードのロックおよびロック解除のアクションは、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="259bd-156">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="259bd-157">**レコード ステータスがロックに変更されました**および**レコード ステータスがロック解除に変更されました**の特定のアクティビティを検索できます。これらのアクティビティはセキュリティ/コンプライアンス センター内にあり、[**ファイルとページのアクティビティ**] セクションは [**アクティビティ**] ドロップダウン リストに、そしてこのドロップダウン リストは [**監査ログの検索**] ページ にあります。</span><span class="sxs-lookup"><span data-stu-id="259bd-157">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![レコードのバージョン管理イベントの監査ログを検索する](../media/recordversioning13.png)

<span data-ttu-id="259bd-159">これらのイベントの検索に関する詳細情報については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)」の "ファイルとページのアクティビティ" セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="259bd-159">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="259bd-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="259bd-160">Next steps</span></span>

<span data-ttu-id="259bd-161">コンテンツをレコードとしてマークするには、[[保持ラベルを使用してレコードを宣言する](declare-records.md)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="259bd-161">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>

<span data-ttu-id="259bd-162">レコードの廃棄の詳細については、「[コンテンツの廃棄](disposition.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="259bd-162">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
