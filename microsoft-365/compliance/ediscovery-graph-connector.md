---
title: Microsoft Purview eDiscovery Graph コネクタ
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
- m365solution-overview
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
description: Microsoft 365 のお客様は、エンタープライズ検索用に取り込まれたコンテンツに対して電子情報開示検索を実行できます。
ms.openlocfilehash: df6f948f60b74da6868f4f3877ee3a39e97c2a46
ms.sourcegitcommit: 180da7b39cfda7263a89bda0c3b93d9d6e55f3c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66995172"
---
# <a name="use-graph-connectors-with-ediscovery-premium"></a>電子情報開示で Graph コネクタを使用する (Premium)

Microsoft 365 のお客様は、エンタープライズ検索用に取り込まれたコンテンツに対して電子情報開示検索を実行できます。 これにより、組織は、Microsoft コンプライアンス ソリューションの純粋な範囲内に収めることで、外部コンテンツ ソースに対するコンプライアンス体制を改善するのに役立ちます。

Graph コネクタを使用すると、外部データ ソースのコンテンツをMicrosoft Purview eDiscovery Premium ソリューションで使用できるようになります。 組織の Graph コネクタの確立の詳細については、「 [Microsoft Search の Microsoft Graph コネクタの概要](/microsoftsearch/connectors-overview)」を参照してください。

## <a name="add-graph-connector-as-a-data-source-within-a-case"></a>ケース内のデータ ソースとして Graph Connector を追加する

組織に対して Graph コネクタが確立され、電子情報開示が有効になると、Graph Connector データ ソースをケースに追加するオプションは、Microsoft 365 以外の場所で使用できるようになります。 ケースに含めるために電子情報開示マネージャーが使用できるのは、確立され、有効になっているコネクタだけです。

:::image type="content" source="../media/ediscovery-graph-new.png" alt-text="データ ソースとして [Graph] を選択できます。":::

## <a name="collect-graph-connectors-content"></a>Graph Connectors コンテンツを収集する

Graph Connectors コンテンツをデータ ソースとして追加すると、このコンテンツは検索と収集に使用できるようになります。 収集ウィザードで、グラフ コネクタコンテンツを非親権データ ソースとして選択し、日付範囲、キーワードなどの条件を使用して、接続されたコンテンツ全体を検索して目的のコンテンツのみを収集します。 ウィザードが完了すると、検索条件へのヒットを含むコンテンツの量の見積もりを取得し、コレクションをレビュー セットにコミットします。  

## <a name="review-content"></a>コンテンツを確認する

電子情報開示マネージャーは、レビュー セットに収集されると、Graph Connectors からコンテンツを確認してコンテンツの詳細を理解し、その情報が重要でケースに関連しているかどうかを評価することができます。  

## <a name="export-content"></a>コンテンツのエクスポート

レビューに収集されたコンテンツが正しいコンテンツであることが検証されると、このコンテンツはレビュー セットから直接エクスポートできるようになります。 エクスポート オプションを選択し、レビュー セットからエクスポートするコネクタ コンテンツのエクスポート ジョブを送信します。
