---
title: Windows 10 PC でアプリの保護設定を検証する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 10 の Windows デバイスで Microsoft 365 のビジネス アプリケーションの保護設定を検証する方法について説明します。
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869406"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Windows 10 PC でアプリの保護設定を検証する

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>ユーザーが会社データを企業のデバイスの個人用ファイルにコピーできないことを確認する

[アプリの保護ポリシーを設定](protection-settings-for-windows-10-devices.md) した後は、ポリシーがユーザーのデバイスに影響を与えるまで最大で数時間かかる場合があります。会社所有のデバイスの [ **ユーザーが会社のデータを個人用ファイルにコピーできないようにして、強制的に作業ファイルを OneDrive for Business に保存させる**] 設定を **オン**にした場合、Azure AD に接続してサインインした後に、ユーザーのデバイスでこの設定を確認できます。 
  
 **接続の設定を確認する**
  
1. 365 ビジネスのマイクロソフトの資格情報を使用してサインインして[Microsoft 365 ビジネス ユーザー向けの Windows デバイスの設定](set-up-windows-devices.md)で説明したように、Azure AD に接続して後、に、 **Windows の設定** \> **アカウント** \> **アクセス職場または学校**.選択して**に接続されている\<テナント名\>Azure AD**、し、**情報**を選択します。
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. [ \>] ページで、次の図のような [ **管理サーバー アドレス**] を含む [ **接続情報**] を表示できます。 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **会社のデータを管理されていないアプリに貼り付けることができないことを確認する**
  
1. Microsoft 365 Business によってインストールされた Outlook 2016 を開きます。
    
2. メールを開き、そこから一部のコンテンツをコピーします。
    
    メモ帳を開き、そこにコンテンツを貼り付けようとします。
    
    アプリがコンテンツにアクセスできないというエラーが表示されます。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    ただし、同じコンテンツを Word 2016 には貼り付けることができます。
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>ユーザーが会社データを個人用デバイスの個人用ファイルにコピーできないことを確認する

 **接続の設定を確認する**
  
1. Windows 10 個人用デバイスの場所は、ローカル ユーザーとしてログインしている**Windows の設定**に移動し、クリックするか**アカウント**をタップして\>**アクセス職場または学校**。
    
2. [ **職場または学校にアクセスする**] の下で [ **接続**] を選びます。
    
3. Microsoft 365 ビジネスの資格情報を入力、 **、作業時間を設定または学校のアカウント] ダイアログ** \> **サインイン**します。
    
4. [ **職場または学校にアクセスする**] ページで、[ **職場または学校アカウント**] を選んで、[ **情報**] を選びます。
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. [ **職場または学校にアクセスする**] ページで、 **wip**  および  **mam**  の単語を含む、次の図のような [ *管理サーバー アドレス*] が示された [ *接続情報*] を表示できます。 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **会社のデータを管理されていないアプリに貼り付けることができないことを確認する**
  
1. Outlook 2016 を開いて、必要に応じて Microsoft 365 Business アカウントを追加し、Microsoft 365 Business の資格情報でサインインします。
    
2. メールを開き、そこから一部のコンテンツをコピーします。
    
    メモ帳を開き、そこにコンテンツを貼り付けようとします。
    
    アプリがコンテンツにアクセスできないというエラーが表示されます。
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    ただし、同じコンテンツを Word 2016 には貼り付けることができます。
    

