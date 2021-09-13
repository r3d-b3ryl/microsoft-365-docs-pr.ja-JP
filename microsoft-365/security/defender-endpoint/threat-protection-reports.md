---
title: Microsoft Defender for Endpoint の脅威に対する保護のレポート
description: 脅威保護レポートを使用してアラートの検出、カテゴリ、重大度を追跡する
keywords: アラート検出, ソース, カテゴリ別アラート, アラート重大度, アラート分類, 決定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 327217a9682e8a50c41c2696292d1a453fbd8cf9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59164902"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の脅威に対する保護のレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

脅威保護レポートは、組織で生成されたアラートに関する高レベルの情報を提供します。 このレポートには、検出元、カテゴリ、重大度、状態、分類、および時間の間のアラートの決定を示す傾向情報が含まれています。

ダッシュボードは、次の 2 つのセクションに構成されます。

![脅威保護レポートのイメージ。](images/threat-protection-reports.png)

Section | 説明 
:---|:---
1 | アラートの傾向
2 | アラートの概要

## <a name="alert-trends"></a>アラートの傾向
既定では、アラートの傾向には、最新の 1 日で終了する 30 日間の期間のアラート情報が表示されます。 組織で発生している傾向についてより良い視点を得るために、表示される期間を調整してレポート期間を微調整できます。 期間を調整するには、ドロップダウン オプションから時間範囲を選択します。

- 30 日間
- 3 か月
- 6 か月
- Custom

>[!NOTE]
>これらのフィルターは、[アラートの傾向] セクションにのみ適用されます。 アラートの概要セクションには影響を与えかねない。


## <a name="alert-summary"></a>アラートの概要
アラートの傾向に傾向アラート情報が表示される一方で、アラートの概要には、現在の日を対象にしたアラート情報が表示されます。

 アラートの概要を使用すると、対応するフィルターが適用された特定のアラート キューにドリルダウンできます。 たとえば、[検出ソース] カードの [EDR] バーをクリックすると、通知キューに通知キューが表示され、検出から生成されたEDR表示されます。 

>[!NOTE]
>[概要] セクションに反映されるデータの範囲は、現在の日付の 180 日前です。 たとえば、今日の日付が 2019 年 11 月 5 日の場合、概要セクションのデータには、2019 年 5 月 5 日から 2019 年 11 月 5 日の数値が反映されます。<br>
> [傾向] セクションに適用されるフィルターは、[概要] セクションには適用されません。 

## <a name="alert-attributes"></a>アラート属性
レポートは、次のアラート属性を表示するカードで構成されています。

- **検出ソース**: Microsoft Defender for Endpoint がアラートをトリガーするために使用するデータを提供するセンサーと検出テクノロジに関する情報を示します。

- **脅威のカテゴリ**: アラートをトリガーした脅威または攻撃アクティビティの種類を示し、セキュリティ操作の可能なフォーカス領域を示します。

- **重大度**: アラートの重大度レベルを示し、組織に対する脅威の潜在的な影響の集合的な潜在的な影響と、脅威に対処するために必要な対応のレベルを示します。

- **Status**: アラートの解決状態を示し、手動のアラート応答の効率と自動修復 (有効な場合) を示します。 

- **分類&決定**: 解決時にアラートを分類した方法、実際の脅威 (真のアラート) として分類したかどうか、または誤った検出 (誤ったアラート) として分類した方法を示します。 これらのカードには、解決されたアラートの決定も表示され、検出された実際の脅威の種類や、誤って検出された正当なアクティビティなどの追加の分析情報が提供されます。

## <a name="filter-data"></a>データをフィルター処理する

指定されたフィルターを使用して、特定の属性を持つアラートを含めるか除外します。

>[!NOTE]
>これらのフィルターは、 **レポート内のすべての** カードに適用されます。

たとえば、重大度の高いアラートに関するデータのみを表示するには、次の処理を行います。

1. [**インシデント] で&**  >  **アラート**  >  **フィルター>重大度]** で、[高] を **選択します**。
2. [重大度] の下の他のすべての **オプションが選択** 解除されている必要があります。
3. **[適用]** を選択します。

## <a name="related-topic"></a>関連トピック
- [デバイスの正常性とコンプライアンスのレポート](machine-reports.md)
