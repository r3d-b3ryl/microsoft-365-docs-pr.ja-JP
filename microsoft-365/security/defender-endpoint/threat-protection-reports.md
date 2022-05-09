---
title: Microsoft Defender for Endpoint の脅威に対する保護のレポート
description: 脅威保護レポートを使用してアラートの検出、カテゴリ、重大度を追跡する
keywords: アラート検出, ソース, カテゴリ別のアラート, アラートの重大度, アラートの分類, 決定
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 55a620343aa7cda05def64acc9027925aaa96a1e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472597"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の脅威に対する保護のレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

脅威保護レポートには、組織で生成されたアラートに関する高度な情報が表示されます。 レポートには、検出ソース、カテゴリ、重大度、状態、分類、およびアラートの決定を時間の間に示す傾向のある情報が含まれています。

ダッシュボードは、次の 2 つのセクションに構成されています。

:::image type="content" source="images/threat-protection-reports.png" alt-text="脅威の保護レポート" lightbox="images/threat-protection-reports.png":::

Section|説明
---|---
1|アラートの傾向
2|アラートの概要

## <a name="alert-trends"></a>アラートの傾向
既定では、アラートの傾向には、最新の 1 日で終わる 30 日間のアラート情報が表示されます。 組織で発生している傾向をより適切に把握するために、表示される期間を調整してレポート期間を微調整できます。 期間を調整するには、ドロップダウン オプションから時間範囲を選択します。

- 30 日間
- 3 か月
- 6 か月
- カスタム

> [!NOTE]
> これらのフィルターは、アラートの傾向セクションにのみ適用されます。 アラートの概要セクションには影響しません。

## <a name="alert-summary"></a>アラートの概要

アラートの傾向は、傾向のあるアラート情報を示していますが、アラートの概要には、現在の日付の範囲を対象とするアラート情報が表示されます。

 アラートの概要を使用すると、対応するフィルターが適用された特定のアラート キューにドリルダウンできます。 たとえば、[検出ソース] カードの [EDR] バーをクリックすると、EDR検出から生成されたアラートのみを示す結果が表示されたアラート キューが表示されます。

> [!NOTE]
> 概要セクションに反映されるデータの範囲は、現在の日付の 180 日前です。 たとえば、今日の日付が 2019 年 11 月 5 日の場合、概要セクションのデータには、2019 年 5 月 5 日から 2019 年 11 月 5 日までの数値が反映されます。
>
> [傾向] セクションに適用されたフィルターは、[概要] セクションには適用されません。

## <a name="alert-attributes"></a>アラート属性

レポートは、次のアラート属性を表示するカードで構成されます。

- **検出ソース**: アラートをトリガーするためにMicrosoft Defender for Endpointによって使用されるデータを提供するセンサーと検出テクノロジに関する情報を示します。
- **脅威カテゴリ**: アラートをトリガーした脅威または攻撃アクティビティの種類を示し、セキュリティ操作の対象となる可能性のある領域を示します。
- **重大度**: アラートの重大度レベルを示し、組織に対する脅威の潜在的な影響と、それに対処するために必要な応答のレベルを示します。
- **状態**: アラートの解決状態を示し、手動アラート応答の効率と自動修復 (有効な場合) を示します。
- **分類&決定**: 解決時にアラートを分類した方法、実際の脅威 (真のアラート) として分類したか、誤検出 (偽アラート) として分類したかを示します。 これらのカードには、解決されたアラートの決定も表示され、検出された実際の脅威の種類や誤って検出された正当なアクティビティなどの追加の分析情報が提供されます。

## <a name="filter-data"></a>データをフィルター処理する

特定の属性を持つアラートを含めたり除外したりするには、指定されたフィルターを使用します。

> [!NOTE]
> これらのフィルターは、レポート **内のすべての** カードに適用されます。

たとえば、重大度の高いアラートについてのみデータを表示するには、次のようにします。

1. [ **インシデント & アラート** \> **アラート** \> **フィルター>重大度] で**、[ **高**] を選択します。
2. **[重大度]** の他のすべてのオプションがオフになっていることを確認します。
3. **[適用]** を選択します。

## <a name="related-topic"></a>関連トピック

- [デバイスの正常性とコンプライアンスのレポート](machine-reports.md)
