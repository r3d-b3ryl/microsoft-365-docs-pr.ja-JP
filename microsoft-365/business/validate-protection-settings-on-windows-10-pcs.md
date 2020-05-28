---
title: Windows 10 PC でアプリの保護設定を検証する
f1.keywords:
- NOCSH
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 Business Premium app protection 設定を Windows 10 デバイスで検証し、ユーザーが会社のデータを個人ファイルや非管理アプリにコピーできないことを確認します。
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403392"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でアプリの保護設定を検証する

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する

[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。 **[** ユーザーが会社の**データを個人用ファイルにコピーできないよう**にする] をオンにして、会社が所有しているデバイスの OneDrive for business の設定に対して作業ファイルの保存を強制する場合は、Azure AD に接続してサインインした後、ユーザーのデバイス上でこれを確認できます。 
  
 **接続の設定を確認する**
  
1. Microsoft 365 business premium の資格情報を使用してサインインし、「 [microsoft 365 Business premium ユーザーの windows デバイス](set-up-windows-devices.md)をセットアップする」の説明に従って Azure AD に接続した後、[ **windows の設定**] の [ \> **アカウント** \> **アクセスの職場または学校**] に移動します。 [ ** \<tenant name\> Azure AD に接続**] を選択してから、[**情報**] を選択します。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. [**管理者** \<tenant name\> ] ページで、次の図に示すような**管理サーバーのアドレス**を含む**接続情報**が表示されます。 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **非管理対象アプリに会社のデータを貼り付けることができないことを確認する**
  
1. Microsoft 365 Business Premium によってインストールされた Outlook 2016 を開きます。
    
2. メールを開き、そこから一部のコンテンツをコピーします。
    
    メモ帳を開き、そこにコンテンツを貼り付けようとします。
    
    アプリがコンテンツにアクセスできないことを示すエラーが表示されます。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    ただし、同じコンテンツを Word 2016 には貼り付けることができます。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する

 **接続の設定を確認する**
  
1. ローカルユーザーとしてログインしている windows 10 個人用デバイスで、[windows の**設定**] に移動して、[**アカウント** \> **アクセスの職場または学校**] をクリックまたはタップします。
    
2. [ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。
    
3. Microsoft 365 Business Premium 資格情報を [**職場または学校のアカウントの設定] ダイアログボックス**に入力し \> **Sign in**ます。
    
4. [ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。
    
    ![[職場または学校のアカウント] ダイアログの [情報] をクリックまたはタップします。](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Access の**職場または学校**のページには、次の図に示すよう**な管理サーバーのアドレス**を含む**接続情報**が表示され、その中に「 *wip* and *mam* 」という単語が含まれています。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **非管理対象アプリに会社のデータを貼り付けることができないことを確認する**
  
1. Outlook 2016 を開き、必要に応じて Microsoft 365 Business Premium アカウントを追加して、Microsoft 365 Business Premium の資格情報でサインインします。
    
2. メールを開き、そこから一部のコンテンツをコピーします。
    
    メモ帳を開き、そこにコンテンツを貼り付けようとします。
    
    アプリがコンテンツにアクセスできないというエラーが表示されます。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    ただし、同じコンテンツを Word 2016 には貼り付けることができます。
    

