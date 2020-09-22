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
description: Exchange Online Protection (EOP) のフィルター処理中にキューに入れられたメッセージ、延期、または返送されたメッセージに関してよく寄せられる質問に対する回答を示します。
ms.openlocfilehash: 4ae38e871c0d6e4321bd7586c5cfd0bea3aeef81
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202941"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP のキューイング、保留、返送されるメッセージに関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


このトピックでは、Exchange Online Protection (EOP) のフィルター処理中にキュー、延期、または返送されたメッセージに関してよく寄せられる質問への回答を提供します。

## <a name="why-is-mail-queuing"></a>なぜメールはキューイングされるのですか?

メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。 ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。

## <a name="how-does-a-message-become-deferred"></a>メッセージはどのようなときに保留状態になるのですか?

受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。 500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>メッセージが保留される期間と再試行の間隔はどのくらいですか?

延期されたメッセージは、1日の間、キューに残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 最初のいくつかの deferrals は15分以内で、以降の再試行 (次の半周期以上) では、複数回の再試行の間隔が最大60分に増加します。 間隔の期間の展開は動的であり、キューのサイズや内部メッセージの優先度などの複数の変数を考慮します。 基本的には、15分 (またはそれ以下) から開始します。その後、次の数時間で最大60分に拡張できます。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?

メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。
