---
title: OME ビューアー アプリの非推奨
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 メッセージ暗号化 (OME) ビューアー アプリは、2018 年に Android ストアと Apple ストアから削除されました。
ms.openlocfilehash: 2e1e0ead7d34761a3159b4b51368ea4460acb596
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630083"
---
# <a name="deprecating-message-encryption-viewer-app"></a>メッセージ暗号化ビューアー アプリの非推奨

2018 年 8 月 15 日に、Android ストアと Apple ストアから Office 365 メッセージ暗号化 (OME) ビューアー モバイル アプリが削除されました。 Office 365 メッセージ暗号化ビューアーモバイル アプリは、Apple および Android スマートフォンの以前のバージョンの OME で暗号化された電子メール メッセージと添付ファイルを読み取るために必要でした。 OME ビューアー アプリを削除する以外に、以前のバージョンの OME に他の変更は加えていません。
  
## <a name="changes-from-august-2018"></a>2018 年 8 月からの変更

2017 年 9 月に発表されたとおり、新しいバージョンの [Office 365 メッセージ暗号化](https://aka.ms/ome2017)がリリースされ、ユーザーはモバイル アプリの要件を満たさずに、組織内または外部のすべてのユーザーに暗号化された保護されたメッセージを送信できます。 その後、次の機能が追加されました。
  
- [暗号化専用テンプレート](https://aka.ms/encryptonly)

- [添付ファイルの暗号化解除を制御する](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

この変更により、ユーザーは 8 月 1 日以降、Office 365 Message Encryption Viewer モバイル アプリをダウンロードできなくなります。 その結果、メール受信者は、一部の Android および Apple モバイル デバイスで、以前のバージョンの OME で暗号化されたメッセージを読み取ることができない場合があります。 ただし、デスクトップ ブラウザーを使用して、個人用コンピューターでこれらのメッセージを読み取ることができるようになります。 アプリを既にダウンロードしたユーザーは引き続き使用できます。
  
## <a name="why-this-change-was-made"></a>この変更が行われた理由

新しいバージョンの OME では、保護された電子メール メッセージと添付ファイルを読み取るためにモバイル アプリが必要なくなりました。 Microsoft Purview Message Encryptionを使用しているお客様は、Outlook モバイルで保護されたメッセージを表示でき、非顧客は保護されたメッセージをブラウザーで表示できます。
  
ユーザーにモバイル アプリのダウンロードを要求することは、顧客が保護されたメッセージを表示するためのもう 1 つのハードルです。 Microsoft Purview Message Encryptionにより、モバイル エクスペリエンスが向上します。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>以前のバージョンの Office 365 メッセージ暗号化を引き続き使用できますか?

以前のバージョンのOffice 365 メッセージ暗号化は、現時点では非推奨になりませんが、Microsoft Purview Message Encryptionが大幅に強化されました。これにより、機密データの暗号化と権限の保護が容易になりました。これには、ユーザーが Outlook (デスクトップ、モバイル、モバイル) で保護されたメッセージを直接読み取る機能を含め、すべてのユーザーやデバイスに対して機密データを簡単に保護できるようになりました。 と web)。
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>この変更に備えるために必要な操作

組織が現在、OME ビューアー アプリを必要とする受信者に暗号化された添付ファイルを送信している場合は、ドキュメントとトレーニング リソースを更新する必要があります。
  
組織が新しい機能と改善された機能を利用できるように、Microsoft Purview Message Encryptionを使用するように既存の Exchange メール フロー ルールを更新することをお勧めします。 Microsoft Purview Message Encryptionを設定すると、受信者はモバイル デバイスで暗号化されたメッセージを読み取るために OME ビューアー アプリを必要としません。
  
組織にとって妥当な場合は、すぐにMicrosoft Purview Message Encryptionに移行する計画を立てるようお勧めします。 手順については、「[Microsoft Purview Message Encryptionのセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。 メッセージ暗号化の最初の動作の詳細については、 [メッセージ暗号化](ome.md)に関するページを参照してください。
