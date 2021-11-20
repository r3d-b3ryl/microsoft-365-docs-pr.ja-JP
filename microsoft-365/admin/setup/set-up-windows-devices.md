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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: ユーザーにWindowsデバイスWindows 10 ProをMicrosoft 365 Business Premium、一元的な管理とセキュリティ制御を有効にします。
ms.openlocfilehash: 250c701a41e9243c81641df2bcc0fd6d6158ec47
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2021
ms.locfileid: "61128654"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>ユーザーのWindowsデバイスをMicrosoft 365 Business Premiumする

## <a name="before-you-begin"></a>はじめに

Microsoft 365 Business Premium ユーザー用に Windows デバイスをセットアップする前に、Windows のすべてのデバイスが Windows 10 Pro バージョン 1703 (Creators Update) を実行している必要があります。 Windows 10 Proは、Windows 10 Business を補完し、Windows 10 Pro の一元的な管理とセキュリティ制御を可能にする一連のクラウド サービスとデバイス管理機能である Windows 10 Business を展開する前提条件です。Microsoft 365 Business Premium。
  
Windows Windows、Pro、Windows 8 Pro、Windows 8.1 Pro を実行しているデバイスがある場合、Microsoft 365 Business Premium サブスクリプションは Windows 10 アップグレードを受Windows 10します。 Windows
  
Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](../../business-video/upgrade.md)」の手順に従います。
  
「[デバイスがデバイスに接続されていることを確認](#verify-the-device-is-connected-to-azure-ad)Azure ADアップグレードを確認するか、アップグレードが正常に動作したのを確認する」を参照してください。

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a>ウォッチ: ConnectをビジネスにMicrosoft 365する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 デバイスを組織の Azure AD に参加させる

組織内のすべての Windows デバイスが Windows 10 Pro Creators Update にアップグレードされている場合、または Windows 10 Pro Creators Update を既に実行している場合は、これらのデバイスを組織の Azure Active Directory に参加できます。 デバイスが参加すると、デバイスは自動的に Windows 10 Business サブスクリプションの一部Microsoft 365 Business Premiumされます。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>新しい、または新たにアップグレードした Windows 10 Pro デバイスについて

Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。
  
1. [ **設定方法**] ページが表示されるまで Windows 10 デバイスのセットアップを行います。 
    
    ![[設定方法] ページで、[組織のセットアップ] を選択します。](../../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. ここでは、[組織 **のセットアップ] を選択し**、組織のユーザー名とパスワードを入力Microsoft 365 Business Premium。 
    
3. Windows 10 デバイスのセットアップを完了します。
    
   完了すると、組織の Azure AD に接続されます。「[デバイスが Azure AD に接続されていることを確認する](#verify-the-device-is-connected-to-azure-ad)」を参照して確認します。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>既にセットアップして、Windows 10 Pro を実行しているデバイスの場合

 **ユーザーを Azure AD に接続する**
  
1. Windows 10 Pro バージョン 1703 (Creators Update) を実行しているユーザーの Windows PC で ([前提条件](../security-and-compliance/pre-requisites-for-data-protection.md)を参照)、Windows ロゴ、[設定] アイコンの順にクリックします。
  
   ![[次のスタート メニュー] アイコンWindows 設定クリックします。](../../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. [**設定**] で、[**アカウント**] に移動します。
  
   ![[アカウントWindows 設定アカウント] に移動します。](../../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. On **Your info** page, click **Access work or school** \> **Connect**.
  
   ![[仕事Connect学校にアクセスする] の下にある [アカウント] を選択します。](../../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. [ **職場または学校アカウントの設定**] ダイアログの [ **別の操作**] の下で、[ **このデバイスを Azure Active Directory に参加させる**] を選びます。
  
   ![[このデバイスに参加する] をクリックしてAzure Active Directory。](../../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![[サインインして取得する] ページに、仕事用または学校用のメールを入力します。](../../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. [組織 **の確認] ページで** 、情報が正しいか確認し、[参加] を **選択します**。
  
   [ **すべて完了しました。** ページで、[完了] **を選択します**。
  
   ![[組織の構成を確認する] 画面で、[参加] を選択します。](../../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。 サード パーティ製のツールを使用してプロファイルとファイルを移行した場合は、新しいプロファイルに同期することもできます。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

同期の状態を確認するには、設定の [仕事または学校へのアクセス] ページで **、[** 接続済み] **_** 領域を選択して、[情報] と [切断] ボタン \<organization name\> **を表示****します**。 [ **情報] を** 選択して同期の状態を取得します。 
  
[同期の **状態] ページで** 、[同期] **を** 選択して、最新のモバイル デバイス管理ポリシーを PC に取得します。
  
Microsoft 365 Business Premium アカウントの使用を開始するには、[スタートWindows] ボタンに移動し、現在のアカウントの画像を右クリックし、[アカウントの切り替え]**をクリックします**。 組織のメール アドレスとパスワードを使用してサインインします。
  
![[情報] ボタンをクリックして、同期の状態を表示します。](../../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>PC がデバイスにアップグレードWindows 10 Business

デバイスに参加Azure ADデバイスWindows 10サブスクリプションの一部としてWindows 10 BusinessアップグレードMicrosoft 365 Business Premiumします。
  
1. Go to **Settings** \> **System** \> **About**.
    
2. [ **エディション**] が **Windows 10 Business** であることを確認します。
    
    ![Verify that Windows edition is Windows 10 Business.](../../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>次の手順

モバイル デバイスをセットアップするには、「Microsoft 365 Business Premium ユーザー用のモバイル デバイスをセットアップする[」、](set-up-mobile-devices.md)デバイス保護ポリシーまたはアプリ保護ポリシーを設定するには、「ビジネス向けモバイル デバイスの管理Microsoft 365」を参照[してください](/admin/index.yml)。
  
## <a name="related-content"></a>関連コンテンツ

[一般法人向け Microsoft 365 のトレーニング ビデオ](../../business-video/index.yml) (リンク ページ)
