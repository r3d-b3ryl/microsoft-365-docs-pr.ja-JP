---
title: パッケージをアップロードする
description: アプリケーション、バイナリ、依存関係をテスト ベースにアップロードする方法
search.appverid: MET150
author: mansipatel-usl
ms.author: rshastri
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9ee299c0972ed4e286e5a660f5082dd5632167e4
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64934271"
---
# <a name="upload-your-test-base-package-zip"></a>テスト ベース パッケージをアップロードする (Zip) 

[テスト ベース ポータル] ページで、次に示すように、左側のナビゲーション バーの **アップロード新しいパッケージ** オプションに移動します。

:::image type="content" alt-text="新しいパッケージをアップロードします。" source="Media/Upload-New-Package.png" lightbox="Media/Upload-New-Package.png":::

次の手順に従って、新しいパッケージをアップロードします。

## <a name="enter-details-for-your-package"></a>パッケージの詳細を入力する

[テストの詳細] タブで、要求されたパッケージの名前、バージョン、その他の詳細を入力します。

**この** ダッシュボードを使用して、すぐに使用できる **機能テストと機能テストを** 実行できます。

次の手順では、パッケージの詳細を入力する方法に関するガイドを示します。

1. フィールドにパッケージを指定する名前を `Package name` 入力します。

    > [!NOTE]
    > 入力するパッケージ名とバージョンの組み合わせは、組織内で一意である必要があります。 これは、次に示すようにチェックマークによって検証されます。

    - パッケージの名前を再利用する場合、バージョン番号は一意である必要があります (つまり、その特定の名前を含むパッケージでは使用されていません)。

    - パッケージ名とバージョンの組み合わせが一意性チェックに合格しない場合は、「 *このパッケージ バージョンのパッケージが既に存在する」という* エラー メッセージが表示されます。

    :::image type="content" alt-text="パッケージの手順をアップロードするための画像。" source="Media/Instructions.png":::

2. [パッケージ バージョン] フィールドにバージョンを入力します。

    :::image type="content" alt-text="パッケージ のバージョン。" source="Media/ApplicationVersion.png":::

3. このパッケージで実行するテストの種類を選択します。

    **Out-Of-Box (OOB)** テストは、パッケージの *インストール*、*起動*、*閉じ*、*アンインストール* を実行します。 インストール後、1 回のアンインストールが実行される前に、起動終了ルーチンが 30 回繰り返されます。

    この OOB テストでは、パッケージで標準化されたテレメトリを提供し、Windows ビルド間で比較できます。

    **機能テスト** では、アップロードしたテスト スクリプトがパッケージに対して実行されます。 スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止されます。

    > [!NOTE]
    > **すべての** スクリプトは、最大で 80 分間実行されます。

4. OS 更新プログラムの種類を選択します。

    - "セキュリティ更新プログラム" を使用すると、パッケージをWindowsリリース前の毎月のセキュリティ更新プログラムの増分チャーンに対してテストできます。
    - "機能更新プログラム" を使用すると、Windows Insider Program からリリース前の 2 年間の機能更新プログラムビルドWindowsパッケージをテストできます。
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="OS 更新プログラムの種類。" source="Media/OSUpdateType.png":::

5. セキュリティ更新プログラムテストの OS バージョンを選択します。

    複数選択ドロップダウンで、パッケージがインストールされるWindowsの OS バージョンを選択します。

    - Windowsクライアント オペレーティング システムに対してのみパッケージをテストするには、メニュー一覧から該当するクライアント OS のバージョンWindows選択します。
    - Windows Server オペレーティング システムに対してのみパッケージをテストするには、メニュー一覧から該当するWindowsサーバー OS のバージョンを選択します。
    - Windowsクライアントオペレーティング システムとWindows サーバー オペレーティング システムに対してパッケージをテストするには、メニュー 一覧から該当するすべてのオペレーティング システムを選択します。

    > [!NOTE]
    > サーバーとクライアントの両方の OS に対してパッケージをテストすることを選択した場合は、パッケージが互換性があり、両方の OS で実行できることを確認してください

    :::image type="content" alt-text="OS バージョンを選択する。" source="Media/OSVersion.png":::
    <!---
    Change to the correct picture
    -->

6. 機能更新テストのオプションを選択します。

    - [Insider Channel の選択] オプションで、パッケージを `Windows Insider Program Channel` テストするビルドとして選択します。

      現在、Insider Beta Channel でフライティングされたビルドを使用しています。

    - [Insight の OS ベースラインの選択] オプションで、テスト結果を比較する際にベースラインとして使用する os バージョンWindowsを選択します。

    > [!NOTE]
    > 現時点では、サーバー OS の機能更新テストはサポートされていません
    <!---
    Note to actual note format for markdown
    -->
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="機能更新プログラムのテスト。" source="Media/FeatureUpdate.png":::

7. 完了したテストの詳細ページは次のようになります。

    :::image type="content" alt-text="テストの詳細を表示します。" source="Media/TestDetails.png":::

## <a name="next-steps"></a>次の手順

次の記事では、バイナリをサービスにアップロードする方法について説明します。

> [!div class="nextstepaction"]
> [次の手順](binaries.md)

<!---
Add button for next page
-->
