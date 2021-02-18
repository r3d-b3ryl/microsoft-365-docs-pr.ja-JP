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
ms.openlocfilehash: e54a260a70a9c68a94412243308bffe60d989e99
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289701"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP のキューイング、保留、返送されるメッセージに関する FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

このトピックでは、Exchange Online Protection (EOP) フィルタリング プロセス中にキューに入れ、保留、返送されたメッセージに関してよく寄せられる質問に対する回答を提供します。

## <a name="why-is-mail-queuing"></a>なぜメールはキューイングされるのですか?

メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。 ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。

## <a name="how-does-a-message-become-deferred"></a>メッセージはどのようなときに保留状態になるのですか?

受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。 500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>メッセージが保留される期間と再試行の間隔はどのくらいですか?

保留状態のメッセージはキューに 1 日間残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 最初の数回の延期は 15 分以下で、後続の再試行 (約 50 分間) で、複数回の再試行の間隔を最大 60 分に増やします。 間隔の期間の拡張は動的であり、キューのサイズや内部メッセージの優先順位など、複数の変数を考慮します。 基本的には、開始は 15 分 (以下) です。その後、次の数時間でそこから最大 60 分まで展開します。

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?

メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。
