---
title: トレーニング可能な分類子の使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 分類子は、さまざまな種類のコンテンツを見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。 この記事では、カスタム分類子を作成してトレーニングする方法と、それらを再トレーニングして精度を高める方法について説明します。
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752661"
---
# <a name="get-started-with-trainable-classifiers"></a>トレーニング可能な分類子の使用を開始する

Microsoft 365 トレーニング可能な分類子は、さまざまな種類のコンテンツを見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。 トレーニングを受けたら、それを使用して、Office の区別ラベル、通信コンプライアンス ポリシー、および保持ラベル ポリシーの適用項目を識別できます。

最初に、トレーニング可能なカスタム分類子を作成するには、ユーザーが選択し、カテゴリに積極的に一致するサンプルを提供する必要があります。 次に、分類子を処理した後、正と負のサンプルを組み合わせ、分類子の予測能力をテストします。 この記事では、カスタム分類子を作成してトレーニングする方法と、トレーニング可能なカスタム分類子と事前トレーニング済みの分類子の有効期間中のパフォーマンスを再トレーニングによって改善する方法について説明します。

さまざまな種類の分類子の詳細については、「トレーニング可能な分類子について [」を参照してください](classifier-learn-about.md)。

## <a name="prerequisites"></a>前提条件

### <a name="licensing-requirements"></a>ライセンスの要件

分類子は、Microsoft 365 E5 または E5 コンプライアンス機能です。 それらを使用するには、これらのサブスクリプションのいずれかが必要です。

### <a name="permissions"></a>アクセス許可

UI で分類子にアクセスするには: 

- グローバル管理者は、カスタム分類子を作成するためにテナントをオプトインする必要があります。
- 分類子をトレーニングするには、コンプライアンス管理者の役割が必要です。

次のシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。

- 保持ラベル ポリシー のシナリオ: レコード管理とアイテム保持管理の役割 
- [Sensitivity label policy scenario]: セキュリティ管理者、コンプライアンス管理者、コンプライアンス データ管理者
- 通信コンプライアンス ポリシー シナリオ: Insider Risk Management Admin、Supervisory Review Administrator 

> [!IMPORTANT]
> 既定では、カスタム分類子を作成したユーザーだけが、その分類子によって行われた予測をトレーニングおよび確認できます。

## <a name="prepare-for-a-custom-trainable-classifier"></a>カスタムのトレーニング可能な分類子を準備する 

カスタムのトレーニング可能な分類子を作成する際に何が関係するのかを理解してから、理解を深めておくのが便利です。 

### <a name="timeline"></a>タイムライン

このタイムラインは、トレーニング可能な分類子のサンプル展開を反映しています。

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> トレーニング可能な分類子では、初めてオプトインが必要です。 組織のコンテンツのベースライン評価を完了するには、Microsoft 365 に 12 日かかります。 オプトイン プロセスを開始するには、グローバル管理者に問い合わせてください。

### <a name="overall-workflow"></a>ワークフロー全体

カスタムのトレーニング可能な分類子を作成する全体的なワークフローの詳細については、「顧客のトレーニング可能な分類子を作成するためのプロセス フロー」を [参照してください](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)。

### <a name="seed-content"></a>シード コンテンツ

トレーニング可能な分類子が、アイテムを特定のカテゴリのコンテンツとして独立して正確に識別するには、まず、そのカテゴリに含むコンテンツの種類の多くのサンプルを表示する必要があります。 このトレーニング可能な分類子へのサンプルのフィードは、シード処理と *呼ばれる方法です*。 シード コンテンツは人間によって選択され、コンテンツのカテゴリを表すと判断されます。

> [!TIP]
> 50 以上の正のサンプルと最大 500 のサンプルが必要です。 トレーニング可能な分類子は、(ファイル作成日時スタンプにより) 作成された最新のサンプルを最大 500 件処理します。 サンプルを提供する数が多い場合、分類子が予測する精度が高くなっています。

### <a name="testing-content"></a>コンテンツのテスト

トレーニング可能な分類子が予測モデルを構築するのに十分な正のサンプルを処理したら、予測をテストして、分類子がカテゴリに一致するアイテムと一致しないアイテムを正しく区別することができるか確認する必要があります。 これを行うには、カテゴリに分類する必要があるサンプルと、分類しないサンプルで構成される、人が選んだ別の大きなコンテンツのセットを選択します。 最初に指定した初期シード データとは異なるデータでテストする必要があります。 これらの予測を処理したら、手動で結果を確認し、各予測が正しいか、正しくないか、または不確かかどうかを確認します。 トレーニング可能な分類子は、このフィードバックを使用して予測モデルを改善します。

> [!TIP]
> 最適な結果を得る場合は、テスト サンプル セット内に、正と負の一致が 200 以上のアイテムが含まれています。

## <a name="how-to-create-a-trainable-classifier"></a>トレーニング可能な分類子を作成する方法

1. 50 ~ 500 のシード コンテンツ アイテムを収集します。 これらは、トレーニング可能な分類子が分類カテゴリ内にあると肯定的に識別するコンテンツの種類を強く表すサンプルである必要があります。 サポートされている [ファイルの種類については、SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) の既定のクロールされたファイル名の拡張子と解析されたファイルの種類を参照してください。

   > [!IMPORTANT]
   > シードとテストのサンプル アイテムは暗号化し、英語である必要があります。

   > [!IMPORTANT]
   > シード セット内のアイテムがカテゴリの強力 **な** 例である必要があります。 トレーニング可能な分類子は、最初に、そのモデルのシードに基づいてモデルを構築します。 分類子は、すべてのシード サンプルが強い陽性と見なし、サンプルがカテゴリに対して弱い一致か負の一致かを知る方法はありません。

2. シード コンテンツのみを保持する専用の SharePoint Online フォルダー *にシード コンテンツを配置します*。 サイト、ライブラリ、およびフォルダーの URL をメモします。

   > [!TIP]
   > シード データ用の新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所のインデックスが作成されるのに少なくとも 1 時間は必要です。

3. コンプライアンス管理者またはセキュリティ管理者の役割にアクセスして Microsoft 365 コンプライアンス センターにサインインし **、Microsoft 365** コンプライアンス センターまたは **Microsoft 365** セキュリティ センターのデータ分類を開  >  **きます**。

4. [ **トレーニング可能な分類子] タブを選択** します。

5. [ **トレーニング可能な分類子の作成] を選択します**。

6. このトレーニング可能な分類子で識別するアイテムのカテゴリとフィールドに適切な値 `Name` `Description` を入力します。

7. 手順 2 のシード コンテンツ サイトの SharePoint Online サイト、ライブラリ、およびフォルダー URL を選択します。 Choose `Add` .

8. 設定を確認し、選択します `Create trainable classifier` 。

9. トレーニング可能な分類子は、24 時間以内にシード データを処理し、予測モデルを構築します。 分類子の状態は、 `In progress` シード データの処理中です。 分類子がシード データの処理を完了すると、状態は次の状態に変わります `Need test items` 。

10. 分類子を選択して詳細ページを表示できます。

    > [!div class="mx-imgBorder"]
    > ![テストの準備が整ったトレーニング可能な分類子](../media/classifier-trainable-ready-to-test-detail.png)

11. 最適な結果を得る場合は、少なくとも 200 のテスト コンテンツ アイテム (最大 10,000 アイテム) を収集します。 これらは、強い陽性、強い陰性、および性質が少し明らかではない項目の組み合わせである必要があります。 サポートされている [ファイルの種類については、SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) の既定のクロールされたファイル名の拡張子と解析されたファイルの種類を参照してください。

    > [!IMPORTANT]
    > サンプルアイテムは暗号化し、英語である必要があります。

12. テスト コンテンツのみを保持する専用の SharePoint Online フォルダー *にテスト コンテンツを配置します*。 SharePoint Online サイト、ライブラリ、およびフォルダーの URL をメモします。

    > [!TIP]
    > テスト データ用に新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所のインデックスが作成されるのに少なくとも 1 時間は必要です。

13. Choose `Add items to test` .

14. 手順 12. で、テスト コンテンツ サイトの SharePoint Online サイト、ライブラリ、およびフォルダー URL を選択します。 Choose `Add` .

15. 選択してウィザードを終了します `Done` 。 トレーニング可能な分類子は、テスト ファイルの処理に最大 1 時間かかる場合があります。

16. トレーニング可能な分類子がテスト ファイルの処理を完了すると、詳細ページの状態が次に変わります `Ready to review` 。 テスト サンプルのサイズを増やす必要がある場合は、トレーニング可能な分類子が追加のアイテムを処理 `Add items to test` する方法を選択して許可します。

    > [!div class="mx-imgBorder"]
    > ![スクリーンショットを確認する準備](../media/classifier-trainable-ready-to-review-detail.png)

17. アイテム `Tested items to review` を確認するタブを選択します。

18. Microsoft 365 では、一度に 30 アイテムが表示されます。 それらを確認し、ボックス `We predict this item is "Relevant". Do you agree?` でどちらかまたは `Yes` 選択 `No` します `Not sure, skip to next item` 。 モデルの精度は、30 項目ごとに自動的に更新されます。

    > [!div class="mx-imgBorder"]
    > ![[アイテムの確認] ボックス](../media/classifier-trainable-review-detail.png)

19. 少 *なくとも* 200 アイテムを確認します。 精度スコアが安定すると、発行 **オプション** が使用可能になり、分類子の状態が表示されます `Ready to use` 。

    > [!div class="mx-imgBorder"]
    > ![精度スコアと公開準備完了](../media/classifier-trainable-review-ready-to-publish.png)

20. 分類子を発行します。

21. 公開された分類子は[、Office](apply-sensitivity-label-automatically.md)の条件として、機度ラベルによる自動ラベル付け、条件と通信コンプライアンスに[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)基づいて保持ラベル ポリシーを自動適用[できます。](communication-compliance.md)
