---
title: SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理者は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルの機密ラベルサポートを有効にすることができます。
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802830"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="bda68-103">SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bda68-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="bda68-104">以前は、SharePoint および OneDrive に格納された Office ファイルへの暗号化を含む機密ラベルを適用すると、サービスはこれらのファイルのコンテンツを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="bda68-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="bda68-105">このような状況では、共同編集、電子情報開示、データ損失防止、検索、Delve、その他のコラボレーション機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="bda68-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="bda68-106">このプレビューでは、次の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bda68-106">This preview enables these features:</span></span>

- <span data-ttu-id="bda68-107">SharePoint は、SharePoint および OneDrive の Word、Excel、および PowerPoint ファイルに適用される機密ラベルを認識します。</span><span class="sxs-lookup"><span data-stu-id="bda68-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="bda68-108">SharePoint では、各ラベルに対応する設定も適用されます。</span><span class="sxs-lookup"><span data-stu-id="bda68-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="bda68-109">SharePoint または OneDrive からファイルをダウンロードすると、機密ラベルがファイルと共に移動し、設定が適用されたままになります。</span><span class="sxs-lookup"><span data-stu-id="bda68-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="bda68-110">Office ファイルに機密ラベルを適用し、機密ラベルが適用されている (ラベルのアクセス許可が許可されている場合) ファイルを開いて編集するには、Word、Excel、および PowerPoint の web バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="bda68-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="bda68-111">Word on the web では、ドキュメントを編集するときに自動ラベル付けを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bda68-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="bda68-112">Office 365 eDiscovery は、機密ラベルが適用されているファイル内のフルテキスト検索をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bda68-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="bda68-113">データ損失防止 (DLP) ポリシーは、これらのファイルの内容を対象としています。</span><span class="sxs-lookup"><span data-stu-id="bda68-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="bda68-114">機密ラベルの監視に使用できる3つの新しい監査イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="bda68-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="bda68-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="bda68-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="bda68-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="bda68-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="bda68-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="bda68-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="bda68-118">また、Microsoft Teams、Office 365 グループ、および SharePoint サイトに機密ラベルを適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bda68-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="bda68-119">[詳細情報](sensitivity-labels-teams-groups-sites.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bda68-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="bda68-120">必要に応じて、いつでもプレビューの表示を中止することができます。</span><span class="sxs-lookup"><span data-stu-id="bda68-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="bda68-121">要件</span><span class="sxs-lookup"><span data-stu-id="bda68-121">Requirements</span></span>

<span data-ttu-id="bda68-122">これらの機能は、[機密ラベル](sensitivity-labels.md)に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bda68-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="bda68-123">Azure Information Protection ラベルを使用した場合は、それらを機密ラベルに変換して、アップロードする新しいファイルに対してこれらの機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bda68-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="bda68-124">方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bda68-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="bda68-125">このプレビューでは、Windows とバージョン19.002.0107.0008 以降の Mac の OneDrive 同期アプリバージョン19.002.0121.0008 を使用します。</span><span class="sxs-lookup"><span data-stu-id="bda68-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="bda68-126">これらのバージョンは、2019年1月28日にリリースされ、現在すべてのリングにリリースされています。</span><span class="sxs-lookup"><span data-stu-id="bda68-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="bda68-127">[OneDrive リリースノートを参照してください](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="bda68-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="bda68-128">このプレビューを有効にすると、以前のバージョンの同期アプリを実行しているユーザーに更新を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bda68-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="bda68-129">制限事項</span><span class="sxs-lookup"><span data-stu-id="bda68-129">Limitations</span></span>

- <span data-ttu-id="bda68-130">このプレビューを有効にすると、Office デスクトップまたはモバイルアプリを使用してファイルにラベルを適用するユーザーは、ファイルに加えた他の変更を保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bda68-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="bda68-131">代わりに、アプリはユーザーにローカルの変更を保存するか、破棄するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bda68-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="bda68-132">作業が失われるのを防ぐには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bda68-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="bda68-133">ラベルを適用するには、Office アプリの web 版を使用します。</span><span class="sxs-lookup"><span data-stu-id="bda68-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="bda68-134">ラベルを適用した後でファイルを閉じてから、他の変更を行うためにファイルを再度開いてください。</span><span class="sxs-lookup"><span data-stu-id="bda68-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="bda68-135">SharePoint では、Azure Information Protection ラベルを使用して既に暗号化されている既存のファイルに新しいラベルが自動的に適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="bda68-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="bda68-136">代わりに、このプレビューを有効にした後で機能を使用できるようにするには、次のタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="bda68-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="bda68-137">Azure Information Protection ラベルを機密ラベルに変換します。</span><span class="sxs-lookup"><span data-stu-id="bda68-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="bda68-138">ファイルをダウンロードし、それらを SharePoint にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bda68-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="bda68-139">SharePoint では、カスタムアクセス許可と、有効期限のあるラベルを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="bda68-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="bda68-140">ユーザーが編集アクセス許可を持っている場合、Office アプリの web 版では、ラベルのコピーポリシー設定に関係なくコピーが許可されます。</span><span class="sxs-lookup"><span data-stu-id="bda68-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="bda68-141">RMS の失効、追跡、およびレポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bda68-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="bda68-142">Office デスクトップアプリとモバイルアプリは共同編集をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bda68-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="bda68-143">代わりに、これらのアプリは引き続き、排他編集モードでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bda68-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="bda68-144">ラベルに暗号化が含まれている場合、Microsoft Cloud App Security は SharePoint のファイルのラベル情報を読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="bda68-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="bda68-145">プレビュー用の SharePoint Online 管理シェルの準備</span><span class="sxs-lookup"><span data-stu-id="bda68-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="bda68-146">プレビューを有効にする前に、SharePoint Online Management Shell バージョン16.0.19418.12000 以降を実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bda68-146">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="bda68-147">最新バージョンが既にある場合は、プレビューを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bda68-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="bda68-148">以前のバージョンの SharePoint Online Management Shell を PowerShell ギャラリーからインストールした場合は、次のコマンドレットを実行してモジュールを更新できます。</span><span class="sxs-lookup"><span data-stu-id="bda68-148">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="bda68-149">または、Microsoft ダウンロードセンターから以前のバージョンの SharePoint Online 管理シェルをインストールした場合は、[**プログラムの追加と削除**] に移動して、Sharepoint Online 管理シェルをアンインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bda68-149">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="bda68-150">Web ブラウザーで、ダウンロードセンターページに移動して、[最新の SharePoint Online 管理シェルをダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=255251)します。</span><span class="sxs-lookup"><span data-stu-id="bda68-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="bda68-151">言語を選択し、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bda68-151">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="bda68-152">X64 ファイルと x86 .msi ファイルのどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bda68-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="bda68-153">64ビット版の Windows または x86 ファイル (32 ビット版を実行している場合) を実行する場合は、x64 ファイルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="bda68-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="bda68-154">不明な場合は、[どのバージョンの Windows オペレーティングシステムを実行](https://support.microsoft.com/help/13443/windows-which-operating-system)しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bda68-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="bda68-155">ファイルをダウンロードした後、ファイルを実行し、セットアップウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bda68-155">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="bda68-156">Microsoft PowerShell を使用してプレビューを有効にする (オプトイン)</span><span class="sxs-lookup"><span data-stu-id="bda68-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="bda68-157">プレビューを有効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bda68-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="bda68-158">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="bda68-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="bda68-159">方法の詳細については、「[SharePoint のオンライン管理シェルを使うにあたって](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bda68-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="bda68-160">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bda68-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="bda68-161">機密ラベルを作成または変更した後のロールアウトをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="bda68-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="bda68-162">Microsoft 365 コンプライアンスセンターで機密ラベルを作成または変更した後、それを段階的に公開します。</span><span class="sxs-lookup"><span data-stu-id="bda68-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="bda68-163">完全に同期されていないラベルを発行した場合、ユーザーがファイルにラベルを適用してそれらを SharePoint にアップロードすると、ファイルを web 版の Office アプリで開くことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="bda68-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="bda68-164">検索と電子情報開示もファイルに対して機能しません。</span><span class="sxs-lookup"><span data-stu-id="bda68-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="bda68-165">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bda68-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="bda68-166">新しいまたは変更された機密ラベルを1人または2人のユーザーにのみ発行します。</span><span class="sxs-lookup"><span data-stu-id="bda68-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="bda68-167">最初の発行の後、少なくとも24時間待機します。</span><span class="sxs-lookup"><span data-stu-id="bda68-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="bda68-168">ラベルが完全に同期していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bda68-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="bda68-169">ラベルを広く公開します。</span><span class="sxs-lookup"><span data-stu-id="bda68-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="bda68-170">Microsoft PowerShell を使用してプレビューを無効にする (オプトアウト)</span><span class="sxs-lookup"><span data-stu-id="bda68-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="bda68-171">このプレビューを無効にすると、プレビュー時にアップロードしたファイルはラベルで保護されたままになります。</span><span class="sxs-lookup"><span data-stu-id="bda68-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="bda68-172">対応する設定は引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="bda68-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="bda68-173">プレビューを無効にした後、新しいファイルにラベルを適用すると、フルテキスト検索、電子情報開示、および共同編集は機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="bda68-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="bda68-174">プレビューを無効にするには、Set-spotenant コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bda68-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="bda68-175">Office 365 で全体管理者または SharePoint 管理者特権を持つ職場または学校のアカウントを使用して、SharePoint に接続します。</span><span class="sxs-lookup"><span data-stu-id="bda68-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="bda68-176">方法の詳細については、「[SharePoint のオンライン管理シェルを使うにあたって](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bda68-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="bda68-177">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bda68-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
