---
title: ユーザーのWindowsデバイスをMicrosoft 365 Business Premiumする
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: ユーザーにWindowsデバイスWindows 10 ProをMicrosoft 365 Business Premium、一元的な管理とセキュリティ制御を有効にします。
ms.openlocfilehash: a911414b1a7abef259f4c5fffbdd48e07f9ebfdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393361"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="b33c6-103">ユーザーのWindowsデバイスをMicrosoft 365 Business Premiumする</span><span class="sxs-lookup"><span data-stu-id="b33c6-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b33c6-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="b33c6-104">Before you begin</span></span>

<span data-ttu-id="b33c6-105">Microsoft 365 Business Premium ユーザー用に Windows デバイスをセットアップする前に、Windows のすべてのデバイスが Windows 10 Pro バージョン 1703 (Creators Update) を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33c6-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="b33c6-106">Windows 10 Proは、Windows 10 Pro を補完し、Microsoft 365 Business Premium の一元的な管理とセキュリティ制御を可能にする一連のクラウド サービスとデバイス管理機能である Windows 10 Business を展開する前提条件です。</span><span class="sxs-lookup"><span data-stu-id="b33c6-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="b33c6-107">Windows Windows、Pro、Windows 8 Pro、Windows 8.1 Pro を実行しているデバイスがある場合、Microsoft 365 Business Premium サブスクリプションは Windows 10 アップグレードを受Windows 10します。 Windows</span><span class="sxs-lookup"><span data-stu-id="b33c6-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="b33c6-108">Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](upgrade-to-windows-pro-creators-update.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b33c6-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="b33c6-109">「 [デバイスが Azure](#verify-the-device-is-connected-to-azure-ad) AD接続されていることを確認する」を参照し、アップグレードが正常に動作したと確認してください。</span><span class="sxs-lookup"><span data-stu-id="b33c6-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a><span data-ttu-id="b33c6-110">ウォッチ: ConnectをビジネスにMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="b33c6-110">Watch: Connect your PC to Microsoft 365 Business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="b33c6-111">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../business-video/index.yml)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b33c6-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../business-video/index.yml).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="b33c6-112">Windows 10 デバイスを組織の Azure AD に参加させる</span><span class="sxs-lookup"><span data-stu-id="b33c6-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="b33c6-113">組織内のすべての Windows デバイスが Windows 10 Pro Creators Update にアップグレードされている場合、または Windows 10 Pro Creators Update を既に実行している場合は、これらのデバイスを組織の Azure Active Directory に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b33c6-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="b33c6-114">デバイスが参加すると、デバイスは自動的に Windows 10 Business サブスクリプションの一部Microsoft 365 Business Premiumされます。</span><span class="sxs-lookup"><span data-stu-id="b33c6-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="b33c6-115">新しい、または新たにアップグレードした Windows 10 Pro デバイスについて</span><span class="sxs-lookup"><span data-stu-id="b33c6-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="b33c6-116">Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b33c6-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="b33c6-117">[ **設定方法**] ページが表示されるまで Windows 10 デバイスのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="b33c6-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="b33c6-119">ここでは、[組織 **のセットアップ] を選択し**、組織のユーザー名とパスワードを入力Microsoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="b33c6-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="b33c6-120">Windows 10 デバイスのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="b33c6-p103">完了すると、組織の Azure AD に接続されます。「[デバイスが Azure AD に接続されていることを確認する](#verify-the-device-is-connected-to-azure-ad)」を参照して確認します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="b33c6-123">既にセットアップして、Windows 10 Pro を実行しているデバイスの場合</span><span class="sxs-lookup"><span data-stu-id="b33c6-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="b33c6-124">**ユーザーを Azure AD に接続する**</span><span class="sxs-lookup"><span data-stu-id="b33c6-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="b33c6-125">Windows 10 Pro バージョン 1703 (Creators Update) を実行しているユーザーの Windows PC で ([前提条件](pre-requisites-for-data-protection.md)を参照)、Windows ロゴ、[設定] アイコンの順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b33c6-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="b33c6-127">[ **設定**] で [ **アカウント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="b33c6-129">On **Your info** page, click **Access work or school** \> **Connect**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="b33c6-131">[ **職場または学校アカウントの設定**] ダイアログの [ **別の操作**] の下で、[ **このデバイスを Azure Active Directory に参加させる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b33c6-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="b33c6-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="b33c6-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="b33c6-136">[組織 **の確認] ページで** 、情報が正しいか確認し、[参加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b33c6-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.</span></span>
  
   <span data-ttu-id="b33c6-137">[ **すべて完了しました。**</span><span class="sxs-lookup"><span data-stu-id="b33c6-137">On the **You're all set!**</span></span> <span data-ttu-id="b33c6-138">ページ, chosse **Done**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-138">page, chosse **Done**.</span></span>
  
   ![[組織の構成を確認する] 画面で、[参加] を選択します。](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="b33c6-140">ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="b33c6-141">サード パーティ製のツールを使用してプロファイルとファイルを移行した場合は、新しいプロファイルに同期することもできます。</span><span class="sxs-lookup"><span data-stu-id="b33c6-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="b33c6-142">デバイスが Azure AD に接続されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="b33c6-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="b33c6-143">同期の状態を確認するには、設定の [仕事または学校へのアクセス] ページで **、[** 接続済み] **_** 領域を選択して、[情報] と [切断] ボタン \<organization name\> **を表示\*\*\*\*します**。</span><span class="sxs-lookup"><span data-stu-id="b33c6-143">To verify your sync status, on the **Access work or school** page in **Settings**, select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="b33c6-144">[ **情報] を** 選択して同期の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="b33c6-145">[同期の **状態] ページで** 、[同期] **を** 選択して、最新のモバイル デバイス管理ポリシーを PC に取得します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="b33c6-146">Microsoft 365 Business Premium アカウントの使用を開始するには、[スタートWindows] ボタンに移動し、現在のアカウントの画像を右クリックし、[アカウントの切り替え]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b33c6-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="b33c6-147">自分の組織のメール アドレスとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b33c6-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="b33c6-149">PC がデバイスにアップグレードWindows 10 Business</span><span class="sxs-lookup"><span data-stu-id="b33c6-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="b33c6-150">Azure に参加しているADデバイスWindows 10サブスクリプションの一部Windows 10 BusinessアップグレードMicrosoft 365 Business Premiumします。</span><span class="sxs-lookup"><span data-stu-id="b33c6-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="b33c6-151">Go to **Settings** \> **System** \> **About**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="b33c6-152">[ **エディション**] が **Windows 10 Business** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b33c6-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="b33c6-154">次の手順</span><span class="sxs-lookup"><span data-stu-id="b33c6-154">Next steps</span></span>

<span data-ttu-id="b33c6-155">モバイル デバイスをセットアップするには、「Microsoft 365 Business Premium ユーザー用のモバイル デバイスをセットアップする[」、](set-up-mobile-devices.md)デバイス保護ポリシーまたはアプリ保護ポリシーを設定するには、「ビジネス向けモバイル デバイスの管理Microsoft 365」を参照[してください](manage.md)。</span><span class="sxs-lookup"><span data-stu-id="b33c6-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="related-content"></a><span data-ttu-id="b33c6-156">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="b33c6-156">Related content</span></span>

<span data-ttu-id="b33c6-157">[一般法人向け Microsoft 365 のトレーニング ビデオ](../business-video/index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="b33c6-157">[Microsoft 365 for business training videos](../business-video/index.yml) (link page)</span></span>
