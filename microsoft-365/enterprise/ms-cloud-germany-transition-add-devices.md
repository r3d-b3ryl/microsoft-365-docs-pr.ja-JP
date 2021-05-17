---
title: Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツのデータセンター地域の Office 365サービスに移行する場合のサービスに関するその他のデバイス情報。'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928158"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="cf507-103">Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報</span><span class="sxs-lookup"><span data-stu-id="cf507-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="cf507-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="cf507-104">Frequently asked questions</span></span>

<span data-ttu-id="cf507-105">**組織が影響を受けるかを確認する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="cf507-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="cf507-106">管理者は、登録済 `https://portal.microsoftazure.de` みのデバイスを持っているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="cf507-107">組織にデバイスが登録されている場合は、影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="cf507-108">**ユーザーに与える影響は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="cf507-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="cf507-109">登録されたデバイスのユーザーは、移行が [Azure](ms-cloud-germany-transition.md#how-is-the-migration-organized) 移行フェーズの最終段階に入った後AD使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cf507-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="cf507-110">組織が Microsoft Cloud Deutschland から切断される前に、すべてのデバイスがワールドワイド エンドポイントに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="cf507-111">**ユーザーがデバイスを再登録する場合**</span><span class="sxs-lookup"><span data-stu-id="cf507-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="cf507-112">成功するには [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 移行フェーズから分離中にデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="cf507-113">**移行後にデバイスの状態を復元する方法**</span><span class="sxs-lookup"><span data-stu-id="cf507-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="cf507-114">Azure AD に登録されているハイブリッド Azure AD に参加し、会社所有の Windows デバイスの場合、管理者は、古いデバイスの状態を登録解除するリモートでトリガーされたワークフローを通じて、これらのデバイスの移行を管理できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="cf507-115">Azure Windowsに登録されている個人用デバイスADを含む他のすべてのデバイスでは、これらの手順を手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="cf507-116">Azure AD参加しているデバイスの場合、ユーザーはデバイスの登録を解除してから再登録するローカル管理者アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="cf507-117">Microsoft は、デバイスの状態を正常に復元する方法に関する手順を公開します。</span><span class="sxs-lookup"><span data-stu-id="cf507-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="cf507-118">**すべてのデバイスがパブリック クラウドに登録されているのを知る方法**</span><span class="sxs-lookup"><span data-stu-id="cf507-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="cf507-119">デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルからデバイスのリストをエクスポートして、Excelする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="cf507-120">次に [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズから分離した後、登録されているデバイスを _(registeredTime_ 列を使用して) フィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cf507-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="cf507-121">デバイスの登録は、テナントの移行後に非アクティブ化され、有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf507-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="cf507-122">Intune を使用しない場合は、サブスクリプションにサインインし、このコマンドを実行してオプションを再アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="cf507-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="cf507-123">Hybrid Azure AD 参加</span><span class="sxs-lookup"><span data-stu-id="cf507-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="cf507-124">Windowsレベルの設定</span><span class="sxs-lookup"><span data-stu-id="cf507-124">Windows down-level</span></span>

<span data-ttu-id="cf507-125">_Windows_ ダウンレベル デバイスは、Windows の以前のバージョン (Windows 8.1 や Windows 7 など) を現在実行している Windows デバイス、または 2019 および 2016 より前の Windows Server バージョンを実行している Windows デバイスです。</span><span class="sxs-lookup"><span data-stu-id="cf507-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="cf507-126">このようなデバイスが以前に登録されている場合は、それらのデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="cf507-127">ダウン レベル のデバイスWindows以前に Azure ADに参加したかどうかを確認するには、デバイスで次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf507-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="cf507-128">デバイスが以前に Azure AD に参加し、デバイスがグローバル Azure AD エンドポイントへのネットワーク接続を持つ場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf507-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="cf507-129">影響を受けるデバイスには、"不明" の値を持つ "Device state" が設定されます。</span><span class="sxs-lookup"><span data-stu-id="cf507-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="cf507-130">出力が "Device not joined" または "Device state" の値が "Okay" の場合は、次のガイダンスを無視してください。</span><span class="sxs-lookup"><span data-stu-id="cf507-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="cf507-131">デバイスが参加している (deviceId、拇印など)、"Device state" 値が "不明" であるデバイスに対してだけ、管理者は、このようなダウンレベルデバイスでドメイン ユーザーがサインインするコンテキストで次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="cf507-132">前のコマンドを実行する必要があるのは、ドメイン ユーザーがダウンレベル デバイスでサインインWindows 1 回のみです。</span><span class="sxs-lookup"><span data-stu-id="cf507-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="cf507-133">このコマンドは、ドメイン ユーザーのサインインのコンテキストで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="cf507-134">ユーザーが後でサインインするときに、このコマンドを実行しないには十分な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="cf507-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="cf507-135">前のコマンドを実行すると、サインインしたユーザーのローカル ハイブリッド Azure AD参加しているコンピューターの参加状態がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="cf507-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="cf507-136">また、コンピューターがハイブリッド Azure AD–join in テナントとして構成されている場合は、ユーザーが再びサインインするときに参加を試みます。</span><span class="sxs-lookup"><span data-stu-id="cf507-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="cf507-137">Windows現在の</span><span class="sxs-lookup"><span data-stu-id="cf507-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="cf507-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="cf507-138">Unjoin</span></span>

<span data-ttu-id="cf507-139">デバイスが Azure Windows 10に以前に参加ADするには、デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf507-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="cf507-140">デバイスがハイブリッド Azure AD参加している場合、管理者には次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf507-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="cf507-141">出力が "AzureAdJoined : No" の場合は、次のガイダンスを無視してください。</span><span class="sxs-lookup"><span data-stu-id="cf507-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="cf507-142">デバイスが Azure AD に参加しているというデバイスの場合にのみ、管理者として次のコマンドを実行して、デバイスの参加状態を削除します。</span><span class="sxs-lookup"><span data-stu-id="cf507-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="cf507-143">前のコマンドは、デバイス上の管理コンテキストで 1 回だけ実行するWindowsです。</span><span class="sxs-lookup"><span data-stu-id="cf507-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="cf507-144">ハイブリッド AD Join\Re-registration</span><span class="sxs-lookup"><span data-stu-id="cf507-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="cf507-145">デバイスは、グローバル Azure ADエンドポイントへのネットワーク接続がある限り、ユーザーまたは管理者の介入なしに Azure ADに参加します。</span><span class="sxs-lookup"><span data-stu-id="cf507-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="cf507-146">Azure AD参加</span><span class="sxs-lookup"><span data-stu-id="cf507-146">Azure AD Join</span></span>

<span data-ttu-id="cf507-147">**重要:** Intune サービス プリンシパルは、コマースの移行後に有効になります。これは、デバイス登録に対する Azure ADを意味します。</span><span class="sxs-lookup"><span data-stu-id="cf507-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="cf507-148">移行前に Azure AD デバイス登録をブロックした場合は、PowerShell を使用して Intune サービス プリンシパルを無効にして、Azure AD デバイス登録を Azure AD ポータルで再度無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="cf507-149">このコマンドを使用して Intune サービス プリンシパルを無効にAzure Active Directory PowerShell Graphできます。</span><span class="sxs-lookup"><span data-stu-id="cf507-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="cf507-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="cf507-150">Unjoin</span></span>

<span data-ttu-id="cf507-151">ユーザーまたは管理者は、Windows 10 デバイスが以前に Azure AD に参加したかどうかを確認するために、デバイスで次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="cf507-152">デバイスが Azure ADに参加している場合、ユーザーまたは管理者には次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf507-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="cf507-153">出力が "AzureAdJoined : NO" の場合は、次のガイダンスを無視してください。</span><span class="sxs-lookup"><span data-stu-id="cf507-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="cf507-154">ユーザー: デバイスが Azure AD参加している場合、ユーザーは設定からデバイスへの参加を解除できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="cf507-155">Azure サーバーからデバイスに接続を解除する前に、デバイスにローカル管理者アカウントAD。</span><span class="sxs-lookup"><span data-stu-id="cf507-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="cf507-156">ローカル管理者アカウントは、デバイスにサインインし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="cf507-157">管理者: 組織の管理者が Azure AD に参加しているユーザーのデバイスへの参加を解除する場合は、グループ ポリシーなどのメカニズムを使用して、各デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf507-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="cf507-158">管理者は、Azure サーバーからデバイスに接続を解除する前に、デバイスにローカル管理者アカウントが存在AD。</span><span class="sxs-lookup"><span data-stu-id="cf507-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="cf507-159">デバイスにサインインし戻すには、ローカル管理者アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf507-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="cf507-160">前のコマンドは、デバイス上の管理コンテキストで 1 回だけ実行するWindowsです。</span><span class="sxs-lookup"><span data-stu-id="cf507-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="cf507-161">Azure AD参加/再登録</span><span class="sxs-lookup"><span data-stu-id="cf507-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="cf507-162">ユーザーは、デバイスを Azure AD に参加AD **設定Windowsアカウント** 設定 >、>または学校にアクセス> Connect。</span><span class="sxs-lookup"><span data-stu-id="cf507-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="cf507-163">Azure AD登録済み (会社所有)</span><span class="sxs-lookup"><span data-stu-id="cf507-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="cf507-164">デバイスが Azure Windows 10登録されているかどうかをADするには、デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf507-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="cf507-165">デバイスが Azure AD登録済みである場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf507-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="cf507-166">デバイス上の既存の Azure ADアカウントを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf507-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="cf507-167">デバイス上の Azure AD登録済みアカウントを削除するには、ここからダウンロードできるツールである CleanupWPJ [ を使用 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)CleanupWPJ.zip。</span><span class="sxs-lookup"><span data-stu-id="cf507-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="cf507-168">ZIP ファイルを抽出し **、WPJCleanup.cmd を実行します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="cf507-169">このツールは、デバイス上のファイルのバージョンに基づいてWindows実行ファイルを起動します。</span><span class="sxs-lookup"><span data-stu-id="cf507-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="cf507-170">グループ ポリシーのようなメカニズムを使用すると、管理者はデバイスにサインインしているすべてのユーザーのコンテキストで、デバイスでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="cf507-171">Azure アカウント にデバイスを登録するように求める Web アカウント マネージャーのプロンプトを無効にするにはAD、次のレジストリ値を追加します。</span><span class="sxs-lookup"><span data-stu-id="cf507-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="cf507-172">場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="cf507-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="cf507-173">種類: DWORD (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="cf507-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="cf507-174">名前: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="cf507-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="cf507-175">値データ: 1</span><span class="sxs-lookup"><span data-stu-id="cf507-175">Value data: 1</span></span>

<span data-ttu-id="cf507-176">このレジストリ値が存在する場合は、職場への参加をブロックし、ユーザーにデバイスへの参加を求めるプロンプトが表示されるのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="cf507-177">Android</span><span class="sxs-lookup"><span data-stu-id="cf507-177">Android</span></span>

<span data-ttu-id="cf507-178">Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="cf507-179">これは、アプリまたはアプリMicrosoft Authenticator使用してポータル サイトできます。</span><span class="sxs-lookup"><span data-stu-id="cf507-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="cf507-180">アプリからMicrosoft Authenticatorデバイス登録に移動設定 >**できます**。</span><span class="sxs-lookup"><span data-stu-id="cf507-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="cf507-181">そこから、ユーザーはデバイスの登録を解除して再登録できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="cf507-182">[デバイス] ポータル サイト[デバイス]**タブに** 移動し、デバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="cf507-183">その後、デバイスを使用してデバイスを再登録ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="cf507-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="cf507-184">ユーザーは、アカウント設定ページからアカウントを削除してから、作業アカウントを再追加することで、登録を解除して再登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf507-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="cf507-185">Android アプリを使用してデバイスの登録を解除して再登録するには、次Microsoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="cf507-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="cf507-186">アプリを開Microsoft Authenticatorに移動し、[設定]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="cf507-187">[デバイス **登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="cf507-188">[登録解除] を選択してデバイスの登録を **解除します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="cf507-189">[ **デバイスの登録]** で、電子メール アドレスを入力してデバイスを再登録し、[登録] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="cf507-190">Android デバイスの登録を解除して、Android デバイスを再登録するには、次設定します。</span><span class="sxs-lookup"><span data-stu-id="cf507-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="cf507-191">[デバイス **] ウィンドウ設定** 開き、[アカウント] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="cf507-192">再登録する作業アカウントを選択し、[アカウントの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="cf507-193">アカウントを削除した後、[アカウント] ページ **で** 、[アカウントの追加] **を選択し、[>] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf507-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="cf507-194">[Workplace **Join] で**、電子メール アドレスを入力し、[参加] を **選択** してデバイスの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="cf507-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="cf507-195">Android でデバイスの登録を解除して再登録するには、次ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="cf507-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="cf507-196">[デバイスポータル サイト起動し、[デバイス] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="cf507-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="cf507-197">デバイスを選択すると、デバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf507-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="cf507-198">省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。</span><span class="sxs-lookup"><span data-stu-id="cf507-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="cf507-199">これで、アプリからログアウトポータル サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="cf507-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="cf507-200">[ **サインイン] を選択** してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="cf507-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="cf507-201">このワークロードの移行フェーズ中に必要なアクション、または管理または使用状況への影響の詳細については[、「Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)からの移行に関する Azure AD の追加情報」の「Azure Active Directory (Azure AD) に関する情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf507-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="cf507-202">iOS</span><span class="sxs-lookup"><span data-stu-id="cf507-202">iOS</span></span>

<span data-ttu-id="cf507-203">iOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除し、デバイス上のネイティブ アプリからサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf507-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="cf507-204">手順 1: 存在する場合は、アプリからアカウントMicrosoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="cf507-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="cf507-205">アプリでアカウントをタップMicrosoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="cf507-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="cf507-206">右上隅にある **設定** アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="cf507-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="cf507-207">このアイコンが表示 **されない設定、** 最新バージョンのファイルを使用していない可能性Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="cf507-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="cf507-208">[アカウントの **削除] ボタンをタップ** します。</span><span class="sxs-lookup"><span data-stu-id="cf507-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="cf507-209">[この **デバイスのすべてのアプリ] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="cf507-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="cf507-210">手順 2: アプリからデバイスの登録をMicrosoft Authenticatorする</span><span class="sxs-lookup"><span data-stu-id="cf507-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="cf507-211">右上隅にあるメニュー アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="cf507-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="cf507-212">[デバイス **設定]** をタップし、[デバイス **登録] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="cf507-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="cf507-213">アカウントが表示されている場合は、[デバイスの登録を **解除] をタップ** し、ダイアログで [ **続行** ] をタップします。</span><span class="sxs-lookup"><span data-stu-id="cf507-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="cf507-214">その後、アカウントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="cf507-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="cf507-215">手順 3: 必要に応じて、個々のアプリからサインアウトする</span><span class="sxs-lookup"><span data-stu-id="cf507-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="cf507-216">ユーザーは、個々のアプリ (Outlook、Teams、OneDrive、それらのアプリからアカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="cf507-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="cf507-217">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cf507-217">More information</span></span>

<span data-ttu-id="cf507-218">はじめに:</span><span class="sxs-lookup"><span data-stu-id="cf507-218">Getting started:</span></span>

- [<span data-ttu-id="cf507-219">Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="cf507-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="cf507-220">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="cf507-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="cf507-221">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="cf507-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="cf507-222">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="cf507-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="cf507-223">切り替えの移動:</span><span class="sxs-lookup"><span data-stu-id="cf507-223">Moving through the transition:</span></span>

- [<span data-ttu-id="cf507-224">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="cf507-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="cf507-225">その他の作業前</span><span class="sxs-lookup"><span data-stu-id="cf507-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="cf507-226">Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。</span><span class="sxs-lookup"><span data-stu-id="cf507-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="cf507-227">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="cf507-227">Cloud apps:</span></span>

- [<span data-ttu-id="cf507-228">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="cf507-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="cf507-229">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="cf507-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="cf507-230">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="cf507-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)