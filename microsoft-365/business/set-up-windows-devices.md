---
title: Microsoft 365 Business ユーザーの Windows デバイスをセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: '365 ビジネスユーザに 10 Pro の Windows を実行している Windows のデバイスを設定する方法について説明します。 '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869212"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Microsoft 365 Business ユーザーの Windows デバイスをセットアップする

## <a name="prerequisites"></a>前提条件

Microsoft 365 Business ユーザーの Windows デバイスをセットアップするには、すべての Windows デバイスで、Windows 10 Pro バージョン 1703 (Creators Update) が実行されていることを確認します。Windows 10 Pro は、Windows 10 Business を展開するための前提条件です。これは、Windows 10 Pro を補完し、Microsoft 365 Business の一元管理とセキュリティ制御を有効にする一連のクラウド サービスとデバイス管理機能です
  
Windows 7 Pro、Windows 8 Pro、Windows 8.1 Pro を実行している Windows デバイスをお使いの場合は、Microsoft 365 Business サブスクリプションをご利用いただくことで Windows 10 にアップグレードできます。
  
Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](upgrade-to-windows-pro-creators-update.md)」の手順に従います。
  
「[デバイスが Windows 10 Business にアップグレードしたことを確認する](set-up-windows-devices.md#bkmk_verifywin10)」を参照して、アップグレードされていることを確認するか、アップグレードが機能していることを確認します。 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 デバイスを組織の Azure AD に参加させる

組織内のすべての Windows デバイスを Windows 10 Pro Creators Update にアップグレードしたか、既に Windows 10 Pro Creators Update が実行されている場合は、これらのデバイスを組織の Azure Active Directory に参加させることができます。デバイスを参加させると、デバイスは自動的に Windows 10 Business にアップグレードされます。これは、Microsoft 365 Business サブスクリプションの一部です。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>新しい、または新たにアップグレードした Windows 10 Pro デバイスについて

Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。
  
1. [ **設定方法**] ページが表示されるまで Windows 10 デバイスのセットアップを行います。 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. ここでは、[ **組織用に設定**] を選び、Microsoft 365 Business のユーザー名とパスワードを入力します。 
    
3. Windows 10 デバイスのセットアップを完了します。
    
   完了すると、組織の Azure AD に接続されます。「[デバイスが Azure AD に接続されていることを確認する](set-up-windows-devices.md#bkmk_verifyaad)」を参照して確認します。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>既にセットアップして、Windows 10 Pro を実行しているデバイスの場合

 **ユーザーを Azure AD に接続する**
  
1. Windows 10 Pro バージョン 1703 (Creators Update) を実行しているユーザーの Windows PC で ([前提条件](pre-requisites-for-data-protection.md)を参照)、Windows ロゴ、[設定] アイコンの順にクリックします。
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. [ **設定**] で [ **アカウント**] に移動します。
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. **情報]** ページでは、「**アクセスの職場または学校**の使用」をクリックしていますください。 \> **接続**します。
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. [ **職場または学校アカウントの設定**] ダイアログの [ **別の操作**] の下で、[ **このデバイスを Azure Active Directory に参加させる**] を選びます。
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. **取得署名する**] ページで、職場、学校のアカウントを入力してください\>**次**です。
  
   [**パスワードの入力**] ページで、パスワードを入力します\>**にサインイン**します。
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. * * これは、組織になっていることを確認 * * ページ、情報が正しいことを確認し、[**参加**] をクリックします。
  
   [ **すべて完了しました。**] ページで、[ **完了**] をクリックします。
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。サードパーティ製のツールを使用してプロファイルとファイルを移行した場合は、これらも新しいプロファイルに同期します。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

同期の状態を確認するには、[ **職場または学校にアクセスする**] ページの [ **設定**] で、[ **接続先** _ \<organization name\> _] 領域内をクリックして、[ **情報**] と [ **切断**] ボタンを表示します。[ **情報**] をクリックして同期状態を取得します。 
  
[同期の状態] ページで、[同期] をクリックして PC で最新のモバイル デバイス管理ポリシーを取得します。
  
Microsoft 365 Business アカウントの使用を開始するには、Windows の [ **開始**] ボタンに移動し、現在のアカウントの画像を右クリックして、[ **アカウントの切り替え**] をクリックします。自分の組織のメール アドレスとパスワードを使用してサインインします。
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>デバイスが Windows 10 Business にアップグレードしたことを確認する

Microsoft 365 Business サブスクリプションの一部として、Azure AD に参加した Windows 10 デバイスが Windows 10 Business にアップグレードしたことを確認します。
  
1. **設定**に\>**システム** \> **について**です。
    
2. [ **エディション**] が **Windows 10 Business** であることを確認します。
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>次のステップ

モバイル デバイスをセットアップするには、「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。デバイス保護ポリシーまたはアプリ保護ポリシーを設定するには、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。
  
