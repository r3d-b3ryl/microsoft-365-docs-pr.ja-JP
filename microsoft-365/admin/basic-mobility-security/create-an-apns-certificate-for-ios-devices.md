---
title: iOS デバイスの APN 証明書を作成する
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Basic Mobility and Security で iPad や iPhone などのiOSデバイスを管理するには、まず APNs 証明書を作成します。
ms.openlocfilehash: 8bcbcdeac9f1cadd945c3f7c44e9192d57db7c82
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65435791"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS デバイスの APN 証明書を作成する

Basic Mobility and Security で iPad や iPhone などのiOSデバイスを管理するには、APNs 証明書を作成します。

1. グローバル管理者アカウントでMicrosoft 365にサインインします。

2. ブラウザーで「.」と入力します <https://protection.office.com/>。

3. **[データ損失防止** \> **デバイス管理]** を選択し、**iOS デバイスの [APNs 証明書] を選択します**。

4. [Apple プッシュ通知証明書設定] ページで、[**次へ**] を選択します。

5. [CSR ファイルのダウンロード] を選択し、覚えているコンピューターのどこかに証明書署名要求を保存します。 **[次へ]** を選択します。

6. [APNs 証明書の作成] ページで、次の手順を実行します。

    1. Select Apple APNS Portal to open the Apple Push Certificates Portal. 

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. [ **証明書の作成** ] を選択し、使用条件に同意します。

    4. Microsoft 365からコンピューターにダウンロードした証明書署名要求に移動し、**アップロード** を選択します。

       Apple Push Certificate Portal によって作成された APNs 証明書をコンピューターにダウンロードします。

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. Microsoft 365に戻るし、[**次へ**] を選択して **アップロード APNS 証明書** ページに移動します。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. [**完了**] を選択します。

セットアップを完了するには、Security & Compliance Center \> **セキュリティ ポリシー** \> **デバイス管理の** \> **管理設定** に戻ります。
