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
description: 高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスと見なされたコンテンツはすべて再利用され、完全に検索可能になります。
ms.openlocfilehash: 95e087884b65628565e596dc8ae9f33aadc4cd9f
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527557"
---
# <a name="advanced-indexing-of-custodian-data"></a>カストディアン データの詳細なインデックス処理

高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスと見なされたコンテンツはすべて再利用され、完全に検索可能になります。  このプロセスは、*高度なインデックス*と呼ばれます。 画像の存在、サポートされていないファイルの種類、インデックスファイルサイズの制限が発生したなど、さまざまな理由でコンテンツを部分的にインデックス処理することができます。

処理のサポートおよび部分的なインデックスが作成されたアイテムの詳細については、以下を参照してください。

- [高度な電子情報開示でサポートされているファイルの種類](supported-filetypes-ediscovery20.md)

- [Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)

- [Exchange Search によってインデックス処理されるファイル形式](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>高度なインデックス作成の結果を表示する

高度なインデックス処理が完了すると、再処理の有効性について理解することができます。  ケースに対して [**処理**] タブの [詳細なインデックス作成の結果] ビューに、*ハイブリッドインデックス*に追加されたアイテムの数がグラフに表示されます。  ハイブリッドインデックスは、高度な電子情報開示が再処理されたコンテンツを格納する場所です。

このビューには、修復を必要とするアイテムの数と、ファイルの種類別のエラーのグラフも含まれています。 詳細については、以下をご参照ください。

- [データ処理中のエラー修復](error-remediation.md)

- [単一アイテムのエラーの修復](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>保管担当者の高度なインデックスを更新する

高度な電子情報開示ケースに保管担当者が追加されると、部分的にインデックスが作成されたすべてのアイテムが再処理されます。 ただし、時間が経過すると、インデックスが作成されたアイテムの数が多くなると、ユーザーのメールボックスまたは OneDrive アカウントに追加されることがあります。  必要に応じて、特定の保管担当者のインデックスを更新できます。 詳細については、「 [Manage 保管担当者 in a Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data)」を参照してください。 [**処理**] タブの [**更新インデックス**] をクリックして、すべての保管担当者のインデックスを更新することもできます。

> [!NOTE]
> 保管担当者インデックスの更新は、長時間実行されるプロセスです。 ケースでは、インデックスを1日に複数回更新しないことをお勧めします。
