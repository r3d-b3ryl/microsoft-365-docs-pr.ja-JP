---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで新しいドメインが転送される電子メール分析情報を使用して、ユーザーが転送されたことがない外部ドメインにメッセージを転送するタイミングを調査する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 1dbcf83d234611af1d209d83191cee24f5bee579
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64974347"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターで電子メール分析情報が転送される新しいドメイン

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

特定のドメインの外部受信者に電子メール メッセージを転送する有効なビジネス上の理由があります。 ただし、組織内のユーザーが突然、組織内の誰もメッセージを転送していないドメイン (新しいドメイン) にメッセージを転送し始めると、疑わしいです。

この状態は、ユーザー アカウントが侵害されたことを示している可能性があります。 アカウントが侵害されたと思われる場合は、「侵害された [メール アカウントへの対応」を](responding-to-a-compromised-email-account.md)参照してください。

[セキュリティ & コンプライアンス センター](https://protection.office.com)で電子メール 分析情報が **転送される新しいドメイン** は、組織内のユーザーが新しいドメインにメッセージを転送するときに通知します。

この分析情報は、問題が検出された場合にのみ表示され、[ [転送レポート](view-mail-flow-reports.md#forwarding-report) ] ページに表示されます。

:::image type="content" source="../../media/mfi-new-domains-being-forwarded.png" alt-text="電子メール分析情報が転送される新しいドメイン" lightbox="../../media/mfi-new-domains-being-forwarded.png":::

ウィジェットをクリックするとポップアップが表示され、転送されたメッセージの詳細 ( [転送レポート](view-mail-flow-reports.md#forwarding-report)へのリンクなど) が表示されます。

:::image type="content" source="../../media/mfi-new-domains-being-forwarded-details.png" alt-text="[新しいドメイン] をクリックした後に表示される [詳細] ポップアップが電子メール分析情報に転送されます。" lightbox="../../media/mfi-new-domains-being-forwarded-details.png":::

[レポート **ダッシュボード** または<https://protection.office.com/insightdashboard>レポート] の [**Top insights & recommendations**] 領域で [**すべて表示**] をクリックした後、\>分析情報を選択すると、この詳細ページに移動することもできます。

外部ドメインへのメッセージの自動転送を防止するには、一部またはすべての外部ドメインに対してリモート ドメインを構成します。 詳細については、「[Exchange Onlineでリモート ドメインを管理する](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)」を参照してください。

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
