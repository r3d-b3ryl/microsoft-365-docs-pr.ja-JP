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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返されるメッセージに関する最も一般的な質問への回答を示します。
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827751"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP のキューイング、保留、返送されるメッセージに関する FAQ

ここでは、Exchange Online Protection (EOP) のフィルター処理中にキューイング、保留、または返されるメッセージに関してよく寄せられる質問の回答を提供します。

## <a name="why-is-mail-queuing"></a>なぜメールはキューイングされるのですか?

メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。 ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。

## <a name="how-does-a-message-become-deferred"></a>メッセージはどのようなときに保留状態になるのですか?

受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。 500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>メッセージが保留される期間と再試行の間隔はどのくらいですか?

保留状態のメッセージはキューに 1 日間保持されます。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 最初の数分の延期は 15 分以下で、(次の半数 00 分以上) 再試行が複数回にわたって再試行され、最大 60 分の再試行が複数回続けられます。 間隔の間隔の拡張は動的ですが、キューのサイズ、内部メッセージの優先度などの複数の変数が考慮されます。 基本的に、15 分 (またはそれより少ない) 点で開始してから、数時間以上から 60 分まで拡張できます。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?

メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。
