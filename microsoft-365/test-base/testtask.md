---
title: テスト タスクを設定する
description: テスト タスクを設定する
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
ms.openlocfilehash: 3356fc09609601d1974cb3daea7ea7aeb6ac979e
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316339"
---
# <a name="step-4-the-tasks-tab"></a>手順 4: [タスク] タブ

[タスク] タブでは、バイナリ タブの下にアップロードした zip フォルダーにあるテスト スクリプトへのパスを指定する必要があります。

  - **既定のテスト スクリプト:** インストール、起動、閉じる、およびアンインストールするスクリプトの相対パスを入力します。 インストール スクリプトの追加設定を選択することもできます。
  - **機能テスト スクリプト:** アップロードされた各機能テスト スクリプトへの相対パスを入力します。 このボタンを使用して、追加の機能テスト スクリプトを ```Add Script``` 追加できます。 少なくとも 1 つの (1) スクリプトが必要であり、最大 8 個の機能テスト スクリプトを追加できます。 
  
    スクリプトは、一覧に示されている順序で実行されます。 特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止されます。
    また、指定されたスクリプトごとに追加の設定を選択することもできます。

## <a name="set-script-path"></a>スクリプト パスを設定する

![テスト タスクの画像。](Media/testtask.png)

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


## <a name="next-steps"></a>次の手順

次の記事の [テスト オプション] タブの詳細を表示する 
> [!div class="nextstepaction"]
> [次のステップ](testoptions.md)
