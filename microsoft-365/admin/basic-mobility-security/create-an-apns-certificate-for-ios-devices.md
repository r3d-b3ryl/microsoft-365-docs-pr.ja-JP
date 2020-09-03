---
title: IOS デバイス用の APNs 証明書を作成する
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 基本的なモビリティとセキュリティで iOS デバイスを管理します。
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336985"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>IOS デバイス用の APNs 証明書を作成する

Ipad や iPhones などの iOS デバイスを基本的なモビリティとセキュリティで管理するには、APNs 証明書を作成します。

1. グローバル管理者アカウントを使用して、Microsoft 365 にサインインします。
    
2. ブラウザーで、と入力  [https://protection.office.com](https://protection.office.com/) します。
    
3. [ **データ損失防止**   >  **デバイス管理**] を選択し、 **iOS デバイス用の APNs 証明書**を選択します。    

4. [Apple プッシュ通知の証明書の設定] ページで、[ **次へ**] をクリックします。
    
5. [CSR ファイルをダウンロードし、証明書の署名要求をコンピューターのどこかに保存する] を選択して、覚えておきます。 [  **次へ**] を選択します。
    
6. [APNs 証明書の作成] ページで、次のようにします。  

    1. Apple APNS Portal を選択して、Apple プッシュ証明書ポータルを開きます。
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. [  **証明書を作成**   し、使用条件に同意します] を選択します。
    
    4. Microsoft 365 からコンピューターにダウンロードした証明書の署名要求を参照し、[ **アップロード**] を選択します。
    
        Apple プッシュ証明書ポータルによって作成された APNs 証明書をコンピューターにダウンロードします。
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365 に戻り、[**次**へ] を選択して [     **APNS 証明書のアップロード**   ] ページに移動します。
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. [  **完了**] を選択します。
    
セットアップを完了するには、セキュリティ & コンプライアンスセンター > **セキュリティポリシー**の [デバイスの管理] [設定の管理] に戻り   >  **Device management**   >  **Manage settings**ます。
