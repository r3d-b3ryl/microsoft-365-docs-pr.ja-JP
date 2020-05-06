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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 と Exchange Online Protection (EOP) が送信スパムからお客様を保護する方法、および大量のメールを送信する必要がある場合の対処方法について説明します。
ms.openlocfilehash: ffedcf68489914865c00eb68aecfa6c74e519ee2
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033928"
---
# <a name="outbound-spam-protection"></a>送信スパム保護

Microsoft 365 (exchange online またはスタンドアロンの exchange online Protection (EOP) が Exchange Online メールボックスを使用しない場合) は、多くのお客様がリソースの共有プールを使用しているオンラインサービスであるため、送信スパムを真剣に管理することになります。 ユーザーが故意または誤って組織からスパムを送信することによって、サービス全体の評判が低下し、他のお客様の電子メール配信に影響を与える可能性があります。365

このトピックでは、送信スパムを防止するために設計されたコントロールと通知、および大量のメールを送信する必要がある場合の対処方法について説明します。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>管理者が送信スパムを制御する方法

- **組み込み通知の使用**: ユーザーが[サービス](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパムポリシー](configure-the-outbound-spam-policy.md)の制限を超え、電子メールの送信が制限されている場合、ユーザーが電子メールを**送信**できないようにする既定の警告ポリシーは、電子メール通知を " **tenantadmins** (**グローバル管理者**)" グループのメンバーに送信します。 これらの通知を受信するユーザーを構成するには、「制限され[たユーザーの通知設定を確認](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)する」を参照してください。 また、電子メールの送信の**制限**を指定した既定の警告ポリシーと、電子メールの送信**パターンが検出さ**れた場合は、 **tenantadmins** (**Global admins**) グループのメンバーに電子メール通知が送信されます。 アラート ポリシーの詳細については、「[セキュリティ/コンプライアンス センターでのアラート ポリシー](../../compliance/alert-policies.md)」を参照してください。

- **サードパーティの電子メールプロバイダーからスパムの苦情を確認**する: Outlook.com、YAHOO、AOL などの多くの電子メールサービスは、フィードバックループを提供します。このような場合、サービスのユーザーが Microsoft 365 からスパムとして電子メールをマークすると、メッセージがパッケージ化され、レビューのために弊社に送り戻されます。 Outlook.com の送信者のサポートの詳細について<https://sendersupport.olc.protection.outlook.com/pm/services.aspx>は、「」を参照してください。

## <a name="how-eop-controls-outbound-spam"></a>EOP が送信スパムを制御する方法

- **送信メールトラフィックの分離**: サービスを通じて送信されたすべての送信メッセージがスパムでスキャンされます。 メッセージがスパムであると判断された場合、そのメッセージは_高リスク配信プール_という、信頼度の低いセカンダリ IP アドレスプールから配信されます。 詳細については、「 [Office 365 での送信メッセージの高リスク配信プール](high-risk-delivery-pool-for-outbound-messages.md)」を参照してください。

- **送信元 ip アドレスの評価**: Microsoft 365 では、さまざまなサードパーティの ip 禁止一覧を照会します。 送信電子メールに使用する IP アドレスのいずれかがこれらのリストに表示される場合は、アラートが生成されます。 これにより、スパムによる評価が低下した場合に迅速に対応することができます。 通知が生成されると、ブロックリストから IP アドレスの削除 (delisted) を取得する方法の概要を示す内部ドキュメントがあります。

- **[次の回数を超えて送信するアカウントを無効に**<sup>\*</sup>する]: 送信スパムが危険度の高い配信プールに分離されている場合でも、スパムを無期限に送信することを許可することはできません。 スパムを送信しているアカウントを監視していて、undisclosed いうの制限を超えている場合、アカウントはメールの送信をブロックされます。 個々のユーザーとテナント全体に異なるしきい値があります。

- **送信するメール**<sup>\*</sup>の数が速すぎるアカウントを無効にする: スパムとしてマークされているメッセージを検索する制限に加えて、送信メッセージの verdict に関係なく、送信メッセージの制限に達した場合にアカウントをブロックする制限もあります。 セキュリティ侵害されたアカウントは、スパムフィルターによって欠落したゼロ (以前に認識されていない) スパムを送信することができます。 正当な大量のメーリングキャンペーンとスパムキャンペーンを識別するのは困難になる可能性があるため、これらの制限は、潜在的な損害を最小限に抑えるために役立ちます。

<sup>\*</sup>スパム送信者がシステムをゲームできないように正確な制限を通知するわけではありません。そのため、必要に応じて制限を増減させることができます。 この制限は、平均のビジネスユーザーがそれを超えないようにするために十分であり、スパム送信者による損害を抑えるために十分な余裕がありません。

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>EOP を介して大量のメールを送信することを希望するお客様向けの推奨事項

大量の電子メールを送信しようとしているお客様と、侵害されたアカウントからのサービスの保護と、受信者の取得方法に不備がある大量の電子メール送信者の間で、バランスを取ることは困難です。 サードパーティの IP 禁止一覧における Microsoft 365 メールソースのランディングのコストは、送信する電子メールの数が多すぎるユーザーをブロックすることよりも大きくなります。

「 [Exchange Online サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」に記載されているように、EOP を使用してバルクメールを送信することは、サービスの使用をサポートしておらず、"ベストエフォート" ベースでのみ許可されています。 バルクメールを送信する場合は、次のソリューションをお勧めします。

- **オンプレミスの電子メールサーバーを使用してバルクメールを送信**する: これは、ユーザーが一括メール用の独自の電子メールインフラストラクチャを維持する必要があることを意味します。

- **サードパーティのバルクメールプロバイダーを使用**する: 大量のメールを送信するために使用できる、いくつかのサードパーティのバルクメールソリューションプロバイダーがあります。 これらの企業は、お客様と協力して電子メールを送信する習慣を確認することに関心があります。

メッセージング、モバイル、マルウェア対策行為グループ (MAAWG) は、メンバーシップ名簿をに<https://www.maawg.org/about/roster>公開します。 複数のバルクメールプロバイダーがリストにあり、責任を負うことがわかっています。
