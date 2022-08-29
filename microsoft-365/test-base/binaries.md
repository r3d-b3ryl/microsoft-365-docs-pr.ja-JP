---
title: アプリケーション バイナリをアップロードする
description: Microsoft 365 の Test Base の使用を開始する方法
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
ms.openlocfilehash: fdb5bfed0eb103be68e1a8967dc97f9fbe64683e
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316405"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>手順 3: バイナリ、依存関係、およびスクリプトをアップロードする

このタブでは、テスト スイートの実行に使用されるバイナリ、依存関係、スクリプトを含む 1 つの zip パッケージをアップロードします。

> [!NOTE]
> zip パッケージのサイズは、最小 10 MB から最大 2 GB の間にする必要があります。

## <a name="upload-package-zip-file"></a>パッケージ zip ファイルをアップロードする

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
> [次のステップ](testtask.md)

