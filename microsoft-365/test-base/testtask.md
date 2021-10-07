---
title: テスト タスクを設定する
description: テスト タスクを設定する
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
ms.openlocfilehash: 1c459b85ed7d6a25de0b8fcdef24a6857531cee3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176153"
---
# <a name="step-4-the-tasks-tab"></a>手順 4: [タスク] タブ

[タスク] タブで、[バイナリ] タブでアップロードした zip フォルダーにあるテスト スクリプトへのパスを指定する必要があります。

  - **アウト オブ ボックスのテスト スクリプト:** インストール、起動、閉じる、アンインストールするスクリプトへの相対パスを入力します。 インストール スクリプトの追加設定を選択することもできます。
  - **機能テスト スクリプト:** アップロードされた各機能テスト スクリプトへの相対パスを入力します。 ボタンを使用して、追加の機能テスト スクリプトを追加 ```Add Script``` できます。 少なくとも 1 つのスクリプトが必要で、最大 8 つの機能テスト スクリプトを追加できます。 
  
    スクリプトはアップロード シーケンスで実行され、特定のスクリプトでエラーが発生すると、後続のスクリプトの実行が停止します。
    また、各スクリプトに対して追加の設定を選択することもできます。

## <a name="set-script-path"></a>スクリプト パスの設定

![テスト タスクのイメージ。](Media/testtask.png)

フォルダー構造に相対パスを指定する方法のサンプルは次のとおりです。

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** 必要があります。 _ScriptX.ps1_ パスとして指定します。
  - **Script.ps1** フォルダー _1/script.ps1パス_ として指定します。


## <a name="next-steps"></a>次の手順

次の記事の [テスト オプション] タブの詳細を表示する 
> [!div class="nextstepaction"]
> [次の手順](testoptions.md)
