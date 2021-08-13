---
title: メール フロー ダッシュボードのトップ ドメイン メール フローの状態の分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでトップ ドメイン メール フローの状態分析情報を使用して、MX レコードに関連するメール フローの問題をトラブルシューティングする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0258aeb57f9821091f29f884a42266da47e63dee4adf44a99b3f22154549d19
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56770469"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターのトップ ドメイン メール フロー&分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ [](mail-flow-insights-v2.md)**センターの [メール フロー]** ダッシュボードの [トップ ドメイン メール フローの状態] &[は](https://protection.office.com)、組織の現在のメール フローの状態を示します。

この分析情報は、メール フローの問題が発生しているドメインを特定してトラブルシューティング ***するのに*** 役立ちます。 たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部メールを受信できません。

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードのトップ ドメイン フロー&ウィジェット](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェットの [**詳細の表示]** をクリックすると、各ドメインの状態の詳細を示すドメイン状態のフライアウトが表示されます。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **電子メールの受信状態**
- **ドメインの** 状態 : 緑色のチェック マークは、現在の MX レコード (ウィジェットをクリックした時点) が、記録されている値と一致し、ドメインが過去 2 時間の間にメールを受信した状態を示します。

  赤い X は、MX レコードが変更され、ドメインが過去 6 時間の間にメールを受信しきっていない状態を示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメイン レジストラーまたは DNS ホスティング サービスに確認して、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないか確認します。

[詳細を表示 **] をクリック** すると、他のドメインの同じ情報を表示できます。

![トップ ドメイン メール フローの状態の分析情報の詳細の飛び出し](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。
