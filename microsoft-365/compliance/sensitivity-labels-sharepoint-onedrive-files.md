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
ms.openlocfilehash: a1b42525984080d56a0f95018003cd251bff0122
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597504"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="e1271-103">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e1271-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="e1271-104">このプレビューの前に、SharePoint および OneDrive に格納されている Office ファイルへの暗号化を含む機密ラベルを適用すると、サービスはこれらのファイルのコンテンツを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e1271-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="e1271-105">このような状況では、共同編集、電子情報開示、データ損失防止、検索、Delve、その他のコラボレーション機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e1271-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="e1271-106">次のプレビューでは、クラウドベースのキーで暗号化が適用されている場合に、次の機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="e1271-106">This preview enables these features when the encryption has been applied with a cloud-based key:</span></span>

- <span data-ttu-id="e1271-107">SharePoint は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。</span><span class="sxs-lookup"><span data-stu-id="e1271-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="e1271-108">SharePoint では、各ラベルに対応する設定も適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1271-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="e1271-109">SharePoint または OneDrive からファイルをダウンロードすると、機密ラベルがファイルと共に移動し、設定が適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="e1271-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="e1271-110">Office ファイルに機密ラベルを適用し、機密ラベルが適用されている (ラベルのアクセス許可が許可されている場合) ファイルを開いて編集するには、Word、Excel、および PowerPoint の web バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1271-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="e1271-111">Word on the web では、ドキュメントを編集するときに自動ラベル付けを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1271-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="e1271-112">Office 365 eDiscovery は、機密ラベルが適用されているファイル内のフルテキスト検索をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e1271-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="e1271-113">データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。</span><span class="sxs-lookup"><span data-stu-id="e1271-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="e1271-114">機密ラベルの監視に使用できる3つの新しい監査イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="e1271-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="e1271-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="e1271-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="e1271-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="e1271-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="e1271-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="e1271-117">FileSensitivityLabelRemoved</span></span>

> [!NOTE]
> <span data-ttu-id="e1271-118">クラウドベースのキーで暗号化が適用されておらず、オンプレミスキーであっても、"自分のキーを保持する" と呼ばれるキー管理トポロジ (HYOK) では、SharePoint の動作はこのプレビューでは変更されません。</span><span class="sxs-lookup"><span data-stu-id="e1271-118">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span> 

<span data-ttu-id="e1271-119">また、Microsoft Teams、Office 365 グループ、および SharePoint サイトに機密ラベルを適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e1271-119">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="e1271-120">この個別のプレビューの詳細については、「 [Microsoft Teams、Office 365 グループ、および SharePoint サイト (パブリックプレビュー) を使用して機密ラベルを使用する](sensitivity-labels-teams-groups-sites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-120">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="e1271-121">いつでもこのプレビューの選択を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="e1271-121">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="e1271-122">次のビデオ (オーディオはない) を見て、これらの新機能をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e1271-122">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="e1271-123">要件</span><span class="sxs-lookup"><span data-stu-id="e1271-123">Requirements</span></span>

<span data-ttu-id="e1271-124">これらの機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e1271-124">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="e1271-125">現在 Azure Information Protection のラベルがある場合は、それらを機密ラベルに移行してから、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1271-125">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="e1271-126">手順については、「 [Azure Information Protection ラベルを統合秘密度ラベルに移行する方法](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-126">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="e1271-127">このプレビューでは、Windows で OneDrive 同期アプリのバージョン19.002.0121.0008 以降、バージョン19.002.0107.0008 以降の Mac を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1271-127">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="e1271-128">これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。</span><span class="sxs-lookup"><span data-stu-id="e1271-128">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="e1271-129">詳細については、 [OneDrive リリースノート](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-129">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="e1271-130">このプレビューを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1271-130">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="e1271-131">制限事項</span><span class="sxs-lookup"><span data-stu-id="e1271-131">Limitations</span></span>

- <span data-ttu-id="e1271-132">このプレビューを有効にすると、OneDrive Sync フォルダー内のファイルに対してラベルを変更したユーザーは、ファイルに加えた他の変更を保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1271-132">When you enable this preview, users who change a label to a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="e1271-133">[白い十字アイコンのエラー](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)が表示された赤い円が表示され、新しい変更内容を別のコピーとして保存するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e1271-133">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="e1271-134">ユーザーによって開始されたラベルの変更に加えて、管理者が、既にユーザーの同期クライアントにダウンロードしたファイルに適用されている発行済みラベルの設定を変更した場合にも、同じ現象が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e1271-134">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="e1271-135">これらのシナリオの作業を失わないようにするには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e1271-135">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="e1271-136">ラベルを適用するには、Office アプリの web 版を使用します。</span><span class="sxs-lookup"><span data-stu-id="e1271-136">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="e1271-137">ラベルを適用した後、ファイルを閉じてから、他の変更を行うためにファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e1271-137">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="e1271-138">SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに新しいラベルが自動的に適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e1271-138">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="e1271-139">代わりに、このプレビューを有効にした後で機能を使用できるようにするには、次のタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="e1271-139">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="e1271-140">Azure Information Protection ラベルを機密ラベルに移行し、Microsoft 365 コンプライアンスセンター (または同等のラベル付き管理センター) から公開していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-140">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="e1271-141">ファイルをダウンロードし、それらを SharePoint にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e1271-141">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="e1271-142">暗号化を適用したラベルが暗号化に使用する次のいずれかの構成を持っている場合、SharePoint は暗号化されたファイルを処理できません。</span><span class="sxs-lookup"><span data-stu-id="e1271-142">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="e1271-143">**ユーザーがラベルを適用するときにアクセス許可を割り当てる** **、Word、PowerPoint、および Excel に**ユーザーがアクセス許可を指定できるようにする</span><span class="sxs-lookup"><span data-stu-id="e1271-143">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="e1271-144">**コンテンツへのユーザーアクセスの有効期限**が、 **Never**以外の値に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e1271-144">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="e1271-145">ユーザーに編集権限を付与する暗号化されたドキュメントの場合、Office アプリの web 版ではコピーをブロックすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e1271-145">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="e1271-146">Azure Information Protection ドキュメント追跡サイトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e1271-146">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="e1271-147">Office デスクトップアプリとモバイルアプリは共同編集をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e1271-147">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="e1271-148">代わりに、これらのアプリは引き続き、排他編集モードでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e1271-148">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="e1271-149">ラベルに暗号化が含まれている場合、Microsoft Cloud App Security は SharePoint のファイルのラベル情報を読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="e1271-149">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="e1271-150">プレビュー用の SharePoint Online 管理シェルの準備</span><span class="sxs-lookup"><span data-stu-id="e1271-150">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="e1271-151">プレビューを有効にする前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-151">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="e1271-152">最新バージョンが既にある場合は、プレビューを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e1271-152">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="e1271-153">以前のバージョンの SharePoint Online Management Shell を PowerShell ギャラリーからインストールした場合は、次のコマンドレットを実行してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="e1271-153">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="e1271-154">または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e1271-154">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="e1271-155">Web ブラウザーで [ダウンロード センター] ページへと移動し、[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="e1271-155">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="e1271-156">言語を選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1271-156">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="e1271-157">x64 および x86 の .msi ファイルのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1271-157">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="e1271-158">64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="e1271-158">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="e1271-159">不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1271-159">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="e1271-160">ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e1271-160">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="e1271-161">Microsoft PowerShell を使用してプレビューを有効にする (オプトイン)</span><span class="sxs-lookup"><span data-stu-id="e1271-161">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="e1271-162">プレビューを有効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1271-162">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="e1271-163">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="e1271-163">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="e1271-164">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-164">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="e1271-165">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1271-165">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="e1271-166">機密ラベルを作成または変更した後のロールアウトをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e1271-166">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="e1271-167">Microsoft 365 コンプライアンスセンターで機密ラベルを作成または変更した後、それを段階的に公開します。</span><span class="sxs-lookup"><span data-stu-id="e1271-167">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="e1271-168">完全に同期されていないラベルを発行した場合、ユーザーがファイルにラベルを適用してそれらを SharePoint にアップロードすると、ファイルを web 版の Office アプリで開くことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1271-168">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="e1271-169">検索と電子情報開示もファイルに対して機能しません。</span><span class="sxs-lookup"><span data-stu-id="e1271-169">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="e1271-170">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1271-170">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="e1271-171">新しいまたは変更された機密ラベルを1人または2人のユーザーにのみ発行します。</span><span class="sxs-lookup"><span data-stu-id="e1271-171">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="e1271-172">最初の発行の後、少なくとも24時間待機します。</span><span class="sxs-lookup"><span data-stu-id="e1271-172">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="e1271-173">ラベルが完全に同期していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1271-173">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="e1271-174">ラベルを広く公開します。</span><span class="sxs-lookup"><span data-stu-id="e1271-174">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="e1271-175">Microsoft PowerShell を使用してプレビューを無効にする (オプトアウト)</span><span class="sxs-lookup"><span data-stu-id="e1271-175">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="e1271-176">このプレビューを無効にすると、プレビュー時にアップロードしたファイルはラベルで保護されたままになります。</span><span class="sxs-lookup"><span data-stu-id="e1271-176">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="e1271-177">対応する設定は引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1271-177">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="e1271-178">プレビューを無効にした後、新しいファイルにラベルを適用すると、フルテキスト検索、電子情報開示、および共同編集は機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="e1271-178">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="e1271-179">プレビューを無効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1271-179">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="e1271-180">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="e1271-180">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="e1271-181">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1271-181">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="e1271-182">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e1271-182">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
