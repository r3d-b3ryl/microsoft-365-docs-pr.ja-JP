---
title: アップロード アプリケーション バイナリ
description: M365 の Test Base の使用を開始する方法
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
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>手順 3: バイナリ、依存関係、スクリプトをアップロードする

このタブでは、テスト スイートの実行に使用されるバイナリ、依存関係、スクリプトを含む 1 つの zip パッケージをアップロードします。

> [!NOTE]
> zip パッケージのサイズは、最小 10 MB から最大 2 GB の間にする必要があります。

## <a name="upload-package-zip-file"></a>アップロード パッケージ zip ファイル

:::image type="content" alt-text="バイナリをアップロードします。" source="Media/AddBinaries.png":::

  - アップロードされた依存関係には、アプリケーションまたはテスト ケースを実行するためにアクセスされるテスト フレームワーク、スクリプト エンジン、またはデータを含めることができます。 たとえば、Selenium と Web ドライバー インストーラーをアップロードして、ブラウザー ベースのテストを実行できます。
  - スクリプト アクティビティがモジュール化された状態に保たれるようにすることをお勧めします。 
    - このスクリプトでは `Install` 、インストール操作のみが実行されます。
    - このスクリプトでは `Launch` 、アプリケーションのみが起動されます。
    - スクリプトは `Close` アプリケーションのみを閉じます。
    - 省略可能な `Uninstall` スクリプトでは、アプリケーションのみがアンインストールされます。

**現時点では、ポータルでは PowerShell スクリプトのみがサポートされています。**


## <a name="next-steps"></a>次の手順 

次の記事に進み、手順 4: **テスト タスクを設定する** に進みます。
> [!div class="nextstepaction"]
> [戻る](uploadApplication.md)
> [!div class="nextstepaction"]
> [次の手順](testtask.md)

