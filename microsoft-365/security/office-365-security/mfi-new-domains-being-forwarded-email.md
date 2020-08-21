---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、最新の Exchange 管理センターでメールの分析情報の転送中の新しいドメインを使用して、組織内のユーザーが転送されなかった外部ドメインにメッセージを転送しているときに調査する方法を学習できます。
ms.openlocfilehash: 0b4cd0490feebc8e05deb889b3cf54e1ea9f5928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826931"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>セキュリティ センターのセキュリティ マネージャーでメールインサイトを転送している新&するドメイン

特定のドメインの外部受信者に電子メール メッセージを転送する有効な業務上の理由が存在する場合がありますが、組織内のユーザーがメッセージを外部のドメインに不審に転送し始めたときに、これ以上にそれらのドメインにメッセージを転送したこと (新しいドメイン) がない場合にこれが不審です。 この状態は、ユーザー アカウントが侵害されたことを示している可能性があります。 アカウントが侵害されている可能性がある場合は、「侵害 [されたメール アカウントへの対応」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。

電子 **メールの分析情報が転送されている** 新しいドメインは、組織内のユーザーが新しいドメインにメッセージを転送しているときに通知します。

この分析情報は、問題が検出されたときのみ表示され、[転送レポート] [ページに表示](view-mail-flow-reports.md#forwarding-report) されます。

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

ウィジェットをクリックすると、転送されたメッセージに関する詳細が、転送レポートへのリンクなど、チップアップ [が表示されます](view-mail-flow-reports.md#forwarding-report)。

![[新しいドメイン] をクリックすると表示される詳細ポップアップ (メールのページに移動します)](../../media/mfi-new-domains-being-forwarded-details.png)

この詳細ページは、**トップ**インサイト &推奨事項領域 (レポート ダッシュボードまたはレポート**View all**) で [すべてのインサイトを表示] をクリックした後で、そのインサイト**を** \> **選択すると**表示されます <https://protection.office.com/insightdashboard> 。

外部ドメインへのメッセージ自動転送を防ぐためには、一部またはすべての外部ドメイン用にリモート ドメインを構成します。 詳細については [、「Exchange Online でリモート ドメインを管理する」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
