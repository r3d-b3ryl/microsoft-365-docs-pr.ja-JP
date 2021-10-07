---
title: メール フロー ダッシュボードの非承諾ドメイン レポート
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで [非承諾ドメイン] レポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミス組織からのメッセージを監視する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b698600cb3fbc85ec86bed4da542d23fe5eb17e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169469"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの非&レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

セキュリティ [&](https://protection.office.com)コンプライアンス センターのメール[](mail-flow-insights-v2.md)フロー ダッシュボードの [承認されていないドメイン] レポートには、送信者のドメインが Microsoft 365 組織で承認されたドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。

Microsoft 365の意図が悪意のあるものであることを証明するデータがある場合は、これらのメッセージを調整する可能性があります。 したがって、何が起こっているのかを理解し、問題を解決することが重要です。

![セキュリティ センターコンプライアンス センターのメール フロー ダッシュボードの非&ウィジェット。](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>非承諾ドメイン レポートのレポート ビュー

[非承諾ドメイン] ウィジェットのグラフ **を** クリックすると、非承諾ドメイン **レポートにアクセス** できます。

既定では、影響を受けるすべてのコネクタのアクティビティが表示されます。 [データの表示 **] をクリックすると**、ドロップダウンから特定のコネクタを選択できます。

グラフ内のデータ ポイント (日) にカーソルを合わせると、コネクタのメッセージの総数が表示されます。

![[承認されていないドメイン] レポートのレポート ビュー。](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>非承諾ドメイン レポートの詳細テーブル ビュー

レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。

- **日付**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージの ID です。

詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲****を指定できます**。

特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。

テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。

- **日付**
- **受信コネクタ名**
- **送信元ドメイン**
- **メッセージ数**
- **サンプル メッセージ**: [サンプル メッセージの [](message-trace-scc.md)**表示] を** クリックすると、影響を受けるメッセージのサンプルのメッセージ トレース結果を確認できます。

![[承認されていないドメイン] レポートの [詳細] テーブル ビューで行を選択した後の詳細フライアウト。](../../media/mfi-non-accepted-domain-report-details-flyout.png)

レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。

## <a name="related-topics"></a>関連トピック

メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。
