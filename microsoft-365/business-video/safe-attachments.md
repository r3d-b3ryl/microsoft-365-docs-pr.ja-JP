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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 安全な添付ファイルを管理する方法について学習します。
ms.openlocfilehash: 75146a05a091cf91a77ee3bc9bb63c813d84dce3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926104"
---
# <a name="manage-safe-attachments"></a>安全な添付ファイルを管理する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

microsoft Defender for Office 365 (以前は Microsoft 365 ATP または Advanced Threat Protection と呼ばばがありました) は、Outlook、OneDrive、SharePoint、および Teams に悪意のあるコンテンツが含まれるファイルからビジネスを保護するのに役立ちます。

## <a name="try-it"></a>演習

1. 管理センターに [移動し、[](https://admin.microsoft.com)セットアップ] を **選択します**。
1. 下にスクロールして **高度な脅威からの保護を強化します**。 [表示 **]、[****管理]、ATP** の [安全な **添付ファイル] の順に選択します**。
1. 安全な添付ファイルルールを選択し、[編集] アイコン **を選択** します。
1. 設定 **を選択** し、[ブロック] が選択されているのを確認します。
1. 下にスクロールします。 Choose **Enable redirect,** and enter your email address or the address of the person you want to review the blocked attachments.
1. Select **applied to,** and then select your domain name.
1. ルールを適用する追加のドメイン (onmicrosoft.com ドメインなど) を選択します。 [追加 **] を** 選択し **、[OK] を選択します**。
1. [**保存**] を選択します。

ATP の安全添付ファイル ルールが更新されました。

これで保護が強化されたので、Outlook、OneDrive、SharePoint、または Teams から悪意のあるファイルを開くことになります。 影響を受けるファイルの横には赤い盾が表示されます。 ブロックされたファイルを開くしようとすると、警告メッセージが表示されます。

ポリシーがしばらくの間適用された後、[レポート] ページにアクセスしてスキャンされた情報を確認します。