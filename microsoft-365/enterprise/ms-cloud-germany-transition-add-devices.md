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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861308"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="09047-103">Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報</span><span class="sxs-lookup"><span data-stu-id="09047-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="09047-104">Azure AD、Microsoft Cloud Deutschland に接続されている登録済みデバイスは、フェーズ 9 以降およびフェーズ 10 より前に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="09047-105">デバイスの移行は、デバイスの種類、オペレーティング システム、および AAD の関係によって異なります。</span><span class="sxs-lookup"><span data-stu-id="09047-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="09047-106">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="09047-106">Frequently asked questions</span></span>

<span data-ttu-id="09047-107">**組織が影響を受けるかを確認する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="09047-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="09047-108">管理者は、登録済みデバイスまたは Azure デバイスが参加しているデバイスAD `https://portal.microsoftazure.de` 確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="09047-109">組織にデバイスが登録されている場合は、影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09047-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="09047-110">**ユーザーに与える影響は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="09047-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="09047-111">移行フェーズ [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) が完了し、Microsoft Cloud Deutschland のエンドポイントが無効になった後、登録済みデバイスのユーザーはサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="09047-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="09047-112">組織が Microsoft Cloud Deutschland から切断される前に、すべてのデバイスがワールドワイド エンドポイントに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="09047-113">**ユーザーがデバイスを再登録する場合**</span><span class="sxs-lookup"><span data-stu-id="09047-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="09047-114">フェーズ [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) の完了後にデバイスの登録を解除して再登録する必要がある場合は、成功にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="09047-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="09047-115">フェーズ 10 が開始する前に再登録を完了する必要があります。それ以外の場合は、デバイスへのアクセスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09047-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="09047-116">**移行後にデバイスの状態を復元する方法**</span><span class="sxs-lookup"><span data-stu-id="09047-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="09047-117">Azure AD に登録されている会社所有の Windows デバイスの場合、管理者は、古いデバイスの状態を登録解除するリモートでトリガーされたワークフローを通じて、これらのデバイスの移行を管理できます。</span><span class="sxs-lookup"><span data-stu-id="09047-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="09047-118">Azure Windowsに登録されている個人用デバイスADを含む他のすべてのデバイスでは、これらの手順を手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="09047-119">Azure AD参加しているデバイスの場合、ユーザーはデバイスの登録を解除してから再登録するローカル管理者アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="09047-120">デバイスの状態を正常に復元する方法については、以下の詳細な手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09047-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="09047-121">**すべてのデバイスがパブリック クラウドに登録されているのを知る方法**</span><span class="sxs-lookup"><span data-stu-id="09047-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="09047-122">デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルからデバイスのリストをエクスポートして、Excelする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="09047-123">次に [、Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズから分離した後、登録されているデバイスを _(registeredTime_ 列を使用して) フィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="09047-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="09047-124">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="09047-124">Additional considerations</span></span>
<span data-ttu-id="09047-125">デバイスの登録は、テナントの移行後に非アクティブ化され、有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09047-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="09047-126">Intune を使用しない場合は、サブスクリプションにサインインし、このコマンドを実行してオプションを再アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="09047-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="09047-127">**重要:** Intune サービス プリンシパルは、コマースの移行後に有効になります。これは、デバイス登録に対する Azure ADを意味します。</span><span class="sxs-lookup"><span data-stu-id="09047-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="09047-128">移行前に Azure AD デバイス登録をブロックした場合は、PowerShell を使用して Intune サービス プリンシパルを無効にして、Azure AD デバイス登録を Azure AD ポータルで再度無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="09047-129">このコマンドを使用して Intune サービス プリンシパルを無効にAzure Active Directory PowerShell Graphできます。</span><span class="sxs-lookup"><span data-stu-id="09047-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="09047-130">Azure AD参加</span><span class="sxs-lookup"><span data-stu-id="09047-130">Azure AD Join</span></span>
<span data-ttu-id="09047-131">これは、デバイスのWindows 10適用されます。</span><span class="sxs-lookup"><span data-stu-id="09047-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="09047-132">デバイスが Azure デバイスに参加AD場合は、Azure サーバーから切断され、AD接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="09047-133">[![Azure AD デバイス Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="09047-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="09047-134">ユーザーがデバイスの管理者であるWindows 10、ユーザーは Azure デバイスからデバイスの登録を解除し、AD再度参加できます。</span><span class="sxs-lookup"><span data-stu-id="09047-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="09047-135">管理者特権がない場合、ユーザーは、このコンピューター上のローカル管理者アカウントの資格情報を必要とします。</span><span class="sxs-lookup"><span data-stu-id="09047-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="09047-136">管理者は、次の構成パスに従ってデバイスにローカル管理者アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="09047-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="09047-137">*設定 > アカウント > アカウント >資格情報不明 > Microsoft-Account を使用せずにユーザーを追加する*</span><span class="sxs-lookup"><span data-stu-id="09047-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="09047-138">手順 1: デバイスが Azure ID に参加しているかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="09047-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="09047-139">ユーザーの電子メールとパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="09047-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="09047-140">[アカウント] 設定 >[>] に移動します。</span><span class="sxs-lookup"><span data-stu-id="09047-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="09047-141">..に接続されているリスト内 **のユーザーを探します。's Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="09047-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="09047-142">接続されているユーザーが存在する場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="09047-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="09047-143">それがない場合は、それ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="09047-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="09047-144">手順 2: Azure サーバーからデバイスを切断AD</span><span class="sxs-lookup"><span data-stu-id="09047-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="09047-145">接続されている **作業時間** または学校アカウントで [切断] をタップします。</span><span class="sxs-lookup"><span data-stu-id="09047-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="09047-146">切断を 2 回確認します。</span><span class="sxs-lookup"><span data-stu-id="09047-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="09047-147">ローカル管理者のユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="09047-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="09047-148">デバイスが切断されています。</span><span class="sxs-lookup"><span data-stu-id="09047-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="09047-149">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="09047-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="09047-150">手順 3: デバイスを Azure デバイスに参加AD</span><span class="sxs-lookup"><span data-stu-id="09047-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="09047-151">ユーザーがローカル管理者の資格情報でサインインする</span><span class="sxs-lookup"><span data-stu-id="09047-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="09047-152">[アカウント]**設定[仕事または** 学校に **アクセスする] の順に移動します。** </span><span class="sxs-lookup"><span data-stu-id="09047-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="09047-153">**[Connect**</span><span class="sxs-lookup"><span data-stu-id="09047-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="09047-154">**重要**: **[Azure に参加] をタップAD**</span><span class="sxs-lookup"><span data-stu-id="09047-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="09047-155">ユーザーの電子メール アドレスとパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="09047-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="09047-156">デバイスが接続されている</span><span class="sxs-lookup"><span data-stu-id="09047-156">The device is connected</span></span>
6.  <span data-ttu-id="09047-157">デバイスを再起動する</span><span class="sxs-lookup"><span data-stu-id="09047-157">Restart the device</span></span> 
7.  <span data-ttu-id="09047-158">電子メール アドレスとパスワードで署名する</span><span class="sxs-lookup"><span data-stu-id="09047-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="09047-159">Azure AD登録済み (会社所有)</span><span class="sxs-lookup"><span data-stu-id="09047-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="09047-160">デバイスが Azure Windows 10登録されているかどうかをADするには、デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="09047-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="09047-161">デバイスが Azure AD登録済みである場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="09047-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="09047-162">デバイス上の既存の Azure ADアカウントを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="09047-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="09047-163">デバイス上の Azure AD登録済みアカウントを削除するには、ここからダウンロードできるツールである CleanupWPJ [ を使用 ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)CleanupWPJ.zip。</span><span class="sxs-lookup"><span data-stu-id="09047-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="09047-164">ZIP ファイルを抽出し **、WPJCleanup.cmd を実行します**。</span><span class="sxs-lookup"><span data-stu-id="09047-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="09047-165">このツールは、デバイス上のファイルのバージョンに基づいてWindows実行ファイルを起動します。</span><span class="sxs-lookup"><span data-stu-id="09047-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="09047-166">グループ ポリシーのようなメカニズムを使用すると、管理者はデバイスにサインインしているすべてのユーザーのコンテキストで、デバイスでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="09047-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="09047-167">Azure アカウント にデバイスを登録するように求める Web アカウント マネージャーのプロンプトを無効にするにはAD、次のレジストリ値を追加します。</span><span class="sxs-lookup"><span data-stu-id="09047-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="09047-168">場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="09047-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="09047-169">種類: DWORD (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="09047-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="09047-170">名前: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="09047-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="09047-171">値データ: 1</span><span class="sxs-lookup"><span data-stu-id="09047-171">Value data: 1</span></span>

<span data-ttu-id="09047-172">このレジストリ値が存在する場合は、職場への参加をブロックし、ユーザーにデバイスへの参加を求めるプロンプトが表示されるのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="09047-173">Android</span><span class="sxs-lookup"><span data-stu-id="09047-173">Android</span></span>

<span data-ttu-id="09047-174">Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="09047-175">これは、アプリまたはアプリMicrosoft Authenticator使用してポータル サイトできます。</span><span class="sxs-lookup"><span data-stu-id="09047-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="09047-176">アプリからMicrosoft Authenticatorデバイス登録に移動設定 >**できます**。</span><span class="sxs-lookup"><span data-stu-id="09047-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="09047-177">そこから、ユーザーはデバイスの登録を解除して再登録できます。</span><span class="sxs-lookup"><span data-stu-id="09047-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="09047-178">[デバイス] ポータル サイト[デバイス]**タブに** 移動し、デバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="09047-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="09047-179">その後、デバイスを使用してデバイスを再登録ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="09047-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="09047-180">ユーザーは、アカウント設定ページからアカウントを削除してから、作業アカウントを再追加することで、登録を解除して再登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="09047-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="09047-181">Android アプリを使用してデバイスの登録を解除して再登録するには、次Microsoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="09047-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="09047-182">アプリを開Microsoft Authenticatorに移動し、[設定]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="09047-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="09047-183">[デバイス **登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="09047-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="09047-184">[登録解除] を選択してデバイスの登録を **解除します**。</span><span class="sxs-lookup"><span data-stu-id="09047-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="09047-185">[ **デバイスの登録]** で、電子メール アドレスを入力してデバイスを再登録し、[登録] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="09047-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="09047-186">Android デバイスの登録を解除して、Android デバイスを再登録するには、次設定します。</span><span class="sxs-lookup"><span data-stu-id="09047-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="09047-187">[デバイス **] ウィンドウ設定** 開き、[アカウント] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="09047-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="09047-188">再登録する作業アカウントを選択し、[アカウントの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="09047-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="09047-189">アカウントを削除した後、[アカウント] ページ **で** 、[アカウントの追加] **を選択し、[>] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="09047-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="09047-190">[Workplace **Join] で**、電子メール アドレスを入力し、[参加] を **選択** してデバイスの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="09047-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="09047-191">Android でデバイスの登録を解除して再登録するには、次ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="09047-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="09047-192">[デバイスポータル サイト起動し、[デバイス] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="09047-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="09047-193">デバイスを選択すると、デバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="09047-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="09047-194">省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。</span><span class="sxs-lookup"><span data-stu-id="09047-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="09047-195">これで、アプリからログアウトポータル サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="09047-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="09047-196">[ **サインイン] を選択** してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="09047-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="09047-197">このワークロードの移行フェーズ中に必要なアクション、または管理または使用状況への影響の詳細については[、「Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)からの移行に関する Azure AD の追加情報」の「Azure Active Directory (Azure AD) に関する情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09047-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="09047-198">iOS</span><span class="sxs-lookup"><span data-stu-id="09047-198">iOS</span></span>

<span data-ttu-id="09047-199">iOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除し、デバイス上のネイティブ アプリからサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09047-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="09047-200">手順 1: 存在する場合は、アプリからアカウントMicrosoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="09047-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="09047-201">アプリでアカウントをタップMicrosoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="09047-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="09047-202">右上隅にある **設定** アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="09047-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="09047-203">このアイコンが表示 **されない設定、** 最新バージョンのファイルを使用していない可能性Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="09047-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="09047-204">[アカウントの **削除] ボタンをタップ** します。</span><span class="sxs-lookup"><span data-stu-id="09047-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="09047-205">[この **デバイスのすべてのアプリ] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="09047-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="09047-206">手順 2: アプリからデバイスの登録をMicrosoft Authenticatorする</span><span class="sxs-lookup"><span data-stu-id="09047-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="09047-207">右上隅にあるメニュー アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="09047-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="09047-208">[デバイス **設定]** をタップし、[デバイス **登録] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="09047-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="09047-209">アカウントが表示されている場合は、[デバイスの登録を **解除] をタップ** し、ダイアログで [ **続行** ] をタップします。</span><span class="sxs-lookup"><span data-stu-id="09047-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="09047-210">その後、アカウントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="09047-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="09047-211">手順 3: 必要に応じて、個々のアプリからサインアウトする</span><span class="sxs-lookup"><span data-stu-id="09047-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="09047-212">ユーザーは、個々のアプリ (Outlook、Teams、OneDrive、それらのアプリからアカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="09047-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="09047-213">詳細情報</span><span class="sxs-lookup"><span data-stu-id="09047-213">More information</span></span>

<span data-ttu-id="09047-214">はじめに:</span><span class="sxs-lookup"><span data-stu-id="09047-214">Getting started:</span></span>

- [<span data-ttu-id="09047-215">Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="09047-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="09047-216">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="09047-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="09047-217">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="09047-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="09047-218">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="09047-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="09047-219">切り替えの移動:</span><span class="sxs-lookup"><span data-stu-id="09047-219">Moving through the transition:</span></span>

- [<span data-ttu-id="09047-220">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="09047-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="09047-221">その他の作業前</span><span class="sxs-lookup"><span data-stu-id="09047-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="09047-222">Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。</span><span class="sxs-lookup"><span data-stu-id="09047-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="09047-223">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="09047-223">Cloud apps:</span></span>

- [<span data-ttu-id="09047-224">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="09047-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="09047-225">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="09047-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="09047-226">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="09047-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)