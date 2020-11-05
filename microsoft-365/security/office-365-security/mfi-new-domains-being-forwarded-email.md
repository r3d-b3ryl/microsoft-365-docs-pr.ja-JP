---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードで転送される新しいドメインを使用して、ユーザーが転送されていない外部ドメインにメッセージを転送していることを調査する方法を学習できます。
ms.openlocfilehash: f2d8c9229062cbef0ad90b3d0fd843d6588a08dc
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920570"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>転送される新しいドメインセキュリティ & コンプライアンスセンターでのメールに関する洞察

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


電子メールメッセージを特定のドメインの外部の受信者に転送するには、ビジネス上の正当な理由があります。 ただし、組織内のユーザーがまだメッセージを転送していないドメイン (新しいドメイン) を組織内のユーザーが突然転送し始めた場合は、疑わしいことがあります。

この状態は、ユーザーアカウントが侵害されたことを示している可能性があります。 アカウントが侵害されている疑いがある場合は、「 [危害を受けた電子メールアカウントへの対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)」を参照してください。

**転送される新しいドメインメール** の [セキュリティ & コンプライアンスセンター](https://protection.office.com)では、組織内のユーザーが新しいドメインにメッセージを転送している場合に通知します。

この洞察は、問題が検出されたときにのみ表示され、 [転送レポート](view-mail-flow-reports.md#forwarding-report) ページに表示されます。

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

ウィジェットをクリックすると、転送されたメッセージの詳細を確認できるポップアップが表示されます。これには、 [転送レポート](view-mail-flow-reports.md#forwarding-report)へのリンクも含まれています。

![転送される新しいドメインをクリックした後に表示される詳細ポップアップ、電子メールの洞察](../../media/mfi-new-domains-being-forwarded-details.png)

また、[詳細] を選択した後に [詳細] を選択すると、[詳細] を選択した後に、[詳細] を選択したときに、この詳細ページ **を表示でき** ます ( **レポート** ダッシュボードまたは) の [ **上位の分析 &** \> **Dashboard** <https://protection.office.com/insightdashboard>

外部ドメインへの自動メッセージ転送を禁止するには、一部またはすべての外部ドメインに対してリモートドメインを構成します。 詳細については、「 [Manage remote domains In Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)」を参照してください。

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
