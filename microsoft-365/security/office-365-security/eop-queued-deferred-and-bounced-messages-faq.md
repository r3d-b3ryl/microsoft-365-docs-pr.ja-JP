---
title: EOP のキューイング、保留、返送されるメッセージに関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) フィルタリング プロセス中にキューに入れ、延期、返送されたメッセージに関する最も一般的な質問に対する回答を見つける。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 854e954e3ebb995ba23db2afc6f2ca9ab19de508
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165429"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP のキューイング、保留、返送されるメッセージに関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

このトピックでは、Exchange Online Protection (EOP) フィルタリング プロセス中にキューに入れ、保留、返送されたメッセージに関してよく寄せられる質問に対する回答を提供します。

## <a name="why-is-mail-queuing"></a>なぜメールはキューイングされるのですか?

メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。 ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。

## <a name="how-does-a-message-become-deferred"></a>メッセージはどのようなときに保留状態になるのですか?

受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。 500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>メッセージが保留される期間と再試行の間隔はどのくらいですか?

保留状態のメッセージはキューに 1 日間残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 最初の数回の延期は 15 分以下で、後続の再試行 (約 50 分ほど) で、複数回の再試行の間隔を最大 60 分に増やします。 キューのサイズや内部メッセージの優先度など、複数の変数を考慮して、間隔の拡張は動的です。 基本的には、開始は 15 分 (以下) です。その後、次の数時間でそこから最大 60 分まで展開します。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?

メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。
