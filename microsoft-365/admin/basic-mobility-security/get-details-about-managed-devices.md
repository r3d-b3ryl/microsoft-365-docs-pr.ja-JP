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
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904254"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="330ba-103">基本的なモビリティとセキュリティの管理対象デバイスに関する詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="330ba-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="330ba-104">この記事では、Windows PowerShell を使用して、基本的なモビリティとセキュリティ用に設定した組織内のデバイスの詳細を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="330ba-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="330ba-105">利用可能なデバイスの詳細の内訳は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="330ba-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="330ba-106">**詳細**</span><span class="sxs-lookup"><span data-stu-id="330ba-106">**Detail**</span></span>|<span data-ttu-id="330ba-107">**PowerShell で検索する内容**</span><span class="sxs-lookup"><span data-stu-id="330ba-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="330ba-108">デバイスは基本的なモビリティとセキュリティに登録されています。</span><span class="sxs-lookup"><span data-stu-id="330ba-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="330ba-109">詳細については、「[基本的なモビリティとセキュリティを使用してモバイル デバイスを登録する](enroll-your-mobile-device.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="330ba-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="330ba-110"> \*isManaged*  パラメーターの値: </span><span class="sxs-lookup"><span data-stu-id="330ba-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="330ba-111">**True** = デバイスは登録されています。</span><span class="sxs-lookup"><span data-stu-id="330ba-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="330ba-112">**False** = デバイスは登録されていません。</span><span class="sxs-lookup"><span data-stu-id="330ba-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="330ba-113">デバイスはデバイス セキュリティ ポリシーに準拠しているかどうか</span><span class="sxs-lookup"><span data-stu-id="330ba-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="330ba-114">詳細については、「[デバイス セキュリティ ポリシーの作成](create-device-security-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="330ba-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="330ba-115"> \*isCompliant*  パラメーターの値: </span><span class="sxs-lookup"><span data-stu-id="330ba-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="330ba-116">**True**  = デバイスはポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="330ba-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="330ba-117">**False**  = デバイスはポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="330ba-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的なモビリティとセキュリティの PowerShell パラメーター":::

>[!NOTE]
><span data-ttu-id="330ba-119">この記事のコマンドとスクリプトでは、 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) で管理されるデバイスに関する詳細情報も返されます。</span><span class="sxs-lookup"><span data-stu-id="330ba-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="330ba-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="330ba-120">Before you begin</span></span>

<span data-ttu-id="330ba-121">この記事で説明されているコマンドとスクリプトを実行するために、少し設定を行う必要あります。</span><span class="sxs-lookup"><span data-stu-id="330ba-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="330ba-122">手順 1: Windows PowerShell 用 Microsoft Azure Active Directory モジュールをダウンロードして、インストールする</span><span class="sxs-lookup"><span data-stu-id="330ba-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="330ba-123">これらの手順の詳細については、「 [PowerShell を使用して Microsoft 365 に接続する](/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="330ba-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="330ba-124"> [IT プロフェッショナル向け Microsoft Online Services サインイン アシスタント RTWl](https://www.microsoft.com/download/details.aspx?id=41950)  に移動し、 *\*Microsoft Online Services サインイン アシスタント用にダウンロード** を選択します。</span><span class="sxs-lookup"><span data-stu-id="330ba-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="330ba-125">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="330ba-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="330ba-126">管理者レベルの PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="330ba-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="330ba-127">Install-Module MSOnline コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="330ba-128">NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="330ba-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="330ba-129">PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="330ba-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="330ba-130">インストール後、PowerShell コマンド ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="330ba-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="330ba-131">手順 2: Microsoft 365 サブスクリプションに接続する</span><span class="sxs-lookup"><span data-stu-id="330ba-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="330ba-132">Windows PowerShell 用 Microsoft Azure Active Directory モジュールで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="330ba-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="330ba-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="330ba-134">[Windows PowerShell 資格情報の要求] ダイアログ ボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力してから、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="330ba-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="330ba-135">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-135">Run the following command.</span></span>

    <span data-ttu-id="330ba-136">Connect-MsolService -Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="330ba-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="330ba-137">手順 3: PowerShell スクリプトを実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="330ba-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="330ba-138">既に PowerShell スクリプトを実行できるように設定している場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="330ba-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="330ba-139">Get-MsolUserDeviceComplianceStatus.ps1 スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="330ba-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="330ba-140">Windows デスクトップから [ **スタート**] を選択し、「Windows PowerShell」と入力します。</span><span class="sxs-lookup"><span data-stu-id="330ba-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="330ba-141">[Windows PowerShell] を右クリックし、 **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="330ba-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="330ba-142">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-142">Run the following command.</span></span>

    <span data-ttu-id="330ba-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="330ba-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="330ba-144">メッセージが表示されたら、「Y」を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="330ba-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="330ba-145">**Get-MsolDevice コマンドレットを実行して組織内のすべてのデバイスの詳細情報を表示する**</span><span class="sxs-lookup"><span data-stu-id="330ba-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="330ba-146">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="330ba-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="330ba-147">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-147">Run the following command.</span></span>

    <span data-ttu-id="330ba-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span><span class="sxs-lookup"><span data-stu-id="330ba-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="330ba-149">その他の例については、「 [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="330ba-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="330ba-150">スクリプトを実行してデバイスの詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="330ba-150">Run a script to get device details</span></span>

<span data-ttu-id="330ba-151">最初に、コンピューターにスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="330ba-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="330ba-152">次のテキストをメモ帳にコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="330ba-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="330ba-153">param (</span><span class="sxs-lookup"><span data-stu-id="330ba-153">param (</span></span>

3.  <span data-ttu-id="330ba-154">[PSObject[]]$users = @(),</span><span class="sxs-lookup"><span data-stu-id="330ba-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="330ba-155">[Switch]$export,</span><span class="sxs-lookup"><span data-stu-id="330ba-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="330ba-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span><span class="sxs-lookup"><span data-stu-id="330ba-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="330ba-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span><span class="sxs-lookup"><span data-stu-id="330ba-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="330ba-158">)</span><span class="sxs-lookup"><span data-stu-id="330ba-158">)</span></span>

9.  <span data-ttu-id="330ba-159">[System.Collections.IDictionary]$script:schema = @{</span><span class="sxs-lookup"><span data-stu-id="330ba-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="330ba-160">DeviceId = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="330ba-161">DeviceOSType = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="330ba-162">DeviceOSVersion = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="330ba-163">DeviceTrustLevel = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="330ba-164">DisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="330ba-165">IsCompliant = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="330ba-166">IsManaged = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="330ba-167">ApproximateLastLogonTimestamp = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="330ba-168">DeviceObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="330ba-169">RegisteredOwnerUpn = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="330ba-170">RegisteredOwnerObjectId = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="330ba-171">RegisteredOwnerDisplayName = ''</span><span class="sxs-lookup"><span data-stu-id="330ba-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="330ba-172">}</span><span class="sxs-lookup"><span data-stu-id="330ba-172">}</span></span>
    

25.  <span data-ttu-id="330ba-173">function createResultObject</span><span class="sxs-lookup"><span data-stu-id="330ba-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="330ba-174">{</span><span class="sxs-lookup"><span data-stu-id="330ba-174">{</span></span>
    

28.  <span data-ttu-id="330ba-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span><span class="sxs-lookup"><span data-stu-id="330ba-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="330ba-176">return $resultObject</span><span class="sxs-lookup"><span data-stu-id="330ba-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="330ba-177">}</span><span class="sxs-lookup"><span data-stu-id="330ba-177">}</span></span>
    

33.  <span data-ttu-id="330ba-178">If ($users.Count -eq 0)</span><span class="sxs-lookup"><span data-stu-id="330ba-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="330ba-179">{</span><span class="sxs-lookup"><span data-stu-id="330ba-179">{</span></span>
    

35.  <span data-ttu-id="330ba-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="330ba-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="330ba-181">}</span><span class="sxs-lookup"><span data-stu-id="330ba-181">}</span></span>
    

38.  <span data-ttu-id="330ba-182">[PSObject[]]$result = foreach ($u in $users)</span><span class="sxs-lookup"><span data-stu-id="330ba-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="330ba-183">{</span><span class="sxs-lookup"><span data-stu-id="330ba-183">{</span></span>
    

41.  <span data-ttu-id="330ba-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="330ba-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="330ba-185">foreach ($d in $devices)</span><span class="sxs-lookup"><span data-stu-id="330ba-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="330ba-186">{</span><span class="sxs-lookup"><span data-stu-id="330ba-186">{</span></span>
    

44.  <span data-ttu-id="330ba-187">[PSObject]$deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="330ba-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="330ba-188">$deviceResult.DeviceId = $d.DeviceId</span><span class="sxs-lookup"><span data-stu-id="330ba-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="330ba-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="330ba-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="330ba-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="330ba-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="330ba-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="330ba-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="330ba-192">$deviceResult.DisplayName = $d.DisplayName</span><span class="sxs-lookup"><span data-stu-id="330ba-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="330ba-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span><span class="sxs-lookup"><span data-stu-id="330ba-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="330ba-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span><span class="sxs-lookup"><span data-stu-id="330ba-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="330ba-195">$deviceResult.DeviceObjectId = $d.ObjectId</span><span class="sxs-lookup"><span data-stu-id="330ba-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="330ba-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="330ba-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="330ba-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span><span class="sxs-lookup"><span data-stu-id="330ba-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="330ba-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span><span class="sxs-lookup"><span data-stu-id="330ba-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="330ba-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="330ba-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="330ba-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="330ba-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="330ba-201">}</span><span class="sxs-lookup"><span data-stu-id="330ba-201">}</span></span>
    

61.  <span data-ttu-id="330ba-202">}</span><span class="sxs-lookup"><span data-stu-id="330ba-202">}</span></span>
    

63.  <span data-ttu-id="330ba-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="330ba-203">If ($export)</span></span>
    

64.  <span data-ttu-id="330ba-204">{</span><span class="sxs-lookup"><span data-stu-id="330ba-204">{</span></span>
    

65.  <span data-ttu-id="330ba-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="330ba-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="330ba-206">}</span><span class="sxs-lookup"><span data-stu-id="330ba-206">}</span></span>
    

67.  <span data-ttu-id="330ba-207">Else</span><span class="sxs-lookup"><span data-stu-id="330ba-207">Else</span></span>
    

68.  <span data-ttu-id="330ba-208">{</span><span class="sxs-lookup"><span data-stu-id="330ba-208">{</span></span>
    

69.  <span data-ttu-id="330ba-209">$result</span><span class="sxs-lookup"><span data-stu-id="330ba-209">$result</span></span>
    

70.  <span data-ttu-id="330ba-210">}</span><span class="sxs-lookup"><span data-stu-id="330ba-210">}</span></span>
    

71.  <span data-ttu-id="330ba-211">ファイル拡張子 .ps1 を使用して、WindowsPowerShell スクリプト ファイルとして保存します。 たとえば、Get-MsolUserDeviceComplianceStatus.ps1 です。</span><span class="sxs-lookup"><span data-stu-id="330ba-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="330ba-212">スクリプトを実行して、単一のユーザー アカウントのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="330ba-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="330ba-213">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="330ba-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="330ba-214">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="330ba-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="330ba-215">たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="330ba-216">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="330ba-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="330ba-217">次のコマンドを実行して、デバイスの詳細情報を取得するユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="330ba-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="330ba-218">この例では、bar@example.com の詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="330ba-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="330ba-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="330ba-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="330ba-220">次のコマンドを実行して、スクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="330ba-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="330ba-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="330ba-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="330ba-222">この情報は、Windows デスクトップに CSV ファイルとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="330ba-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="330ba-223">追加のパラメーターを使用して、ファイル名と CSV のパスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="330ba-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="330ba-224">スクリプトを実行して、ユーザーのグループのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="330ba-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="330ba-225">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="330ba-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="330ba-226">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="330ba-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="330ba-227">たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="330ba-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="330ba-228">cd C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="330ba-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="330ba-229">次のコマンドを実行して、デバイスの詳細情報を取得するグループを特定します。</span><span class="sxs-lookup"><span data-stu-id="330ba-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="330ba-230">この例では、FinanceStaff グループのユーザーの詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="330ba-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="330ba-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span><span class="sxs-lookup"><span data-stu-id="330ba-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="330ba-232">次のコマンドを実行して、スクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="330ba-232">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="330ba-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span><span class="sxs-lookup"><span data-stu-id="330ba-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="330ba-234">この情報は、Windows デスクトップに CSV ファイルとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="330ba-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="330ba-235">追加のパラメーターを使用して、ファイル名と CSV のパスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="330ba-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="330ba-236">関連トピック</span><span class="sxs-lookup"><span data-stu-id="330ba-236">Related topics</span></span>

[<span data-ttu-id="330ba-237">Microsoft Connect は廃止されました</span><span class="sxs-lookup"><span data-stu-id="330ba-237">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="330ba-238">基本的なモビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="330ba-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="330ba-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="330ba-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)