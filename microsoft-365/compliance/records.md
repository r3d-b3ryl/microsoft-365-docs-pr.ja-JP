---
title: レコードの概要
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
description: Office 365 または Microsoft 組織でレコード管理戦略を実装するには、コンテンツをレコードとして宣言する保持ラベルを使用します。 次に、保持レコードラベルを公開または自動適用します。
ms.openlocfilehash: ba69c9705c14c2f836f67c8747d30ee2280c6d99
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106145"
---
# <a name="overview-of-records"></a><span data-ttu-id="22cd6-104">レコードの概要</span><span class="sxs-lookup"><span data-stu-id="22cd6-104">Overview of records</span></span>

><span data-ttu-id="22cd6-105">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="22cd6-105">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="22cd6-106">Microsoft 365 でレコードを管理することで、組織は企業のポリシー、法的および規制上の義務を順守し、リスクおよび法的責任を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-106">Managing records in Microsoft 365 helps an organization comply with their corporate policies, legal and regulatory obligations while reducing risk and legal liability.</span></span>

<span data-ttu-id="22cd6-107">大まかに言うと、コンテンツをレコードとして宣言することは以下のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-107">At a high level, declaring content as a record means that:</span></span>

- <span data-ttu-id="22cd6-108">アイテムは不変になります (レコードは変更または削除できません)</span><span class="sxs-lookup"><span data-stu-id="22cd6-108">The item becomes immutable (a record can't be modified or deleted)</span></span>

- <span data-ttu-id="22cd6-109">アイテムに関する追加のアクティビティが記録されます</span><span class="sxs-lookup"><span data-stu-id="22cd6-109">Additional activities about the item are logged</span></span>

- <span data-ttu-id="22cd6-110">レコードは、指定された保存期間が過ぎた後に廃棄されます</span><span class="sxs-lookup"><span data-stu-id="22cd6-110">Records are disposed of after their stated retention period is past</span></span>

<span data-ttu-id="22cd6-111">[保持ラベル](labels.md)を使用して、コンテンツをレコードとして分類できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-111">You can use [retention labels](labels.md) to classify content as a record.</span></span> <span data-ttu-id="22cd6-112">レコードを宣言する保持ラベルを作成した後、それらのラベルを[公開](labels.md#how-retention-labels-work-with-retention-label-policies) (それによりユーザーがそれらを使用してコンテンツをレコードとして分類できるようになる)、またはレコードとして分類するコンテンツに[それらのラベルを自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-112">After you create retention labels that declare records, you can either [publish](labels.md#how-retention-labels-work-with-retention-label-policies) those labels (so that users can use them to classify content as records) or [auto-apply those labels](labels.md#applying-a-retention-label-automatically-based-on-conditions) to content that you want to classify as a record.</span></span> <span data-ttu-id="22cd6-113">保持ラベルを使用してレコードを宣言することにより、Office 365 全体で単一の一貫したレコード管理戦略を実装できますが、レコード センターなどの他のレコード管理機能は SharePoint Online のコンテンツにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-113">By using retention labels to declare records, you can implement a single, consistent records-management strategy across all of Office 365, whereas other records-management features such as the Record Center apply only to content in SharePoint Online.</span></span>

<span data-ttu-id="22cd6-114">レコードについては、以下の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="22cd6-114">Keep the following things in mind about records:</span></span>

  - <span data-ttu-id="22cd6-115">**レコードは不変です。**</span><span class="sxs-lookup"><span data-stu-id="22cd6-115">**Records are immutable.**</span></span> <span data-ttu-id="22cd6-116">コンテンツをレコードとして宣言する保持ラベルは、SharePoint および OneDrive for Business に加えて、Exchange のコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-116">A retention label that declares content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="22cd6-117">ただし、[レコードのバージョン管理](#record-versioning)は SharePoint および OneDrive でのみ使用でき、Exchange では使用できません。</span><span class="sxs-lookup"><span data-stu-id="22cd6-117">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="22cd6-118">Exchange では、レコードとしてラベル付けされたコンテンツは、最終的に削除されるまで不変です。</span><span class="sxs-lookup"><span data-stu-id="22cd6-118">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="22cd6-119">Exchange アイテムがレコードとしてラベル付けされると、以下の 4 つのことが起こります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-119">When an Exchange item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="22cd6-120">アイテムの完全な削除。</span><span class="sxs-lookup"><span data-stu-id="22cd6-120">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="22cd6-121">アイテムの編集。</span><span class="sxs-lookup"><span data-stu-id="22cd6-121">The item can't be edited.</span></span>

    - <span data-ttu-id="22cd6-122">ラベルの変更。</span><span class="sxs-lookup"><span data-stu-id="22cd6-122">The label can't be changed.</span></span>

    - <span data-ttu-id="22cd6-123">ラベルの削除。</span><span class="sxs-lookup"><span data-stu-id="22cd6-123">The label can't be removed.</span></span>

  - <span data-ttu-id="22cd6-124">**レコードとフォルダー。**</span><span class="sxs-lookup"><span data-stu-id="22cd6-124">**Records and folders.**</span></span> <span data-ttu-id="22cd6-125">Exchange、SharePoint、および OneDrive のフォルダーに保持ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-125">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="22cd6-126">フォルダーがレコードとしてラベル付けされている場合、アイテムをフォルダーに移動すると、アイテムはレコードとしてラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-126">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="22cd6-127">アイテムをフォルダから移動すると、アイテムはレコードとしてラベル付けされたままになります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-127">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="22cd6-128">また、フォルダー (SharePoint および OneDrive) に適用されるレコード ラベルを、コンテンツをレコードとして宣言しない保持ラベルに変更すると、フォルダー内のアイテムは既存のレコード ラベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-128">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, then items in the folder keep their existing  record label.</span></span>

    <span data-ttu-id="22cd6-129">SharePoint および OneDrive フォルダーへの保持ラベルの適用の詳細については、「[SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22cd6-129">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="22cd6-130">**レコードは削除できません**。</span><span class="sxs-lookup"><span data-stu-id="22cd6-130">**Records can't be deleted**.</span></span> <span data-ttu-id="22cd6-131">「[アイテム保持ポリシーは保持されたコンテンツに対してどのように作用するのか](retention-policies.md#content-in-mailboxes-and-public-folders)」で説明されているように、ユーザーが Exchange でレコードを削除しようとすると、アイテムは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-131">If a user attempts to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How a retention policy works with content in place](retention-policies.md#content-in-mailboxes-and-public-folders).</span></span>

    <span data-ttu-id="22cd6-132">ユーザーが SharePoint のレコードを削除しようとすると、「アイテムが削除されませんでした」というエラーが表示され、ライブラリに残ります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-132">If a user attempts to delete a record in a SharePoint, an error is displayed say that the item wasn't deleted, and remains in the library.</span></span>

    ![SharePoint の「アイテムが削除されませんでした」というメッセージ](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="22cd6-134">「[アイテム保持ポリシーは所定の場所にあるコンテンツに対してどのように作用するか](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites)」で説明されているように、ユーザーが OneDrive でレコードを削除しようとすると、アイテムはアイテム保管ライブラリに移動されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-134">If a user attempts to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How a retention policy works with content in place](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites).</span></span>

  - <span data-ttu-id="22cd6-135">**レコード ラベルは削除できません。**</span><span class="sxs-lookup"><span data-stu-id="22cd6-135">**Records labels can't be removed.**</span></span> <span data-ttu-id="22cd6-136">レコードラベルがアイテムに適用されると、その場所の管理者 (SharePoint サイトのサイト コレクション管理者など) のみがそのレコード ラベルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-136">Once a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="22cd6-137">保持ラベルを使用してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="22cd6-137">Using retention labels to declare records</span></span>

<span data-ttu-id="22cd6-138">保持ラベルを作成する際に、保持ラベルを使用してコンテンツをレコードとして分類するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-138">When you create a retention label, you have the option to use the retention label to classify the content as a record.</span></span> <span data-ttu-id="22cd6-139">コンテンツをレコードとして宣言するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-139">To declare content as a record, follow these steps:</span></span>

1. <span data-ttu-id="22cd6-140">保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-140">Create a retention label.</span></span> <span data-ttu-id="22cd6-141">Microsoft 365 コンプライアンス センターで、[**レコードの管理**] [\>ファイル プラン\*\*] に移動します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-141">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="22cd6-142">[**ファイル プラン**] ページで、[**ラベルの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22cd6-142">On the **File plan** page, click  **Create a label**.</span></span>

2. <span data-ttu-id="22cd6-143">ウィザードの [**ラベルの設定**] ページで、保持ラベルを設定してコンテンツをレコードとして宣言するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-143">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span><br/>

   ![[このラベルを使用して、コンテンツをレコードに分類する] チェックボックスをクリックします](../media/recordversioning6.png)

3. <span data-ttu-id="22cd6-145">保持ラベルを SharePoint サイトおよび/または OneDrive アカウントに[公開](labels.md#how-retention-labels-work-with-retention-label-policies)または[自動適用](labels.md#applying-a-retention-label-automatically-based-on-conditions)します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-145">[Publish](labels.md#how-retention-labels-work-with-retention-label-policies) or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) the retention label to SharePoint sites and/or OneDrive accounts.</span></span>

### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="22cd6-146">コンテンツに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="22cd6-146">Applying a retention label to content</span></span>

<span data-ttu-id="22cd6-147">Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、メール メッセージにレコード ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-147">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="22cd6-148">SharePoint および OneDrive のコンテンツの場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがレコード ラベルをコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-148">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="22cd6-149">そのレコード ラベルが適用された後に削除または変更できるのは、サイト コレクション管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="22cd6-149">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="22cd6-150">前述のように、コンテンツをレコードとして分類する保持ラベルは、コンテンツに自動適用できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-150">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="22cd6-151">これは、SharePoint サイトまたは OneDrive アカウント上のドキュメントにレコード ラベルが適用されたときの外観です。</span><span class="sxs-lookup"><span data-stu-id="22cd6-151">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="22cd6-153">レコードのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="22cd6-153">Record versioning</span></span>

<span data-ttu-id="22cd6-154">レコード管理における重要な部分は、ドキュメントをレコードとして宣言し、そのレコードを不変にする機能です。</span><span class="sxs-lookup"><span data-stu-id="22cd6-154">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="22cd6-155">同時にレコードの不変性により、ユーザーが後続のバージョンを作成する必要がある場合、ドキュメントでの共同作業が妨げられます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-155">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="22cd6-156">たとえば販売契約をレコードとして宣言する場合、新しい条件で契約を更新し、そして前のレコード バージョンを保持したまま最新バージョンを新しいレコードとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-156">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="22cd6-157">これらのタイプのシナリオでは、SharePoint Online および OneDrive for Business が*レコードのバージョン管理*をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="22cd6-157">For these types of scenarios, SharePoint Online and OneDrive for Business now support *record versioning*.</span></span> <span data-ttu-id="22cd6-158">OneNote ノートブック フォルダーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="22cd6-158">OneNote notebook folders are not supported.</span></span>

<span data-ttu-id="22cd6-159">レコードのバージョン管理を使用するための最初の手順は、Microsoft 365 コンプライアンス センターを使用して、すべての SharePoint サイトおよび/または OneDrive アカウントにレコードを宣言する保持ラベルを作成し公開するか、特定の SharePoint サイトおよび/または OneDrive アカウントにそれらを公開することです。</span><span class="sxs-lookup"><span data-stu-id="22cd6-159">To use record versioning, the first step is to use the Microsoft 365 compliance center to create and publish retention labels that declare records to all SharePoint sites and/or OneDrive accounts, or publish them to specific SharePoint sites and/or OneDrive accounts.</span></span> <span data-ttu-id="22cd6-160">次の手順では、公開された保持レコード ラベルをドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-160">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="22cd6-161">これが完了すると、*レコード ステータス*と呼ばれるドキュメント プロパティが保持ラベルの横に表示され、初期レコード ステータスは**ロック済み**になります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-161">When this is done, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="22cd6-162">この時点で、以下のことができます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-162">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="22cd6-163">**レコード ステータス プロパティをロック解除およびロックすることにより、ドキュメントの個々のバージョンをレコードとして継続的に編集および宣言します。**</span><span class="sxs-lookup"><span data-stu-id="22cd6-163">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="22cd6-164">**レコード ステータス**プロパティが**ロック済み**に設定されている場合、レコードとして宣言されたバージョンのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-164">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="22cd6-165">これにより、ドキュメントの不要なバージョンおよびコピーを保持するリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-165">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="22cd6-166">**サイト コレクション内にあるインプレース レコード リポジトリにレコードを自動的に保存します。**</span><span class="sxs-lookup"><span data-stu-id="22cd6-166">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="22cd6-167">SharePoint および OneDrive の各サイト コレクションは、アイテム保管ライブラリのコンテンツを保持します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-167">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="22cd6-168">レコード バージョンは、このライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-168">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="22cd6-169">**すべてのバージョンを含むエバーグリーン ドキュメントを維持します。**</span><span class="sxs-lookup"><span data-stu-id="22cd6-169">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="22cd6-170">既定では、各 SharePoint および OneDrive ドキュメントには、アイテム メニューで利用可能なバージョン履歴があります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-170">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="22cd6-171">このバージョン履歴ではどのバージョンがレコードであるかを簡単に確認し、それらのドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-171">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="22cd6-172">レコードのバージョン管理は、アイテムをレコードとして宣言する保持ラベルを持つすべてのドキュメントで自動的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-172">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="22cd6-173">ユーザーが詳細ウィンドウでドキュメントのプロパティを表示すると、**レコード ステータス**が**ロック済み**から**ロック解除**に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-173">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="22cd6-174">この一回のクリックによりアイテム保管ライブラリの [レコード] フォルダーにレコードが作成され、保存期間の残りの期間はそこに保存されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-174">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> <span data-ttu-id="22cd6-175">ドキュメントのロックが解除されている間、アクセス許可を持つすべてのユーザーがファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-175">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="22cd6-176">ただし、宣言されたレコードと見なされるため、ユーザーはファイルを削除できません。</span><span class="sxs-lookup"><span data-stu-id="22cd6-176">However, users can't delete the file, because it's considered a declared record.</span></span> <span data-ttu-id="22cd6-177">必要な変更が行われた後、ユーザーは**レコード ステータス**を**ロック解除**から**ロック済み**へと切り替えることができるため、ドキュメントは再びレコードとして宣言され、編集できなくなります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-177">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

![レコードとしてタグ付けされたドキュメントのレコード ステータス プロパティ](../media/recordversioning8.png)

> [!NOTE]
> <span data-ttu-id="22cd6-179">レコードのバージョン管理には、SharePoint サイトまたは OneDrive アカウントでレコードとして宣言されているコンテンツを編集する権限を持つユーザーごとに Office 365 Enterprise E5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="22cd6-179">Record versioning requires an Office 365 Enterprise E5 license for each user who has permissions to edit content that's been declared a record in a SharePoint site or OneDrive account.</span></span> <span data-ttu-id="22cd6-180">読み取り専用アクセス権を持つユーザーは、このライセンスを必要としません。</span><span class="sxs-lookup"><span data-stu-id="22cd6-180">Users who have read-only access don't require this license.</span></span>

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="22cd6-181">レコードのロックおよびロック解除</span><span class="sxs-lookup"><span data-stu-id="22cd6-181">Locking and unlocking a record</span></span>

<span data-ttu-id="22cd6-182">レコード ラベルがドキュメントに割り当てられた後、投稿権限またはより狭い権限レベルを持つユーザーは、レコードをロック解除したり、ロック解除されたレコードをロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-182">After a record label is assigned to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![レコード ステータスは、レコード ドキュメントがロック解除されていることを示しています](../media/recordversioning9.png)

<span data-ttu-id="22cd6-184">ユーザーがレコードのロックを解除すると、以下のアクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-184">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="22cd6-185">現在のサイト コレクションにアイテム保管ライブラリがない場合は、それが作成されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-185">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="22cd6-186">アイテム保管ライブラリに [レコード] フォルダーがない場合は、[レコード] フォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-186">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="22cd6-187">[**コピー先**] アクションは、ドキュメントの最新バージョンを [レコード] フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="22cd6-187">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="22cd6-188">[**コピー先**] アクションには最新バージョンのみが含まれ、以前のバージョンは含まれません。</span><span class="sxs-lookup"><span data-stu-id="22cd6-188">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="22cd6-189">このコピーされたドキュメントはドキュメントのレコード バージョンと見なされ、ファイル名の形式は以下のようになります: \[タイトル GUID バージョン\#\]</span><span class="sxs-lookup"><span data-stu-id="22cd6-189">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="22cd6-190">[レコード] フォルダーに作成されたコピーは元のドキュメントのバージョン履歴に追加され、このバージョンでは、[コメント] フィールドに**レコード**という単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-190">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="22cd6-191">元のドキュメントは、編集可能な (ただし削除はされない) 新しいバージョンです。</span><span class="sxs-lookup"><span data-stu-id="22cd6-191">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="22cd6-192">ドキュメントが編集可能になった場合でもドキュメントはまだレコードとして見なされるため、ドキュメント ライブラリの [**アイテムはレコードです**] 列には [**はい**] の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-192">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="22cd6-193">ユーザーがレコードをロックすると、元のドキュメントは再び編集ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-193">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="22cd6-194">ただしこれは、バージョンをアイテム保管ライブラリの [レコード] フォルダーにコピーするレコードのロックを解除するアクションです。</span><span class="sxs-lookup"><span data-stu-id="22cd6-194">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="22cd6-195">レコードのバージョン</span><span class="sxs-lookup"><span data-stu-id="22cd6-195">Record versions</span></span>

<span data-ttu-id="22cd6-196">ユーザーがレコードのロックを解除するたびに、最新バージョンがアイテム保管ライブラリの [レコード] フォルダーにコピーされ、そのバージョンには**レコード**の値がバージョン履歴の [**コメント**] フィールドに含まれます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-196">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![アイテム保管ライブラリに表示されるレコード](../media/recordversioning10.png)

<span data-ttu-id="22cd6-198">バージョン履歴を表示するには、ドキュメント ライブラリでドキュメントを選択し、[アイテム] メニューの [**バージョン履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22cd6-198">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="22cd6-199">レコードが保存される場所</span><span class="sxs-lookup"><span data-stu-id="22cd6-199">Where records are stored</span></span>

<span data-ttu-id="22cd6-200">レコードは、サイト コレクションのトップレベル サイトにあるアイテム保管ライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-200">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="22cd6-201">トップレベル サイトの左側のナビゲーションで、[**サイト コンテンツ**] \> [**アイテム保管ライブラリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22cd6-201">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![アイテム保管ライブラリ](../media/recordversioning11.png)

<br/><br/>

![アイテム保管ライブラリの [レコード] フォルダー](../media/recordversioning12.png)

<span data-ttu-id="22cd6-204">アイテム保管ライブラリは、サイト コレクション管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-204">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="22cd6-205">また、アイテム保管ライブラリは規定では存在しません。</span><span class="sxs-lookup"><span data-stu-id="22cd6-205">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="22cd6-206">保持ラベルまたは保持ポリシーの対象となるコンテンツがサイト コレクション内で初めて削除された場合にのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-206">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="22cd6-207">レコードのバージョン管理イベントの監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="22cd6-207">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="22cd6-208">レコードのロックおよびロック解除のアクションは、Office 365 監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="22cd6-208">The actions of locking and unlocking records are logged in the Office 365 audit log.</span></span> <span data-ttu-id="22cd6-209">**レコード ステータスがロックに変更されました**および**レコード ステータスがロック解除に変更されました**の特定のアクティビティを検索できます。これらのアクティビティはセキュリティ/コンプライアンス センター内にあり、[**ファイルとページのアクティビティ**] セクションは [**アクティビティ**] ドロップダウン リストに、そしてこのドロップダウン リストは [**監査ログの検索**] ページ にあります。</span><span class="sxs-lookup"><span data-stu-id="22cd6-209">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![レコードのバージョン管理イベントの監査ログを検索する](../media/recordversioning13.png)

<span data-ttu-id="22cd6-211">これらのイベントの検索に関する詳細情報については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)」の "ファイルとページのアクティビティ" セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22cd6-211">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>
