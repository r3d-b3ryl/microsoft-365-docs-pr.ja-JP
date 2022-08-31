---
title: クエリ結果をガイド モードで操作して、Microsoft 365 Defenderで検索する
description: Microsoft 365 Defenderで高度なハンティングを行うためのガイドモードでクエリ結果を使用してカスタマイズする
keywords: ガイドモード, 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 7b14628c50e16c976471f3daf8764166f6cdd0a2
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67476084"
---
# <a name="work-with-query-results-in-guided-mode"></a>ガイド モードでクエリ結果を操作する
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

ガイドモードを使用したハンティングでは、クエリの結果が [ **結果** ] タブに表示されます。 

[![[結果] タブ](../../media/guided-hunting/results-view.png)のスクリーンショット ](../../media/guided-hunting/results-view.png#lightbox)

結果をさらに処理するには、[エクスポート] を選択して CSV ファイルに **エクスポート** します。 これにより、使用する CSV ファイルがダウンロードされます。

その他の情報は、[結果] ビューで確認できます。
- 結果リスト内のレコードの数 ([検索] ボタンの横)
- クエリの実行時間の期間
- クエリのリソース使用量

## <a name="view-more-columns"></a>その他の列を表示する

簡単に表示できるように、いくつかの標準列が結果に含まれています。 

その他の列を表示するには:
1. 結果ビューの右上にある **[列のカスタマイズ** ] を選択します。
 

2. ここから、結果ビューに含める列を選択し、非表示にする列の選択を解除します。 


[![結果ビュー](../../media/guided-hunting/results-view-customize-columns.png)に追加できる列の一覧のスクリーンショット ](../../media/guided-hunting/results-view-customize-columns-tb.png#lightbox)

3. [ **適用]** を選択すると、列が追加された結果が表示されます。 必要に応じて、スクロール バーを使用します。


## <a name="see-also"></a>関連項目
- [高度なハンティング クォータと使用パラメーター](advanced-hunting-limits.md)
- [高度なモードに切り替える](advanced-hunting-query-builder-details.md#switch-to-advanced-mode-after-building-a-query)
- [ガイド モードでクエリを絞り込む](advanced-hunting-query-builder-details.md)