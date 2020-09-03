---
title: 基本的なモビリティおよびセキュリティ管理デバイスの詳細を取得する
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
description: Windows PowerShell を使用して、組織内の基本的なモビリティおよびセキュリティデバイスに関する詳細を取得します。
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336965"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="df568-103">基本的なモビリティおよびセキュリティ管理デバイスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="df568-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="df568-104">この記事では、Windows PowerShell を使用して、基本的なモビリティとセキュリティのためにセットアップした組織内のデバイスに関する詳細を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="df568-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="df568-105">使用可能なデバイスの詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df568-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="df568-106">**詳細**</span><span class="sxs-lookup"><span data-stu-id="df568-106">**Detail**</span></span>|<span data-ttu-id="df568-107">**PowerShell での検索対象**</span><span class="sxs-lookup"><span data-stu-id="df568-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="df568-108">デバイスは基本的なモビリティとセキュリティに登録されています。</span><span class="sxs-lookup"><span data-stu-id="df568-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="df568-109">詳細については、「 [Basic Mobility And Security を使用したモバイルデバイスの登録](enroll-your-mobile-device-using-basic-mobility-and-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df568-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span></span>|<span data-ttu-id="df568-110"> \*Ismanaged*   パラメーターの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df568-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="df568-111">**True**= デバイスは登録されています。</span><span class="sxs-lookup"><span data-stu-id="df568-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="df568-112">**False**= デバイスは登録されていません。</span><span class="sxs-lookup"><span data-stu-id="df568-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="df568-113">デバイスは、デバイスのセキュリティポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="df568-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="df568-114">詳細については、「[デバイスセキュリティポリシーの作成](create-device-security-policies-in-basic-mmobility-and-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df568-114">For more info, see [Create device security policies](create-device-security-policies-in-basic-mmobility-and-security.md)</span></span>|<span data-ttu-id="df568-115"> \*Iscompliant*   パラメーターの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df568-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="df568-116">**True**  = デバイスはポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="df568-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="df568-117">**False**  = デバイスはポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="df568-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的な Mobility および Security PowerShell パラメーター":::

>[!NOTE]
><span data-ttu-id="df568-119">この記事のコマンドとスクリプトは、 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)によって管理されるすべてのデバイスに関する詳細も返します。</span><span class="sxs-lookup"><span data-stu-id="df568-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="df568-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="df568-120">Before you begin</span></span>

<span data-ttu-id="df568-121">この記事で説明されているコマンドとスクリプトを実行するためにセットアップする必要があるいくつかの事柄があります。</span><span class="sxs-lookup"><span data-stu-id="df568-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="df568-122">手順 1: Windows PowerShell 用 Azure Active Directory モジュールをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="df568-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="df568-123">これらの手順の詳細については、「 [Connect To Microsoft 365 With PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df568-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="df568-124"> [IT プロフェッショナル向け Microsoft Online Services サインインアシスタント](https://www.microsoft.com/download/details.aspx?id=41950)に移動   し、  *\*Microsoft online Services サインインアシスタントのダウンロード*\*を選択します。</span><span class="sxs-lookup"><span data-stu-id="df568-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="df568-125">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="df568-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="df568-126">管理者レベルの PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="df568-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="df568-127">Install-Module MSOnline コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="df568-128">NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。</span><span class="sxs-lookup"><span data-stu-id="df568-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="df568-129">PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="df568-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="df568-130">インストール後、PowerShell コマンド ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="df568-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="df568-131">手順 2: Microsoft 365 サブスクリプションに接続する</span><span class="sxs-lookup"><span data-stu-id="df568-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="df568-132">Windows PowerShell 用 Windows Azure Active Directory モジュールで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="df568-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="df568-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="df568-134">[Windows PowerShell 資格情報の要求] ダイアログボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="df568-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="df568-135">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-135">Run the following command.</span></span>
    
    <span data-ttu-id="df568-136">Connect-msolservice-Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="df568-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="df568-137">手順 3: PowerShell スクリプトを実行できることを確認する</span><span class="sxs-lookup"><span data-stu-id="df568-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="df568-138">PowerShell スクリプトを実行するように設定されている場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="df568-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="df568-139">Get-MsolUserDeviceComplianceStatus.ps1 スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df568-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="df568-140">Windows デスクトップから [ **スタート**] を選択し、「windows PowerShell」と入力します。</span><span class="sxs-lookup"><span data-stu-id="df568-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="df568-141">[Windows PowerShell] を右クリックし、[ **管理者として実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df568-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="df568-142">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-142">Run the following command.</span></span>
    
    <span data-ttu-id="df568-143">ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="df568-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="df568-144">プロンプトが表示されたら、「Y」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="df568-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="df568-145">**MsolDevice コマンドレットを実行して、組織内のすべてのデバイスの詳細を表示します。**</span><span class="sxs-lookup"><span data-stu-id="df568-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="df568-146">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="df568-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="df568-147">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-147">Run the following command.</span></span>
    
    <span data-ttu-id="df568-148">MsolDevice-ReturnRegisteredOwners |ここで、オブジェクト {$ _ を指定します。RegisteredOwners-gt 0}</span><span class="sxs-lookup"><span data-stu-id="df568-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="df568-149">詳細な例については、「  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df568-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="df568-150">スクリプトを実行してデバイスの詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="df568-150">Run a script to get device details</span></span>

<span data-ttu-id="df568-151">最初に、スクリプトをコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="df568-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="df568-152">次のテキストをコピーしてメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="df568-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="df568-153">param</span><span class="sxs-lookup"><span data-stu-id="df568-153">param (</span></span>
    

3.  <span data-ttu-id="df568-154">[PSObject []] $users = @ ()、</span><span class="sxs-lookup"><span data-stu-id="df568-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="df568-155">[スイッチ] $export、</span><span class="sxs-lookup"><span data-stu-id="df568-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="df568-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (取得日-日付形式 "yyMMdd_HHMMss") + ".csv"、</span><span class="sxs-lookup"><span data-stu-id="df568-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="df568-157">[String] $exportPath = [Environment]:: GetFolderPath ("Desktop")</span><span class="sxs-lookup"><span data-stu-id="df568-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="df568-158">)</span><span class="sxs-lookup"><span data-stu-id="df568-158">)</span></span>
    

9.  <span data-ttu-id="df568-159">[System.web] $script: スキーマ = @ {</span><span class="sxs-lookup"><span data-stu-id="df568-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="df568-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="df568-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="df568-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="df568-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="df568-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="df568-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="df568-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="df568-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="df568-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="df568-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="df568-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="df568-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="df568-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="df568-172">}</span><span class="sxs-lookup"><span data-stu-id="df568-172">}</span></span>
    

25.  <span data-ttu-id="df568-173">関数 createResultObject</span><span class="sxs-lookup"><span data-stu-id="df568-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="df568-174">{</span><span class="sxs-lookup"><span data-stu-id="df568-174">{</span></span>
    

28.  <span data-ttu-id="df568-175">[PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: schema</span><span class="sxs-lookup"><span data-stu-id="df568-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="df568-176">$resultObject を返します。</span><span class="sxs-lookup"><span data-stu-id="df568-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="df568-177">}</span><span class="sxs-lookup"><span data-stu-id="df568-177">}</span></span>
    

33.  <span data-ttu-id="df568-178">If ($users。Count-eq 0)</span><span class="sxs-lookup"><span data-stu-id="df568-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="df568-179">{</span><span class="sxs-lookup"><span data-stu-id="df568-179">{</span></span>
    

35.  <span data-ttu-id="df568-180">$users = Get-msoluser</span><span class="sxs-lookup"><span data-stu-id="df568-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="df568-181">}</span><span class="sxs-lookup"><span data-stu-id="df568-181">}</span></span>
    

38.  <span data-ttu-id="df568-182">[PSObject []] $result = foreach ($u $users)</span><span class="sxs-lookup"><span data-stu-id="df568-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="df568-183">{</span><span class="sxs-lookup"><span data-stu-id="df568-183">{</span></span>
    

41.  <span data-ttu-id="df568-184">[PSObject] $devices = msoldevice-RegisteredOwnerUpn $u</span><span class="sxs-lookup"><span data-stu-id="df568-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="df568-185">foreach ($d $devices)</span><span class="sxs-lookup"><span data-stu-id="df568-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="df568-186">{</span><span class="sxs-lookup"><span data-stu-id="df568-186">{</span></span>
    

44.  <span data-ttu-id="df568-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="df568-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="df568-188">$deviceResult: DeviceId = $d</span><span class="sxs-lookup"><span data-stu-id="df568-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="df568-189">$deviceResult DeviceOSType = $d DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="df568-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="df568-190">$deviceResult DeviceOSVersion = $d DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="df568-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="df568-191">DeviceTrustLevel = $d $deviceResult。 DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="df568-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="df568-192">$deviceResult DisplayName = $d DisplayName</span><span class="sxs-lookup"><span data-stu-id="df568-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="df568-193">$deviceResult IsCompliant = $d GraphDeviceObject 準拠</span><span class="sxs-lookup"><span data-stu-id="df568-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="df568-194">$deviceResult IsManaged = $d GraphDeviceObject。</span><span class="sxs-lookup"><span data-stu-id="df568-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="df568-195">$deviceResult DeviceObjectId = $d ObjectId</span><span class="sxs-lookup"><span data-stu-id="df568-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="df568-196">$deviceResult RegisteredOwnerUpn = $u</span><span class="sxs-lookup"><span data-stu-id="df568-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="df568-197">RegisteredOwnerObjectId = $u $deviceResult</span><span class="sxs-lookup"><span data-stu-id="df568-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="df568-198">$deviceResult RegisteredOwnerDisplayName = $u</span><span class="sxs-lookup"><span data-stu-id="df568-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="df568-199">ApproximateLastLogonTimestamp = $d $deviceResult。 ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="df568-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="df568-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="df568-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="df568-201">}</span><span class="sxs-lookup"><span data-stu-id="df568-201">}</span></span>
    

61.  <span data-ttu-id="df568-202">}</span><span class="sxs-lookup"><span data-stu-id="df568-202">}</span></span>
    

63.  <span data-ttu-id="df568-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="df568-203">If ($export)</span></span>
    

64.  <span data-ttu-id="df568-204">{</span><span class="sxs-lookup"><span data-stu-id="df568-204">{</span></span>
    

65.  <span data-ttu-id="df568-205">$result |エクスポート-Csv-path ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="df568-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="df568-206">}</span><span class="sxs-lookup"><span data-stu-id="df568-206">}</span></span>
    

67.  <span data-ttu-id="df568-207">Else</span><span class="sxs-lookup"><span data-stu-id="df568-207">Else</span></span>
    

68.  <span data-ttu-id="df568-208">{</span><span class="sxs-lookup"><span data-stu-id="df568-208">{</span></span>
    

69.  <span data-ttu-id="df568-209">$result</span><span class="sxs-lookup"><span data-stu-id="df568-209">$result</span></span>
    

70.  <span data-ttu-id="df568-210">}</span><span class="sxs-lookup"><span data-stu-id="df568-210">}</span></span>
    

71.  <span data-ttu-id="df568-211">ファイル拡張子 ps1 を使用して、Windows PowerShell スクリプトファイルとして保存します。 ps1;たとえば、Get-MsolUserDeviceComplianceStatus.ps1 のようにします。</span><span class="sxs-lookup"><span data-stu-id="df568-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="df568-212">スクリプトを実行して1つのユーザーアカウントのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="df568-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="df568-213">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="df568-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="df568-214">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="df568-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="df568-215">たとえば、これを c: ¥スクリプトに保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="df568-216">cd の C:\windows psscripts</span><span class="sxs-lookup"><span data-stu-id="df568-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="df568-217">デバイスの詳細を取得するユーザーを識別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="df568-218">この例では、bar@example.com の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="df568-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="df568-219">$u = Get-msoluser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="df568-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="df568-220">スクリプトを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="df568-221">.\Get-MsolUserDeviceComplianceStatus.ps1-ユーザー $u エクスポート</span><span class="sxs-lookup"><span data-stu-id="df568-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="df568-222">情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="df568-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="df568-223">CSV のファイル名とパスを指定するには、追加のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df568-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="df568-224">スクリプトを実行してユーザーのグループのデバイス情報を取得する</span><span class="sxs-lookup"><span data-stu-id="df568-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="df568-225">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="df568-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="df568-226">スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="df568-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="df568-227">たとえば、これを c: ¥スクリプトに保存した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="df568-228">cd の C:\windows psscripts</span><span class="sxs-lookup"><span data-stu-id="df568-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="df568-229">デバイスの詳細を取得するグループを識別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="df568-230">この例では、FinanceStaff グループ内のユーザーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="df568-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="df568-231">$u = MsolGroupMember-SearchString "FinanceStaff" |% {Get-msoluser-ObjectId $ _。Id</span><span class="sxs-lookup"><span data-stu-id="df568-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="df568-232">スクリプトを開始するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df568-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="df568-233">.\Get-MsolUserDeviceComplianceStatus.ps1-ユーザー $u エクスポート</span><span class="sxs-lookup"><span data-stu-id="df568-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="df568-234">情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="df568-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="df568-235">CSV のファイル名とパスを指定するには、追加のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df568-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="df568-236">関連項目</span><span class="sxs-lookup"><span data-stu-id="df568-236">Related topics</span></span>

[<span data-ttu-id="df568-237">Microsoft Connect は廃止されました</span><span class="sxs-lookup"><span data-stu-id="df568-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="df568-238">基本的なモビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="df568-238">Overview of Basic Mobility and Security</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="df568-239">MsolDevice</span><span class="sxs-lookup"><span data-stu-id="df568-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)