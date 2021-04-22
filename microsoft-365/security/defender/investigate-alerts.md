---
title: Microsoft 365 Defender でアラートを分析する
description: デバイス、ユーザー、およびメールボックス間で表示されるアラートを分析します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18b4df6a2dbb22235d6781f1430f7a75e319fbcf
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939544"
---
# <a name="analyze-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defender でアラートを分析する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントや不審なイベントが発生したかどうかを示します。 アラートは通常、より広範な攻撃の一部であり、インシデントに関する手がかりを提供します。

Microsoft 365 Defender では、関連するアラートがまとめて集計され、インシデント [が発生します](incidents-overview.md)。 インシデントは常に攻撃の広範なコンテキストを提供しますが、アラートの分析は、より深い分析が必要な場合に有用です。 

アラート **キューには、** 現在の一連のアラートが表示されます。 Microsoft 365セキュリティ センター (& >) のクイック 起動時に[インシデント] から通知キューに[security.microsoft.com。](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="アラート キューの例":::

Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft 365 Defender など、さまざまな Microsoft セキュリティ ソリューションからのアラートがここに表示されます。

既定では、Microsoft 365 セキュリティ センターのアラート キューには、過去 30 日間の新しいアラートと進行中のアラートが表示されます。 最新のアラートはリストの一番上に表示されます。最初に確認できます。 

既定のアラート キューから [フィルター] を選択 **すると、[** フィルター] ウィンドウが表示され、そこからアラートのサブセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="アラート キューのフィルター ウィンドウの例":::

次の条件に従ってアラートをフィルター処理できます。

- 重要度
- 状態
- カテゴリ
- 検出ソース
- タグ
- ポリシー
- 影響を受け取ったアセット

## <a name="analyze-an-alert"></a>アラートの分析

メインのアラート ページを表示するには、アラートの名前を選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 セキュリティ センターのアラートの詳細ページの例":::

[警告の管理] ウィンドウ **から [メインのアラート ページを開** く] **アクションを選択** することもできます。

アラート ページは、次のセクションで構成されます。 

- アラート ストーリー
- 実行されたアクション (影響を受け取ったアセットを含む)
- 関連イベント
- 概要の詳細

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 セキュリティ センターのアラートの詳細ページの例":::

アラート ページ全体で、任意のエンティティの横にある省略記号 (**...**) を選択すると、特定のアセット ページを開く、または特定の修復手順を実行するなどの使用可能なアクションを確認できます。

### <a name="analyze-affected-assets"></a>影響を受けるアセットを分析する

[ **実行されたアクション** ] セクションには、このアラートの影響を受けるメールボックス、デバイス、ユーザーなど、影響を受けるアセットの一覧があります。 

[アクション センターで **表示] を選択して**、Microsoft 365 セキュリティ センターの [アクション センター] の [履歴] タブを表示することもできます。   

### <a name="trace-an-alerts-role-in-the-alert-story"></a>アラート ストーリー内のアラートの役割を追跡する

アラート ストーリーは、プロセス ツリー ビューでアラートに関連付けのすべてのアセットまたはエンティティを表示します。 タイトル内のアラートは、選択したアラートのページに最初に着陸した場合にフォーカスを置くアラートです。 アラート ストーリー内のアセットは展開可能でクリック可能です。 アラート ページのコンテキストでアクションを実行できるようにして、追加情報を提供し、応答を迅速化します。 

> [!NOTE]
> [アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。

### <a name="view-more-alert-information-on-the-details-page"></a>詳細ページでアラートの詳細情報を表示する

[詳細] ページには、選択したアラートの詳細と、そのアラートに関連する詳細とアクションが表示されます。 アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ページが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。

目的のエンティティを選択すると、詳細ページが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。

## <a name="manage-alerts"></a>アラートの管理

アラートを管理するには、その行のアラート キューでアラートを選択して、[警告の管理] **ウィンドウを表示** します。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="アラートの概要ウィンドウの例":::

[ **警告の管理]** ウィンドウでは、次の項目を指定できます。

- アラートの状態 (新規、解決済み、進行中)。
- アラートの分類 (設定されていない、True アラート、False Alert)。
- 真のアラートとして分類する場合は、[決定] フィールドのアラートの脅威の種類 **を指定** します。
- アラートに関するコメント。

> [!NOTE]
> タグを使用してアラートを管理する方法の 1 つ。 Microsoft Defender for Office 365 のタグ付け機能は段階的に展開され、現在プレビュー中です。 <br>
> 現在、変更されたタグ名は、更新後に作成された *アラートにのみ* 適用されます。 変更前に生成されたアラートには、更新されたタグ名は反映されません。 

このウィンドウから、次の追加アクションを実行することもできます。 

- メインアラート ページを開く
- Microsoft 脅威の専門家に相談する
- 提出の表示
- 別のインシデントへのリンク
- タイムラインでアラートを表示する
- 抑制ルールの作成

次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Microsoft 365 セキュリティ センターでのアラートに対するアクションの例":::

追加のアクションの一覧は、アラートの種類によって異なります。

## <a name="resolve-an-alert"></a>アラートを解決する

アラートの分析が完了し、解決したら、[アラートの管理] ウィンドウに移動し、その状態を [解決済み] としてマークし、False アラートまたは **True** アラートとして分類します。 true アラートの場合は、[決定] フィールドにアラートの脅威の種類 **を指定** します。

アラートを分類し、その決定を指定すると、Microsoft 365 Defender を調整して、より真のアラートと誤ったアラートを減らします。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの分析](investigate-incidents.md)
