---
title: 複数のコンテンツ検索の作成、報告、削除
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
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: オンプレミスの Office 365 のセキュリティ/コンプライアンス センターにある PowerShell スクリプトを使用した検索の作成やレポートの実行など、コンテンツ &検索タスクを自動化する方法 Officeについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d748e12942fa2d634f27c04de37ccf5b3ec19297
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845899"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>複数のコンテンツ検索の作成、報告、削除

 多くの場合、探索検索を迅速に作成してレポートを作成およびレポートするプロセスは、基礎となるデータと検索の豊富性と品質について学習しようとしているときに電子情報開示と調査で重要なステップとなります。 この作業を簡単に行うために、セキュリティ & コンプライアンス センターの PowerShell には、コンテンツ検索タスクを自動化する一連のコマンドレットが用意されています。 これらのスクリプトでは、複数の検索を簡単に作成して、問題となたるデータの量を判断するために役立つ推定検索結果のレポートを実行できます。 また、スクリプトを使用して異なるバージョンの検索を作成し、それぞれの結果を比較することもできます。 これらのスクリプトは、データをすばやく効率的に識別し、次の情報を含めたく方法で役に立ちます。

## <a name="before-you-create-a-content-search"></a>コンテンツ検索を作成する前に

- このトピックで説明されているスクリプトを実行するには、セキュリティ コンプライアンス センターの電子情報開示 &マネージャー役割グループのメンバーである必要があります。

- 手順 1 で CSV ファイルに追加できる、組織内の OneDrive for Business サイトの URL のリストを収集するには、「 [組織内のすべての OneDrive の場所のリストを作成する」を参照してください](https://docs.microsoft.com/onedrive/list-onedrive-urls)。

- このトピックで作成するファイルはすべて同じフォルダーに保存してください。 これにより、スクリプトの実行が容易になり、スクリプトの実行が容易になり、スクリプトの実行が容易になり、スクリプトの実行が容易になり、スクリプトの実行が

- スクリプトには、最小限のエラー処理が含まれます。 主な目的は、複数のコンテンツ検索を迅速に作成、報告、および削除することです。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>手順 1: 実行する検索に関する情報が含まれる CSV ファイルを作成する

この手順で作成するコンマ区切り値 (CSV) ファイルには、検索するユーザーごとに 1 行があります。 ユーザーの Exchange Online メールボックス (有効になっていない場合はアーカイブ メールボックスを含む) と OneDrive for Business サイトを検索できます。 または、メールボックスまたは OneDrive for Business サイトのみを検索することもできます。 SharePoint Online 組織内の任意のサイトを検索することもできます。 手順 3 で実行するスクリプトでは、CSV ファイルの行ごとに個別に検索を実行します。

1. メモ帳を使用して、次のテキストをコピーして .txt ファイルに貼り付けます。 このファイルをローカル コンピューター上のフォルダーに保存します。 このフォルダーには、他のスクリプトも保存します。

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   ファイルの最初の行、つまりヘッダー行には、新しいコンテンツ検索を **作成するために New-ComplianceSearch** コマンドレット (手順 3 のスクリプト内) で使用するパラメーターが一覧表示されます。 各パラメーター名はコンマで区切られています。 ヘッダー行にスペースが含まれていることを確認します。 ヘッダー行の下の各行は、各検索のパラメーター値を表します。 CSV ファイル内のプレースホルダのデータは、実際のデータに必ず置き換えてください。

2. Excel で .txt ファイルを開き、次の表の情報を使用して、各検索の情報を含むファイルを編集します。

   ****

   |パラメーター|説明|
   |---|---|
   |`ExchangeLocation`|ユーザーのメールボックスの SMTP アドレス。|
   |`SharePointLocation`|ユーザーの OneDrive for Business サイトの URL または組織内の任意のサイトの URL。 OneDrive for Business サイトの URL には、次の形式を使用します ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` 。 例: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。|
   |`ContentMatchQuery`|検索に対する検索クエリ。 検索クエリの作成の詳細については、「コンテンツ検索 [のキーワード クエリと検索条件」を参照してください](keyword-queries-and-search-conditions.md)。|
   |`StartDate`|メールの場合、受信者がメッセージを受信した日付または送信された日付、または送信者によってメッセージが送信された日付。 SharePoint または OneDrive for Business のサイトにあるドキュメントの場合、ドキュメントの最終更新日または後の日付。|
   |`EndDate`|メールの場合、メッセージの日付または日付 (送信者がメッセージがユーザーによって送信された前) SharePoint または OneDrive for Business のサイトにあるドキュメントの場合、ドキュメントの最終更新日または前の日付。|
   |

3. Excel ファイルを CSV ファイルとしてローカル コンピューター上のフォルダーに保存します。 手順 3 で作成するスクリプトは、この CSV ファイルの情報を使用して検索を作成します。

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>手順 2: セキュリティ/コンプライアンス センターの PowerShell に接続する

次に、組織のセキュリティ/コンプライアンス センターの PowerShell に接続します。 詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>手順 3: スクリプトを実行して検索を作成および開始する

この手順のスクリプトにより、手順 1 で作成した CSV ファイルの各行に対して個別のコンテンツ検索が作成されます。 このスクリプトを実行すると、2 つの値の入力が求めまれます。

- **Search Group ID** - この名前は、CSV ファイルから作成された検索を簡単に整理する方法です。 作成した各検索には、検索グループ ID が付けられます。その後、番号が検索名に付けられます。 たとえば、検索グループ ID**に ContosoCase**と入力すると、**検索の名前は**ContosoCase_1、ContosoCase_2、ContosoCase_3 などになります。 **ContosoCase_2** **ContosoCase_3** 入力した名前では大文字と小文字が区別されることに注意してください。 手順 4. と手順 5. で検索グループ ID を使用する場合は、作成時と同じケースを使用する必要があります。

- **CSV ファイル** - 手順 1 で作成した CSV ファイルの名前。 完全なファイル名を使用し、.csv ファイル拡張子を必ず指定してください。たとえば、 `ContosoCase.csv`

このスクリプトを実行するには、以下の手順を実行します。

1. ファイル拡張子 .ps1 のWindows PowerShell、スクリプト ファイルに次のテキストを保存します。たとえば、 `CreateSearches.ps1` そのファイルを、他のファイルを保存したフォルダーと同じフォルダーに保存します。

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

2. 次Windows PowerShell、前の手順でスクリプトを保存したフォルダーに移動して、そのスクリプトを実行します。例えば：

   ```Powershell
   .\CreateSearches.ps1
   ```

3. 検索グループ**ID プロンプトで**検索グループ名を入力し、Enter キーを**押します**。たとえば、 `ContosoCase` この名前では大文字と小文字が区別されるため、それ以降の手順と同じ方法で入力する必要があります。

4. [ソース**CSV ファイル] で**、CSV ファイルの名前 (.csv ファイル拡張子を含む) を入力します。たとえば、 `ContosoCase.csv`

5. Enter キー **を押** して、スクリプトの実行を続行します。

   スクリプトには、検索の作成と実行の進行状況が表示されます。 スクリプトが完了すると、プロンプトに返されます。

   ![複数のコンプライアンス検索を作成するスクリプトを実行した場合の出力例](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>手順 4: スクリプトを実行して検索の予想を報告する

検索を作成したら、次の手順として、手順 3. で作成された各検索のヒット数の簡単なレポートを表示するスクリプトを実行します。 このレポートには、各検索の結果のサイズと、すべての検索のヒット数と合計サイズも含まれます。 レポート スクリプトを実行する際、検索グループ ID と CSV ファイルにレポートを保存する場合は CSV ファイル名の入力を求められたら、それが求めれます。

1. ファイル拡張子 .ps1 のWindows PowerShell、スクリプト ファイルに次のテキストを保存します。たとえば、 `SearchReport.ps1` そのファイルを、他のファイルを保存したフォルダーと同じフォルダーに保存します。

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

2. 次Windows PowerShell、前の手順でスクリプトを保存したフォルダーに移動して、そのスクリプトを実行します。例えば：

   ```Powershell
   .\SearchReport.ps1
   ```

3. 検索グループ**ID プロンプトで**検索グループ名を入力し、Enter キーを**押します**。たとえば、 `ContosoCase` この名前では大文字と小文字が区別されるため、手順 3. のスクリプトを実行した時と同じ方法で名前を入力する必要があります。

4. CSV **ファイルにレポートを保存するファイル パス (レポートを表示する場合は空白のまま) に、CSV ファイル** にレポートを保存する場合は、ファイル名の完全なファイル名 (.csv ファイル拡張子を含む) を入力します。 CSV ファイルの名前 (.csv ファイル拡張子を含む) です。 たとえば、データベースをカ  `ContosoCaseReport.csv` レント ディレクトリに保存するか、別のフォルダー  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` に保存することができます。 また、ダイアログ ボックスを表示する空白のままにしてレポートを表示できますが、レポートをファイルに保存しないでください。

5. **[Enter]** キーを押します。

   スクリプトには、検索の作成と実行の進行状況が表示されます。 スクリプトが完了すると、レポートが表示されます。

   ![検索レポートを実行して検索グループの推定値を表示する](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> 同じメールボックスまたはサイトが検索グループの複数の検索でコンテンツの場所として指定されている場合は、レポート内の (アイテム数と合計サイズの両方) 結果の合計結果が同じアイテムの結果に含まれる可能性があります。 これは、同じメール メッセージやドキュメントが検索グループ内のさまざまな検索クエリに関するクエリに一致した場合、複数回カウントされるからです。

## <a name="step-5-run-the-script-to-delete-the-searches"></a>手順 5: スクリプトを実行して検索を削除する

多数の検索を作成する可能性があるため、この最後のスクリプトは、手順 3. で作成した検索を簡単に削除できるようにするための方法です。 他のスクリプトと同様に、これも検索グループ ID の入力を求めます。 このスクリプトを実行すると、検索名に検索グループ ID が含まれます、

1. ファイル拡張子 .ps1 のWindows PowerShell、スクリプト ファイルに次のテキストを保存します。たとえば、 `DeleteSearches.ps1` そのファイルを、他のファイルを保存したフォルダーと同じフォルダーに保存します。

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

2. 次Windows PowerShell、前の手順でスクリプトを保存したフォルダーに移動して、そのスクリプトを実行します。例えば：

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. 検索グループ**ID プロンプト**で、削除する検索の検索グループ名を入力し **、Enter**キーを押します。たとえば、 `ContosoCase` この名前では大文字と小文字が区別されるため、手順 3. のスクリプトを実行した時と同じ方法で名前を入力する必要があります。

   削除された各検索の名前がスクリプトに表示されます。

   ![検索グループ内の検索を削除するスクリプトを実行する](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
