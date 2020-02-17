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
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Microsoft 365 Business ユーザーの Windows デバイスをセットアップする

## <a name="prerequisites"></a>前提条件

Microsoft 365 Business ユーザーの Windows デバイスをセットアップするには、すべての Windows デバイスで、Windows 10 Pro バージョン 1703 (Creators Update) が実行されていることを確認します。Windows 10 Pro は、Windows 10 Business を展開するための前提条件です。これは、Windows 10 Pro を補完し、Microsoft 365 Business の一元管理とセキュリティ制御を有効にする一連のクラウド サービスとデバイス管理機能です
  
Windows 7 Pro、Windows 8 Pro、Windows 8.1 Pro を実行している Windows デバイスをお使いの場合は、Microsoft 365 Business サブスクリプションをご利用いただくことで Windows 10 にアップグレードできます。
  
Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](upgrade-to-windows-pro-creators-update.md)」の手順に従います。
  
アップグレードが完了していることを確認するには、[[デバイスが AZURE AD に接続されていること](#verify-the-device-is-connected-to-azure-ad)を確認する] を参照してください。

Microsoft 365 への Windows の接続に関する短いビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 デバイスを組織の Azure AD に参加させる

組織内のすべての Windows デバイスを Windows 10 Pro クリエーターの更新プログラムにアップグレードするか、または Windows 10 Pro クリエーターの更新プログラムを既に実行している場合は、これらのデバイスを組織の Azure Active Directory に参加させることができます。 参加したデバイスは、Microsoft 365 Business サブスクリプションの一部である Windows 10 Business に自動的にアップグレードされます。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>新しい、または新たにアップグレードした Windows 10 Pro デバイスについて

Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。
  
1. [ **設定方法**] ページが表示されるまで Windows 10 デバイスのセットアップを行います。 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. ここでは、[ **組織用に設定**] を選び、Microsoft 365 Business のユーザー名とパスワードを入力します。 
    
3. Windows 10 デバイスのセットアップを完了します。
    
   完了すると、組織の Azure AD に接続されます。「[デバイスが Azure AD に接続されていることを確認する](#verify-the-device-is-connected-to-azure-ad)」を参照して確認します。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>既にセットアップして、Windows 10 Pro を実行しているデバイスの場合

 **ユーザーを Azure AD に接続する**
  
1. Windows 10 Pro バージョン 1703 (Creators Update) を実行しているユーザーの Windows PC で ([前提条件](pre-requisites-for-data-protection.md)を参照)、Windows ロゴ、[設定] アイコンの順にクリックします。
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. [ **設定**] で [ **アカウント**] に移動します。
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. On **Your info** page, click **Access work or school** \> **Connect**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. [ **職場または学校アカウントの設定**] ダイアログの [ **別の操作**] の下で、[ **このデバイスを Azure Active Directory に参加させる**] を選びます。
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. [**組織が組織**であることを確認してください] ページで、情報が正しいことを確認し、[**参加**] をクリックします。
  
   [ **すべて完了しました。**] ページで、[ **完了**] をクリックします。
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。 サードパーティ製のツールを使用してプロファイルとファイルを移行した場合は、それらを新しいプロファイルにも同期します。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

同期の状態を確認するには、[ **職場または学校にアクセスする**] ページの [ **設定**] で、[ **接続先** _ \<organization name\> _] 領域内をクリックして、[ **情報**] と [ **切断**] ボタンを表示します。[ **情報**] をクリックして同期状態を取得します。 
  
[同期の状態] ページで、[同期] をクリックして PC で最新のモバイル デバイス管理ポリシーを取得します。
  
Microsoft 365 Business アカウントの使用を開始するには、Windows の [**スタート**] ボタンに移動し、現在のアカウントの画像を右クリックして、**アカウントを切り替え**ます。 自分の組織のメール アドレスとパスワードを使用してサインインします。
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>デバイスが Windows 10 Business にアップグレードしたことを確認する

Microsoft 365 Business サブスクリプションの一部として、Azure AD に参加した Windows 10 デバイスが Windows 10 Business にアップグレードしたことを確認します。
  
1. Go to **Settings** \> **System** \> **About**.
    
2. [ **エディション**] が **Windows 10 Business** であることを確認します。
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>次の手順

モバイル デバイスをセットアップするには、「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。デバイス保護ポリシーまたはアプリ保護ポリシーを設定するには、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 Business のトレーニング ビデオ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
