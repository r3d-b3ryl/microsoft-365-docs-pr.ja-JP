---
title: カストディアン データの詳細なインデックス処理
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたと見なされたコンテンツは再処理され、完全に検索可能になります。
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750758"
---
# <a name="advanced-indexing-of-custodian-data"></a>カストディアン データの詳細なインデックス処理

保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたと見なされたコンテンツは再処理され、完全に検索可能になります。  このプロセスは、高度な *インデックス作成と呼ばれる処理です*。 画像の存在、サポートされていないファイルの種類、ファイル サイズの制限のインデックスを作成する場合など、多くの理由から、コンテンツに部分的にインデックスを作成できます。

サポートと部分的にインデックスが作成されたアイテムの処理の詳細については、以下を参照してください。

- [Advanced eDiscovery でサポートされるファイルの種類](supported-filetypes-ediscovery20.md)

- [Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)

- [Exchange Search によってインデックス処理されるファイル形式](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成結果の表示

高度なインデックス作成プロセスが完了すると、再処理の有効性を理解できます。  ケースの [処理] タブの[詳細なインデックス作成の結果] ビューに、ハイブリッド インデックスに追加されたアイテムの数が *グラフに表示されます*。  ハイブリッド インデックスは、Advanced eDiscovery が再処理されたコンテンツを格納する場所です。

このビューには、修復が必要なアイテムの数と、ファイルの種類別のエラーの別のグラフも含まれます。 詳細については、以下を参照してください。

- [データ処理中のエラー修復](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [単一アイテムのエラーの修復](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>カストディアンの高度なインデックスの更新

保管担当者が Advanced eDiscovery ケースに追加された場合、部分的にインデックスが作成されたアイテムはすべて再処理されます。 ただし、時間が経過すると、部分的にインデックスが作成されたアイテムがユーザーのメールボックスまたは OneDrive アカウントに追加される可能性があります。  必要に応じて、特定のカストディアンのインデックスを更新できます。 詳細については [、「Advanced eDiscovery ケースで保管担当者を管理する」を参照してください](manage-new-custodians.md#re-index-custodian-data)。 ケース内のすべての保管担当者のインデックスを更新するには、[処理] タブの [更新 **] インデックス** を **クリック** します。

> [!NOTE]
> カストディアン インデックスの更新は、長時間実行されるプロセスです。 1 日に 2 回以上インデックスを更新しないでお勧めします。
