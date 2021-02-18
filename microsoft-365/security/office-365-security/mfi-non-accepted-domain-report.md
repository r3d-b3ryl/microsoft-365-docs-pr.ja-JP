---
title: メール フロー ダッシュボードの非承諾ドメイン レポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで非承諾ドメイン レポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミス組織からのメッセージを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d7355af49c5810a593c5776b70cf7497b43af6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287867"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターの非& レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[セキュリティ](https://protection.office.com)& コンプライアンス センターのメール[](mail-flow-insights-v2.md)フロー ダッシュボードの [非承諾ドメイン] レポートには、送信者のドメインが Microsoft 365 組織の承認されたドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。 

これらのメッセージの意図が悪意のあるものであることを証明するデータがある場合、Microsoft 365 はこれらのメッセージを調整する可能性があります。 そのため、何が起こっているかを理解し、問題を解決することが重要です。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの&ドメイン ウィジェット](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>非承諾ドメイン レポートのレポート ビュー

非承諾ドメイン ウィジェットのグラフ **を** クリックすると、非承諾ドメイン **レポートが表示** されます。

既定では、影響を受けるすべてのコネクタのアクティビティが表示されます。 [データの **表示] をクリック** すると、ドロップダウンから特定のコネクタを選択できます。

グラフ内のデータ ポイント (日) にマウス ポインターを合わせると、コネクタのメッセージの総数が表示されます。

![[非承諾ドメイン] レポートのレポート ビュー](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>非承諾ドメイン レポートの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **日付**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージの ID。

詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で日付 **範囲** を **指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。

- **日付**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: [サンプル メッセージの表示 [](message-trace-scc.md)]**を** クリックすると、影響を受けるメッセージのサンプルのメッセージ追跡結果を表示できます。

![[承認されていないドメイン] レポートの [詳細] テーブル ビューで行を選択した後の詳細フライアウト](../../media/mfi-non-accepted-domain-report-details-flyout.png)

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
