---
title: カストディアン データの詳細なインデックス処理
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: カストディアンが電子情報開示 (Premium) ケースに追加されると、部分的にインデックスが作成されたと見なされたすべてのコンテンツが再処理され、完全に検索できるようになります。
ms.openlocfilehash: 0d0474306415a59615960cc15580af0f67dc49aa
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629555"
---
# <a name="advanced-indexing-of-custodian-data"></a>カストディアン データの詳細なインデックス処理

カストディアンが電子情報開示 (Premium) ケースに追加されると、部分的にインデックスが作成された、またはインデックス作成エラーが発生したと見なされたコンテンツは、インデックスが再作成されます。 このインデックス再作成プロセスは *、高度なインデックス作成* と呼ばれます。 コンテンツが部分的にインデックス付けされているか、インデックス作成エラーが発生する理由は多数あります。 これには、イメージ ファイル、ファイル内のイメージの存在、サポートされていないファイルの種類、ファイル サイズのインデックス作成の制限が含まれます。 SharePoint ファイルの場合、項目に対してのみ実行される高度なインデックス作成は、部分的にインデックス付けされているか、インデックス作成エラーがあるアイテムとしてマークされます。 Exchange では、画像の添付ファイルを含む電子メール メッセージは、部分的にインデックス付けされているか、インデックス作成エラーでマークされません。 つまり、これらのファイルは高度なインデックス作成プロセスによってインデックスが再作成されません。

サポートと部分的にインデックスが付けられたアイテムの処理の詳細については、次を参照してください。

- [電子情報開示でサポートされているファイルの種類 (Premium)](supported-filetypes-ediscovery20.md)

- [電子情報開示で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)

- [Exchange Search によってインデックス処理されるファイル形式](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成結果の表示

高度なインデックス作成プロセスが完了したら、再処理の有効性を理解できます。  ケースの [ **処理** ] タブの [高度なインデックス作成結果] ビューで、 *ハイブリッド インデックス* に追加された項目の数がグラフに一覧表示されます。  ハイブリッドインデックスは、電子情報開示 (プレミアム) が再処理されたコンテンツを保存する場所です。

このビューには、修復が必要な項目の数と、ファイルの種類別のエラーの別のグラフも含まれます。 詳細については、以下を参照してください。

- [データ処理中のエラー修復](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [単一アイテムのエラーの修復](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>カストディアンの高度なインデックスを更新する

カストディアンが電子情報開示 (Premium) ケースに追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。 ただし、時間が経過すると、ユーザーのメールボックスまたは OneDrive アカウントに、より部分的にインデックスが付けられたアイテムが追加される場合があります。  必要に応じて、特定のカストディアンのインデックスを更新できます。 詳細については、「 [電子情報開示 (Premium) ケースでのカストディアンの管理](manage-new-custodians.md#reindex-custodian-data)」を参照してください。 [**処理**] タブの [更新] インデックスをクリックして、ケース内のすべてのカストディアンの **インデックスを更新** することもできます。

> [!NOTE]
> カストディアン インデックスの更新は、長時間実行されるプロセスです。 1 日に 1 回以上インデックスを更新しないことをお勧めします。
