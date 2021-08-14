---
title: パッケージをアップロードする
description: アプリケーション、バイナリ、依存関係をテスト ベースにアップロードする方法
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 80ea369284e9b9677bbd1e51612915057eea3136b5e8c6172230e332187edb1e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53816525"
---
# <a name="step-2-uploading-a-package"></a>手順 2: パッケージのアップロード

[テスト ベース ポータル] ページで、次に示すようにアップロード左側のナビゲーション バーの [新しいパッケージ] オプションに移動します。

:::image type="content" alt-text="アップロードパッケージを作成します。" source="Media/Upload-New-Package.png" lightbox="Media/Upload-New-Package.png":::

その後、以下の手順に従って新しいパッケージをアップロードします。

## <a name="enter-details-for-your-package"></a>パッケージの詳細を入力する

[テストの詳細] タブで、要求に応じてパッケージの名前、バージョン、その他の詳細を入力します。

**アウトオブボックステストと****機能テストは**、このダッシュボードを使用して実行できます。

以下の手順では、パッケージの詳細を入力する方法のガイドを示します。

1. フィールドにパッケージを指定する名前を入力 `Package name` します。

    > [!NOTE]
    > 入力したパッケージ名とバージョンの組み合わせは、組織内で一意である必要があります。 これは、次に示すようにチェックマークによって検証されます。

    - パッケージの名前を再利用する場合、バージョン番号は一意である必要があります (つまり、その特定の名前を持つパッケージでは使用されません)。

    - パッケージ名とバージョンの組み合わせが一意性チェックに合格しない場合は、「このパッケージバージョンのパッケージが既に存在する」というエラー メッセージ *が表示されます*。

    :::image type="content" alt-text="パッケージの手順をアップロードするイメージ。" source="Media/Instructions.png":::

2. [パッケージ のバージョン] フィールドにバージョンを入力します。

    :::image type="content" alt-text="パッケージのバージョン。" source="Media/ApplicationVersion.png":::

3. このパッケージで実行するテストの種類を選択します。

    アウト **オブボックス (OOB)** テストでは、パッケージのインストール、*起動*、*終了*、*アンインストール* を実行します。 インストール後、1 回のアンインストールが実行される前に、起動終了ルーチンが 30 回繰り返されます。

    この OOB テストでは、パッケージ上で標準化されたテレメトリを提供し、さまざまなビルドWindowsします。

    機能 **テストでは、** パッケージにアップロードされたテスト スクリプトが実行されます。 スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止します。

    > [!NOTE]
    > **すべての** スクリプトは最大で 80 分間実行されます。

4. OS 更新プログラムの種類を選択します。

    - 'セキュリティ更新プログラム' を使用すると、パッケージをリリース前の月次セキュリティ更新プログラムWindows増分チャーンに対してテストできます。
    - 'フィーチャー更新プログラム' を使用すると、パッケージを、Windows Insider Program からビルドされた 2 年のプレリリース機能更新プログラムに対してWindowsできます。
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="OS の更新の種類。" source="Media/OSUpdateType.png":::

5. セキュリティ更新プログラムテストの OS バージョンを選択します。

    [複数選択] ドロップダウンで、パッケージがインストールWindowsの OS バージョンを選択します。

    - パッケージをクライアント オペレーティング システムWindowsのみをテストするには、メニュー リストから該当する Windows 11 の OS バージョンを選択します。
    - パッケージをサーバー オペレーティング システムWindowsテストするには、メニュー リストから該当するサーバー OS Windowsバージョンを選択します。
    - パッケージをクライアントおよびサーバー オペレーティング Windowsサーバー Windows対してのみテストするには、メニューリストから該当するオペレーティング システムを選択します。

    > [!NOTE]
    > サーバーとクライアントの両方の OSes に対してパッケージをテストする場合は、パッケージが互換性があり、両方の OSes で実行可能である必要があります。

    :::image type="content" alt-text="OS バージョンの選択。" source="Media/OSVersion.png":::
    <!---
    Change to the correct picture
    -->

6. 機能更新プログラムのテストのオプションを選択します。

    - [Insider チャネルの選択] オプションで、パッケージをテストするビルド `Windows Insider Program Channel` として選択します。

      現在、Insider ベータ チャネルで提供されているビルドを使用しています。

    - [分析情報の OS ベースラインを選択する] オプションで、テストWindows比較の基準として使用する OS バージョンを選択します。

    > [!NOTE]
    > 現時点では、サーバー OSes の機能更新テストはサポートされていません
    <!---
    Note to actual note format for markdown
    -->
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="機能更新プログラムのテスト。" source="Media/FeatureUpdate.png":::

7. 完了したテストの詳細ページは次のように表示されます。

    :::image type="content" alt-text="テストの詳細の表示。" source="Media/TestDetails.png":::

## <a name="next-steps"></a>次の手順

次の記事では、サービスへのバイナリのアップロードについて説明します。

> [!div class="nextstepaction"]
> [次の手順](binaries.md)

<!---
Add button for next page
-->
