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
description: 365 Office (OME) ビューアー アプリは、2018 年に Android ストアと Apple ストアから削除されました。
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741524"
---
# <a name="deprecating-message-encryption-viewer-app"></a>メッセージ暗号化ビューアー アプリの非推奨

2018 年 8 月 15 日、Android ストアと Apple ストアから Office 365 Message Encryption (OME) ビューアー モバイル アプリが削除されました。 Apple Office Android 携帯電話で以前のバージョンの OME で暗号化された電子メール メッセージと添付ファイルを読み取るには、365 Message Encryption Viewer モバイル アプリが必要でした。 OME ビューアー アプリを削除する以外に、以前のバージョンの OME に他の変更を加える必要があります。
  
## <a name="changes-from-august-2018"></a>2018 年 8 月からの変更点

2017 年 9 月に発表された新しいバージョン [の Office 365 Message Encryption](https://aka.ms/ome2017) がリリースされ、ユーザーはモバイル アプリの要件を満たさずに組織の内部または外部の誰にでも暗号化および保護されたメッセージを送信できます。 それ以来、次の機能が追加されました。
  
- [暗号化専用テンプレート](https://aka.ms/encryptonly)

- [添付ファイルの復号化を制御する](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

この変更により、ユーザーは 8 月 1 日から Office 365 Message Encryption Viewer モバイル アプリをダウンロードできなくなりました。 その結果、一部の Android および Apple モバイル デバイスでは、メール受信者が以前のバージョンの OME で暗号化されたメッセージを読み取れない場合があります。 ただし、これらのメッセージは、(デスクトップ ブラウザーを介して) 個人のコンピューターで読み取る可能性があります。 アプリを既にダウンロードしているユーザーは、引き続きアプリを使用できます。
  
## <a name="why-this-change-was-made"></a>この変更が行われた理由

OME の新しいバージョンでは、保護された電子メール メッセージと添付ファイルを読み取るためにモバイル アプリが必要なくなりました。 新しい OME 機能を使用しているお客様は、Outlook モバイルで保護されたメッセージを表示し、非顧客はブラウザーで保護されたメッセージを表示できます。
  
ユーザーにモバイル アプリのダウンロードを要求する場合は、保護されたメッセージを表示するためのもう 1 つのハードルです。 365 Officeの新しい機能により、モバイル エクスペリエンスが向上します。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>365 Message Encryption の以前のバージョンOffice使用できる

Office 365 Message Encryption の以前のバージョンは、現時点では廃止されませんが、新しいバージョンの Office 365 Message Encryption が大幅に強化され、機密データの暗号化と権限の保護が容易になり、ユーザーが Outlook (デスクトップ、モバイル) で保護されたメッセージを直接読み取る機能を含め、すべてのデバイスで機密データを簡単に保護できます。、および Web)。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>この変更の準備に必要な操作

組織が現在、OME ビューアー アプリを必要とする受信者に暗号化された添付ファイルを送信している場合は、ドキュメントとトレーニング リソースを更新する必要があります。
  
組織が新しい機能と改善された機能を利用できるよう、既存の Exchange メール フロー ルールを更新して、現在のバージョンの OME を使用することをお勧めします。 新しい OME 機能を設定すると、受信者はモバイル デバイスで暗号化されたメッセージを読み取る OME ビューアー アプリを必要としません。
  
Microsoft では、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。 手順については [、「Set up new Office 365 Message Encryption capabilitis」を参照してください](set-up-new-message-encryption-capabilities.md)。 新しい機能が最初に機能する方法の詳細については [、「365 Message Encryption](ome.md)」を参照Office参照してください。
  

