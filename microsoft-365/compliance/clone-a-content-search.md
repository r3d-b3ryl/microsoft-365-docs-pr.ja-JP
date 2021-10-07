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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: この記事の PowerShell スクリプトを使用して、コンプライアンス センターの既存のコンテンツ検索をすばやく複製Office 365またはMicrosoft 365。
ms.openlocfilehash: 763bd6ac49841e5b55bbbc187631ef74426d9d0a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153212"
---
# <a name="clone-a-content-search"></a>コンテンツ検索をコピーする

Office 365 または Microsoft 365 のコンプライアンス センターで、多くのメールボックスまたは SharePoint サイトと OneDrive for Business サイトを検索するコンテンツ検索を作成するには、しばらく時間がかかる場合があります。 URL を誤って入力すると、検索するサイトを指定すると、エラーが発生する可能性があります。 これらの問題を回避するには、この記事の Windows PowerShell スクリプトを使用して、既存のコンテンツ検索をすばやく複製できます。 検索を複製すると、元の検索と同じプロパティ (コンテンツの場所や検索クエリなど) を含む新しい検索 (名前が異なる) が作成されます。 次に、キーワード クエリまたは日付範囲を変更して新しい検索を編集し、実行できます。
  
コンテンツ検索を複製する理由
  
- 異なるキーワード検索クエリの結果を比較するには、同じコンテンツの場所で実行します。
    
- 新しい検索を作成するときに多数のコンテンツの場所を再入力する必要が生じなさる場合。
    
- 検索結果のサイズを小さくする。 たとえば、エクスポートする結果が多すぎる検索がある場合は、検索結果を複製し、日付範囲に基づいて検索条件を追加して検索結果の数を減らします。
  
## <a name="script-information"></a>スクリプト情報

- このトピックで説明するスクリプトを実行するには、Microsoft 365 コンプライアンス センターの電子情報開示マネージャー役割グループのメンバーである必要があります。
    
- スクリプトには、最小限のエラー処理が含まれています。 スクリプトの主な目的は、コンテンツ検索をすばやく複製する方法です。
    
- スクリプトは新しいコンテンツ検索を作成しますが、開始は行わない。
    
- このスクリプトでは、複製するコンテンツ検索が電子情報開示ケースに関連付けられているかどうかを考慮します。 検索がケースに関連付けられている場合は、新しい検索も同じケースに関連付けされます。 既存の検索がケースに関連付けされていない場合は、コンプライアンス センターの [コンテンツ検索]ページに新しい検索が表示されます。 
    
- このトピックで提供されるサンプル スクリプトは、Microsoft 標準のサポート プログラムまたはサービスではサポートされていません。 サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。 さらに、Microsoft は、商品性、特定目的への適合性の黙示の保証を含む、一切の黙示の保証をいたしかねます。 本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>手順 1: スクリプトを実行して検索を複製する

この手順のスクリプトでは、既存のコンテンツ検索を複製して新しいコンテンツ検索を作成します。 このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。
  
- **ユーザー資格情報** - スクリプトは資格情報を使用して、コンプライアンス センター PowerShell &に接続します。 前に述べたように、スクリプトを実行するには、セキュリティ & compCompliance Center の電子情報開示マネージャー役割グループのメンバーである必要があります。 
    
- **既存の検索の名前** - 複製するコンテンツ検索です。 
    
- **作成される** 新しい検索の名前 - この値を空白のままにすると、複製する検索の名前に基づいて、新しい検索の名前が作成されます。 
    
検索を複製するには、次の操作を行います。
  
1. ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存.ps1。たとえば、 `CloneSearch.ps1` .
    
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

2. [Windows PowerShellを開き、スクリプトを保存したフォルダーに移動します。
    
3. スクリプトを実行します。例えば：
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. 資格情報の入力を求めるメッセージが表示されたら、メール アドレスとパスワードを入力し **、[OK] をクリックします**。
    
5. スクリプトの指示に従って、次の情報を入力します。 各情報を入力し、Enter キーを **押します**。
    
    - 既存の検索の名前。
    
    - 新しい検索の名前。
    
    スクリプトは新しいコンテンツ検索を作成しますが、開始は行わない。 これにより、次の手順で検索を編集して実行できます。 **Get-ComplianceSearch** コマンドレットを実行するか、新しい検索がケースに関連付けられているかどうかに応じて、コンプライアンスセンターの [コンテンツ検索] または [電子情報開示] ページに移動して、新しい検索のプロパティを表示できます。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>手順 2: コンプライアンス センターで複製された検索を編集して実行する

スクリプトを実行して既存のコンテンツ検索を複製した後、次にコンプライアンス センターに移動して新しい検索を編集して実行します。 前に述べたように、キーワード検索クエリを変更し、検索条件を追加または削除することで、検索を編集できます。 詳しくは、次のトピックを参照してください。
  
- [Office 365 のコンテンツ検索](content-search.md)
    
- [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
    
- [電子情報開示のケース](./get-started-core-ediscovery.md)