---
title: フィッシング対策の保護を設定する
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: フィッシング対策保護を設定する方法について学習します。
ms.openlocfilehash: 71acaf070ea121db93947423e9824ae93d90b53c3ccbd3cc47e57df23a92a40f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53887517"
---
# <a name="set-up-anti-phishing"></a>フィッシング詐欺対策を設定する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

フィッシングは、電子メールが使い慣れたソースから送信されたように見えるが、個人情報の収集を試みる悪意のある攻撃です。 既定では、Microsoft 365フィッシング対策保護が含まれていますが、設定を絞り込み、その保護を強化できます。 それでは、見てみよ。

## <a name="try-it"></a>お試しください!

1. 管理センターで、[セキュリティ [https://admin.microsoft.com](https://admin.microsoft.com) ] 、[**脅威** 管理] 、[**ポリシー**] 、[ATP フィッシング対策]**の順に選択します**。 
1. [既定 **のポリシー] を** 選択して絞り込む。
1. [偽装 **] セクションで、[** 編集] を **選択します**。
1. [ドメインの **追加] に移動して、** 自分が所有するドメインを自動的に含めるトグルを保護して選択します。
1. [アクション **] に移動** し、ドロップダウンを **開きます** 偽装ユーザーからメールが送信された場合は、必要なアクションを選択します。

    [偽装されたドメインから **メールが** 送信された場合] ドロップダウンを開き、必要なアクションを選択します。
1. [偽装 **の安全ヒントを有効にする] を選択します**。 システムが偽装ユーザー、ドメイン、または異常な文字を検出した場合に、ヒントをユーザーに提供するかどうかを選択します。 **[保存]** を選択します。
1. [ **メールボックス インテリジェンス] を** 選択し、オンになっていることを確認します。 これにより、使用パターンを学習することで、電子メールの効率が向上します。
1. [信頼 **できる送信者とドメインの追加] を選択します**。 ここでは、偽装として分類しない電子メール アドレスまたはドメインを追加できます。
1. [ **設定の確認] を** 選択し、すべてが正しいか確認し、[保存] 、[ **閉** じる] の順に **選択します**。

    組織では、フィッシングの脅威からの保護が強化されました。