---
title: Google ワークスペース ドメインを追加する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google ワークスペースからビジネス向けのMicrosoft 365にドメインを移動する方法について説明します。
ms.openlocfilehash: b41fdf304d0f0b9680f87f40a4564573593d6e75
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825668"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Google Workspace ドメインを Microsoft 365 に追加します

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

ビジネス用のメール アドレスを使用し続けられるように、Google ワークスペース ドメインをビジネス向けのMicrosoft 365に追加します。

## <a name="try-it"></a>お試しください!

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. Microsoft 365 管理センターの左側のナビゲーションで、**すべて** > 表示 **設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a> を選択します。
1. [ **ドメインの追加]** を選択し、ドメイン名を入力し、[ **このドメインを使用** する] を選択します。 
1. ドメイン **の DNS レコードに TXT レコードを追加し**、[ **続行**] を選択して TXT 値をコピーします。 
1. [Google 管理コンソール](https://admin.google.com)に戻る、**ドメイン**、**ドメインの管理**、**詳細の表示**、ドメイン、**DNS** の **管理** を選択し、**カスタム リソース レコード** まで下にスクロールします。 
1. レコードの種類ドロップダウンを開き、[ **TXT**] を選択し、コピーした TXT 値を貼り付けて、[ **追加**] を選択します。 

    更新には通常、数分以内に事実が発生しますが、最大で 48 時間かかる場合があります。 
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>に戻り、[**確認**] を選択し、[**閉じる**] を選択します。 
1. ドメインをユーザーのプライマリ 電子メールとして設定するには、左側のナビゲーションで [**UsersActive ユーザー**](https://go.microsoft.com/fwlink/p/?linkid=834822)**を** > 選択します。 
1. ユーザーを選択し、[**ユーザー名と電子メールの管理****]、[編集]** の順に選択し、ドロップダウンからドメインを選択して、[**完了]** と [**変更の保存**] を選択します。 
1. ユーザーごとにこのプロセスを繰り返します。 

    完了したら、Office アプリをインストールし、メールアイテムと予定表アイテムをMicrosoft 365に移行する準備が整います。 