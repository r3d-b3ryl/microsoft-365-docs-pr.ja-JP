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
ms.openlocfilehash: 10d2e8412cfecf3627c7520123592b371bf01fdb
ms.sourcegitcommit: 1fa0b15f86470c49dddf0d6de59d553a38ae259b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65863524"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS デバイスの APN 証明書を作成する

Basic Mobility and Security で iPad や iPhone などのiOSデバイスを管理するには、APNs 証明書を作成します。

1. グローバル管理者アカウントでMicrosoft 365にサインインします。

1. [Microsoft 365 管理センター](https://portal.office.com/adminportal/home?#/MifoDevices)に移動し、**iOSの APNs 証明書を** 選択します。

1. [Apple プッシュ通知証明書設定] ページで、[**次へ**] を選択します。

1. [CSR ファイルのダウンロード] を選択し、覚えているコンピューターのどこかに証明書署名要求を保存します。 **[次へ]** を選択します。

1. [APNs 証明書の作成] ページで、次の手順を実行します。

    1. Select Apple APNS Portal to open the Apple Push Certificates Portal. 

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. [ **証明書の作成** ] を選択し、使用条件に同意します。

    4. Microsoft 365からコンピューターにダウンロードした証明書署名要求に移動し、**アップロード** を選択します。

       Apple Push Certificate Portal によって作成された APNs 証明書をコンピューターにダウンロードします。

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

1. Microsoft 365に戻るし、[**次へ**] を選択して **アップロード APNS 証明書** ページに移動します。

1.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

1. **[完了]** を選択します。

セットアップを完了するには、Security & Compliance Center \> **セキュリティ ポリシー** \> **デバイス管理の** \> **管理設定** に戻ります。
