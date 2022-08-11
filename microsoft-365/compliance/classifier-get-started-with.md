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
ms.localizationpriority: ''
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkDEFENDER
search.appverid:
- MOE150
- MET150
description: Microsoft 365 分類子は、見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。 この記事では、カスタム分類子を作成してトレーニングする方法と、それらを再トレーニングして精度を高める方法について説明します。
ms.openlocfilehash: 16ae9e3d3ee7efc6d82be7b89f99b8b57cdb0845
ms.sourcegitcommit: 771f7bbb241f910b3e16b4d1f9bbd9c0c8c6fa34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67309815"
---
# <a name="get-started-with-trainable-classifiers"></a>トレーニング可能な分類子の使用を開始する

Microsoft 365 トレーニング可能な分類子は、見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。 トレーニングが完了したら、それを使用して、Office 秘密度ラベル、通信コンプライアンス ポリシー、およびアイテム保持ラベル ポリシーの適用項目を識別できます。

最初にカスタムトレーニング可能な分類子を作成するには、人間が選ばれ、カテゴリに正に一致するサンプルを提供する必要があります。 次に、それらを処理した後、正と負のサンプルを組み合わせて分類子に予測する能力をテストします。 この記事では、カスタム分類子を作成してトレーニングする方法と、再トレーニングを通じてカスタムトレーニング可能な分類子と事前トレーニング済み分類子の有効期間にわたるパフォーマンスを向上させる方法について説明します。

さまざまな種類の分類子の詳細については、「 [トレーニング可能な分類子の詳細」](classifier-learn-about.md)を参照してください。

トレーニング可能な分類子の作成の簡単な概要については、このビデオをご覧ください。 詳細を取得するには、この完全な記事を読む必要があります。

</br>

<!-- [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]-->


## <a name="prerequisites"></a>前提条件

### <a name="licensing-requirements"></a>ライセンスの要件

分類子は、Microsoft 365 E5または E5 コンプライアンス機能です。 それらを使用するには、これらのサブスクリプションのいずれかが必要です。

### <a name="permissions"></a>アクセス許可

UI で分類子にアクセスするには: 

- グローバル管理者は、カスタム分類子を作成するためにテナントをオプトインする必要があります。
- 分類子をトレーニングするには、コンプライアンス管理者ロールが必要です。

これらのシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。

- アイテム保持ラベル ポリシーのシナリオ: レコード管理ロールと保持管理ロール 
- 秘密度ラベル ポリシーのシナリオ: セキュリティ管理者、コンプライアンス管理者、コンプライアンス データ管理者
- コミュニケーション コンプライアンス ポリシーのシナリオ: Insider Risk Management 管理、スーパーバイザー レビュー管理者 

> [!IMPORTANT]
> 既定では、カスタム分類子を作成するユーザーのみが、その分類子によって行われた予測をトレーニングおよび確認できます。

## <a name="prepare-for-a-custom-trainable-classifier"></a>カスタムトレーニング可能な分類子の準備 

詳細を確認する前に、カスタムトレーニング可能な分類子の作成に何が関係するかを理解しておくと便利です。 

### <a name="timeline"></a>タイムライン

このタイムラインには、トレーニング可能な分類子のサンプルデプロイが反映されています。

![trainable-classifier-timeline。](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> トレーニング可能な分類子には、初めてオプトインが必要です。 Microsoft 365 が組織のコンテンツのベースライン評価を完了するまでに 12 日かかります。 オプトイン プロセスを開始するには、グローバル管理者に問い合わせてください。

### <a name="overall-workflow"></a>全体的なワークフロー

カスタムトレーニング可能な分類子を作成する全体的なワークフローの詳細については、「カスタムトレーニング可能な分類子 [を作成するためのプロセス フロー](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)」を参照してください。

### <a name="seed-content"></a>シード コンテンツ

トレーニング可能な分類子でアイテムを特定のカテゴリのコンテンツとして個別かつ正確に識別する場合は、最初に、カテゴリ内のコンテンツの種類の多くのサンプルを提示する必要があります。 トレーニング可能な分類子へのサンプルのこのフィードは、 *シード* 処理と呼ばれます。 シード コンテンツは人間によって選択され、コンテンツのカテゴリを表すと判断されます。

> [!TIP]
> 少なくとも 50 個の正のサンプルと 500 個のサンプルが必要です。 トレーニング可能な分類子は、作成された最新の 500 個のサンプル (ファイル作成日時スタンプ別) まで処理します。 提供するサンプルが多いほど、分類子が行う予測の精度が高くなります。

### <a name="testing-content"></a>コンテンツのテスト

トレーニング可能な分類子が予測モデルを構築するのに十分な正のサンプルを処理したら、分類子がカテゴリと一致する項目と一致しない項目を正しく区別できるかどうかを確認するために、予測をテストする必要があります。 これを行うには、カテゴリに分類されるはずのサンプルと、該当しないサンプルで構成される、人間が選んだ別の、できれば大きなコンテンツのセットを選択します。 最初に指定した初期シード データとは異なるデータを使用してテストする必要があります。 これらの処理が完了したら、結果を手動で調べて、各予測が正しいか、正しくないか、わからないかを確認します。 トレーニング可能な分類子は、このフィードバックを使用して予測モデルを改善します。

> [!TIP]
> 最良の結果を得るには、テスト サンプル セットに少なくとも 200 個の項目があり、正と負の一致が均等に分布します。

## <a name="how-to-create-a-trainable-classifier"></a>トレーニング可能な分類子を作成する方法

1. 50 ~ 500 個のシード コンテンツ アイテムを収集します。 これらは、トレーニング可能な分類子が分類カテゴリ内にあると肯定的に識別するコンテンツの種類を強く表すサンプルである必要があります。 サポート [されているファイルの種類については、SharePoint Server の既定のクロールされたファイル名拡張子と解析された](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) ファイルの種類を参照してください。

   > [!IMPORTANT]
   > シード セット内の項目が、カテゴリの **強力な** 例であることを確認します。 トレーニング可能な分類子は、最初に、それをシードした内容に基づいてモデルを構築します。 分類子は、すべてのシード サンプルが強力な陽性であり、サンプルがカテゴリに対して弱いか負の一致かどうかを知る方法がないことを前提としています。

2. シード コンテンツのみを保持する専用の SharePoint Online フォルダーに *シード コンテンツを* 配置します。 サイト、ライブラリ、フォルダーの URL を書き留めます。

   > [!TIP]
   > シード データ用に新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所に少なくとも 1 時間はインデックスを付けます。

3. コンプライアンス管理者またはセキュリティ管理者ロールへのアクセスを使用してMicrosoft Purview コンプライアンス ポータルにサインインし <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">、ポータルデータ分類Microsoft Purview コンプライアンス ポータル</a>または <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> > 開 **きます**。

4. **[トレーニング可能な分類子]** タブを選択します。

5. **[トレーニング可能な分類子を作成]** を選択します。

6. このトレーニング可能な分類子で識別する項目のカテゴリと`Description`フィールドに適切な値`Name`を入力します。

7. 手順 2. から、シード コンテンツ サイトの SharePoint Online サイト、ライブラリ、フォルダーの URL を選択します。 を選択します `Add`。

8. 設定を確認し、 `Create trainable classifier`.

9. トレーニング可能な分類子は 24 時間以内にシード データを処理し、予測モデルを構築します。 分類子の状態は、 `In progress` シード データの処理中です。 分類子がシード データの処理を完了すると、状態 `Need test items`は .

10. 分類子を選択して詳細ページを表示できるようになりました。

    > [!div class="mx-imgBorder"]
    > ![トレーニング可能な分類子をテストする準備ができました。](../media/classifier-trainable-ready-to-test-detail.png)

11. 最適な結果を得るには、少なくとも 200 個のテスト コンテンツ アイテム (最大 10,000 個) を収集します。 これらは、強い陽性、強いネガティブ、その性質上少し明らかでない項目の組み合わせである必要があります。 サポート [されているファイルの種類については、SharePoint Server の既定のクロールされたファイル名拡張子と解析された](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) ファイルの種類を参照してください。

12. テスト コンテンツのみを保持する専用の SharePoint Online フォルダーに *テスト コンテンツを* 配置します。 SharePoint Online のサイト、ライブラリ、フォルダーの URL を書き留めます。

    > [!TIP]
    > テスト データ用に新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所に少なくとも 1 時間はインデックスを付けます。

13. を選択します `Add items to test`。

14. 手順 12 から、テスト コンテンツ サイトの SharePoint Online サイト、ライブラリ、フォルダーの URL を選択します。 を選択します `Add`。

15. を選択してウィザードを `Done`終了します。 トレーニング可能な分類子は、テスト ファイルの処理に最大 1 時間かかります。

16. トレーニング可能な分類子でテスト ファイルの処理が完了すると、詳細ページの状態が `Ready to review`[ . テスト サンプル サイズを大きくする必要がある場合は、トレーニング可能な分類子が追加の項目を処理することを選択 `Add items to test` して許可します。

    > [!div class="mx-imgBorder"]
    > ![スクリーンショットを確認する準備ができました。](../media/classifier-trainable-ready-to-review-detail.png)

17. タブを選択 `Tested items to review` してアイテムを確認します。

18. Microsoft 365 では、一度に 30 個のアイテムが表示されます。 それらを確認し、ボックスで`We predict this item is "Relevant". Do you agree?`いずれかまたはを選択します`No``Not sure, skip to next item`。`Yes` モデルの精度は、30 項目ごとに自動的に更新されます。

    > [!div class="mx-imgBorder"]
    > ![[レビュー アイテム] ボックス。](../media/classifier-trainable-review-detail.png)

19. *少なくとも* 200 個のアイテムを確認します。 精度スコアが安定すると、 **発行** オプションが使用可能になり、分類子の状態は次のように表示 `Ready to use`されます。

    > [!div class="mx-imgBorder"]
    > ![精度スコアと公開の準備が整いました。](../media/classifier-trainable-review-ready-to-publish.png)

20. 分類子を発行します。

21. 公開されると、機密ラベルを使用した [Office 自動ラベル付けの](apply-sensitivity-label-automatically.md)条件として分類子を使用できるようになります。条件と[通信コンプライアンス](communication-compliance.md)[に基づいてアイテム保持ラベル ポリシーを自動適用](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)します。
