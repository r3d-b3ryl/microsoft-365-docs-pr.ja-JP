---
title: iOS デバイス用の APNs 証明書を作成する
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
description: Basic Mobility and Security で iOS デバイスを管理します。
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877082"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS デバイス用の APNs 証明書を作成する

Basic Mobility and Security で iPad や iPhone などの iOS デバイスを管理するには、ANS 証明書を作成します。

1. グローバル管理者アカウントで Microsoft 365 にサインインします。

2. ブラウザーで、「.」と入力します  [https://protection.office.com](https://protection.office.com/) 。

3. [ **データ損失防止デバイス**   >  **管理] を選択し**、[iOS デバイスの **APNs 証明書] を選択します**。

4. On the Apple Push Notification Certificate Settings page, choose **Next**.

5. [CSR ファイルをダウンロードする] を選択し、コンピューター上の任意の場所に証明書署名要求を保存します。 [次へ  **] を選択します**。

6. [APNs 証明書の作成] ページで、次の設定を行います。  

    1. Apple APNS ポータルを選択して、Apple Push Certificates Portal を開きます。

    2. Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. [  **証明書の作成] を**   選択し、使用条件に同意します。

    4. Microsoft 365 からコンピューターにダウンロードした証明書署名要求を参照し、[アップロード] を選択 **します**。

        Apple Push Certificate Portal によって作成された APNs 証明書をコンピューターにダウンロードします。

       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365 に戻り、[次へ]**を選択して**[APNS 証明書のアップロード   ]  **ページに移動**   します。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. [完了]  **を選択します**。

セットアップを完了するには、セキュリティ センターコンプライアンス センターに戻り&セキュリティ > **デバイス** 管理   > の管理 **の** 設定に   >  **戻る必要があります**。
