---
title: データ調査でサポートされているファイルの種類 (プレビュー)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: サポートされているファイルの種類と、データ調査で閲覧できる閲覧者 (プレビュー) を一覧にした表。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc4b8efb7c4212261e16f1e307c6ca05fea064ec
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817140"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>データ調査でサポートされているファイルの種類 (プレビュー)

データ調査 (プレビュー) ツールは、次の表で説明されているさまざまな方法で、多くのファイルの種類をサポートしています。 この一覧は最終処理されていません。検証テストを続行するときに、新しいファイルの種類を追加します。 この表は、証拠をレビューしているときに、利用可能なビューアーでファイルの種類を表示できるかどうかも示しています。

| Mime の種類 | File クラス | ネイティブビューアー | テキストビューアー | ビューアーに注釈を付ける | コンテナーの抽出 | 拡張機能 |
|:------|:------|:------|:------|:------|:------|:------|
|application/msword | 文書 | はい | はい | はい | いいえ | .doc、.dat |
|application/pdf | 文書 | はい | はい | はい | いいえ | .pdf |
|アプリケーション/rtf | 文書 | はい | はい | はい | いいえ | .rtf、.doc |
|application/vnd. が application | 文書 | はい | はい | はい | いいえ | .xls、.dat |
|アプリケーション/vnd を有効にします。12 | 生産性/オープンドキュメント形式 | はい | はい | いいえ | いいえ | .xlsb |
|アプリケーション/vnd を有効にします。12 | 文書 | はい | はい | はい | いいえ | .xlsm |
|アプリケーション/が application を有効にします。12 | 生産性/オープンドキュメント形式 | いいえ | はい | いいえ | いいえ | 。 xltm |
|application/vnd. ms-outlook | 生産性 | いいえ | いいえ | いいえ | いいえ | .msg |
|application/vnd. ms-outlook-pst | 生産性/コラボレーション | いいえ | いいえ | いいえ | はい | .pst |
|application/vnd. が application | 文書 | はい | はい | はい | いいえ | .ppt; .pps; .pot |
|application/vnd.ms-word.document を有効にします。 | 文書 | はい | はい | はい | いいえ | .docm |
|アプリケーション/が application を有効にします。12 | 文書 | はい | はい | はい | いいえ | normal.dotm |
|application/vnd. oasis | 文書 | はい | はい | はい | いいえ | odt  |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | 文書 | はい | はい | はい | いいえ | .pptx |
|openxmlformats-officedocument (アプリケーション/vnd) | 生産性/オープンドキュメント形式 | はい | はい | はい | いいえ | . ppsx |
|openxmlformats-officedocument (アプリケーション/vnd) | 文書 | はい | はい | はい | いいえ | . potx |
| apadsheet ml シート | 文書 | はい | はい | はい | いいえ | .xlsx |
|application/vnd. openxmlformats-officedocument | 文書 | はい | はい | はい | いいえ | 。 xltx |
|application/vnd.openxmlformats-officedocument.wordproessingml.document | 文書 | はい | はい | はい | いいえ | .docx |
|application/vnd. openxmlformats-officedocument | 文書 | はい | はい | はい | いいえ | .dotx |
|アプリケーション/vnd visio | 文書 | はい | はい | はい | いいえ | .vsd |
|アプリケーション/x-7z-圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | . 7z |
|application/xhtml + xml | 文書 | はい | はい | はい | いいえ | xhtml |
|application/xml | 文書 | はい | はい | はい | いいえ | .xml |
|アプリケーション/x-msaccess.exe | 文書 | はい | はい | はい | いいえ | .mdb |
|アプリケーション/x-mspublisher | 文書 | はい | はい | はい | いいえ | .pub |
|アプリケーション/x-rar 圧縮 | Archive/Container | いいえ | いいえ | いいえ | はい | rar |
| アプリケーション/zip | Archive/Container | いいえ | いいえ | いいえ | はい | .zip |
|image/bmp | イメージ | はい | はい | はい | いいえ | .bmp |
|イメージ/emf | イメージ | はい | はい | はい | いいえ | .emf |
|image/gif | 文書 | はい | はい | はい | いいえ | .gif |
|image/jpeg | イメージ | はい | はい | はい | いいえ | .jpg、.jpeg、.dat、jpgt |
|image/png | イメージ | はい | はい | はい | いいえ | .png |
|image/tiff | イメージ | はい | はい | はい | いいえ | .tif |
|画像/vnd. .dwg | 文書 | はい | はい | はい | いいえ | .dwg、dxf、 |
|image/wmf | 文書 | はい | はい | はい | いいえ | .wmf |
| message/rfc822 | 生産性/コラボレーション | いいえ | いいえ | いいえ | いいえ | .eml |
|text/csv | 文書 | はい | はい | はい | いいえ | .csv |
|text/html | 文書 | はい | はい | はい | いいえ | .html;. shtml.dll; .htm |
|text/plain | 文書 | はい | はい | はい | いいえ | .txt、.css、。con; pl; .csv; .dat |
|テキスト/vcard-連絡先 | 文書 | はい | はい | はい | いいえ | .vcf |
||||||||
