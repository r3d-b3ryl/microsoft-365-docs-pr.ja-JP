---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
ms.custom: admindeeplinkDEFENDER
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 Defender ポータルl と Microsoft Purview コンプライアンス ポータルは、組織の現在の設定に基づいてデータ ガバナンスのための推奨事項を提供し、何回かクリックするだけで設定することができます。 これらの推奨事項の一部は、組織内の特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。 たとえば、推奨事項によって業務上重要なコンテンツ (弁護士/依頼人特権や NDA 情報など) が含まれる項目が検出されると、これらの項目に保持ラベルが自動的に適用され、必要に応じて分類および保持されます。 このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。
ms.openlocfilehash: 27fcc5dd07695be355fc15ba2145ffa5540673ca
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637309"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>データ ガバナンスの推奨事項のためのコンテンツの識別方法

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>と <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>は、組織の現在の設定に基づいてデータ ガバナンスのための推奨事項を提供し、何回かクリックするだけで設定することができます。 これらの推奨事項の一部は、組織内の特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。 たとえば、推奨事項によって業務上重要なコンテンツ (弁護士/依頼人特権や NDA 情報など) が含まれる項目が検出されると、これらの項目に保持ラベルが自動的に適用され、必要に応じて分類および保持されます。

このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。

## <a name="clean-up-voicemail"></a>ボイスメールのクリーンアップ

この推奨事項は、メッセージの種類が "ボイスメール" と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange)」を参照してください。

## <a name="label-attorney-client-privilege-content"></a>弁護士/依頼人特権関連コンテンツのラベル付け

この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。

- メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。
  - ACP
  - 弁護士依頼人特権
  - 弁護士/依頼人特権
  - 弁護士/依頼人特権がある

- SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます
  - ACP
  - 弁護士依頼人特権*
  - AC 特権

## <a name="retain-audio-files"></a>オーディオ ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>CAD ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>画像ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>NDA 関連コンテンツの保持

この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。

- メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。
  - NDA
  - "秘密保持契約"
  - "秘密保持契約"

- SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。
  - NDA
  - “秘密保持契約”

## <a name="retain-software-development-files"></a>ソフトウェア開発ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>ビデオ ファイルの保持

この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
