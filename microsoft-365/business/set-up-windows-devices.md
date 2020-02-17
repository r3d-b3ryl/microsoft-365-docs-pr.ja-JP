---
title: Microsoft 365 Business ユーザーの Windows デバイスをセットアップする
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Microsoft 365 Business ユーザー用に Windows 10 Pro を実行している Windows デバイスをセットアップする方法について説明します。 '
ms.openlocfilehash: 427e1c25b5c6ad52ab280502133a0e2808bb48b1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42090714"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="954de-103">Microsoft 365 Business ユーザーの Windows デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="954de-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="954de-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="954de-104">Prerequisites</span></span>

<span data-ttu-id="954de-p101">Microsoft 365 Business ユーザーの Windows デバイスをセットアップするには、すべての Windows デバイスで、Windows 10 Pro バージョン 1703 (Creators Update) が実行されていることを確認します。Windows 10 Pro は、Windows 10 Business を展開するための前提条件です。これは、Windows 10 Pro を補完し、Microsoft 365 Business の一元管理とセキュリティ制御を有効にする一連のクラウド サービスとデバイス管理機能です</span><span class="sxs-lookup"><span data-stu-id="954de-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="954de-107">Windows 7 Pro、Windows 8 Pro、Windows 8.1 Pro を実行している Windows デバイスをお使いの場合は、Microsoft 365 Business サブスクリプションをご利用いただくことで Windows 10 にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="954de-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="954de-108">Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](upgrade-to-windows-pro-creators-update.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="954de-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="954de-109">アップグレードが完了していることを確認するには、[[デバイスが AZURE AD に接続されていること](#verify-the-device-is-connected-to-azure-ad)を確認する] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="954de-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="954de-110">Microsoft 365 への Windows の接続に関する短いビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="954de-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="954de-111">このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="954de-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="954de-112">Windows 10 デバイスを組織の Azure AD に参加させる</span><span class="sxs-lookup"><span data-stu-id="954de-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="954de-113">組織内のすべての Windows デバイスを Windows 10 Pro クリエーターの更新プログラムにアップグレードするか、または Windows 10 Pro クリエーターの更新プログラムを既に実行している場合は、これらのデバイスを組織の Azure Active Directory に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="954de-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="954de-114">参加したデバイスは、Microsoft 365 Business サブスクリプションの一部である Windows 10 Business に自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="954de-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="954de-115">新しい、または新たにアップグレードした Windows 10 Pro デバイスについて</span><span class="sxs-lookup"><span data-stu-id="954de-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="954de-116">Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="954de-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="954de-117">[ **設定方法**] ページが表示されるまで Windows 10 デバイスのセットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="954de-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="954de-119">ここでは、[ **組織用に設定**] を選び、Microsoft 365 Business のユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="954de-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="954de-120">Windows 10 デバイスのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="954de-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="954de-p103">完了すると、組織の Azure AD に接続されます。「[デバイスが Azure AD に接続されていることを確認する](#verify-the-device-is-connected-to-azure-ad)」を参照して確認します。</span><span class="sxs-lookup"><span data-stu-id="954de-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="954de-123">既にセットアップして、Windows 10 Pro を実行しているデバイスの場合</span><span class="sxs-lookup"><span data-stu-id="954de-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="954de-124">**ユーザーを Azure AD に接続する**</span><span class="sxs-lookup"><span data-stu-id="954de-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="954de-125">Windows 10 Pro バージョン 1703 (Creators Update) を実行しているユーザーの Windows PC で ([前提条件](pre-requisites-for-data-protection.md)を参照)、Windows ロゴ、[設定] アイコンの順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="954de-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="954de-127">[ **設定**] で [ **アカウント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="954de-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="954de-129">On **Your info** page, click **Access work or school** \> **Connect**.</span><span class="sxs-lookup"><span data-stu-id="954de-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="954de-131">[ **職場または学校アカウントの設定**] ダイアログの [ **別の操作**] の下で、[ **このデバイスを Azure Active Directory に参加させる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="954de-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="954de-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="954de-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="954de-134">On the **Enter password** page, enter your password \> **Sign in**.</span><span class="sxs-lookup"><span data-stu-id="954de-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="954de-136">[**組織が組織**であることを確認してください] ページで、情報が正しいことを確認し、[**参加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="954de-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="954de-p104">[ **すべて完了しました。**] ページで、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="954de-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="954de-140">ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。</span><span class="sxs-lookup"><span data-stu-id="954de-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="954de-141">サードパーティ製のツールを使用してプロファイルとファイルを移行した場合は、それらを新しいプロファイルにも同期します。</span><span class="sxs-lookup"><span data-stu-id="954de-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="954de-142">デバイスが Azure AD に接続されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="954de-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="954de-p106">同期の状態を確認するには、[ **職場または学校にアクセスする**] ページの [ **設定**] で、[ **接続先** _ \<organization name\> _] 領域内をクリックして、[ **情報**] と [ **切断**] ボタンを表示します。[ **情報**] をクリックして同期状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="954de-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="954de-145">[同期の状態] ページで、[同期] をクリックして PC で最新のモバイル デバイス管理ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="954de-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="954de-146">Microsoft 365 Business アカウントの使用を開始するには、Windows の [**スタート**] ボタンに移動し、現在のアカウントの画像を右クリックして、**アカウントを切り替え**ます。</span><span class="sxs-lookup"><span data-stu-id="954de-146">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="954de-147">自分の組織のメール アドレスとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="954de-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="954de-149">デバイスが Windows 10 Business にアップグレードしたことを確認する</span><span class="sxs-lookup"><span data-stu-id="954de-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="954de-150">Microsoft 365 Business サブスクリプションの一部として、Azure AD に参加した Windows 10 デバイスが Windows 10 Business にアップグレードしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="954de-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="954de-151">Go to **Settings** \> **System** \> **About**.</span><span class="sxs-lookup"><span data-stu-id="954de-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="954de-152">[ **エディション**] が **Windows 10 Business** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="954de-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="954de-154">次の手順</span><span class="sxs-lookup"><span data-stu-id="954de-154">Next steps</span></span>

<span data-ttu-id="954de-155">モバイル デバイスをセットアップするには、「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。デバイス保護ポリシーまたはアプリ保護ポリシーを設定するには、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="954de-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="954de-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="954de-156">See also</span></span>

[<span data-ttu-id="954de-157">Microsoft 365 Business のトレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="954de-157">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
