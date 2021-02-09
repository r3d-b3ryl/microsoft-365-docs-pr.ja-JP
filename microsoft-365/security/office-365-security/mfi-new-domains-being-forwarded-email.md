---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで電子メールの転送される新しいドメインの分析情報を使用して、ユーザーが転送されたことがない外部ドメインにメッセージを転送する状況を調査する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150605"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでメールを転送&新しいドメイン

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

電子メール メッセージを特定のドメインの外部受信者に転送するには、ビジネス上の有効な理由があります。 ただし、組織内のユーザーが、組織内の誰もメッセージを (新しいドメイン) に転送しなきドメインにメッセージを転送し始め、疑わしい場合があります。

この状態は、ユーザー アカウントが侵害された可能性があります。 アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。

セキュリティ **/コンプライアンス** [&](https://protection.office.com) センターでメールの分析情報を転送する新しいドメインは、組織内のユーザーが新しいドメインにメッセージを転送するときに通知します。

この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

ウィジェットをクリックすると、転送レポートへのリンクなど、転送されたメッセージの詳細を確認できるフライアウトが [表示されます](view-mail-flow-reports.md#forwarding-report)。

![メールを転送する新しいドメインの分析情報をクリックした後に表示される詳細フライアウト](../../media/mfi-new-domains-being-forwarded-details.png)

[上位の分析情報とおすすめ] 領域 **([** レポート ダッシュボード] または [ &]) で [すべて表示] をクリックした後に、分析情報を選択すると、**この詳細ページ** に移動 \> することもできます <https://protection.office.com/insightdashboard> 。

外部ドメインへのメッセージの自動転送を防ぐには、一部またはすべての外部ドメインのリモート ドメインを構成します。 詳細については [、「Exchange Online でのリモート ドメインの管理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)。

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
