---
title: レビュー
description: オンボード後にセクションを確認します。
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

1. このタブでは、サービスによってテストの詳細が表示され、クイックコンプリート チェックが実行されます。

    **渡された検証** または **検証に失敗した** メッセージは、次の手順に進めるかどうかを示します。

2. テストの詳細を確認し、問題が発生した場合は、[ **作成** ] ボタンをクリックします。

    :::image type="content" alt-text="検証を表示します。" source="Media/validation.png" lightbox="Media/validation.png":::

3. これにより、パッケージがテスト ベース環境にオンボードされます。 パッケージが正常に作成されると、Azure でパッケージを正常に実行できるかどうかを検証する自動テストがトリガーされます。

    ![成功した結果。](Media/successful.png)

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
