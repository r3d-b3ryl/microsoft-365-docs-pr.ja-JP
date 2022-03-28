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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 配信プールを使用して、データ センター内の電子メール サーバーの評判を保護するMicrosoft 365します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 273d105ca600face4d79d70fc1622dfce8bf9f5e
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403846"
---
# <a name="outbound-delivery-pools"></a>送信方向の配信のプール

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

データ センター内のMicrosoft 365サーバーは、スパムの送信に一時的に有罪になる可能性があります。 たとえば、オンプレミスの電子メール組織でマルウェアや悪意のあるスパム攻撃が発生し、Microsoft 365アカウントを介して送信Microsoft 365されます。 また、攻撃者は、転送を介してメッセージを中継して検出Microsoft 365します。

これらのシナリオでは、影響を受けるデータセンター サーバー Microsoft 365の IP アドレスがサード パーティのブロックリストに表示される可能性があります。 これらのブロックリストを使用する宛先の電子メール組織は、それらのメッセージ ソースからのMicrosoft 365拒否します。

## <a name="high-risk-delivery-pool"></a>リスクの高い配信プール

IP アドレスがブロックされるのを防ぐために、スパムと判断された Microsoft 365 データセンター サーバーからの送信メッセージはすべて、リスクの高い配信プールを _介して送信されます_。

リスクの高い配信プールは、"低品質" メッセージ (スパムやバックスカッターなど) の送信にのみ使用される送信メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。 リスクの高い配信プールを使用すると、送信メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。 送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持し、IP ブロックリストにこれらの IP アドレスが表示される可能性を低減します。

リスクの高い配信プール内の IP アドレスが IP ブロックリストに配置される可能性は非常に高いですが、これは設計上です。 多くの電子メール組織がリスクの高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。

詳細については、「送信スパムを [制御する」を参照してください](outbound-spam-controls.md)。

> [!NOTE]
> 送信元メール ドメインに A レコードがないメッセージと、パブリック DNS で定義されている MX レコードがないメッセージは、スパムや送信制限の廃棄に関係なく、常にリスクの高い配信プールを経由してルーティングされます。
>
> 次の制限を超えるメッセージはブロックされ、リスクの高い配信プールを介して送信されません。
>
> - サービス [の送信制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。
> - [送信者がメールの](configure-the-outbound-spam-policy.md) 送信を制限されている送信スパム ポリシー。

### <a name="bounce-messages"></a>バウンス メッセージ

送信リスクの高い配信プールは、すべての配信不可レポート (NDRs、バウンス メッセージ、配信状態通知、または DSN とも呼ばれる) の配信を管理します。

NDRs の急増の原因としては、次のようなものがあります。

- サービスを使用しているユーザーの 1 人に影響を与えるスプーフィング キャンペーン。
- ディレクトリハーベスト攻撃。
- スパム攻撃。
- 不正なメール サーバー。

これらの問題はすべて、サービスによって処理されるNDRsの数が急激に増加する可能性があります。 多くの場合、これらのNDRsは、他の電子メール サーバーやサービス ( _[backscatter](backscatter-messages-and-eop.md)_ とも呼ばれる) へのスパムのように見える。

### <a name="relay-pool"></a>リレー プール

特定のシナリオで Microsoft 365 経由で転送または中継されるメッセージは、宛先が実際の送信者として Microsoft 365 を考慮しないので、特別なリレー プールを使用して送信されます。 この電子メール トラフィックは、自動転送または電子メールの自動転送または中継に関する正当で無効なシナリオが発生Microsoft 365。 リスクの高い配信プールと同様に、中継メールには別の IP アドレス プールが使用されます。 このアドレス プールは頻繁に変更される可能性があります。また、このアドレス プールは公開された SPF レコードの一部Microsoft 365。

Microsoft 365、転送されたメッセージを自信を持って配信できるよう、元の送信者が正当なメッセージを提供することを確認する必要があります。

転送または中継されたメッセージは、リレー プールの使用を避けるために、次のいずれかの条件を満たす必要があります。

- 送信送信者は、受け入れ [可能なドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
- SPF は、メッセージが送信される際にMicrosoft 365。
- 送信者ドメインの DKIM は、メッセージが送信される際にMicrosoft 365。

送信サーバー IP (中継プールは 40.95.0.0/16 の範囲になります) を見て、または送信サーバー名 (名前に "rly" が含む) を見て、リレー プールを介してメッセージが送信されたことを確認できます。

送信者を認証できる場合は、送信者書き換えスキーム (SRS) を使用して、転送されたメッセージが信頼できるソースからのメッセージである受信者の電子メール システムが知るのを支援します。 送信側ドメインが Office 365 の [Sender Rewriting Scheme (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme) で認証に合格する方法と、その方法について詳しく説明します。

DKIM が動作するには、ドメインの送信に DKIM を有効にしてください。 たとえば、fabrikam.com は組織の contoso.com ドメインで定義されます。 メッセージの送信者が sender@fabrikam.com 場合は、DKIM を有効にする必要 fabrikam.com。 「DKIM を使用してカスタム ドメインから送信された送信メールを検証する」で有効にする [方法について説明します](use-dkim-to-validate-outbound-email.md)。

カスタム ドメインを追加するには、「ドメインを追加する」の手順に従[Microsoft 365](../../admin/setup/add-domain.md)。

ドメインの MX レコードがサード パーティ のサービスまたはオンプレミスの電子メール サーバーをポイントしている場合は、コネクタの拡張フィルターを [使用する必要があります](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。 拡張フィルターを使用すると、受信メールに対して SPF 検証が正しく、リレー プールを介した電子メールの送信を回避できます。
