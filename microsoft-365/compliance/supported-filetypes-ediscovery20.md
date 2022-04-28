---
title: 電子情報開示でサポートされているファイルの種類 (プレミアム)
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
description: 電子情報開示 (プレミアム) でサポートされているファイルの種類 (電子情報開示 (プレミアム) の OCR 機能でサポートされているイメージ ファイルの種類を含む、Microsoft 365電子情報開示でサポートされているファイルの種類の一覧。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 422200b3015ff86566507cbe3f63bc2a75a84bea
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095798"
---
# <a name="supported-file-types-in-ediscovery-premium"></a>電子情報開示でサポートされているファイルの種類 (プレミアム)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview 電子情報開示 (プレミアム) は、さまざまなレベルで多くのファイルの種類をサポートしています。 サポート ファイルの種類については、この記事の次の表で説明します。 この一覧は確定されておらず、検証テストを続行する際に新しいファイルの種類を追加します。 これらのテーブルは、テキスト抽出 (および画像ファイルの光学式文字認識または OCR テキスト抽出) でファイルの種類がサポートされているかどうかを示します。ネイティブ ビューアーで表示でき、電子情報開示の注釈ビューアー (プレミアム) でもサポートされます。

## <a name="archive--container"></a>アーカイブ/コンテナー

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|コンテナーの抽出|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|
|application/x-7z-compressed|はい|はい|はい|.7z|
|application/x-rar-compressed|はい|はい|はい|.rar|
|application/x-tar|はい|はい|はい|.tar|
|application/zip|はい|はい|はい|.zip|
|

## <a name="audio--video"></a>オーディオ/ビデオ

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/mp4|はい|はい|いいえ|はい|なし|.f4v; .m4a; .m4v;.mp4; .mp4v;.mpeg; .mpeg4|
|audio/mpeg|はい|はい|いいえ|はい|なし|.mpeg|
|video/3gpp|はい|はい|いいえ|はい|なし|.3gp|
|video/3gpp2|はい|はい|いいえ|はい|なし|.3g2; .3gp2|
|video/quicktime|はい|はい|いいえ|はい|いいえ|.moov; .mov; .qt|
|video/x-m4v|はい|はい|いいえ|はい|いいえ|.m4v|
|

## <a name="database"></a>Database

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-msaccess|はい|はい|はい|いいえ|いいえ|.mdb|
|

## <a name="email"></a>メール

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-outlook|はい|はい|はい|はい|はい|.msg|
|message/rfc822|はい|はい|はい|はい|はい|.eml|
|text/vcard-contact|はい|はい|はい|はい|はい|.vcf|
|

## <a name="email-container"></a>電子メール コンテナー

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|コンテナーの抽出|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|
|application/mbox|はい|はい|はい|.mbox|
|application/vnd.ms-outlook-pst|はい|はい|はい|.pst|
|

## <a name="html"></a>HTML

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/xhtml+xml|はい|はい|はい|はい|はい|.xhtml|
|application/xml|はい|はい|はい|はい|はい|.xml|
|text/html|はい|はい|はい|はい|はい|.htm;.html; .shtml|
|

## <a name="image"></a>イメージ

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|OCR テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|image/bmp|はい|はい|はい|はい|はい|.bmp|
|image/emf|はい|はい|はい|はい|はい|*.emf|
|image/gif|はい|はい|はい|はい|はい|.gif|
|image/jpeg|はい|はい|はい|はい|はい|.jpeg;.jpg|
|image/png|はい|はい|はい|はい|はい|.png|
|image/svg+xml|はい|はい|はい|はい|いいえ|.svg|
|image/tiff|はい|はい|はい|はい|はい|.tif|
|image/vnd.dwg|はい|はい|はい|はい|はい|.dwg; .dxf|
|image/wmf|はい|はい|はい|はい|はい|.wmf|
|

## <a name="microsoft-excel"></a>Microsoft Excel

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-excel|はい|はい|はい|はい|はい|.dat;.xls|
|application/vnd.ms-excel.sheet.binary.macroenabled.12|はい|はい|はい|はい|なし|.xlsb|
|application/vnd.ms-excel.sheet.macroenabled.12|はい|はい|はい|はい|はい|.xlsm|
|application/vnd.ms-excel.template.macroenabled.12|はい|はい|はい|いいえ|なし|.xltm|
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet|はい|はい|はい|はい|はい|.xlsx|
|application/vnd.openxmlformats-officedocument.spreadsheetml.template|はい|はい|はい|はい|はい|.xltx|
|

## <a name="microsoft-onenote"></a>Microsoft OneNote

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/onenote|はい|はい|はい|いいえ|いいえ|.one|
|

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-powerpoint|はい|はい|はい|はい|はい|.pot; .pps;.ppt|
|application/vnd.openxmlformats-officedocument.presentationml.presentation|はい|はい|はい|はい|はい|.pptx|
|application/vnd.openxmlformats-officedocument.presentationml.slideshow|はい|はい|はい|はい|はい|.ppsx|
|application/vnd.openxmlformats-officedocument.presentationml.template|はい|はい|はい|はい|はい|.potx|
|

## <a name="microsoft-project"></a>Microsoft Project

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-project|はい|はい|はい|いいえ|はい|.mpp|
|

## <a name="microsoft-publisher"></a>Microsoft Publisher

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-mspublisher|はい|はい|はい|はい|はい|.pub|
|

## <a name="microsoft-visio"></a>Microsoft Visio

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-visio.drawing|はい|はい|はい|はい|なし||
|application/vnd.visio|はい|はい|はい|はい|はい|.vsd|
|

## <a name="microsoft-word"></a>Microsoft Word

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/msword|はい|はい|はい|はい|はい|.dat;.doc|
|application/rtf|はい|はい|はい|はい|はい|.doc; .rtf|
|application/vnd.ms-word.document.macroenabled.12|はい|はい|はい|はい|はい|.docm|
|application/vnd.ms-word.template.macroenabled.12|はい|はい|はい|はい|はい|.dotm|
|application/vnd.openxmlformats-officedocument.wordprocessingml.document|はい|はい|はい|はい|はい|.docx|
|application/vnd.openxmlformats-officedocument.wordprocessingml.template|はい|はい|はい|はい|はい|.dotx|
|

## <a name="microsoft-works"></a>Microsoft Works

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-works-ss|はい|はい|いいえ|いいえ|なし|.wps|
|application/vnd.ms-works-wp|はい|はい|いいえ|いいえ|なし|.wps|
|

## <a name="open-document-format"></a>ドキュメント形式を開く

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.oasis.opendocument.text|はい|はい|はい|はい|はい|.odt|
|

## <a name="other"></a>その他

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/json|はい|はい|はい|はい|はい|×|
|application/octet-stream|はい|いいえ|いいえ|いいえ|いいえ|.fluid|
|application/vnd.ms-graph|はい|はい|いいえ|いいえ|なし||
|application/winhlp|はい|はい|いいえ|いいえ|なし|.hlp|
|application/x-tnef|はい|はい|いいえ|いいえ|なし||
|

## <a name="plain-text"></a>プレーン テキスト

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|text/csv|はい|はい|はい|はい|はい|.csv|
|text/plain|はい|はい|はい|はい|はい|.con; .css;.csv; .dat; .pl;.txt|
|

## <a name="portable-document-format"></a>Portable Document Format

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/pdf|はい|はい|はい|はい|はい|.pdf|
|

## <a name="word-perfect"></a>Word Perfect

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.wordperfect;version=5.0|はい|はい|はい|いいえ|なし|.wpd|
|application/vnd.wordperfect;version=5.1|はい|はい|はい|いいえ|いいえ|.wpd|
|application/vnd.wordperfect;version=6.x|はい|はい|はい|いいえ|いいえ|.wpd|
|

## <a name="word-pro"></a>Word Pro

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|ビューアーに注釈を付ける|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.lotus-wordpro|はい|はい|いいえ|いいえ|なし|.lwp|
|
