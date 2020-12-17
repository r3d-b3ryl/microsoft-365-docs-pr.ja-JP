---
title: ドメインの追加
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: サブスクリプションに別のドメインを追加する方法について学習します。
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702790"
---
# <a name="add-another-domain"></a>別のドメインを追加する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

会社で異なる目的のために複数のドメイン名が必要になる場合があります。 たとえば、顧客が既に会社名を使用し、連絡に失敗した場合に、別のスペルを追加できます。

## <a name="try-it"></a>演習

1. Microsoft 365 管理センターで、[セットアップ] を選択 **します**。
1. [ **カスタム ドメインのセットアップを取得する] で、[表示**] を **選択します**。
1. Choose **Manage,** and then **Add domain**.
1. 追加する新しいドメイン名を入力し、[次へ] を選択 **します**。
1. ドメイン レジストラー (この場合は GoDaddy) にサインインし、[次へ] を選択 **します**。
1. ダイアログが表示されたら、レジストラーにサインインし、[承認] を選択 **します**。
1. Choose **Add the DNS records for me,** and then select **Next**.
1. 新しいドメインのサービスを選択し、別のドメインによって処理されるサービスのチェック ボックスをオフにします。 たとえば、電子メールに新しいドメインを使用するだけの場合は **、[Exchange]** を選択し **、Skype for Business** およびモバイル デバイス管理 (Office **365** 用) のチェック ボックスをオフにします。
1. [**次へ] を** 選択し **、[承認]、[****次へ**]、および [完了] の順に **選択します**。 新しいドメインが追加されました。

新しいドメインでメールを受信するには、ユーザーごとに新しいメール エイリアスを追加する必要があります。

1. [ **ユーザー]**、[ **アクティブなユーザー**] の順に選択し、新しいエイリアスを割り当てるユーザーを選択します。
1. Choose **Manage email aliases,** and then **Add an alias**.
1. ユーザー名を入力し、ドロップダウン リストから新しいドメインを選択します。
1. [変更 **の保存] を** 選択し、ウィンドウを閉じます。
1. 新しいドメインでメールを受信する必要があるユーザーごとに、これらの手順を繰り返します。