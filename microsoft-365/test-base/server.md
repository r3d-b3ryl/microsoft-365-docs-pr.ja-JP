---
title: Windowsサーバー アプリケーションのテスト
description: Windows サーバー アプリケーションのテストで検証する方法
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 70ad9d19fac15f7fb0b996a5afc759a0c3e69279d79bea406da9d22d314a4f56
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53798509"
---
# <a name="windows-server-application-testing"></a>Windowsサーバー アプリケーションのテスト

テスト ベースを使用Microsoft 365、Server Core を含む、Windows Server 2016および 2019 に対してアプリケーションを検証できます。

Microsoft 365 のテスト ベースの Windows Server 2016 および 2019 オペレーティング システムのプレリリース更新プログラムに対してアップロードしたアプリケーションの検証を開始するには、次の手順に従ってください。

1. セルフサービス オンボーディング ポータルにログオンします。 左側のナビゲーション メニューで、[テストの詳細] の下を選択して `Upload new package` `Package catalogue` 入力します。

2. `Security updates`OS 更新プログラムの種類として選択します。

   ![セキュリティ更新プログラムの選択](Media/selecting-security-updates.png)

3. [テストする OS のバージョン] で、該当する OS バージョンを選択します。 サーバー OS のWindowsまたはサーバーとクライアントの OS バージョンの組み合わせを選択できます。

   ![[OS バージョンの選択]](Media/selecting-OS-versions.png)

4. その他の必要な情報を提供し、提供された詳細を確認し、アプリケーション パッケージをアップロードします。 アップロード後、[パッケージの管理] メニュー タブでパッケージの状態を表示できます。

5. Windows Server 2016 および 2019 のプレリリース セキュリティ更新プログラムに対するアプリケーションの検証のテスト結果と分析情報を表示するには、[テストの概要] ページまたは [セキュリティ更新プログラムの結果] ページに移動します。

   ![テスト結果の表示](Media/access-test-results.png)

機能テストを開始する次の記事 **に進む**
> [!div class="nextstepaction"]
> [次の手順](functional.md)
