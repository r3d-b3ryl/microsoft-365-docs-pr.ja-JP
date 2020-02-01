---
title: データ調査でサポートされているファイルの種類 (プレビュー)
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
description: ''
ms.openlocfilehash: 055104a5b7f60fe54b421e7236143aa9af08b57f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601434"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>データ調査でサポートされているファイルの種類 (プレビュー)

データ調査 (プレビュー) では、さまざまな方法で多くのファイルの種類がサポートされています。次の表で説明します。 この一覧は最終処理されていません。検証テストを続行するときに、新しいファイルの種類を追加します。 この表は、証拠をレビューしているときに、利用可能なビューアーでファイルの種類を表示できるかどうかも示しています。

| Mime の種類 | File クラス | ネイティブビューアー | テキストビューアー | ビューアーに注釈を付ける | コンテナーの抽出 | 拡張機能 |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Document | はい | はい | はい | 不要 | .doc、.dat |
| application/pdf | Document | はい | はい | はい | 不要 | .pdf |
| アプリケーション/rtf | Document | はい | はい | はい | 不要 | .rtf;。.doc |
| application/vnd. が application | Document | はい | はい | はい | 不要 | .xls、.dat |
| アプリケーション/vnd を有効にします。12 | 生産性/オープンドキュメント形式 | はい | はい | 不要 | いいえ | .xlsb |
| アプリケーション/vnd を有効にします。12 | Document | はい | はい | はい | 不要 | .xlsm |
| アプリケーション/が application を有効にします。12 | 生産性/オープンドキュメント形式 | いいえ | はい | 不要 | いいえ | 。 xltm |
| application/vnd. ms-outlook | 生産性 | 不要 | いいえ | いいえ | いいえ | .msg |
| application/vnd. ms-outlook-pst | 生産性/コラボレーション | 不要 | いいえ | いいえ | はい | .pst |
| application/vnd. が application | Document | はい | はい | はい | 不要 | .ppt; .pps;。なべ |
| アプリケーション/vnd を有効にします。12 | Document | はい | はい | はい | 不要 | .docm |
| アプリケーション/が application を有効にします。12 | Document | はい | はい | はい | 不要 | normal.dotm |
| application/vnd. oasis | Document | はい | はい | はい | 不要 | odt  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Document | はい | はい | はい | 不要 | .pptx |
| openxmlformats-officedocument (アプリケーション/vnd) | 生産性/オープンドキュメント形式 | はい | はい | はい | 不要 | . ppsx |
| openxmlformats-officedocument (アプリケーション/vnd) | Document | はい | はい | はい | 不要 | . potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Document | はい | はい | はい | 不要 | .xlsx |
| application/vnd. openxmlformats-officedocument | Document | はい | はい | はい | 不要 | 。 xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Document | はい | はい | はい | 不要 | .docx |
| application/vnd. openxmlformats-officedocument | Document | はい | はい | はい | 不要 | .dotx |
| アプリケーション/vnd visio | Document | はい | はい | はい | 不要 | .vsd |
| アプリケーション/x-7z-圧縮 | Archive/Container | 不要 | いいえ | いいえ | はい | . 7z |
| application/xhtml + xml | Document | はい | はい | はい | 不要 | xhtml |
| application/xml | Document | はい | はい | はい | 不要 | .xml |
| アプリケーション/x-msaccess.exe | Document | はい | はい | はい | 不要 | .mdb |
| アプリケーション/x-mspublisher | Document | はい | はい | はい | 不要 | .pub |
| アプリケーション/x-rar 圧縮 | Archive/Container | 不要 | いいえ | いいえ | はい | rar |
| アプリケーション/zip | Archive/Container | 不要 | いいえ | いいえ | はい | .zip |
| image/bmp | イメージ | はい | はい | はい | 不要 | .bmp |
| イメージ/emf | イメージ | はい | はい | はい | 不要 | .emf |
| image/gif | Document | はい | はい | はい | 不要 | .gif |
| image/jpeg | イメージ | はい | はい | はい | 不要 | .jpg、.jpeg、...jpgt |
| image/png | イメージ | はい | はい | はい | 不要 | .png |
| image/tiff | イメージ | はい | はい | はい | 不要 | .tif |
| 画像/vnd. .dwg | Document | はい | はい | はい | 不要 | .dwg;。dxf |
| image/wmf | Document | はい | はい | はい | 不要 | .wmf |
| message/rfc822 | 生産性/コラボレーション | 不要 | いいえ | いいえ | いいえ | .eml |
| text/csv | Document | はい | はい | はい | 不要 | .csv |
| text/html | Document | はい | はい | はい | 不要 | .html;。shtml.dll; .htm |
| text/plain | Document | はい | はい | はい | 不要 | .txt、.css、。con; pl; .csv; .dat |
| テキスト/vcard-連絡先 | Document | はい | はい | はい | 不要 | .vcf |
||||||||
