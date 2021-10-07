---
title: 組織の Microsoft 製品 NPS フィードバックと分析情報
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
description: エンド ユーザーの Net プロモーター スコア (NPS) を使用して、Microsoft 製品とサービスに対するユーザーの気持ちを確認します。
ms.openlocfilehash: afde0abf85cca682a5cda3206fa78d24cafc8cb8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168124"
---
# <a name="microsoft-product-nps-feedback-and-insights-for-your-organization"></a>組織の Microsoft 製品 NPS フィードバックと分析情報

組織の管理者Microsoft 365、組織内のユーザーによって生成された分析情報とデータを確認できます。

Net Promoter Score (NPS) アンケートは、ユーザーからのフィードバックを収集し、ユーザーが友人や同僚に製品やサービスを勧める可能性を測定します。 このデータを組織レベルで使用して、導入とロールアウトの戦略を決定できます。

Microsoft は、エンド ユーザーからの NPS アンケートとフィードバックを使用して、Microsoft 製品およびサービスに関する分析情報を提供します。 この情報は、組織内のエンド ユーザーが使用している製品とサービスを確認するのに役立つだけでなく、問題を特定して迅速に解決するのに役立ちます。 この情報を使用すると、次の機能を使用できます。

<!--See location of users who have submitted feedback-->
- 使用しているオペレーティング システムまたはプラットフォームを確認する
- キーワードを使用して製品、プラットフォーム、検索をフィルター処理する
- 上位の製品と問題に関するエンド ユーザーのコメントを表示する
- フィードバックとアンケート情報を CSV ファイルにエクスポートして詳細な調査を行う

## <a name="before-you-begin"></a>はじめに

アンケート レポートを表示および読 [み](../add-users/about-admin-roles.md) 取る管理者である必要があります。 アンケート レポートを表示および読み取りするには、組織でフィードバックアンケートを有効にしている必要があります。 詳細については、「 [組織の Microsoft フィードバックの管理」](manage-feedback-ms-org.md) を参照してください。

## <a name="survey-insights"></a>アンケートの分析情報

1. 管理センターで、[正常性製品 **のフィードバック**  >    >  **NPS アンケートの分析情報] に移動します**。
2. **[NPS アンケートの分析** 情報] ページで、ページを移動して、組織の NPS に関連するアンケート分析情報を表示します。

:::image type="content" source="../../media/prosight-product-feedback.png" alt-text="スクリーンショット: nps Microsoft 365分析情報を確認する":::

### <a name="chart-information"></a>グラフ情報

**フィードバックの総数** は、エンド ユーザーが送信した NPS フィードバック応答の総数を示し、コメントとコメントのない NPS フィードバックを含む。

**コメント** は、コメントを含むエンド ユーザーが送信した NPS フィードバック応答の総数を示します。

**アプリケーション別のボリュームは** 、アプリケーション別の NPS フィードバック応答ボリュームの総数を示します。

**月別のフィードバック量は** 、NPS フィードバック応答の月別の総数を示します。

:::image type="content" source="../../media/prosight-charts-area.png" alt-text="スクリーンショット: Microsoft 365分析情報":::

### <a name="top-topic-filters"></a>トップ トピック フィルター

トピックは、NPS アンケートフィードバックのコメント、語句、および動詞を分析するのに役立つ機械学習モデルであり、最も一般的なテーマへのアクセスをトップ レベルで提供します。 トップ トピック フィルターには、最も多くの逐語的なフィードバックを含む上位 5 つのトピックが表示されます。

:::image type="content" source="../../media/prosight-top-topic-filters-2.png" alt-text="スクリーンショット: NPS アンケート データのトップ トピック フィルター":::

> [!NOTE]
> インテリジェント なトピックは、主題の専門家とのパートナーシップで設定された最小品質のバーを満たした後にのみ公開されます。 精度と呼び出しのメトリックは、同じ値を決定するために使用されます。

**Verbatim の精度** は、このトピックで分類された動詞が正しい可能性を示します。

**Verbatim Recall** は、このトピックに関連する動詞がこのトピックで分類される可能性を示します。

現在利用可能なトピックは次のとおりです。

**ナビゲーションには** 、アプリのナビゲーションと使いやすさに関する顧客のコメントが含まれます。

- Verbatim Precision- 93%
- Verbatim Recall - 98%

**コラボレーションとは** 、ユーザーが Microsoft アプリを使用して共同作業を行う簡単な方法を指します。

- Verbatim Precision- 92%
- Verbatim Recall-91%

**値** は、価格設定や支払い設定などのトピックに関する顧客の認識を表します。

- Verbatim Precision- 86%
- Verbatim Recall- 100%

**信頼性には、** アプリとシステムの動作に関する顧客のコメントが含まれるので、予期しない終了が発生します。

- Verbatim Precision- 97%
- Verbatim Recall- 94%

**パフォーマンス** とは、Microsoft 製品の使用中にユーザーが経験する操作の知覚速度に関連する問題に対応する顧客のコメントを指します。 このトピックでは、クラッシュの領域や、より広範な信頼性の問題については説明します。

- Verbatim Precision- 92%
- Verbatim Recall - 98%

**ユーザー教育の** フィードバックには、ヘルプ ドキュメント、チュートリアル、ガイド、その他の製品内学習コンテンツやオンライン学習コンテンツに関する顧客のコメントが含まれます。

- Verbatim Precision- 83%
- Verbatim Recall- 87%

**複雑とは** 、アプリが複雑で使いやすいと感じるかどうかに関する顧客のフィードバックを指します。

- Verbatim Precision- 92%
- Verbatim Recall - 89%

**一称賛** は、肯定的な感情を持ち、他のトピックに収まらない顧客のコメントを指します。

- Verbatim Precision- 93%
- Verbatim Recall - 98%

### <a name="export-to-csv-and-search"></a>CSV と検索にエクスポートする

CSV にエクスポート機能を使用して、生データをエクスポートして詳細な分析を行います。

> [!NOTE]
> 生データには、NPS 以外のフィードバックを含むすべての種類のフィードバックが含まれます。

### <a name="filters"></a>フィルター

チャネル、製品 **、** プラットフォーム、**フィードバック****の種類** で **フィルター処理できます**。

**チャネル** は、組織がユーザーの機能更新プログラムを取得する頻度を選択Office。 詳細については、「更新プログラム[の更新プログラム チャネルの概要」を参照Microsoft 365 Apps。](/deployoffice/overview-update-channels) このフィルターを使用すると、特定のチャネルでユーザーから送信されたフィードバックにフィルターを適用できます。

フィードバックは、Android、iOS、Mac、およびプラットフォームなど、さまざまなプラットフォームWindows。  このフィルターを使用すると、送信されたプラットフォームに基づいてフィードバックをフィルター処理できます。

ビジネス製品のMicrosoft 365の **大部分は**、このフィルターの下に表示されます。 このフィルターを使用して、フィードバックが送信された製品を選択します。

フィードバック **の種類** (NPS フィードバックの種類にのみ設定) を使用して、収集したフィードバックをフィルター処理します。

:::image type="content" source="../../media/prosight-filters.png" alt-text="スクリーンショット: NPS Microsoft 365インサイト フィルターの詳細":::
