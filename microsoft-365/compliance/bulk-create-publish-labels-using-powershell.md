---
title: PowerShell を使用して保持ラベルを作成および発行する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: PowerShell を使用して、Microsoft 365 コンプライアンス センターとは別に、コマンド ラインから保持ラベルを作成および発行する方法について説明します。
ms.openlocfilehash: 5b8bb7a08c9794139e840d59f9238d858e15dd4e
ms.sourcegitcommit: 2b8c3fc39a7cbd4ca35e98dca430d2470cd2c925
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47426984"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="4cb99-103">PowerShell を使用して保持ラベルを作成および発行する</span><span class="sxs-lookup"><span data-stu-id="4cb99-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="4cb99-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="4cb99-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4cb99-105">Microsoft 365 のドキュメントやメールを保持または削除するために[保持ラベル](retention.md)を使用することを決定した後で、非常に多くの、時には数百個もの保持ラベルを作成して発行することが必要であることが判明する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cb99-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="4cb99-106">大量に保持ラベルを作成する場合、Microsoft 365 コンプライアンス センターから[ファイル プラン](file-plan-manager.md)を使用して保持ラベルを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4cb99-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4cb99-107">ただし、[PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) も使用できます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="4cb99-108">この記事の情報、テンプレート ファイルと例、およびスクリプトを参考にすると、保持ラベルを一括作成し、保持ラベル ポリシーでそれらを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="4cb99-109">そのようにすると、それらの保持ラベルを[管理者とユーザーが適用する](create-apply-retention-labels.md#how-to-apply-published-retention-labels)ことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4cb99-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="4cb99-110">説明されている手順では、自動適用される保持ラベルはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4cb99-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="4cb99-111">概要:</span><span class="sxs-lookup"><span data-stu-id="4cb99-111">Overview:</span></span> 

1. <span data-ttu-id="4cb99-112">Excel で、保持ラベルのリストとそれらの保持ラベル ポリシーのリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="4cb99-113">PowerShell を使用して、それらのリストに含まれる保持ラベルと保持ラベル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="4cb99-114">免責事項</span><span class="sxs-lookup"><span data-stu-id="4cb99-114">Disclaimer</span></span>

<span data-ttu-id="4cb99-115">この記事で提供されるサンプル スクリプトは、Microsoft のいかなる標準サポート プログラムまたはサービスの下でもサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4cb99-115">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="4cb99-116">サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。</span><span class="sxs-lookup"><span data-stu-id="4cb99-116">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="4cb99-117">さらに、Microsoft は、商品性、特定目的への適合性を含む一切の黙示の保証をいたしかねます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-117">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="4cb99-118">本サンプル スクリプトおよびドキュメントの使用または性能に起因するすべてのリスクは、お客様が負うものとします。</span><span class="sxs-lookup"><span data-stu-id="4cb99-118">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="4cb99-119">サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。</span><span class="sxs-lookup"><span data-stu-id="4cb99-119">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="4cb99-120">手順 1: 保持ラベル用の .csv ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4cb99-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="4cb99-121">4 種類の異なる保持ラベルのテンプレートおよびエントリ例を含む、次のサンプル .csv ファイルをコピーして、Excel に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="4cb99-122">**[データ]** タブ \> **[区切り位置]** \> **[区切り文字]** \> **[カンマ]** \> **[標準]** の順に選択して、テキストを列に変換します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="4cb99-123">例を、実際に使用する保持ラベルと設定のエントリに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="4cb99-124">パラメーター値の詳細については、「[New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb99-124">For more information about the parameter values, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>

3. <span data-ttu-id="4cb99-125">後の手順で見つけやすい場所に、このワークシートを .csv ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="4cb99-126">例: C:\>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="4cb99-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="4cb99-127">注:</span><span class="sxs-lookup"><span data-stu-id="4cb99-127">Notes:</span></span>

- <span data-ttu-id="4cb99-p106">既に存在するものと同じ名前の保持ラベルが .csv ファイルに含まれている場合、スクリプトはその保持ラベルの作成をスキップします。重複する保持ラベルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="4cb99-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="4cb99-130">サンプル .csv ファイルで指定されている列見出しを変更したり、名前を変更したりしないでください。変更すると、スクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="4cb99-131">保持ラベル用のサンプル .csv ファイル</span><span class="sxs-lookup"><span data-stu-id="4cb99-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="4cb99-132">手順 2: 保持ラベル ポリシー用の .csv ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="4cb99-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="4cb99-133">3 種類の異なる保持ラベル ポリシーのテンプレートおよびエントリ例を含む、次のサンプル .csv ファイルをコピーして、Excel に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="4cb99-134">**[データ]** タブ \> **[区切り位置]** \> **[区切り文字]** \> **[カンマ]** \> **[標準]** の順に選択して、テキストを列に変換します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="4cb99-135">例を、実際に使用する保持ラベル ポリシーとそれらの設定のエントリに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="4cb99-136">このコマンドレットのパラメーター値の詳細については、「[New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb99-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="4cb99-137">後の手順で見つけやすい場所に、このワークシートを .csv ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="4cb99-138">例: `<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="4cb99-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="4cb99-139">注:</span><span class="sxs-lookup"><span data-stu-id="4cb99-139">Notes:</span></span>
  
- <span data-ttu-id="4cb99-p109">既に存在するものと同じ名前の保持ラベル ポリシーが .csv ファイルに含まれている場合、スクリプトはその保持ラベル ポリシーの作成をスキップします。重複する保持ラベル ポリシーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="4cb99-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="4cb99-142">サンプル .csv ファイルで指定されている列見出しを変更したり、名前を変更したりしないでください。変更すると、スクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="4cb99-143">アイテム保持ポリシー用のサンプル .csv ファイル</span><span class="sxs-lookup"><span data-stu-id="4cb99-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="4cb99-144">手順 3: PowerShell スクリプトを作成する</span><span class="sxs-lookup"><span data-stu-id="4cb99-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="4cb99-145">次の PowerShell スクリプトをコピーして、メモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="4cb99-146">ファイル名拡張子として **.ps1** を使用して、見つけやすい場所にファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="4cb99-147">例: `<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="4cb99-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="4cb99-148">注:</span><span class="sxs-lookup"><span data-stu-id="4cb99-148">Notes:</span></span>

- <span data-ttu-id="4cb99-149">このスクリプトを実行すると、前の 2 つの手順で作成した 2 つのソース ファイルを指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="4cb99-150">保持ラベルを作成するソース ファイルを指定しない場合、スクリプトは保持ラベル ポリシーの作成に進みます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="4cb99-151">保持ラベル ポリシーを作成するソース ファイルを指定しない場合、スクリプトは保持ラベルのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="4cb99-152">スクリプトを実行すると、ログ ファイルが生成されます。このファイルには、実行されたアクションと、そのアクションが成功したか失敗したかが記録されます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="4cb99-153">このログ ファイルの場所については、最後の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cb99-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="4cb99-154">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="4cb99-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="4cb99-155">手順 4: PowerShell スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="4cb99-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="4cb99-156">まず、[セキュリティ/コンプライアンス センターの PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-156">First, [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="4cb99-157">次に、保持ラベルを作成および発行するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="4cb99-158">セキュリティ/コンプライアンス センターの PowerShell セッションで、パスを入力し、その後ろに文字「`.\`」とスクリプトのファイル名を入力し、Enter キーを押してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="4cb99-159">例:</span><span class="sxs-lookup"><span data-stu-id="4cb99-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="4cb99-160">スクリプトにより、前の手順で作成した .csv ファイルの場所を要求するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4cb99-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="4cb99-161">パスを入力し、その後ろに文字「`.\`」と .csv ファイルの名前を入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="4cb99-162">たとえば、最初のプロンプトでは次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="4cb99-163">手順 5: 結果を記録したログ ファイルを確認する</span><span class="sxs-lookup"><span data-stu-id="4cb99-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="4cb99-164">スクリプトが作成したログ ファイルを使用して、結果を確認し、解決する必要があるエラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="4cb99-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="4cb99-165">ログ ファイルは次の場所にあります。ただし、サンプル ファイル名の数字は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4cb99-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


