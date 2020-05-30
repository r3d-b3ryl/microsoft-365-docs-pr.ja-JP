---
title: 送信配信プール
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
description: Microsoft 365 データセンター内の電子メールサーバーの評価を保護するために、配信プールを使用する方法について説明します。
ms.openlocfilehash: 213149eda3dd121b65b64e3bddbb4bd73d66f57c
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419162"
---
# <a name="outbound-delivery-pools"></a>送信配信プール

Microsoft 365 データセンター内の電子メールサーバーは、一時的にスパムを送信している可能性があります。 たとえば、Microsoft 365 を介して送信メールを送信する社内電子メール組織、または Microsoft 365 アカウントを侵害したマルウェアまたは悪意のあるスパム攻撃。 また、攻撃者は Microsoft 365 転送を経由してメッセージを中継することで、検出を回避しています。

これらのシナリオでは、影響を受ける Microsoft 365 datacenter サーバーの IP アドレスが、サードパーティのブロックリストに表示されることがあります。 [宛先電子メール] これらのブロックリストを使用する組織は、それらのメッセージソースからの電子メールを拒否します。

## <a name="high-risk-delivery-pool"></a>高リスク配信プール
これを防ぐために、スパムであると判断された、または、[サービス](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパムポリシー](configure-the-outbound-spam-policy.md)の送信制限を超えている Microsoft 365 datacenter サーバーからのすべての送信メッセージは、_高リスク配信プール_を経由して送信されます。

高リスク配信プールは、"低品質" メッセージを送信するためにのみ使用される送信電子メールの個別の IP アドレスプールです (たとえば、スパムや[バックスキャター](backscatter-messages-and-eop.md))。 高リスク配信プールを使用すると、送信電子メールの通常の IP アドレスプールがスパムを送信するのを防ぐことができます。 送信電子メール用の通常の IP アドレスプールは、"高品質" メッセージを送信するという評価を維持します。これにより、IP アドレスが IP 禁止一覧に表示される可能性が低くなります。

高リスク配信プールの IP アドレスが IP 禁止一覧に配置される本当の可能性は残っていますが、これは仕様です。 多くの電子メール組織は高リスク配信プールからのメッセージを受け付けないため、目的の受信者への配信は保証されません。

詳細については、「[送信スパムの制御](outbound-spam-controls.md)」を参照してください。

> [!NOTE]
> 送信元の電子メールドメインにレコードがなく、パブリック DNS で定義されている MX レコードが、スパムや送信制限の廃棄に関係なく、常に高リスク配信プールを経由してルーティングされるメッセージ。

### <a name="bounce-messages"></a>メッセージをバウンスする

送信高リスク配信プールは、配信不能レポート (Ndr、バウンスメッセージ、配信状態通知、または Dsn とも呼ばれます) の配信を管理します。

Ndr のサージには、次のような原因が考えられます。

- サービスを使用しているお客様の1人に影響を与えるスプーフィングキャンペーン。
- ディレクトリハーベスト攻撃。
- スパム攻撃。
- 不正な電子メールサーバー。

これらのすべての問題により、サービスによって処理されている Ndr の数が急激に増加する可能性があります。 多くの場合、これらの ndr は他の電子メールサーバーおよびサービス (_[バックスキャター](backscatter-messages-and-eop.md)_ とも呼ばれます) に対してスパムに見えます。

## <a name="relay-pool"></a>中継プール

Microsoft 365 で転送または中継されたメッセージは、最終的な送信先では実際の送信者として Microsoft 365 を考慮しない必要があるため、特別な中継プールを使用して送信されます。 また、このトラフィックを分離することも重要です。これは、Microsoft 365 からの自動転送またはメールの中継のための正当で illegitmate のシナリオがあるためです。 危険度の高い配信プールと同様に、中継したメールには別の IP アドレスプールが使用されます。 このアドレスプールは、頻繁に変更されることがあるため、公開されていません。 

Microsoft 365 では、転送されたメッセージを確実に配信できるように、元の送信者が正当であることを確認する必要があります。 そのためには、メッセージの受信時に電子メール認証 (SPF、DKIM および DMARC) が渡される必要があります。 送信者を認証できる場合は、送信者が信頼できる送信元から転送されたメッセージであることを受信者に知らせるために、送信者書き換えを使用します。 この機能のしくみと、送信ドメインが[送信者リライトスキーム (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)で認証を通過することを確認するために、どのように役立つかについて参照できます。
