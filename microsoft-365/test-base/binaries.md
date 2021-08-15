---
title: アップロードアプリケーション バイナリ
description: M365 のテスト ベースの使用を開始する方法
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
ms.openlocfilehash: 72300374c90e0142bdbf713ffee1dba40869fff3293014e1b9884d5e148fed8e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53827580"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>手順 3: アップロード、依存関係、およびスクリプトを削除する

このタブでは、テスト スイートの実行に使用するバイナリ、依存関係、スクリプトを含む単一の zip パッケージをアップロードします。

## <a name="upload-package-zip-file"></a>アップロード zip ファイル

![アップロードバイナリの作成](Media/AddBinaries.png)

  - アップロードされた依存関係には、テスト フレームワーク、スクリプト エンジン、またはアプリケーションまたはテスト ケースを実行するためにアクセスされるデータが含まれます。 たとえば、ブラウザー ベースのテストの実行に役立つ Selenium インストーラーと Webdriver インストーラーをアップロードできます。
  - スクリプトアクティビティがモジュール形式で保持されるのがベスト プラクティスです。 
    - スクリプト ```Install``` はインストール操作のみを実行します。
    - スクリプト ```Launch``` はアプリケーションのみを起動します。
    - スクリプト ```Close``` はアプリケーションのみを閉じます。
    - オプションの ```Uninstall``` スクリプトは、アプリケーションのみをアンインストールします。

**現在、ポータルは PowerShell スクリプトのみをサポートしています。**


## <a name="next-steps"></a>次の手順 

次の記事に進み、「手順 4: テスト タスクを設定 **する」に進みます**。
> [!div class="nextstepaction"]
> [戻ってください](uploadApplication.md)
> [!div class="nextstepaction"]
> [次の手順](testtask.md)

