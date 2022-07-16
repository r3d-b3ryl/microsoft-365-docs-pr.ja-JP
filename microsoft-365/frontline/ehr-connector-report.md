---
title: Microsoft Teams EHR コネクタ仮想予定レポート
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ''
description: Microsoft Teams 管理センターで Teams EHR コネクタ仮想予定レポートを使用して、組織内の EHR 統合仮想予定の使用状況の概要を確認する方法について説明します。
ms.openlocfilehash: 6ec3423df4b6cd094bd2cab07e44c06923ec58bf
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822675"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Microsoft Teams EHR コネクタ仮想予定レポート

Microsoft Teams 管理センターの Microsoft Teams 電子カルテ (EHR) コネクタ仮想予定レポートを使用すると、組織内の Teams EHR 統合仮想予定の使用状況をすばやく簡単に表示できます。

レポートを表示するには、グローバル管理者、Teams 管理者、グローバル閲覧者、またはレポート閲覧者である必要があります。

## <a name="view-the-report"></a>レポートを表示する

Teams 管理センターでレポートにアクセスして表示するには、2 つの方法があります。

- ダッシュボードの [EHR コネクタ使用状況カード](#the-ehr-connector-usage-card) を使用する
- **分析およびレポート** >  の **使用状況レポート** で [**EHR コネクタ仮想予定**](#the-teams-ehr-connector-virtual-appointments-report) を直接選択して

### <a name="the-ehr-connector-usage-card"></a>EHR コネクタの使用状況カード

Microsoft Teams 管理センターの左側のナビゲーションで、**[ダッシュボード]** を選択し、**[EHR コネクタ仮想予定]** カードに移動します。

ここでは、完了した予定、残りの割り当て、(所有しているライセンスに応じて) 毎月の制限を超えたかどうかなど、月ごとの Teams EHR 統合仮想予定アクティビティの概要を確認できます。

:::image type="content" source="media/ehr-connector-report-card.png" alt-text="Teams 管理センター ダッシュボードの EHR コネクタ使用状況カードのスクリーンショット。" lightbox="media/ehr-connector-report-card.png":::

**[詳細の表示]** を選択して、レポートの詳細を表示します。 より多くのライセンスを購入するには、**[追加購入]** を選択します。

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>Teams EHR コネクタ仮想予定レポート

1. Teams 管理センターの左側のナビゲーションで、**分析およびレポート** > **使用状況レポート** に移動します。
1. **[レポートの表示]** タブで、**[EHR コネクタ仮想予定]** と日付範囲を選択します。 次に、**[レポートの実行]** を選択します。

    :::image type="content" source="media/ehr-connector-report.png" alt-text="Teams 管理センターの Teams EHR コネクタ仮想予定レポートのスクリーンショット。" lightbox="media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>レポートを解釈する

|吹き出し |説明  |
|--------|-------------|
|**1**   |各レポートには、レポートが生成された日付と選択した日付範囲が表示されます。|
|**2**   |この表には、選択した日付範囲で行われた各予定に関する詳細情報が表示されます。 スタッフまたは患者が参加していない予定のエントリは表示されないことに注意してください。 <ul><li>**開始時刻 (UTC)** は、スタッフ メンバーと参加者の両方が予定に参加している日付と時刻です。  </li> <li>**期間** は、開始時刻と最後のユーザーが予定を離れる時刻の間の時間差です。</li> <li>**プライマリ** は、会議の開催者の名前です。 <li>**プライマリの電子メール** は、会議の開催者のメール アドレスです。</li> <li> **部署** は、予定の部署情報です。 情報が正しく表示されない場合は、EHR サポート チームにお問い合わせください。 エピックとの統合については、```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` はプロバイダー統合レコードの一部であることを確認してください。 </li></li> <li>**出席者** は、予定のスタッフ メンバーと参加者の合計数です。</li> <li>**制限内** は、予定が割り当て制限内であるかどうかを示します。 </li> </ul> |
|**3**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 **[Excel にエクスポート]** を選択して、レポートをダウンロードします。 |
|**4**   |**[フィルター]** を選択して、レポートの詳細ビューをフィルター処理します。 |
|**5**   |**[全画面]** を選択すると、レポートが全画面モードで表示されます。 |
|**6**   |**[列の編集]** を選択して、テーブル内の列を追加または削除します。 |

> [!NOTE]
> Teams EHR 統合仮想予定の分析の詳細については、「[仮想訪問の使用状況レポート](virtual-visits-usage-report.md)」を参照してください。 仮想訪問の使用状況レポートを使用すると、予定の合計、ロビーでの待機時間、予定の期間、ノー ショー などの主要なメトリックを表示できます。 この情報を使用して使用状況の傾向を把握し、仮想予定を最適化してビジネス成果を向上させるために役立ちます。

## <a name="related-articles"></a>関連記事

- [Teams での仮想予定 - Cerner EHR への統合](ehr-admin-cerner.md)
- [Teams での仮想アクセス - Epic EHR への統合](ehr-admin-epic.md) 
