---
title: ランサムウェア用のメール ルールを作成する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: ランサムウェアを防止するために電子メール ルールを作成する方法について学習します。
ms.openlocfilehash: f76d9883ef2d22803867da267f48760ec8894f99
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172745"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>ランサムウェアを防止する電子メール ルールを作成する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365は、JavaScript、バッチ、実行可能ファイルなどの潜在的に危険なファイルがランサムウェアで開かされないようにすることで、ランサムウェアからビジネスを保護するのにOutlook。 追加の種類のファイルをブロックまたは警告するルールを追加して、このレベルの保護を強化するには、次の手順を実行します。

## <a name="try-it"></a>お試しください!

1. [管理センター] で [https://admin.microsoft.com](https://admin.microsoft.com) 、[管理センター]**のExchange** を **選択します**。
1. 左側のメニューから、[メール フロー] **を選択します**。
1. [ルール] タブで、プラス記号 (+) の横にある矢印を選択し、[新しいルールの作成] **を選択します**。
1. 新しい **ルール ページで** 、ルールの名前を入力し、一番下までスクロールし、[その他のオプション] **を選択します**。
1. [ **このルールを適用する場合]** で、[任意の添付 **ファイル] を** 選択し、[ファイル拡張子 **にこれらの単語が含まれる] を選択します**。
1. [単語または語句の **指定**] ボックスに、ルールを適用するファイル拡張子 (マクロを含むファイル拡張子など) を入力します。 プラス記号 (+) を使用して、一度に 1 つ追加します。

    ファイルの種類の詳細については、「ランサムウェアから保護 [する」を参照してください](../admin/security-and-compliance/secure-your-business-data.md#ransomware)。

1. 下にスクロールしてリストを確認し **、[OK] を選択します**。
1. 新しい **ルール ページで、[** 条件の追加] **を** 選択し、[次の操作] で条件 **を選択します**。
1. 選択できるルール オプションは多数存在しますが、この例では[メッセージで受信者に通知する **] を選択します**。
1. 通知のメッセージ テキストを入力し **、[OK] を選択します**。
1. オプション: 新しい **ルール ページで**、[例外の追加] を選択し、ルールに対する例外の詳細 (信頼できる送信者からのメッセージなど) を入力します。 
1. 新しいルール ページで、[保存] **を選択** し、提供されたルールの概要情報を確認します。