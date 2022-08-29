---
title: Windows Server アプリケーションのテスト
description: Windows サーバー アプリケーションのテストを使用して検証する方法
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 5d111b680105628ab1351a2cc45eeba01c41aa68
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316010"
---
# <a name="windows-server-application-testing"></a>Windows Server アプリケーション テスト

Microsoft 365 の Test Base を使用すると、Server Core を含むWindows Server 2016と 2019 に対してアプリケーションを検証できるようになりました。

Test Base for Microsoft 365 のWindows Server 2016および 2019 オペレーティング システムのプレリリース更新プログラムに対してアップロードされたアプリケーションの検証を開始するには、次の手順に従ってください。

1. セルフサービスオンボード ポータルにログオンします。 左側のナビゲーション メニューで、テストの詳細の下を`Package catalogue`選択`Upload new package`して入力します。

2. OS 更新プログラムの種類として選択 `Security updates` します。

   ![セキュリティ更新プログラムを選択します。](Media/selecting-security-updates.png)

3. テストする OS バージョンで、該当する OS バージョンを選択します。 Windows Server OS のバージョンまたはサーバーとクライアントの OS バージョンの組み合わせを選択できます。

   ![OS バージョンを選択します。](Media/selecting-OS-versions.png)

4. その他の必要な情報を入力し、提供された詳細を確認し、アプリケーション パッケージをアップロードします。 アップロード後、[パッケージの管理] メニュー タブでパッケージの状態を表示できます。

5. Windows Server 2016および 2019 のプレリリース セキュリティ更新プログラムに対するアプリケーションの検証からテスト結果と分析情報を表示するには、テストの概要ページまたはセキュリティ更新プログラムの結果ページに移動します。

   ![テスト結果を表示します。](Media/access-test-results.png)

次の記事に進み、 **機能テストを開始する**
> [!div class="nextstepaction"]
> [次のステップ](functional.md)
