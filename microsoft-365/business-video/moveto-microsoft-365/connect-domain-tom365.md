---
title: Microsoft 365 にドメインを接続する
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
description: ドメインをドメインに接続する方法についてMicrosoft 365。
ms.openlocfilehash: d54b3bbf00dd0cf37006924e2884f2861c345d3e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191075"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Connectをビジネス向Microsoft 365に設定する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Google Workspace からメール データMicrosoft 365設定して移動したら、ドメインをユーザーに接続Microsoft 365。 

まず、Google から既存の DNS レコードを削除する必要があります。次に、新しい DNS レコードを新しい DNS レコードから追加Microsoft 365。

## <a name="try-it"></a>お試しください!

1. Google Workspace 管理コンソールにサインインするには[、admin.google.com。](https://admin.google.com)
1. [**ドメイン] 、[****ドメインの管理]**、[**詳細の** 表示] 、[**ドメインの管理**] の順に選択し、**左側のナビゲーションで DNS** を選択します。
1. 下にスクロールして **代理レコードに移動し****、Google ワークスペースを開** き、[削除 **]** を選択し、もう一 **度削除** します。
1. [カスタム リソース レコード **]** まで下にスクロールし、表示される既存の DNS レコード (以前に作成した DNS レコードを含む) を削除Microsoft 365。
1. 
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. 左側のナビゲーションで、[すべてのドメイン **を表示設定**  >    >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**します**</a>。
1. 次に、既定のドメインを選択します。
1. [セットアップ **の続行]** を選択し、ドメインを接続するには、[続行] を  **選択します**。
1. 下にスクロールして、Google にコピーする必要がある DNS レコードを表示します。
1. [MX **レコード] を開** き、[ **ポイント先アドレスまたは値] で** レコードをコピーします。
1. Google に戻り、[ユーザー設定のリソース レコード **] セクション** で、レコードの種類ドロップダウンを開き **、[MX]** を選択します。
1. [データ **] フィールド** に、コピーしたレコードを貼り付けます。
1. 次に **[追加]** を選択します。
1. CNAME レコードと TXT レコードの処理を繰り返し、Google DNS 管理ページに値を追加します。
1. [次へ] に戻Microsoft 365 管理センターし、[続行] を **選択します**。

    ドメインのセットアップが完了しました。