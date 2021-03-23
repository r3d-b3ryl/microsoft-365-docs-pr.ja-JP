---
title: Basic Mobility および Security 管理対象デバイスの詳細を取得する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 組織Windows PowerShellの Basic Mobility および Security デバイスの詳細を取得するには、次の情報を使用します。
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904254"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="9887c-103">Basic Mobility および Security 管理対象デバイスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="9887c-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="9887c-104">この記事では、基本モビリティとセキュリティWindows PowerShell設定した組織内のデバイスに関する詳細を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9887c-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="9887c-105">利用可能なデバイスの詳細の内訳を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9887c-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="9887c-106">**詳細**</span><span class="sxs-lookup"><span data-stu-id="9887c-106">**Detail**</span></span>|<span data-ttu-id="9887c-107">**PowerShell で探す情報**</span><span class="sxs-lookup"><span data-stu-id="9887c-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="9887c-108">デバイスは Basic Mobility and Security に登録されています。</span><span class="sxs-lookup"><span data-stu-id="9887c-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="9887c-109">詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください。](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="9887c-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="9887c-110"> \*isManaged* パラメーターの値   は次の値です。</span><span class="sxs-lookup"><span data-stu-id="9887c-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="9887c-111">**True**= デバイスが登録されています。</span><span class="sxs-lookup"><span data-stu-id="9887c-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="9887c-112">**False**= デバイスは登録されません。</span><span class="sxs-lookup"><span data-stu-id="9887c-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="9887c-113">デバイスは、デバイスのセキュリティ ポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="9887c-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="9887c-114">詳細については、「デバイス セキュリティ [ポリシーの作成」を参照してください。](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9887c-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="9887c-115"> \*isCompliant パラメーターの値は次*   の値です。</span><span class="sxs-lookup"><span data-stu-id="9887c-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="9887c-116">**True**  = デバイスはポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="9887c-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="9887c-117">**False**  = デバイスがポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9887c-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的なモビリティとセキュリティの PowerShell パラメーター":::

>[!NOTE]
><span data-ttu-id="9887c-119">この記事のコマンドとスクリプトは、Microsoft Intune によって管理されるデバイスに関する詳細 [も返します](https://www.microsoft.com/cloud-platform/microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="9887c-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9887c-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="9887c-120">Before you begin</span></span>

<span data-ttu-id="9887c-121">この記事で説明するコマンドとスクリプトを実行するために設定する必要があるものがあります。</span><span class="sxs-lookup"><span data-stu-id="9887c-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9887c-122">手順 1: Azure Active Directory モジュールをダウンロードしてインストールします。Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9887c-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9887c-123">これらの手順の詳細については [、「Connect to Microsoft 365 with PowerShell」を参照してください](/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9887c-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="9887c-124">[IT 担当者 [向Microsoft Online Services Sign-In RTWl]](https://www.microsoft.com/download/details.aspx?id=41950)に移動し、[サインイン アシスタントのダウンロードMicrosoft Online Services    **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9887c-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="9887c-125">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9887c-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="9887c-126">管理者レベルの PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9887c-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="9887c-127">Install-Module MSOnline コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="9887c-128">NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="9887c-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="9887c-129">PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="9887c-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="9887c-130">インストール後、PowerShell コマンド ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9887c-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="9887c-131">手順 2: Microsoft 365 サブスクリプションに接続する</span><span class="sxs-lookup"><span data-stu-id="9887c-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="9887c-132">Windows Azure Active Directory モジュールで、Windows PowerShellコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="9887c-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="9887c-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="9887c-134">[資格情報Windows PowerShell] ダイアログ ボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9887c-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="9887c-135">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-135">Run the following command.</span></span>

    <span data-ttu-id="9887c-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="9887c-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="9887c-137">手順 3: PowerShell スクリプトを実行することを確認する</span><span class="sxs-lookup"><span data-stu-id="9887c-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="9887c-138">PowerShell スクリプトの実行を既に設定している場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="9887c-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="9887c-139">このスクリプトをGet-MsolUserDeviceComplianceStatus.ps1するには、PowerShell スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9887c-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="9887c-140">Windows デスクトップで 、[スタート] を **選択し**、[スタート] と入力Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9887c-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="9887c-141">[管理者] をWindows PowerShellし、[管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9887c-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="9887c-142">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-142">Run the following command.</span></span>

    <span data-ttu-id="9887c-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="9887c-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="9887c-144">プロンプトが表示されたら、「Y」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9887c-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="9887c-145">**組織のすべてのGet-MsolDeviceの詳細を表示するには、このコマンドレットを実行します。**</span><span class="sxs-lookup"><span data-stu-id="9887c-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="9887c-146">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9887c-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="9887c-147">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-147">Run the following command.</span></span>

    <span data-ttu-id="9887c-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$\_.RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="9887c-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$\_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="9887c-149">その他の例については  [、「Get-MsolDevice」を参照してください](https://go.microsoft.com/fwlink/?linkid=2157939)。</span><span class="sxs-lookup"><span data-stu-id="9887c-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="9887c-150">スクリプトを実行してデバイスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="9887c-150">Run a script to get device details</span></span>

<span data-ttu-id="9887c-151">まず、スクリプトをコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="9887c-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="9887c-152">次のテキストをコピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9887c-152">Copy and paste the following text into Notepad.</span></span>  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  return $resultObject
    

31.  }
    

33.  If ($users.Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  <span data-ttu-id="9887c-211">ファイル拡張子 .ps1 を使用Windows PowerShellスクリプト ファイルとして保存します。たとえば、Get-MsolUserDeviceComplianceStatus.ps1。</span><span class="sxs-lookup"><span data-stu-id="9887c-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="9887c-212">スクリプトを実行して、1 つのユーザー アカウントのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="9887c-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="9887c-213">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9887c-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9887c-214">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9887c-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="9887c-215">たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="9887c-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="9887c-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="9887c-217">次のコマンドを実行して、デバイスの詳細を取得するユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9887c-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="9887c-218">この例では、データの詳細を取得 bar@example.com。</span><span class="sxs-lookup"><span data-stu-id="9887c-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="9887c-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="9887c-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="9887c-220">スクリプトを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="9887c-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="9887c-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="9887c-222">この情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="9887c-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="9887c-223">追加のパラメーターを使用して、CSV のファイル名とパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9887c-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="9887c-224">スクリプトを実行して、ユーザーのグループのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="9887c-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="9887c-225">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9887c-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="9887c-226">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9887c-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="9887c-227">たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="9887c-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="9887c-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="9887c-229">次のコマンドを実行して、デバイスの詳細を取得するグループを特定します。</span><span class="sxs-lookup"><span data-stu-id="9887c-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="9887c-230">この例では、FinanceStaff グループのユーザーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="9887c-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="9887c-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" |% { Get-MsolUser -ObjectId $_.ObjectId }</span><span class="sxs-lookup"><span data-stu-id="9887c-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="9887c-232">スクリプトを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9887c-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="9887c-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="9887c-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="9887c-234">この情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="9887c-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="9887c-235">追加のパラメーターを使用して、CSV のファイル名とパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9887c-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9887c-236">関連項目</span><span class="sxs-lookup"><span data-stu-id="9887c-236">Related topics</span></span>

[<span data-ttu-id="9887c-237">Microsoft Connect が廃止されました</span><span class="sxs-lookup"><span data-stu-id="9887c-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="9887c-238">基本的なモビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="9887c-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="9887c-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="9887c-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
