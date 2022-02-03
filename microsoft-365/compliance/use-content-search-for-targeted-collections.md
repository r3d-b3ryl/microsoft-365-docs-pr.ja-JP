---
title: 対象のコレクションにコンテンツ検索を使用する
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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 特定のメールボックスまたはサイト フォルダー内Microsoft 365 コンプライアンス センターを検索する対象となるコレクションを実行するには、フォルダー内のコンテンツ検索を使用します。
ms.openlocfilehash: 9de0c562f570a3028c7a96698241ac1be06b8ec1
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321953"
---
# <a name="use-content-search-for-targeted-collections"></a>対象のコレクションにコンテンツ検索を使用する

Microsoft 365 コンプライアンス センター のコンテンツ検索ツールは、UI で Exchange メールボックスまたは SharePoint サイトおよび OneDrive for Business サイト内の特定のフォルダーを検索する直接的な方法を提供します。 ただし、実際の検索クエリ構文でサイトのメールまたはパス ( *DocumentLink) プロパティ* のフォルダー ID プロパティを指定することで、特定のフォルダー (ターゲット コレクションと呼ばれる) を検索できます。 コンテンツ検索を使用して対象のコレクションを実行すると、ケースや特権アイテムに対応するアイテムが特定のメールボックスまたはサイト フォルダーにあると確信している場合に便利です。 この記事のスクリプトを使用して、メールボックス フォルダーのフォルダー ID を取得したり、SharePoint サイトおよびサイト上のフォルダーのパス (DocumentLink) をOneDrive for Businessできます。 次に、検索クエリのフォルダー ID またはパスを使用して、フォルダー内にあるアイテムを返します。

> [!NOTE]
> SharePoint または OneDrive for Business サイトのフォルダーにあるコンテンツを返す場合、このトピックのスクリプトでは Path プロパティの代わりに DocumentLink 管理プロパティを使用します。 DocumentLink プロパティはフォルダー内のすべてのコンテンツを返すのに対し、Path プロパティは一部のメディア ファイルを返さないので、Path プロパティよりも堅牢です。

## <a name="before-you-run-a-targeted-collection"></a>対象のコレクションを実行する前に

- 手順 1 でスクリプトを実行するには、Microsoft 365 コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーである必要があります。 詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。

- また、組織でメール受信者の役割を割り当Exchange Onlineがあります。 これは、スクリプトに含まれる **Get-MailboxFolderStatistics** コマンドレットを実行するために必要です。 既定では、メール受信者の役割は、組織の [組織の管理] 役割グループと [受信者の管理] 役割グループに割りExchange Online。 アクセス許可の割り当て方法の詳細については、「Exchange Onlineグループメンバーの[管理」を参照してください](/exchange/manage-role-group-members-exchange-2013-help)。 カスタム役割グループを作成し、その役割にメール受信者の役割を割り当て、手順 1 でスクリプトを実行する必要があるメンバーを追加することもできます。 詳細については、「役割グループの [管理」を参照してください](/Exchange/permissions-exo/role-groups)。

- この記事のスクリプトは、最新の認証をサポートしています。 スクリプトは、ユーザーまたは組織のMicrosoft 365使用Microsoft 365 GCCできます。 ドイツの Office 365、Microsoft 365 GCC High 組織、または Microsoft 365 DoD 組織の場合は、スクリプトを編集して正常に実行する必要があります。 具体的には、`Connect-ExchangeOnline`行を編集し、*ExchangeEnvironmentName* パラメーター (および組織の種類に適した値) を使用して、PowerShell に接続Exchange Onlineがあります。  `Connect-IPPSSession`また、行を編集し、*ConnectionUri* パラメーターと *AzureADAuthorizationEndpointUri* パラメーター (および組織の種類に適した値) を使用して、セキュリティ & コンプライアンス センター PowerShell に接続する必要があります。 詳細については、「[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) の使用例Connect、Exchange Onlineセキュリティ Connectコンプライアンス センター [PowerShell &参照してください](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)。

- スクリプトを実行する度に、新しいリモート PowerShell セッションが作成されます。 つまり、利用可能なすべてのリモート PowerShell セッションを使いきりできます。 この問題を回避するには、次のコマンドを実行して、アクティブなリモート PowerShell セッションを切断します。

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    詳細については、「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- スクリプトには、最小限のエラー処理が含まれています。 スクリプトの主な目的は、対象となるコレクションを実行するためにコンテンツ検索の検索クエリ構文で使用できるメールボックス フォルダーの ID またはサイト パスの一覧をすばやく表示することです。

- このトピックで提供されるサンプル スクリプトは、Microsoft 標準のサポート プログラムまたはサービスではサポートされていません。 サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。 さらに、Microsoft は、商品性、特定目的への適合性の黙示の保証を含む、一切の黙示の保証をいたしかねます。 本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得する

この最初の手順で実行するスクリプトは、メールボックス フォルダーまたは SharePoint フォルダーと OneDrive for Business フォルダーの一覧、および各フォルダーの対応するフォルダー ID またはパスを返します。 このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。

- **電子メール アドレスまたはサイトの URL**: 保管担当者の電子メール アドレスを入力して、メールボックス フォルダーとExchangeの一覧を返します。 または、指定したサイトのパスSharePointリストをOneDrive for Businessサイトの URL を入力します。 次に、いくつかの例を示します:

  - **Exchange**:`stacig@contoso.onmicrosoft.com`

  - **SharePoint**:`https://contoso.sharepoint.com/sites/marketing`

  - **OneDrive for Business**:`https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com`

- **ユーザー資格情報**: スクリプトは、資格情報を使用して、最新の認証を使用Exchange Online PowerShell またはセキュリティ & コンプライアンス センター PowerShell に接続します。 前に説明したように、このスクリプトを正常に実行するには、適切なアクセス許可を割り当てる必要があります。

メールボックス フォルダーまたはサイト ドキュメントリンク (パス) 名の一覧を表示するには、

1. 次のテキストを、Windows PowerShell のファイル名サフィックスを使用して、.ps1 スクリプト ファイルに保存します`GetFolderSearchParameters.ps1`。

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Microsoft 365 compliance center.            #
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
   # Authenticate with Exchange Online and the Microsoft 365 compliance center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline -ShowBanner:$false -CommandName Get-MailboxFolderStatistics
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

2. ローカル コンピューターで、[スクリプト] Windows PowerShell開き、スクリプトを保存したフォルダーに移動します。

3. スクリプトを実行します。例えば：

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. スクリプトから求める情報を入力します。

    スクリプトは、指定したユーザーのメールボックス フォルダーまたはサイト フォルダーの一覧を表示します。 このウィンドウを開いたままにしておき、フォルダー ID またはドキュメントリンク名をコピーし、手順 2 で検索クエリに貼り付けます。

    > [!TIP]
    > コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキスト ファイルに再送できます。 このファイルは、スクリプトがあるフォルダーに保存されます。 たとえば、スクリプト出力をテキスト ファイルにリダイレクトするには、[手順 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` ] で次のコマンドを実行します。次に、検索クエリで使用するフォルダー ID またはドキュメントリンクをファイルからコピーできます。

### <a name="script-output-for-mailbox-folders"></a>メールボックス フォルダーのスクリプト出力

メールボックス フォルダーの ID を取得する場合、スクリプトは Exchange Online PowerShell に接続し、**Get-MailboxFolderStatisics** コマンドレットを実行し、指定したメールボックスのフォルダーの一覧を表示します。 メールボックス内のすべてのフォルダーに対して、スクリプトは FolderPath 列内のフォルダー名と **FolderQuery** 列のフォルダー ID **を表示** します。 さらに、スクリプトは **folderId** のプレフィックス (メールボックス プロパティの名前) をフォルダー ID に追加します。 **folderid プロパティは**`folderid:<folderid>`検索可能なプロパティなので、手順 2 の検索クエリでそのフォルダーを検索します。 このスクリプトには、最大 100 のメールボックス フォルダーが表示されます。

> [!IMPORTANT]
> この記事のスクリプトには、 **Get-MailboxFolderStatistics** によって返される 64 文字のフォルダー Id 値を、検索用にインデックス付けされた 48 文字の形式に変換するエンコード ロジックが含まれています。 **PowerShell で Get-MailboxFolderStatistics** コマンドレットを実行して、(この記事のスクリプトを実行する代わりに) フォルダー ID を取得した場合、そのフォルダー ID 値を使用する検索クエリは失敗します。 コンテンツ検索で使用できる正しい形式のフォルダー ID を取得するには、スクリプトを実行する必要があります。

メールボックス フォルダーのスクリプトによって返される出力の例を次に示します。

![スクリプトによって返されるメールボックス フォルダーとフォルダーの一覧の例。](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

手順 2 の例は、ユーザーの回復可能なアイテム フォルダー内の Purges サブフォルダーの検索に使用されるクエリを示しています。

### <a name="script-output-for-site-folders"></a>サイト フォルダーのスクリプト出力

SharePoint または OneDrive for Business サイトから **documentlink** プロパティのパスを取得する場合、スクリプトはセキュリティ & コンプライアンス PowerShell に接続し、サイトでフォルダーを検索し、指定したサイトにあるフォルダーの一覧を表示する新しいコンテンツ検索を作成します。 スクリプトは、各フォルダーの名前を表示し、 **documentlink** のプレフィックスをフォルダー URL に追加します。 **documentlink プロパティ** は`documentlink:<path>`検索可能なプロパティなので、手順 2 の検索クエリで property:value ペアを使用して、そのフォルダーを検索します。 このスクリプトには、最大 200 のサイト フォルダーが表示されます。 サイト フォルダーが 200 を超える場合は、最新のフォルダーが表示されます。

サイト フォルダーのスクリプトによって返される出力の例を次に示します。

![スクリプトによって返されるサイト フォルダーのドキュメントリンク名の一覧の例。](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>手順 2: フォルダー ID またはドキュメントリンクを使用して、対象のコレクションを実行する

スクリプトを実行して、特定のユーザーのフォルダー ID またはドキュメント リンクの一覧を収集した後、次の手順で Microsoft 365 コンプライアンス センター に移動し、特定のフォルダーを検索する新しいコンテンツ検索を作成します。 [コンテンツ検索] キーワード `folderid:<folderid>` `documentlink:<path>` ボックスで構成した検索クエリで、または property:value ペアを使用します (**または、New-ComplianceSearch** コマンドレットを使用する場合は *ContentMatchQuery* パラメーターの値として)。 or プロパティを他の  `folderid` 検索  `documentlink` パラメーターまたは検索条件と組み合わせて使用できます。 クエリに or プロパティのみを`folderid``documentlink`含める場合は、指定したフォルダー内のすべてのアイテムが検索によって返されます。

1. <https://compliance.microsoft.com>手順 1 でスクリプトの実行に使用したアカウントと資格情報を使用して、移動してサインインします。

2. コンプライアンス センターの左側のウィンドウで、[**allContent** >  検索の表示] をクリックし、[新しい検索] **をクリックします**。

3. [キーワード **] ボックス** に、手順 `folderid:<folderid>`  `documentlink:<path>/*` 1 のスクリプトから返された値または値を貼り付けます。

    たとえば、次のスクリーンショットのクエリでは、ユーザーの回復可能なアイテム フォルダーの Purges サブフォルダー内のアイテムを検索します ( `folderid` Purges サブフォルダーのプロパティの値は、手順 1 のスクリーンショットに示されています)。

    ![folderid または documentlink を検索クエリのキーワード ボックスに貼り付けます。](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > documentlink 検索では、末尾を使用する必要があります  `asterisk '/*'`。  

4. [ **場所] で、[** 特定の **場所] を選択し** 、[変更] を **クリックします**。

5. メールボックス フォルダーまたはサイト フォルダーを検索するかどうかに基づいて、次のいずれかを実行します。

    - [メールの **Exchange]** の横にある [ユーザー、グループ、またはチームの選択] をクリックし、手順 1 でスクリプトを実行した際に指定したメールボックスと同じメールボックスを追加します。

      または

    - [サイトの **SharePoint] の** 横にある  [サイトの選択] をクリックし、手順 1 でスクリプトを実行した際に指定したのと同じサイト URL を追加します。

6. 検索するコンテンツの場所を保存したら、[ファイルの保存&実行] **を** クリックし、コンテンツ検索の名前を入力し、[保存] をクリックして対象のコレクション検索を開始します。

### <a name="examples-of-search-queries-for-targeted-collections"></a>対象となるコレクションの検索クエリの例

検索クエリの and プロパティを使用して`folderid``documentlink`対象のコレクションを実行する例を次に示します。 プレースホルダーは、スペースを節約  `folderid:<folderid>` するために  `documentlink:<path>` 使用されます。

- 次の使用例は、3 つの異なるメールボックス フォルダーを検索します。 同様のクエリ構文を使用して、ユーザーの回復可能なアイテム フォルダー内の非表示のフォルダーを検索できます。

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 次の使用例は、正確な語句を含むアイテムのメールボックス フォルダーを検索します。

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 次の使用例は、サイト フォルダー (およびサブフォルダー) で、タイトルに "NDA" という文字が含まれているドキュメントを検索します。

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- 次の使用例は、日付範囲内で変更されたドキュメントのサイト フォルダー (およびサブフォルダー) を検索します。

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>詳細

この記事のスクリプトを使用して対象となるコレクションを実行する場合は、次のことを念頭に置いておきます。

- スクリプトでは、結果からフォルダーは削除されません。 そのため、結果にリストされている一部のフォルダーは、システム生成コンテンツが含まれているか、またはメールボックス アイテムではなくサブフォルダーのみを含むため、検索不能 (またはゼロアイテムを返す) 可能性があります。

- このスクリプトは、ユーザーのプライマリ メールボックスのフォルダー情報のみを返します。 ユーザーのアーカイブ メールボックス内のフォルダーに関する情報は返されません。 ユーザーのアーカイブ メールボックス内のフォルダーに関する情報を返す場合は、スクリプトを編集できます。 これを行うには、行を変更`$folderStatistics = Get-MailboxFolderStatistics $emailAddress``$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive`してから、編集したスクリプトを保存して実行します。 この変更により、ユーザーのアーカイブ メールボックス内のフォルダーとサブフォルダーのフォルダー ID が返されます。 アーカイブ メールボックス全体を検索するには、検索クエリですべてのフォルダー ID プロパティ:値 `OR` のペアを演算子と接続できます。

- メールボックス フォルダーを検索する場合、指定したフォルダー ( `folderid` プロパティによって識別される) だけが検索され、サブフォルダーは検索されません。 サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使用する必要があります。

- サイト フォルダーを検索すると、フォルダー ( `documentlink` そのプロパティで識別) とすべてのサブフォルダーが検索されます。

- 検索クエリ `folderid` でプロパティのみを指定した検索の結果をエクスポートする場合は、最初のエクスポート オプションを選択できます。"認識できない形式のアイテムを除くすべてのアイテムが暗号化されている、または他の理由でインデックスが作成されていない" を選択できます。 フォルダー ID は常にインデックス付けされますので、フォルダー内のすべてのアイテムは、インデックスの状態に関係なく常にエクスポートされます。
