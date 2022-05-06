---
title: Microsoft 365 管理センターでコスト管理を使用する
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_subscriptions
- AdminTemplateSet
search.appverid: MET150
description: Microsoft 365 管理センターのコスト管理機能を使用して、組織のコストを表示、分析、管理する方法について説明します。
ms.date: 03/09/2022
ms.openlocfilehash: c0cfcd47e20d34b12af1276995b0c0cfe1dc1ee7
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63524923"
---
# <a name="use-cost-management-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでコスト管理を使用する

Microsoft 顧客契約 (MCA) を持つグローバル管理者または課金管理者の場合は、Microsoft 365 管理センターの **[コスト管理**] ページを使用して、サービス コストを表示、分析、管理できます。 **[コスト管理**] ページに移動するには、管理センターの左側のナビゲーション ウィンドウで **BillingCost** >  管理を選択します。

## <a name="before-you-begin"></a>はじめに

この記事で説明する手順を実行するには、グローバル管理者または課金管理者である必要があります。詳細については、「[管理者ロールについて](../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-is-cost-management"></a>コスト管理とは

コスト管理は、組織の予算を計画および制御するために使用される手法です。 Microsoft では、従量課金モデルを使用する新しい製品とサービスを導入しています。このモデルでは、使用した分だけを支払います。 Microsoft 365 管理センターでは、コスト管理機能は、組織の資産を管理するために必要なコストとオーバーヘッドを削減し、従量課金制の変動料金を追跡するのに役立ちます。 以下のことも実行できます。

- 月次請求書の生成に使用するコストと使用状況データをダウンロードする
- データ分析をコストにプロアクティブに適用する
- 使用しきい値を設定する
- 支出を最適化できるワークロード変更の機会を特定する (内部プロセス)

## <a name="understand-your-costs"></a>コストを把握する

Microsoft 365課金機能を使用して、請求書のコストを確認し、課金情報へのアクセスを管理できます。 大規模な組織では、通常、調達チームと財務チームが課金タスクを実行します。

Microsoft 365を使用するようにサインアップすると、自動的に課金アカウントが作成されます。 課金アカウントを使用して、請求書と支払いを管理し、コストを追跡します。 複数の課金アカウントを持つことができます。 組織の法人または販売先住所ごとに、個別の請求先アカウントを受け取ります。

## <a name="plan-and-control-costs"></a>コストの計画と管理

Microsoft 365 管理センターのコスト管理は、次のタスクを行う際に役立ち、組織のコストを計画および制御するのに役立ちます。

- **コストを分析する:** コスト管理ビューを使用すると、組織のコストを調査して分析できます。 組織別に集計されたコストを表示して、コストが発生する場所を把握し、支出の傾向を特定できます。 また、時間の経過に伴う累積コストを確認して、予算に対して毎月、四半期、または毎年のコスト傾向を見積もることもできます。
- **予算を作成する:** 予算は、組織の財務説明責任を計画し、満たすのに役立ちます。 これらは、コストのしきい値または制限を超えないようにするのに役立ちます。 予算は、コストを事前に管理するために他のユーザーに支出を通知するのに役立ちます。 また、予算を使用すると、組織内の支出が時間の経過と共にどのように進行するかを確認できます。

## <a name="view-costs"></a>コストを表示する

管理センターの **[コスト管理** ] ページには、[ **サービス** ] タブがあり、現在使用しているさまざまな製品とサービスの内訳を確認できます。

:::image type="content" source="../media/mac-billing-costmgmt/MAC-Billing-CostMgmt.png" alt-text="Microsoft 365 管理センターの [コスト管理] ページ。":::

[ **サービス** ] タブを使用して、選択した期間中に使用されているすべてのサービスの一覧を表示します。 ページ上のグラフは、上位 10 サービスの毎日のコストを分解します。 日付ピッカーを使用して、過去のコストを確認し、異なる日付範囲を使用してコストの傾向を比較します。

## <a name="download-costs"></a>コストのダウンロード

[**ダウンロード**] を選択して、毎日のコスト データを CSV またはExcel ファイルにダウンロードします。 必要に応じて、データを使用して料金をさらに分析したり、他のデータとマージしたりできます。

## <a name="create-budgets"></a>予算を作成する

予算を使用すると、料金を監視し、指定したしきい値を超えたときに確実に把握できます。 クイック 予算を作成して、毎月の下に留めるしきい値の金額を設定できます。 クイック 予算では、コストがこのしきい値を超えた場合に通知が送信されます。 通知は、予算を作成した管理者にのみ送信されます。

:::image type="content" source="../media/mac-billing-costmgmt/MAC-Billing-CostMgmt-CreateBudget.png" alt-text="Microsoft 365 管理センターの [予算の作成] ウィンドウ。":::

予算をカスタマイズするには、[ **詳細設定の構成**] を選択します。 予算に名前を付けて、予算の頻度を変更できます。 毎月、四半期、または年間予算を設定し、予算通知の送信期間を選択することもできます。

:::image type="content" source="../media/mac-billing-costmgmt/MAC-Billing-CostMgmt-CreateBudget-Details.png" alt-text="Microsoft 365 管理センターの展開された予算の詳細ウィンドウ。":::

## <a name="related-content"></a>関連コンテンツ

[Cost Management のベスト プラクティス](/azure/cost-management-billing/costs/cost-mgt-best-practices) (記事)
