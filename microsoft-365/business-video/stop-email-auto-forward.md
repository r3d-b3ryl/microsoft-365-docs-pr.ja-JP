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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- AdminTemplateSet
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 独自の情報の盗難を回避するためにメール フロー ルールを作成して、電子メールの自動転送を停止する方法について説明します。
ms.openlocfilehash: 2879be5db078ba32ba088e30d1de5e4e062cff25
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195907"
---
# <a name="stop-email-auto-forward"></a>電子メールの自動転送を停止する

## <a name="watch-stop-auto-forwarding-emails"></a>ウォッチ: 自動転送メールを停止する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

ハッカーがユーザーのメールボックスにアクセスすると、ユーザーの電子メールを外部アドレスに自動転送し、専有情報を盗む可能性があります。 これを停止するには、メール フロー ルールを作成します。

## <a name="try-it"></a>お試しください!

1. [ルール] <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>、[メール フロー] **Exchange** を選択し、[ルール]タブでプラス記号を選択し、[新しいルールの作成]**を選択します**。
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

[ユーザーに別のメール エイリアスを追加する](../admin/email/add-another-email-alias-for-a-user.md) (記事)
[Microsoft 365 でメールの転送を構成する](../admin/email/configure-email-forwarding.md) (記事)
[ビジネス管理者向けメール配信の問題Office 365検索して修正](/exchange/troubleshoot/email-delivery/email-delivery-issues)する (記事)