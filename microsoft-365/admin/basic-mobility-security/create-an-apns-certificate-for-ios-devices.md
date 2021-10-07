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
description: Basic Mobility and Security で iOS デバイスを管理します。
ms.openlocfilehash: f2539ac1c27bd63c13766e197fc12fafc3906f07
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166182"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS デバイスの APN 証明書を作成する

Basic Mobility and Security で iPad や iPhone などの iOS デバイスを管理するには、ANS 証明書を作成します。

1. グローバル管理者アカウントMicrosoft 365にサインインします。

2. ブラウザーで、と入力します  <https://protection.office.com/> 。

3. [ **データ損失防止デバイス**   >  **の管理] を** 選択し **、[iOS デバイスの APNs 証明書] を選択します**。

4. [Apple プッシュ通知証明書] ページ設定[次へ] を **選択します**。

5. [CSR ファイルをダウンロードする] を選択し、覚えているコンピューターのどこかに証明書署名要求を保存します。 [次  **へ] を選択します**。

6. [APNs 証明書の作成] ページで、次の設定を行います。

    1. [Apple APNS ポータル] を選択して、Apple プッシュ証明書ポータルを開きます。

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. [  **証明書の作成] を**   選択し、利用規約に同意します。

    4. コンピューターにダウンロードした証明書署名要求を [証明書] から参照し、[Microsoft 365] を **アップロード。**

       Apple プッシュ証明書ポータルによって作成された APNs 証明書をコンピューターにダウンロードします。

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. [次へ] にMicrosoft 365し、[**次** へ] を   選択して[APNS 証明書]  **アップロードを取得**   します。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. [完了  **] を選択します**。

セットアップを完了するには、コンプライアンス センターのセキュリティ &ポリシーに>デバイス管理の管理 **** 設定に   >  ****   >  **戻します**。
