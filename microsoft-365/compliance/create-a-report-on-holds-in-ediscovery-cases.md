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
description: 電子情報開示ケースに関連付けられているすべての保留についての情報を含むレポートを生成する方法について説明します。
ms.openlocfilehash: 4da2b93ad9055363a5f8a7d61eff04270dfd00dc
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845869"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="c2377-103">電子情報開示ケースの保留リストのレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="c2377-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="c2377-104">この記事のスクリプトにより、電子情報開示管理者と電子情報開示管理者は、Office 365 または Microsoft 365 のコンプライアンス センターの電子情報開示ケースに関連付けられたすべての保留リストに関する情報を含むレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="c2377-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="c2377-105">レポートには、保留リストの名前、保留リストに配置されているコンテンツの場所、保留がクエリに基づいたかどうかなどの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2377-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="c2377-106">保留がなっていないケースがある場合、スクリプトは、保留リストを使用せずに追加のレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2377-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="c2377-107">レポートに [含まれる](#more-information) 情報の詳細については、詳細情報セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2377-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="c2377-108">管理者の要件とスクリプトの情報</span><span class="sxs-lookup"><span data-stu-id="c2377-108">Admin requirements and script information</span></span>

- <span data-ttu-id="c2377-109">組織内のすべての電子情報開示ケースに関するレポートを生成するには、組織内の電子情報開示管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2377-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="c2377-110">電子情報開示マネージャーは、アクセスできるケースに関する情報のみを含むドキュメントになります。</span><span class="sxs-lookup"><span data-stu-id="c2377-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="c2377-111">電子情報開示のアクセス許可の詳細については、「電子情報開示のアクセス許可を [割り当てる」を参照してください](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c2377-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="c2377-112">この記事のスクリプトには、最小限のエラー処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2377-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="c2377-113">主な目的は、組織内の電子情報開示ケースに関連付けられている保留リストに関するレポートをすばやく作成することです。</span><span class="sxs-lookup"><span data-stu-id="c2377-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="c2377-p104">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="c2377-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="c2377-119">手順 1: コンプライアンス センター PowerShell &に接続する</span><span class="sxs-lookup"><span data-stu-id="c2377-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="c2377-120">最初の手順は、組織のコンプライアンス センターの PowerShell &に接続する手順です。</span><span class="sxs-lookup"><span data-stu-id="c2377-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="c2377-121">詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2377-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="c2377-122">手順 2: スクリプトを実行して電子情報開示ケースに関連付けられた保留リストを報告する</span><span class="sxs-lookup"><span data-stu-id="c2377-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="c2377-123">セキュリティ コンプライアンス センターの & PowerShell に接続したら、次の手順として、組織の電子情報開示ケースに関する情報を収集するスクリプトを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="c2377-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="c2377-124">ファイル拡張子 .ps1 のWindows PowerShell、スクリプト ファイルに次のテキストを保存します。たとえば、「CaseHoldsReport.ps1」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c2377-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

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

2. <span data-ttu-id="c2377-125">手順 1 Windows PowerShell開いたセッションで、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2377-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="c2377-126">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="c2377-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="c2377-127">このスクリプトは、レポートの保存先のフォルダーを要求します。</span><span class="sxs-lookup"><span data-stu-id="c2377-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="c2377-128">レポートの保存先フォルダーの完全パス名を入力して、Enter キーを押 **します**。</span><span class="sxs-lookup"><span data-stu-id="c2377-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="c2377-129">レポートをスクリプトがあるフォルダーと同じフォルダーに保存するには、対象のフォルダーの入力を要求するメッセージが表示されたら、ピリオド (".") を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2377-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="c2377-130">スクリプトが置かされたフォルダー内のサブフォルダーにレポートを保存するには、サブフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2377-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="c2377-131">スクリプトは、組織内のすべての電子情報開示ケースに関する情報の収集を開始します。</span><span class="sxs-lookup"><span data-stu-id="c2377-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="c2377-132">スクリプトの実行中はレポート ファイルにアクセスしないでください。</span><span class="sxs-lookup"><span data-stu-id="c2377-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="c2377-133">スクリプトが完了すると、確認メッセージが表示され、ユーザーの Windows PowerShellされます。</span><span class="sxs-lookup"><span data-stu-id="c2377-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="c2377-134">このメッセージが表示された後、手順 4 で指定したフォルダー内のレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c2377-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="c2377-135">レポートのファイル名が表示されます `CaseHoldsReport<DateTimeStamp>.csv` 。</span><span class="sxs-lookup"><span data-stu-id="c2377-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="c2377-136">さらに、スクリプトは、保留のないケースの一覧を含むレポートも作成します。</span><span class="sxs-lookup"><span data-stu-id="c2377-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="c2377-137">このレポートのファイル名が `CaseswithNoHolds<DateTimeStamp>.csv`</span><span class="sxs-lookup"><span data-stu-id="c2377-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="c2377-138">リスト スクリプトを実行する例を次にCaseHoldsReport.ps1します。</span><span class="sxs-lookup"><span data-stu-id="c2377-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![出力は、このスクリプトを実行CaseHoldsReport.ps1出力](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="c2377-140">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c2377-140">More information</span></span>

<span data-ttu-id="c2377-141">この記事のスクリプトを実行するときに作成されるケース保留レポートには、それぞれの保留に関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2377-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="c2377-142">前述したように、組織内のすべてのホールドに関する情報を返すには、電子情報開示管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2377-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="c2377-143">ケース ホールドの詳細については、電子情報開示ケース [を参照してください](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="c2377-143">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>

- <span data-ttu-id="c2377-144">保留リストの名前と、保留が関連付けられている電子情報開示ケースの名前。</span><span class="sxs-lookup"><span data-stu-id="c2377-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="c2377-145">電子情報開示ケースがアクティブか閉じられていないか。</span><span class="sxs-lookup"><span data-stu-id="c2377-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="c2377-146">ホールドが有効であるかどうか。</span><span class="sxs-lookup"><span data-stu-id="c2377-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="c2377-147">保留が関連付けられている電子情報開示ケースのメンバー。</span><span class="sxs-lookup"><span data-stu-id="c2377-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="c2377-148">ケースのメンバーは、割り当てられている電子情報開示のアクセス許可に応じて、ケースを表示または管理できます。</span><span class="sxs-lookup"><span data-stu-id="c2377-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="c2377-149">ケースが作成された日時。</span><span class="sxs-lookup"><span data-stu-id="c2377-149">The time and date the case was created.</span></span>

- <span data-ttu-id="c2377-150">ケースが閉じられていない場合は、そのケースを閉じたユーザーと終了日付と日付を示します。</span><span class="sxs-lookup"><span data-stu-id="c2377-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="c2377-151">保留中の Exchange メールボックスと SharePoint サイトの場所。</span><span class="sxs-lookup"><span data-stu-id="c2377-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="c2377-152">保持がクエリベースの場合は、クエリ構文です。</span><span class="sxs-lookup"><span data-stu-id="c2377-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="c2377-153">保留が作成された時刻と日付と、その保留を作成したユーザー。</span><span class="sxs-lookup"><span data-stu-id="c2377-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="c2377-154">前回保留が変更された時刻と、その保留を変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="c2377-154">The time and date the hold was last changed and the person who changed it.</span></span>
