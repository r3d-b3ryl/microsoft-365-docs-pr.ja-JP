---
title: サポートされているファイルの種類 (Advanced eDiscovery
f1.keywords:
  - NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: null
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
  - MOE150
  - MET150
description: サポートされているファイルの種類の一覧 (Microsoft 365 Advanced eDiscovery の OCR 機能でサポートされるイメージ ファイルの種類をAdvanced eDiscovery。
ms.custom: seo-marvel-apr2020
---

# <a name="supported-file-types-in-advanced-ediscovery"></a>サポートされているファイルの種類 (Advanced eDiscovery

Advanced eDiscoveryさまざまなレベルで多数のファイルの種類をサポートしています。 サポート ファイルの種類については、この記事の次の表で説明します。 このリストは完成していません。検証テストを続行する場合は、新しいファイルの種類を追加します。 これらの表は、ファイルの種類がテキスト抽出 (および画像ファイルの光学式文字認識または OCR テキスト抽出) でサポートされるかどうかを示します。ネイティブ ビューアーで表示可能で、Advanced eDiscovery の Annotate ビューアーでもサポートされます。

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

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/mp4|はい|はい|不要|はい|不要|.f4v; .m4a; .m4v;.mp4; .mp4v;.mpeg; .mpeg4|
|audio/mpeg|はい|はい|不要|はい|不要|.mpeg|
|video/3gpp|はい|はい|不要|はい|不要|.3gp|
|video/3gpp2|はい|はい|不要|はい|不要|.3g2; .3gp2|
|video/quicktime|はい|はい|不要|はい|不要|.moov; .mov; .qt|
|video/x-m4v|はい|はい|不要|はい|不要|.m4v|
|

## <a name="database"></a>Database

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-msaccess|はい|はい|はい|不要|不要|.mdb|
|

## <a name="email"></a>電子メール

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-outlook|はい|はい|はい|はい|はい|.msg|
|message/rfc822|はい|はい|はい|はい|はい|.eml|
|text/vcard-contact|はい|はい|はい|はい|はい|.vcf|
|

## <a name="email-container"></a>メール コンテナー

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

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/xhtml+xml|はい|はい|はい|はい|はい|.xhtml|
|application/xml|はい|はい|はい|はい|はい|.xml|
|text/html|はい|はい|はい|はい|はい|.htm;.html; .shtml|
|

## <a name="image"></a>Image

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|OCR テキストの抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|image/bmp|はい|はい|はい|はい|はい|.bmp|
|image/emf|はい|はい|はい|はい|はい|.emf|
|image/gif|はい|はい|はい|はい|はい|.gif|
|image/jpeg|はい|はい|はい|はい|はい|.jpeg;.jpg|
|image/png|はい|はい|はい|はい|はい|.png|
|image/svg+xml|はい|はい|はい|はい|不要|.svg|
|image/tiff|はい|はい|はい|はい|はい|.tif|
|image/vnd.dwg|はい|はい|はい|はい|はい|.dwg; .dxf|
|image/wmf|はい|はい|はい|はい|はい|.wmf|
|

## <a name="microsoft-excel"></a>Microsoft Excel

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-excel|はい|はい|はい|はい|はい|.dat;.xls|
|application/vnd.ms-excel.sheet.binary.macroenabled.12|はい|はい|はい|はい|不要|.xlsb|
|application/vnd.ms-excel.sheet.macroenabled.12|はい|はい|はい|はい|はい|.xlsm|
|application/vnd.ms-excel.template.macroenabled.12|はい|はい|はい|不要|不要|.xltm|
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet|はい|はい|はい|はい|はい|.xlsx|
|application/vnd.openxmlformats-officedocument.spreadsheetml.template|はい|はい|はい|はい|はい|.xltx|
|

## <a name="microsoft-onenote"></a>Microsoft OneNote

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/onenote|はい|はい|はい|不要|不要|.one|
|

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-powerpoint|はい|はい|はい|はい|はい|.pot; .pps;.ppt|
|application/vnd.openxmlformats-officedocument.presentationml.presentation|はい|はい|はい|はい|はい|.pptx|
|application/vnd.openxmlformats-officedocument.presentationml.slideshow|はい|はい|はい|はい|はい|.ppsx|
|application/vnd.openxmlformats-officedocument.presentationml.template|はい|はい|はい|はい|はい|.potx|
|

## <a name="microsoft-project"></a>Microsoft Project

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-project|はい|はい|はい|不要|はい|.mpp|
|

## <a name="microsoft-publisher"></a>Microsoft Publisher

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-mspublisher|はい|はい|はい|はい|はい|.pub|
|

## <a name="microsoft-visio"></a>Microsoft Visio

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-visio.drawing|はい|はい|はい|はい|不要||
|application/vnd.visio|はい|はい|はい|はい|はい|.vsd|
|

## <a name="microsoft-word"></a>Microsoft Word

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
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

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-works-ss|はい|はい|不要|不要|不要|.wps|
|application/vnd.ms-works-wp|はい|はい|不要|不要|不要|.wps|
|

## <a name="open-document-format"></a>ドキュメント形式を開く

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.oasis.opendocument.text|はい|はい|はい|はい|はい|.odt|
|

## <a name="other"></a>その他

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/json|はい|はい|はい|はい|はい|×|
|application/octet-stream|はい|不要|不要|不要|不要|.fluid|
|application/vnd.ms-graph|はい|はい|不要|不要|不要||
|application/winhlp|はい|はい|不要|不要|不要|.hlp|
|application/x-tnef|はい|はい|不要|不要|不要||
|

## <a name="plain-text"></a>プレーン テキスト

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|text/csv|はい|はい|はい|はい|はい|.csv|
|text/plain|はい|はい|はい|はい|はい|.con; .css;.csv; .dat; .pl;.txt|
|

## <a name="portable-document-format"></a>Portable Document Format

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/pdf|はい|はい|はい|はい|はい|.pdf|
|

## <a name="word-perfect"></a>Word Perfect

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.wordperfect;version=5.0|はい|はい|はい|不要|不要|.wpd|
|application/vnd.wordperfect;version=5.1|はい|はい|はい|不要|不要|.wpd|
|application/vnd.wordperfect;version=6.x|はい|はい|はい|不要|不要|.wpd|
|

## <a name="word-pro"></a>Word Pro

<br>

****

|Mime の種類|ファイルの識別|メタデータの抽出|テキスト抽出|ネイティブ ビューアー|注釈ビューアー|可能な拡張機能|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.lotus-wordpro|はい|はい|不要|不要|不要|.lwp|
|
