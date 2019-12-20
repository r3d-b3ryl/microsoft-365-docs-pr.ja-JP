---
title: Trainable 分類子を作成する (プレビュー)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: '[使用準備完了] ボックス分類子のいずれかがニーズに合わない場合は、trainable 分類子を使用します。 Microsoft 365 の分類子は、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。そのためのサンプルを参照してください。 このトピックでは、カスタム分類子を作成する方法について説明します。'
ms.openlocfilehash: 6343635bb8e9dac12a8dde0867b3468347c2e84a
ms.sourcegitcommit: d656fd58e5491cfb7fee16b55dc7a58904ed128d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "39891088"
---
# <a name="creating-a-trainable-classifier-preview"></a>Trainable 分類子を作成する (プレビュー)

Trainable 分類子のいずれかがニーズに合わない場合は、分類子を使用します。 Microsoft 365 の分類子は、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。そのためのサンプルを参照してください。 分類子のトレーニングでは、まず、人間が選択され、カテゴリに対してプラスに一致するサンプルを提供します。 その後、それらを処理した後、正と負の両方のサンプルを組み合わせて予測をテストします。

さまざまな分類子の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-getting-started-with.md) 」を参照してください。

このタイムラインには、サンプルの展開が反映されています。

![trainable-クラシファイア-タイムライン](media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Trainable 分類子では、最初にオプトインが必要です。 Microsoft 365 で組織のコンテンツのベースライン評価を完了するには、12日間かかります。 グローバル管理者に連絡して、オプトインプロセスを開始します。

## <a name="seed-content"></a>Seed コンテンツ

Trainable 分類子を個別に特定のカテゴリのコンテンツにする必要がある場合は、まず、カテゴリに含まれるコンテンツの種類の多くのサンプルを提示する必要があります。 Trainable 分類子へのこのサンプルのフィードは、*シード*と呼ばれます。 Seed コンテンツは人間が選択し、コンテンツのカテゴリを表すことを判断します。

> [!TIP]
> 少なくとも50の正のサンプルと最大500が必要です。 Trainable 分類子は、最新の作成済みサンプル (ファイル作成日時スタンプ) を500まで処理します。 指定したサンプル数が多いほど、分類子が実行する予測がより正確になります。

## <a name="testing-content"></a>コンテンツのテスト

Trainable クラシファイアが、予測モデルを構築するのに十分な正のサンプルを処理したら、その分類をテストして、分類項目に一致する項目と、それに一致しないアイテムを正しく区別できるかどうかを確認する必要があります。 これを行うには、より大きなユーザーが選択したコンテンツセットを別のものにします。これは、カテゴリとサンプルに分類される必要のあるサンプルで構成されます。 それらを処理した後、結果を手動で調べ、各予測が正しいかどうか、または確認できないかどうかを確認します。 Trainable 分類子は、このフィードバックを使用して予測モデルを改善します。

> [!TIP]
> 最良の結果を得るには、正と負の一致が均等に分配された1万アイテムをテストサンプルセットに含める必要があります。

## <a name="how-to-create-a-trainable-classifier"></a>Trainable 分類子を作成する方法

1. 50-500 の seed コンテンツ項目の間で収集します。 これらは、trainable 分類子が分類カテゴリに含まれるコンテンツの種類を厳密に表すサンプルである必要があります。 サポートされているファイルの種類については、「 [SharePoint Server での既定のクロール対象ファイル名拡張子および解析済みファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)」を参照してください。

> [!IMPORTANT]
> シードおよびテストサンプルアイテムは、暗号化する必要があり、英語である必要があります。

> [!IMPORTANT]
> Seed セット内のアイテムがカテゴリの**強力な**例であることを確認してください。 Trainable 分類子は、最初にそのモデルをシードしたものに基づいてモデルを作成します。 この分類子は、すべてのシードサンプルが強力なものであることを前提としていますが、サンプルがカテゴリに対して弱いまたは否定的一致であるかどうかを知ることはできません。

2. Seed*コンテンツを保持する*専用の SharePoint Online フォルダーにシードコンテンツを配置します。 サイト、ライブラリ、およびフォルダーの URL をメモしておきます。

> [!TIP]
> Seed データ用の新しいサイトとフォルダーを作成する場合は、そのシードデータを使用する trainable 分類子を作成する前に、少なくとも1時間、その場所にインデックスを作成するようにしてください。

3. コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**または**microsoft 365 セキュリティセンター** > の**データ分類**を開く

4. [ **Trainable 分類子**] タブを選択します。

5. [ **Create trainable クラシファイア**] を選択します。

6. この trainable 分類子`Name`で識別するアイテム`Description`のカテゴリのフィールドに適切な値を入力します。

7. 手順2で、seed コンテンツサイトの正確な SharePoint Online サイト、ライブラリ、およびフォルダーの URL を入力します。 [ `Add`] を選択します。

8. 設定を確認し、 `Create trainable classifier`[] を選択します。

9. 24時間以内、trainable クラシファイアはシードデータを処理し、予測モデルを作成します。 分類子の状態`In progress`は、シードデータを処理している間になります。 分類子がシードデータの処理を完了すると、状態は`Need test items`に変わります。

10. 分類子を選択することによって、[詳細] ページを表示できるようになりました。


![テストの準備が整った trainable クラシファイア](media/classifier-trainable-ready-to-test-detail.png)

11. 少なくとも200のテストコンテンツアイテムを収集します。 Microsoft では、最適な結果を得るために1万をお勧めします。 これらのアイテムは、強力な陽性、強力なネガ、およびそれらの性質上の明確にわかりにくい項目を組み合わせたものにする必要があります。 サポートされているファイルの種類については、「 [SharePoint Server での既定のクロール対象ファイル名拡張子および解析済みファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)」を参照してください。

> [!IMPORTANT]
> サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。

12. テストコンテンツ*のみ*を保持する専用の SharePoint Online フォルダーにテストコンテンツを配置します。 SharePoint Online のサイト、ライブラリ、およびフォルダーの URL をメモしておきます。

> [!TIP]
> テストデータ用に新しいサイトとフォルダーを作成する場合は、そのシードデータを使用する trainable 分類子を作成する前に、少なくとも1時間、その場所にインデックスを設定するようにしてください。

13. [ `Add items to test`] を選択します。

14. 手順12から、テストコンテンツサイトの正確な SharePoint Online サイト、ライブラリ、およびフォルダーの URL を入力します。 [ `Add`] を選択します。

15. を選択`Done`してウィザードを終了します。 Trainable の分類子は、テストファイルの処理に最大1時間かかります。

16. Trainable クラシファイアがテストファイルの処理を完了すると、詳細ページの状態はに`Ready to review`変わります。 テストサンプルサイズを増やす必要がある場合は、 `Add items to test` trainable クラシファイアが追加のアイテムを処理することを選択して許可します。

![スクリーンショットを確認する準備ができました](media/classifier-trainable-ready-to-review-detail.png)

17. [ `Tested items to review`タブ] を選択してアイテムを確認します。

18. Microsoft 365 は、一度に30個のアイテムを提示します。 それらを確認し、 `We predict this item is "Relevant". Do you agree?`ボックスで、 `Yes`また`No`は`Not sure, skip to next item`のどちらかを選択します。 モデル精度は30アイテムごとに自動的に更新されます。

![[アイテムの確認] ボックス](media/classifier-trainable-review-detail.png)

19. *少なく*とも200のアイテムを確認します。

<!-- insert Analyze steps here-->

20. 精度が少なくとも70% に達するまで確認を続け`Publish the classifier` 、状態`Ready to use`はになります。

![精度と発行の準備ができている](media/classifier-trainable-review-ready-to-publish.png)

21. 分類子を発行します。

22. 発行された分類子は、条件および[通信のコンプライアンス](communication-compliance.md)に基づいて、[自動適用の保持ラベルポリシー](labels.md#applying-a-retention-label-automatically-based-on-conditions)の条件として使用できます。

> [!CAUTION]
> 分類子が公開されると、追加のトレーニングを受けることはできません。そのため、できるだけ多くのアイテムをテストして確認し、その精度が可能な限り高くなることを確認してください。

## <a name="see-also"></a>関連項目

- [トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-getting-started-with.md)
- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
