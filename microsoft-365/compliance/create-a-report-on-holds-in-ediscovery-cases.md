---
title: 電子情報開示ケースの保留リストのレポートを作成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: 電子情報開示ケースに関連付けられているすべての保留リストに関する情報を含むレポートを生成する方法について説明します。
ms.openlocfilehash: b4387434d57373f9569b6472786e8ad40de85b21
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818036"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>電子情報開示ケースの保留リストのレポートを作成する
  
この記事に記載されているスクリプトを使用すると、Office 365 または Microsoft 365 のコンプライアンスセンターで電子情報開示ケースに関連付けられているすべての保留リストに関する情報を含むレポートを、電子情報開示管理者と電子情報開示マネージャーが生成できます。 このレポートには、保留リストが関連付けられているケースの名前、保留になっているコンテンツの場所、保留がクエリベースかどうかなどの情報が含まれています。 保持されていないケースがある場合、スクリプトは、保留を行わないケースの一覧を含む追加のレポートを作成します。

レポートに含まれる情報の詳細については、「 [More information](#more-information) 」セクションを参照してください。
  
## <a name="admin-requirements-and-script-information"></a>管理者の要件とスクリプト情報

- 組織内のすべての電子情報開示ケースに関するレポートを生成するには、組織の電子情報開示管理者である必要があります。 電子情報開示マネージャーの場合、レポートには、アクセスできるケースに関する情報のみが含まれます。 EDiscovery アクセス許可の詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。
    
- この記事のスクリプトには、最小限のエラー処理が含まれています。 主な目的は、組織内の電子情報開示ケースに関連付けられている保留リストに関するレポートをすばやく作成することです。
    
- The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>手順 1: セキュリティ & コンプライアンスセンター PowerShell に接続する

最初の手順として、組織のセキュリティ & コンプライアンスセンターの PowerShell に接続します。 詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。
  
Microsoft 365 アカウントで多要素認証 (MFA) やフェデレーション認証を使用する場合、次のトピックの手順ではセキュリティ/コンプライアンス センターの PowerShell に接続できません。 代わりに、「[多要素認証を使用してセキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)」の手順を参照してください。
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>手順 2: 電子情報開示ケースに関連付けられている保留リストをレポートするスクリプトを実行する

セキュリティ & コンプライアンスセンター PowerShell に接続した後、次の手順では、組織内の電子情報開示ケースに関する情報を収集するスクリプトを作成して実行します。 
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、CaseHoldsReport.ps1 のようにします。 
    
  ```powershell
#script begin
" " 
write-host "***********************************************"
write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. 手順1で開いた Windows PowerShell セッションで、スクリプトを保存したフォルダーに移動します。 
    
3. スクリプトを実行します。例えば：

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    スクリプトは、レポートを保存するターゲットフォルダーの入力を求めるメッセージを表示します。 
    
4. レポートを保存するフォルダーの完全パス名を入力し、 **enter**キーを押します。
    
    > [!TIP]
    > スクリプトが配置されているのと同じフォルダーにレポートを保存するには、ターゲットフォルダーの入力を求めるメッセージが表示されたら、ピリオド (".") を入力します。 スクリプトが配置されているフォルダー内のサブフォルダーにレポートを保存するには、サブフォルダーの名前を入力するだけです。 
  
    このスクリプトは、組織内のすべての電子情報開示ケースに関する情報の収集を開始します。 スクリプトの実行中はレポートファイルにアクセスしないでください。 スクリプトが完了すると、Windows PowerShell セッションに確認メッセージが表示されます。 このメッセージが表示された後、手順4で指定したフォルダー内のレポートにアクセスできます。 レポートのファイル名は `CaseHoldsReport<DateTimeStamp>.csv` です。

    さらでは、このスクリプトは、保留がないケースの一覧を含むレポートも作成します。 このレポートのファイル名は `CaseswithNoHolds<DateTimeStamp>.csv` です。
    
    CaseHoldsReport.ps1 スクリプトを実行する例を次に示します。 
    
    ![CaseHoldsReport.ps1 スクリプトを実行した後の出力](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>詳細情報

この記事のスクリプトを実行したときに作成されるケース保持レポートには、各ホールドに関する以下の情報が含まれています。 前述のように、組織内のすべての保留リストに関する情報を返すには、電子情報開示管理者でなければなりません。 ケース保持の詳細については、「[電子情報開示ケース](ediscovery-cases.md)」を参照してください。
  
  - 保留の名前と、保留が関連付けられている電子情報開示ケースの名前。
    
  - 電子情報開示ケースがアクティブかクローズかを指定します。
    
  - 保留が有効であるか無効であるか。
    
  - 保留が関連付けられている電子情報開示ケースのメンバ。 ケースメンバーは、割り当てられている電子情報開示のアクセス許可に応じて、ケースを表示または管理できます。
    
  - ケースが作成された日時。
    
  - ケースがクローズされている場合は、そのケースをクローズしたユーザーと、それがクローズされた日時。
    
  - 保留中の Exchange メールボックスと SharePoint サイトの場所。
    
  - 保留がクエリベースの場合は、クエリ構文。
    
  - 保留が作成された日時と、それを作成したユーザー。
    
  - 保留が最後に変更された日時と、それを変更したユーザー。
