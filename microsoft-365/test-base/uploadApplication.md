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
ms.openlocfilehash: 23c21eae9ad149aea5442c0c8a00f716f3d22506
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099479"
---
# <a name="upload-your-test-base-package-zip"></a>テスト ベース パッケージをアップロードする (Zip) 

Test Base ポータル ページで、左側のナビゲーション バーの **[新しいパッケージ** ] オプションに移動し、[ **レガシ アップロード エクスペリエンス** ] をクリックして、次に示すように Zip アップロード エクスペリエンスを有効にします。

:::image type="content" alt-text="新しいパッケージをアップロードします。" source="Media/testapplication01.png" lightbox="Media/testapplication01.png":::

:::image type="content" alt-text="操作を適用します。" source="Media/testapplication21.png" lightbox="Media/testapplication21.png":::

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



## <a name="upload-your-binaries-dependencies-and-scripts"></a>バイナリ、依存関係、スクリプトをアップロードする

このタブでは、テスト スイートの実行に使用されるバイナリ、依存関係、スクリプトを含む 1 つの zip パッケージをアップロードします。

> [!NOTE]
> zip パッケージのサイズは、最小 10 MB から最大 2 GB の間にする必要があります。

**アップロード パッケージ zip ファイル**

:::image type="content" alt-text="バイナリをアップロードします。" source="Media/AddBinaries.png":::

  - アップロードされた依存関係には、アプリケーションまたはテスト ケースを実行するためにアクセスされるテスト フレームワーク、スクリプト エンジン、またはデータを含めることができます。 たとえば、Selenium と Web ドライバー インストーラーをアップロードして、ブラウザー ベースのテストを実行できます。
  - スクリプト アクティビティがモジュール化された状態に保たれるようにすることをお勧めします。 
    - このスクリプトでは `Install` 、インストール操作のみが実行されます。
    - このスクリプトでは `Launch` 、アプリケーションのみが起動されます。
    - スクリプトは `Close` アプリケーションのみを閉じます。
    - 省略可能な `Uninstall` スクリプトでは、アプリケーションのみがアンインストールされます。

**現時点では、ポータルでは PowerShell スクリプトのみがサポートされています。**



## <a name="the-tasks-tab"></a>[タスク] タブ

[タスク] タブでは、バイナリ タブの下にアップロードした zip フォルダーにあるテスト スクリプトへのパスを指定する必要があります。

  - **既定のテスト スクリプト:** インストール、起動、閉じる、およびアンインストールするスクリプトの相対パスを入力します。 また、インストール スクリプトの追加設定を選択することもできます。
  - **機能テスト スクリプト:** アップロードされた各機能テスト スクリプトへの相対パスを入力します。 ボタンを使用して、追加の機能テスト スクリプトを ```Add Script``` 追加できます。 少なくとも 1 つの (1) スクリプトが必要であり、最大 8 個の機能テスト スクリプトを追加できます。 
  
    スクリプトは、一覧に示されている順序で実行されます。 特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止されます。
    また、指定されたスクリプトごとに追加の設定を選択することもできます。

**スクリプト パスを設定する**

:::image type="content" alt-text="テスト タスクの画像。" source="Media/testtask.png":::

フォルダー構造の相対パスを指定する方法の例を次に示します。

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** が必要です。 相対パスとして _ScriptX.ps1_。
  - **Script.ps1** は、相対パスとして _folder1/script.ps1_ を持つことになります。



## <a name="choose-your-test-options"></a>テスト オプションを選択します。 

この```Test Options```タブは、機能テスト スクリプトを実行する順序でWindows Updateパッチを適用するタイミングを示す機能テストを実行するユーザー向けです。

:::image type="content" alt-text="テスト オプションの画像。既定または機能テスト。" source="Media/testoptions.png":::

[ _**確認**_ ] を選択して次のタブに移動し、選択したテスト オプションを確認します。



## <a name="review-your-selections-to-create-your-package"></a>選択内容を確認してパッケージを作成します。

1. このタブでは、サービスによってテストの詳細が表示され、クイックコンプリート チェックが実行されます。

    **渡された検証** または **検証に失敗した** メッセージは、次の手順に進めるかどうかを示します。

2. テストの詳細を確認し、問題が発生した場合は、[ **作成** ] ボタンをクリックします。

    :::image type="content" alt-text="検証を表示します。" source="Media/validation.png" lightbox="Media/validation.png":::

3. これにより、パッケージがテスト ベース環境にオンボードされます。 パッケージが正常に作成されると、Azure でパッケージを正常に実行できるかどうかを検証する自動テストがトリガーされます。

    :::image type="content" alt-text="成功した結果。" source="Media/successful.png":::

    > [!NOTE]
    > Azure portalから、パッケージの検証の成功または失敗を通知する通知が表示されます。
    >
    > プロセスには最大 24 時間かかる可能性があるため、アクティブでない場合は Web ページがタイムアウトする可能性があるため、このオンデマンド実行の完了を通知しません。

    - この問題が発生した場合は、[パッケージの管理] タブでパッケージの状態 **を** 表示できます。

      :::image type="content" alt-text="パッケージを管理するためのイメージ。" source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - テストが成功した場合は、テスト **の概要**、 **セキュリティ更新プログラムの結果** 、 **機能更新プログラムの結果** のページをスケジュールされた間隔で確認できます。多くの場合、アップロードの数日後に開始されます。
  
    - 失敗したテストでは、新しいパッケージをアップロードする必要があります。 

      **テスト ログ** をダウンロードして、**セキュリティ更新プログラムの結果と機能更新プログラムの結果** ページから詳細 **な分析を行** うことができます。

    - テストエラーが繰り返し発生した場合は、エラーの詳細を testbasepreview@microsoft.com にお問い合わせください。

## <a name="next-steps"></a>次の手順

以下のリンクからコンテンツ ガイドラインをご覧ください。

> [!div class="nextstepaction"]
> [次の手順](contentguideline.md)
