---
title: Microsoft SharePoint Syntex の試用版を実行SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 組織のユーザー向け試用版パイロット プログラムを計画SharePoint Syntexする方法について学習します。
ms.openlocfilehash: 336a4c164f15035168d8842b05cdd4b5c566a97a
ms.sourcegitcommit: ef9cd046c47b340686a4f7bb123ea3b0a269769a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "58863679"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex の試用版を実行SharePoint Syntex

この記事では、試用版パイロット プログラムをセットアップして実行して、組織にSharePoint Syntexする方法について説明します。 また、試用版のベスト プラクティスも推奨します。

## <a name="sign-up-for-a-trial"></a>試用版にサインアップする

この試用版では、SharePoint Syntex 30 日間、300 人のユーザーにアクセスできます。

> [!NOTE]
> 最大 300 人のユーザーが試用版に含まれており、100 万の AI ビルダー クレジットが自動的に追加されます。 試用版を成功するには、300 人のユーザーを含める必要があります。

試用版は、次のいずれかのソースから取得できます。

- [[SharePoint Syntex] ページ](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- この[Microsoft 365 管理センター](https://admin.microsoft.com)
    1. [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。
    2. [課金購入 **サービス**  >  **] に移動します**。
    3. **[アドオン]** セクションまで下にスクロールします。
    4. [詳細] タイルSharePoint Syntex[詳細] を **選択します**。
    5. **[無料試用版を取得]** を選択します。
    6. 試用版を確認するには、残りのウィザードの手順に従います。

試用版をアクティブにするには、Microsoft 365管理者または課金管理者である必要があります。

### <a name="who-should-be-involved-in-a-trial"></a>Whoに関与する必要がある場合

|役割|アクティビティ|
|---|---|
|Microsoft 365管理者または請求管理者|試用版をアクティブ化し、ライセンスを割り当てる|
|Microsoft 365管理者または管理者SharePointする|コンテンツ センター SharePoint Syntex作成する方法を構成する|
|ビジネス ユーザー|モデルの構築とテスト|

### <a name="before-you-activate-a-trial"></a>試用版をアクティブにする前に

試用版を正常に計画SharePoint Syntex、次の要因を検討してください。

- 最も意味のあるテストは、"現実世界" のシナリオとデータで完了します。
- ライセンス認証は、テナントごとに 1 SharePoint Syntex 1 回のみ有効にできます。

テストテナントまたはデモ テナントを "ドライ ラン" として使用して、ライセンス認証手順と管理コントロールを実行できます。 ただし、おそらく、実稼働テナントのモデル構築を評価する方が最適です。

実稼働テナントの試用版の価値を最大限に高めるには、計画とビジネスエンゲージメントが不可欠です。 1 つ以上のビジネス 領域を使用して、ユーザーが対処できる可能性のある 3 ~ 6 の使用例を特定SharePoint Syntex。 これらの使用例は、次の必要があります。

- フォーム処理モデルまたはドキュメント理解モデルで解決できるシナリオを含める。
- 抽出されたメタデータの目的を明確に理解する。たとえば、書式設定やオートメーションを表示するには、次のPower Automate。 ドキュメントSharePoint Syntexメタデータの抽出に重点を置いて説明しますが、数値化する値は、このメタデータによって可能になります。
- 定義された一連のデータに基づく。たとえば、特定のサイトSharePointライブラリなどです。 一般的な誤解SharePoint Syntex、汎用モデルをすべての組織のコンテンツに適用できるという点です。 より正確なビューは、対象となる場所で特定のビジネス上の問題を解決するためにモデルが構築されているという考え方です。

これらのすべての使用例は、ユーザーに適していないSharePoint Syntex。 品質評価の目標は、すべてのシナリオに適合するSharePoint Syntex証明する必要があります。 代わりに、試用版は製品の価値をよりよく理解するのに役立ちます。

計画された各使用例について、関連するコンテンツまたはプロセスの専門家であるユーザーを特定します。 このモデルのSharePoint Syntexは、IT 専門家や開発者リソースではなく、コンテンツのドメイン専門家に焦点を当て、

## <a name="activate-a-trial"></a>試用版をアクティブ化する

試用版を開始する場合は、次の操作を行う必要があります。

- 関連するユーザーにライセンスを割り当てる。
- 追加[のセットアップを実行SharePoint Syntex。](set-up-content-understanding.md)
  - 追加のコンテンツ センター [を作成する場合があります](create-a-content-center.md)。

試用版をアクティブ化した後、モデルを作成し、ファイルを処理できます。 モデル作成 [のガイダンスを参照してください](create-a-content-center.md)。

## <a name="during-a-trial"></a>試用版中

試用期間は限られているので、SharePoint Syntex モデルがドキュメントを分類し、定義された使用例のメタデータを抽出できるかどうかに最初に焦点を当てるのが最善の方法です。 試用期間が終了した後、メタデータの悪用方法を評価できます。

## <a name="after-a-trial"></a>試用版の後

試用版の結果に基づいて、製品の生産使用に進むかどうかを決定SharePoint Syntex。

### <a name="proceed-to-production-use"></a>実稼働環境の使用に進む

サービスの継続性を確保するには、必要な数のライセンスを購入し、それらのライセンスをユーザーに割り当てる必要があります。 試用期間の最後に完全なライセンスを持ってない試用版ユーザーは、ライセンスを完全にSharePoint Syntex。

予想されるフォーム処理の使用を見積もり、予想される量の AI Builder クレジットを計画する必要がある場合があります。 ヘルプについては、「 [自分に合った AI ビルダーの容量を見積もる」を参照してください](https://powerapps.microsoft.com/ai-builder-calculator/)。

### <a name="dont-proceed-to-production-use"></a>実稼働環境での使用に進む

試用版に従ってライセンスを購入しない場合は、次の手順を実行します。

- 新しいモデルを作成できない。
- モデルを実行していたライブラリは、ファイルを自動的に分類したり、モデルを抽出したりしなくなりました。
- 以前に分類されたファイルや抽出されたメタデータは影響を受け取らない。
- コンテンツ センターとドキュメントを理解するモデルは自動的に削除されません。 今後ライセンスを購入する場合は、これらは引き続き使用できます。
- フォーム処理モデルは、既定の Power Platform 環境の Dataverse (以前は Common Data Service [CDS]) インスタンスに格納されます。 これらは、将来のライセンスや power プラットフォームSharePoint Syntex AI ビルダー機能で使用できます。

## <a name="see-also"></a>関連項目

[Microsoft SharePoint Syntex導入: 使い始める](adoption-getstarted.md)
