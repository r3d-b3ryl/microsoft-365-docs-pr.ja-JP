---
title: 送信メッセージにおける危険度の高い配信プール
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 高リスク配信プールを使用して、Office 365 データセンター内の電子メールサーバーの評価を保護する方法について説明します。
ms.openlocfilehash: 5d1bd2b14eb17ed74ee1cf1e44967f660f4595b8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895361"
---
# <a name="high-risk-delivery-pool-for-outbound-messages-in-office-365"></a>Office 365 の送信メッセージ用の高リスク配信プール

Office 365 データセンター内の電子メールサーバーは、一時的にスパムを送信している可能性があります。 たとえば、オンプレミスの電子メール組織では、Office 365 を経由して送信メールを送信したり、Office 365 アカウントに侵害されたりするマルウェアまたは悪意のあるスパム攻撃があります。 これらのシナリオでは、影響を受ける Office 365 datacenter サーバーの IP アドレスが、サードパーティのブロックリストに表示されることがあります。 [宛先電子メール] これらのブロックリストを使用する組織は、それらのメッセージソースからの電子メールを拒否します。

これを防ぐために、スパムであると判断された、または[サービス](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパムポリシー](configure-the-outbound-spam-policy.md)の送信制限を超えている Office 365 データセンターサーバーからのすべての送信メッセージは、_高リスク配信プール_を経由して送信されます。

高リスク配信プールは、"低品質" メッセージの送信にのみ使用される送信電子メールのセカンダリ IP アドレスプールです (たとえば、スパムや[バックスキャター](backscatter-messages-and-eop.md))。 高リスク配信プールを使用すると、送信電子メールの通常の IP アドレスプールがスパムを送信するのを防ぐことができます。 送信電子メール用の通常の IP アドレスプールは、"高品質" メッセージを送信するという評価を維持します。これにより、IP アドレスが IP 禁止一覧に表示される可能性が低くなります。

高リスク配信プールの IP アドレスが IP 禁止一覧に配置される本当の可能性は残っていますが、これは仕様です。 多くの電子メール組織は高リスク配信プールからのメッセージを受け付けないため、目的の受信者への配信は保証されません。

詳細については、「 [Office 365 で送信スパムを制御](outbound-spam-controls.md)する」を参照してください。

> [!NOTE]
> 送信元の電子メールドメインにレコードがなく、パブリック DNS で定義されている MX レコードが、スパムや送信制限の廃棄に関係なく、常に高リスク配信プールを経由してルーティングされるメッセージ。

## <a name="bounce-messages"></a>メッセージをバウンスする

送信高リスク配信プールは、配信不能レポート (Ndr、バウンスメッセージ、配信状態通知、または Dsn とも呼ばれます) の配信を管理します。

Ndr のサージには、次のような原因が考えられます。

- サービスを使用しているお客様の1人に影響を与えるスプーフィングキャンペーン。

- ディレクトリハーベスト攻撃。

- スパム攻撃。

- 不正な電子メールサーバー。

これらのすべての問題により、サービスによって処理されている Ndr の数が急激に増加する可能性があります。 多くの場合、これらの ndr は他の電子メールサーバーおよびサービス (_[バックスキャター](backscatter-messages-and-eop.md)_ とも呼ばれます) に対してスパムに見えます。
