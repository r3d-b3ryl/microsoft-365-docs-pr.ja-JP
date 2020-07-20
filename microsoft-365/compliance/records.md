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
ms.openlocfilehash: aa5952b26549f9ba9b1c584eb55e203fd53c50e5
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127504"
---
# <a name="learn-about-records"></a><span data-ttu-id="a4fb3-103">レコードについての詳細</span><span class="sxs-lookup"><span data-stu-id="a4fb3-103">Learn about records</span></span>

><span data-ttu-id="a4fb3-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="a4fb3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a4fb3-105">Microsoft 365 でレコードを管理することで、組織は企業のポリシー、法的および規制上の義務を順守し、リスクや法的責任を軽減することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="a4fb3-106">コンテンツがレコードとしてマークされているときには:</span><span class="sxs-lookup"><span data-stu-id="a4fb3-106">When content is marked as an record:</span></span>

- <span data-ttu-id="a4fb3-107">アイテムは不変になり、変更や削除をすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-107">The item becomes immutable, which means that it can't be modified or deleted.</span></span>

- <span data-ttu-id="a4fb3-108">アイテムに関する追加のアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="a4fb3-109">保持期間の終了時に削除された時点で、廃棄の証明を取得します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-109">You have proof of disposition when they are deleted at the end of their retention period.</span></span>

<span data-ttu-id="a4fb3-110">[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="a4fb3-111">レコードを宣言する保持ラベルを作成すると、それらのラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-111">After you create retention labels that declare records, you can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="a4fb3-112">保持ラベルを使用してレコードを宣言することで、Microsoft 365 環境全体で単一の、一貫したレコード管理戦略を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-112">By using retention labels to declare records, you can implement a single, consistent records-management strategy across your Microsoft 365 environment.</span></span>

<span data-ttu-id="a4fb3-113">レコードについては、以下の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-113">Keep the following things in mind about records:</span></span>

  - <span data-ttu-id="a4fb3-114">**レコードは不変です。**</span><span class="sxs-lookup"><span data-stu-id="a4fb3-114">**Records are immutable.**</span></span> <span data-ttu-id="a4fb3-115">コンテンツをレコードとしてマークする保持ラベルは、SharePoint や OneDrive に加えて、Exchange のコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-115">A retention label that marks content as a record can be applied to content in Exchange, in addition to SharePoint and OneDrive.</span></span> <span data-ttu-id="a4fb3-116">ただし、[レコードのバージョン管理](#record-versioning)は SharePoint および OneDrive でのみ使用でき、Exchange では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-116">However, [record versioning](#record-versioning) is available only in SharePoint and OneDrive, and not for Exchange.</span></span>

    <span data-ttu-id="a4fb3-117">Exchange では、レコードとしてラベル付けされたコンテンツは、最終的に削除されるまで不変です。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-117">In Exchange, content labeled as a record is immutable until its final deletion.</span></span> <span data-ttu-id="a4fb3-118">Exchange アイテムがレコードとしてラベル付けされると、以下の 4 つのことが起こります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-118">When an Exchange item is labeled as a record, four things happen:</span></span>

    - <span data-ttu-id="a4fb3-119">アイテムの完全な削除。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-119">The item can't be permanently deleted.</span></span>

    - <span data-ttu-id="a4fb3-120">アイテムの編集。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-120">The item can't be edited.</span></span>

    - <span data-ttu-id="a4fb3-121">ラベルの変更。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-121">The label can't be changed.</span></span>

    - <span data-ttu-id="a4fb3-122">ラベルの削除。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-122">The label can't be removed.</span></span>

  - <span data-ttu-id="a4fb3-123">**レコードとフォルダー。**</span><span class="sxs-lookup"><span data-stu-id="a4fb3-123">**Records and folders.**</span></span> <span data-ttu-id="a4fb3-124">Exchange、SharePoint、および OneDrive のフォルダーに保持ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-124">You can apply a retention label to a folder in Exchange, SharePoint, and OneDrive.</span></span> <span data-ttu-id="a4fb3-125">フォルダーがレコードとしてラベル付けされている場合、アイテムをフォルダーに移動すると、アイテムはレコードとしてラベル付けされます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-125">If a folder is labeled as a record, and you move an item into the folder, the item is labeled as a record.</span></span> <span data-ttu-id="a4fb3-126">アイテムをフォルダから移動すると、アイテムはレコードとしてラベル付けされたままになります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-126">When you move the item out of the folder, the item remains labeled as a record.</span></span>

    <span data-ttu-id="a4fb3-127">また、(SharePoint と OneDrive 内の) フォルダーに適用されるレコード ラベルを、コンテンツをレコードとして宣言しない保持ラベルに変更すると、フォルダー内のアイテムは既存のレコード ラベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-127">Also, if you change the record label that's applied to a folder (in SharePoint and OneDrive) to a retention label that does not declare content as a record, items in the folder keep their existing record label.</span></span>

    <span data-ttu-id="a4fb3-128">SharePoint および OneDrive フォルダーへの保持ラベルの適用の詳細については、「[SharePoint ライブラリ、フォルダー、またはドキュメント セット内のすべてのコンテンツへの既定の保持ラベルの適用](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-128">For more information about applying retention labels to SharePoint and OneDrive folders, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>

  - <span data-ttu-id="a4fb3-129">**レコードは削除できません**。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-129">**Records can't be deleted**.</span></span> <span data-ttu-id="a4fb3-130">「[Exchange の保持のしくみ](retention-policies-exchange.md#how-retention-works-for-exchange)」で説明されているように、ユーザーが Exchange でレコードを削除しようとすると、アイテムは [回復可能なアイテム] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-130">If a user attempts to delete a record in Exchange, the item is moved to the Recoverable Items folder as described in [How retention works for Exchange](retention-policies-exchange.md#how-retention-works-for-exchange).</span></span>

    <span data-ttu-id="a4fb3-131">ユーザーが SharePoint のレコードを削除しようとすると、「アイテムが削除されませんでした」というエラーが表示され、ライブラリに残ります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-131">If a user attempts to delete a record in a SharePoint, an error is displayed say that the item wasn't deleted, and remains in the library.</span></span>

    ![SharePoint の「アイテムが削除されませんでした」というメッセージ](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    <span data-ttu-id="a4fb3-133">「[SharePoint と OneDrive の保持のしくみ](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive)」で説明されているように、ユーザーが OneDrive でレコードを削除しようとすると、アイテムはアイテム保管ライブラリに移動されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-133">If a user attempts to delete a record in OneDrive, the item is moved to the Preservation Hold library as described in [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

  - <span data-ttu-id="a4fb3-134">**レコード ラベルは削除できません。**</span><span class="sxs-lookup"><span data-stu-id="a4fb3-134">**Records labels can't be removed.**</span></span> <span data-ttu-id="a4fb3-135">レコードラベルがアイテムに適用された後、その場所の管理者 (SharePoint サイトのサイト コレクション管理者など) のみがそのレコード ラベルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-135">After a record label has been applied to an item, only the admin of that location (for example, a site collection admin of a SharePoint site) can remove that record label.</span></span>

## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="a4fb3-136">保持ラベルを使用してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="a4fb3-136">Using retention labels to declare records</span></span>

<span data-ttu-id="a4fb3-137">保持ラベルを作成するときに、保持ラベルを使用してコンテンツをレコードとしてマークするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-137">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="a4fb3-138">Microsoft 365 コンプライアンス センターで、[**レコードの管理**] [\>ファイル プラン\*\*] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-138">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="a4fb3-139">[**ファイルプラン**] ページで、[**ラベルの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-139">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="a4fb3-140">ウィザードの [**ラベルの設定**] ページで、保持ラベルを設定してコンテンツをレコードとして宣言するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-140">On the **Label settings** page in the wizard, choose the option to set the retention label to declare content as a record.</span></span>
    
   ![[このラベルを使用して、コンテンツをレコードに分類する] チェックボックスをクリックします](../media/recordversioning6.png)

3. <span data-ttu-id="a4fb3-142">保持ラベルを SharePoint サイトと OneDrive アカウントに適用します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-142">Apply the retention label to SharePoint sites and OneDrive accounts:</span></span>
    
    - [<span data-ttu-id="a4fb3-143">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="a4fb3-143">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="a4fb3-144">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="a4fb3-144">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


### <a name="applying-a-retention-label-to-content"></a><span data-ttu-id="a4fb3-145">コンテンツに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="a4fb3-145">Applying a retention label to content</span></span>

<span data-ttu-id="a4fb3-146">Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、メール メッセージにレコード ラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-146">For Exchange, any user with write-access to the mailbox can apply a record label to an email message.</span></span> <span data-ttu-id="a4fb3-147">SharePoint および OneDrive のコンテンツの場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがレコード ラベルをコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-147">For content in SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply a record label to content.</span></span> <span data-ttu-id="a4fb3-148">そのレコード ラベルが適用された後に削除または変更できるのは、サイト コレクション管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-148">Only a site collection admin can remove or change that record label after it's been applied.</span></span> <span data-ttu-id="a4fb3-149">前述のように、コンテンツをレコードとして分類する保持ラベルは、コンテンツに自動適用できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-149">As previously explained, a retention label that classifies content as a record can be auto-applied to content.</span></span>

<span data-ttu-id="a4fb3-150">これは、SharePoint サイトまたは OneDrive アカウント上のドキュメントにレコード ラベルが適用されたときの外観です。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-150">Here's what this looks like when a record label is applied to a document on a SharePoint site or OneDrive account.</span></span>
<br/><br/>

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="a4fb3-152">レコードのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="a4fb3-152">Record versioning</span></span>

<span data-ttu-id="a4fb3-153">レコード管理における重要な部分は、ドキュメントをレコードとして宣言し、そのレコードを不変にする機能です。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-153">An essential part of records management is the ability to declare a document as a record and have that record be immutable.</span></span> <span data-ttu-id="a4fb3-154">同時にレコードの不変性により、ユーザーが後続のバージョンを作成する必要がある場合、ドキュメントでの共同作業が妨げられます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-154">At the same time, record immutability prevents collaboration on the document if people need to create subsequent versions.</span></span> <span data-ttu-id="a4fb3-155">たとえば販売契約をレコードとして宣言する場合、新しい条件で契約を更新し、そして前のレコード バージョンを保持したまま最新バージョンを新しいレコードとして宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-155">For example, you might declare a sales contract as a record, but then need to update the contract with new terms and declare the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="a4fb3-156">これらのタイプのシナリオでは、SharePoint と OneDrive が*レコードのバージョン管理*をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-156">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="a4fb3-157">OneNote ノートブックのフォルダーは、レコードのバージョン管理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-157">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="a4fb3-158">レコードのバージョン管理を使用するための最初の手順は、Microsoft 365 コンプライアンス センターを使用して、すべての SharePoint サイトや OneDrive アカウントにレコードを宣言してそれらを公開する保持ラベルを作成するか、特定の SharePoint サイトまたは OneDrive アカウントにそれらを公開することです。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-158">To use record versioning, the first step is to use the Microsoft 365 compliance center to create retention labels that declare records and and publish them to all SharePoint sites and OneDrive accounts, or publish them to specific SharePoint sites or OneDrive accounts.</span></span> <span data-ttu-id="a4fb3-159">次の手順では、公開された保持レコード ラベルをドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-159">The next step is to apply a published retention record label to a document.</span></span> <span data-ttu-id="a4fb3-160">これが発生すると、*レコード ステータス*と呼ばれるドキュメント プロパティが保持ラベルの横に表示され、初期レコード ステータスは**ロック済み**になります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-160">When this happens, a document property, called *Record status* is displayed next to the retention label, and the initial record status will be **Locked**.</span></span> <span data-ttu-id="a4fb3-161">この時点で、以下のことができます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-161">At this point, you can do the following things:</span></span>

  - <span data-ttu-id="a4fb3-162">**レコード ステータス プロパティをロック解除およびロックすることにより、ドキュメントの個々のバージョンをレコードとして継続的に編集および宣言します。**</span><span class="sxs-lookup"><span data-stu-id="a4fb3-162">**Continually edit and declare individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="a4fb3-163">**レコード ステータス**プロパティが**ロック済み**に設定されている場合、レコードとして宣言されたバージョンのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-163">Only the versions declared as records are retained when the **Record status** property is set to **Locked**.</span></span> <span data-ttu-id="a4fb3-164">これにより、ドキュメントの不要なバージョンおよびコピーを保持するリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-164">This reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="a4fb3-165">**サイト コレクション内にあるインプレース レコード リポジトリにレコードを自動的に保存します。**</span><span class="sxs-lookup"><span data-stu-id="a4fb3-165">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="a4fb3-166">SharePoint および OneDrive の各サイト コレクションは、アイテム保管ライブラリのコンテンツを保持します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-166">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="a4fb3-167">レコード バージョンは、このライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-167">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="a4fb3-168">**すべてのバージョンを含むエバーグリーン ドキュメントを維持します。**</span><span class="sxs-lookup"><span data-stu-id="a4fb3-168">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="a4fb3-169">既定では、各 SharePoint および OneDrive ドキュメントには、アイテム メニューで利用可能なバージョン履歴があります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-169">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="a4fb3-170">このバージョン履歴ではどのバージョンがレコードであるかを簡単に確認し、それらのドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-170">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="a4fb3-171">レコードのバージョン管理は、アイテムをレコードとして宣言する保持ラベルを持つすべてのドキュメントで自動的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-171">Record versioning is automatically available for any document that has a retention label that declares the item as a record.</span></span> <span data-ttu-id="a4fb3-172">ユーザーが詳細ウィンドウでドキュメントのプロパティを表示すると、**レコード ステータス**が**ロック済み**から**ロック解除**に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-172">When a user views the document properties through the details pane, they toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="a4fb3-173">この一回のクリックによりアイテム保管ライブラリの [レコード] フォルダーにレコードが作成され、保存期間の残りの期間はそこに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-173">This single click creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="a4fb3-174">ドキュメントのロックが解除されている間、アクセス許可を持つすべてのユーザーがファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-174">While the document is unlocked, any user with permissions can edit the file.</span></span> <span data-ttu-id="a4fb3-175">ただし、これはレコードと見なされるため、ユーザーはファイルを削除することができません。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-175">However, users can't delete the file, because it's considered a record.</span></span> <span data-ttu-id="a4fb3-176">必要な変更が行われた後、ユーザーは**レコード ステータス**を**ロック解除**から**ロック済み**へと切り替えることができるため、ドキュメントは再びレコードとして宣言され、編集できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-176">After the necessary changes are made, the user can then toggle the **Record status** from **Unlocked** to **Locked**, so that the document is again declared a record and can't be edited.</span></span>
<br/><br/>

![レコードとしてタグ付けされたドキュメントのレコード ステータス プロパティ](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="a4fb3-178">レコードのロックおよびロック解除</span><span class="sxs-lookup"><span data-stu-id="a4fb3-178">Locking and unlocking a record</span></span>

<span data-ttu-id="a4fb3-179">レコード ラベルがドキュメントに割り当てられた後、投稿権限またはより狭い権限レベルを持つユーザーは、レコードをロック解除したり、ロック解除されたレコードをロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-179">After a record label is assigned to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![レコード ステータスは、レコード ドキュメントがロック解除されていることを示しています](../media/recordversioning9.png)

<span data-ttu-id="a4fb3-181">ユーザーがレコードのロックを解除すると、以下のアクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-181">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="a4fb3-182">現在のサイト コレクションにアイテム保管ライブラリがない場合は、それが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-182">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="a4fb3-183">アイテム保管ライブラリに [レコード] フォルダーがない場合は、[レコード] フォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-183">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="a4fb3-184">[**コピー先**] アクションは、ドキュメントの最新バージョンを [レコード] フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-184">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="a4fb3-185">[**コピー先**] アクションには最新バージョンのみが含まれ、以前のバージョンは含まれません。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-185">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="a4fb3-186">このコピーされたドキュメントはドキュメントのレコード バージョンと見なされ、ファイル名の形式は以下のようになります: \[タイトル GUID バージョン\#\]</span><span class="sxs-lookup"><span data-stu-id="a4fb3-186">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="a4fb3-187">[レコード] フォルダーに作成されたコピーは元のドキュメントのバージョン履歴に追加され、このバージョンでは、[コメント] フィールドに**レコード**という単語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-187">The copy created in the Records folder added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="a4fb3-188">元のドキュメントは、編集可能な (ただし削除はされない) 新しいバージョンです。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-188">The original document is a new version that can be edited (but not deleted).</span></span> <span data-ttu-id="a4fb3-189">ドキュメントが編集可能になった場合でもドキュメントはまだレコードとして見なされるため、ドキュメント ライブラリの [**アイテムはレコードです**] 列には [**はい**] の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-189">The document library column **Item is a Record** still shows the **Yes** value because the document is still considered a record, even if it can now be edited.</span></span>

<span data-ttu-id="a4fb3-190">ユーザーがレコードをロックすると、元のドキュメントは再び編集ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-190">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="a4fb3-191">ただしこれは、バージョンをアイテム保管ライブラリの [レコード] フォルダーにコピーするレコードのロックを解除するアクションです。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-191">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="a4fb3-192">レコードのバージョン</span><span class="sxs-lookup"><span data-stu-id="a4fb3-192">Record versions</span></span>

<span data-ttu-id="a4fb3-193">ユーザーがレコードのロックを解除するたびに、最新バージョンがアイテム保管ライブラリの [レコード] フォルダーにコピーされ、そのバージョンには**レコード**の値がバージョン履歴の [**コメント**] フィールドに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-193">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![アイテム保管ライブラリに表示されるレコード](../media/recordversioning10.png)

<span data-ttu-id="a4fb3-195">バージョン履歴を表示するには、ドキュメント ライブラリでドキュメントを選択し、[アイテム] メニューの [**バージョン履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-195">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="a4fb3-196">レコードが保存される場所</span><span class="sxs-lookup"><span data-stu-id="a4fb3-196">Where records are stored</span></span>

<span data-ttu-id="a4fb3-197">レコードは、サイト コレクションのトップレベル サイトにあるアイテム保管ライブラリの [レコード] フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-197">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="a4fb3-198">トップレベル サイトの左側のナビゲーションで、[**サイト コンテンツ**] \> [**アイテム保管ライブラリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-198">In the left nav on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![アイテム保管ライブラリ](../media/recordversioning11.png)

<br/><br/>

![アイテム保管ライブラリの [レコード] フォルダー](../media/recordversioning12.png)

<span data-ttu-id="a4fb3-201">アイテム保管ライブラリは、サイト コレクション管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-201">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="a4fb3-202">また、アイテム保管ライブラリは規定では存在しません。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-202">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="a4fb3-203">保持ラベルまたは保持ポリシーの対象となるコンテンツがサイト コレクション内で初めて削除された場合にのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-203">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="a4fb3-204">レコードのバージョン管理イベントの監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="a4fb3-204">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="a4fb3-205">レコードのロックおよびロック解除のアクションは、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-205">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="a4fb3-206">**レコード ステータスがロックに変更されました**および**レコード ステータスがロック解除に変更されました**の特定のアクティビティを検索できます。これらのアクティビティはセキュリティ/コンプライアンス センター内にあり、[**ファイルとページのアクティビティ**] セクションは [**アクティビティ**] ドロップダウン リストに、そしてこのドロップダウン リストは [**監査ログの検索**] ページ にあります。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-206">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![レコードのバージョン管理イベントの監査ログを検索する](../media/recordversioning13.png)

<span data-ttu-id="a4fb3-208">これらのイベントの検索に関する詳細情報については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)」の "ファイルとページのアクティビティ" セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-208">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a4fb3-209">次の手順</span><span class="sxs-lookup"><span data-stu-id="a4fb3-209">Next steps</span></span>

<span data-ttu-id="a4fb3-210">レコード管理に使用する保持ラベルをまだ作成していない場合は、「[アイテム保持ポリシーと保持ラベルの使用を開始する](get-started-with-retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-210">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="a4fb3-211">レコード管理の構成と使用に関連するビデオをご希望の場合は、[YouTube のデータ ガバナンスに関するシリーズ](https://go.microsoft.com/fwlink/?linkid=867039)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a4fb3-211">To watch videos related to configuring and using records management, see the [Data governance selections on YouTube](https://go.microsoft.com/fwlink/?linkid=867039).</span></span>
