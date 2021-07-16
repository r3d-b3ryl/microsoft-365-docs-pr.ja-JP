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
ms.openlocfilehash: 1eb7b18360cefeeb2d5770c3d77e564d5a757a5e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453569"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="90f0a-103">Microsoft Cloud Deutschland からの移行に関するその他のデバイス情報</span><span class="sxs-lookup"><span data-stu-id="90f0a-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="90f0a-104">Azure AD、Microsoft Cloud Deutschland に接続されている登録済みデバイスは、フェーズ 9 以降およびフェーズ 10 より前に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="90f0a-105">デバイスの移行は、デバイスの種類、オペレーティング システム、および Azure のADされます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span>

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="90f0a-106">Azure AD参加Windows 10デバイス</span><span class="sxs-lookup"><span data-stu-id="90f0a-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="90f0a-107">デバイスが Azure Windows 10参加しているAD、Azure デバイスから切断され、再び接続AD必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span>

<span data-ttu-id="90f0a-108">[![Azure AD デバイス Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="90f0a-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="90f0a-109">ユーザーが Windows 10 デバイスの管理者である場合、ユーザーは Azure AD からデバイスの登録を解除し、3 つの手順で再度参加できます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="90f0a-110">手順 1: デバイスが Azure ID に参加しているかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="90f0a-110">Step 1: Determine if the device is Azure ID joined</span></span>

1. <span data-ttu-id="90f0a-111">職場アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-111">Sign in with your work account.</span></span>
2. <span data-ttu-id="90f0a-112">[アカウントアクセス設定  >    >  **ワークまたは学校] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="90f0a-113">**[...]' に接続されているアカウントを一覧で探します。s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="90f0a-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span>
4. <span data-ttu-id="90f0a-114">接続されているアカウントが存在する場合は、手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-114">If a connected account exists, proceed with Step 2.</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="90f0a-115">手順 2: Azure サーバーからデバイスを切断AD</span><span class="sxs-lookup"><span data-stu-id="90f0a-115">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="90f0a-116">接続されている **作業時間または** 学校アカウントで [切断] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-116">Click **Disconnect** on the connected work or School Account.</span></span>
2. <span data-ttu-id="90f0a-117">切断を 2 回確認します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-117">Confirm the disconnect twice.</span></span>
3. <span data-ttu-id="90f0a-118">ローカル管理者のユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="90f0a-119">デバイスが切断されています。</span><span class="sxs-lookup"><span data-stu-id="90f0a-119">The device is disconnected.</span></span>
4. <span data-ttu-id="90f0a-120">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-120">Restart the device.</span></span>

### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="90f0a-121">手順 3: デバイスを Azure デバイスに参加AD</span><span class="sxs-lookup"><span data-stu-id="90f0a-121">Step 3: Join the device to Azure AD</span></span>

1. <span data-ttu-id="90f0a-122">ローカル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-122">Sign in with the credentials of the local administrator.</span></span>
2. <span data-ttu-id="90f0a-123">[アカウントアクセス設定  >    >  **ワークまたは学校] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="90f0a-124">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-124">Click **Connect**.</span></span>
4. <span data-ttu-id="90f0a-125">**重要**: **[Azure に参加] をクリックAD。**</span><span class="sxs-lookup"><span data-stu-id="90f0a-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5. <span data-ttu-id="90f0a-126">仕事用アカウントの電子メール アドレスとパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="90f0a-127">デバイスが接続されています。</span><span class="sxs-lookup"><span data-stu-id="90f0a-127">The device is connected.</span></span>
6. <span data-ttu-id="90f0a-128">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-128">Restart the device.</span></span>
7. <span data-ttu-id="90f0a-129">仕事用アカウントのメール アドレスとパスワードでサインインします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="90f0a-130">ユーザーがデバイスの管理者ではない場合、Azure AD グローバル管理者は、この構成パスに従ってデバイスにローカル管理者アカウントを作成し、デバイスに接続を解除できます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="90f0a-131">*設定 > アカウント > アカウント >資格情報不明 > Microsoft-Account を使用せずにユーザーを追加する*</span><span class="sxs-lookup"><span data-stu-id="90f0a-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="90f0a-132">再参加の場合、組織の任意の作業アカウントの資格情報をこの手順で使用できます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span>

<span data-ttu-id="90f0a-133">デバイスに参加するために使用される作業アカウントは、デバイスの管理者として自動的に昇格されます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="90f0a-134">組織の他の仕事用アカウントはデバイスにサインインできますが、管理者権限はありません。</span><span class="sxs-lookup"><span data-stu-id="90f0a-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="90f0a-135">Azure ADデバイスに登録された (workplace-joined) Windows 10デバイス</span><span class="sxs-lookup"><span data-stu-id="90f0a-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>

<span data-ttu-id="90f0a-136">デバイスが azure Windows 10登録されているAD場合は、Azure デバイスから切断され、再度接続AD必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="90f0a-137">[![Azure AD デバイス Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="90f0a-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="90f0a-138">手順 1: デバイスが Azure ID 登録かどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="90f0a-138">Step 1: Determine if the device is Azure ID registered</span></span>

1. <span data-ttu-id="90f0a-139">ユーザーと一緒にサインインします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-139">Sign in with your user.</span></span>
2. <span data-ttu-id="90f0a-140">[アカウントアクセス設定  >    >  **ワークまたは学校] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="90f0a-141">一覧で作業用アカウントを検出し **、[....]に接続されていることを確認します。s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="90f0a-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="90f0a-142">仕事用アカウントが一覧にあるのに Azure サーバーに接続されていない場合AD手順 2 に進みます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="90f0a-143">それ以外の場合、デバイスは Azure AD参加しているデバイスであり、Azure AD参加デバイスWindows 10[必要があります](#azure-ad-joined-windows-10-devices)。</span><span class="sxs-lookup"><span data-stu-id="90f0a-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="90f0a-144">手順 2: Azure サーバーからデバイスを切断AD</span><span class="sxs-lookup"><span data-stu-id="90f0a-144">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="90f0a-145">仕事用アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-145">Click on your work account.</span></span> <span data-ttu-id="90f0a-146">[情報] ボタン *と [切断* ] *ボタンが* 表示されます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-146">The buttons *Info* and *Disconnect* appear.</span></span>
2. <span data-ttu-id="90f0a-147">[切断 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-147">Click **Disconnect**.</span></span>
3. <span data-ttu-id="90f0a-148">[はい] をクリックして、デバイスからのアカウントの削除を **確認します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-148">Confirm account removal from the device by clicking **Yes**.</span></span>

### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="90f0a-149">手順 3: Connect Azure デバイスに接続AD</span><span class="sxs-lookup"><span data-stu-id="90f0a-149">Step 3: Connect the device to Azure AD</span></span>

1. <span data-ttu-id="90f0a-150">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-150">Click **Connect**.</span></span>
2. <span data-ttu-id="90f0a-151">仕事用アカウントのメール アドレスを入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-151">Enter the email address of your work account and click **Next**.</span></span>
3. <span data-ttu-id="90f0a-152">仕事用アカウントのパスワードを入力し、[サインイン] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-152">Enter the password of your work account and click **Sign in**.</span></span>
4. <span data-ttu-id="90f0a-153">[完了] をクリックして **確認します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="90f0a-154">作業アカウントが再び表示されます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="90f0a-155">Android</span><span class="sxs-lookup"><span data-stu-id="90f0a-155">Android</span></span>

<span data-ttu-id="90f0a-156">Android の場合、ユーザーはデバイスの登録を解除して再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="90f0a-157">これは、アプリまたはアプリMicrosoft Authenticator使用してポータル サイトできます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span>

- <span data-ttu-id="90f0a-158">アプリからMicrosoft Authenticatorデバイス登録に移動設定 >**できます**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="90f0a-159">そこから、ユーザーはデバイスの登録を解除して再登録できます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-159">From there users can unregister and re-register their device.</span></span>

- <span data-ttu-id="90f0a-160">[デバイス] ポータル サイト[デバイス]**タブに** 移動し、デバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="90f0a-161">その後、デバイスを使用してデバイスを再登録ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="90f0a-161">After that, re-enroll the device by using Company Portal.</span></span>

- <span data-ttu-id="90f0a-162">ユーザーは、アカウント設定ページからアカウントを削除してから、作業アカウントを再追加することで、登録を解除して再登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="90f0a-163">Android アプリを使用してデバイスの登録を解除して再登録するには、次Microsoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1. <span data-ttu-id="90f0a-164">アプリを開Microsoft Authenticatorに移動し、[設定]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2. <span data-ttu-id="90f0a-165">[デバイス **登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-165">Select **Device registration**.</span></span>
3. <span data-ttu-id="90f0a-166">[登録解除] を選択してデバイスの登録を **解除します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-166">Unregister the device by selecting **Unregister**.</span></span>
4. <span data-ttu-id="90f0a-167">[ **デバイスの登録]** で、電子メール アドレスを入力してデバイスを再登録し、[登録] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="90f0a-168">Android デバイスの登録を解除して、Android デバイスを再登録するには、次設定します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1. <span data-ttu-id="90f0a-169">[デバイス **] ウィンドウ設定** 開き、[アカウント] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-169">Open **Device Settings** and go to **Accounts**.</span></span>
2. <span data-ttu-id="90f0a-170">再登録する作業アカウントを選択し、[アカウントの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3. <span data-ttu-id="90f0a-171">アカウントを削除した後、[アカウント] ページ **で** 、[アカウントの追加] **を選択し、[>] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4. <span data-ttu-id="90f0a-172">[Workplace **Join] で**、電子メール アドレスを入力し、[参加] を **選択** してデバイスの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="90f0a-173">Android でデバイスの登録を解除して再登録するには、次ポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="90f0a-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1. <span data-ttu-id="90f0a-174">[デバイスポータル サイト起動し、[デバイス] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-174">Launch Company Portal and go to **Devices** tab.</span></span>
2. <span data-ttu-id="90f0a-175">デバイスを選択すると、デバイスの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-175">Select the device to see the device details.</span></span>
3. <span data-ttu-id="90f0a-176">省略記号 (3 つのドット)メニューから [デバイスの削除] を選択し、ダイアログで確認して削除を完了します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4. <span data-ttu-id="90f0a-177">これで、アプリからログアウトポータル サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="90f0a-178">[ **サインイン] を選択** してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="90f0a-179">このワークロードの移行フェーズ中に必要なアクション、または管理または使用状況への影響の詳細については[、「Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)からの移行に関する Azure AD の追加情報」の「Azure Active Directory (Azure AD) に関する情報」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90f0a-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="90f0a-180">iOS</span><span class="sxs-lookup"><span data-stu-id="90f0a-180">iOS</span></span>

<span data-ttu-id="90f0a-181">iOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除し、デバイス上のネイティブ アプリからサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="90f0a-182">手順 1: 存在する場合は、アプリからアカウントMicrosoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="90f0a-183">アプリでアカウントをタップMicrosoft Authenticatorします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="90f0a-184">右上隅にある **設定** アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="90f0a-185">このアイコンが表示 **されない設定、** 最新バージョンのファイルを使用していない可能性Microsoft Authenticator。</span><span class="sxs-lookup"><span data-stu-id="90f0a-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="90f0a-186">[アカウントの **削除] ボタンをタップ** します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="90f0a-187">[この **デバイスのすべてのアプリ] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-187">Tap **All apps on this device**.</span></span>

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="90f0a-188">手順 2: アプリからデバイスの登録をMicrosoft Authenticatorする</span><span class="sxs-lookup"><span data-stu-id="90f0a-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="90f0a-189">右上隅にあるメニュー アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="90f0a-190">[デバイス **設定]** をタップし、[デバイス **登録] をタップします**。</span><span class="sxs-lookup"><span data-stu-id="90f0a-190">Tap **Settings** and then **Device Registration**.</span></span>
3. <span data-ttu-id="90f0a-191">アカウントが表示されている場合は、[デバイスの登録を **解除] をタップ** し、ダイアログで [ **続行** ] をタップします。</span><span class="sxs-lookup"><span data-stu-id="90f0a-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="90f0a-192">その後、アカウントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="90f0a-192">You should see no account after that.</span></span>

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="90f0a-193">手順 3: 必要に応じて、個々のアプリからサインアウトする</span><span class="sxs-lookup"><span data-stu-id="90f0a-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="90f0a-194">ユーザーは、個々のアプリ (Outlook、Teams、OneDrive、それらのアプリからアカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="90f0a-195">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="90f0a-195">Frequently asked questions</span></span>

<span data-ttu-id="90f0a-196">**組織が影響を受けるかを確認する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="90f0a-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="90f0a-197">管理者は、Azure アカウントが登録済みか `https://portal.microsoftazure.de` 、または Azure AD参加AD確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="90f0a-198">組織に Azure ADまたは Azure AD参加している場合、組織は、このページの指示に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="90f0a-199">**ユーザーがデバイスを再登録する場合**</span><span class="sxs-lookup"><span data-stu-id="90f0a-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="90f0a-200">フェーズ [9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) の完了後にデバイスの登録を解除して再登録する必要がある場合は、成功にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="90f0a-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="90f0a-201">フェーズ 10 が開始する前に再登録を完了する必要があります。それ以外の場合は、デバイスへのアクセスが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="90f0a-202">**すべてのデバイスがパブリック クラウドに登録されているのを知る方法**</span><span class="sxs-lookup"><span data-stu-id="90f0a-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="90f0a-203">デバイスがパブリック クラウドに登録されているかどうかを確認するには、Azure AD ポータルからデバイスのリストをエクスポートして、Excelする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="90f0a-204">次に、組織が移行プロセスのフェーズ 9 を通過した日付の後に 、登録されているデバイスを _(registeredTime_ 列を使用して) [フィルター処理します](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)。</span><span class="sxs-lookup"><span data-stu-id="90f0a-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

<span data-ttu-id="90f0a-205">**「Microsoft の DNS レコードを作成する」に記載されている DNS 名を追加する必要がある場合は、Windows [ベースの DNS を使用しますか](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?view=o365-worldwide#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)。**</span><span class="sxs-lookup"><span data-stu-id="90f0a-205">**Do I still need to add the DNS name as stated in [Create DNS records for Microsoft using Windows-based DNS](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?view=o365-worldwide#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)?**</span></span>

<span data-ttu-id="90f0a-206">この DNS エントリは、デバイスの再登録には不要です。</span><span class="sxs-lookup"><span data-stu-id="90f0a-206">This DNS entry is no longer needed for re-registering your device.</span></span> 

## <a name="additional-considerations"></a><span data-ttu-id="90f0a-207">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="90f0a-207">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90f0a-208">Intune サービス プリンシパルは、移行プロセスのフェーズ [3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)の後に有効になります。これは、デバイス登録に対する Azure ADを意味します。</span><span class="sxs-lookup"><span data-stu-id="90f0a-208">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="90f0a-209">移行前に Azure AD デバイス登録をブロックした場合は、PowerShell を使用して Intune サービス プリンシパルを無効にして、Azure AD デバイス登録を Azure AD ポータルで再度無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f0a-209">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="90f0a-210">このコマンドを使用して Intune サービス プリンシパルを無効にAzure Active Directory PowerShell Graphできます。</span><span class="sxs-lookup"><span data-stu-id="90f0a-210">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="90f0a-211">詳細情報</span><span class="sxs-lookup"><span data-stu-id="90f0a-211">More information</span></span>

<span data-ttu-id="90f0a-212">はじめに:</span><span class="sxs-lookup"><span data-stu-id="90f0a-212">Getting started:</span></span>

- [<span data-ttu-id="90f0a-213">Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="90f0a-213">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="90f0a-214">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="90f0a-214">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="90f0a-215">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="90f0a-215">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="90f0a-216">移行中のカスタマー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="90f0a-216">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="90f0a-217">切り替えの移動:</span><span class="sxs-lookup"><span data-stu-id="90f0a-217">Moving through the transition:</span></span>

- [<span data-ttu-id="90f0a-218">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="90f0a-218">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="90f0a-219">その他の作業前</span><span class="sxs-lookup"><span data-stu-id="90f0a-219">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="90f0a-220">Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。</span><span class="sxs-lookup"><span data-stu-id="90f0a-220">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="90f0a-221">クラウド アプリ:</span><span class="sxs-lookup"><span data-stu-id="90f0a-221">Cloud apps:</span></span>

- [<span data-ttu-id="90f0a-222">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="90f0a-222">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="90f0a-223">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="90f0a-223">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="90f0a-224">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="90f0a-224">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
