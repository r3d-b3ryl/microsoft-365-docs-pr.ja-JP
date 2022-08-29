---
title: レビュー
description: オンボード後にセクションを確認します。
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
ms.openlocfilehash: f2c685af5c94260fce717db791eceee6a8a87060
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316558"
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

    - テストが成功した場合は、テスト **の概要**、**セキュリティ更新結果**、**機能更新結果** ページをスケジュールされた間隔で確認できます。多くの場合、アップロードの数日後に開始されます。
  
    - 失敗したテストでは、新しいパッケージをアップロードする必要があります。 

      **テスト ログ** をダウンロードして、**セキュリティ更新プログラムの結果と機能更新プログラムの結果** ページから詳細 **な分析を行** うことができます。

    - テストエラーが繰り返し発生した場合は、エラーの詳細を testbasepreview@microsoft.com にお問い合わせください。

## <a name="next-steps"></a>次の手順

以下のリンクからコンテンツ ガイドラインをご覧ください。

> [!div class="nextstepaction"]
> [次のステップ](contentguideline.md)
