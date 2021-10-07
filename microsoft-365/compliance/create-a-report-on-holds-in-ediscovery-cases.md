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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: 電子情報開示ケースに関連付けられているすべてのホールドに関する情報を含むレポートを生成する方法について説明します。
ms.openlocfilehash: 953b2aaa1b133d79b82f17e5f75603947cc5d6d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200571"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>電子情報開示ケースの保留リストのレポートを作成する

この記事のスクリプトを使用すると、電子情報開示管理者と電子情報開示管理者は、Office 365 または Microsoft 365 のコンプライアンス センターで電子情報開示ケースに関連付けられているすべてのホールドに関する情報を含むレポートを生成できます。 レポートには、保留リストに関連付けられているケースの名前、保留にされるコンテンツの場所、保留リストがクエリ ベースかどうかなどの情報が含まれる。 保持がないケースがある場合、スクリプトは保留のないケースの一覧を含む追加のレポートを作成します。

レポートに [含まれる情報の](#more-information) 詳細については、「詳細」セクションを参照してください。

## <a name="admin-requirements-and-script-information"></a>管理者の要件とスクリプト情報

- 組織内のすべての電子情報開示ケースに関するレポートを生成するには、組織内の電子情報開示管理者である必要があります。 電子情報開示マネージャーの場合、レポートにはアクセスできるケースに関する情報だけが含まれます。 電子情報開示のアクセス許可の詳細については、「電子情報開示の [アクセス許可を割り当てる」を参照してください](assign-ediscovery-permissions.md)。

- この記事のスクリプトのエラー処理は最小限です。 主な目的は、組織内の電子情報開示ケースに関連付けられている保留リストに関するレポートをすばやく作成します。

- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>手順 1: セキュリティ/コンプライアンス センターの PowerShell に接続する

最初の手順は、組織のセキュリティ/コンプライアンス センターの PowerShell に接続することです。 詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)」を参照してください。

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>手順 2: スクリプトを実行して、電子情報開示ケースに関連付けられた保留を報告する

セキュリティ & コンプライアンス センター PowerShell に接続した後、次の手順では、組織内の電子情報開示ケースに関する情報を収集するスクリプトを作成して実行します。

1. ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキストを保存.ps1。たとえば、CaseHoldsReport.ps1。

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

2. 手順 1 Windows PowerShell開いたセッションで、スクリプトを保存したフォルダーに移動します。

3. スクリプトを実行します。例えば：

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   スクリプトは、レポートを保存するターゲット フォルダーの入力を求めるメッセージを表示します。

4. レポートを保存するフォルダーの完全なパス名を入力し、Enter キーを **押します**。

   > [!TIP]
   > スクリプトが保存されているのと同じフォルダーにレポートを保存するには、ターゲット フォルダーの入力を求めるメッセージが表示されたら、ピリオド (".") を入力します。 スクリプトがあるフォルダー内のサブフォルダーにレポートを保存するには、サブフォルダーの名前を入力します。

   スクリプトは、組織内のすべての電子情報開示ケースに関する情報の収集を開始します。 スクリプトの実行中にレポート ファイルにアクセスしない。 スクリプトが完了すると、確認メッセージがセッションの開始Windows PowerShellされます。 このメッセージが表示された後、手順 4 で指定したフォルダー内のレポートにアクセスできます。 レポートのファイル名はです `CaseHoldsReport<DateTimeStamp>.csv` 。

   さらに、このスクリプトでは、保留リストを持つケースの一覧を含むレポートも作成されます。 このレポートのファイル名はです `CaseswithNoHolds<DateTimeStamp>.csv` 。

   次に、スクリプトを実行する例をCaseHoldsReport.ps1します。

   ![スクリプトを実行した後のCaseHoldsReport.ps1です。](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>詳細情報

このケースには、この記事のスクリプトを実行するときに作成されたレポートが保持されます。各保留に関する次の情報が含まれます。 前に説明したように、組織内のすべての保留に関する情報を返す電子情報開示管理者である必要があります。 ケースホールドの詳細については、「電子情報開示ケース [」を参照してください](./get-started-core-ediscovery.md)。

- 保留リストの名前と、保留リストが関連付けられている電子情報開示ケースの名前。

- 電子情報開示ケースがアクティブか閉じているか。

- 保留が有効か無効かを指定します。

- 保留リストが関連付けられている電子情報開示ケースのメンバー。 ケース メンバーは、割り当てられた電子情報開示のアクセス許可に応じて、ケースを表示または管理できます。

- ケースが作成された日時。

- ケースが閉じている場合、そのケースを閉じたユーザーと、そのケースを閉じた日時。

- 保留ExchangeメールボックスとSharePointサイトの場所を指定します。

- 保留リストがクエリ ベースの場合、クエリ構文。

- 保留が作成された日時と、保持を作成したユーザー。

- 保留が最後に変更された日時と、その保持を変更したユーザー。