---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: デバイスMicrosoft 365 Business Premiumアプリ保護設定Windows 10検証し、ユーザーが会社のデータを個人用ファイルまたは管理されていないアプリにコピーできないことを確認します。
ms.openlocfilehash: ab084ded5ef052a7b85839f0debb96eb1bc5bdf332230293613396825c7263f0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53861720"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でアプリの保護設定を検証する

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する

[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。 [ユーザーが会社のデータを個人用ファイルにコピーし、会社所有のデバイスの作業ファイルを **OneDrive for Business** に保存するように強制する] 設定をオンにした場合は、Azure AD に接続してサインインした後、ユーザーのデバイスでこれを確認できます。 
  
 **接続の設定を確認する**
  
1. Microsoft 365 Business Premium 資格情報を使用してサインインし、「Microsoft 365 Business Premium ユーザー用 [の Windows](set-up-windows-devices.md)デバイスのセットアップ」の説明に従って Azure AD に接続した後、[Windows 設定アカウント アクセスの仕事または学校] に \>  \> **移動します**。 [Azure **に接続] \<tenant name\> をAD** し、[情報] を **選択します**。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. [**管理] ページで**、次の図に示すように、管理サーバー アドレスを含む接続 \<tenant name\> 情報を確認できます。   
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **管理されていないアプリに会社のデータを貼り付けできないことを確認する**
  
1. ユーザー Outlook 2016によってインストールされたファイルを開Microsoft 365 Business Premium。
    
2. メールを開き、そこから一部のコンテンツをコピーします。
    
    メモ帳を開き、そこにコンテンツを貼り付けようとします。
    
    アプリがコンテンツにアクセスできないというエラーが表示されます。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    ただし、同じコンテンツを Word 2016 には貼り付けることができます。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する

 **接続の設定を確認する**
  
1. ローカル ユーザー Windows 10ログインしている個人用デバイスで、[Windows 設定] に移動し、[アカウントアクセスの仕事または学校] をクリックまたは \> **タップします**。
    
2. [ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。
    
3. [仕事Microsoft 365 Business Premiumアカウントの設定] ダイアログに資格情報を入力 **します** \> 。サインイン **します**。
    
4. [ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。
    
    ![[仕事または学校のアカウント] ダイアログで [情報] をクリックまたはタップします。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. [アクセス **の作業時間または** 学校] ページで、次の図に示すような管理サーバー アドレスを含む接続情報を確認できます。その中に wip と *mam* という単語が含まれています。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **管理されていないアプリに会社のデータを貼り付けできないことを確認する**
  
1. アカウントOutlook 2016開き、必要に応Microsoft 365 Business Premiumアカウントを追加し、資格情報を使用Microsoft 365 Business Premiumします。
    
2. メールを開き、そこから一部のコンテンツをコピーします。
    
    メモ帳を開き、そこにコンテンツを貼り付けようとします。
    
    アプリがコンテンツにアクセスできないというエラーが表示されます。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    ただし、同じコンテンツを Word 2016 には貼り付けることができます。
    

