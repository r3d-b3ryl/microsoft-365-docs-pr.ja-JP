---
title: デバイスタイムラインの手法
description: Microsoft Defender for Endpointのデバイス タイムラインについて
keywords: デバイスタイムライン, エンドポイント, MITRE, MITRE ATT&CK, テクニック, 戦術
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d724b7663bd4484c630e97362eb5766490e1fa8e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465907"
---
# <a name="techniques-in-the-device-timeline"></a>デバイスタイムラインの手法

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

特定のデバイスで発生したイベントを分析することで、調査に関するより多くの洞察を得ることができます。 まず、[デバイス] [の一覧](machines-view-overview.md)から目的のデバイスを選択します。 デバイス ページで[ **タイムライン** ] タブを選択すると、デバイスで発生したすべてのイベントを表示できます。

## <a name="understand-techniques-in-the-timeline"></a>タイムラインの手法を理解する

> [!IMPORTANT]
> 一部の情報は、パブリック プレビューのプレリリースされた製品機能に関連しており、商用リリースされる前に大幅に変更される可能性があります。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft Defender for Endpointでは、**手法** はイベント タイムラインの追加のデータ型です。 技法は、 [MITRE ATT&CK](https://attack.mitre.org/) 技法またはサブ技法に関連するアクティビティに関するより多くの洞察を提供します。

この機能は、アナリストがデバイスで観察されたアクティビティを理解できるようにすることで、調査エクスペリエンスを簡素化します。 アナリストは、さらに調査することを決定できます。

パブリック プレビューでは、デバイスのタイムラインが表示されるときに、既定で手法が使用でき、イベントと共に表示されます。

:::image type="content" source="images/device-timeline-2.png" alt-text="デバイスタイムラインの手法" lightbox="images/device-timeline-2.png":::

技術は太字で強調表示され、左側に青いアイコンが表示されます。 対応する MITRE ATT&CK ID とテクニック名は、[追加情報] の下にタグとして表示されます。

検索オプションとエクスポート オプションは、テクニックでも使用できます。

## <a name="investigate-using-the-side-pane"></a>サイド ウィンドウを使用して調査する

[テクニック] を選択して、対応するサイド ウィンドウを開きます。 ここでは、関連する ATT&CK 手法、戦術、説明などの追加情報と分析情報を確認できます。

特定の *攻撃手法* を選択して、関連する ATT&CK 手法のページを開きます。ここで、その詳細を確認できます。

右側に青いアイコンが表示されたら、エンティティの詳細をコピーできます。 たとえば、関連ファイルの SHA1 をコピーするには、青いページ アイコンを選択します。

:::image type="content" source="images/techniques-side-pane-clickable.png" alt-text="エンティティの詳細をコピーする" lightbox="images/techniques-side-pane-clickable.png":::

コマンド ラインでも同じ操作を実行できます。

:::image type="content" source="images/techniques-side-pane-command.png" alt-text="コマンド ラインをコピーするオプション" lightbox="images/techniques-side-pane-command.png":::

## <a name="investigate-related-events"></a>関連するイベントを調査する

[高度なハンティング](advanced-hunting-overview.md)を使用して、選択した手法に関連するイベントを検索するには、**関連するイベントのハント** を選択します。 これにより、高度なハンティング ページにクエリが表示され、テクニックに関連するイベントが見つかります。

:::image type="content" source="images/techniques-hunt-for-related-events.png" alt-text="[関連イベントのハント] オプション" lightbox="images/techniques-hunt-for-related-events.png":::

> [!NOTE]
> [手法] サイド ウィンドウの [ **関連イベントの検索** ] ボタンを使用したクエリでは、識別された手法に関連するすべてのイベントが表示されますが、クエリ結果にはテクニック自体は含まれません。

## <a name="customize-your-device-timeline"></a>デバイスのタイムラインをカスタマイズする

デバイス タイムラインの右上で、タイムライン内のイベントと手法の数を制限する日付範囲を選択できます。

公開する列をカスタマイズできます。 また、データ型またはイベント グループ別にフラグ付きイベントをフィルター処理することもできます。

### <a name="choose-columns-to-expose"></a>公開する列を選択する

タイムラインで公開する列を選択するには、[ **列の選択]** ボタンを選択します。

:::image type="content" source="images/filter-customize-columns.png" alt-text="列をカスタマイズできるウィンドウ" lightbox="images/filter-customize-columns.png":::


そこから、含める情報セットを選択できます。

### <a name="filter-to-view-techniques-or-events-only"></a>フィルターを使用して手法またはイベントのみを表示する

イベントまたは手法のみを表示するには、デバイスタイムラインから **[フィルター** ] を選択し、表示するデータの種類を選択します。

:::image type="content" source="images/device-timeline-filters.png" alt-text="[フィルター] ウィンドウ" lightbox="images/device-timeline-filters.png":::

## <a name="see-also"></a>関連項目

- [デバイスの一覧を表示および整理する](machines-view-overview.md)
- [デバイス タイムライン イベント フラグをMicrosoft Defender for Endpointする](device-timeline-event-flag.md)
