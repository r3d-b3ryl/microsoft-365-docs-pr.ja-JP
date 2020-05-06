---
title: 高度な電子情報開示のレビューセットのデータを分析する
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
description: 高度な電子情報開示ケースを分析する際にドキュメントセットを整理するために使用できるツールについて説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87788e444a5ef671586567510448dab8b9deddcd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033821"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>高度な電子情報開示のレビューセットのデータを分析する

収集されたドキュメントの数が多い場合は、それらをすべて確認するのは困難です。 Advanced eDiscovery には、ドキュメントを分析して、情報が失われずにレビューされるドキュメントのボリュームを減らし、一貫性のある方法でドキュメントを整理するのに役立つさまざまなツールが用意されています。 これらの機能の詳細については、以下を参照してください。

- [準重複の検出](near-duplicates.md)

- [電子メールのスレッド化](email-threading.md)

- [テーマ](themes.md)

レビューセット内のデータを分析するには、次のようにします。

1. ケースの分析設定を構成します。 詳細については、「 [Configure search and analytics settings](configure-search-analytics-settings.md)」を参照してください。

2. 分析するレビューセットを開きます。

3. [**レビューセットの管理**] をクリックします。

4. [**レビューセットの分析を実行**する] をクリックします。

ケースの [**ジョブ**] タブで、分析の進行状況を確認できます。

 分析が完了したら、analytics レポートを表示し、分析の出力に対してレビューセット内のクエリを実行し ([レビューセット内のクエリ](review-set-search.md)を参照)、特定のドキュメントの関連ドキュメントを表示できます (「[レビューセット内のデータ](reviewing-data-in-review-set.md)のレビュー」を参照してください)。

## <a name="analytics-report"></a>分析レポート

レビューセットの分析レポートを表示するには、次のようにします。

1. レビューセットを開きます。

2. [**レビューセットの管理**] をクリックします。

3. [**レポートの表示**] をクリックします。

レポートには、分析から7つのコンポーネントがあります。

- **ターゲットの作成:** レビューセットに含まれている電子メールメッセージ、添付ファイル、およびルースドキュメントの数。

- **ドキュメント (添付ファイルを除く):** ピボットされた非圧縮ドキュメントの数、ピボットの一意の重複、または別のドキュメントの正確な複製。

- **メール:** Inclusives の電子メールメッセージ数、包括的なコピー、包括 minuses、または上記のいずれでもないもの。

- **添付ファイル:** レビューセット内の別の電子メール添付ファイルの一意の、または重複する電子メール添付ファイルの数。

- **種類別のファイル数:** ファイル拡張子で識別されるファイルの数。

- **ソース別のドキュメント:** 元のデータソースによってコンテンツの概要を示します。

- **プロセスによって集約**されたドキュメント:レビューによるコンテンツの概要セットのプロセス。 
