---
title: 高度な電子情報開示のための CJK/ダブルバイトのサポート
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 の Advanced eDiscovery が、2バイト文字セットを使用する中国、日本語、および韓国語 (CJK) の言語をサポートする方法について説明します。
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626937"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>高度な電子情報開示のための CJK 言語サポート

高度な電子情報開示では、2バイト文字セットの言語がサポートされています (これらには、簡体字中国語、繁体字中国語、日本語、韓国語が含まれています)。レビューセットの次の高度なシナリオについては、次 *のように* なります。

- [レビューセット内のデータに対してクエリ](review-set-search.md)を実行する場合。

- [レビューセット内のドキュメントにタグ付け](tagging-documents.md)するとき。

- 近い重複検出、電子メールスレッド、およびテーマ分析を使用して、 [レビューセット内のケースデータを分析](analyzing-data-in-review-set.md) する場合。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**CJK 文字を含むアイテムを収集するために検索を作成するにはどうすればよいですか?**

高度な電子情報開示のコンテンツを検索するときに、 [キーワード検索](building-search-queries.md#keyword-searches)、 [キーワードクエリ、および検索条件](keyword-queries-and-search-conditions.md) に CJK 文字を使用することができます。 主な電子情報開示とコンテンツ検索でコンテンツを検索する場合も、CJK 文字の検索がサポートされています。

すべての [検索演算子](keyword-queries-and-search-conditions.md#search-operators) と [検索条件](keyword-queries-and-search-conditions.md#search-conditions)(ブール演算子 **and**、 **OR**、 **NOT**、 **NEAR**など) に対して、CJK サポートが提供されています。

コンテンツの場所またはアイテムに CJK 文字が含まれているが、検索結果が返されない場合は、[クエリ言語-国/地域] アイコンをクリックします。 ![クエリ言語-コンテンツ検索の国/地域アイコン](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) を選択して、検索に対応する言語-国のカルチャコード値を選択します。 デフォルトの言語/地域はニュートラルです。

**一度に複数の言語を検索できますか。**

検索シナリオによって異なります。

- 高度な電子情報開示の [レビューセットのデータ](review-set-search.md) に対してクエリを実行すると、複数の言語を検索できます。

- データを [収集する](create-search-to-collect-data.md)ための検索を作成するときは、対象とする言語ごとに個別の検索を作成します。 たとえば、中国語と韓国語の両方を含むドキュメントを検索する場合は、最初のクエリで中国語を選択し、2番目のクエリに対して [韓国語] を選択します。

**[クエリ言語-国/地域] アイコンが表示されないので、レビューセット内のクエリの言語を選択できます。レビューセットの検索でクエリ言語を指定するにはどうすればよいですか?**

レビューセットのクエリの場合は、ドキュメントの言語を指定する必要はありません。 コンテンツをレビューセットに追加すると、高度な電子情報開示によってドキュメント言語が自動的に検出されます。 これにより、クエリ結果をレビューセットで最適化することができます。

**検出された言語が [ファイルメタデータ](view-documents-in-review-set.md#file-metadata)に表示されますか。**

いいえ、ファイルメタデータに検出された言語は表示できません。

**校閲セットでドキュメントの言語によってフィルター**を適用できますか。

いいえ。校閲セットでドキュメントの言語によるフィルター、並べ替え、または検索を行うことはできません。

**この CJK リリースをレビューセットシナリオで既存の検索およびレビューセットに影響を与えるかどうか。**

いいえ。既存の検索と校閲セットは変更されません。 既存のデータのインデックスを再作成する必要はありません。また、英語のテキストの検索結果も同じになります。

**表示言語を中国語、日本語、または韓国語に変更するにはどうすればよいですか?**

表示言語とタイムゾーンを変更する方法については、「 [Office 365 の言語と地域の設定を設定する方法](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)」を参照してください。

## <a name="known-issues"></a>既知の問題

- OCR では、画像ファイルの CJK 文字はサポートされていません

- [注釈ビュー](view-documents-in-review-set.md#annotate-view)での電子メールファイル (* .eml、* .msg など) は、CJK 言語ではサポートされていません。

- [テキストビュー](view-documents-in-review-set.md#text-view)での検索の検索は、CJK 言語ではサポートされていません。

- データの分析に使用される [関連性モジュール](using-relevance.md) は、CJK 言語をサポートしていません。

- [クエリベースの保持](managing-holds.md#manage-non-custodial-holds) は、CJK 言語ではサポートされていません。 
