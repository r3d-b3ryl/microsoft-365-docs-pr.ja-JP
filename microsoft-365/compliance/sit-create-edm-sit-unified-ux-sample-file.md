---
title: 新しいエクスペリエンス用の EDM SIT サンプル ファイルを作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 新しいエクスペリエンスで使用するサンプル ファイルを作成します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d14a336602a2945bcf19b182c22784c12489cdba
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360704"
---
# <a name="create-edm-sit-sample-file-for-the-new-experience"></a>新しいエクスペリエンス用の EDM SIT サンプル ファイルを作成する

完全なデータ一致 (EDM) ベースの機密情報の種類 (SIT) を作成して使用できるようにするのは、多フェーズ プロセスです。 Microsoft Purview データ損失防止ポリシー、電子情報開示、特定のコンテンツ ガバナンス タスクで使用できます。この記事では、クラシック エクスペリエンスを使用して、ワークフローと各フェーズの手順へのリンクについて説明します。

## <a name="applies-to"></a>適用対象

- 新しいエクスペリエンス

クラシック エクスペリエンスを使用して EDM SIT を作成する場合は、「 [EDM SIT クラシック エクスペリエンスを作成する](sit-create-edm-sit-classic-ux-workflow.md)」を参照してください。

## <a name="before-you-begin"></a>はじめに

- [完全なデータ一致ベースの機密情報の種類については、「ソース データをエクスポートする」の](sit-get-started-exact-data-match-export-data.md)手順を完了していることを確認します。

## <a name="formatting-the-sample-file"></a>サンプル ファイルの書式設定

システムは、スキーマを作成するためにサンプル ファイルから列名を抽出し、サンプル フィールド データをマップするベース SIT を推奨します。 ソースの機密情報テーブル ファイルと同じ形式にする必要があり、実際のデータを表す合成値を含める必要があります。 ファイルは.csv (コンマ区切り値)、.tsv (タブ区切り値)、またはパイプ区切り (|) 形式で保存できますが、実際のソースの機密情報テーブル ファイルと同じにする必要があります。 .tsv 形式は、データ値に住所などのコンマが含まれる場合に推奨されます。

- 約 10 ~ 20 行のデータを使用して、システムで十分なサンプルを操作できるようにします。
- コンマを含むフィールド値は、引用符 *"* で囲む必要があります。
- 最初の行はヘッダー行で、列名を含む必要があります。
- ファイルには、少なくとも 1 行のデータが含まれている必要があります。
- データの各行には、ヘッダーに対応する正しいフィールド数を含める必要があります。
- サンプル ファイルには、最大 32 個の列が含まれます。
- サンプル ファイルのサイズは 2.5 MB を超える可能性があります。
- 列 (フィールド) 名は文字で始まり、長さは 3 文字以上で、英数字 (A-Z、a-z、0-9) のみで構成され、スペース、アンダースコア、その他の特殊文字は含められません。 

たとえば、実際のデータが次のように表示され、タブ区切り (.tsv) 形式を使用している場合などです。

![4 つの列と人工実データの 3 行のデータを含むタブ区切りテーブルを示す画像](../media/sit-edm-tsv-actual-file.png)

その後、サンプル ファイルには同じ列ヘッダーが必要ですが、このような行には合成値を使用します。

![4 つの列と 3 行の合成代表的なデータを含むタブ区切りテーブルを示す画像](../media/sit-edm-tsv-sample-file.png)

> [!TIP]
> 新しいエクスペリエンスでは、サンプル ファイルをアップロードするか、サンプル ファイルの値を手動で入力するかを選択します。 どちらの方法でも、サンプル ファイルを作成することをお勧めします。

## <a name="next-step"></a>次のステップ

- **新しいエクスペリエンスの場合**: [EDM SIT スキーマとルール パッケージを作成](sit-create-edm-sit-unified-ux-schema-rule-package.md)する