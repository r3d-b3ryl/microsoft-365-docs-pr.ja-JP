---
title: 安全な添付ファイルを管理する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 安全な添付ファイルを管理する方法について学習します。
ms.openlocfilehash: 89297ec7daeca4b20c01baa9f9554d4574d9df6a
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422281"
---
# <a name="manage-safe-attachments"></a>安全な添付ファイルを管理する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

Microsoft Defender for Office 365 (以前は Microsoft 365 ATP、または Advanced Threat Protection) は、Outlook、OneDrive、SharePoint、Teams に悪意のあるコンテンツを含むファイルからビジネスを保護するのに役立ちます。

## <a name="try-it"></a>演習

1. 管理センターに移動 [し、[セットアップ](https://admin.microsoft.com)] を **選択します**。
1. 下にスクロールして **高度な脅威からの保護を強化します**。 [表示 **] 、[****管理] の順** に選択し **、[ATP の安全な添付ファイル] を選択します**。
1. 安全な添付ファイルルールを選択し、[編集] アイコン **を選択** します。
1. [ **設定]** を選択し、[ブロック] が選択されているのを確認します。
1. 下にスクロールします。 [ **リダイレクトを有効にする**] を選択し、メール アドレスまたはブロックされた添付ファイルを確認するユーザーのアドレスを入力します。
1. [ **適用] を** 選択し、ドメイン名を選択します。
1. ルールを適用する追加のドメイン (onmicrosoft.com ドメインなど) を選択します。 [追加 **] を** 選択し **、[OK] を選択します**。
1. **[保存]** を選択します。

ATP の安全な添付ファイルルールが更新されました。

これで、Outlook、OneDrive、SharePoint、または Teams から悪意のあるファイルを開くことができません。 影響を受けるファイルの横に赤いシールドが表示されます。 ブロックされたファイルを開くしようとすると、警告メッセージが表示されます。

しばらくポリシーが適用された後、[レポート] ページにアクセスして、スキャンされた情報を確認します。