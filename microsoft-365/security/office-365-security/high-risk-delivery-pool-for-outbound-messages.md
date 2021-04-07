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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Microsoft 365 データセンターの電子メール サーバーの評判を保護するために、配信プールがどのように使用されるのかについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599913"
---
# <a name="outbound-delivery-pools"></a>送信方向の配信のプール

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 データセンター内の電子メール サーバーは、スパムの送信について一時的に有罪になる可能性があります。 たとえば、Microsoft 365 経由で送信メールを送信するオンプレミスの電子メール組織でのマルウェアや悪意のあるスパム攻撃、または Microsoft 365 アカウントの侵害などです。 また、攻撃者は Microsoft 365 転送を介してメッセージを中継して検出を回避しようとする。

これらのシナリオでは、影響を受ける Microsoft 365 データセンター サーバーの IP アドレスがサード パーティのブロックリストに表示される可能性があります。 これらのブロックリストを使用する宛先電子メール組織は、これらのメッセージ ソースからの電子メールを拒否します。

## <a name="high-risk-delivery-pool"></a>リスクの高い配信プール
これを防止するために、スパムと判断された Microsoft 365 データセンター サーバーからの送信メッセージ、またはサービスまたは送信スパム ポリシーの送信制限 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)を超えている [](configure-the-outbound-spam-policy.md)すべての送信メッセージは、リスクの高い配信プールを介して _送信されます_。

リスクの高い配信プールは、"低品質" メッセージ (スパムやバックスカッターなど) の送信にのみ使用される送信メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。 リスクの高い配信プールを使用すると、送信メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。 送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持し、IP ブロックリストにこれらの IP アドレスが表示される可能性を低減します。

リスクの高い配信プール内の IP アドレスが IP ブロックリストに配置される可能性は非常に高いですが、これは設計上です。 多くの電子メール組織がリスクの高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。

詳細については、「送信スパムを [制御する」を参照してください](outbound-spam-controls.md)。

> [!NOTE]
> 送信元メール ドメインに A レコードがないメッセージと、パブリック DNS で定義されている MX レコードがないメッセージは、スパムや送信制限の廃棄に関係なく、常にリスクの高い配信プールを経由してルーティングされます。

### <a name="bounce-messages"></a>バウンス メッセージ

送信リスクの高い配信プールは、すべての配信不可レポート (NDRs、バウンス メッセージ、配信状態通知、または DSN とも呼ばれる) の配信を管理します。

NDRs の急増の原因としては、次のようなものがあります。

- サービスを使用しているユーザーの 1 人に影響を与えるスプーフィング キャンペーン。
- ディレクトリハーベスト攻撃。
- スパム攻撃。
- 不正なメール サーバー。

これらの問題はすべて、サービスによって処理されるNDRsの数が急激に増加する可能性があります。 多くの場合、これらのNDRsは、他の電子メール サーバーやサービス _[(backscatter](backscatter-messages-and-eop.md)_ とも呼ばれる) へのスパムのように見える。
