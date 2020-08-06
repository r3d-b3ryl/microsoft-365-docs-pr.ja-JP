---
title: 転送される新しいドメインメールの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、新しい Exchange 管理センターで転送された新しいドメインを使用して、組織内のユーザーが転送されていない外部ドメインにメッセージを転送していることを調査する方法を学習できます。
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578442"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>転送される新しいドメインセキュリティ & コンプライアンスセンターでのメールに関する洞察

電子メールメッセージを特定のドメインの外部の受信者に転送するのに有効なビジネス上の理由があるかもしれませんが、組織内のユーザーが外部ドメインへのメッセージ転送を突然開始したときに、組織内のユーザーがそのドメインにメッセージを転送していない場合 (新しいドメイン) は疑わしいことがあります。 この条件は、ユーザーアカウントが侵害されていることを示している可能性があります。 アカウントが侵害されている疑いがある場合は、「[危害を受けた電子メールアカウントへの対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)」を参照してください。

**メールを転送している新しいドメイン**は、組織内のユーザーが新しいドメインにメッセージを転送しているときに通知します。

この洞察は、問題が検出されたときにのみ表示され、[転送レポート](view-mail-flow-reports.md#forwarding-report)ページに表示されます。

![転送される新しいドメインメールの洞察](../../media/mfi-new-domains-being-forwarded.png)

ウィジェットをクリックすると、転送されたメッセージの詳細を確認できるポップアップが表示されます。これには、[転送レポート](view-mail-flow-reports.md#forwarding-report)へのリンクも含まれています。

![転送される新しいドメインをクリックした後に表示される詳細ポップアップ、電子メールの洞察](../../media/mfi-new-domains-being-forwarded-details.png)

また、[詳細] を選択した後に [詳細] を選択すると、[詳細] を選択した後に、[詳細] を選択したときに、この詳細ページ**を表示でき**ます (**レポート**ダッシュボードまたは) の [**上位の分析 &** \> **Dashboard** <https://protection.office.com/insightdashboard>

外部ドメインへの自動メッセージ転送を禁止するには、一部またはすべての外部ドメインに対してリモートドメインを構成します。 詳細については、「 [Manage remote domains In Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)」を参照してください。

## <a name="related-topics"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
