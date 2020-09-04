---
title: 高度な電子情報開示でサポートされているファイルの種類
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
ms.assetid: ''
description: Microsoft 365 Advanced eDiscovery でサポートされているファイルの種類の一覧。これには、高度な電子情報開示の OCR 機能でサポートされている画像ファイルの種類が含まれます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4b23e0b0f428c91b13e461eb6514da99e5a69f42
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357748"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>高度な電子情報開示でサポートされているファイルの種類

高度な電子情報開示では、多くの種類のファイルをサポートしています。これについては、次の表で説明します。 この一覧は最終処理されていないため、検証テストを続行するときに新しいファイルの種類を追加します。 これらの表は、ファイルの種類がテキスト抽出 (および画像ファイルの OCR テキストの抽出) に対してサポートされているかどうかを示し、ネイティブビューアーで表示できます。また、Advanced eDiscovery の注釈ビューアーでもサポートしています。

## <a name="archive--container"></a>Archive/Container

| Mime の種類 | ファイルの識別 | メタデータ抽出 | コンテナーの抽出 | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |
| アプリケーション/x-7z-圧縮 | はい | はい | はい | . 7z |
| アプリケーション/x-rar 圧縮 | はい | はい | はい | rar |
| アプリケーション/x-tar | はい | はい | はい | tar |
| アプリケーション/zip | はい | はい | はい | .zip |
||||||||

## <a name="audio--video"></a>音声/ビデオ

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/mp4 | はい | はい | いいえ | はい | いいえ | . f4v;. m4a;. m4v;. mp4;. mp4v;。 mpeg4 |
| 音声/mpeg | はい | はい | いいえ | はい | いいえ | mpeg-2 |
| ビデオ/3gpp | はい | はい | いいえ | はい | いいえ | .3gp |
| video/3gpp2 | はい | はい | いいえ | はい | いいえ | . 3g2;. 3g2 |
| ビデオ/quicktime | はい | はい | いいえ | はい | いいえ | . moov、.mov、.qt |
| ビデオ/m4v | はい | はい | いいえ | はい | いいえ | .m4v |
||||||||

## <a name="database"></a>Database

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| アプリケーション/x-msaccess.exe | はい | はい | はい | いいえ | いいえ | .mdb |
||||||||

## <a name="email"></a>メール

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-outlook | はい | はい | はい | はい | はい | .msg |
| message/rfc822 | はい | はい | はい | はい | はい | .eml |
| テキスト/vcard-連絡先 | はい | はい | はい | はい | はい | .vcf |
||||||||

## <a name="email-container"></a>メールコンテナー

| Mime の種類 | ファイルの識別 | メタデータ抽出 | コンテナーの抽出 | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |
| application/mbox | はい | はい | はい | mbox |
| application/vnd. ms-outlook-pst | はい | はい | はい | .pst |
||||||||

## <a name="html"></a>HTML

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/xhtml + xml | はい | はい | はい | はい | はい | xhtml |
| application/xml | はい | はい | はい | はい | はい | .xml |
| text/html | はい | はい | はい | はい | はい | .htm、.html、. shtml.dll |
||||||||

## <a name="image"></a>イメージ

| Mime の種類 | ファイルの識別 | メタデータ抽出 | OCR テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| image/bmp | はい | はい | はい | はい | はい | .bmp |
| イメージ/emf | はい | はい | はい | はい | はい | .emf |
| image/gif | はい | はい | はい | はい | はい | .gif |
| image/jpeg | はい | はい | はい | はい | はい | .jpeg、.jpg |
| image/png | はい | はい | はい | はい | はい | .png |
| image/svg + xml | はい | はい | はい | はい | いいえ | svg |
| image/tiff | はい | はい | はい | はい | はい | .tif |
| 画像/vnd. .dwg | はい | はい | はい | はい | はい | .dwg、dxf |
| image/wmf | はい | はい | はい | はい | はい | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. が application | はい | はい | はい | はい | はい | .dat; .xls |
| アプリケーション/vnd を有効にします。12 | はい | はい | はい | はい | いいえ | .xlsb |
| アプリケーション/vnd を有効にします。12 | はい | はい | はい | はい | はい | .xlsm |
| アプリケーション/が application を有効にします。12 | はい | はい | はい | いいえ | いいえ | 。 xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | はい | はい | はい | はい | はい | .xlsx |
| application/vnd. openxmlformats-officedocument | はい | はい | はい | はい | はい | 。 xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| アプリケーション/onenote | はい | はい | はい | はい | いいえ | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. が application | はい | はい | はい | はい | はい | .pot; .pps; .ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | はい | はい | はい | はい | はい | .pptx |
| openxmlformats-officedocument (アプリケーション/vnd) | はい | はい | はい | はい | はい | . ppsx |
| openxmlformats-officedocument (アプリケーション/vnd) | はい | はい | はい | はい | はい | . potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-project | はい | はい | はい | いいえ | はい | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| アプリケーション/x-mspublisher | はい | はい | はい | はい | はい | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-visio | はい | はい | はい | はい | いいえ |  |
| アプリケーション/vnd visio | はい | はい | はい | はい | はい | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/msword | はい | はい | はい | はい | はい | .dat; .doc |
| アプリケーション/rtf | はい | はい | はい | はい | はい | .doc; .rtf |
| application/vnd.ms-word.document を有効にします。 | はい | はい | はい | はい | はい | .docm |
| アプリケーション/が application を有効にします。12 | はい | はい | はい | はい | はい | normal.dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | はい | はい | はい | はい | はい | .docx |
| application/vnd. openxmlformats-officedocument | はい | はい | はい | はい | はい | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-works-ss | はい | はい | いいえ | いいえ | いいえ | wps |
| application/vnd-wp | はい | はい | いいえ | いいえ | いいえ | wps |
||||||||

## <a name="open-document-format"></a>開いているドキュメント形式

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. oasis | はい | はい | はい | はい | はい | odt |
||||||||

## <a name="other"></a>その他

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/json | はい | はい | はい | はい | はい | × |
| application/vnd. ms-graph | はい | はい | いいえ | いいえ | いいえ |  |
| application/winhlp | はい | はい | いいえ | いいえ | いいえ | .hlp |
| アプリケーション/x-tnef | はい | はい | いいえ | いいえ | いいえ |  |
||||||||

## <a name="plain-text"></a>プレーン テキスト

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| text/csv | はい | はい | はい | はい | はい | .csv |
| text/plain | はい | はい | はい | はい | はい | .. .css; .csv;... pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/pdf | はい | はい | はい | はい | はい | .pdf |
||||||||

## <a name="word-perfect"></a>完全な単語

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd wordperfect;バージョン = 5.0 | はい | はい | はい | いいえ | いいえ | wpd |
| application/vnd wordperfect;バージョン = 5.1 | はい | はい | はい | いいえ | いいえ | wpd |
| application/vnd wordperfect;バージョン = 6. x | はい | はい | はい | いいえ | いいえ | wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Mime の種類 | ファイルの識別 | メタデータ抽出 | テキストの抽出 | ネイティブビューアー | ビューアーに注釈を付ける | 可能な拡張機能 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. lotus-wordpro | はい | はい | いいえ | いいえ | いいえ | lwp |
||||||||
