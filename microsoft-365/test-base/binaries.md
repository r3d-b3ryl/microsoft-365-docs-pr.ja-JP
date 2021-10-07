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
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 200da9ca73bc666f3f11fc3fda95493d2c0954fb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180641"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>手順 3: アップロード、依存関係、およびスクリプトを削除する

このタブでは、テスト スイートの実行に使用するバイナリ、依存関係、スクリプトを含む単一の zip パッケージをアップロードします。

> [!NOTE]
> zip パッケージのサイズは、最小 10 MB から最大 2 GB の間である必要があります。

## <a name="upload-package-zip-file"></a>アップロード zip ファイル

:::image type="content" alt-text="アップロードバイナリを作成します。" source="Media/AddBinaries.png":::

  - アップロードされた依存関係には、テスト フレームワーク、スクリプト エンジン、またはアプリケーションまたはテスト ケースを実行するためにアクセスされるデータが含まれます。 たとえば、ブラウザー ベースのテストの実行に役立つ Selenium と Web ドライバー インストーラーをアップロードできます。
  - スクリプトアクティビティがモジュール形式で保持されるのがベスト プラクティスです。 
    - スクリプト `Install` はインストール操作のみを実行します。
    - スクリプト `Launch` はアプリケーションのみを起動します。
    - スクリプト `Close` はアプリケーションのみを閉じます。
    - オプションの `Uninstall` スクリプトは、アプリケーションのみをアンインストールします。

**現在、ポータルは PowerShell スクリプトのみをサポートしています。**


## <a name="next-steps"></a>次の手順 

次の記事に進み、「手順 4: テスト タスクを設定 **する」に進みます**。
> [!div class="nextstepaction"]
> [戻ってください](uploadApplication.md)
> [!div class="nextstepaction"]
> [次の手順](testtask.md)

