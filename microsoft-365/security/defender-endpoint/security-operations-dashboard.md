---
title: Microsoft Defender セキュリティ センター セキュリティ操作ダッシュボード
description: ダッシュボードを使用して、危険にさらされているデバイスを識別し、サービスの状態を追跡し、デバイスとアラートに関する統計情報と情報を確認します。
keywords: ダッシュボード, アラート, 新規, 進行中, 解決済み, リスク, リスクのあるデバイス, 感染, レポート, 統計, グラフ, 正常性, アクティブなマルウェア検出, 脅威カテゴリ, カテゴリ, パスワード盗難, ランサムウェア, エクスプロイト, 脅威, 重要度の低い, アクティブなマルウェア
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa55d3ab9fe082d00d957cfc404ccf2a6cf35301
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331491"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a>Microsoft Defender セキュリティ センター セキュリティ操作ダッシュボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

**セキュリティ操作ダッシュボード** は、エンドポイントの検出機能と応答機能が表示される場所です。 検出が見られた場所の概要と、応答アクションが必要な場所を強調します。

ダッシュボードには、次のスナップショットが表示されます。

- アクティブなアラート
- 危険的状況のデバイス
- センサーの正常性
- サービス正常性
- 毎日のデバイス レポート
- アクティブな自動調査
- 自動調査統計
- リスクにさらされているユーザー
- 不審なアクティビティ

:::image type="content" source="images/atp-sec-ops-dashboard.png" alt-text="セキュリティ操作ダッシュボード" lightbox="images/atp-sec-ops-dashboard.png":::

アラートとデバイスを調べて調査し、ネットワーク内で疑わしいアクティビティが発生したかどうか、場所、タイミングをすばやく判断して、それらが出現したコンテキストを理解するのに役立ちます。

**セキュリティ操作ダッシュボード** には、デバイス上の重大なイベントまたは動作を識別しやすくするために、集計されたイベントが表示されます。 詳細なイベントと低レベルのインジケーターにドリルダウンすることもできます。

また、組織の全体的な正常性状態を視覚的に示すクリック可能なタイルもあります。 各タイルで、対応する概要の詳細ビューが開きます。

## <a name="active-alerts"></a>アクティブなアラート

ネットワーク内の過去 30 日間のアクティブなアラートの合計数をタイルから表示できます。 アラートは、[ **新規]** と **[進行中]** にグループ化されます。

:::image type="content" source="images/active-alerts-tile.png" alt-text="[アクティブなアラート] ページ" lightbox="images/active-alerts-tile.png":::

各グループはさらに、対応するアラート重大度レベルに分類されます。 各アラート リング内のアラートの数をクリックすると、そのカテゴリのキュー (**新規** または **進行中**) の並べ替えられたビューが表示されます。

詳細については、「アラートの [概要」を](alerts-queue.md)参照してください。

各行には、アラートの重大度カテゴリとアラートの簡単な説明が含まれます。 アラートをクリックすると、その詳細ビューを表示できます。 詳細については、「アラートと[アラートの概要Microsoft Defender for Endpoint調査](investigate-alerts.md)する」[を参照してください](alerts-queue.md)。

## <a name="devices-at-risk"></a>危険的状況のデバイス

このタイルには、アクティブなアラートの数が最も多いデバイスの一覧が表示されます。 各デバイスのアラートの合計数は、デバイス名の横の円に表示され、タイルの左端の重大度レベルでさらに分類されます (各重大度バーにマウス ポインターを合わせると、ラベルが表示されます)。

:::image type="content" source="images/devices-at-risk-tile.png" alt-text="[危険なデバイス] ページ" lightbox="images/devices-at-risk-tile.png":::

デバイスの名前をクリックすると、そのデバイスの詳細が表示されます。 詳細については、「[Microsoft Defender for Endpoint デバイスの一覧でデバイスを調査する」を参照してください](investigate-machines.md)。

タイルの上部にある [ **デバイス一覧** ] をクリックして、[ **デバイス] リスト** に直接移動し、アクティブなアラートの数で並べ替えることができます。 詳細については、「[Microsoft Defender for Endpoint デバイスの一覧でデバイスを調査する」を参照してください](investigate-machines.md)。

## <a name="devices-with-sensor-issues"></a>センサーの問題があるデバイス

[**センサーの問題があるデバイス]** タイルには、Microsoft Defender for Endpoint サービスにセンサー データを提供する個々のデバイスの機能に関する情報が表示されます。 注意が必要なデバイスの数が報告され、問題のあるデバイスを特定するのに役立ちます。

:::image type="content" source="images/atp-tile-sensor-health.png" alt-text="[センサーの問題があるデバイス] タイル" lightbox="images/atp-tile-sensor-health.png":::

サービスに正しく報告されていないデバイスの数に関する情報を提供する状態インジケーターは 2 つあります。

- **正しく構成されていない**: これらのデバイスは、センサー データをMicrosoft Defender for Endpoint サービスに部分的に報告している可能性があり、修正する必要がある構成エラーが発生する可能性があります。
- **非アクティブ**: 過去 1 か月間に 7 日間以上、Microsoft Defender for Endpoint サービスへのレポートを停止したデバイス。

いずれかのグループをクリックすると、デバイスの一覧に移動し、選択した内容に従ってフィルター処理されます。 詳細については、「 [センサーの状態を確認](check-sensor-status.md) する」と「 [デバイスの調査](investigate-machines.md)」を参照してください。

## <a name="service-health"></a>サービス正常性

**サービス正常性** タイルは、サービスがアクティブかどうか、または問題が発生した場合に通知します。

:::image type="content" source="images/status-tile.png" alt-text="[サービス正常性] ページ" lightbox="images/status-tile.png":::

サービス正常性の詳細については、「[Microsoft Defender for Endpointサービスの正常性を確認する](service-status.md)」を参照してください。

## <a name="daily-devices-reporting"></a>毎日のデバイス レポート

**[日次デバイスレポート**] タイルには、過去 30 日間に毎日報告されたデバイスの数を表す棒グラフが表示されます。 グラフ上の個々のバーにマウス ポインターを合わせると、毎日のデバイス レポートの正確な数が表示されます。

:::image type="content" source="images/atp-daily-devices-reporting.png" alt-text="[日次デバイスレポート] タイル" lightbox="images/atp-daily-devices-reporting.png":::

## <a name="active-automated-investigations"></a>アクティブな自動調査

ネットワーク内の過去 30 日間の自動調査の合計数は、[ **アクティブな自動調査]** タイルから確認できます。 調査は、[ **保留中] アクション**、[ **デバイスの待機中**]、[実行中] にグループ化 **されます**。

:::image type="content" source="images/atp-active-investigations-tile.png" alt-text="アクティブな自動調査" lightbox="images/atp-active-investigations-tile.png":::

## <a name="automated-investigations-statistics"></a>自動調査統計

このタイルには、過去 7 日間の自動調査に関連する統計情報が表示されます。 完了した調査の数、正常に修復された調査の数、調査の開始に要する平均保留中時間、アラートの修復にかかる平均時間、調査されたアラートの数、一般的な手動調査から保存された自動化の時間数を示します。 

:::image type="content" source="images/atp-automated-investigations-statistics.png" alt-text="自動調査の統計" lightbox="images/atp-automated-investigations-statistics.png":::

[ **自動調査**]、[ **修復された調査**]、[ **調査されたアラート]** をクリックして、[ **調査** ] ページに移動し、適切なカテゴリでフィルター処理できます。 これにより、コンテキスト内の調査の詳細な内訳を確認できます。

## <a name="users-at-risk"></a>リスクにさらされているユーザー

タイルには、最もアクティブなアラートを含むユーザー アカウントの一覧と、高、中、または低のアラートに表示されるアラートの数が表示されます。 

:::image type="content" source="images/atp-users-at-risk.png" alt-text="[危険なユーザー] ページ" lightbox="images/atp-users-at-risk.png":::

ユーザー アカウントをクリックすると、ユーザー アカウントの詳細が表示されます。 詳細については、「 [ユーザー アカウントを調査する」を](investigate-user.md)参照してください。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint ポータルについて](use.md)
- [ポータルの概要](portal-overview.md)
- [Microsoft Defender 脆弱性の管理 ダッシュボードを表示する](tvm-dashboard-insights.md)
- [脅威分析ダッシュボードを表示し、推奨される軽減策を実行する](threat-analytics.md)
