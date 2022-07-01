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
description: ドメインを Google ワークスペースから Microsoft 365 for Business に移行する方法について説明します。
ms.openlocfilehash: 06129811ea1d97b0ffb770843c58373427228559
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601138"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Google Workspace ドメインを Microsoft 365 に追加します

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

## <a name="watch-add-google-workspace-domain"></a>ウォッチ: Google ワークスペース ドメインを追加する

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198105)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

ビジネス用のメール アドレスを使用し続けられるように、ビジネス向け Microsoft 365 に Google ワークスペース ドメインを追加します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. Microsoft 365 管理センターの左側のナビゲーションで、[**すべての** > 設定 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**ドメイン**</a>を表示 **]** >  を選択します。
1. [ **ドメインの追加]** を選択し、ドメイン名を入力し、[ **このドメインを使用** する] を選択します。 
1. ドメイン **の DNS レコードに TXT レコードを追加し**、[ **続行**] を選択して TXT 値をコピーします。 
1. [Google 管理 コンソール](https://admin.google.com)に戻る、**ドメイン**、**ドメインの管理**、**詳細の表示**、**ドメインの管理**、**DNS** の順に選択し、**カスタム リソース レコード** まで下にスクロールします。 
1. レコードの種類ドロップダウンを開き、[ **TXT**] を選択し、コピーした TXT 値を貼り付けて、[ **追加**] を選択します。 

    更新には通常、数分以内に事実が発生しますが、最大で 48 時間かかる場合があります。 
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>に戻り、[**確認**] を選択し、[**閉じる**] を選択します。 
1. ドメインをユーザーのプライマリ 電子メールとして設定するには、左側のナビゲーションで [ **ユーザー** > [**アクティブ ユーザー**](https://go.microsoft.com/fwlink/p/?linkid=834822)] を選択します。 
1. ユーザーを選択し、[**ユーザー名と電子メールの管理****]、[編集]** の順に選択し、ドロップダウンからドメインを選択して、[**完了]** と [**変更の保存**] を選択します。 
1. ユーザーごとにこのプロセスを繰り返します。 

    完了したら、Office アプリをインストールし、メールアイテムと予定表アイテムを Microsoft 365 に移行する準備が整います。 