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
description: 配信プールを使用して、データ センター内の電子メール サーバーの評判を保護するMicrosoft 365します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5881b20eaed8387988d01b69a4acd022c5924a2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214404"
---
# <a name="outbound-delivery-pools"></a>送信方向の配信のプール

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

データセンター内のMicrosoft 365サーバーは、スパムの送信を一時的に有罪にしている可能性があります。 たとえば、オンプレミスの電子メール組織でマルウェアや悪意のあるスパム攻撃が発生し、Microsoft 365アカウントを介して送信Microsoft 365します。 攻撃者は、転送を介してメッセージを中継して検出Microsoft 365します。

これらのシナリオでは、影響を受けるデータセンター サーバーの IP Microsoft 365サード パーティのブロックリストに表示される可能性があります。 これらのブロックリストを使用する宛先電子メール組織は、これらのメッセージ ソースからの電子メールを拒否します。

## <a name="high-risk-delivery-pool"></a>リスクの高い配信プール
これを防止するために、スパムと判断された、またはサービスまたは送信スパム ポリシーの送信制限を超えている Microsoft 365 データセンター サーバーからの送信メッセージはすべて [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)、リスクの [](configure-the-outbound-spam-policy.md)高い配信プールを介して _送信されます_。

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


### <a name="relay-pool"></a>リレー プール

特定のシナリオで Microsoft 365 経由で転送または中継されるメッセージは、宛先が実際の送信者として Microsoft 365 を考慮しないので、特別なリレー プールを使用して送信されます。 自動転送や電子メールの自動転送やメールの転送に関する正当で無効なシナリオがMicrosoft 365。 リスクの高い配信プールと同様に、中継メールには別の IP アドレス プールが使用されます。 このアドレス プールは頻繁に変更される可能性があります。また、このアドレス プールは公開された SPF レコードの一部Microsoft 365。

Microsoft 365、転送されたメッセージを自信を持って配信できるよう、元の送信者が正当なメッセージを提供することを確認する必要があります。

転送/中継されたメッセージは、リレー プールの使用を避けるために、次のいずれかの条件を満たす必要があります。

- 送信送信者は、受け入 [れ可能なドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- SPF は、メッセージが送信される際にMicrosoft 365。
- 送信者ドメインの DKIM は、メッセージが送信される際にMicrosoft 365。
 
送信サーバー IP (中継プールは 40.95.0.0/16 の範囲になります) を見て、または送信サーバー名 (名前に "rly" が含む) を見て、リレー プールを介してメッセージが送信されたことを確認できます。

送信者を認証できる場合は、送信者書き換えスキーム (SRS) を使用して、転送されたメッセージが信頼できるソースからのメッセージである受信者の電子メール システムが知るのを支援します。 送信側ドメインが Office 365 の[Sender Rewriting Scheme (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme)で認証に合格する方法と、その方法について詳しく説明します。

DKIM が動作するには、ドメインの送信に DKIM を有効にしてください。 たとえば、fabrikam.com は組織の contoso.com ドメインで定義されます。 メッセージの送信者が sender@fabrikam.com 場合は、DKIM を有効にする必要 fabrikam.com。 「DKIM を使用してカスタム ドメインから送信された送信メールを検証する」で有効にする [方法について説明します](use-dkim-to-validate-outbound-email.md)。

カスタム ドメインを追加するには、「ドメインを追加する」の手順に[従Microsoft 365。](../../admin/setup/add-domain.md)

ドメインの MX レコードがサード パーティ のサービスまたはオンプレミスの電子メール サーバーをポイントしている場合は、コネクタの拡張フィルター [を使用する必要があります](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 拡張フィルターを使用すると、受信メールに対して SPF 検証が正しく、リレー プールを介した電子メールの送信を回避できます。

