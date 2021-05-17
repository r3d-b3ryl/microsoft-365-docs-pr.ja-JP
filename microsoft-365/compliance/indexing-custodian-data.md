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
description: 保管担当者を Advanced eDiscovery ケースに追加すると、部分的にインデックスが作成されたと見なされたコンテンツが再処理され、完全に検索可能になります。
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911211"
---
# <a name="advanced-indexing-of-custodian-data"></a>カストディアン データの詳細なインデックス処理

保管担当者を Advanced eDiscovery ケースに追加すると、部分的にインデックスが作成されたと見なされたコンテンツが再処理され、完全に検索可能になります。  このプロセスは Advanced *indexing と呼ばれる。* 画像の存在、サポートされていないファイルの種類、またはファイル サイズの制限のインデックスを作成する場合など、さまざまな理由でコンテンツを部分的にインデックス化できます。

サポートの処理と部分的にインデックス付きアイテムの詳細については、以下を参照してください。

- [サポートされているファイルの種類 (Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)

- [Exchange Search によってインデックス処理されるファイル形式](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成結果の表示

高度なインデックス作成プロセスが完了したら、再処理の有効性を理解できます。  ケースの [処理] タブの[高度なインデックス作成結果] ビューで、ハイブリッド インデックスに追加されたアイテムの数が *グラフに一覧表示されます*。  ハイブリッド インデックスは、再Advanced eDiscoveryコンテンツを格納する場所です。

このビューには、修復が必要なアイテムの数と、ファイルの種類別のエラーの別のグラフも含まれます。 詳細については、以下を参照してください。

- [データ処理中のエラー修復](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [単一アイテムのエラーの修復](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>保管担当者の高度なインデックスの更新

保管担当者がケースに追加Advanced eDiscovery、部分的にインデックスが作成されたアイテムはすべて再処理されます。 ただし、時間が経過すると、部分的にインデックスが作成されたアイテムがユーザーのメールボックスまたはアカウントに追加OneDriveがあります。  必要に応じて、特定の保管担当者のインデックスを更新できます。 詳細については、「Manage [custodians in an Advanced eDiscovery ケース」を参照してください](manage-new-custodians.md#re-index-custodian-data)。 [処理] タブの [更新] インデックスをクリックすると、ケース内のすべての保管担当者の **インデックス** を **更新** することもできます。

> [!NOTE]
> 保管担当者インデックスの更新は、長時間実行されるプロセスです。 1 つのケースで 1 日に 2 回以上インデックスを更新しない方が推奨されます。