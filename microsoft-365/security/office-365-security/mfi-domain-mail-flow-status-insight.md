---
title: メール フロー ダッシュボードのトップ ドメイン メール フローの状態の分析情報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでトップ ドメイン メール フローの状態分析情報を使用して、MX レコードに関連するメール フローの問題をトラブルシューティングする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a22589ece98e497c55d61d29256b2480a2f55d3
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679722"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターのトップ ドメイン メール フロー&分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ **コンプライアンス センターの [** メール フロー] ダッシュボード [](mail-flow-insights-v2.md)の [[トップ ドメイン メール](https://protection.office.com) フローの状態] &は、組織の現在のメール フローの状態を示します。

この分析情報は、メール フローの問題が発生しているドメインを特定してトラブルシューティング ***するのに*** 役立ちます。 たとえば、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないため、ドメインは外部メールを受信できません。

![セキュリティ センターコンプライアンス センターのメール フロー ダッシュボードのトップ ドメイン フロー&ウィジェット。](../../media/mfi-top-domain-mail-flow-status-widget.png)

ウィジェットの [**詳細の表示]** をクリックすると、各ドメインの状態の詳細を示すドメイン状態のフライアウトが表示されます。

- **ドメイン**
- **以前の MX レコード**
- **現在の MX レコード**
- **電子メールの受信状態**
- **ドメインの** 状態: 緑色のチェック マークは、現在の MX レコード (ウィジェットをクリックした時点) が、記録されている値と一致し、ドメインが過去 2 時間の間にメールを受信した状態を示します。

  赤い X は、MX レコードが変更され、ドメインが過去 6 時間の間にメールを受信しきっていない状態を示します。 これは、ドメインの有効期限が切れているか、MX レコードが正しく更新されていないことを示している可能性があります。 ドメイン レジストラーまたは DNS ホスティング サービスに確認して、ドメインの有効期限が切れているか、ドメインの MX レコードが正しくないか確認します。

[詳細を表示 **] をクリック** すると、他のドメインの同じ情報を表示できます。

![トップ ドメイン メール フローの状態の分析情報の詳細フライアウト。](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、「Security [& コンプライアンス センター」を参照してください](mail-flow-insights-v2.md)。
