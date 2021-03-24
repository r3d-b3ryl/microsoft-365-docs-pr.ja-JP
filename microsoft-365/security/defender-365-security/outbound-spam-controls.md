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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の送信スパムコントロールと、大量メールを送信する必要がある場合の処理について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e84cd636abee42a03ff8590091542c96714f2d8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065163"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP での送信スパム保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、送信スパムの管理を真剣に行います。 組織から意図的または意図せずにスパムを送信する顧客の 1 人は、サービス全体の評判を低下させ、他の顧客の電子メール配信に影響を与える可能性があります。

このトピックでは、送信スパムを防止するために設計されたコントロールと通知、および大量メールを送信する必要がある場合に実行できる操作について説明します。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>送信スパムを制御するために管理者が実行できる操作

- **組** み込みの通知を使用する : ユーザーがサービスまたは送信 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)スパム ポリシー [](configure-the-outbound-spam-policy.md)の送信制限を超え、電子メールの送信が制限されている場合、Userという名前の既定のアラート ポリシーは、メールの送信を制限された状態で **、TenantAdmins** ( Global **admins**) グループのメンバーに電子メール通知を送信します。 これらの通知を受け取る他のユーザーを構成するには、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 また、メール送信制限という名前の既定のアラート ポリシーが超過し、疑わしいメール送信パターンが **検出され、TenantAdmins** ( Global **admins**) グループのメンバーに電子メール通知を送信しました。 アラート ポリシーの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。

- サード パーティの電子メール プロバイダーからのスパムの苦情を確認 **する:** Outlook.com、Yahoo、AOL などの多くの電子メール サービスでは、サービス内のユーザーが Microsoft 365 からのメールをスパムとしてマークすると、メッセージがパッケージ化され、レビューのために返送されるフィードバック ループが提供されます。 送信者のサポートの詳細については、「Outlook.com」を参照してください <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。

## <a name="how-eop-controls-outbound-spam"></a>EOP が送信スパムを制御する方法

- **送信メール トラフィックの** 分離 : サービスを通じて送信される送信メッセージの中で、スパムがスキャンされます。 メッセージがスパムと判断された場合は、リスクの高い配信プールという名前のセカンダリで評判の低い IP アドレス プールから _配信されます_。 詳細については、「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。

- **ソース IP アドレス評価の監視**: Microsoft 365 は、さまざまなサード パーティの IP ブロック リストを照会します。 送信メールに使用する IP アドレスがこれらのリストに表示されると、アラートが生成されます。 これにより、スパムによって評判が低下した場合に迅速に対応できます。 アラートが生成されると、IP アドレスをブロック リストから削除 (リストから削除) する方法を説明する内部ドキュメントがあります。

- スパムを送信しすぎるアカウントを無効にする : 送信スパムをリスクの高い配信プールに分離しても、アカウント (多くの場合、侵害されたアカウント) が無期限にスパムを送信することはできません。 <sup>\*</sup> スパムを送信しているアカウントを監視し、未公開の制限を超えると、アカウントが電子メールの送信をブロックされます。 個々のユーザーとテナント全体に対して異なるしきい値があります。

- メールの送信が速すぎるアカウントを無効にする : スパムとしてマークされたメッセージを検索する制限に加えて、送信メッセージのスパム フィルターの評決に関係なく、全体的な送信メッセージ制限に達するとアカウントをブロックする制限もあります。 <sup>\*</sup> 侵害されたアカウントは、スパム フィルターによって見逃された 0 日 (以前は認識されていない) スパムを送信する可能性があります。 正当な大量メール キャンペーンとスパム キャンペーンを特定することは困難な場合があります。これらの制限は、潜在的な損害を最小限に抑えるのに役立ちます。

<sup>\*</sup> スパム送信者がシステムにゲームをプレイできないので、必要に応じて制限を増減できるよう、正確な制限を宣伝する必要はありません。 この制限は、平均的なビジネス ユーザーが超過するのを防ぐのに十分な高値であり、スパム送信者による損害を含むのに十分な低レベルです。

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>EOP を介して大量のメールを送信する場合の推奨事項

大量のメールを送信する顧客と、侵害されたアカウントからサービスを保護する顧客と、受信者の取得方法が不十分なバルクメール送信者との間でバランスを取りにくい。 Microsoft 365 の電子メール ソースがサード パーティの IP ブロック リストに上陸するコストは、電子メールの送信が多すぎるユーザーをブロックするよりも大きくなります。

[「Exchange Online サービス](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)の説明」で説明したように、EOP を使用してバルク メールを送信する方法は、サービスのサポートされる使用ではなく、"ベスト エベスト" ベースでのみ許可されます。 一括メールを送信する場合は、次のソリューションをお勧めします。

- **オンプレミスの電子メール サーバーを介** して一括メールを送信する : つまり、大量メール用の独自の電子メール インフラストラクチャを維持する必要があります。

- **サード パーティのバルク メール** プロバイダーを使用する: 大量メールの送信に使用できるサードパーティのバルク メール ソリューション プロバイダーが複数あります。 これらの企業は、優れた電子メール送信方法を確保するために顧客と一緒に作業する上で既得権益を持っています。

メッセージング、モバイル、マルウェアの不正使用防止ワーキング グループ (MAAWG) は、 でメンバーシップ名簿を発行します <https://www.maawg.org/about/roster> 。 一覧には複数のバルク メール プロバイダーが含め、責任あるインターネット市民として知られています。