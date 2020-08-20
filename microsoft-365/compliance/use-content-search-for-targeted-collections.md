---
title: コンテンツ検索を使用して対象コレクションを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: セキュリティ/コンプライアンス センターのコンテンツ&使用して対象のコレクションを実行し、アイテムが特定のメールボックスまたはサイト フォルダーに配置される。これにより、アイテムが特定のメールボックスまたはサイト フォルダーに配置されます。
ms.openlocfilehash: aa311d0f9226330d9f2d881af6dabbdc6d0a15b5
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814539"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="87fbb-103">コンテンツ検索を使用して対象コレクションを検索する</span><span class="sxs-lookup"><span data-stu-id="87fbb-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="87fbb-104">セキュリティ コンプライアンス センターのコンテンツ検索機能は、UI で Exchange メールボックスまたは SharePoint および OneDrive for Business サイト内の特定 &amp; のフォルダーを直接検索する機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="87fbb-104">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="87fbb-105">ただし、検索クエリ構文で、メールのフォルダー ID プロパティまたは*targeted collection*パス (DocumentLink) プロパティを指定して、特定のフォルダー (ターゲット コレクションと呼ばれるコレクション) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="87fbb-106">大文字と小文字が含まれるアイテムに関連するアイテムが特定のメールボックスまたはサイト フォルダーに存在すると、コンテンツ検索を使用して、対象のコレクションを実行する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="87fbb-107">この記事のスクリプトを使用すると、メールボックス フォルダーのフォルダー ID や、SharePoint と OneDrive for Business サイトのフォルダーのパス (DocumentLink) を取得できます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="87fbb-108">次に、検索クエリでフォルダー ID またはパスを使用して、フォルダーにあるアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="87fbb-109">SharePoint または OneDrive for Business サイト内のフォルダーにあるコンテンツを返すには、このトピックのスクリプトで、Path プロパティの代わりに DocumentLink 管理プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="87fbb-110">DocumentLink プロパティは、フォルダー内のすべてのコンテンツを返すのに対し、Path プロパティは一部のメディア ファイルを返さないのに対し、Path プロパティよりも堅牢です。</span><span class="sxs-lookup"><span data-stu-id="87fbb-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-use-content-search"></a><span data-ttu-id="87fbb-111">コンテンツ検索を使用する前に</span><span class="sxs-lookup"><span data-stu-id="87fbb-111">Before you use Content Search</span></span>

- <span data-ttu-id="87fbb-112">手順 1 でスクリプトを実行するには、セキュリティ コンプライアンス センターの電子情報開示マネージャー &amp; 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="87fbb-113">詳細については、「電子情報開示のアクセス許可 [を割り当てる」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="87fbb-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="87fbb-114">さらに、Exchange Online 組織でメール受信者の役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="87fbb-115">これは、手順 1 のスクリプト **に含まれる Get-MailboxFolderStatistics** コマンドレットを実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="87fbb-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="87fbb-116">既定では、メール受信者の役割は、Exchange Online の Organization Management および Recipient Management 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="87fbb-117">Exchange Online でアクセス許可を割り当てる方法の詳細については、「役割グループ [のメンバーの管理」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=692102)。</span><span class="sxs-lookup"><span data-stu-id="87fbb-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="87fbb-118">また、カスタム役割グループを作成し、その役割にメール受信者の役割を割り当て、手順 1 でスクリプトを実行する必要のあるメンバーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="87fbb-119">詳細については、「役割グループの [管理」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="87fbb-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="87fbb-120">手順 1 でスクリプトを実行するごとに、新しいリモート PowerShell セッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="87fbb-121">したがって、使用可能なすべてのリモート PowerShell セッションを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="87fbb-122">これを防ぐには、次のコマンドを実行してアクティブなリモート PowerShell セッションを切断できます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="87fbb-123">詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87fbb-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="87fbb-124">このスクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="87fbb-124">The script includes minimal error handling.</span></span> <span data-ttu-id="87fbb-125">このスクリプトの主な目的は、対象となるコレクションを実行するコンテンツ検索の検索クエリ構文で使用できるメールボックス フォルダー ID またはサイト パスのリストをすばやく表示することです。</span><span class="sxs-lookup"><span data-stu-id="87fbb-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="87fbb-126">このトピックで提供されているサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスの下でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="87fbb-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="87fbb-127">サンプル スクリプトは AS IS IS に用意されているので、いかに変更の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="87fbb-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="87fbb-128">さらに、Microsoft は、商品性、特定目的への適合性を含む一切の黙示の保証をいたしかねます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="87fbb-129">サンプル スクリプトおよびドキュメントの使用または実行の結果として発生するリスクはすべてお持つとおりです。</span><span class="sxs-lookup"><span data-stu-id="87fbb-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="87fbb-130">サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。</span><span class="sxs-lookup"><span data-stu-id="87fbb-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="87fbb-131">手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="87fbb-132">この最初の手順で実行するスクリプトは、メールボックス フォルダー、SharePoint および OneDrive for Business フォルダー、および各フォルダーに対応するフォルダー ID またはパスのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-132">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="87fbb-133">このスクリプトを実行すると、次の情報の入力を求めれます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="87fbb-134">**電子メール アドレスまたはサイトの URL** カシュート辞書の電子メール アドレスを入力し、Exchange メールボックス フォルダーとフォルダー ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-134">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="87fbb-135">または、指定したサイトのパスのリストを返す SharePoint サイトの URL または OneDrive for Business サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="87fbb-136">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="87fbb-136">Here are some examples:</span></span> 
    
  - <span data-ttu-id="87fbb-137">**Exchange** - stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="87fbb-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="87fbb-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="87fbb-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="87fbb-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="87fbb-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="87fbb-140">**ユーザー資格情報 -** スクリプトは、ユーザーの資格情報を使用して Exchange Online とセキュリティ コンプライアンス センターにリモート PowerShell &に接続します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-140">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="87fbb-141">前述のように、このスクリプトを正常に実行するには、適切なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-141">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="87fbb-142">メールボックス フォルダー名またはサイト ドキュメントリンク (パス) 名の一覧を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87fbb-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="87fbb-143">ファイル拡張子 .ps1 のWindows PowerShell、スクリプト ファイルに次のテキストを保存します。たとえば、 `GetFolderSearchParameters.ps1`</span><span class="sxs-lookup"><span data-stu-id="87fbb-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if (!$credentials)
   {
      $credentials = Get-Credential
   }
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. <span data-ttu-id="87fbb-144">ローカル コンピューターで、ファイルWindows PowerShell開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="87fbb-145">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="87fbb-145">Run the script; for example:</span></span>
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="87fbb-146">スクリプトが入力を求められた情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="87fbb-147">スクリプトは、指定されたユーザーのメールボックス フォルダーまたはサイト フォルダーのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-147">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="87fbb-148">フォルダー ID または documentlink 名をコピーして、手順 2 で検索クエリに貼り付けることができるように、このウィンドウを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="87fbb-148">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="87fbb-149">コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキスト ファイルに移行する場合は、その出力を再実行できます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="87fbb-150">このファイルは、スクリプトが置かされたフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="87fbb-151">たとえば、スクリプトの出力をテキスト ファイルにリダイレクトするには、手順 3 で次のコマンドを  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 実行します。その後、フォルダー ID または documentlink をファイルからコピーして、検索クエリで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="87fbb-152">メールボックス フォルダーのスクリプト出力</span><span class="sxs-lookup"><span data-stu-id="87fbb-152">Script output for mailbox folders</span></span>

<span data-ttu-id="87fbb-153">メールボックス フォルダー ID を取得する場合、スクリプトはリモート PowerShell を使用して Exchange Online に接続し **、Get-MailboxFolderStatisics** コマンドレットを実行し、指定したメールボックスのフォルダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="87fbb-154">メールボックス内のすべてのフォルダーについて、スクリプトは FolderPath 列にフォルダーの名前 **を、フォルダー** ID を **FolderQuery 列に表示** します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="87fbb-155">さらに、スクリプトは **folderId** のプレフィックス (メールボックス プロパティの名前) をフォルダー ID に追加します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="87fbb-156">**folderid プロパティは検索**可能なプロパティなので、手順 2 の `folderid:<folderid>` 検索クエリでそのフォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="87fbb-157">スクリプトによって表示されるメールボックス フォルダーの最大数は 100 です。</span><span class="sxs-lookup"><span data-stu-id="87fbb-157">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87fbb-158">この記事のスクリプトには **、Get-MailboxFolderStatistics** によって返される 64 文字フォルダー ID 値を、検索用にインデックスが作成される同じ 48 文字形式に変換するエンコード ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87fbb-158">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="87fbb-159">PowerShell で **Get-MailboxFolderStatistics** コマンドレットを実行して (この記事のスクリプトを実行する代わりに) フォルダー ID を取得する場合、そのフォルダー ID 値を使用する検索クエリは失敗します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-159">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="87fbb-160">コンテンツ検索で使用できる正しい形式のフォルダー ID を取得するには、スクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-160">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="87fbb-161">次に、メールボックス フォルダーのスクリプトによって返される出力の例を示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-161">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![スクリプトによって返されるメールボックス フォルダーおよびフォルダー ID のリストの例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="87fbb-163">手順 2 の例では、ユーザーの回復可能なアイテム フォルダー内の Purges サブフォルダーを検索するために使用するクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-163">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="87fbb-164">サイト フォルダーのスクリプト出力</span><span class="sxs-lookup"><span data-stu-id="87fbb-164">Script output for site folders</span></span>

<span data-ttu-id="87fbb-165">SharePoint または OneDrive for Business のサイト **から documentlink** プロパティのパスを取得している場合、このスクリプトは、リモート PowerShell を使用してセキュリティ & コンプライアンス センターに接続し、サイトでフォルダーを検索する新しいコンテンツ検索を作成し、指定したサイトにあるフォルダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-165">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="87fbb-166">このスクリプトは各フォルダの名前を表示し **、documentlink** のプレフィックスをフォルダーの URL に追加します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-166">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="87fbb-167">**documentlink プロパティは検索**可能なプロパティであるため、手順 2 の検索クエリでは `documentlink:<path>` property:value のペアを使用して、そのフォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-167">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="87fbb-168">最大 200 個のサイト フォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-168">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="87fbb-169">サイト フォルダーが 200 を超える場合は、最新のフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-169">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="87fbb-170">サイト フォルダーのスクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-170">Here's an example of the output returned by the script for site folders.</span></span>
  
![スクリプトによって返されるサイト フォルダーの documentlink 名のリストの例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="87fbb-172">手順 2: フォルダー ID または documentlink を使用して対象コレクションを実行する</span><span class="sxs-lookup"><span data-stu-id="87fbb-172">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="87fbb-173">特定のユーザーのフォルダー ID または documentlink のリストを収集するスクリプトを実行したら、次の手順でセキュリティ & コンプライアンス センターに移動し、特定のフォルダーを検索する新しいコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-173">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="87fbb-174">また、プロパティとプロパティのペアは、[コンテンツ検索] キーワード ボックスで構成 `folderid:<folderid>` `documentlink:<path>` した検索クエリ内 (**または、New-ComplianceSearch**コマンドレットを*使用する場合は ContentMatchQuery*パラメーターの値として) 使用します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-174">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="87fbb-175">またはプロパティは、他  `folderid` の  `documentlink` 検索パラメーターまたは検索条件と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-175">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="87fbb-176">クエリにだけ、または  `folderid` プロパティ  `documentlink` を含めると、指定したフォルダーに存在するすべてのアイテムが検索によって返されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-176">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="87fbb-177">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-177">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="87fbb-178">手順 1 でスクリプトを実行するために使用したアカウントと資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="87fbb-178">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="87fbb-179">セキュリティ/コンプライアンス センターの左側のウィンドウで &、[コンテンツ検索]、[ **コンテンツ検索** \> **]、新**しい [追加] アイコン **の下の** ![ ボタンをクリックします ](../media/O365-MDM-CreatePolicy-AddIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="87fbb-179">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="87fbb-180">**[新規検索]** ページで、コンテンツ検索の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-180">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="87fbb-181">この名前は、組織内で固有である必要があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-181">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="87fbb-182">確認 **する場所で、メールボックス**フォルダーとサイト フォルダーの検索に応じて、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-182">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="87fbb-183">[ **特定のメールボックスを選択して検索** し、手順 1 のスクリプトを実行して、指定したのメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-183">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="87fbb-184">または</span><span class="sxs-lookup"><span data-stu-id="87fbb-184">Or</span></span>
    
    - <span data-ttu-id="87fbb-185">[ **検索する特定のサイトを選択** ] をクリックし、手順 1. のスクリプトを実行して実行したのと同じサイト URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-185">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="87fbb-186">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87fbb-186">Click **Next**.</span></span>
    
7. <span data-ttu-id="87fbb-187">ページを検索する対象の [ **いいえ] のキーワード ボックスに、** 手順 1 のスクリプトによって返された  `folderid:<folderid>`  `documentlink:<path>` 値または値を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-187">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="87fbb-188">たとえば、次のスクリーンショットのクエリでは、ユーザーの回復可能なアイテム フォルダー内の Purges サブフォルダーにあるアイテムが検索されます (手順 `folderid` 1 のスクリーンショットに、Purges サブフォルダーのプロパティ値が示されています)。</span><span class="sxs-lookup"><span data-stu-id="87fbb-188">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![検索クエリのキーワード ボックスにフォルダー ID またはドキュメントのリンクを貼り付ける](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="87fbb-190">[ **検索]** をクリックして、対象とするコレクションの検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-190">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="87fbb-191">ターゲット コレクションの検索クエリの例</span><span class="sxs-lookup"><span data-stu-id="87fbb-191">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="87fbb-192">検索クエリでプロパティを使用して対象  `folderid`  `documentlink` コレクションを実行する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-192">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="87fbb-193">プレースホルダーは、スペースの節約に使用  `folderid:<folderid>` され、  `documentlink:<path>` スペースを節約するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-193">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="87fbb-194">この例では、3 つの異なるメールボックス フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-194">This example searches three different mailbox folders.</span></span> <span data-ttu-id="87fbb-195">同様のクエリ構文を使用して、ユーザーの回復可能なアイテム フォルダー内の隠しフォルダーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-195">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="87fbb-196">この例では、メールボックス フォルダー内で完全に一致する語句が含まれるアイテムを検索します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-196">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="87fbb-197">この例では、サイト フォルダー (および任意のサブフォルダー) で、タイトルに "NDA" という文字が含まれるドキュメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-197">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="87fbb-198">この例では、サイト フォルダー (およびその他のサブフォルダー) で、日付範囲内に変更が行われていた文書を検索します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-198">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="87fbb-199">詳細情報</span><span class="sxs-lookup"><span data-stu-id="87fbb-199">More information</span></span>

<span data-ttu-id="87fbb-200">この記事のスクリプトを使用して対象のコレクションを実行する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="87fbb-200">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="87fbb-201">スクリプトは、結果からフォルダーを削除しません。</span><span class="sxs-lookup"><span data-stu-id="87fbb-201">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="87fbb-202">そのため、結果に一覧表示されるフォルダーにはシステム生成されたコンテンツが含まれているため、検索不可能になる (アイテムがゼロである) 場合があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-202">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="87fbb-203">このスクリプトは、ユーザーのプライマリ メールボックスのフォルダー情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="87fbb-203">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="87fbb-204">ユーザーのアーカイブ メールボックス内のフォルダーに関する情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="87fbb-204">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="87fbb-205">メールボックスのフォルダーを検索するときには、指定したフォルダーだけが検索され、  `folderid` サブフォルダーは検索されません。</span><span class="sxs-lookup"><span data-stu-id="87fbb-205">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="87fbb-206">サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="87fbb-206">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="87fbb-207">サイト フォルダーを検索する場合は、(プロパティで識別  `documentlink` される) フォルダとすべてのサブフォルダが検索されます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-207">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="87fbb-208">検索クエリでしか指定した検索の結果をエクスポートする際に、最初のエクスポート オプション [認識されない形式のアイテムを含む、暗号化されているアイテムを含む、または他の理由でインデックスが作成され `folderid` なけないアイテムを含む) を選択できます。」を選択できます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-208">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="87fbb-209">フォルダー ID には常にインデックスが作成されているため、フォルダー内のすべてのアイテムがそのインデックス作成状態に関係なく、常にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="87fbb-209">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
