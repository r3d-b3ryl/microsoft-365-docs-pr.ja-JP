---
title: 送信スパム保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の送信スパム制御と、大量のメールを送信する必要がある場合の対処方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 26be514584a8fb2f8c024c0f4db208018d951868
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202395"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP の送信スパム保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含むMicrosoft 365組織では、Exchange Onlineメールボックスがない組織では、送信スパムの管理を深刻に受け止めています。 1 人の顧客が意図的に、または意図せずに組織からスパムを送信した場合でも、そのアクションはサービス全体の評判を低下させ、他の顧客の電子メール配信に影響を与える可能性があります。

この記事では、送信スパムを防止するために設計された制御と通知、および大量の宛名を送信する必要がある場合の対処方法について説明します。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>送信スパムを制御するために管理者ができること

- **組み込みの通知を使用** する: ユーザーが [サービス](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) または [送信スパム ポリシー](configure-the-outbound-spam-policy.md) の送信制限を超え、電子メールの送信を制限されている場合、 **ユーザーが電子メールの送信を制限** されているという既定のアラート ポリシーは **、TenantAdmins** (**グローバル管理者**) グループのメンバーに電子メール通知を送信します。 これらの通知を受け取る他のユーザーを構成するには、「 [制限付きユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 また、**電子メール送信制限を超** えたという名前の既定のアラート ポリシーと **、不審な電子メール送信パターンが検出され****、TenantAdmins** (**グローバル管理者**) グループのメンバーに電子メール通知を送信しました。 アラート ポリシーの詳細については、「[Alert policies in Microsoft 365 (Microsoft 365 でのアラート ポリシー)](../../compliance/alert-policies.md)」を参照してください。

- **サードパーティのメール プロバイダーからのスパムの苦情を確認する**: Outlook.com、Yahoo、AOL などの多くのメール サービスでは、サービス内のユーザーがメールを Microsoft 365スパムとしてマークすると、メッセージがパッケージ化され、レビューのために返送されるフィードバック ループが提供されます。 Outlook.com の送信者のサポートの詳細については、次のページを<https://sendersupport.olc.protection.outlook.com/pm/services.aspx>参照してください。

## <a name="how-eop-controls-outbound-spam"></a>EOP が送信スパムを制御する方法

- **送信電子メール トラフィックの分離**: サービスを介して送信されるすべての送信メッセージは、スパムをスキャンします。 メッセージがスパムであると判断された場合は、危険度の _高い配信_ プールという名前の、信頼性の低いセカンダリ IP アドレス プールから配信されます。 詳細については、「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。

- **ソース IP アドレスの評判を監視** する: Microsoft 365は、さまざまなサード パーティの IP ブロック リストに対してクエリを実行します。 送信メールに使用する IP アドレスのいずれかがこれらのリストに表示された場合、アラートが生成されます。 この監視により、スパムによって評判が低下した場合に迅速に対応できます。 アラートが生成されると、IP アドレスをブロック リストから削除 (リスト解除) する方法を説明する内部ドキュメントが表示されます。

- **スパムを送信しすぎるアカウントを無効にする**: 送信スパムを危険度の高い配信プールに分離しても、アカウント (多くの場合、侵害されたアカウント) にスパムを無期限に送信することはできません。<sup>\*</sup> スパムを送信しているアカウントを監視し、非公開の制限を超えると、アカウントは電子メールの送信をブロックされます。 個々のユーザーとテナント全体に対して異なるしきい値があります。

- **メールの送信速度が高すぎるアカウントを無効にする**<sup>\*</sup>: スパムとしてマークされたメッセージを検索する制限に加えて、送信メッセージに対するスパム フィルターの判定に関係なく、送信メッセージの全体的な制限に達したときにアカウントをブロックする制限もあります。 侵害されたアカウントは、スパム フィルターによって見逃されたゼロデイ (以前は認識されなかった) スパムを送信する可能性があります。 正当な大量宛名キャンペーンとスパム キャンペーンを特定するのは困難な場合があるため、これらの制限は潜在的な被害を最小限に抑えるのに役立ちます。

<sup>\*</sup> スパム送信者がシステムをゲームできないので、必要に応じて制限を増減できるように、正確な制限をアドバタイズしません。 この制限は、平均的なビジネス ユーザーがそれらを超えるのを防ぐのに十分な高さであり、スパム送信者による被害を封じ込めるのに十分な低さです。

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>EOP 経由で大量の宛名を送信する顧客のおすすめ

大量のメールを送信する顧客と、侵害されたアカウントからサービスを保護する顧客と、受信者の取得方法が不十分な一括メール送信者とのバランスを取るのは困難です。 サード パーティの IP ブロック リストにMicrosoft 365電子メール ソースをランディングするコストは、メールの送信量が多すぎるユーザーをブロックするよりも大きくなります。

[Exchange Onlineサービスの説明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)で説明されているように、EOP を使用して一括メールを送信することは、サービスのサポートされる使用ではなく、"ベスト エフォート" ベースでのみ許可されます。 一括メールを送信する場合は、次の解決策をお勧めします。

- **オンプレミスの電子メール サーバーを介して一括メールを送信する**: お客様は、大量のメール用の独自の電子メール インフラストラクチャを維持します。

- **サード パーティの一括メール プロバイダーを使用** する: 大量のメールを送信するために使用できるサード パーティの一括メール ソリューション プロバイダーがいくつかあります。 これらの企業は、良好な電子メール送信プラクティスを確保するために顧客と協力することに既得権を持っています。

メッセージング、モバイル、マルウェア対策ワーキング グループ (MAAWG) は、そのメンバーシップ名簿 <https://www.maawg.org/about/roster>を . いくつかの一括メール プロバイダーが一覧に表示され、責任のあるインターネット市民であることが知られています。
