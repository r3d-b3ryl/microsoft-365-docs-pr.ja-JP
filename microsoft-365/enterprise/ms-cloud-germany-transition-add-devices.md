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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する場合のサービスに関するその他のデバイス情報。'
ms.openlocfilehash: 151fcac882dc91d96df3ece000c28d1a7abe1d1f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780298"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="70296-103">Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報</span><span class="sxs-lookup"><span data-stu-id="70296-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="70296-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="70296-104">Frequently asked questions</span></span>

<span data-ttu-id="70296-105">**組織が影響を受けるのを確認する方法**</span><span class="sxs-lookup"><span data-stu-id="70296-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="70296-106">管理者は、デバイス `https://portal.microsoftazure.de` が登録されていないかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="70296-107">組織にデバイスが登録されている場合は、影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70296-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="70296-108">**ユーザーにどのような影響がありますか?**</span><span class="sxs-lookup"><span data-stu-id="70296-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="70296-109">登録されたデバイスのユーザーは、移行が Azure 移行フェーズの最終段階に入った後 [AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) でサインインできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="70296-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="70296-110">組織が Microsoft Cloud Deutschland から切断される前に、すべてのデバイスがワールドワイド エンドポイントに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="70296-111">**ユーザーがデバイスを再登録する場合**</span><span class="sxs-lookup"><span data-stu-id="70296-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="70296-112">成功するには [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 移行フェーズとは別にデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="70296-113">**移行後にデバイスの状態を復元する方法**</span><span class="sxs-lookup"><span data-stu-id="70296-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="70296-114">Azure AD に登録されているハイブリッド Azure AD に参加し、会社が所有する Windows デバイスが Azure AD に登録されている場合、管理者は、古いデバイスの状態の登録を解除するリモートでトリガーされたワークフローを通じて、これらのデバイスの移行を管理できます。</span><span class="sxs-lookup"><span data-stu-id="70296-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="70296-115">Azure AD に登録されている個人用 Windows デバイスを含む他のすべてのデバイスでは、エンド ユーザーは手動でこれらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="70296-116">Azure ADに参加しているデバイスの場合、ユーザーはデバイスの登録を解除してから再登録するためにローカル管理者アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="70296-117">Microsoft は、デバイスの状態を正常に復元する方法に関する手順を公開します。</span><span class="sxs-lookup"><span data-stu-id="70296-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="70296-118">**すべてのデバイスがパブリック クラウドに登録されているのを確認する方法**</span><span class="sxs-lookup"><span data-stu-id="70296-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="70296-119">デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルから Excel スプレッドシートにデバイスの一覧をエクスポートしてダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="70296-120">次に [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズから分離した後、登録されているデバイスを _(registeredTime_ 列を使用して) フィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="70296-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="70296-121">デバイスの登録は、テナントの移行後に非アクティブ化され、有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="70296-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="70296-122">Intune が使用されていない場合は、サブスクリプションにサインインし、次のコマンドを実行してオプションを再アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="70296-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="70296-123">Hybrid Azure AD 参加</span><span class="sxs-lookup"><span data-stu-id="70296-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="70296-124">Windows のダウンレベル</span><span class="sxs-lookup"><span data-stu-id="70296-124">Windows down-level</span></span>

<span data-ttu-id="70296-125">_Windows_ ダウンレベル デバイスは、現在、以前のバージョンの Windows (Windows 8.1 や Windows 7 など) を実行している、または 2019 および 2016 より前のバージョンの Windows Server を実行している Windows デバイスです。</span><span class="sxs-lookup"><span data-stu-id="70296-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="70296-126">このようなデバイスが以前に登録されている場合は、それらのデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="70296-127">Windows のダウンレベル デバイスが以前に Azure AD に参加したかどうかを確認するには、デバイスで次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="70296-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="70296-128">デバイスが以前に Azure AD に参加し、デバイスがグローバル Azure AD エンドポイントへのネットワーク接続を持つ場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70296-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="70296-129">影響を受けるデバイスは、値が "Unknown" の "Device state" になります。</span><span class="sxs-lookup"><span data-stu-id="70296-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="70296-130">出力が "デバイスに参加していない" 場合、または "デバイスの状態" の値が "Okay" の場合は、次のガイダンスは無視してください。</span><span class="sxs-lookup"><span data-stu-id="70296-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="70296-131">デバイスが参加している (deviceId、拇印などによって) "Device state" の値が "Unknown" であるデバイスに対してだけ、管理者はこのようなダウンレベル デバイスにサインインするドメイン ユーザーのコンテキストで次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="70296-132">上のコマンドは、Windows のダウンレベル デバイスにサインインするドメイン ユーザーごとに 1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="70296-133">このコマンドは、ドメイン ユーザーのサインインのコンテキストで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="70296-134">ユーザーが後でサインインするときに、このコマンドを実行しない場合は十分な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="70296-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="70296-135">前のコマンドを実行すると、サインインしたユーザーのローカル ハイブリッド Azure ADに参加しているコンピューターの参加状態がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="70296-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="70296-136">また、コンピューターが引き続きハイブリッド Azure AD に参加するように構成されている場合は、ユーザーが再びサインインするときに参加を試みます。</span><span class="sxs-lookup"><span data-stu-id="70296-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="70296-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="70296-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="70296-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="70296-138">Unjoin</span></span>

<span data-ttu-id="70296-139">Windows 10 デバイスが以前に Azure AD に参加したかどうかを確認するには、デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70296-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="70296-140">デバイスがハイブリッド Azure AD参加している場合、管理者には次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70296-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="70296-141">出力が "AzureAdJoined : No" の場合は、次のガイダンスは無視してください。</span><span class="sxs-lookup"><span data-stu-id="70296-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="70296-142">デバイスが Azure AD に参加しているデバイスの場合にのみ、管理者として次のコマンドを実行して、デバイスの参加状態を削除します。</span><span class="sxs-lookup"><span data-stu-id="70296-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="70296-143">上のコマンドは、Windows デバイスの管理コンテキストで 1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="70296-144">ハイブリッド AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="70296-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="70296-145">デバイスは、グローバル Azure AD エンドポイントへのネットワーク接続がある限り、ユーザーまたは管理者の介入なしに自動的に Azure AD に参加します。</span><span class="sxs-lookup"><span data-stu-id="70296-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="70296-146">Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="70296-146">Azure AD Join</span></span>

<span data-ttu-id="70296-147">**重要:** Intune サービス プリンシパルは、商取引の移行後に有効になります。これは、Azure AD Device Registration のアクティブ化を意味します。</span><span class="sxs-lookup"><span data-stu-id="70296-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="70296-148">移行前に Azure AD デバイス登録をブロックした場合は、PowerShell で Intune サービス プリンシパルを無効にして、Azure AD ポータルでの Azure AD デバイス登録を再度無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="70296-149">Azure Active Directory PowerShell for Graph モジュールで次のコマンドを使用して、Intune サービス プリンシパルを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="70296-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="70296-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="70296-150">Unjoin</span></span>

<span data-ttu-id="70296-151">Windows 10 デバイスが以前に Azure AD に参加したかどうかを確認するために、ユーザーまたは管理者はデバイスで次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70296-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="70296-152">デバイスが Azure AD に参加している場合、ユーザーまたは管理者には次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70296-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="70296-153">出力が "AzureAdJoined : NO" の場合は、次のガイダンスは無視してください。</span><span class="sxs-lookup"><span data-stu-id="70296-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="70296-154">ユーザー: デバイスが Azure AD参加している場合、ユーザーは設定からデバイスの参加を解除できます。</span><span class="sxs-lookup"><span data-stu-id="70296-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="70296-155">Azure AD からデバイスに接続を解除する前に、デバイスにローカル管理者アカウントが存在AD。</span><span class="sxs-lookup"><span data-stu-id="70296-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="70296-156">ローカル管理者アカウントは、デバイスにサインインし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="70296-157">管理者: 組織の管理者が、Azure AD に参加しているユーザーのデバイスの参加を解除する場合は、グループ ポリシーなどのメカニズムを使用して、各デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70296-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="70296-158">管理者は、Azure アカウントからデバイスに接続を解除する前に、デバイスにローカル管理者アカウントが存在AD。</span><span class="sxs-lookup"><span data-stu-id="70296-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="70296-159">ローカル管理者アカウントは、デバイスにサインインし戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="70296-160">上のコマンドは、Windows デバイスの管理コンテキストで 1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="70296-161">Azure ADの参加/再登録</span><span class="sxs-lookup"><span data-stu-id="70296-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="70296-162">ユーザーは、Windows の設定からデバイスを Azure AD に参加>アカウント **>、> Connect** にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="70296-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="70296-163">Azure AD登録済み (会社所有)</span><span class="sxs-lookup"><span data-stu-id="70296-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="70296-164">Windows 10 デバイスが Azure AD登録されているかどうかを確認するには、デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70296-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="70296-165">デバイスが Azure AD Registered である場合、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70296-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="70296-166">デバイス上の既存の Azure AD登録済みアカウントを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="70296-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="70296-167">デバイスで Azure AD登録済みアカウントを削除するには、CleanupWPJ を使用します。このツールは、次の場所からダウンロード[CleanupWPJ.zip。 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="70296-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="70296-168">ZIP ファイルを抽出し **、WPJCleanup.cmd を実行します**。</span><span class="sxs-lookup"><span data-stu-id="70296-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="70296-169">このツールは、デバイス上の Windows のバージョンに基づいて適切な実行可能ファイルを起動します。</span><span class="sxs-lookup"><span data-stu-id="70296-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="70296-170">管理者は、グループ ポリシーのようなメカニズムを使用して、デバイスにサインインしているすべてのユーザーのコンテキストで、デバイスでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70296-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="70296-171">Azure AD にデバイスを登録するように求める Web アカウント マネージャーのプロンプトを無効にするには、次のレジストリ値を追加します。</span><span class="sxs-lookup"><span data-stu-id="70296-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="70296-172">場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="70296-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="70296-173">型: DWORD (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="70296-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="70296-174">名前: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="70296-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="70296-175">値データ: 1</span><span class="sxs-lookup"><span data-stu-id="70296-175">Value data: 1</span></span>

<span data-ttu-id="70296-176">このレジストリ値が存在する場合は、職場への参加をブロックし、ユーザーにデバイスへの参加を求めるメッセージが表示されるのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="70296-177">Android</span><span class="sxs-lookup"><span data-stu-id="70296-177">Android</span></span>

<span data-ttu-id="70296-178">Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="70296-179">これは、Microsoft Authenticator アプリまたはポータル サイト アプリから実行できます。</span><span class="sxs-lookup"><span data-stu-id="70296-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="70296-180">Microsoft Authenticator アプリから、[デバイス登録] の [設定 **] >移動できます**。</span><span class="sxs-lookup"><span data-stu-id="70296-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="70296-181">そこから、ユーザーはデバイスの登録を解除して再登録できます。</span><span class="sxs-lookup"><span data-stu-id="70296-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="70296-182">ポータル サイトから、[デバイス] タブに移動し、デバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="70296-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="70296-183">その後、ポータル サイトを使用してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="70296-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="70296-184">ユーザーは、アカウント設定ページからアカウントを削除してから、仕事用アカウントを再追加することで、登録を解除して再登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="70296-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="70296-185">Microsoft Authenticator アプリを使用して Android のデバイスの登録を解除して再登録するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="70296-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="70296-186">Microsoft Authenticator アプリを開き、[設定] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="70296-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="70296-187">[デバイス **の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70296-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="70296-188">[登録解除] を選択してデバイスの登録を **解除します**。</span><span class="sxs-lookup"><span data-stu-id="70296-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="70296-189">デバイス **登録の場合** は、電子メール アドレスを入力してデバイスを再登録し、[登録] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="70296-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="70296-190">Android デバイスの登録を解除し、Android デバイスを [設定] ページに再登録するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="70296-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="70296-191">デバイス設定 **を開き、[** アカウント] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="70296-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="70296-192">再登録する仕事用アカウントを選択し、[アカウントの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70296-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="70296-193">アカウントを削除した後、[アカウント]ページで[アカウントの追加] を選択し、[>**アカウント] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="70296-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="70296-194">Workplace **Join の場合は**、メール アドレスを入力し、[参加] **を選択して** デバイスの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="70296-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="70296-195">ポータル サイトから Android のデバイスの登録を解除して再登録するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="70296-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="70296-196">ポータル サイトを起動し、[デバイス] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="70296-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="70296-197">デバイスを選択して、デバイスの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="70296-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="70296-198">省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。</span><span class="sxs-lookup"><span data-stu-id="70296-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="70296-199">ポータル サイト アプリからログアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="70296-200">[ **サインイン] を** 選択してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="70296-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="70296-201">このワークロードの移行フェーズ中に必要なアクション、または管理や使用状況への影響の詳細については [、Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)からの移行に関する Azure AD の追加情報の Azure Active Directory (Azure AD) に関する情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="70296-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="70296-202">iOS</span><span class="sxs-lookup"><span data-stu-id="70296-202">iOS</span></span>

<span data-ttu-id="70296-203">iOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除し、デバイス上のネイティブ アプリからサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="70296-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="70296-204">手順 1: 存在する場合は、Microsoft Authenticator アプリからアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="70296-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="70296-205">Microsoft Authenticator アプリでアカウントをタップします。</span><span class="sxs-lookup"><span data-stu-id="70296-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="70296-206">右上隅にある **[** 設定] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="70296-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="70296-207">[設定] アイコンが表示されない場合は、Microsoft Authenticator の最新バージョンを使用していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70296-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="70296-208">[アカウントの **削除] ボタンをタップ** します。</span><span class="sxs-lookup"><span data-stu-id="70296-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="70296-209">この **デバイスのすべてのアプリをタップします**。</span><span class="sxs-lookup"><span data-stu-id="70296-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="70296-210">手順 2: Microsoft Authenticator アプリからデバイスの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="70296-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="70296-211">右上隅にあるメニュー アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="70296-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="70296-212">[設定 **] をタップ** し、[デバイス **の登録] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="70296-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="70296-213">アカウントが表示されている場合は、[デバイスの登録解除] **を** タップし、ダイアログ **で** [続行] をタップします。</span><span class="sxs-lookup"><span data-stu-id="70296-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="70296-214">その後、アカウントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="70296-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="70296-215">手順 3: 必要に応じて個々のアプリからサインアウトする</span><span class="sxs-lookup"><span data-stu-id="70296-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="70296-216">ユーザーは、Outlook、Teams、OneDrive など、個々のアプリに移動し、それらのアプリからアカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="70296-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="70296-217">詳細情報</span><span class="sxs-lookup"><span data-stu-id="70296-217">More information</span></span>

<span data-ttu-id="70296-218">はじめに:</span><span class="sxs-lookup"><span data-stu-id="70296-218">Getting started:</span></span>

- [<span data-ttu-id="70296-219">Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="70296-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="70296-220">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="70296-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="70296-221">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="70296-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="70296-222">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="70296-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="70296-223">移行を進む:</span><span class="sxs-lookup"><span data-stu-id="70296-223">Moving through the transition:</span></span>

- [<span data-ttu-id="70296-224">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="70296-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="70296-225">追加の作業前作業</span><span class="sxs-lookup"><span data-stu-id="70296-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="70296-226">[Azure](ms-cloud-germany-transition-azure-ad.md)AD、[デバイス、エクスペリエンス](ms-cloud-germany-transition-add-devices.md)、[および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="70296-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="70296-227">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="70296-227">Cloud apps:</span></span>

- [<span data-ttu-id="70296-228">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="70296-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="70296-229">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="70296-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="70296-230">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="70296-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
