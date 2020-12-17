---
title: ランサムウェアの電子メール ルールを作成する
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
description: ランサムウェアを防止するメール ルールを作成する方法について学習します。
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702450"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>ランサムウェアを防止するメール ルールを作成する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 は、JavaScript、バッチ、実行可能ファイルなどの潜在的な危険なファイルが Outlook で開かされないようにすることで、ランサムウェアからビジネスを保護します。 他の種類のファイルをブロックまたは警告するルールを追加して、このレベルの保護を強化するには、次の手順を実行します。

## <a name="try-it"></a>演習

1. From the admin center [https://admin.microsoft.com](https://admin.microsoft.com) at, choose **Exchange** under **Admin centers**.
1. 左側のメニューから、[メール フロー] **を選択します**。
1. [ルール] タブで、プラス記号 (+) の横にある矢印を選択し、[新しいルールの作成] **を選択します**。
1. 新しい **ルール ページで** 、ルールの名前を入力し、一番下までスクロールして、[その他のオプション] **を選択します**。
1. [ **このルールを適用する条件] で**[任意の添付ファイル] **を** 選択し、ファイル拡張子 **に次の単語が含まれる場合に選択します**。
1. [単語 **または語句の** 指定] ボックスに、ルールを適用するファイル拡張子 (マクロを含むファイル拡張子など) を入力します。 プラス記号 (+) を使用して、一度に 1 つ追加します。

    ランサムウェアからの保護に関する記事を参照して、ファイル [の種類の詳細を確認します](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)。

1. 下にスクロールしてリストを確認し **、[OK] を選択します**。
1. On the **new rule** page, choose **add condition,** and then choose a condition under **Do the following**.
1. You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.
1. 通知のメッセージ テキストを入力し **、[OK]** を選択します。
1. オプション: 新しいルール **ページ** で、[例外の追加] を選択し、ルールに対する例外の詳細 (信頼できる送信者からのメッセージなど) を入力します。
1. 新しいルール ページで、[保存] **を選択** し、提供されたルールの概要情報を確認します。