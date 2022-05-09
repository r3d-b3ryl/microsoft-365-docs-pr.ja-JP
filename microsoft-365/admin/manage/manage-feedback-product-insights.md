---
title: 組織に対する Microsoft 製品 NPS のフィードバックと分析情報
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: エンド ユーザーの Net プロモータスコア (NPS) を使用して、Microsoft 製品とサービスに対するユーザーの考え方を確認します。
ms.openlocfilehash: ec261553a5713d9e12205cbf4c88611a128bc48b
ms.sourcegitcommit: b3f5fe84a319741583954ef8ff2ec9ec6da69bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217356"
---
# <a name="microsoft-product-nps-feedback-and-insights-for-your-organization"></a>組織に対する Microsoft 製品 NPS のフィードバックと分析情報

Microsoft 365組織の管理者は、Microsoft から送信された NPS 製品アンケートにアクセスして分析情報を取得できます。  

Net Framework Score (NPS) アンケートでは、ユーザーからのフィードバックを収集し、ユーザーが友人や同僚に製品やサービスを推奨すると言う可能性を測定します。 このデータは、組織で使用して、Microsoft 365製品とサービスの導入とロールアウトに関する戦略を決定できます。

Microsoft は、エンド ユーザーからの NPS アンケートとフィードバックを使用して、Microsoft 製品とサービスに関する分析情報を提供します。 この情報は、組織内のエンド ユーザーが使用している製品やサービスの情報を確認するのに役立ち、問題を特定して迅速に解決するのに役立ちます。 この情報を使用すると、次のことができます。

- ユーザーが議論しているトップ テーマへのアクセス。
- 幸せなユーザーを特定します。
- 不満なユーザーからの苦情に対処する。
- ユーザーが使用しているオペレーティング システムまたはプラットフォームを確認します。
- キーワードを使用して、製品、プラットフォーム、チャネル、または検索でフィルター処理します。
- 上位の製品と問題に関するエンド ユーザーのコメントを参照してください。
- フィードバックとアンケート情報を CSV ファイルにエクスポートします。

## <a name="before-you-begin"></a>開始する前に

アンケート レポートを表示および読み取るには [、管理者](../add-users/about-admin-roles.md) である必要があります。 組織では、アンケート レポートを表示および読み取るために、フィードバックアンケートを有効にする必要があります。 詳細については、 [組織の Microsoft フィードバックの管理](manage-feedback-ms-org.md) に関するページを参照してください。

> [!IMPORTANT]
> NPS アンケートの分析情報を表示するには、エンド ユーザーから少なくとも 30 件の NPS アンケート提出が必要です。

## <a name="nps-survey-insights"></a>NPS アンケートの分析情報

1. 管理センターで、**HealthProduct** >  **feedbackNPS** >  **アンケートの分析情報** に移動します。
2. **[NPS アンケートの分析情報**] ページでページに移動し、組織の NPS に関連するアンケート分析情報を表示します。

:::image type="content" source="../../media/product-feedback-main-page.png" alt-text="スクリーンショット: Net Score (NPS) メイン チャート":::

### <a name="top-topic-filters"></a>トップ トピック フィルター

ユーザーからのフィードバックから共通のテーマを特定しました。 次に、機械学習モデルを使用してデータ セットをトレーニングし、フィードバックを **上位トピック** に自動的に整理しました。 その後、最も多くの詳細なフィードバックを含む上位 5 つのトピックを特定できます。  

:::image type="content" source="../../media/top-topics-filter.png" alt-text="スクリーンショット: 最も詳細なフィードバックを含む上位 5 つのトピック":::

> [!NOTE]
> インテリジェントなトピックは、主題の専門家と連携して設定された最小品質バーを満たした後にのみ公開されます。 精度メトリックと呼び出しメトリックは、同じものを決定するために使用されます。

**Verbatim の有効桁数** は、このトピックで分類された逐語が正しい可能性が高いということです。

**Verbatim Recall** は、このトピックに関連する逐語的なことがこのトピックで分類される可能性が高いということです。

現在使用できるトピックは次のとおりです。

**Change Management** とは、更新プロセス、お気に入りのアプリの使用方法、デザインの変更など、更新されたエクスペリエンスに関連する顧客のコメントを指します。

- Verbatim Precision- 82%
- Verbatim Recall- 81%

**コラボレーション** とは、ユーザーが Microsoft アプリを使用して簡単に共同作業できる方法を指します。

- Verbatim Precision- 92%
- Verbatim Recall-91%

**複雑さは** 、アプリが複雑で使いやすいと感じるかどうかに関する顧客からのフィードバックを指します。

- Verbatim Precision- 92%
- Verbatim Recall- 89%

**一般的な称賛** は、肯定的な感情を持ち、他のトピックには当てはまらない顧客のコメントを指します。

- Verbatim Precision- 93%
- Verbatim Recall- 98%

**信頼性** には、アプリとシステムの動作に関する顧客のコメントが含まれており、予期しない終了が発生します。

- Verbatim Precision- 97%
- Verbatim Recall- 94%

**ナビゲーション** には、アプリのナビゲーションと使いやすさに関する顧客のコメントが含まれます。  

- Verbatim Precision- 93%
- Verbatim Recall- 98%

**パフォーマンス** とは、Microsoft 製品の使用時にユーザーが経験する操作の認識速度に関連する問題に対処する顧客のコメントを指します。 このトピックでは、クラッシュや広範な信頼性の問題の領域については説明しません。

- Verbatim Precision- 92%
- Verbatim Recall- 98%

**信頼性** とは、アプリとシステムの動作に関する顧客のコメントを指し、予期しない終了が発生します。  

Verbatim Precision- 97% Verbatim Recall- 94%

**ユーザー教育** は、ヘルプ ドキュメント、チュートリアル、ガイド、その他の製品内またはオンライン学習コンテンツに関するお客様のコメントで構成されています。

- Verbatim Precision- 83%
- Verbatim Recall- 87%

**値** は、価格や支払い設定などのトピックに関する顧客の認識を指します。  

- Verbatim Precision- 86%
- Verbatim Recall- 100%

### <a name="chart-information"></a>グラフ情報

**フィードバックの合計数** は、エンド ユーザーが送信した NPS フィードバック応答の合計数を示し、コメント付きの NPS フィードバックとコメントなしを含めます。

**コメントには、** コメントを含むエンド ユーザーによって送信された NPS フィードバック応答の合計数が表示されます。

**アプリケーションごとの応答量は、アプリケーションごとの** NPS フィードバック応答ボリュームの合計数を示します。

**プラットフォーム別の応答量** は、プラットフォームごとの NPS フィードバック応答ボリュームの合計数を示します。

**月ごとのフィードバック量** は、過去 12 か月間の NPS フィードバック応答量の合計数を示します。

:::image type="content" source="../../media/response-details.png" alt-text="スクリーンショット: 応答量と応答量 (月単位)":::

グラフは、NPS レーティングによって次のようにフィルター処理されます。

- デトラクターは、製品やサービスを推奨する可能性が低い、不満を持つ顧客です。
- パッシブは、サービスに満足しているが、製品やサービスを推奨するのに十分ではない顧客です。
- 主催者 - 忠実で、熱中し、製品やサービスをお勧めする可能性が高い幸せのお客様。

:::image type="content" source="../../media/how-likely-recommend.png" alt-text="スクリーンショット: 友人や同僚にアプリを推奨する可能性を示すグラフ":::

### <a name="export-to-csv-and-search"></a>CSV と検索にエクスポートする

CSV へのエクスポート機能を使用して、詳細な分析のために生データをエクスポートできます。 フィードバック領域に対応するコメント セクションでキーワードを検索できます。

:::image type="content" source="../../media/export-to-csv.png" alt-text="スクリーンショット: CSV にエクスポートする場合に選択する":::

> [!NOTE]
> 生データには、NPS 以外のフィードバックを含むすべての種類のフィードバックが含まれます。

### <a name="filters"></a>フィルター

**チャネル**、**製品**、**プラットフォーム**、**フィードバックの種類** でフィルター処理できます。

**チャネル** は、組織がOfficeの機能更新プログラムを取得する頻度を選択する方法です。 詳細については、「[Microsoft 365 Appsの更新チャネルの概要](/deployoffice/overview-update-channels)」を参照してください。 このフィルターを使用すると、特定のチャネルのユーザーから送信されたフィードバックにフィルターを適用できます。

フィードバックは、Android、iOS、Mac、Windowsなどのさまざまな **プラットフォーム** で送信できます。 このフィルターを使用すると、送信されたプラットフォームに基づいてフィードバックをフィルター処理できます。

ビジネス **向け製品** のMicrosoft 365の大部分は、このフィルターの下にあります。 このフィルターを使用して、フィードバックが送信された製品を選択します。

**フィードバックの種類** (NPS フィードバックの種類のみに設定) を使用して、収集したフィードバックをフィルター処理します。

:::image type="content" source="../../media/feedback-filters.png" alt-text="スクリーンショット: フィードバックの種類を示すグラフ":::

### <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

NPS アンケート分析情報ダッシュボードに関する考えと、それを改善する方法に関するアイデアを共有します。 製品とサービスのフィードバック セクションを使用します。 prosight@microsoft.com でメールを送信することもできます。
