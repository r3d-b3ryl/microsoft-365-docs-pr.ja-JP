---
title: 複数のコンテンツ検索の作成、報告、削除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 検索の作成や PowerShell スクリプトによるレポートの実行など、コンテンツ検索タスクを自動化する方法については、「セキュリティ & コンプライアンス センター」Officeします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 615c6b59ea484a4a0cd5248ce5083e7ee7d817ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908311"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="ac7eb-103">複数のコンテンツ検索の作成、報告、削除</span><span class="sxs-lookup"><span data-stu-id="ac7eb-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="ac7eb-104">探索検索の迅速な作成とレポート作成は、多くの場合、基になるデータと検索の豊富さと品質について学ぶ際に、電子情報開示と調査の重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="ac7eb-105">これを行うのに役立つセキュリティ & コンプライアンス センター PowerShell には、時間のかかるコンテンツ検索タスクを自動化するための一連のコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="ac7eb-106">これらのスクリプトを使用すると、多数の検索を簡単に作成し、推定検索結果のレポートを実行して、問題のデータ量を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="ac7eb-107">スクリプトを使用して、異なるバージョンの検索を作成して、それぞれ生成される結果を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="ac7eb-108">これらのスクリプトを使用すると、データを迅速かつ効率的に識別して作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="ac7eb-109">コンテンツ検索を作成する前に</span><span class="sxs-lookup"><span data-stu-id="ac7eb-109">Before you create a Content Search</span></span>

- <span data-ttu-id="ac7eb-110">このトピックで説明するスクリプトを実行するには、セキュリティ & コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="ac7eb-111">手順 1 で CSV ファイルに追加できる組織内の OneDrive for Business サイトの URL の一覧を収集するには、「組織内のすべての OneDrive の場所のリストを作成する」を [参照してください](/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="ac7eb-112">このトピックで作成したファイルはすべて、必ず同じフォルダーに保存してください。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="ac7eb-113">そうすると、スクリプトの実行が容易になります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="ac7eb-114">スクリプトには、最小限のエラー処理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="ac7eb-115">主な目的は、複数のコンテンツ検索をすばやく作成、レポート、および削除する方法です。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="ac7eb-p104">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="ac7eb-121">手順 1: 実行する検索に関する情報を含む CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="ac7eb-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="ac7eb-122">この手順で作成するコンマ区切り値 (CSV) ファイルには、検索する各ユーザーの行が含まれる。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="ac7eb-123">ユーザーの Exchange Online メールボックス (アーカイブ メールボックスが有効な場合は含む) と OneDrive for Business サイトを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="ac7eb-124">または、メールボックスまたは OneDrive for Business サイトを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="ac7eb-125">SharePoint Online 組織内の任意のサイトを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="ac7eb-126">手順 3 で実行するスクリプトは、CSV ファイル内の各行に対して個別の検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="ac7eb-127">NotePad を使用して、次のテキストを .txt ファイルにコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="ac7eb-128">このファイルをローカル コンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="ac7eb-129">他のスクリプトもこのフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="ac7eb-130">ファイルの最初の行 (ヘッダー行) には **、New-ComplianceSearch** コマンドレット (手順 3 のスクリプト) で新しいコンテンツ検索を作成するために使用されるパラメーターが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="ac7eb-131">各パラメーター名はコンマで区切られています。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="ac7eb-132">ヘッダー行にスペースが入っていなかご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="ac7eb-133">ヘッダー行の下の各行は、各検索のパラメーター値を表します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="ac7eb-134">CSV ファイル内のプレースホルダー データを実際のデータに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="ac7eb-135">Excel で .txt ファイルを開き、次の表の情報を使用して、各検索の情報を含むファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="ac7eb-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac7eb-136">Parameter</span></span>|<span data-ttu-id="ac7eb-137">説明</span><span class="sxs-lookup"><span data-stu-id="ac7eb-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="ac7eb-138">ユーザーのメールボックスの SMTP アドレス。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="ac7eb-139">ユーザーの OneDrive for Business サイトの URL、または組織内の任意のサイトの URL。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="ac7eb-140">OneDrive for Business サイトの URL については、次の形式を使用します ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` 。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="ac7eb-141">例: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="ac7eb-142">検索の検索クエリ。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-142">The search query for the search.</span></span> <span data-ttu-id="ac7eb-143">検索クエリの作成の詳細については、「コンテンツ検索のキーワード クエリと [検索条件」を参照してください](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="ac7eb-144">電子メールの場合、メッセージが受信者によって受信された日付または送信者によって送信された日付または後の日付。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="ac7eb-145">SharePoint サイトまたは OneDrive for Business サイトのドキュメントの場合、ドキュメントが最後に変更された日付または変更後の日付。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="ac7eb-146">電子メールの場合、ユーザーが送信したメッセージの日付またはメッセージが送信される前の日付。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="ac7eb-147">SharePoint サイトまたは OneDrive for Business サイトのドキュメントの場合、ドキュメントが最後に変更された日付または前の日付。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="ac7eb-148">Excel ファイルを CSV ファイルとしてローカル コンピューター上のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="ac7eb-149">手順 3 で作成したスクリプトは、この CSV ファイルの情報を使用して検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="ac7eb-150">手順 2: セキュリティ/コンプライアンス センターの PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="ac7eb-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="ac7eb-151">次に、組織のセキュリティ/コンプライアンス センターの PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="ac7eb-152">詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="ac7eb-153">手順 3: スクリプトを実行して検索を作成して開始する</span><span class="sxs-lookup"><span data-stu-id="ac7eb-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="ac7eb-154">この手順のスクリプトでは、手順 1 で作成した CSV ファイルの行ごとに個別のコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="ac7eb-155">このスクリプトを実行すると、次の 2 つの値を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="ac7eb-156">**検索グループ ID** - この名前を使用すると、CSV ファイルから作成された検索を簡単に整理できます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="ac7eb-157">作成された各検索には、検索グループ ID が付いた名前が付き、検索名に番号が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="ac7eb-158">たとえば、検索グループ ID に **ContosoCase** と入力すると、検索の名前は **ContosoCase_1、ContosoCase_2、ContosoCase_3** などです。 </span><span class="sxs-lookup"><span data-stu-id="ac7eb-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="ac7eb-159">入力する名前では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="ac7eb-160">手順 4 と手順 5 の検索グループ ID を使用する場合は、作成した場合と同じケースを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="ac7eb-161">**CSV ファイル** - 手順 1 で作成した CSV ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="ac7eb-162">必ず完全なファイル名を使用し、.csv ファイル拡張子を含めます。たとえば、  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="ac7eb-163">このスクリプトを実行するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-163">To run the script:</span></span>

1. <span data-ttu-id="ac7eb-164">ファイル名のサフィックス .ps1 をWindows PowerShellして、次のテキストをスクリプト ファイルに保存します。たとえば、 `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="ac7eb-165">他のファイルを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="ac7eb-166">次Windows PowerShell、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="ac7eb-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="ac7eb-167">[グループ **ID の検索] プロンプト** で、検索グループ名を入力し、Enter キーを **押します**。たとえば、  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="ac7eb-168">この名前は大文字と小文字を区別しますので、以降の手順で同じ方法で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="ac7eb-169">[ソース **CSV ファイル] プロンプトで** 、.csv ファイル拡張子を含む CSV ファイルの名前を入力します。たとえば、  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="ac7eb-170">Enter キー **を押** してスクリプトの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="ac7eb-171">スクリプトには、検索の作成と実行の進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="ac7eb-172">スクリプトが完了すると、プロンプトに戻されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-172">When the script is complete, it returns to the prompt.</span></span>

   ![複数のコンプライアンス検索を作成するスクリプトを実行した場合の出力例](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="ac7eb-174">手順 4: スクリプトを実行して検索の見積もりを報告する</span><span class="sxs-lookup"><span data-stu-id="ac7eb-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="ac7eb-175">検索を作成した後、次の手順では、手順 3 で作成した各検索の検索ヒット数の簡単なレポートを表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="ac7eb-176">レポートには、各検索の結果のサイズと、すべての検索のヒット数と合計サイズも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="ac7eb-177">レポート スクリプトを実行すると、レポートを CSV ファイルに保存する場合は、検索グループ ID と CSV ファイル名の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="ac7eb-178">ファイル名のサフィックス .ps1 をWindows PowerShellして、次のテキストをスクリプト ファイルに保存します。たとえば、 `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="ac7eb-179">他のファイルを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="ac7eb-180">次Windows PowerShell、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="ac7eb-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="ac7eb-181">[グループ **ID の検索] プロンプト** で、検索グループ名を入力し、Enter キーを **押します**。たとえば  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="ac7eb-182">この名前は大文字と小文字を区別しますので、手順 3 でスクリプトを実行した場合と同じ方法で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="ac7eb-183">レポートを CSV ファイルに保存するファイル パス (レポートを表示する場合は空白 **のままにする)** プロンプトで、レポートを CSV ファイルに保存する場合は、完全なファイル名パス (.csv ファイル拡張子を含む) のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="ac7eb-184">CSV ファイルの名前 (.csv ファイル拡張子を含む)。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="ac7eb-185">たとえば、現在のディレクトリに保存する場合や、別のフォルダーに保存する場合  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` に入力できます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="ac7eb-186">また、プロンプトを空白のままにしてレポートを表示できますが、ファイルに保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="ac7eb-187">**[Enter]** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-187">Press **Enter**.</span></span>

   <span data-ttu-id="ac7eb-188">スクリプトには、検索の作成と実行の進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="ac7eb-189">スクリプトが完了すると、レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-189">When the script is complete, the report is displayed.</span></span>

   ![検索レポートを実行して検索グループの推定値を表示する](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="ac7eb-191">検索グループ内の複数の検索で同じメールボックスまたはサイトがコンテンツの場所として指定されている場合、レポート内の合計結果の推定値 (アイテム数と合計サイズの両方) には、同じアイテムの結果が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="ac7eb-192">これは、検索グループ内の異なる検索に対するクエリと一致する場合、同じ電子メール メッセージまたはドキュメントが複数カウントされるためです。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="ac7eb-193">手順 5: スクリプトを実行して検索を削除する</span><span class="sxs-lookup"><span data-stu-id="ac7eb-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="ac7eb-194">多くの検索を作成している可能性があるから、この最後のスクリプトを使用すると、手順 3 で作成した検索をすばやく簡単に削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="ac7eb-195">他のスクリプトと同様に、検索グループ ID の入力も求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="ac7eb-196">このスクリプトを実行すると、検索名に検索グループ ID を含むすべての検索が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="ac7eb-197">ファイル名のサフィックス .ps1 をWindows PowerShellして、次のテキストをスクリプト ファイルに保存します。たとえば、 `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="ac7eb-198">他のファイルを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="ac7eb-199">次Windows PowerShell、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="ac7eb-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="ac7eb-200">[グループ **ID の検索** ] プロンプトで、削除する検索の検索グループ名を入力し、Enter キーを **押します**。たとえば、  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="ac7eb-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="ac7eb-201">この名前は大文字と小文字を区別しますので、手順 3 でスクリプトを実行した場合と同じ方法で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="ac7eb-202">スクリプトには、削除された各検索の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac7eb-202">The script displays the name of each search that's deleted.</span></span>

   ![検索グループ内の検索を削除するスクリプトを実行する](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)