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
description: 配信プールを使用して、Microsoft 365 データセンター内の電子メール サーバーの評判を保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5480916f55fc180a6f08d3c420cb92c730e4065b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167541"
---
# <a name="outbound-delivery-pools"></a>送信方向の配信のプール

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft 365 データセンターの電子メール サーバーは、一時的にスパムを送信したとして有悪な場合があります。 たとえば、Microsoft 365 経由で送信メールを送信するオンプレミスの電子メール組織でのマルウェアや悪意のあるスパム攻撃や、Microsoft 365 アカウントの侵害などです。 攻撃者は、Microsoft 365 の転送を介してメッセージを中継して検出を回避することもできます。

これらのシナリオでは、影響を受ける Microsoft 365 データセンター サーバーの IP アドレスがサード パーティ製のブロック リストに表示される可能性があります。 これらのブロック リストを使用する送信先の電子メール組織は、それらのメッセージ ソースからの電子メールを拒否します。

## <a name="high-risk-delivery-pool"></a>危険度の高い配信プール
これを防止するために、スパムと判断された、またはサービスまたは送信スパム ポリシーの送信制限を超えている Microsoft 365 データセンター サーバー [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)からの送信メッセージ [](configure-the-outbound-spam-policy.md)はすべて、危険度の高い配信プールを介して送信 _されます。_

高リスク配信プールは、"低品質" メッセージ (スパムやバックスカターなど) の送信にのみ使用される送信電子メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。 危険度の高い配信プールを使用すると、送信電子メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。 送信電子メール用の通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持します。このため、これらの IP アドレスが IP ブロック リストに表示される可能性が低下します。

リスクの高い配信プール内の IP アドレスが IP ブロック リストに配置される可能性は非常に高いですが、これは設計上の問題です。 多くの電子メール組織は危険度の高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。

詳細については、「送信スパム [を制御する」を参照してください](outbound-spam-controls.md)。

> [!NOTE]
> 送信元の電子メール ドメインに A レコードが含ず、パブリック DNS で定義された MX レコードがないメッセージは、スパムや送信制限の廃棄に関係なく、常にリスクの高い配信プールを経由してルーティングされます。

### <a name="bounce-messages"></a>バウンス メッセージ

送信の危険度の高い配信プールは、すべての配信レポート (NDRs、バウンス メッセージ、配信状態通知、または DSN とも呼ばれる) の配信を管理します。

次のような、NDRs の急増の原因として考えられるものがあります。

- サービスを使用しているお客様の 1 人に影響を与えるスプーフィング キャンペーン。
- ディレクトリの収集攻撃。
- スパム攻撃。
- 不正な電子メール サーバー。

これらの問題はすべて、サービスによって処理されるNDRs の数が突然増加する可能性があります。 多くの場合、これらの NDRs は、他の電子メール サーバーやサービス (バックスカターとも呼ばれる) に対するスパム _[のように見なされます](backscatter-messages-and-eop.md)_。

## <a name="relay-pool"></a>中継プール

Microsoft 365 から転送または中継されるメッセージは、特別な中継プールを使用して送信されます。最終的な送信先では、Microsoft 365 を実際の送信者と見なす必要はなだからです。 また、Microsoft 365 からメールを自動送信または中継する正当で無効なシナリオが発生する場合、このトラフィックを分離することが重要です。 危険度の高い配信プールと同様に、中継されたメールには別の IP アドレス プールが使用されます。 このアドレス プールは頻繁に変更される可能性が高く、公開されません。

Microsoft 365 では、転送されたメッセージを自信を持って配信できるよう、元の送信者が正当な送信者である必要があります。 これを行うには、電子メール認証 (SPF、DKIM、DMARC) がメッセージに届く際にパスする必要があります。 送信者を認証できる場合は、送信者書き換えを使用して、転送されたメッセージが信頼できる送信元からのメッセージであるのを受信者が把握するのに役立ちます。 このしくみと、送信者書き換えスキーム [(SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)で送信側ドメインが認証に合格した場合の確認方法について説明します。
