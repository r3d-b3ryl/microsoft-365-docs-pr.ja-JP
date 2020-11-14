---
title: トレーニング可能な分類子の使用を開始する (プレビュー)
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
description: Microsoft 365 の分類子は、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。そのためのサンプルを参照してください。 この記事では、カスタム分類子を作成してトレーニングする方法と、それらを再トレーニングして精度を向上させる方法について説明します。
ms.openlocfilehash: 9fe50f7faada77492fd93a86d0c3549cc8e1d361
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072966"
---
# <a name="get-started-with-trainable-classifiers-preview"></a>トレーニング可能な分類子の使用を開始する (プレビュー)

Microsoft 365 trainable クラシファイアは、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。このツールを使用して、さまざまな種類のコンテンツを確認できます。 トレーニングを受けた後、それを使用して、Office の秘密度ラベル、通信コンプライアンスポリシー、および保持ラベルポリシーのアプリケーションの項目を識別できます。

最初にカスタム trainable 分類子を作成するには、人間が選択され、カテゴリに対して明確に一致するサンプルを提供する必要があります。 その後、それらを処理した後で、正と負の両方のサンプルを混在させて予測する分類子機能をテストします。 この記事では、ユーザー設定の分類子を作成してトレーニングする方法、およびユーザー設定の trainable 分類子と事前に分類された分類子のパフォーマンスを改善する方法について説明します。

分類子のさまざまな種類の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-learn-about.md)」を参照してください。

## <a name="prerequisites"></a>前提条件

### <a name="licensing-requirements"></a>ライセンスの要件

分類子は、Microsoft 365 E5 または E5 準拠の機能です。 それらを使用するには、これらのサブスクリプションのいずれかが必要です。

### <a name="permissions"></a>アクセス許可

UI の分類子にアクセスするには、次のようにします。 

- グローバル管理者は、カスタム分類子を作成するためにテナントを選択する必要があります。
- 分類子を教育するには、コンプライアンス管理者またはデータ調査の役割が必要です。

次のシナリオでは、分類子を使用するために、以下のアクセス許可を持つアカウントが必要になります。

- 保持ラベルポリシーシナリオ: レコード管理および保持管理の役割 
- 機密ラベルポリシーのシナリオ: セキュリティ管理者、コンプライアンス管理者、コンプライアンスデータ管理者
- コミュニケーションコンプライアンスポリシーのシナリオ: Insider リスク管理管理者、監督レビュー管理者 

> [!IMPORTANT]
> 既定では、カスタムの分類子を作成したユーザーのみが、その分類子によって行われた予測を教育およびレビューすることができます。

## <a name="prepare-for-a-custom-trainable-classifier"></a>カスタム trainable 分類子の準備 

事前に説明する前に、カスタムの trainable 分類子を作成するために必要なことを理解しておくと役立ちます。 

### <a name="timeline"></a>タイムライン

このタイムラインには、trainable 分類子の展開サンプルが反映されています。

![trainable-クラシファイア-タイムライン](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Trainable 分類子では、最初にオプトインが必要です。 Microsoft 365 で組織のコンテンツのベースライン評価を完了するには、12日間かかります。 グローバル管理者に連絡して、オプトインプロセスを開始します。

### <a name="overall-workflow"></a>全体的なワークフロー

カスタム trainable 分類子を作成する全体的なワークフローの詳細については、「 [customer trainable 分類子を作成するためのプロセスフロー](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)」を参照してください。

### <a name="seed-content"></a>Seed コンテンツ

Trainable 分類子を個別に特定のカテゴリのコンテンツにする必要がある場合は、まず、カテゴリに含まれるコンテンツの種類の多くのサンプルを提示する必要があります。 Trainable 分類子へのこのサンプルのフィードは、 *シード* と呼ばれます。 Seed コンテンツは人間が選択し、コンテンツのカテゴリを表すことを判断します。

> [!TIP]
> 少なくとも50の正のサンプルと最大500が必要です。 Trainable 分類子は、最新の作成済みサンプル (ファイル作成日時スタンプ) を500まで処理します。 指定したサンプル数が多いほど、分類子が実行する予測がより正確になります。

### <a name="testing-content"></a>コンテンツのテスト

Trainable クラシファイアが、予測モデルを構築するのに十分な正のサンプルを処理したら、その分類をテストして、分類項目に一致する項目と、それに一致しないアイテムを正しく区別できるかどうかを確認する必要があります。 これを行うには、多くの場合、より大きなユーザー選択コンテンツセットを選択します。これは、カテゴリとサンプルに含まれるサンプルで構成されています。 最初に提供した最初のシードデータとは異なるデータを使用してテストする必要があります。 それらを処理した後、結果を手動で調べ、各予測が正しいかどうか、または確認できないかどうかを確認します。 Trainable 分類子は、このフィードバックを使用して予測モデルを改善します。

> [!TIP]
> 最良の結果を得るには、正と負の一致が均等に分配されたテストサンプルセットに、少なくとも200のアイテムが含まれている必要があります。

## <a name="how-to-create-a-trainable-classifier"></a>Trainable 分類子を作成する方法

1. 50-500 の seed コンテンツ項目の間で収集します。 これらは、trainable 分類子が分類カテゴリに含まれるコンテンツの種類を厳密に表すサンプルである必要があります。 サポートされているファイルの種類については、「 [SharePoint Server での既定のクロール対象ファイル名拡張子および解析済みファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 」を参照してください。

   > [!IMPORTANT]
   > シードおよびテストサンプルアイテムは、暗号化する必要があり、英語である必要があります。

   > [!IMPORTANT]
   > Seed セット内のアイテムがカテゴリの **強力な** 例であることを確認してください。 Trainable 分類子は、最初にそのモデルをシードしたものに基づいてモデルを作成します。 この分類子は、すべてのシードサンプルが強力なものであることを前提としていますが、サンプルがカテゴリに対して弱いまたは否定的一致であるかどうかを知ることはできません。

2. Seed *コンテンツを保持する* 専用の SharePoint Online フォルダーにシードコンテンツを配置します。 サイト、ライブラリ、およびフォルダーの URL をメモしておきます。

   > [!TIP]
   > Seed データ用の新しいサイトとフォルダーを作成する場合は、そのシードデータを使用する trainable 分類子を作成する前に、少なくとも1時間、その場所にインデックスを作成するようにしてください。

3. コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター** または **microsoft 365 セキュリティセンター** の  >  **データ分類** を開きます。

4. [ **Trainable 分類子** ] タブを選択します。

5. [ **Create trainable クラシファイア** ] を選択します。

6. `Name` `Description` この trainable クラシファイアで識別するアイテムのカテゴリのフィールドとフィールドに適切な値を入力します。

7. 手順2で、seed コンテンツサイトの SharePoint Online サイト、ライブラリ、およびフォルダーの URL を選択します。 [] を選択 `Add` します。

8. 設定を確認し、[] を選択し `Create trainable classifier` ます。

9. 24時間以内、trainable クラシファイアはシードデータを処理し、予測モデルを作成します。 分類子の状態は、 `In progress` シードデータを処理している間になります。 分類子がシードデータの処理を完了すると、状態はに変わり `Need test items` ます。

10. 分類子を選択することによって、[詳細] ページを表示できるようになりました。

    > [!div class="mx-imgBorder"]
    > ![テストの準備が整った trainable クラシファイア](../media/classifier-trainable-ready-to-test-detail.png)

11. 最良の結果を得るために、少なくとも200のテストコンテンツ項目 (1万 max) を収集します。 これらのアイテムは、強力な陽性、強力なネガ、およびそれらの性質上の明確にわかりにくい項目を組み合わせたものにする必要があります。 サポートされているファイルの種類については、「 [SharePoint Server での既定のクロール対象ファイル名拡張子および解析済みファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) 」を参照してください。

    > [!IMPORTANT]
    > サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。

12. テストコンテンツ *のみ* を保持する専用の SharePoint Online フォルダーにテストコンテンツを配置します。 SharePoint Online のサイト、ライブラリ、およびフォルダーの URL をメモしておきます。

    > [!TIP]
    > テストデータ用に新しいサイトとフォルダーを作成する場合は、そのシードデータを使用する trainable 分類子を作成する前に、少なくとも1時間、その場所にインデックスを設定するようにしてください。

13. [] を選択 `Add items to test` します。

14. 手順12からテストコンテンツサイトの SharePoint Online サイト、ライブラリ、およびフォルダーの URL を選びます。 [] を選択 `Add` します。

15. を選択してウィザードを終了し `Done` ます。 Trainable の分類子は、テストファイルの処理に最大1時間かかります。

16. Trainable クラシファイアがテストファイルの処理を完了すると、詳細ページの状態はに変わり `Ready to review` ます。 テストサンプルサイズを増やす必要がある場合は、 `Add items to test` trainable クラシファイアが追加のアイテムを処理することを選択して許可します。

    > [!div class="mx-imgBorder"]
    > ![スクリーンショットを確認する準備ができました](../media/classifier-trainable-ready-to-review-detail.png)

17. [ `Tested items to review` タブ] を選択してアイテムを確認します。

18. Microsoft 365 は、一度に30個のアイテムを提示します。 それらを確認し、 `We predict this item is "Relevant". Do you agree?` ボックスで、またはのどちらかを選択し `Yes` `No` `Not sure, skip to next item` ます。 モデル精度は30アイテムごとに自動的に更新されます。

    > [!div class="mx-imgBorder"]
    > ![[アイテムの確認] ボックス](../media/classifier-trainable-review-detail.png)

19. *少なく* とも200のアイテムを確認します。 精度スコアが安定すると、[ **発行** ] オプションが使用可能になり、分類子の状態が表示され `Ready to use` ます。

    > [!div class="mx-imgBorder"]
    > ![精度スコアと発行の準備ができている](../media/classifier-trainable-review-ready-to-publish.png)

20. 分類子を発行します。

21. 公開されると、分類子は、[条件に基づいて、条件に基づいて [自動適用の保持ラベルポリシー](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) ] を使用して[Office の自動ラベル](apply-sensitivity-label-automatically.md)付けの条件として使用できるようになり[ます。](communication-compliance.md)
