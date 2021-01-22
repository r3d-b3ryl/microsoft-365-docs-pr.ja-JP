---
title: Microsoft 365 Business Premium ユーザー向け Windows デバイスのセットアップ
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
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Microsoft 365 Business Premium ユーザー向け Windows 10 Pro を実行している Windows デバイスをセットアップして、一元管理とセキュリティ制御を有効にする方法について説明します。
ms.openlocfilehash: b1877d83f113a2ba23d0db374967e0afcd7fe067
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928726"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium ユーザー向け Windows デバイスのセットアップ

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium ユーザー向け Windows デバイスをセットアップするための前提条件

Microsoft 365 Business Premium ユーザー向け Windows デバイスをセットアップする前に、すべての Windows デバイスで Windows 10 Pro バージョン 1703 (Creators Update) が実行されている必要があります。 Windows 10 Pro は、Windows 10 Business を展開する前提条件です。これは、Windows 10 Pro を補完し、Microsoft 365 Business Premium の一元的な管理とセキュリティ制御を可能にする一連のクラウド サービスとデバイス管理機能です。
  
Windows 7 Pro、Windows 8 Pro、または Windows 8.1 Pro を実行している Windows デバイスがある場合、Microsoft 365 Business Premium サブスクリプションは Windows 10 のアップグレードを受ける権利を持っています。
  
Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](upgrade-to-windows-pro-creators-update.md)」の手順に従います。
  
「 [デバイスが Azure AD に](#verify-the-device-is-connected-to-azure-ad) 接続されていることを確認する」を参照して、アップグレードが完了したのか確認してください。

Windows から Microsoft 365 への接続に関する短いビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 デバイスを組織の Azure AD に参加させる

組織内のすべての Windows デバイスが Windows 10 Pro Creators Update にアップグレードされている場合、または既に Windows 10 Pro Creators Update を実行している場合は、これらのデバイスを組織の Azure Active Directory に参加できます。 デバイスが参加すると、Microsoft 365 Business Premium サブスクリプションの一部である Windows 10 Business に自動的にアップグレードされます。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>新しい、または新たにアップグレードした Windows 10 Pro デバイスについて

Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。
  
1. [ **設定方法**] ページが表示されるまで Windows 10 デバイスのセットアップを行います。 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. ここで、[組織の **セットアップ] を** 選択し、Microsoft 365 Business Premium のユーザー名とパスワードを入力します。 
    
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
  
6. On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join**.
  
   [ **すべて完了しました。** page,100,000 
  
   ![On the Make sure this is your organization screen, choose Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。 サード パーティ製のツールを使用してプロファイルとファイルを移行した場合は、それらのツールを新しいプロファイルと同期します。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

To verify your sync status, on the **Access work or school** page in **Settings,** select the **Connected to** _ area to expose \<organization name\> the buttons **Info** and **Disconnect**. [ **情報] を** 選択して同期状態を取得します。 
  
[同期 **の状態] ページ** で、[ **同期** ] を選択して最新のモバイル デバイス管理ポリシーを PC に適用します。
  
Microsoft 365 Business Premium アカウントの使用を開始するには、Windows **の** [スタート] ボタンに移動し、現在のアカウントの画像を右クリックして、アカウントを **切り替えます**。 自分の組織のメール アドレスとパスワードを使用してサインインします。
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>PC が Windows 10 Business にアップグレードされたのを確認する

Azure AD参加している Windows 10 デバイスが、Microsoft 365 Business Premium サブスクリプションの一部として Windows 10 Business にアップグレードされます。
  
1. Go to **Settings** \> **System** \> **About**.
    
2. [ **エディション**] が **Windows 10 Business** であることを確認します。
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>次の手順

モバイル デバイスをセットアップするには [、「Microsoft 365 Business Premium](set-up-mobile-devices.md)ユーザー向けモバイル デバイスのセットアップ」、デバイス保護ポリシーまたはアプリ保護ポリシーを設定するには [、「Microsoft 365 for business](manage.md)の管理」を参照してください。
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Microsoft 365 Business Premium のセットアップと使用の詳細

[一般法人向け Microsoft 365 のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
