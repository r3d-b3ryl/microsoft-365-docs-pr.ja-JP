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
description: 管理者は、Exchange Online Protection (EOP) の送信スパム コントロールと、大量メールを送信する必要がある場合の対応方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d5a82b4a2c7f94b3c5d0958abc8c4552cc04032
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150690"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP での送信スパム保護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、送信スパムの管理を重く受け止めています。 組織から意図的または意図せずにスパムを送信する顧客の 1 人は、サービス全体の評判を低下させ、他の顧客の電子メール配信に影響を与える可能性があります。

このトピックでは、送信スパムを防止するために設計されたコントロールと通知、および大量メールを送信する必要がある場合に実行できる操作について説明します。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>送信スパムを制御するために管理者が実行できる操作

- 組み込みの通知を使用する **:** ユーザーがサービスまたは送信スパム ポリシー [](configure-the-outbound-spam-policy.md)の送信制限を超え、電子メールの送信が制限されている場合、Userという名前の既定のアラート ポリシーは、電子メールの送信が制限され **、TenantAdmins** (**グローバル** 管理者) グループのメンバーに電子メール通知を送信します。 [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) これらの通知を他のユーザーが受け取るユーザーを構成するには、「制限されたユーザーの [アラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 また、[電子メール送信の制限]という名前の既定のアラートポリシーが超過し、疑わしい電子メール送信パターンが検出され **、TenantAdmins** **(グローバル** 管理者) グループのメンバーに電子メール通知を送信しました。 アラート ポリシーの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。

- サード パーティの電子メール プロバイダーからのスパムの苦情を確認 **する:** Outlook.com、Yahoo、AOL などの多くのメール サービスは、サービス内のユーザーが Microsoft 365 からのメールをスパムとしてマークした場合、メッセージがパッケージ化され、レビューのために Microsoft に送信されるフィードバック ループを提供します。 送信者のサポートの詳細については、「Outlook.com」を参照してください <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> 。

## <a name="how-eop-controls-outbound-spam"></a>EOP が送信スパムを制御する方法

- **送信電子メール トラフィックの分離**: サービス経由で送信される送信メッセージごとにスパムがスキャンされます。 メッセージがスパムと判断された場合は、危険度の高い配信プールという名前の、評判の低いセカンダリ IP アドレス プール _から配信されます_。 詳細については、「[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。

- **ソース IP アドレス評価の監視**: Microsoft 365 は、さまざまなサード パーティ IP ブロック リストに対してクエリを実行します。 送信電子メールに使用する IP アドレスがこれらのリストに表示されると、アラートが生成されます。 これにより、スパムによって評判が低下した場合に迅速に対応できます。 アラートが生成されると、IP アドレスをブロック リストから削除 (リストから削除) する方法の概要を示す内部ドキュメントが提供されます。

- **スパム** を多く送信するアカウントを無効にする : 送信スパムをリスクの高い配信プールに分離しても、アカウント (多くの場合、侵害されたアカウント) が無期限にスパムを送信することはできません。 <sup>\*</sup> スパムを送信しているアカウントを監視し、未公開の制限を超えると、アカウントが電子メールの送信をブロックされます。 個々のユーザーとテナント全体に対して異なるしきい値があります。

- 電子メールの送信が速すぎるアカウントを無効にする : スパムとしてマークされたメッセージを検索する制限に加えて、送信メッセージのスパム フィルターの条件に関係なく、アカウントが全体的な送信メッセージ制限に達した場合にアカウントをブロックする制限もあります。 <sup>\*</sup> 侵害されたアカウントは、スパム フィルターによって見つからないゼロデイ (以前は認識されていない) スパムを送信する可能性があります。 正当な大量メール キャンペーンとスパム キャンペーンの識別が困難な場合があります。これらの制限により、潜在的な損害を最小限に抑えるのに役立ちます。

<sup>\*</sup> スパム送信者がシステムをゲームに使用できないので、正確な制限は通知しないので、必要に応じて制限を増減できます。 制限値は、平均的なビジネス ユーザーが超過する可能性を防ぐのに十分な高値と、スパム送信者による損害を含むのに十分な低い値です。

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>EOP を使用して大量のメールを送信する場合の推奨事項

大量のメールを送信したいお客様と、侵害されたアカウントからサービスを保護する顧客と、受信者の取得方法が不十分なバルク メール送信者との間でバランスを取るのは困難です。 Microsoft 365 のメール ソースがサード パーティの IP ブロック リストに追加されるコストは、多くのメールを送信しているユーザーをブロックするよりも大きくなります。

[「Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)サービスの説明」で説明したように、EOP を使用してバルク メールを送信する方法は、サービスのサポートされていないので、"ベストエベスト" ベースでのみ許可されます。 バルク メールを送信する場合は、次の解決策をお勧めします。

- **オンプレミスの電子メール サーバーを介** してバルク メールを送信する : つまり、顧客は大量メール用に独自の電子メール インフラストラクチャを維持する必要があります。

- **サード パーティのバルク** メール プロバイダーを使用する : 大量メールを送信するために使用できるいくつかのサード パーティのバルク メール ソリューション プロバイダーがあります。 これらの企業は、優れた電子メール送信プラクティスを確保するために、顧客との作業に大きな関心を持っています。

Messaging, Mobile, Malware Anti-Abuse Working Group (WG) は、メンバーシップ名簿を公開します <https://www.maawg.org/about/roster> 。 一覧にはいくつかのバルク メール プロバイダーが含め、インターネット市民を担当することが知られています。
