---
title: メッセージ暗号化ビューアー アプリの非推奨
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 2018 Office 365 Message Encryption (OME) ビューアー アプリは、Android ストアと Apple ストアから削除されました。
ms.openlocfilehash: dc12eaa783c43fb80fb8ecbe984ecbcd0cda315f33b2cd1d3bc65e8932d77bda
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53892089"
---
# <a name="deprecating-message-encryption-viewer-app"></a>メッセージ暗号化ビューアー アプリの非推奨

2018 年 8 月 15 日、Android ストアと Apple ストアから Office 365 Message Encryption (OME) ビューアー モバイル アプリを削除しました。 Apple Office 365 Message Encryption Viewer Android の携帯電話で以前のバージョンの OME で暗号化された電子メール メッセージと添付ファイルを読み取る際には、モバイル アプリが必要でした。 OME ビューアー アプリを削除する以外に、以前のバージョンの OME に他の変更を加える必要があります。
  
## <a name="changes-from-august-2018"></a>2018 年 8 月からの変更点

2017 年[9](https://aka.ms/ome2017)月に発表された新しいバージョンの Office 365 Message Encryption がリリースされ、ユーザーはモバイル アプリの要件を満たさずに組織の内部または外部のユーザーに暗号化されたメッセージと保護されたメッセージを送信できます。 それ以来、次の機能が追加されました。
  
- [暗号化専用テンプレート](https://aka.ms/encryptonly)

- [添付ファイルの復号化を制御する](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

この変更により、ユーザーは 8 月 1 日からモバイル Office 365 Message Encryption Viewerをダウンロードできなくなりました。 その結果、一部の Android および Apple モバイル デバイスでは、メール受信者が以前のバージョンの OME で暗号化されたメッセージを読み取れない場合があります。 ただし、これらのメッセージは、(デスクトップ ブラウザーを介して) 個人のコンピューターで読み取る可能性があります。 アプリを既にダウンロードしているユーザーは、引き続きアプリを使用できます。
  
## <a name="why-this-change-was-made"></a>この変更が行われた理由

OME の新しいバージョンでは、保護された電子メール メッセージと添付ファイルを読み取るためにモバイル アプリが必要なくなりました。 新しい OME 機能を使用しているお客様は、モバイルで保護されたメッセージOutlook、お客様以外のユーザーはブラウザーで保護されたメッセージを表示できます。
  
ユーザーにモバイル アプリのダウンロードを要求する場合は、保護されたメッセージを表示するためのもう 1 つのハードルです。 新しいOffice 365 Message Encryption機能は、より優れたモバイル エクスペリエンスを提供します。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>以前のバージョンのファイルを引き続き使用Office 365 Message Encryption

Office 365 Message Encryption の以前のバージョンは現時点では廃止されませんが、新しいバージョンの Office 365 Message Encryption は大幅に強化されました。これにより、ユーザーが Outlook (デスクトップ、モバイル、および Web) で保護されたメッセージを直接読み取る機能を含め、機密データを暗号化し、権利を簡単に保護できます。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>この変更の準備に必要な操作

組織が現在、OME ビューアー アプリを必要とする受信者に暗号化された添付ファイルを送信している場合は、ドキュメントとトレーニング リソースを更新する必要があります。
  
既存のメール フロー ルールExchange更新して、現在のバージョンの OME を使用して、組織が新しい機能と改善された機能を利用できるようお勧めします。 新しい OME 機能を設定すると、受信者はモバイル デバイスで暗号化されたメッセージを読み取る OME ビューアー アプリを必要としません。
  
Microsoft では、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。 手順については、「新しい機能を[セットアップする」をOffice 365 Message Encryptionしてください](set-up-new-message-encryption-capabilities.md)。 新しい機能の最初の動作の詳細については、「Office 365 Message Encryption」[を参照してください](ome.md)。
  

