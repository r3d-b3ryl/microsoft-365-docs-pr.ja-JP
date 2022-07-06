---
title: 電子情報開示の CJK/Double Byte サポート (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 のMicrosoft Purview eDiscovery (Premium) で、2 バイト文字セットを使用する中国語、日本語、韓国語 (CJK) 言語をサポートする方法について説明します。
ms.openlocfilehash: a16f1f63deee7cbc77b105c9c49431a8eeda0e71
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636207"
---
# <a name="cjk-language-support-for-ediscovery-premium"></a>電子情報開示の CJK 言語サポート (Premium)

Microsoft Purview eDiscovery (Premium) では、レビュー セットの次の高度なシナリオに対して、2 バイト文字セット言語 (簡体字中国語、繁体字中国語、日本語、韓国語など)がサポートされています。これらは *CJK* 言語と総称されます)。

- [レビュー セット内のデータに対してクエリを実行](review-set-search.md)する場合。

- [レビュー セット内のドキュメントにタグを付](tagging-documents.md)けるとき。

- ほぼ重複データ検出、電子メール スレッド、テーマ分析を使用して [、レビュー セット内のケース データを分析](analyzing-data-in-review-set.md) する場合。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CJK 文字を含むアイテムを収集する検索を作成操作方法?**

電子情報開示 (Premium) でコンテンツを検索するときに、 [キーワード検索](building-search-queries.md#keyword-searches)、 [キーワード クエリ、検索条件](keyword-queries-and-search-conditions.md) に CJK 文字を使用できます。 CJK 文字の検索は、Microsoft Purview eDiscovery (Standard) および Content Search でコンテンツを検索するときにもサポートされます。

ブール演算子 **AND**、**OR**、**NOT**、**NEAR** など、すべての [検索演算子](keyword-queries-and-search-conditions.md#search-operators)と [検索条件](keyword-queries-and-search-conditions.md#search-conditions)に対して CJK サポートを提供しています。

コンテンツの場所またはアイテムに CJK 文字が含まれていて、検索によって結果が返されない場合は、クエリ言語の国/地域アイコンをクリックします。 ![コンテンツ検索のクエリ言語-国/地域アイコン。](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) をクリックし、検索に対応する言語と国のカルチャ コードの値を選択します。 デフォルトの言語/地域はニュートラルです。

**複数の言語を一度に検索できますか?**

検索シナリオによって異なります。

- 電子情報開示 (Premium) [でレビュー セット内のデータにクエリを実行](review-set-search.md) すると、複数の言語を検索できます。

- [データを収集する検索を作成](create-draft-collection.md)するときは、ターゲットとする言語ごとに個別のコレクションを作成します。 たとえば、中国語と韓国語の両方を含むドキュメントを検索する場合は、最初のコレクションに中国語を選択し、2 番目のコレクションに韓国語を選択します。

**レビュー セット内のクエリの言語を選択するためのクエリ言語 -country/region アイコンが表示されません。レビュー セット検索でクエリ言語を指定するにはどうすればよいですか?**

レビュー セットクエリの場合、ドキュメント言語を指定する必要はありません。 電子情報開示 (Premium) は、レビュー セットにコンテンツを追加すると、ドキュメント言語を自動的に検出します。 これにより、レビュー セットでクエリ結果を最適化できます。

**検出された言語を [ファイル メタデータ](view-documents-in-review-set.md#file-metadata)に表示できますか?**

いいえ。ファイル メタデータに検出された言語は表示されません。

**レビュー セット内のドキュメント言語でフィルター処理できますか**?

いいえ。レビュー セット内のドキュメント言語でフィルター処理、並べ替え、検索を行うことはできません。

**レビュー セットのシナリオに対するこの CJK リリースは、既存の検索セットとレビュー セットのいずれかに影響しますか?**

いいえ。既存の検索セットとレビュー セットは変更されません。 既存のデータのインデックスを再作成する必要はありません。英語テキストの検索結果も同じになります。

**表示言語操作方法中国語、日本語、韓国語に変更しますか?**

表示言語とタイム ゾーンを変更する方法については、「[Office 365の言語と地域の設定を設定する方法」を](/office365/troubleshoot/access-management/set-language-and-region)参照してください。

## <a name="known-issues"></a>既知の問題

- OCR では、イメージ ファイルの CJK 文字がサポートされていません

- [注釈ビュー](view-documents-in-review-set.md#annotate-view)の電子メール ファイル (*.eml や *.msg など) は、CJK 言語ではサポートされていません。

- [テキスト ビュー](view-documents-in-review-set.md#text-view)での検索ヒットの強調表示は、CJK 言語ではサポートされていません。

- データの分析に使用される [関連性モジュール](using-relevance.md) では、CJK 言語はサポートされていません。

- [クエリ ベースの保留は](managing-holds.md#manage-non-custodial-holds) 、CJK 言語ではサポートされていません。