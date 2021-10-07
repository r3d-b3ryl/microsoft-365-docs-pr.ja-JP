---
title: CJK/Double Byte のサポートは、Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 2 Advanced eDiscovery文字セットMicrosoft 365使用する中国語、日本語、韓国語 (CJK) 言語をサポートする方法について学習します。
ms.openlocfilehash: 0d6287afb373c6c1c51ea61de3906ce994590e87
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197619"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>CJK 言語サポートのAdvanced eDiscovery

Advanced eDiscoveryでは、レビュー セットで次の高度なシナリオに対応する 2 バイト文字セット言語 (簡体字中国語、繁体字中国語、日本語、韓国語を総称して *CJK* 言語と呼ばれる) をサポートしています。

- レビュー セット [のデータをクエリする場合](review-set-search.md)。

- レビュー セット [内のドキュメントにタグを付けするときに使用します](tagging-documents.md)。

- レビュー セット [内のケース データを、](analyzing-data-in-review-set.md) ほぼ重複検出、電子メール スレッド、テーマ分析を使用して分析する場合。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CJK 文字を含むアイテムを収集する検索を作成する方法**

CJK 文字は、キーワード[](building-search-queries.md#keyword-searches)検索、キーワード[](keyword-queries-and-search-conditions.md)クエリ、および検索条件に Advanced eDiscovery使用できます。 コア電子情報開示とコンテンツ検索でコンテンツを検索する場合は、CJK 文字の検索もサポートされています。

ブール演算子 AND  [](keyword-queries-and-search-conditions.md#search-operators) **、OR、NOT、NEAR** など、すべての検索演算子と検索条件に対して CJK サポートを **提供します**。 [](keyword-queries-and-search-conditions.md#search-conditions)

コンテンツの場所またはアイテムに CJK 文字が含まれているが、検索で結果が返されない場合は、クエリ言語の国/地域アイコンをクリックします。 ![コンテンツ検索で言語と国/地域のアイコンを照会します。](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) をクリックし、検索に対応する言語と国のカルチャ コードの値を選択します。 デフォルトの言語/地域はニュートラルです。

**複数の言語を一度に検索できますか?**

検索シナリオによって異なります。

- レビュー セット[内のデータをクエリ](review-set-search.md)するときに、Advanced eDiscovery言語を検索できます。

- データを [収集する検索を作成する場合](create-search-to-collect-data.md)は、ターゲットとする言語ごとに個別の検索を作成します。 たとえば、中国語と韓国語の両方を含むドキュメントを検索する場合は、最初のクエリで [中国語] を選択し、2 番目のクエリに [韓国語] を選択します。

**レビュー セット内のクエリの言語を選択するクエリ言語と国/地域のアイコンが表示されます。レビュー セット検索でクエリ言語を指定する方法**

レビュー セットのクエリでは、ドキュメント言語を指定する必要があります。 Advanced eDiscoveryにコンテンツを追加すると、ドキュメント言語が自動的に検出されます。 これにより、レビュー セットでクエリ結果を最適化できます。

**ファイル メタデータで検出された言語を [確認できますか](view-documents-in-review-set.md#file-metadata)?**

いいえ、ファイル メタデータに検出された言語は表示されません。

**レビュー セット内のドキュメント言語でフィルター処理できますか**。

いいえ、レビュー セット内のドキュメント言語でフィルター処理、並べ替え、または検索を行う方法はありません。

**レビュー セットシナリオ用のこの CJK リリースは、既存の検索セットとレビュー セットに影響しますか?**

いいえ、既存の検索セットとレビュー セットは変更されません。 既存のデータのインデックスを再作成する必要はなく、英語のテキストの検索結果は同じです。

**表示言語を中国語、日本語、韓国語に変更する方法**

表示言語とタイム ゾーンを変更する方法については、「言語と地域の設定を設定する方法」を参照[Office 365。](/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>既知の問題

- OCR はイメージ ファイルからの CJK 文字をサポートしません

- 注釈ビューの電子メール ファイル (*.eml や[](view-documents-in-review-set.md#annotate-view)*.msg など) は、CJK 言語ではサポートされていません。

- テキスト ビューでの検索ヒット [の](view-documents-in-review-set.md#text-view) 強調表示は、CJK 言語ではサポートされていません。

- データ [の分析に](using-relevance.md) 使用される関連性モジュールは、CJK 言語をサポートしています。

- [クエリ ベースの保留は](managing-holds.md#manage-non-custodial-holds) 、CJK 言語ではサポートされていません。