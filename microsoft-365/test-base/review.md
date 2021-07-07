---
title: レビュー
description: オンボーディング後にセクションを確認します。
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
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323284"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>手順 6: 選択内容を確認してパッケージを作成します。

1.  このタブでは、サービスはテストの詳細を表示し、クイック完了チェックを実行します。 

    メッセージ ```Validation passed``` は ```Validation failed``` 、次の手順に進めるかどうかを示します。

2.  テストの詳細を確認し、満たされた場合は、ボタンをクリック ```Create``` します。 

![検証の表示](Media/validation.png)

3.  これにより、パッケージが Test Base 環境にオンボードされます。 パッケージが正常に作成されると、Azure でパッケージを正常に実行できるかどうかを確認する自動テストがトリガーされます。

![成功した結果](Media/successful.png)

> [!Note]
> Azure portal から通知を受け取り、パッケージ検証の成功または失敗を通知します。 
>
> このプロセスには最大 24 時間かかる場合があるため、アクティブではない場合は Web ページがタイムアウトする可能性があるため、このオンデマンド実行が完了したという通知は通知されません。 

  - Peradventure この問題が発生すると、タブでパッケージの状態を表示 ```Manage packages``` できます。

![パッケージを管理するためのイメージ](Media/managepackages.png)

  - テストの結果は、アップロード後数日後にスケジュールされた間隔で 、およびページを介して ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` 確認できます。
  
  - テストに失敗した場合は、新しいパッケージをアップロードする必要があります。 
  
    詳細な分析については ```test logs``` 、'とページから ```Security update results``` ダウンロード ```Feature updates results``` できます。

  - テストエラーが繰り返し発生する場合は、エラーの testbasepreview@microsoft.com を確認してください。 

## <a name="next-steps"></a>次の手順

以下のリンクからコンテンツ ガイドラインをご覧ください。
> [!div class="nextstepaction"]
> [次の手順](contentguideline.md)
