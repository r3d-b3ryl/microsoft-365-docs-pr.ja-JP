---
title: OneDrive for Business &のメールボックスを検索し、コンテンツ検索を使用するユーザーの一覧を検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: この記事のコンテンツ検索とスクリプトを使用して、ユーザーのグループのメールボックスと OneDrive for Business サイトを検索します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922469"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="9d7bc-103">コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーのリストを探す</span><span class="sxs-lookup"><span data-stu-id="9d7bc-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="9d7bc-104">セキュリティ & コンプライアンス センターには、時間Windows PowerShell電子情報開示関連のタスクを自動化できるさまざまなコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="9d7bc-105">現在、セキュリティ コンプライアンス センターでコンテンツ検索を&多数の保管担当者コンテンツの場所を検索するには、時間と準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="9d7bc-106">検索を作成する前に、各 OneDrive for Business サイトの URL を収集し、各メールボックスと OneDrive for Business サイトを検索に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="9d7bc-107">今後のリリースでは、セキュリティ コンプライアンス センターで行う方が&になります。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="9d7bc-108">それまでは、この記事のスクリプトを使用して、このプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="9d7bc-109">このスクリプトでは、組織の MySite ドメインの名前 (URL の **contoso** など)、ユーザーの電子メール アドレスの一覧、新しいコンテンツ検索の名前、および使用する検索クエリを求めるメッセージが表示されます。 `https://contoso-my.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="9d7bc-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="9d7bc-110">スクリプトは、リスト内の各ユーザーの OneDrive for Business URL を取得し、指定した検索クエリを使用して、リスト内の各ユーザーのメールボックスと OneDrive for Business サイトを検索するコンテンツ検索を作成して開始します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="9d7bc-111">アクセス許可とスクリプト情報</span><span class="sxs-lookup"><span data-stu-id="9d7bc-111">Permissions and script information</span></span>

- <span data-ttu-id="9d7bc-112">手順 3 でスクリプトを実行するには、セキュリティ & コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーであり、SharePoint Online グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="9d7bc-113">手順 2 で作成したユーザーの一覧と、手順 3 のスクリプトを同じフォルダーに保存してください。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="9d7bc-114">そうすると、スクリプトの実行が容易になります。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="9d7bc-115">スクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-115">The script includes minimal error handling.</span></span> <span data-ttu-id="9d7bc-116">その主な目的は、各ユーザーのメールボックスと OneDrive for Business サイトをすばやく簡単に検索することです。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="9d7bc-p104">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="9d7bc-122">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="9d7bc-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="9d7bc-123">最初の手順は、SharePoint Online 管理シェルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="9d7bc-124">この手順ではシェルを使用する必要はありません。ただし、手順 3 で実行するスクリプトに必要な前提条件が含まれているため、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="9d7bc-125">これらの前提条件により、スクリプトは SharePoint Online と通信して OneDrive for Business サイトの URL を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="9d7bc-126">[SharePoint Online 管理シェル のセットアップ] [Windows PowerShell、](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 手順 1 と手順 2 を実行して SharePoint Online 管理シェルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="9d7bc-127">手順 2: ユーザーの一覧を生成する</span><span class="sxs-lookup"><span data-stu-id="9d7bc-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="9d7bc-128">手順 3 のスクリプトでは、ユーザーの一覧のメールボックスと OneDrive アカウントを検索するコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="9d7bc-129">テキスト ファイルに電子メール アドレスを入力するか、Windows PowerShell でコマンドを実行して電子メール アドレスの一覧を取得し、ファイルに保存できます (手順 3 でスクリプトを保存するフォルダーと同じフォルダーにあります)。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="9d7bc-130">組織内のすべてのユーザーの電子メール アドレスの一覧を取得し、それをという名前のテキスト ファイルに保存するために実行できる [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) コマンドを次に示します `Users.txt` 。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="9d7bc-131">このコマンドを実行した後、必ずファイルを開き、プロパティ名を含むヘッダーを削除します  `PrimarySmtpAddress` 。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="9d7bc-132">テキスト ファイルには、メール アドレスの一覧が含まれているだけで、それ以外は含めずにしてください。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="9d7bc-133">電子メール アドレスの一覧の前または後に空白行が表示されません。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="9d7bc-134">手順 3: スクリプトを実行して検索を作成して開始する</span><span class="sxs-lookup"><span data-stu-id="9d7bc-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="9d7bc-135">この手順でスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="9d7bc-136">スクリプトを実行する前に、この情報を準備してください。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="9d7bc-137">**ユーザー資格情報** - スクリプトは資格情報を使用して SharePoint Online にアクセスして OneDrive for Business URL を取得し、リモート PowerShell を使用してセキュリティ & コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="9d7bc-138">**MySite ドメインの名前** - MySite ドメインは、組織内のすべての OneDrive for Business サイトを含むドメインです。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="9d7bc-139">たとえば、MySite ドメインの URL が次の場合は、MySite ドメインの名前を求めるメッセージがスクリプトに表示されたら **https://contoso-my.sharepoint.com**  `contoso` 入力します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="9d7bc-140">**手順 2 のテキスト ファイル** のパス名 - 手順 2 で作成したテキスト ファイルのパス名。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="9d7bc-141">テキスト ファイルとスクリプトが同じフォルダーにある場合は、テキスト ファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="9d7bc-142">それ以外の場合は、テキスト ファイルの完全なパス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="9d7bc-143">**コンテンツ検索の名前** - スクリプトによって作成されるコンテンツ検索の名前。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="9d7bc-144">**検索クエリ** - コンテンツ検索で使用される検索クエリが作成され、実行されます。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="9d7bc-145">検索クエリの詳細については、「コンテンツ検索のキーワード クエリと [検索条件」を参照してください](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="9d7bc-146">**このスクリプトを実行するには、以下の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="9d7bc-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="9d7bc-147">ファイル名のサフィックス .ps1 をWindows PowerShellして、次のテキストをスクリプト ファイルに保存します。たとえば、 `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9d7bc-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="9d7bc-148">手順 2 でユーザーの一覧を保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="9d7bc-149">[Windows PowerShellを開き、手順 2 からスクリプトとユーザーの一覧を保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="9d7bc-150">スクリプトを開始します。例えば：</span><span class="sxs-lookup"><span data-stu-id="9d7bc-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="9d7bc-151">資格情報の入力を求めるメッセージが表示されたら、メール アドレスとパスワードを入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="9d7bc-152">スクリプトの指示に従って、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="9d7bc-153">各情報を入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="9d7bc-154">MySite ドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="9d7bc-155">ユーザーのリストを含むテキスト ファイルのパス名。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="9d7bc-156">コンテンツ検索の名前。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="9d7bc-157">検索クエリ (コンテンツの場所のすべてのアイテムを返す場合は、この空白のままにします)。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="9d7bc-158">このスクリプトは、OneDrive for Business サイトごとに URL を取得し、検索を作成して開始します。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="9d7bc-159">**Get-ComplianceSearch** コマンドレットをセキュリティ & コンプライアンス センター PowerShell で実行して検索の統計情報と結果を表示するか、セキュリティ &コンプライアンス センターの [コンテンツ検索] ページに移動して検索に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9d7bc-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>