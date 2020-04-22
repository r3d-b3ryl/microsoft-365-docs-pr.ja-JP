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
ms.openlocfilehash: 3127b4ac7b661cd5143052d298424e24d26071a5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635785"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="7c2f7-103">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7c2f7-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

><span data-ttu-id="7c2f7-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="7c2f7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7c2f7-105">このプレビューの前に、Office の web 上に[機密ラベル](sensitivity-labels.md)を適用することができませんでした。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-105">Before this preview, you couldn't apply your [sensitivity labels](sensitivity-labels.md) in Office on the web.</span></span> <span data-ttu-id="7c2f7-106">リボンに [**秘密度**] オプションが表示されていないか、またはステータスバーに適用されたラベル名が表示されていません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-106">You didn't see the **Sensitivity** option on the ribbon, or the applied label name on the status bar.</span></span> <span data-ttu-id="7c2f7-107">さらに、デスクトップアプリを使用してファイルにラベルを付け、それらを SharePoint または Onedrive に保存した場合、ラベルが暗号化を適用した場合、サービスはこれらのファイルのコンテンツを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-107">In addition, if you used desktop apps to label your files and then save them on SharePoint or Onedrive, the service couldn't process the content of these files if the label applied encryption.</span></span> <span data-ttu-id="7c2f7-108">このような状況では、共同編集、電子情報開示、データ損失防止、検索、Delve、その他のコラボレーション機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-108">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> 

<span data-ttu-id="7c2f7-109">このプレビューでは、これらのすべての機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-109">This preview enables all these capabilities.</span></span> <span data-ttu-id="7c2f7-110">機密ラベルをユーザーに表示することに加えて、クラウドベースのキーを使用した暗号化を含む、新しいファイルと変更されたファイルについては、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-110">In addition to displaying sensitivity labels to users, for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="7c2f7-111">Sharepoint は、sharepoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。ファイルが SharePoint に格納されている間は、ファイルの内容を処理できるように、Azure Information Protection からの暗号化が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-111">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed.</span></span> <span data-ttu-id="7c2f7-112">SharePoint に保存されているドキュメントを保護する方法については、「 [OneDrive for business および Sharepoint Online のデータ暗号化](data-encryption-in-odb-and-spo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-112">For information about how documents are protected while they are stored in SharePoint, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>

- <span data-ttu-id="7c2f7-113">このファイルを SharePoint または OneDrive からダウンロードするか、またはそのファイルにアクセスすると、ラベルからの暗号化設定がファイルに再適用され、これらの設定はファイルが保存されているすべての場所に適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-113">When you download or access this file from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span> <span data-ttu-id="7c2f7-114">この動作により、ドキュメントを保護するためにラベルのみを使用するようにユーザーガイダンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-114">Because of this behavior, ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="7c2f7-115">詳細については、「 [Information Rights Management (IRM) のオプション」および「機密ラベル](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-115">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="7c2f7-116">アップロード時に SharePoint がファイルから暗号化を削除するには、ラベル付きおよび暗号化されたファイルをアップロードするユーザーは、少なくともファイルを表示するための使用権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-116">For SharePoint to remove the encryption from the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="7c2f7-117">ユーザーが SharePoint の外部でファイルを開くことができない場合、SharePoint はファイルから暗号化を削除しません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-117">SharePoint doesn't remove encryption from files if the user can't open them outside SharePoint.</span></span>

- <span data-ttu-id="7c2f7-118">Web 上の Office (Word、Excel、PowerPoint) を使用して、暗号化を適用する機密ラベルが設定された Office ファイルを開いて編集します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-118">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="7c2f7-119">暗号化によって割り当てられたアクセス許可が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-119">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="7c2f7-120">Word on the web では、これらの文書を編集するときに自動ラベルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-120">With Word on the web, you can also use auto-labeling when you edit these documents.</span></span>

- <span data-ttu-id="7c2f7-121">Office 365 電子情報開示では、これらのファイルのフルテキスト検索がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-121">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="7c2f7-122">データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-122">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

> [!NOTE]
> <span data-ttu-id="7c2f7-123">クラウドベースのキーで暗号化が適用されておらず、オンプレミスキーであっても、"自分のキーを保持する" と呼ばれるキー管理トポロジ (HYOK) では、ファイルコンテンツを処理するための SharePoint の動作はこのプレビューでは変更されません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-123">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior for processing the file contents doesn't change with this preview.</span></span>
>
> <span data-ttu-id="7c2f7-124">プレビューを有効にする前に、sharepoint の既存のラベル付きファイルと暗号化されたファイルについても SharePoint の動作は変わりません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-124">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint before you enable the preview.</span></span> <span data-ttu-id="7c2f7-125">これらのファイルが新機能を利用できるようにするには、プレビューを有効にした後、それらのファイルをダウンロードしてアップロードするか、編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-125">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you enable the preview.</span></span> <span data-ttu-id="7c2f7-126">たとえば、それらは検索と電子情報開示の結果として返されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-126">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="7c2f7-127">このプレビューを有効にすると、web 上の Office を使用して適用される機密ラベルを監視するための3つの新しい[監査イベント](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-127">When you enable this preview, three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied using Office on the web:</span></span>
- <span data-ttu-id="7c2f7-128">**ファイルに適用された機密ラベル**</span><span class="sxs-lookup"><span data-stu-id="7c2f7-128">**Applied sensitivity label to file**</span></span>
- <span data-ttu-id="7c2f7-129">**ファイルに適用された機密ラベルの変更**</span><span class="sxs-lookup"><span data-stu-id="7c2f7-129">**Changed sensitivity label applied to file**</span></span>
- <span data-ttu-id="7c2f7-130">**ファイルから削除された機密ラベル**</span><span class="sxs-lookup"><span data-stu-id="7c2f7-130">**Removed sensitivity label from file**</span></span>

<span data-ttu-id="7c2f7-131">次のビデオ (オーディオはない) を見て、これらの新機能をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-131">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

<span data-ttu-id="7c2f7-132">いつでもこのプレビューの選択を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-132">You always have the choice to opt out of this preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="7c2f7-133">Requirements</span><span class="sxs-lookup"><span data-stu-id="7c2f7-133">Requirements</span></span>

<span data-ttu-id="7c2f7-134">これらの機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-134">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="7c2f7-135">現在 Azure Information Protection のラベルがある場合は、それらを機密ラベルに移行してから、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-135">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="7c2f7-136">手順については、「 [Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-136">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="7c2f7-137">このプレビューでは、Windows で OneDrive 同期アプリのバージョン19.002.0121.0008 以降、バージョン19.002.0107.0008 以降の Mac を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-137">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="7c2f7-138">これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-138">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="7c2f7-139">詳細については、 [OneDrive リリースノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-139">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="7c2f7-140">このプレビューを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-140">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="7c2f7-141">制限事項</span><span class="sxs-lookup"><span data-stu-id="7c2f7-141">Limitations</span></span>

- <span data-ttu-id="7c2f7-142">このプレビューを有効にすると、OneDrive Sync フォルダー内のファイルのラベルを変更したユーザーは、ファイルに加えた他の変更を保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-142">When you enable this preview, users who change a label on a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="7c2f7-143">このシナリオは、暗号化のラベルが付けられたファイルに適用されます。また、暗号化を適用したラベルに暗号化が適用されなかったラベルからラベルが変更された場合にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-143">This scenario applies to files that are labeled with encryption, and also when the label change is from a label that didn't apply encryption to a label that does apply encryption.</span></span> <span data-ttu-id="7c2f7-144">[白い十字アイコンのエラー](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示された赤い円が表示され、新しい変更内容を別のコピーとして保存するように求められます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-144">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  
    
    <span data-ttu-id="7c2f7-145">ユーザーによって開始されたラベルの変更に加えて、管理者が、既にユーザーの同期クライアントにダウンロードしたファイルに適用されている発行済みラベルの設定を変更した場合にも、同じ現象が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-145">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="7c2f7-146">これらのシナリオの作業を失わないようにするには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-146">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="7c2f7-147">ラベルを適用するには、Office アプリの web 版を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-147">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="7c2f7-148">ラベルを適用した後、ファイルを閉じてから、他の変更を行うためにファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-148">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="7c2f7-149">SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに機密ラベルが自動的に適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-149">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="7c2f7-150">代わりに、このプレビューを有効にした後で機能を使用できるようにするには、次のタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-150">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="7c2f7-151">Azure Information Protection ラベルを機密ラベルに移行し、Microsoft 365 コンプライアンスセンター (または同等のラベル付き管理センター) から公開していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-151">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="7c2f7-152">ファイルをダウンロードしてから、それらを SharePoint にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-152">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="7c2f7-153">暗号化を適用したラベルが暗号化に使用する次のいずれかの構成を持っている場合、SharePoint は暗号化されたファイルを処理できません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-153">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="7c2f7-154">ユーザーがラベルと Word、PowerPoint、Excel のチェックボックスを**適用するときにアクセス許可を割り当てること**ができるようにし **、[アクセス許可を指定するようユーザーに要求する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-154">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="7c2f7-155">この設定は、"ユーザー定義の権限" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-155">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="7c2f7-156">**コンテンツへのユーザーアクセスの有効期限**が、 **Never**以外の値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-156">**User access to content expires** is set to a value other than **Never**.</span></span>
    
    <span data-ttu-id="7c2f7-157">これらの暗号化構成のいずれかを使用したラベルの場合、web 上の Office のユーザーにはラベルが表示されません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-157">For labels with either of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="7c2f7-158">また、このプレビューの新機能は、既にこれらの暗号化設定を持つラベル付きドキュメントでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-158">Additionally, the new capabilities from this preview can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="7c2f7-159">たとえば、これらのドキュメントは、更新された場合でも、検索結果では返されません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-159">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="7c2f7-160">ユーザーに編集権限を付与する暗号化されたドキュメントの場合、Office アプリの web 版ではコピーをブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-160">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="7c2f7-161">Azure Information Protection ドキュメント追跡サイトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-161">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="7c2f7-162">Office デスクトップアプリとモバイルアプリは、暗号化によってラベルが付けられたファイルの共同編集をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-162">Office desktop apps and mobile apps don't support coauthoring for files that are labeled with encryption.</span></span> <span data-ttu-id="7c2f7-163">これらのアプリは、ラベル付きで暗号化されたファイルを排他編集モードで引き続き開きます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-163">These apps continue to open labeled and encrypted files in exclusive editing mode.</span></span>

- <span data-ttu-id="7c2f7-164">ラベル付きのドキュメントが SharePoint にアップロードされ、そのラベルがサービスプリンシパル名のアカウントを使用して暗号化されている場合、そのドキュメントを web 上の Office で開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-164">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="7c2f7-165">シナリオの例としては、Microsoft Cloud App Security と、電子メールで Teams に送信されるファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-165">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="7c2f7-166">ユーザーは、web 用の Office を使用する代わりに、オフラインまたはスリープモードに移行した後に、Word、Excel、または PowerPoint 用のデスクトップおよびモバイルアプリを使用して、保存の問題を発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-166">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="7c2f7-167">これらのユーザーは、Office アプリセッションを再開して変更を保存しようとすると、元のファイルを保存するのではなく、コピーを保存するためのオプションを含むアップロードエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-167">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span> 

- <span data-ttu-id="7c2f7-168">次の方法で暗号化されたドキュメントは、web 上の Office で開くことができません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-168">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="7c2f7-169">オンプレミスキー ("自分のキーを保持する" または HYOK) を使用する暗号化</span><span class="sxs-lookup"><span data-stu-id="7c2f7-169">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="7c2f7-170">ラベルとは独立して適用された暗号化。たとえば、Rights Management protection テンプレートを直接適用します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-170">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="7c2f7-171">SharePoint でドキュメントに適用されているラベルを削除する場合、該当するラベルポリシーからラベルを削除するのではなく、ダウンロードしたドキュメントがラベル付けまたは暗号化されないようにします。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-171">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="7c2f7-172">比較すると、ラベル付きドキュメントが SharePoint の外部に保存されている場合、ラベルが削除されてもドキュメントは暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-172">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="7c2f7-173">テストフェーズではラベルを削除することもできますが、運用環境でラベルを削除するのは非常にまれです。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-173">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="7c2f7-174">プレビュー用の SharePoint Online 管理シェルの準備</span><span class="sxs-lookup"><span data-stu-id="7c2f7-174">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="7c2f7-175">プレビューを有効にする前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-175">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="7c2f7-176">最新バージョンが既にある場合は、プレビューを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-176">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="7c2f7-177">PowerShell ギャラリーから以前のバージョンの SharePoint Online 管理シェルをインストールした場合、次のコマンドレットを実行してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-177">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="7c2f7-178">または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-178">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="7c2f7-179">Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-179">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="7c2f7-180">言語を選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-180">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="7c2f7-181">x64 および x86 の .msi ファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-181">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="7c2f7-182">64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-182">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="7c2f7-183">不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-183">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="7c2f7-184">ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-184">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="7c2f7-185">Microsoft PowerShell を使用してプレビューを有効にする (オプトイン)</span><span class="sxs-lookup"><span data-stu-id="7c2f7-185">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="7c2f7-186">プレビューを有効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-186">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="7c2f7-187">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-187">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="7c2f7-188">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-188">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>
    
    <span data-ttu-id="7c2f7-189">注: Office 365 複数地域を使用している場合は、-Url パラメーターと[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)を使用して、地理的な場所の1つに対して SharePoint Online 管理センターサイトの Url を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-189">Note: If you have Office 365 Multi-Geo, use the -Url parameter with [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), and specify the SharePoint Online Administration Center site URL for one of your geo-locations.</span></span>

2. <span data-ttu-id="7c2f7-190">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-190">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. <span data-ttu-id="7c2f7-191">Office 365 の複数地域: 残りの各地域の場所について、手順1と2を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-191">For Office 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.</span></span>

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="7c2f7-192">機密ラベルを作成または変更した後のロールアウトをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="7c2f7-192">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="7c2f7-193">Microsoft 365 コンプライアンスセンターで機密ラベルを作成または変更した後、それを段階的に公開します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-193">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="7c2f7-194">完全に同期されていないラベルを発行した場合、ユーザーがファイルにラベルを適用してそれらを SharePoint にアップロードすると、ファイルを web 版の Office アプリで開くことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-194">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="7c2f7-195">検索と電子情報開示もファイルに対して機能しません。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-195">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="7c2f7-196">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-196">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="7c2f7-197">新しいまたは変更された機密ラベルを1人または2人のユーザーにのみ発行します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-197">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="7c2f7-198">最初の発行の後、少なくとも24時間待機します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-198">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="7c2f7-199">ラベルが完全に同期していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-199">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="7c2f7-200">ラベルを広く公開します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-200">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="7c2f7-201">Microsoft PowerShell を使用してプレビューを無効にする (オプトアウト)</span><span class="sxs-lookup"><span data-stu-id="7c2f7-201">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="7c2f7-202">このプレビューを無効にすると、プレビュー時にアップロードしたファイルはラベルで保護されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-202">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="7c2f7-203">対応する設定は引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-203">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="7c2f7-204">プレビューを無効にした後、新しいファイルにラベルを適用すると、フルテキスト検索、電子情報開示、および共同編集は機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-204">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="7c2f7-205">プレビューを無効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-205">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="7c2f7-206">グローバル管理者または SharePoint 管理者権限を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-206">Using a work or school account that has global administrator or SharePoint admin privileges, connect to SharePoint.</span></span> <span data-ttu-id="7c2f7-207">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-207">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="7c2f7-208">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-208">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```

## <a name="next-steps"></a><span data-ttu-id="7c2f7-209">次の手順</span><span class="sxs-lookup"><span data-stu-id="7c2f7-209">Next steps</span></span>

<span data-ttu-id="7c2f7-210">SharePoint と OneDrive で Office ファイルの機密ラベルを有効にしたので、自動ラベル付けポリシーを使用してこれらのファイルに自動的にラベル付けすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-210">Now that you've enabled sensitivity labels for Office files in SharePoint and OneDrive, consider automatically labeling these files by using auto-labeling policies.</span></span> <span data-ttu-id="7c2f7-211">詳細については、「[コンテンツに機密ラベルを自動的に適用する](apply-sensitivity-label-automatically.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c2f7-211">For more information, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>