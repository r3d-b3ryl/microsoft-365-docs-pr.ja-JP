---
title: '[リンクセーフ管理]'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 悪意のあるサイトからビジネスセーフリンクを管理する方法について学習します。
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580632"
---
# <a name="manage-safe-links"></a>[リンクセーフ管理]

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender for Office 365 (以前は Microsoft 365 ATP、または Advanced Threat Protection) は、ユーザーが Office アプリのリンクをクリックすると、悪意のあるサイトからビジネスを保護するのに役立ちます。

## <a name="try-it"></a>お試しください!

1. 管理センターに移動 [し、[セットアップ](https://admin.microsoft.com)] を **選択します**。
1. 下にスクロールして **高度な脅威からの保護を強化します**。 [表示 **] 、[****管理]** の順に選択し **、[ATP セーフリンク] を選択します**。
1. [ **組織全体に適用されるポリシー] で**、[既定のポリシー] **を** 選択し、[編集] アイコン **を選択** します。
1. ブロックする URL を入力します。
1. [**アプリで安全なリンクをOfficeする] を選択Office iOS と Android の場合は[安全なリンクを使用する] を選択します**。[ユーザー **が安全なリンクをクリックしても追跡しない] を選択します**。をクリック **し、[ユーザーが元の URL への安全なリンクをクリックさせない] を選択します**。 既定のポリシーを設定した場合、これらは既に選択されている可能性があります。 **[保存]** を選択します。
1. [ **特定の受信者に適用されるポリシー]** で、[推奨される安全なリンクルール] を **選択** し、[編集] アイコン **を選択** します。
1. [ **設定]** を選択し、下にスクロールして、チェックしない URL を入力し、[追加] アイコン **を選択** します。
1. [ **適用] を** 選択し、ドメイン名を選択します。 ルールを適用する追加のドメインを選択します。 [ **追加]** **、[OK] の順** に選択し、[保存] **を選択します**。

ATP セーフリンクが構成されています。 変更を有効にするには、最大 30 分かかります。

ユーザーがリンク付きメールを受信すると、リンクがスキャンされます。 リンクが安全であると判断された場合は、クリック可能です。 ただし、リンクがブロックリストにある場合、ユーザーにはブロックされたというメッセージが表示されます。