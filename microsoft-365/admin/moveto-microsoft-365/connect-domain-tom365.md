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
description: ドメインをMicrosoft 365に接続する方法について説明します。
ms.openlocfilehash: d54b3bbf00dd0cf37006924e2884f2861c345d3e
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825657"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>ドメインをビジネス向けのMicrosoft 365にConnectする

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Microsoft 365を設定し、Google ワークスペースからメール データを移動したら、ドメインをMicrosoft 365に接続できます。 

まず、Google から既存の DNS レコードを削除する必要があります。次に、Microsoft 365から新しい DNS レコードを追加できます。

## <a name="try-it"></a>お試しください!

1. [admin.google.com](https://admin.google.com) で Google ワークスペース管理コンソールにサインインします。
1. 左側のナビゲーションで[ **ドメイン]**、[ **ドメインの管理**]、[ **詳細の表示]**、[ **ドメインの管理**]、[ **DNS** ] の順に選択します。
1. **合成レコード** まで下にスクロールし、**Google ワークスペース** を開き、[**削除**]、[**削除**] の順に再度選択します。
1. **[カスタム リソース レコード**] まで下にスクロールし、表示された既存の DNS レコード (Microsoft 365用に以前に作成した可能性のあるものも含む) を削除します。
1. [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. 左側のナビゲーションで、[**すべて** > 表示 **設定** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Domains**</a>] を選択します。
1. 次に、既定のドメインを選択します。
1. [ **セットアップの続行**] を選択し、ドメインに接続するには、[続行] を選択  **します**。
1. 下にスクロールして、Google にコピーする必要がある DNS レコードを表示します。
1. **MX レコード** を開き、[**アドレスまたは値のポイント**] でレコードをコピーします。
1. Google に戻り、[ **カスタム リソース レコード** ] セクションでレコードの種類ドロップダウンを開き、[ **MX**] を選択します。
1. [ **データ** ] フィールドに、コピーしたレコードを貼り付けます。
1. 次に **[追加]** を選択します。
1. CNAME レコードと TXT レコードのプロセスを繰り返し、Google DNS 管理ページで値を追加します。
1. Microsoft 365 管理センターに戻り、[続行] を選択 **します**。

    ドメインのセットアップは完了です。