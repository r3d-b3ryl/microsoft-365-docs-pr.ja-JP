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
description: ドメインを Microsoft 365 に接続する方法について説明します。
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794644"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>ドメインを Microsoft 365 for business に接続する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Microsoft 365 をセットアップし、Google Workspace からメール データを移動したら、ドメインを Microsoft 365 に接続できます。 

まず、Google から既存の DNS レコードを削除する必要があります。その後、Microsoft 365 から新しい DNS レコードを追加できます。

## <a name="try-it"></a>演習

1. Google Workspace 管理コンソールにサインインします[(admin.google.com)。](https://admin.google.com)
1. Select **Domains,** **Manage domains**, **View details**, Manage **domain,** then **DNS** in the left nav.
1. 下にスクロールして **代理レコードを表示し****、Google Workspace** を開き、[削除]**を選択** して、もう一 **度削除** します。
1. カスタム リソース レコード **まで** 下にスクロールし、表示される既存の DNS レコード (以前に Microsoft 365 用に作成したレコードを含む) を削除します。
1. 
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. 左側のナビゲーションで、[すべて表示 **]、[****設定]、[** ドメイン]**の選択を行います**。
1. 次に、既定のドメインを選択します。
1. Select **Continue setup,** then, to connect your domain, choose  **Continue**.
1. 下にスクロールして、Google にコピーする必要がある DNS レコードを表示します。
1. MX **レコードを開** き、[ポイント先アドレス] または **[値] の下にある** レコードをコピーします。
1. Google に戻り、[ **カスタム** リソース レコード] セクションで、レコードの種類のドロップダウンを開き **、[MX]** を選択します。
1. [ **データ] フィールド** に、コピーしたレコードを貼り付けます。
1. 次に **[追加]** を選択します。
1. CNAME レコードと TXT レコードに対してこのプロセスを繰り返し、Google DNS 管理ページで値を追加します。
1. Microsoft 365 管理センターに戻り、[続行] を選択 **します**。

    ドメインのセットアップが完了しました。