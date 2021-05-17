---
title: メールの自動転送を停止する
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
description: 電子メールの自動転送を停止する方法について学習します。
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903684"
---
# <a name="stop-email-auto-forward"></a>電子メールの自動転送を停止する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

ハッカーがユーザーのメールボックスにアクセスすると、ユーザーの電子メールを外部アドレスに自動転送し、専有情報を盗む可能性があります。 これを停止するには、メール フロー ルールを作成します。

## <a name="try-it"></a>お試しください!

1. 管理センター Microsoft 365 、[メール フロー] Exchangeを選択し、[ルール] タブでプラス記号を選択し、[新しいルールの作成]**を選択します**。 
1. [その **他のオプション] を選択します**。 新しいルールの名前を指定します。
1. 次に、ドロップダウンを開いて、送信者を選択し、外部内部である場合にこのルール **を適用します**。
1. [組織内 **] を選択し****、[OK] を選択します**。
1. [ **条件の追加]** を選択し、ドロップダウンを開き、[メッセージのプロパティ] を **選択して**、メッセージ **の種類を指定します**。
1. [メッセージの **種類の選択] ドロップダウン** を開き、[**自動転送] を選択し****、[OK] を選択します**。
1. [次の **操作を行う** ] ドロップダウンを開き、[メッセージをブロックする] **を選択し**、メッセージを拒否 **して説明を含める**。
1. 説明のメッセージ テキストを入力し **、[OK] を選択します**。
1. 一番下までスクロールし、[保存] を **選択します**。

    ルールが作成され、ハッカーはメッセージを自動転送できなくなりました。

## <a name="related-content"></a>関連コンテンツ

[ユーザーに別](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user)のメール エイリアスを追加する (記事) [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)でメール転送を構成する ([記事)](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues)ビジネス管理者向け Office 365 としてメール配信の問題を検索して修正する (記事)