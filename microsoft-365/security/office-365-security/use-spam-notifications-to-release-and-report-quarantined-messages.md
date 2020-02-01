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
ms.openlocfilehash: c9cd0849f826e66411695a3758f271ec70d24c9b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598024"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する

管理者がユーザーのスパム通知を有効にした場合、スパムとして識別されたメールボックス宛てのメッセージを一覧表示する通知メッセージを受け取ります。

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

- メールフロールールに一致したために検疫されたメッセージは、ユーザーの検疫済みメッセージには含まれません。 スパム検疫済みメッセージのみが列挙されます。

- メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。
