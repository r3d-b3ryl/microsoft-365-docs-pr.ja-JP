---
title: テストをオンデマンドで実行する
description: テストをオンデマンドで実行する方法
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 08/10/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 883b142b9ddaa70ef307d307265b98baac34b4f6
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316694"
---
# <a name="run-your-test-on-demand"></a>テストをオンデマンドで実行する

> [!NOTE]
> テスト ベースでは、オンデマンド アプローチを使用してテストを開始するオプションが提供されるようになりました。

## <a name="run-as-request-under-manage-packages"></a>[パッケージの管理] で要求として実行する

アクティブなパッケージの場合は、[パッケージの管理] ページから要求時実行機能にアクセスできます。

> [!div class="mx-imgBorder"]
> [![パッケージを管理する](Media/runondemand01-managepackages.png) ](Media/runondemand01-managepackages.png#lightbox)

パッケージで事前に定義されている OS 更新プログラムの種類と Windows 製品を指定することで、Windows 更新プログラムの現在の月次チャーンに対してすぐにスケジュールされたテストをオンデマンドで開始できます。


> [!div class="mx-imgBorder"]
> [![要求](Media/runondemand02-runonrequest.png)時に実行する ](Media/runondemand02-runonrequest.png#lightbox)

この機能を使用する前に、自動ケイデンスでテストを実行する必要はありません。 これで、テストする製品とタイミングを決定できるようになりました。

> [!div class="mx-imgBorder"]
> [![Testsummary](Media/runondemand03-testsummary.png) ](Media/runondemand03-testsummary.png#lightbox)

> [!NOTE]
> [要求時に実行] ボタンが有効になっているのは、アクティブなパッケージだけです。 この機能のパッケージをオプトインする場合は、今後のテストでパッケージを有効にしてください。