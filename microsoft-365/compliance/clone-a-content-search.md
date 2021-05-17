---
title: コンテンツ検索をコピーする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: この記事の PowerShell スクリプトを使用して、コンプライアンス センターの既存のコンテンツ検索をすばやく複製Office 365またはMicrosoft 365。
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918063"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="2432e-103">コンテンツ検索をコピーする</span><span class="sxs-lookup"><span data-stu-id="2432e-103">Clone a Content Search</span></span>

<span data-ttu-id="2432e-104">Office 365 または Microsoft 365 のコンプライアンス センターで、多くのメールボックスまたは SharePoint サイトと OneDrive for Business サイトを検索するコンテンツ検索を作成するには、しばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2432e-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="2432e-105">URL を誤って入力すると、検索するサイトを指定すると、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2432e-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="2432e-106">これらの問題を回避するには、この記事の Windows PowerShell スクリプトを使用して、既存のコンテンツ検索をすばやく複製できます。</span><span class="sxs-lookup"><span data-stu-id="2432e-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="2432e-107">検索を複製すると、元の検索と同じプロパティ (コンテンツの場所や検索クエリなど) を含む新しい検索 (名前が異なる) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2432e-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="2432e-108">次に、キーワード クエリまたは日付範囲を変更して新しい検索を編集し、実行できます。</span><span class="sxs-lookup"><span data-stu-id="2432e-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="2432e-109">コンテンツ検索を複製する理由</span><span class="sxs-lookup"><span data-stu-id="2432e-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="2432e-110">異なるキーワード検索クエリの結果を比較するには、同じコンテンツの場所で実行します。</span><span class="sxs-lookup"><span data-stu-id="2432e-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="2432e-111">新しい検索を作成するときに多数のコンテンツの場所を再入力する必要が生じなさる場合。</span><span class="sxs-lookup"><span data-stu-id="2432e-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="2432e-112">検索結果のサイズを小さくする。</span><span class="sxs-lookup"><span data-stu-id="2432e-112">To decrease the size of the search results.</span></span> <span data-ttu-id="2432e-113">たとえば、エクスポートする結果が多すぎる検索がある場合は、検索結果を複製し、日付範囲に基づいて検索条件を追加して検索結果の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="2432e-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="2432e-114">スクリプト情報</span><span class="sxs-lookup"><span data-stu-id="2432e-114">Script information</span></span>

- <span data-ttu-id="2432e-115">このトピックで説明するスクリプトを実行するには、セキュリティ &コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2432e-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="2432e-116">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2432e-116">The script includes minimal error handling.</span></span> <span data-ttu-id="2432e-117">スクリプトの主な目的は、コンテンツ検索をすばやく複製する方法です。</span><span class="sxs-lookup"><span data-stu-id="2432e-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="2432e-118">スクリプトは新しいコンテンツ検索を作成しますが、開始は行わない。</span><span class="sxs-lookup"><span data-stu-id="2432e-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="2432e-119">このスクリプトでは、複製するコンテンツ検索が電子情報開示ケースに関連付けられているかどうかを考慮します。</span><span class="sxs-lookup"><span data-stu-id="2432e-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="2432e-120">検索がケースに関連付けられている場合は、新しい検索も同じケースに関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="2432e-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="2432e-121">既存の検索がケースに関連付けされていない場合は、コンプライアンス センターの [コンテンツ検索]ページに新しい検索が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2432e-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="2432e-122">このトピックで提供されるサンプル スクリプトは、Microsoft 標準のサポート プログラムまたはサービスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2432e-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="2432e-123">サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。</span><span class="sxs-lookup"><span data-stu-id="2432e-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="2432e-124">さらに、Microsoft は、商品性、特定目的への適合性の黙示の保証を含む、一切の黙示の保証をいたしかねます。</span><span class="sxs-lookup"><span data-stu-id="2432e-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="2432e-125">本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。</span><span class="sxs-lookup"><span data-stu-id="2432e-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="2432e-126">サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。</span><span class="sxs-lookup"><span data-stu-id="2432e-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="2432e-127">手順 1: スクリプトを実行して検索を複製する</span><span class="sxs-lookup"><span data-stu-id="2432e-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="2432e-128">この手順のスクリプトでは、既存のコンテンツ検索を複製して新しいコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="2432e-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="2432e-129">このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2432e-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="2432e-130">**ユーザー資格情報**- スクリプトは、資格情報を使用して、組織のセキュリティ & コンプライアンス センターに接続Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2432e-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="2432e-131">前に述べたように、スクリプトを実行するには、セキュリティ & compCompliance Center の電子情報開示マネージャー役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2432e-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="2432e-132">**既存の検索の名前** - 複製するコンテンツ検索です。</span><span class="sxs-lookup"><span data-stu-id="2432e-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="2432e-133">**作成される** 新しい検索の名前 - この値を空白のままにすると、複製する検索の名前に基づいて、新しい検索の名前が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2432e-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="2432e-134">検索を複製するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2432e-134">To clone a search:</span></span>
  
1. <span data-ttu-id="2432e-135">ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存.ps1。たとえば、 `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2432e-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="2432e-136">[Windows PowerShellを開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="2432e-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="2432e-137">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="2432e-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="2432e-138">資格情報の入力を求めるメッセージが表示されたら、メール アドレスとパスワードを入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2432e-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="2432e-139">スクリプトの指示に従って、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2432e-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="2432e-140">各情報を入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="2432e-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="2432e-141">既存の検索の名前。</span><span class="sxs-lookup"><span data-stu-id="2432e-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="2432e-142">新しい検索の名前。</span><span class="sxs-lookup"><span data-stu-id="2432e-142">The name of the new search.</span></span>
    
    <span data-ttu-id="2432e-143">スクリプトは新しいコンテンツ検索を作成しますが、開始は行わない。</span><span class="sxs-lookup"><span data-stu-id="2432e-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="2432e-144">これにより、次の手順で検索を編集して実行できます。</span><span class="sxs-lookup"><span data-stu-id="2432e-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="2432e-145">**Get-ComplianceSearch** コマンドレットを実行するか、新しい検索がケースに関連付けられているかどうかに応じて、コンプライアンスセンターの [コンテンツ検索] または [電子情報開示] ページに移動して、新しい検索のプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2432e-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="2432e-146">手順 2: コンプライアンス センターで複製された検索を編集して実行する</span><span class="sxs-lookup"><span data-stu-id="2432e-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="2432e-147">スクリプトを実行して既存のコンテンツ検索を複製した後、次にコンプライアンス センターに移動して新しい検索を編集して実行します。</span><span class="sxs-lookup"><span data-stu-id="2432e-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="2432e-148">前に述べたように、キーワード検索クエリを変更し、検索条件を追加または削除することで、検索を編集できます。</span><span class="sxs-lookup"><span data-stu-id="2432e-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="2432e-149">詳しくは、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2432e-149">For more information, see:</span></span>
  
- [<span data-ttu-id="2432e-150">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="2432e-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="2432e-151">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="2432e-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="2432e-152">電子情報開示のケース</span><span class="sxs-lookup"><span data-stu-id="2432e-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)