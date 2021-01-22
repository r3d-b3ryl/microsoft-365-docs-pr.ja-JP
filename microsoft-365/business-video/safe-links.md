---
title: 安全なリンクを管理する
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
description: 安全なリンクを管理して悪意のあるサイトからビジネスを保護する方法について学習します。
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928020"
---
# <a name="manage-safe-links"></a>安全なリンクを管理する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

microsoft Defender for Office 365 (以前の Microsoft 365 ATP または Advanced Threat Protection) は、ユーザーが Office アプリのリンクをクリックすると、悪意のあるサイトからビジネスを保護するのに役立ちます。

## <a name="try-it"></a>演習

1. 管理センターに [移動し、[](https://admin.microsoft.com)セットアップ] を **選択します**。
1. 下にスクロールして **高度な脅威からの保護を強化します**。 [表示 **]、[****管理]、ATP** の [安全なリンク **] の順に選択します**。
1. [**組織全体に適用するポリシー**] で、[既定のポリシー] を選択し、[編集] アイコン **を選択** します。
1. ブロックする URL を入力します。
1. [アプリ **で安全なリンクをOffice、iOS および Android Officeを使用する] を選択します**。[ユーザー **が安全なリンクをクリックしても追跡しない] を選択します**。[元の **URL への安全なリンクをユーザーがクリックさせない] を選択します**。 既定のポリシーを設定する場合、これらは既に選択されている可能性があります。 [**保存**] を選択します。
1. [**特定の受信者に適用** するポリシー] で、[推奨される安全なリンクルール] を選択し、[編集] アイコン **を選択** します。
1. 設定 **を** 選択し、下にスクロールして、チェックしない URL を入力して、[追加] アイコン **を選択** します。
1. Select **applied to,** and then select your domain name. ルールを適用する追加のドメインを選択します。 [追加 **]、[OK]、** および [保存] の順 **に選択します**。 

ATP の安全なリンクが構成されています。 変更が有効にな最大 30 分かかります。

ユーザーがリンク付きメールを受信すると、リンクがスキャンされます。 リンクが安全であると判断された場合は、クリック可能になります。 ただし、リンクがブロックリストにある場合、ブロックされたというメッセージがユーザーに表示されます。