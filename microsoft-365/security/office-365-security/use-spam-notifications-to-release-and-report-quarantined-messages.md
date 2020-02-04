---
title: Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 管理者がユーザーの通知を有効にした場合、スパム、大量、またはフィッシングメッセージとして識別されたメールボックスに送信されたメッセージを一覧表示する通知メッセージを受け取ります。 通知された後にメッセージを解放または報告することができます。
ms.openlocfilehash: 51fcdefc08987b153d045994927f56df3b670fd0
ms.sourcegitcommit: 836bd8135cc49d6db37e78a7cfeb7d2cc4159e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722038"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する

管理者がユーザーに対してスパム通知を有効にすると、スパム、一括、またはフィッシングとして識別されたメールボックス宛てのメッセージを一覧表示する通知メッセージが表示されます。

> [!TIP]
> 管理者がこの機能を有効にする場合は、[既定のスパム対策ポリシーを変更](configure-your-spam-filter-policies.md)するときにオプションを選択できます。

受信するメッセージには、スパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻または UTC) が含まれます。 一覧には、各メッセージの次の情報が含まれています。

- **送信者**検疫済みメッセージの送信名と電子メールアドレス。

- **件名** 検疫されたメッセージの件名テキスト。

- **日付** メッセージが検疫された日付と時刻 (UTC)。

以下に、検疫済みメッセージを使用して実行できるアクションを示します。

- [**送信者をブロック**する] Office 365 で、受信拒否リストに送信者を追加する場合。

- メッセージがスパムではなく、Office 365 がメールボックスにメッセージを送信する場合は、**リリースを解放**します。

- プレビューやリリースなどの他のアクションを実行する場合は、セキュリティ/コンプライアンスセンター内の検疫ポータルに移動することを**確認**してください。

以下の点にご注意ください。

- メールフロールールに一致したために検疫されたマルウェアと信頼性の高いフィッシングメッセージとメッセージは、ユーザーのスパム通知に含まれません。 

- メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。
