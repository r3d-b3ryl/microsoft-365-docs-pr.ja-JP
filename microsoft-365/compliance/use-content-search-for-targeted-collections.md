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
description: Microsoft 365 コンプライアンスセンターのコンテンツ検索を使用して対象のコレクションを実行します。これにより、アイテムは特定のメールボックスまたはサイトフォルダーに格納されます。
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376594"
---
# <a name="use-content-search-for-targeted-collections"></a>コンテンツ検索を使用して対象コレクションを検索する

Microsoft 365 コンプライアンスセンターのコンテンツ検索機能では、Exchange メールボックスまたは SharePoint および OneDrive for business サイトの特定のフォルダーを検索するための直接 UI を使用することはできません。 ただし、実際の検索クエリ構文で、サイトの email または path (DocumentLink) プロパティを指定して、特定のフォルダー ( *対象のコレクション* と呼ばれる) を検索することができます。 コンテンツ検索を使用して対象のコレクションを実行することは、特定のメールボックスまたはサイトフォルダーに、訴訟や権限のあるアイテムに応答するアイテムがあることを確信する場合に役立ちます。 この記事に記載されているスクリプトを使用して、SharePoint および OneDrive for business サイト上のフォルダーのメールボックスフォルダーのフォルダー ID またはパス (DocumentLink) を取得することができます。 その後、検索クエリでフォルダー ID またはパスを使用して、フォルダー内にあるアイテムを返すことができます。

> [!NOTE]
> SharePoint または OneDrive for Business サイト内のフォルダーにあるコンテンツを返すには、このトピックのスクリプトで Path プロパティの代わりに DocumentLink 管理プロパティを使用します。 DocumentLink プロパティは、フォルダー内のすべてのコンテンツを返すので、Path プロパティよりも堅牢ですが、Path プロパティはいくつかのメディアファイルを返すわけではありません。

## <a name="before-you-run-a-targeted-collection"></a>対象となるコレクションを実行する前に

- 手順1でスクリプトを実行するには、セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 詳細については、「 [電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。

    さらに、Exchange Online 組織内のメール受信者の役割を割り当てる必要があります。 これは、スクリプトに含まれている **get-mailboxfolderstatistics** コマンドレットを実行するために必要です。 既定では、メール受信者の役割は、Exchange Online の [組織の管理] および [受信者の管理] 役割グループに割り当てられます。 Exchange Online でのアクセス許可の割り当ての詳細については、「 [役割グループのメンバーの管理](https://go.microsoft.com/fwlink/p/?linkid=692102)」を参照してください。 また、カスタム役割グループを作成し、メール受信者の役割を割り当ててから、手順1でスクリプトを実行する必要があるメンバーを追加することもできます。 詳細については、「 [役割グループの管理](https://go.microsoft.com/fwlink/p/?linkid=730688)」を参照してください。

- この記事のスクリプトは先進認証をサポートしています。 Microsoft 365 または Microsoft 365 GCC 組織の場合は、スクリプトをそのようにして使用できます。 Office 365 ドイツ組織、Microsoft 365 GCC 高組織、または Microsoft 365 DoD 組織の場合は、スクリプトを編集して正常に実行する必要があります。 具体的には、 `Connect-ExchangeOnline` Exchange Online PowerShell に接続するには、行を編集し、 *Exchangeの名前* パラメーター (および組織の種類の適切な値) を使用する必要があります。  また、この行を編集して、 `Connect-IPPSSession` *Connectionuri* および *AzureADAuthorizationEndpointUri* パラメーター (および組織の種類に応じた適切な値) を使用して、セキュリティ & コンプライアンスセンターの PowerShell に接続する必要があります。 詳細については、「 [Exchange Online powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) 」および「 [connect To Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)」の例を参照してください。

- スクリプトを実行するたびに、新しいリモート PowerShell セッションが作成されます。 これは、使用可能なすべてのリモート PowerShell セッションを使用できることを意味します。 この問題が発生しないようにするには、次のコマンドを実行して、アクティブなリモート PowerShell セッションを切断します。

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

- スクリプトには、最小限のエラー処理が含まれています。 このスクリプトの主な目的は、コンテンツ検索の検索クエリ構文で対象のコレクションを実行するために使用できるメールボックスフォルダー Id またはサイトパスの一覧をすばやく表示することです。

- このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。 このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。 さらに、Microsoft は、商品性、特定目的への適合性を含む一切の黙示の保証をいたしかねます。 サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得する

この最初の手順で実行するスクリプトは、メールボックスフォルダーまたは SharePoint と OneDrive for business フォルダーの一覧と、各フォルダーの対応するフォルダー ID またはパスを返します。 このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。
  
- [**電子メールアドレスまたはサイトの URL**]: 保管担当者の電子メールアドレスを入力して、Exchange メールボックスフォルダーとフォルダー id の一覧を返します。 または、指定したサイトのパスの一覧を返すには、SharePoint サイトまたは OneDrive for Business サイトの URL を入力します。 次に、いくつかの例を示します:

  - **Exchange**: <spam> stacig@contoso。 <spam>

  - **SharePoint**: https <span>//</span>contoso.sharepoint.com/sites/marketing 

  - **OneDrive For business**: https:<span>//</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 

- **ユーザー資格情報**: このスクリプトでは、資格情報を使用して、モダン認証を使用して Exchange Online powershell または Security & コンプライアンスセンター powershell に接続します。 前述のとおり、このスクリプトを正常に実行するには、適切なアクセス許可が割り当てられている必要があります。

メールボックスフォルダーまたはサイト documentlink (path) 名の一覧を表示するには、次のようにします。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、のように `GetFolderSearchParameters.ps1` なります。

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

2. ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。

3. スクリプトを実行します。例えば：

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. スクリプトによってプロンプトが表示される情報を入力します。

    スクリプトによって、指定したユーザーのメールボックスフォルダーまたはサイトフォルダーの一覧が表示されます。 フォルダー ID または documentlink の名前をコピーして、手順2で検索クエリに貼り付けるには、このウィンドウを開いたままにしておきます。

    > [!TIP]
    > コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキストファイルにリダイレクトすることができます。 このファイルは、スクリプトが配置されているフォルダーに保存されます。 たとえば、スクリプトの出力をテキストファイルにリダイレクトするには、手順3で次のコマンドを実行します。次に、  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` ファイルからフォルダー ID または documentlink をコピーして、検索クエリで使用できます。
  
### <a name="script-output-for-mailbox-folders"></a>メールボックスフォルダーのスクリプト出力

メールボックスフォルダー Id を取得している場合、スクリプトは Exchange Online PowerShell に接続し、 **MailboxFolderStatisics** コマンドレットを実行して、指定されたメールボックスのフォルダーの一覧を表示します。 メールボックス内のすべてのフォルダーについて、スクリプトによって、 **FolderPath** 列にフォルダーの名前と、フォルダー ID が **folderquery** 列に表示されます。 また、スクリプトは **folderId** (メールボックスプロパティの名前) のプレフィックスをフォルダー ID に追加します。 **Folderid** プロパティは検索可能なプロパティであるため、 `folderid:<folderid>` 手順2の検索クエリでそのフォルダーを検索するために使用します。 スクリプトは最大100のメールボックスフォルダーを表示します。

> [!IMPORTANT]
> この記事のスクリプトには、 **get-mailboxfolderstatistics** によって返される64文字のフォルダー Id 値を、検索用にインデックス付けされたものと同じ48文字形式に変換するためのエンコードロジックが含まれています。 PowerShell で **get-mailboxfolderstatistics** コマンドレットを実行してフォルダー id を取得した場合 (この記事のスクリプトを実行するのではなく)、そのフォルダー id 値を使用する検索クエリは失敗します。 コンテンツ検索で使用できる正しい形式のフォルダー Id を取得するには、スクリプトを実行する必要があります。
  
メールボックスフォルダーのスクリプトによって返される出力の例を次に示します。
  
![スクリプトによって返されるメールボックスフォルダーとフォルダー Id のリストの例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
手順2の例は、ユーザーの [回復可能なアイテム] フォルダー内の [削除] サブフォルダーを検索するために使用されるクエリを示しています。
  
### <a name="script-output-for-site-folders"></a>サイトフォルダーのスクリプト出力

SharePoint または OneDrive for Business サイトから **documentlink** プロパティのパスを取得している場合、スクリプトはセキュリティ & コンプライアンス PowerShell に接続し、サイトを検索する新しいコンテンツ検索を作成し、指定されたサイトにあるフォルダーの一覧を表示します。 このスクリプトは、各フォルダーの名前を表示し、" **documentlink of ドキュメント** " というプレフィックスをフォルダーの URL に追加します。 **Documentlink** プロパティは検索可能なプロパティであるため、 `documentlink:<path>` 手順2の検索クエリで [プロパティ: 値のペア] を使用して、そのフォルダーを検索します。 スクリプトには、最大200のサイトフォルダーが表示されます。 200を超えるサイトフォルダーがある場合は、最新のフォルダーが表示されます。
  
サイトフォルダーのスクリプトによって返される出力の例を次に示します。
  
![スクリプトによって返されるサイトフォルダーのドキュメントリンク名のリストの例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>手順 2: フォルダー ID または documentlink を使用して対象のコレクションを実行する

特定のユーザーのフォルダー Id またはドキュメントリンクの一覧を収集するスクリプトを実行した後、次の手順では、Microsoft 365 コンプライアンスセンターに移動し、新しいコンテンツ検索を作成して特定のフォルダーを検索します。 `folderid:<folderid>` `documentlink:<path>` コンテンツ検索キーワードボックスで構成した検索クエリで、またはプロパティ: 値のペアを使用します (または、 **new-compliancesearch** コマンドレットを使用する場合は、 *contentmatchquery* パラメーターの値として指定します)。 `folderid`または `documentlink` プロパティを他の検索パラメーターまたは検索条件と組み合わせることができます。 `folderid`またはプロパティのみを `documentlink` クエリに含める場合、検索では指定したフォルダーにあるすべてのアイテムが返されます。
  
1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) して、手順1でスクリプトの実行に使用したアカウントと資格情報を使用してサインインします。

2. コンプライアンスセンターの左側のウィンドウで、[すべてのコンテンツ検索を **表示する**] をクリックし、[  >  **Content search****新しい検索**] をクリックします。

3. [ **キーワード** ] ボックスに、 `folderid:<folderid>`  `documentlink:<path>` 手順1でスクリプトによって返された値を貼り付けます。

    たとえば、次のスクリーンショットのクエリは、ユーザーの回復可能なアイテムフォルダーのパージサブフォルダー内のアイテムを検索します ( `folderid` パージサブフォルダーのプロパティの値は、手順1のスクリーンショットに示されています)。

    ![検索クエリのキーワードボックスに folderid または documentlink を貼り付ける](../media/FolderIDSearchQuery.png)

4. [ **場所**] で [ **特定の場所** ] を選択し、[ **変更**] をクリックします。

5. メールボックスフォルダーとサイトフォルダーのどちらを検索するかに基づいて、次のいずれかの操作を行います。

    - [ **Exchange 電子メール**] の横にある [ **ユーザー、グループ、またはチームの選択** ] をクリックし、手順1でスクリプトを実行したときに指定したものと同じメールボックスを追加します。

      または

    - [ **SharePoint サイト**] の横にある [ **サイトの選択** ] をクリックし、手順1でスクリプトを実行したときに指定したものと同じサイト URL を追加します。

6. 検索するコンテンツの場所を保存したら、[ **保存 & 実行**] をクリックして、コンテンツ検索の名前を入力し、[ **保存** ] をクリックして対象となるコレクション検索を開始します。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>対象となるコレクションの検索クエリの例

ここでは、  `folderid` 検索クエリで and プロパティを使用して  `documentlink` 対象となるコレクションを実行する例をいくつか示します。 プレースホルダーは、スペースを節約するために使用され  `folderid:<folderid>`  `documentlink:<path>` ます。 
  
- この例では、3つの異なるメールボックスフォルダーを検索します。 同じようなクエリ構文を使用して、ユーザーの回復可能なアイテムフォルダー内の隠しフォルダーを検索することができます。

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- この例では、完全に一致する語句を含むアイテムをメールボックスフォルダーから検索します。

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 次の使用例は、タイトルに "NDA" という文字が含まれるドキュメントのサイトフォルダー (およびすべてのサブフォルダー) を検索します。

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- この例では、日付の範囲内で変更されたドキュメントのサイトフォルダー (およびすべてのサブフォルダー) を検索します。

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>詳細情報

この記事に記載されているスクリプトを使用して対象のコレクションを実行する場合は、次の点に注意してください。
  
- このスクリプトでは、結果からフォルダーは削除されません。 そのため、検索結果に一覧表示されるフォルダーには、システム生成コンテンツが含まれているかどうか、またはサブフォルダーのみが含まれていてメールボックスアイテムが含まれていないために検索できない、または返されないものがあります。

- このスクリプトは、ユーザーのプライマリメールボックスのフォルダー情報のみを返します。 ユーザーのアーカイブメールボックス内のフォルダーに関する情報は返されません。 ユーザーのアーカイブメールボックス内のフォルダーに関する情報を戻すには、スクリプトを編集します。 これを行うには、行 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` をに変更し、 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` 編集したスクリプトを保存して実行します。 この変更により、ユーザーのアーカイブメールボックス内のフォルダーとサブフォルダーのフォルダー Id が返されます。 アーカイブメールボックス全体を検索するには、検索クエリですべてのフォルダー ID プロパティと値のペアを演算子と接続でき `OR` ます。

- メールボックスフォルダーを検索する場合、指定されたフォルダー (そのプロパティで識別される) のみ検索されます。 `folderid` サブフォルダーは検索されません。 サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使用する必要があります。

- サイトフォルダーを検索すると、そのフォルダー (プロパティによって識別される `documentlink` ) とすべてのサブフォルダーが検索されます。 

- 検索クエリで指定したプロパティのみを使用した検索の結果をエクスポートする場合は、 `folderid` [最初のエクスポート] オプションを選択できます。「すべてのアイテム、認識できない形式のすべてのアイテム、暗号化されている、またはその他の理由でインデックスが作成されていません」というオプションがあります。 フォルダー内のすべてのアイテムは、常にインデックス作成の状態にかかわらずエクスポートされます。フォルダー ID には常にインデックスが付けられています。
