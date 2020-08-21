---
title: 送信方向の配信のプール
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 配信プールを使用して、Microsoft 365 データセンター内の電子メール サーバーの評判を保護する方法について説明します。
ms.openlocfilehash: 83ea21a9230240f1339513efc75587f3d84733cb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827739"
---
# <a name="outbound-delivery-pools"></a>送信方向の配信のプール

Microsoft 365 データセンターのメール サーバーでは、スパムを送信したメールが一時的に有効な場合があります。 たとえば、オンプレミスのメール組織のマルウェアまたは悪意のあるスパム攻撃で、Microsoft 365 経由で送信メールを送信したり、Microsoft 365 アカウントに問題が侵害されたりした場合などです。 攻撃者は、Microsoft 365 転送経由でメッセージを中継して検出の回避も試みてください。

これらのシナリオによって、影響を受ける Microsoft 365 データセンター サーバーの IP アドレスがサード パーティのブロック リストに表示される可能性があります。 このブロック リストを使用している送信先メール組織は、これらのメッセージ ソースからのメールを拒否します。

## <a name="high-risk-delivery-pool"></a>危険度の高い配信プール
これを防ぐため、スパムとして判断された、またはサービスや送信スパム ポリシーの送信制限を超えるすべての送信メッセージが、危険度の高[the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)い配信プール[outbound spam policies](configure-the-outbound-spam-policy.md)_で送信されます_。

危険度の高い配信プールとは、送信電子メール用の独立した IP アドレス プールです。送信電子メール専用のルーティング プールです (スパムやバックス [キャターなど](backscatter-messages-and-eop.md))。 高リスク配信プールを使用すると、送信電子メールに対して通常の IP アドレス プールがスパムを送信するのを防止できます。 送信電子メールの通常の IP アドレス プールは、"高品質" メッセージの送信を維持します。これは、これらの IP アドレスが IP 禁止一覧に表示される可能性を低減します。

非常に、より危険度の高い配信プールの IP アドレスは IP 禁止一覧に残されますが、これは設計上のためです。 多くの電子メール組織が危険性の高い配信プールからメッセージを受け付けないため、意図された受信者への配信は一切切必要しません。

詳細については、「送信スパムの [制御」を参照してください](outbound-spam-controls.md)。

> [!NOTE]
> 送信元メール ドメインに A レコードがなく、パブリック DNS で MX レコードが定義されていないメッセージは、スパムや送信制限の処分に関係なく、常に危険度の高い配信プールでルーティングされます。

### <a name="bounce-messages"></a>バウンス メッセージ

送信用の危険度の高い配信プールは、すべての配信不能レポート (NDR、バウンス メッセージ、配信状態通知、DSN とも呼ばれる) の配信を管理します。

NDR のスージングの原因としては、次のようなものがあります。

- サービスを使用している顧客のいずれかに影響を与えるスプーフィング キャンペーン。
- ディレクトリ取得攻撃。
- スパム攻撃。
- 問題の電子メール サーバー。

これらのすべての問題により、サービスが処理する NDR の数が多く増えてしう可能性があります。 多くの場合、このような NDR は、他の電子メール サーバーやサービス (バックスキャター _[とも呼ばれる) へのスパムのように見えることもあります](backscatter-messages-and-eop.md)_。

## <a name="relay-pool"></a>リレー プール

Microsoft 365 から転送または中継されるメッセージは、特別な中継プールを使用して送信されます。最終的な送信先は実際の送信者として Microsoft 365 とは見なされないからです。 また、Microsoft 365 からメールの自動転送または中継に対しては正当で無効なシナリオがあるため、このトラフィックを分離するのも重要です。 危険度の高い配信プールと同様に、別の IP アドレス プールが中継されたメールに使用されます。 このアドレス プールは頻繁に変更される可能性があから、公開されません。

Microsoft 365 は、元の送信者が正当なものであるかどうかを検証して、転送されたメッセージを不確認できる必要があります。 これを行うためには、メール認証 (SPF、DKIM、および DMARC) がメッセージが Microsoft に送信されるときに合格する必要があります。 送信者が認証できる場合は、送信者書き換えを使用して、転送されたメッセージが信頼できる送信元からのものであることが受信者にわかるようにします。 この操作のしくみと、送信ドメインが [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)で認証に合格したことを確認するために役立つ方法を参照できます。
