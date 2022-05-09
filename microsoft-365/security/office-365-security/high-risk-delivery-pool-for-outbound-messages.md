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
description: 配信プールを使用して、Microsoft 365 データセンター内の電子メール サーバーの評判を保護する方法について説明します。
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

Microsoft 365 データセンター内の電子メール サーバーは、スパムの送信で一時的に有罪になる可能性があります。 たとえば、Microsoft 365経由で送信メールを送信するオンプレミスの電子メール組織でのマルウェアや悪意のあるスパム攻撃、または侵害されたMicrosoft 365 アカウントなどです。 また、攻撃者は、Microsoft 365転送を介してメッセージを中継することで、検出を回避しようとします。

これらのシナリオでは、影響を受けるMicrosoft 365 データセンター サーバーの IP アドレスがサード パーティのブロックリストに表示される可能性があります。 これらのブロックリストを使用する宛先電子メール組織は、それらのMicrosoft 365メッセージ ソースからのメールを拒否します。

## <a name="high-risk-delivery-pool"></a>危険度の高い配信プール

IP アドレスがブロックされないようにするために、スパムと判断されたデータセンター サーバー Microsoft 365からの送信メッセージはすべて _、危険度の高い配信プール_ を介して送信されます。

危険度の高い配信プールは、"低品質" メッセージ (スパムや [バックスキャッター](backscatter-messages-and-eop.md)など) の送信にのみ使用される送信電子メール用の個別の IP アドレス プールです。 危険度の高い配信プールを使用すると、送信メールの通常の IP アドレス プールがスパムを送信するのを防ぐことができます。 送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持します。これにより、これらの IP アドレスが IP ブロックリストに表示される可能性が低くなります。

危険度の高い配信プール内の IP アドレスが IP ブロックリストに配置される可能性は実際には残りますが、これは設計上です。 多くの電子メール組織はリスクの高い配信プールからのメッセージを受け入れないため、目的の受信者への配信は保証されません。

詳細については、「 [送信スパムの制御](outbound-spam-controls.md)」を参照してください。

> [!NOTE]
> 送信元電子メール ドメインに A レコードがなく、パブリック DNS に MX レコードが定義されていないメッセージは、スパムや送信制限の処理に関係なく、常に危険度の高い配信プールを経由してルーティングされます。
>
> 次の制限を超えるメッセージはブロックされるため、危険度の高い配信プールを介して送信されることはありません。
>
> - [サービスの送信制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。
> - 送信者がメールの送信を制限されている[送信スパム ポリシー](configure-the-outbound-spam-policy.md)。

### <a name="bounce-messages"></a>メッセージをバウンスする

送信の高リスク配信プールは、配信不能レポート (NDR、バウンス メッセージ、配信状態通知、または DSN とも呼ばれます) のすべての配信を管理します。

NDR の急増の原因として考えられる原因は次のとおりです。

- サービスを使用している顧客の 1 つに影響を与えるスプーフィング キャンペーン。
- ディレクトリの収集攻撃。
- スパム攻撃。
- 不正な電子メール サーバー。

これらの問題はすべて、サービスによって処理される NDR の数が急増する可能性があります。 多くの場合、これらの NDR は他の電子メール サーバーやサービス ( _[バックスキャッター](backscatter-messages-and-eop.md)_ とも呼ばれます) へのスパムのように見えます。

### <a name="relay-pool"></a>リレー プール

特定のシナリオでMicrosoft 365経由で転送または中継されるメッセージは、宛先が実際の送信者としてMicrosoft 365を考慮する必要がないため、特別なリレー プールを使用して送信されます。 このメール トラフィックを分離することは重要です。これは、Microsoft 365から電子メールを自動転送または中継する正当で無効なシナリオがあるためです。 危険度の高い配信プールと同様に、中継メールには別の IP アドレス プールが使用されます。 このアドレス プールは頻繁に変更される可能性があり、Microsoft 365用に公開された SPF レコードの一部ではないため、発行されません。

転送されたメッセージを確実に配信できるように、Microsoft 365元の送信者が正当であることを確認する必要があります。

転送またはリレーされたメッセージは、リレー プールの使用を回避するために、次のいずれかの条件を満たす必要があります。

- 送信送信者が [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)内にあります。
- メッセージがMicrosoft 365に来ると SPF は渡されます。
- 送信者ドメインの DKIM は、メッセージがMicrosoft 365になると渡されます。

メッセージがリレー プール経由で送信されたことを確認するには、送信サーバー IP (リレー プールは 40.95.0.0/16 の範囲になります)、または送信サーバー名 (名前に "rly" が含まれます) を調べます。

送信者を認証できる場合は、送信者書き換えスキーム (SRS) を使用して、転送されたメッセージが信頼できるソースからのメッセージであることを受信者電子メール システムが認識できるようにします。 そのしくみと、送信側ドメインが送信者[書き換えスキーム (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme) で認証に合格していることを確認するためにOffice 365でできることの詳細を確認できます。

DKIM を機能させるには、ドメインの送信に対して DKIM を有効にしてください。 たとえば、fabrikam.com は contoso.com の一部であり、組織の承認済みドメインで定義されます。 メッセージ送信者が sender@fabrikam.com の場合は、DKIM を fabrikam.com に対して有効にする必要があります。 [DKIM を使用してカスタム ドメインから送信された送信メールを検証する方法については、「DKIM を使用する](use-dkim-to-validate-outbound-email.md)」を参照してください。

カスタム ドメインを追加するには、「[Microsoft 365にドメインを追加する](../../admin/setup/add-domain.md)」の手順に従います。

ドメインの MX レコードがサード パーティのサービスまたはオンプレミスの電子メール サーバーを指している場合は、 [コネクタの拡張フィルター処理を使用する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)必要があります。 強化されたフィルター処理により、SPF の検証が受信メールに対して正しく行われ、リレー プール経由での電子メールの送信が回避されます。
