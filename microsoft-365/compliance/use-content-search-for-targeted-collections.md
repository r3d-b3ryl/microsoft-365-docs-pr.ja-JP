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
# <a name="use-content-search-for-targeted-collections"></a>コンテンツ検索を使用して対象コレクションを検索する

セキュリティ コンプライアンス センターのコンテンツ検索機能は、UI で Exchange メールボックスまたは SharePoint および OneDrive for Business サイト内の特定 &amp; のフォルダーを直接検索する機能を提供しません。 ただし、検索クエリ構文で、メールのフォルダー ID プロパティまたは*targeted collection*パス (DocumentLink) プロパティを指定して、特定のフォルダー (ターゲット コレクションと呼ばれるコレクション) を検索できます。 大文字と小文字が含まれるアイテムに関連するアイテムが特定のメールボックスまたはサイト フォルダーに存在すると、コンテンツ検索を使用して、対象のコレクションを実行する際に役立ちます。 この記事のスクリプトを使用すると、メールボックス フォルダーのフォルダー ID や、SharePoint と OneDrive for Business サイトのフォルダーのパス (DocumentLink) を取得できます。 次に、検索クエリでフォルダー ID またはパスを使用して、フォルダーにあるアイテムを返します。

> [!NOTE]
> SharePoint または OneDrive for Business サイト内のフォルダーにあるコンテンツを返すには、このトピックのスクリプトで、Path プロパティの代わりに DocumentLink 管理プロパティを使用します。 DocumentLink プロパティは、フォルダー内のすべてのコンテンツを返すのに対し、Path プロパティは一部のメディア ファイルを返さないのに対し、Path プロパティよりも堅牢です。

## <a name="before-you-use-content-search"></a>コンテンツ検索を使用する前に

- 手順 1 でスクリプトを実行するには、セキュリティ コンプライアンス センターの電子情報開示マネージャー &amp; 役割グループのメンバーである必要があります。 詳細については、「電子情報開示のアクセス許可 [を割り当てる」を参照してください](assign-ediscovery-permissions.md)。
    
    さらに、Exchange Online 組織でメール受信者の役割を割り当てられている必要があります。 これは、手順 1 のスクリプト **に含まれる Get-MailboxFolderStatistics** コマンドレットを実行するために必要です。 既定では、メール受信者の役割は、Exchange Online の Organization Management および Recipient Management 役割グループに割り当てられます。 Exchange Online でアクセス許可を割り当てる方法の詳細については、「役割グループ [のメンバーの管理」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=692102)。 また、カスタム役割グループを作成し、その役割にメール受信者の役割を割り当て、手順 1 でスクリプトを実行する必要のあるメンバーを追加することもできます。 詳細については、「役割グループの [管理」を参照してください](https://go.microsoft.com/fwlink/p/?linkid=730688)。
    
- 手順 1 でスクリプトを実行するごとに、新しいリモート PowerShell セッションが作成されます。 したがって、使用可能なすべてのリモート PowerShell セッションを使うことができます。 これを防ぐには、次のコマンドを実行してアクティブなリモート PowerShell セッションを切断できます。
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
- このスクリプトには、最小限のエラー処理が含まれています。 このスクリプトの主な目的は、対象となるコレクションを実行するコンテンツ検索の検索クエリ構文で使用できるメールボックス フォルダー ID またはサイト パスのリストをすばやく表示することです。
    
- このトピックで提供されているサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスの下でサポートされていません。 サンプル スクリプトは AS IS IS に用意されているので、いかに変更の必要はありません。 さらに、Microsoft は、商品性、特定目的への適合性を含む一切の黙示の保証をいたしかねます。 サンプル スクリプトおよびドキュメントの使用または実行の結果として発生するリスクはすべてお持つとおりです。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得します。

この最初の手順で実行するスクリプトは、メールボックス フォルダー、SharePoint および OneDrive for Business フォルダー、および各フォルダーに対応するフォルダー ID またはパスのリストを返します。 このスクリプトを実行すると、次の情報の入力を求めれます。
  
- **電子メール アドレスまたはサイトの URL** カシュート辞書の電子メール アドレスを入力し、Exchange メールボックス フォルダーとフォルダー ID の一覧を返します。 または、指定したサイトのパスのリストを返す SharePoint サイトの URL または OneDrive for Business サイトの URL を入力します。 次に、いくつかの例を示します: 
    
  - **Exchange** - stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **ユーザー資格情報 -** スクリプトは、ユーザーの資格情報を使用して Exchange Online とセキュリティ コンプライアンス センターにリモート PowerShell &に接続します。 前述のように、このスクリプトを正常に実行するには、適切なアクセス許可を割り当てる必要があります。
    
メールボックス フォルダー名またはサイト ドキュメントリンク (パス) 名の一覧を表示するには、次の操作を行います。
  
1. ファイル拡張子 .ps1 のWindows PowerShell、スクリプト ファイルに次のテキストを保存します。たとえば、 `GetFolderSearchParameters.ps1`
    
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

2. ローカル コンピューターで、ファイルWindows PowerShell開き、スクリプトを保存したフォルダーに移動します。
    
3. スクリプトを実行します。例えば：
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. スクリプトが入力を求められた情報を入力します。
    
    スクリプトは、指定されたユーザーのメールボックス フォルダーまたはサイト フォルダーのリストを表示します。 フォルダー ID または documentlink 名をコピーして、手順 2 で検索クエリに貼り付けることができるように、このウィンドウを開いたままにします。
    
    > [!TIP]
    > コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキスト ファイルに移行する場合は、その出力を再実行できます。 このファイルは、スクリプトが置かされたフォルダーに保存されます。 たとえば、スクリプトの出力をテキスト ファイルにリダイレクトするには、手順 3 で次のコマンドを  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 実行します。その後、フォルダー ID または documentlink をファイルからコピーして、検索クエリで使用することができます。
  
### <a name="script-output-for-mailbox-folders"></a>メールボックス フォルダーのスクリプト出力

メールボックス フォルダー ID を取得する場合、スクリプトはリモート PowerShell を使用して Exchange Online に接続し **、Get-MailboxFolderStatisics** コマンドレットを実行し、指定したメールボックスのフォルダーの一覧を表示します。 メールボックス内のすべてのフォルダーについて、スクリプトは FolderPath 列にフォルダーの名前 **を、フォルダー** ID を **FolderQuery 列に表示** します。 さらに、スクリプトは **folderId** のプレフィックス (メールボックス プロパティの名前) をフォルダー ID に追加します。 **folderid プロパティは検索**可能なプロパティなので、手順 2 の `folderid:<folderid>` 検索クエリでそのフォルダーを検索します。 スクリプトによって表示されるメールボックス フォルダーの最大数は 100 です。

> [!IMPORTANT]
> この記事のスクリプトには **、Get-MailboxFolderStatistics** によって返される 64 文字フォルダー ID 値を、検索用にインデックスが作成される同じ 48 文字形式に変換するエンコード ロジックが含まれています。 PowerShell で **Get-MailboxFolderStatistics** コマンドレットを実行して (この記事のスクリプトを実行する代わりに) フォルダー ID を取得する場合、そのフォルダー ID 値を使用する検索クエリは失敗します。 コンテンツ検索で使用できる正しい形式のフォルダー ID を取得するには、スクリプトを実行する必要があります。
  
次に、メールボックス フォルダーのスクリプトによって返される出力の例を示します。
  
![スクリプトによって返されるメールボックス フォルダーおよびフォルダー ID のリストの例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
手順 2 の例では、ユーザーの回復可能なアイテム フォルダー内の Purges サブフォルダーを検索するために使用するクエリを示します。
  
### <a name="script-output-for-site-folders"></a>サイト フォルダーのスクリプト出力

SharePoint または OneDrive for Business のサイト **から documentlink** プロパティのパスを取得している場合、このスクリプトは、リモート PowerShell を使用してセキュリティ & コンプライアンス センターに接続し、サイトでフォルダーを検索する新しいコンテンツ検索を作成し、指定したサイトにあるフォルダーの一覧を表示します。 このスクリプトは各フォルダの名前を表示し **、documentlink** のプレフィックスをフォルダーの URL に追加します。 **documentlink プロパティは検索**可能なプロパティであるため、手順 2 の検索クエリでは `documentlink:<path>` property:value のペアを使用して、そのフォルダーを検索します。 最大 200 個のサイト フォルダーが表示されます。 サイト フォルダーが 200 を超える場合は、最新のフォルダーが表示されます。
  
サイト フォルダーのスクリプトによって返される出力の例を次に示します。
  
![スクリプトによって返されるサイト フォルダーの documentlink 名のリストの例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>手順 2: フォルダー ID または documentlink を使用して対象コレクションを実行する

特定のユーザーのフォルダー ID または documentlink のリストを収集するスクリプトを実行したら、次の手順でセキュリティ & コンプライアンス センターに移動し、特定のフォルダーを検索する新しいコンテンツ検索を作成します。 また、プロパティとプロパティのペアは、[コンテンツ検索] キーワード ボックスで構成 `folderid:<folderid>` `documentlink:<path>` した検索クエリ内 (**または、New-ComplianceSearch**コマンドレットを*使用する場合は ContentMatchQuery*パラメーターの値として) 使用します。 またはプロパティは、他  `folderid` の  `documentlink` 検索パラメーターまたは検索条件と組み合わせることができます。 クエリにだけ、または  `folderid` プロパティ  `documentlink` を含めると、指定したフォルダーに存在するすべてのアイテムが検索によって返されます。 
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 手順 1 でスクリプトを実行するために使用したアカウントと資格情報を使用してサインインします。
    
3. セキュリティ/コンプライアンス センターの左側のウィンドウで &、[コンテンツ検索]、[ **コンテンツ検索** \> **]、新**しい [追加] アイコン **の下の** ![ ボタンをクリックします ](../media/O365-MDM-CreatePolicy-AddIcon.gif) 。
    
4. **[新規検索]** ページで、コンテンツ検索の名前を入力します。 この名前は、組織内で固有である必要があります。 
    
5. 確認 **する場所で、メールボックス**フォルダーとサイト フォルダーの検索に応じて、次のいずれかを実行します。
    
    - [ **特定のメールボックスを選択して検索** し、手順 1 のスクリプトを実行して、指定したのメールボックスを追加します。 
    
      または
    
    - [ **検索する特定のサイトを選択** ] をクリックし、手順 1. のスクリプトを実行して実行したのと同じサイト URL を追加します。 
    
6. [**次へ**] をクリックします。
    
7. ページを検索する対象の [ **いいえ] のキーワード ボックスに、** 手順 1 のスクリプトによって返された  `folderid:<folderid>`  `documentlink:<path>` 値または値を貼り付けます。 
    
    たとえば、次のスクリーンショットのクエリでは、ユーザーの回復可能なアイテム フォルダー内の Purges サブフォルダーにあるアイテムが検索されます (手順 `folderid` 1 のスクリーンショットに、Purges サブフォルダーのプロパティ値が示されています)。
    
    ![検索クエリのキーワード ボックスにフォルダー ID またはドキュメントのリンクを貼り付ける](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. [ **検索]** をクリックして、対象とするコレクションの検索を開始します。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>ターゲット コレクションの検索クエリの例

検索クエリでプロパティを使用して対象  `folderid`  `documentlink` コレクションを実行する例を次に示します。 プレースホルダーは、スペースの節約に使用  `folderid:<folderid>` され、  `documentlink:<path>` スペースを節約するために使用されます。 
  
- この例では、3 つの異なるメールボックス フォルダーを検索します。 同様のクエリ構文を使用して、ユーザーの回復可能なアイテム フォルダー内の隠しフォルダーを検索できます。
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- この例では、メールボックス フォルダー内で完全に一致する語句が含まれるアイテムを検索します。
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- この例では、サイト フォルダー (および任意のサブフォルダー) で、タイトルに "NDA" という文字が含まれるドキュメントを検索します。
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- この例では、サイト フォルダー (およびその他のサブフォルダー) で、日付範囲内に変更が行われていた文書を検索します。
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>詳細情報

この記事のスクリプトを使用して対象のコレクションを実行する場合は、次の点に注意してください。
  
- スクリプトは、結果からフォルダーを削除しません。 そのため、結果に一覧表示されるフォルダーにはシステム生成されたコンテンツが含まれているため、検索不可能になる (アイテムがゼロである) 場合があります。
    
- このスクリプトは、ユーザーのプライマリ メールボックスのフォルダー情報のみを返します。 ユーザーのアーカイブ メールボックス内のフォルダーに関する情報は返されません。
    
- メールボックスのフォルダーを検索するときには、指定したフォルダーだけが検索され、  `folderid` サブフォルダーは検索されません。 サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使う必要があります。 
    
- サイト フォルダーを検索する場合は、(プロパティで識別  `documentlink` される) フォルダとすべてのサブフォルダが検索されます。 
    
- 検索クエリでしか指定した検索の結果をエクスポートする際に、最初のエクスポート オプション [認識されない形式のアイテムを含む、暗号化されているアイテムを含む、または他の理由でインデックスが作成され `folderid` なけないアイテムを含む) を選択できます。」を選択できます。 フォルダー ID には常にインデックスが作成されているため、フォルダー内のすべてのアイテムがそのインデックス作成状態に関係なく、常にエクスポートされます。
