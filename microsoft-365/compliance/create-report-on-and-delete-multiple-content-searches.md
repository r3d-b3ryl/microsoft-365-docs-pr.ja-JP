---
title: 複数のコンテンツ検索の作成、報告、削除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Office 365 のセキュリティ & コンプライアンスセンターで、PowerShell スクリプトを使用して検索を作成したりレポートを実行したりするなど、コンテンツ検索タスクを自動化する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 389cc9e15bc661e967f7af769ac48c4ae6e27228
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817986"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="346f9-103">複数のコンテンツ検索の作成、報告、削除</span><span class="sxs-lookup"><span data-stu-id="346f9-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="346f9-104">検索検索を迅速に作成およびレポートすることは、基礎となるデータについて学習しようとしているときに電子情報開示や調査を行う際に重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="346f9-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="346f9-105">これを実現するために、セキュリティ & コンプライアンスセンターの PowerShell は、時間のかかるコンテンツ検索タスクを自動化する一連のコマンドレットを提供します。</span><span class="sxs-lookup"><span data-stu-id="346f9-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="346f9-106">これらのスクリプトを使用すると、多数の検索をすばやく簡単に作成し、予想される検索結果のレポートを実行して、問題のデータ量を判断するのに役立つことができます。</span><span class="sxs-lookup"><span data-stu-id="346f9-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="346f9-107">また、これらのスクリプトを使用して、それぞれの結果を比較するさまざまなバージョンの検索を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="346f9-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="346f9-108">これらのスクリプトは、データを迅速かつ効率的に識別してカリングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="346f9-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-create-a-content-search"></a><span data-ttu-id="346f9-109">コンテンツ検索を作成する前に</span><span class="sxs-lookup"><span data-stu-id="346f9-109">Before you create a Content Search</span></span>

- <span data-ttu-id="346f9-110">このトピックで説明するスクリプトを実行するには、セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f9-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="346f9-111">手順1で CSV ファイルに追加できる、組織内の OneDrive for Business サイトの Url の一覧を収集するには、「[組織内のすべての onedrive の場所の一覧を作成](https://docs.microsoft.com/onedrive/list-onedrive-urls)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span> 
    
- <span data-ttu-id="346f9-112">このトピックで作成するすべてのファイルを同じフォルダーに保存するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="346f9-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="346f9-113">これにより、スクリプトをより簡単に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="346f9-113">That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="346f9-114">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="346f9-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="346f9-115">その主な目的は、複数のコンテンツ検索をすばやく作成、レポート作成、および削除することです。</span><span class="sxs-lookup"><span data-stu-id="346f9-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="346f9-116">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span><span class="sxs-lookup"><span data-stu-id="346f9-116">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="346f9-117">The sample scripts are provided AS IS without warranty of any kind.</span><span class="sxs-lookup"><span data-stu-id="346f9-117">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="346f9-118">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span><span class="sxs-lookup"><span data-stu-id="346f9-118">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="346f9-119">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span><span class="sxs-lookup"><span data-stu-id="346f9-119">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="346f9-120">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span><span class="sxs-lookup"><span data-stu-id="346f9-120">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="346f9-121">手順 1: 実行する検索に関する情報を含む CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="346f9-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="346f9-122">この手順で作成するコンマ区切り値 (CSV) ファイルには、検索するユーザーごとに1つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="346f9-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="346f9-123">ユーザーの Exchange Online メールボックス (アーカイブメールボックスが有効になっている場合) と OneDrive for Business サイトを検索できます。</span><span class="sxs-lookup"><span data-stu-id="346f9-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="346f9-124">または、メールボックスまたは OneDrive for Business サイトのみを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="346f9-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="346f9-125">SharePoint Online 組織の任意のサイトを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="346f9-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="346f9-126">手順3で実行するスクリプトは、CSV ファイルの各行に対して個別に検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="346f9-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="346f9-127">次のテキストをコピーして、メモ帳を使用して .txt ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="346f9-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="346f9-128">このファイルをローカルコンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="346f9-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="346f9-129">他のスクリプトもこのフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="346f9-129">You'll save the other scripts to this folder as well.</span></span>
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="346f9-130">ファイルの最初の行、つまりヘッダー行には、新しいコンテンツ検索を作成するために、 **new-compliancesearch**コマンドレットで使用するパラメーター (手順3のスクリプト) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="346f9-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="346f9-131">各パラメーター名はコンマで区切られています。</span><span class="sxs-lookup"><span data-stu-id="346f9-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="346f9-132">ヘッダー行にスペースがないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="346f9-133">ヘッダー行の下の各行は、各検索のパラメーター値を表します。</span><span class="sxs-lookup"><span data-stu-id="346f9-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="346f9-134">必ず、CSV ファイル内のプレースホルダーデータを実際のデータに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="346f9-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="346f9-135">Excel で .txt ファイルを開き、次の表の情報を使用して、各検索の情報でファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="346f9-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="346f9-136">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="346f9-136">**Parameter**</span></span>|<span data-ttu-id="346f9-137">**説明**</span><span class="sxs-lookup"><span data-stu-id="346f9-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="346f9-138">ユーザーのメールボックスの SMTP アドレス。</span><span class="sxs-lookup"><span data-stu-id="346f9-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="346f9-139">ユーザーの OneDrive for Business サイトの URL、または組織内のサイトの URL。</span><span class="sxs-lookup"><span data-stu-id="346f9-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="346f9-140">OneDrive for Business サイトの URL の場合は、次の形式を使用します ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` 。</span><span class="sxs-lookup"><span data-stu-id="346f9-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="346f9-141">例: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="346f9-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>  <br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="346f9-142">検索の検索クエリ。</span><span class="sxs-lookup"><span data-stu-id="346f9-142">The search query for the search.</span></span> <span data-ttu-id="346f9-143">検索クエリの作成の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>  <br/> |
    | `StartDate` <br/> |<span data-ttu-id="346f9-144">電子メールの場合、メッセージが受信者によって受信された日付または送信者によって送信された日付。</span><span class="sxs-lookup"><span data-stu-id="346f9-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="346f9-145">SharePoint または OneDrive for Business サイトのドキュメントの場合は、ドキュメントが最後に変更された日付またはそれ以降の日付を指定します。</span><span class="sxs-lookup"><span data-stu-id="346f9-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="346f9-146">電子メールの場合、ユーザーによって送信されたメッセージが送信された日付またはそれ以前の日付。</span><span class="sxs-lookup"><span data-stu-id="346f9-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="346f9-147">SharePoint または OneDrive for Business サイトのドキュメントの場合、ドキュメントが最後に変更された日付またはそれ以前の日付。</span><span class="sxs-lookup"><span data-stu-id="346f9-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="346f9-148">Excel ファイルを CSV ファイルとして、ローカルコンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="346f9-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="346f9-149">手順3で作成したスクリプトでは、この CSV ファイルの情報を使用して検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="346f9-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="346f9-150">手順 2: セキュリティ/コンプライアンス センターの PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="346f9-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>
  
<span data-ttu-id="346f9-151">次に、組織のセキュリティ/コンプライアンス センターの PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="346f9-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="346f9-152">詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="346f9-153">Microsoft 365 アカウントで多要素認証 (MFA) やフェデレーション認証を使用する場合、次のトピックの手順ではセキュリティ/コンプライアンス センターの PowerShell に接続できません。</span><span class="sxs-lookup"><span data-stu-id="346f9-153">If your Microsoft 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="346f9-154">代わりに、「[多要素認証を使用してセキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-154">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="346f9-155">手順 3: スクリプトを実行して検索を作成および開始する</span><span class="sxs-lookup"><span data-stu-id="346f9-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="346f9-156">この手順のスクリプトは、手順1で作成した CSV ファイルの各行に対して個別のコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="346f9-156">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="346f9-157">このスクリプトを実行すると、次の2つの値を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="346f9-157">When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="346f9-158">**検索グループ ID** -この名前は、CSV ファイルから作成された検索を簡単に整理する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="346f9-158">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="346f9-159">作成された各検索には、検索グループ ID が付けられ、検索名に数字が追加されます。</span><span class="sxs-lookup"><span data-stu-id="346f9-159">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="346f9-160">たとえば、検索グループ ID に「 **ContosoCase** 」と入力した場合、検索には**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**などの名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="346f9-160">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="346f9-161">入力する名前は大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-161">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="346f9-162">手順4と手順5で検索グループ ID を使用する場合は、作成時と同じケースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f9-162">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="346f9-163">**Csv ファイル**-手順1で作成した csv ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="346f9-163">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="346f9-164">必ず完全なファイル名を指定してください。ファイル拡張子は .csv にします。たとえば、のように `ContosoCase.csv` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-164">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="346f9-165">このスクリプトを実行するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="346f9-165">To run the script:</span></span>

1. <span data-ttu-id="346f9-166">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、のように `CreateSearches.ps1` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-166">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="346f9-167">他のファイルを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="346f9-167">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. <span data-ttu-id="346f9-168">Windows PowerShell で、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="346f9-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="346f9-169">[**検索グループ ID** ] プロンプトで、検索グループ名**を入力し、enter キーを**押します。たとえば、のように `ContosoCase` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-169">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="346f9-170">この名前は大文字と小文字が区別されるので、以降の手順と同じ方法で入力する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="346f9-170">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="346f9-171">[**ソース csv ファイル**] プロンプトで、csv ファイル拡張子を含む csv ファイルの名前を入力します。たとえば、のように `ContosoCase.csv` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="346f9-172">**Enter**キーを押して、スクリプトの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="346f9-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="346f9-173">スクリプトには、検索の作成と実行の進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="346f9-173">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="346f9-174">スクリプトが完了すると、プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="346f9-174">When the script is complete, it returns to the prompt.</span></span> 
    
    ![複数のコンプライアンス検索を作成するスクリプトを実行した場合の出力例](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="346f9-176">手順 4: 検索結果を報告するスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="346f9-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="346f9-177">検索を作成した後、手順3で作成した各検索の検索ヒット数の簡単なレポートを表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="346f9-177">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="346f9-178">レポートには、各検索の結果のサイズと、ヒットの合計数とすべての検索の合計サイズも含まれます。</span><span class="sxs-lookup"><span data-stu-id="346f9-178">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="346f9-179">レポートスクリプトを実行すると、検索グループ ID の入力を求められます。また、レポートを CSV ファイルに保存する場合は、CSV ファイル名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f9-179">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="346f9-180">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、のように `SearchReport.ps1` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-180">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="346f9-181">他のファイルを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="346f9-181">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. <span data-ttu-id="346f9-182">Windows PowerShell で、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="346f9-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="346f9-183">[**検索グループ ID** ] プロンプトで、検索グループ名**を入力し、enter キーを**押します。例を示し `ContosoCase` ます。</span><span class="sxs-lookup"><span data-stu-id="346f9-183">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="346f9-184">この名前は大文字と小文字が区別されるので、手順3でスクリプトを実行したときと同じ方法で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f9-184">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="346f9-185">レポートを csv ファイルに保存するための**ファイルパス (空白のままに**してレポートを表示します) を入力します。レポートを csv ファイルに保存する場合は、完全なファイル名パス (.csv ファイル拡張子を含む) のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="346f9-185">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="346f9-186">csv ファイル拡張子を含む CSV ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="346f9-186">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="346f9-187">たとえば、 `ContosoCaseReport.csv` 現在のディレクトリに保存するか、 `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` 別のフォルダーに保存するように入力することができます。</span><span class="sxs-lookup"><span data-stu-id="346f9-187">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="346f9-188">また、メッセージを空白のままにしてレポートを表示することもできますが、ファイルに保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="346f9-188">You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="346f9-189">**[Enter]** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="346f9-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="346f9-190">スクリプトには、検索の作成と実行の進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="346f9-190">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="346f9-191">スクリプトが完了すると、レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="346f9-191">When the script is complete, the report is displayed.</span></span> 
    
    ![検索レポートを実行して検索グループの推定値を表示する](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="346f9-193">同じメールボックスまたはサイトが検索グループ内の複数の検索でコンテンツの場所として指定されている場合、レポート内の合計結果の推定 (アイテム数と合計サイズの両方) に同じアイテムに対する結果が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="346f9-193">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="346f9-194">これは、同じ電子メールメッセージまたはドキュメントが検索グループ内のさまざまな検索のクエリに一致する場合に、複数回カウントされるためです。</span><span class="sxs-lookup"><span data-stu-id="346f9-194">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="346f9-195">手順 5: 検索を削除するスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="346f9-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="346f9-196">多数の検索を作成している可能性があるため、この最後のスクリプトにより、手順3で作成した検索を簡単に削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="346f9-196">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="346f9-197">他のスクリプトと同様に、この1つは検索グループ ID の入力も求められます。</span><span class="sxs-lookup"><span data-stu-id="346f9-197">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="346f9-198">このスクリプトを実行すると、検索グループ ID が指定されている検索はすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="346f9-198">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="346f9-199">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、のように `DeleteSearches.ps1` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-199">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="346f9-200">他のファイルを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="346f9-200">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. <span data-ttu-id="346f9-201">Windows PowerShell で、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="346f9-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="346f9-202">[**検索グループ ID** ] プロンプトで、削除する検索の検索グループ名**を入力し、enter キーを**押します。たとえば、のように `ContosoCase` なります。</span><span class="sxs-lookup"><span data-stu-id="346f9-202">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="346f9-203">この名前は大文字と小文字が区別されるので、手順3でスクリプトを実行したときと同じ方法で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346f9-203">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="346f9-204">スクリプトは、削除された各検索の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="346f9-204">The script displays the name of each search that's deleted.</span></span>
    
    ![検索グループ内の検索を削除するスクリプトを実行する](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
