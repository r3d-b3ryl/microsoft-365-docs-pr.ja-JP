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
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bb6ef605d360e259ef9fa91ed51da35506a2942
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208819"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>手順 6: 選択内容を確認してパッケージを作成します。

1. このタブでは、サービスはテストの詳細を表示し、クイック完了チェックを実行します。

    渡 **された検証または****検証に失敗したメッセージ** は、次の手順に進むかどうかを示します。

2. テストの詳細を確認し、満足したら、[作成] ボタン **をクリック** します。

    :::image type="content" alt-text="検証を表示します。" source="Media/validation.png" lightbox="Media/validation.png":::

3. これにより、パッケージが Test Base 環境にオンボードされます。 パッケージが正常に作成されると、Azure でパッケージを正常に実行できるかどうかを確認する自動テストがトリガーされます。

    ![成功した結果。](Media/successful.png)

    > [!NOTE]
    > Azure portal から通知を受け取り、パッケージ検証の成功または失敗を通知します。
    >
    > このプロセスには最大 24 時間かかる場合があるため、アクティブではない場合は Web ページがタイムアウトする可能性があるため、このオンデマンド実行が完了したという通知は通知されません。

    - Peradventure この問題が発生すると、[パッケージの管理] タブでパッケージの状態 **を表示** できます。

      :::image type="content" alt-text="パッケージを管理するためのイメージ。" source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - 成功したテストでは、テストの概要、セキュリティ更新プログラムの結果、機能更新プログラムの結果ページをスケジュールされた間隔で確認できます。多くの場合、アップロードの数日後に開始します。 
  
    - テストに失敗した場合は、新しいパッケージをアップロードする必要があります。 

      テスト ログをダウンロード **して、セキュリティ** 更新プログラムの結果と機能更新プログラムの結果ページ **から詳細な分析を行** います。

    - テストエラーが繰り返し発生する場合は、エラーの testbasepreview@microsoft.com を確認してください。

## <a name="next-steps"></a>次の手順

以下のリンクからコンテンツ ガイドラインをご覧ください。

> [!div class="nextstepaction"]
> [次の手順](contentguideline.md)
