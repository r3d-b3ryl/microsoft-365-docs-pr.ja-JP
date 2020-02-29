---
title: SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルの機密ラベルサポートを有効にすることができます。
ms.openlocfilehash: 89925858ac749ac6f50b7a049a372cf2f7912698
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341242"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="9ba99-103">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9ba99-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="9ba99-104">このプレビューの前に、SharePoint および OneDrive に格納されている Office ファイルへの暗号化を含む機密ラベルを適用すると、サービスはこれらのファイルのコンテンツを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9ba99-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="9ba99-105">このような状況では、共同編集、電子情報開示、データ損失防止、検索、Delve、その他のコラボレーション機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="9ba99-106">このプレビューでは、クラウドベースのキーを使用した暗号化を含む、機密ラベルが適用された新規ファイルおよび変更されたファイルに対して次の機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-106">This preview enables these features for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="9ba99-107">Sharepoint は、sharepoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。ファイルが SharePoint に格納されている間は、ファイルの内容を処理できるように、Azure Information Protection からの暗号化が削除されます。その後、ファイルがダウンロードされると、ラベルの暗号化設定が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed, and then the encryption settings from the label are reapplied when the file is downloaded.</span></span> <span data-ttu-id="9ba99-108">ドキュメントがダウンロードされる前に保護される方法については、「 [OneDrive for business および SharePoint Online のデータ暗号化](data-encryption-in-odb-and-spo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-108">For information about how documents are protected before they are downloaded, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>
 
- <span data-ttu-id="9ba99-109">アップロード時に SharePoint がファイルを復号化するには、ラベル付きおよび暗号化されたファイルをアップロードするユーザーに、少なくともファイルを表示するための使用権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ba99-109">For SharePoint to decrypt the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="9ba99-110">Sharepoint では、ユーザーが SharePoint の外部で開くことができないファイルは復号化されません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-110">SharePoint doesn't decrypt files that the user can't open outside SharePoint.</span></span>

- <span data-ttu-id="9ba99-111">SharePoint または OneDrive からファイルをダウンロードするか、またはファイルにアクセスすると、ファイルの保存時に機密ラベルと暗号化の設定が再適用されます。これらの設定は、ファイルを保存するときに常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-111">When you download or access the file from SharePoint or OneDrive, the sensitivity label and any encryption settings are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span>

- <span data-ttu-id="9ba99-112">Web 上の Office (Word、Excel、PowerPoint) を使用して、暗号化を適用する機密ラベルが設定された Office ファイルを開いて編集します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-112">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="9ba99-113">暗号化によって割り当てられたアクセス許可が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-113">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="9ba99-114">Word on the web では、これらのドキュメントを編集するときに自動ラベル付けを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-114">With Word on the web, you can also use auto labeling when you edit these documents.</span></span>

- <span data-ttu-id="9ba99-115">Office 365 電子情報開示では、これらのファイルのフルテキスト検索がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9ba99-115">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="9ba99-116">データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。</span><span class="sxs-lookup"><span data-stu-id="9ba99-116">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="9ba99-117">Web 上の Office を使用して適用される機密ラベルを監視するには、次の3つの新しい[監査イベント](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-117">Three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied using Office on the web:</span></span>
  - <span data-ttu-id="9ba99-118">**ファイルに適用された機密ラベル**</span><span class="sxs-lookup"><span data-stu-id="9ba99-118">**Applied sensitivity label to file**</span></span>
  - <span data-ttu-id="9ba99-119">**ファイルに適用された機密ラベルの変更**</span><span class="sxs-lookup"><span data-stu-id="9ba99-119">**Changed sensitivity label applied to file**</span></span>
  - <span data-ttu-id="9ba99-120">**ファイルから削除された機密ラベル**</span><span class="sxs-lookup"><span data-stu-id="9ba99-120">**Removed sensitivity label from file**</span></span>

> [!NOTE]
> <span data-ttu-id="9ba99-121">クラウドベースのキーで暗号化が適用されておらず、オンプレミスキーであっても、"自分のキーを保持する" と呼ばれるキー管理トポロジ (HYOK) では、SharePoint の動作はこのプレビューでは変更されません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-121">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span>
>
> <span data-ttu-id="9ba99-122">プレビューを有効にする前に、sharepoint の既存のラベル付きファイルと暗号化されたファイルについても SharePoint の動作は変わりません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-122">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint before you enable the preview.</span></span> <span data-ttu-id="9ba99-123">これらのファイルが新機能を利用できるようにするには、プレビューを有効にした後、それらのファイルをダウンロードしてアップロードするか、編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-123">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you enable the preview.</span></span> <span data-ttu-id="9ba99-124">たとえば、それらは検索と電子情報開示の結果として返されます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-124">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="9ba99-125">また、Microsoft Teams、Office 365 グループ、および SharePoint サイトに機密ラベルを適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9ba99-125">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="9ba99-126">この個別のプレビューの詳細については、「 [Microsoft Teams、Office 365 グループ、および SharePoint サイト (パブリックプレビュー) を使用して機密ラベルを使用する](sensitivity-labels-teams-groups-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-126">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="9ba99-127">いつでもこのプレビューの選択を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-127">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="9ba99-128">次のビデオ (オーディオはない) を見て、これらの新機能をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-128">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="9ba99-129">要件</span><span class="sxs-lookup"><span data-stu-id="9ba99-129">Requirements</span></span>

<span data-ttu-id="9ba99-130">これらの機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-130">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="9ba99-131">現在 Azure Information Protection のラベルがある場合は、それらを機密ラベルに移行してから、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-131">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="9ba99-132">手順については、「 [Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-132">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="9ba99-133">このプレビューでは、Windows で OneDrive 同期アプリのバージョン19.002.0121.0008 以降、バージョン19.002.0107.0008 以降の Mac を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-133">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="9ba99-134">これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。</span><span class="sxs-lookup"><span data-stu-id="9ba99-134">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="9ba99-135">詳細については、 [OneDrive リリースノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-135">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="9ba99-136">このプレビューを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-136">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="9ba99-137">制限事項</span><span class="sxs-lookup"><span data-stu-id="9ba99-137">Limitations</span></span>

- <span data-ttu-id="9ba99-138">このプレビューを有効にすると、OneDrive Sync フォルダー内のファイルのラベルを変更したユーザーは、ファイルに加えた他の変更を保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-138">When you enable this preview, users who change a label on a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="9ba99-139">[白い十字アイコンのエラー](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示された赤い円が表示され、新しい変更内容を別のコピーとして保存するように求められます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-139">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="9ba99-140">ユーザーによって開始されたラベルの変更に加えて、管理者が、既にユーザーの同期クライアントにダウンロードしたファイルに適用されている発行済みラベルの設定を変更した場合にも、同じ現象が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-140">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="9ba99-141">これらのシナリオの作業を失わないようにするには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9ba99-141">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="9ba99-142">ラベルを適用するには、Office アプリの web 版を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-142">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="9ba99-143">ラベルを適用した後、ファイルを閉じてから、他の変更を行うためにファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-143">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="9ba99-144">SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに機密ラベルが自動的に適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-144">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="9ba99-145">代わりに、このプレビューを有効にした後で機能を使用できるようにするには、次のタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-145">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="9ba99-146">Azure Information Protection ラベルを機密ラベルに移行し、Microsoft 365 コンプライアンスセンター (または同等のラベル付き管理センター) から公開していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-146">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="9ba99-147">ファイルをダウンロードしてから、それらを SharePoint にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9ba99-147">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="9ba99-148">暗号化を適用したラベルが暗号化に使用する次のいずれかの構成を持っている場合、SharePoint は暗号化されたファイルを処理できません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-148">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="9ba99-149">ユーザーがラベルと Word、PowerPoint、Excel のチェックボックスを**適用するときにアクセス許可を割り当てること**ができるようにし **、[アクセス許可を指定するようユーザーに要求する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-149">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="9ba99-150">この設定は、"ユーザー定義の権限" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-150">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="9ba99-151">**コンテンツへのユーザーアクセスの有効期限**が、 **Never**以外の値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9ba99-151">**User access to content expires** is set to a value other than **Never**.</span></span>
    
    <span data-ttu-id="9ba99-152">これらの暗号化構成のいずれかを使用したラベルの場合、web 上の Office のユーザーにはラベルが表示されません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-152">For labels with either of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="9ba99-153">また、このプレビューの新機能は、既にこれらの暗号化設定を持つラベル付きドキュメントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-153">Additionally, the new capabilities from this preview can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="9ba99-154">たとえば、これらのドキュメントは、更新された場合でも、検索結果では返されません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-154">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="9ba99-155">ユーザーに編集権限を付与する暗号化されたドキュメントの場合、Office アプリの web 版ではコピーをブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-155">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="9ba99-156">Azure Information Protection ドキュメント追跡サイトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-156">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="9ba99-157">Office デスクトップアプリとモバイルアプリは共同編集をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-157">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="9ba99-158">代わりに、これらのアプリは引き続き、排他編集モードでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-158">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="9ba99-159">ラベルに暗号化が含まれている場合、Microsoft Cloud App Security は SharePoint のファイルのラベル情報を読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-159">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

- <span data-ttu-id="9ba99-160">ラベル付きのドキュメントが SharePoint にアップロードされ、そのラベルがサービスプリンシパル名のアカウントを使用して暗号化されている場合、そのドキュメントを web 上の Office で開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-160">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="9ba99-161">シナリオの例としては、Microsoft Cloud App Security と、電子メールで Teams に送信されるファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-161">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="9ba99-162">次の方法で暗号化されたドキュメントは、web 上の Office で開くことができません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-162">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="9ba99-163">オンプレミスキー ("自分のキーを保持する" または HYOK) を使用する暗号化</span><span class="sxs-lookup"><span data-stu-id="9ba99-163">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="9ba99-164">ラベルとは独立して適用された暗号化。たとえば、Rights Management protection テンプレートを直接適用します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-164">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="9ba99-165">SharePoint でドキュメントに適用されているラベルを削除する場合、該当するラベルポリシーからラベルを削除するのではなく、ダウンロードしたドキュメントがラベル付けまたは暗号化されないようにします。</span><span class="sxs-lookup"><span data-stu-id="9ba99-165">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="9ba99-166">比較すると、ラベル付きドキュメントが SharePoint の外部に保存されている場合、ラベルが削除されてもドキュメントは暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-166">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="9ba99-167">テストフェーズではラベルを削除することもできますが、運用環境でラベルを削除するのは非常にまれです。</span><span class="sxs-lookup"><span data-stu-id="9ba99-167">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="9ba99-168">プレビュー用の SharePoint Online 管理シェルの準備</span><span class="sxs-lookup"><span data-stu-id="9ba99-168">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="9ba99-169">プレビューを有効にする前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-169">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="9ba99-170">最新バージョンが既にある場合は、プレビューを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-170">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="9ba99-171">PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-171">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="9ba99-172">または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-172">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="9ba99-173">Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="9ba99-173">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="9ba99-174">言語を選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9ba99-174">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="9ba99-175">x64 および x86 の .msi ファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-175">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="9ba99-176">64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-176">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="9ba99-177">不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-177">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="9ba99-178">ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9ba99-178">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="9ba99-179">Microsoft PowerShell を使用してプレビューを有効にする (オプトイン)</span><span class="sxs-lookup"><span data-stu-id="9ba99-179">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="9ba99-180">プレビューを有効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-180">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="9ba99-181">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-181">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="9ba99-182">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-182">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="9ba99-183">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-183">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="9ba99-184">機密ラベルを作成または変更した後のロールアウトをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="9ba99-184">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="9ba99-185">Microsoft 365 コンプライアンスセンターで機密ラベルを作成または変更した後、それを段階的に公開します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-185">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="9ba99-186">完全に同期されていないラベルを発行した場合、ユーザーがファイルにラベルを適用してそれらを SharePoint にアップロードすると、ファイルを web 版の Office アプリで開くことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-186">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="9ba99-187">検索と電子情報開示もファイルに対して機能しません。</span><span class="sxs-lookup"><span data-stu-id="9ba99-187">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="9ba99-188">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ba99-188">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="9ba99-189">新しいまたは変更された機密ラベルを1人または2人のユーザーにのみ発行します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-189">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="9ba99-190">最初の発行の後、少なくとも24時間待機します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-190">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="9ba99-191">ラベルが完全に同期していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-191">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="9ba99-192">ラベルを広く公開します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-192">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="9ba99-193">Microsoft PowerShell を使用してプレビューを無効にする (オプトアウト)</span><span class="sxs-lookup"><span data-stu-id="9ba99-193">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="9ba99-194">このプレビューを無効にすると、プレビュー時にアップロードしたファイルはラベルで保護されたままになります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-194">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="9ba99-195">対応する設定は引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ba99-195">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="9ba99-196">プレビューを無効にした後、新しいファイルにラベルを適用すると、フルテキスト検索、電子情報開示、および共同編集は機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="9ba99-196">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="9ba99-197">プレビューを無効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-197">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="9ba99-198">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-198">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="9ba99-199">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ba99-199">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="9ba99-200">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ba99-200">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
