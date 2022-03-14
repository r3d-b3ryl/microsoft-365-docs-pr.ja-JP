---
title: サーバーでコスト管理を使用Microsoft 365 管理センター
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_subscriptions
- AdminTemplateSet
search.appverid: MET150
description: 組織のコストを表示、分析、および管理するには、Microsoft 365 管理センターのコスト管理機能を使用する方法について説明します。
ms.date: 03/09/2022
ms.openlocfilehash: 64531e7b7422c3267f053e1ef098a92bfe6bed28
ms.sourcegitcommit: 9af389e4787383cd97bc807f7799ef6ecf0664d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2022
ms.locfileid: "63468750"
---
# <a name="use-cost-management-in-the-microsoft-365-admin-center"></a>サーバーでコスト管理を使用Microsoft 365 管理センター

Microsoft Customer Agreement (MCA) を使用するグローバル管理者または課金管理者の場合は、Microsoft 365 管理センター の [コスト管理] ページを使用して、サービス コストを表示、分析、および管理できます。 [コスト管理] **ページに移動するには**、管理センターの左側のナビゲーション ウィンドウで、[**BillingCost** >  管理] **を選択します**。

## <a name="before-you-begin"></a>はじめに

この記事で説明する手順を実行するには、グローバル管理者または課金管理者である必要があります。詳細については、「[管理者ロールについて](../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="what-is-cost-management"></a>コスト管理とは

コスト管理は、組織の予算を計画および制御するために使用される方法です。 Microsoft では、使用する料金のみを支払う有料課金モデルを使用する新しい製品とサービスが導入されています。 このMicrosoft 365 管理センター、コスト管理機能は、組織の資産を管理するために必要なコストとオーバーヘッドを削減し、移動時の変動費用を追跡するのに役立ちます。 以下のことも実行できます。

- 月次請求書の生成に使用されるコストと使用状況データをダウンロードする
- データ分析をコストに積極的に適用する
- 支出しきい値の設定
- 支出を最適化できるワークロード変更の機会を特定する (内部プロセス)

## <a name="understand-your-costs"></a>コストを理解する

請求機能をMicrosoft 365して、請求コストを確認し、請求情報へのアクセスを管理できます。 大規模な組織では、調達チームと財務チームが通常、課金タスクを実行します。

アカウントを使用するためにサインアップすると、Microsoft 365アカウントが自動的に作成されます。 請求アカウントを使用して請求書と支払いを管理し、コストを追跡します。 複数の請求アカウントを持つ可能性があります。 組織の法人または販売先住所ごとに、個別の請求先アカウントを受け取る。

## <a name="plan-and-control-costs"></a>コストの計画と管理

コスト管理は、Microsoft 365 管理センタータスクを実行することで、組織のコストを計画および制御するのに役立ちます。

- **コストの分析:** コスト管理ビューを使用すると、組織のコストを確認して分析できます。 組織別に集計されたコストを表示して、コストが発生する場所を把握し、支出の傾向を特定できます。 また、月次、四半期、または年次のコスト傾向を予算に対して見積もる時間の累積コストを確認できます。
- **予算の作成:** 予算は、組織の財務説明責任を計画し、満たすのに役立ちます。 これらは、コストのしきい値または制限が超過されるのを防ぐのに役立ちます。 予算は、コストを積極的に管理するために他のユーザーに支出を通知するのにも役立ちます。 また、予算を使用すると、組織の支出が時間の経過と一緒にどのように進むのか確認できます。

## <a name="view-costs"></a>コストの表示

管理 **センターの [** コスト管理] ページには [サービス] タブが表示され、現在使用しているさまざまな製品とサービスの内訳を確認できます。

:::image type="content" source="../media/mac-billing-costmgmt/MAC-Billing-CostMgmt.png" alt-text="[コスト管理] ページは、Microsoft 365 管理センター。":::

[サービス **] タブ** を使用して、選択した期間中に使用されているすべてのサービスの一覧を表示します。 ページ上のグラフは、上位 10 サービスの毎日のコストを分解します。 日付ピッカーを使用して、過去のコストを振り返り、さまざまな日付範囲を使用してコストの傾向を比較します。

## <a name="download-costs"></a>コストのダウンロード

[**ダウンロード] を** 選択して、毎日のコスト データを CSV ファイルまたはデータ ファイルExcelします。 必要に応じて、データを使用して料金をさらに分析したり、他のデータと結合することができます。

## <a name="create-budgets"></a>予算の作成

予算を使用すると、料金を監視し、指定したしきい値を超えたときに確認できます。 簡単な予算を作成して、毎月のしきい値を設定できます。 クイック予算は、コストがこのしきい値を超えたときに通知を送信します。 通知は、予算を作成した管理者にのみ送信されます。

:::image type="content" source="../media/mac-billing-costmgmt/MAC-Billing-CostMgmt-CreateBudget.png" alt-text="[予算の作成] ウィンドウMicrosoft 365 管理センター。":::

予算をカスタマイズするには、[詳細設定の **構成] を選択します**。 予算に名前を付け、予算の頻度を変更できます。 また、月次、四半期、または年間の予算を設定し、予算通知を送信する期間を選択することもできます。

:::image type="content" source="../media/mac-billing-costmgmt/MAC-Billing-CostMgmt-CreateBudget-Details.png" alt-text="[予算の詳細] ウィンドウの [予算の詳細] ウィンドウMicrosoft 365 管理センター。":::

## <a name="related-content"></a>関連コンテンツ

[コスト管理のベスト プラクティス](/azure/cost-management-billing/costs/cost-mgt-best-practices) (記事)
