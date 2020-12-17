---
title: フィッシング対策保護を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: フィッシング対策保護を設定する方法について学習します。
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702889"
---
# <a name="set-up-anti-phishing"></a>フィッシング詐欺対策を設定する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

フィッシングは悪意のある攻撃で、メールは使い慣れたソースから送信されたように見えますが、個人情報の収集を試みてきます。 既定では、Microsoft 365 にはフィッシング対策保護がいくつか含まれていますが、設定を調整することでその保護を強化できます。 見て見てみしましょう。

## <a name="try-it"></a>演習

1. In the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at, select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.
1. [既定 **のポリシー] を** 選択して絞り込む。
1. [偽装 **] セクションで、[** 編集] を **選択します**。
1. Go to **Add domains to protect** and select the toggle to automatically include the domains you own.
1. [アクション **] に** 移動し、ドロップダウンを開きます。偽装したユーザーからメールが送信された場合は、必要なアクションを選択します。

    [偽装されたドメインから **メール** が送信された場合] ドロップダウンを開き、必要なアクションを選択します。
1. [偽装 **の安全性のヒントを有効にする] を選択します**。 偽装されたユーザー、ドメイン、または異常な文字が検出された場合に、ユーザーにヒントを提供するかどうかを選択します。 [**保存**] を選択します。
1. メールボックス **インテリジェンスを選択** し、有効になっていることを確認します。 これにより、使用パターンを学習することで、電子メールの効率が向上します。
1. [信頼 **できる送信者とドメインの追加] を選択します**。 ここでは、偽装として分類しない電子メール アドレスまたはドメインを追加できます。
1. Choose **Review your settings,** make sure everything is correct, select **Save,** then **Close**.

    組織では、フィッシングの脅威からの保護が強化されました。