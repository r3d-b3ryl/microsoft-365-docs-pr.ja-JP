---
title: コンテンツ検索を使用して対象コレクションを検索する
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 対象となるコレクションを実行するには、Microsoft 365 コンプライアンス センターのコンテンツ検索を使用します。これにより、アイテムが特定のメールボックスまたはサイト フォルダーに確実に格納されます。
ms.openlocfilehash: 9c549b3ae418d13b6e1aafbf0cc171c52f89e621
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423458"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="e3dbb-103">コンテンツ検索を使用して対象コレクションを検索する</span><span class="sxs-lookup"><span data-stu-id="e3dbb-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="e3dbb-104">Microsoft 365 コンプライアンス センターのコンテンツ検索機能は、EXCHANGE メールボックスまたは SharePoint および OneDrive for Business サイト内の特定のフォルダーを検索するための直接の方法を UI で提供されません。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-104">The Content Search feature in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="e3dbb-105">ただし、実際の検索クエリ構文でサイトのメールまたはパス (DocumentLink) プロパティのフォルダー ID プロパティを指定することで、特定のフォルダー (ターゲット *コレクションと呼* ばれる) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="e3dbb-106">コンテンツ検索を使用して対象のコレクションを実行すると、ケースや特権アイテムに対応するアイテムが特定のメールボックスまたはサイト フォルダーにあると確信している場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="e3dbb-107">この記事のスクリプトを使用して、SharePoint および OneDrive for Business サイト上のフォルダーのメールボックス フォルダーまたはパス (DocumentLink) のフォルダー ID を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="e3dbb-108">次に、検索クエリのフォルダー ID またはパスを使用して、フォルダー内にあるアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="e3dbb-109">SharePoint または OneDrive for Business サイト内のフォルダーにあるコンテンツを取得するには、このトピックのスクリプトで Path プロパティの代わりに DocumentLink 管理プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="e3dbb-110">DocumentLink プロパティはフォルダー内のすべてのコンテンツを返すのに対し、Path プロパティは一部のメディア ファイルを返さないので、Path プロパティよりも堅牢です。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="e3dbb-111">対象のコレクションを実行する前に</span><span class="sxs-lookup"><span data-stu-id="e3dbb-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="e3dbb-112">手順 1 でスクリプトを実行するには、セキュリティ コンプライアンス センターの電子情報開示マネージャー役割グループ&メンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="e3dbb-113">詳細については、「Assign [eDiscovery permissions 」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="e3dbb-114">さらに、Exchange Online 組織でメール受信者の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="e3dbb-115">これは、スクリプトに含まれる **Get-MailboxFolderStatistics** コマンドレットを実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="e3dbb-116">既定では、メール受信者の役割は Exchange Online の [組織の管理] 役割グループと [受信者の管理] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="e3dbb-117">Exchange Online でのアクセス許可の割り当ての詳細については、「役割グループ [メンバーの管理」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=692102)。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="e3dbb-118">カスタム役割グループを作成し、その役割にメール受信者の役割を割り当て、手順 1 でスクリプトを実行する必要があるメンバーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="e3dbb-119">詳細については、「役割グループの [管理」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="e3dbb-120">この記事のスクリプトは、最新の認証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="e3dbb-121">Microsoft 365 または Microsoft 365 GCC 組織の場合は、このスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="e3dbb-122">Office 365 ドイツの組織、Microsoft 365 GCC High 組織、または Microsoft 365 DoD 組織の場合は、スクリプトを編集して正常に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="e3dbb-123">具体的には、行を編集し `Connect-ExchangeOnline` *、ExchangeEnvironmentName* パラメーター (および組織の種類に適した値) を使用して Exchange Online PowerShell に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="e3dbb-124">また、行を編集し `Connect-IPPSSession` *、ConnectionUri* パラメーターと *AzureADAuthorizationEndpointUri* パラメーター (および組織の種類に適した値) を使用して、セキュリティ & コンプライアンス センター PowerShell に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="e3dbb-125">詳細については [、「Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) に接続する」および「コンプライアンス センター PowerShell に接続する」の [例&を参照してください](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-125">For more information, see the examples in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="e3dbb-126">スクリプトを実行する度に、新しいリモート PowerShell セッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="e3dbb-127">つまり、利用可能なすべてのリモート PowerShell セッションを使いきりできます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="e3dbb-128">この問題を回避するには、次のコマンドを実行して、アクティブなリモート PowerShell セッションを切断します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="e3dbb-129">詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-129">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e3dbb-130">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-130">The script includes minimal error handling.</span></span> <span data-ttu-id="e3dbb-131">スクリプトの主な目的は、対象となるコレクションを実行するためにコンテンツ検索の検索クエリ構文で使用できるメールボックス フォルダーの ID またはサイト パスの一覧をすばやく表示することです。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="e3dbb-132">このトピックで提供されるサンプル スクリプトは、Microsoft 標準のサポート プログラムまたはサービスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="e3dbb-133">サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="e3dbb-134">さらに、Microsoft は、商品性、特定目的への適合性の黙示の保証を含む、一切の黙示の保証をいたしかねます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="e3dbb-135">本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="e3dbb-136">サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="e3dbb-137">手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="e3dbb-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="e3dbb-138">この最初の手順で実行するスクリプトは、メールボックス フォルダーまたは SharePoint フォルダーと OneDrive for Business フォルダーの一覧、および各フォルダーの対応するフォルダー ID またはパスを返します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="e3dbb-139">このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-139">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="e3dbb-140">**電子メール アドレスまたはサイトの URL**: 保管担当者の電子メール アドレスを入力して、Exchange メールボックス フォルダーとフォルダーの ID の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="e3dbb-141">または、指定したサイトのパスの一覧を返す SharePoint サイトまたは OneDrive for Business サイトの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="e3dbb-142">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="e3dbb-142">Here are some examples:</span></span>

  - <span data-ttu-id="e3dbb-143">**Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com</span><span class="sxs-lookup"><span data-stu-id="e3dbb-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="e3dbb-144">**SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="e3dbb-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="e3dbb-145">**OneDrive for Business**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="e3dbb-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="e3dbb-146">**ユーザー資格情報**: スクリプトは、資格情報を使用して、最新の認証を使用して Exchange Online PowerShell またはセキュリティ &コンプライアンス センター PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="e3dbb-147">前に説明したように、このスクリプトを正常に実行するには、適切なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="e3dbb-148">メールボックス フォルダーまたはサイト ドキュメントリンク (パス) 名の一覧を表示するには、</span><span class="sxs-lookup"><span data-stu-id="e3dbb-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="e3dbb-149">ファイル名のサフィックス .ps1 をWindows PowerShellして、次のテキストをスクリプト ファイルに保存します。たとえば、 `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e3dbb-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
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
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
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

2. <span data-ttu-id="e3dbb-150">ローカル コンピューターで、[スクリプト] Windows PowerShell開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="e3dbb-151">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="e3dbb-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="e3dbb-152">スクリプトから求める情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="e3dbb-153">スクリプトは、指定したユーザーのメールボックス フォルダーまたはサイト フォルダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="e3dbb-154">このウィンドウを開いたままにしておき、フォルダー ID またはドキュメントリンク名をコピーし、手順 2 で検索クエリに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="e3dbb-155">コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキスト ファイルに再送できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="e3dbb-156">このファイルは、スクリプトがあるフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="e3dbb-157">たとえば、スクリプト出力をテキスト ファイルにリダイレクトするには、[手順 3:] で次のコマンドを実行します。次に、検索クエリで使用するフォルダー ID またはドキュメントリンクをファイルからコピーできます  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="e3dbb-158">メールボックス フォルダーのスクリプト出力</span><span class="sxs-lookup"><span data-stu-id="e3dbb-158">Script output for mailbox folders</span></span>

<span data-ttu-id="e3dbb-159">メールボックス フォルダーの ID を取得する場合、スクリプトは Exchange Online PowerShell に接続し **、Get-MailboxFolderStatisics** コマンドレットを実行し、指定したメールボックスのフォルダーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="e3dbb-160">メールボックス内のすべてのフォルダーに対して、スクリプトは FolderPath 列内のフォルダー名と **FolderQuery** 列のフォルダー ID **を表示** します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="e3dbb-161">さらに、スクリプトは **folderId** のプレフィックス (メールボックス プロパティの名前) をフォルダー ID に追加します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="e3dbb-162">**folderid プロパティは** 検索可能なプロパティなので、手順 2 の検索クエリでそのフォルダー `folderid:<folderid>` を検索します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="e3dbb-163">このスクリプトには、最大 100 のメールボックス フォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3dbb-164">この記事のスクリプトには **、Get-MailboxFolderStatistics** によって返される 64 文字のフォルダー Id 値を、検索用にインデックス付けされた 48 文字の形式に変換するエンコード ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="e3dbb-165">PowerShell で **Get-MailboxFolderStatistics** コマンドレットを実行して、(この記事のスクリプトを実行する代わりに) フォルダー ID を取得した場合、そのフォルダー ID 値を使用する検索クエリは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="e3dbb-166">コンテンツ検索で使用できる正しい形式のフォルダー ID を取得するには、スクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="e3dbb-167">メールボックス フォルダーのスクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-167">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![スクリプトによって返されるメールボックス フォルダーとフォルダーの一覧の例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="e3dbb-169">手順 2 の例は、ユーザーの回復可能なアイテム フォルダー内の Purges サブフォルダーの検索に使用されるクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="e3dbb-170">サイト フォルダーのスクリプト出力</span><span class="sxs-lookup"><span data-stu-id="e3dbb-170">Script output for site folders</span></span>

<span data-ttu-id="e3dbb-171">SharePoint または OneDrive for Business サイトから **documentlink** プロパティのパスを取得する場合、スクリプトはセキュリティ & コンプライアンス PowerShell に接続し、サイトでフォルダーを検索し、指定したサイトにあるフォルダーの一覧を表示する新しいコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="e3dbb-172">スクリプトは、各フォルダーの名前を表示し **、documentlink** のプレフィックスをフォルダー URL に追加します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="e3dbb-173">**documentlink プロパティ** は検索可能なプロパティなので、手順 2 の検索クエリで property:value ペアを使用して、そのフォルダー `documentlink:<path>` を検索します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="e3dbb-174">このスクリプトには、最大 200 のサイト フォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="e3dbb-175">サイト フォルダーが 200 を超える場合は、最新のフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="e3dbb-176">サイト フォルダーのスクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-176">Here's an example of the output returned by the script for site folders.</span></span>
  
![スクリプトによって返されるサイト フォルダーのドキュメントリンク名の一覧の例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="e3dbb-178">手順 2: フォルダー ID またはドキュメントリンクを使用して、対象のコレクションを実行する</span><span class="sxs-lookup"><span data-stu-id="e3dbb-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="e3dbb-179">スクリプトを実行して、特定のユーザーのフォルダー ID またはドキュメント リンクの一覧を収集した後、次に Microsoft 365 コンプライアンス センターに移動し、特定のフォルダーを検索する新しいコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="e3dbb-180">[コンテンツ検索] キーワード ボックスで構成した検索クエリで、または `folderid:<folderid>` `documentlink:<path>` property:value ペアを使用します (**または、New-ComplianceSearch** コマンドレットを使用する場合は *ContentMatchQuery* パラメーターの値として)。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="e3dbb-181">or プロパティを他  `folderid` の  `documentlink` 検索パラメーターまたは検索条件と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="e3dbb-182">クエリに or プロパティのみを含める場合は、指定したフォルダー内のすべてのアイテム  `folderid`  `documentlink` が検索によって返されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="e3dbb-183">手順 1 でスクリプトの実行に使用したアカウントと資格情報を使用して、移動して [https://compliance.microsoft.com](https://compliance.microsoft.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-183">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="e3dbb-184">コンプライアンス センターの左側のウィンドウで、[すべてのコンテンツ検索を表示する] をクリックし、[  >  新しい検索]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="e3dbb-185">[キーワード **] ボックス** に、手順 1 のスクリプトから返された値 `folderid:<folderid>`  `documentlink:<path>` または値を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="e3dbb-186">たとえば、次のスクリーンショットのクエリでは、ユーザーの回復可能なアイテム フォルダーの Purges サブフォルダー内のアイテムを検索します (Purges サブフォルダーのプロパティの値は、手順 1 のスクリーンショットに `folderid` 示されています)。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![folderid または documentlink を検索クエリのキーワード ボックスに貼り付ける](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="e3dbb-188">[ **場所] で、[** 特定の **場所] を選択し** 、[変更] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="e3dbb-189">メールボックス フォルダーまたはサイト フォルダーを検索するかどうかに基づいて、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="e3dbb-190">**[Exchange メール] の横** にある **[ユーザー** 、グループ、またはチームの選択] をクリックし、手順 1 でスクリプトを実行した際に指定したのと同じメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="e3dbb-191">または</span><span class="sxs-lookup"><span data-stu-id="e3dbb-191">Or</span></span>

    - <span data-ttu-id="e3dbb-192">**[SharePoint サイト] の横** にある [サイトの選択] をクリックし、手順 1 でスクリプトを実行した際に指定したのと同じサイト URL を追加します。 </span><span class="sxs-lookup"><span data-stu-id="e3dbb-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="e3dbb-193">検索するコンテンツの場所を保存したら、[ファイルの保存&実行]**を** クリックし、コンテンツ検索の名前を入力し、[保存] をクリックして対象のコレクション検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="e3dbb-194">対象となるコレクションの検索クエリの例</span><span class="sxs-lookup"><span data-stu-id="e3dbb-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="e3dbb-195">検索クエリの and プロパティを使用して対象のコレクションを実行する  `folderid`  `documentlink` 例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="e3dbb-196">プレースホルダーは、スペースを節約  `folderid:<folderid>` するために  `documentlink:<path>` 使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="e3dbb-197">次の使用例は、3 つの異なるメールボックス フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="e3dbb-198">同様のクエリ構文を使用して、ユーザーの回復可能なアイテム フォルダー内の非表示のフォルダーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="e3dbb-199">次の使用例は、正確な語句を含むアイテムのメールボックス フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="e3dbb-200">次の使用例は、サイト フォルダー (およびサブフォルダー) で、タイトルに "NDA" という文字が含まれているドキュメントを検索します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="e3dbb-201">次の使用例は、日付範囲内で変更されたドキュメントのサイト フォルダー (およびサブフォルダー) を検索します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="e3dbb-202">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e3dbb-202">More information</span></span>

<span data-ttu-id="e3dbb-203">この記事のスクリプトを使用して対象となるコレクションを実行する場合は、次のことを念頭に置いておきます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="e3dbb-204">スクリプトでは、結果からフォルダーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="e3dbb-205">そのため、結果にリストされている一部のフォルダーは、システム生成コンテンツが含まれているか、またはメールボックス アイテムではなくサブフォルダーのみを含むため、検索不能 (またはゼロアイテムを返す) 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="e3dbb-206">このスクリプトは、ユーザーのプライマリ メールボックスのフォルダー情報のみを返します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="e3dbb-207">ユーザーのアーカイブ メールボックス内のフォルダーに関する情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="e3dbb-208">ユーザーのアーカイブ メールボックス内のフォルダーに関する情報を返す場合は、スクリプトを編集できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="e3dbb-209">これを行うには、行を変更してから、編集 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` したスクリプトを保存して実行します。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="e3dbb-210">この変更により、ユーザーのアーカイブ メールボックス内のフォルダーとサブフォルダーのフォルダー ID が返されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="e3dbb-211">アーカイブ メールボックス全体を検索するには、検索クエリですべてのフォルダー ID プロパティ:値のペアを演算子 `OR` と接続できます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="e3dbb-212">メールボックス フォルダーを検索する場合、指定したフォルダー (プロパティによって識別される) だけが検索され、サブフォルダー `folderid` は検索されません。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="e3dbb-213">サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="e3dbb-214">サイト フォルダーを検索すると、フォルダー (そのプロパティで識別 `documentlink` ) とすべてのサブフォルダーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="e3dbb-215">検索クエリでプロパティのみを指定した検索の結果をエクスポートする場合は、最初のエクスポート オプションを選択できます。"認識できない形式のアイテムを除くすべてのアイテムが暗号化されている、または他の理由でインデックスが作成されていない" を選択できます。 `folderid`</span><span class="sxs-lookup"><span data-stu-id="e3dbb-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="e3dbb-216">フォルダー ID は常にインデックス付けされますので、フォルダー内のすべてのアイテムは、インデックスの状態に関係なく常にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="e3dbb-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
