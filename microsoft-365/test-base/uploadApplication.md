---
title: パッケージをアップロードする
description: Appplication、バイナリ、依存関係をテスト ベースにアップロードする方法
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
ms.openlocfilehash: e8b4323eda31c55bbf32de0996fc7bd48d54ade2
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323092"
---
# <a name="step-2-uploading-a-package"></a>手順 2: パッケージのアップロード

[Test Base portal] ページで、左側のナビゲーション バーの [アップロード 新しいパッケージ] オプションに移動します。次に示すように、新しいパッケージアップロード ![ 選択します。](Media/Upload-New-Package.png)

その後、以下の手順に従って新しいパッケージをアップロードします。

## <a name="enter-details-for-your-package"></a>パッケージの詳細を入力する

[テストの詳細] タブで、要求に応じてパッケージの名前、バージョン、その他の詳細を入力します。 

**アウトオブボックステストと****機能テストは**、このダッシュボードを使用して実行できます。

以下の手順では、パッケージの詳細を入力する方法のガイドを示します。

1.  **フィールドにパッケージを指定する名前を入力 ```“Package name``` します。**

> [!Note]  
> 入力したパッケージ名とバージョンの組み合わせは、組織内で一意である必要があります。 これは、次に示すようにチェックマークによって検証されます。
  
  - パッケージの名前を再使用する場合、バージョン番号は一意である必要があります (つまり、その特定の名前を持つパッケージでは使用されません)。
  - パッケージ名 + バージョンの組み合わせが一意性チェックに合格しない場合は、「このパッケージバージョンのパッケージが既に存在する」というエラー メッセージ *が表示されます*。 

![パッケージの手順をアップロードするイメージ](Media/Instructions.png)

2. **[パッケージ のバージョン] フィールドにバージョンを入力します。**

![パッケージのバージョン](Media/ApplicationVersion.png)

3.  **このパッケージで実行するテストの種類を選択する**

    アウト **オブボックス (OOB)** テストでは、パッケージのインストール、*起動*、*閉じる*、*アンインストール* を実行します。 インストール後、1 回のアンインストールが実行される前に、起動終了ルーチンが 30 回繰り返されます。 
    
    この OOB テストでは、パッケージ上で標準化されたテレメトリを提供し、さまざまなビルドWindowsします。

    機能 **テストでは、** パッケージにアップロードされたテスト スクリプトが実行されます。 スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止します。

> [!Note]
> **すべての** スクリプトは最大で 80 分間実行されます。 
    
4.  **OS の更新の種類を選択する**

   - 'セキュリティ更新プログラム' を使用すると、パッケージをリリース前の月次セキュリティ更新プログラムWindows増分チャーンに対してテストできます。 
   - 'フィーチャー更新プログラム' を使用すると、パッケージを、Windows Insider Program からビルドされた 2 年のプレリリース機能更新プログラムに対してWindowsできます。
<!---
Change to the correct picture
-->
![OS 更新プログラムの種類](Media/OSUpdateType.png)

5.  **セキュリティ更新プログラムテストの OS バージョンを選択します。**

[複数選択] ドロップダウンで、パッケージがインストールWindowsの OS バージョンを選択します。 

  - パッケージをクライアント OSes Windowsテストするには、メニュー リストから該当する Windows 11 OS バージョンを選択します。
  - パッケージをサーバー OSes Windowsテストするには、メニュー リストから該当するサーバー OS Windowsを選択します。
  - パッケージをクライアントおよびサーバー Windowsに対してテストするには、メニューリストから該当する OS を選択します。 

> [!Note]
> サーバーとクライアントの両方の OSes に対してパッケージをテストする場合は、パッケージが互換性があり、両方の OSes で実行可能である必要があります。


![OS バージョンの選択](Media/OSVersion.png)
<!---
Change to the correct picture
-->
6.  **機能更新プログラムのテストのオプションを選択します。**

  - [Insider チャネルの選択] オプションで、パッケージをテストするビルド ```Windows Insider Program Channel``` として選択します。
  
    現在、Insider ベータ チャネルで提供されているビルドを使用しています。

  - [分析情報の OS ベースラインを選択する] オプションで、テストWindows比較の基準として使用する OS バージョンを選択します。 

> [!Note]
> 現時点では、サーバー OSes の機能更新テストはサポートされていません
<!---
Note to actual note format for markdown
-->
<!---
Change to the correct picture
-->
![機能更新プログラムのテスト](Media/FeatureUpdate.png)

7.  完了したテストの詳細ページは次のように表示されます。 

![テストの詳細の表示](Media/TestDetails.png)
## <a name="next-steps"></a>次の手順

次の記事では、バイナリをセリブセにアップロードする方法について説明します。
> [!div class="nextstepaction"]
> [次の手順](binaries.md)

<!---
Add button for next page
-->

