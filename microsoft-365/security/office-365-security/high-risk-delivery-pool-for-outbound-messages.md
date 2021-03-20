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
ms.openlocfilehash: 5b35474c4d2b00c70e02f6f0127c3191a1e459bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910728"
---
# <a name="outbound-delivery-pools"></a>送信方向の配信のプール

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365 データセンター内の電子メール サーバーは、スパムの送信について一時的に有罪になる可能性があります。 たとえば、Microsoft 365 経由で送信メールを送信するオンプレミスの電子メール組織でのマルウェアや悪意のあるスパム攻撃、または Microsoft 365 アカウントの侵害などです。 また、攻撃者は Microsoft 365 転送を介してメッセージを中継して検出を回避しようとする。

これらのシナリオでは、影響を受ける Microsoft 365 データセンター サーバーの IP アドレスがサード パーティのブロック リストに表示される可能性があります。 これらのブロック リストを使用する宛先電子メール組織は、これらのメッセージ ソースからの電子メールを拒否します。

## <a name="high-risk-delivery-pool"></a>リスクの高い配信プール
これを防止するために、スパムと判断された Microsoft 365 データセンター サーバーからの送信メッセージ、またはサービスまたは送信スパム ポリシーの送信制限 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)を超えている [](configure-the-outbound-spam-policy.md)すべての送信メッセージは、リスクの高い配信プールを介して _送信されます_。

リスクの高い配信プールは、"低品質" メッセージ (スパムやバックスカッターなど) の送信にのみ使用される送信メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。 リスクの高い配信プールを使用すると、送信メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。 送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持し、これらの IP アドレスが IP ブロック リストに表示される可能性を低減します。

リスクの高い配信プール内の IP アドレスが IP ブロック リストに配置される可能性は非常に高いですが、これは設計上です。 多くの電子メール組織がリスクの高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。

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

## <a name="relay-pool"></a>リレー プール

Microsoft 365 から転送または中継されるメッセージは、最終的な宛先が Microsoft 365 を実際の送信者と見なす必要はなかから、特別なリレー プールを使用して送信されます。 また、Microsoft 365 から電子メールを自動送信または中継する正当で無効なシナリオが用意されているため、このトラフィックを分離することが重要です。 リスクの高い配信プールと同様に、中継メールには別の IP アドレス プールが使用されます。 このアドレス プールは頻繁に変更される可能性があるから公開されません。

Microsoft 365 では、転送されたメッセージを自信を持って配信できるよう、元の送信者が正当な送信者である必要があります。 これを行うには、電子メール認証 (SPF、DKIM、DMARC) がメッセージが届くときに渡す必要があります。 送信者を認証できる場合は、送信者書き換えを使用して、転送されたメッセージが信頼できるソースからのメッセージである受信者が知るのを支援します。 送信者書き換えスキーム [(SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme)で送信側ドメインが認証に合格する方法と、その動作について詳しく説明します。