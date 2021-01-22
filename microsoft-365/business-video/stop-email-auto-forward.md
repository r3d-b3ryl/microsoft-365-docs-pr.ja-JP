---
title: メールの自動転送を停止する
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: メールの自動転送を停止する方法について学習します。
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925888"
---
# <a name="stop-email-auto-forward"></a>メールの自動転送を停止する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

ハッカーがユーザーのメールボックスにアクセスした場合、ハッカーはユーザーの電子メールを外部のアドレスに自動転送し、専有情報を盗む可能性があります。 これを停止するには、メール フロー ルールを作成します。

## <a name="try-it"></a>演習

1. Microsoft 365 管理センターで **Exchange、** メール フローを選択し、[ルール] タブでプラス記号を選択し、新しいルールの作成 **を選択します**。 
1. [その **他のオプション] を選択します**。 新しいルールに名前を付け、
1. 次に、このルールを適用するドロップダウンを開きます **(** 送信者を選択し、外部 **内部の** 場合)。
1. [**組織内] を選択し****、[OK] をクリックします**。
1. [**条件の追加]** を選択し、ドロップダウンを開き、[メッセージのプロパティ] を **選択** して **、メッセージの種類を含める。**
1. [メッセージの **種類の選択]** ドロップダウンを開き、[自動転送] を選択し **、[OK] を選択します**。 
1. Open the **Do the following** drop-down, select Block the **message,** then **reject the message and include an explanation**.
1. 説明のメッセージ テキストを入力し **、[OK]** を選択します。
1. 一番下までスクロールし、[保存] を **選択します**。

    ルールが作成され、ハッカーはメッセージを自動転送できなくなりました。