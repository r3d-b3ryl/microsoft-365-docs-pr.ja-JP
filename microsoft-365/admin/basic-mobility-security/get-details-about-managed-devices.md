---
title: 基本的なモビリティとセキュリティの管理対象デバイスに関する詳細を取得する
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
description: Windows PowerShell を使用して、組織内の基本的なモビリティおよびセキュリティ デバイスの詳細を取得します。
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228173"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="8c853-103">基本的なモビリティとセキュリティの管理対象デバイスに関する詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="8c853-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="8c853-104">この記事では、Windows PowerShell を使用して、基本的なモビリティとセキュリティ用に設定した組織内のデバイスの詳細を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c853-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="8c853-105">利用可能なデバイスの詳細の内訳は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c853-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="8c853-106">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8c853-106">**Detail**</span></span>|<span data-ttu-id="8c853-107">**PowerShell で検索する内容**</span><span class="sxs-lookup"><span data-stu-id="8c853-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="8c853-108">デバイスは基本的なモビリティとセキュリティに登録されています。</span><span class="sxs-lookup"><span data-stu-id="8c853-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="8c853-109">詳細については、「[基本的なモビリティとセキュリティを使用してモバイル デバイスを登録する](enroll-your-mobile-device.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c853-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="8c853-110"> \*isManaged*  パラメーターの値: </span><span class="sxs-lookup"><span data-stu-id="8c853-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="8c853-111">**True** = デバイスは登録されています。</span><span class="sxs-lookup"><span data-stu-id="8c853-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="8c853-112">**False** = デバイスは登録されていません。</span><span class="sxs-lookup"><span data-stu-id="8c853-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="8c853-113">デバイスはデバイス セキュリティ ポリシーに準拠しているかどうか</span><span class="sxs-lookup"><span data-stu-id="8c853-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="8c853-114">詳細については、「[デバイス セキュリティ ポリシーの作成](create-device-security-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c853-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="8c853-115"> \*isCompliant*  パラメーターの値: </span><span class="sxs-lookup"><span data-stu-id="8c853-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="8c853-116">**True**  = デバイスはポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="8c853-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="8c853-117">**False**  = デバイスはポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="8c853-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的なモビリティとセキュリティの PowerShell パラメーター":::

> [!NOTE]
> <span data-ttu-id="8c853-119">この記事のコマンドとスクリプトでは、 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) で管理されるデバイスに関する詳細情報も返されます。</span><span class="sxs-lookup"><span data-stu-id="8c853-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8c853-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="8c853-120">Before you begin</span></span>

<span data-ttu-id="8c853-121">この記事で説明されているコマンドとスクリプトを実行するために、少し設定を行う必要あります。</span><span class="sxs-lookup"><span data-stu-id="8c853-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8c853-122">手順 1: Windows PowerShell 用 Microsoft Azure Active Directory モジュールをダウンロードして、インストールする</span><span class="sxs-lookup"><span data-stu-id="8c853-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8c853-123">これらの手順の詳細については、「 [PowerShell を使用して Microsoft 365 に接続する](/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c853-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="8c853-124"> [IT プロフェッショナル向け Microsoft Online Services サインイン アシスタント RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)  に移動し、 *\*Microsoft Online Services サインイン アシスタント用にダウンロード** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c853-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="8c853-125">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c853-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="8c853-126">管理者レベルの PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c853-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="8c853-127">`Install-Module MSOnline` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="8c853-128">NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="8c853-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="8c853-129">PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="8c853-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="8c853-130">インストール後、PowerShell コマンド ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8c853-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="8c853-131">手順 2: Microsoft 365 サブスクリプションに接続する</span><span class="sxs-lookup"><span data-stu-id="8c853-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="8c853-132">Windows PowerShell 用 Microsoft Azure Active Directory モジュールで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="8c853-133">[Windows PowerShell 資格情報の要求] ダイアログ ボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力してから、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c853-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="8c853-134">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="8c853-135">手順 3: PowerShell スクリプトを実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c853-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="8c853-136">既に PowerShell スクリプトを実行できるように設定している場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="8c853-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="8c853-137">Get-MsolUserDeviceComplianceStatus.ps1 スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c853-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="8c853-138">Windows デスクトップから [ **スタート**] を選択し、「Windows PowerShell」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8c853-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="8c853-139">[Windows PowerShell] を右クリックし、 **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c853-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="8c853-140">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="8c853-141">メッセージが表示されたら、「Y」を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8c853-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="8c853-142">Get-MsolDevice コマンドレットを実行して組織内のすべてのデバイスの詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="8c853-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="8c853-143">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c853-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="8c853-144">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="8c853-145">その他の例については、「 [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c853-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="8c853-146">スクリプトを実行してデバイスの詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="8c853-146">Run a script to get device details</span></span>

<span data-ttu-id="8c853-147">最初に、コンピューターにスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="8c853-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="8c853-148">次のテキストをメモ帳にコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="8c853-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="8c853-149">ファイル拡張子 .ps1 を使用して、WindowsPowerShell スクリプト ファイルとして保存します。 たとえば、Get-MsolUserDeviceComplianceStatus.ps1 です。</span><span class="sxs-lookup"><span data-stu-id="8c853-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="8c853-150">スクリプトを実行して、単一のユーザー アカウントのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="8c853-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="8c853-151">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c853-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="8c853-152">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8c853-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="8c853-153">たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="8c853-154">次のコマンドを実行して、デバイスの詳細情報を取得するユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="8c853-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="8c853-155">この例では、bar@example.com の詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c853-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="8c853-156">次のコマンドを実行して、スクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="8c853-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="8c853-157">この情報は、Windows デスクトップに CSV ファイルとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8c853-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="8c853-158">追加のパラメーターを使用して、ファイル名と CSV のパスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8c853-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="8c853-159">スクリプトを実行して、ユーザーのグループのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="8c853-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="8c853-160">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c853-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="8c853-161">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8c853-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="8c853-162">たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c853-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="8c853-163">次のコマンドを実行して、デバイスの詳細情報を取得するグループを特定します。</span><span class="sxs-lookup"><span data-stu-id="8c853-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="8c853-164">この例では、FinanceStaff グループのユーザーの詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c853-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="8c853-165">次のコマンドを実行して、スクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="8c853-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="8c853-166">この情報は、Windows デスクトップに CSV ファイルとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="8c853-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="8c853-167">追加のパラメーターを使用して、ファイル名と CSV のパスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8c853-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c853-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8c853-168">Related topics</span></span>

[<span data-ttu-id="8c853-169">Microsoft Connect は廃止されました</span><span class="sxs-lookup"><span data-stu-id="8c853-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="8c853-170">基本的なモビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="8c853-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="8c853-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="8c853-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
