---
title: Microsoft GraphとDelveでのテナントの分離をMicrosoft 365する
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: この記事では、テナントの分離Microsoft 365 Office GraphとDelveでどのように機能するかについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464087"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft GraphとDelveでのテナントの分離をMicrosoft 365する

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft Graphのテナント分離

[Microsoft Graph](https://developer.microsoft.com/graph) では、Exchange Online、SharePoint Online、Yammer、Skype for Business、Azure Active Directoryなど、Microsoft 365 サービスでのアクティビティをモデルにしていますなど、外部サービス (他のMicrosoft サービスやサード パーティのサービスなど)。 Microsoft Graph コンポーネントは、Microsoft 365全体で使用されます。 Microsoft Graphは、コンテンツとアクティビティのコレクションと、Office スイート全体で発生するそれらの間のリレーションシップを表します。 高度な機械学習手法を使用して、関連するコンテンツ、会話、周囲のユーザーにユーザーを接続します。 たとえば、SharePoint Online のテナント インデックスには、Delveクエリの処理に使用される Microsoft Graph インデックスがあり、SharePoint Online の分析処理エンジンはシグナルの格納と分析情報の計算に使用され、Exchange Onlineはテナント分析への入力として各ユーザーの受信者キャッシュを計算します。

Microsoft Graphには、ユーザーやドキュメントなどのエンタープライズ オブジェクトに関する情報と、これらのオブジェクト間のリレーションシップと相互作用が含まれています。 関係とやり取りは、*エッジ* で表現されます。 Microsoft Graphは、同じテナント内の *ノード* 間にのみエッジが存在できるように、テナントによってセグメント化されます。 *ノード* は、Uniform Resource Identifier (URI)、ノードの種類、アクセス制御リスト、*およびメタデータ* とエッジを含むファセットのセットを持つエンティティです。 各ノードには、共通ナレッジ モデルのように *ファセット* に配置されたメタデータとエッジが関連付けられています。 *メタデータ* は、Microsoft Graph内の検索、フィルター処理、または分析に使用できるノードに格納されている名前付きプロパティです。 *ファセット* は、ノード上のメタデータとエッジの論理コレクションです。 各ファセットでは、ノードの 1 つの側面について説明します。 

Microsoft Graphは、すべてのデータを 1 つのリポジトリに取り込むのではなく、他の場所に存在するデータに関するメタデータとリレーションシップを格納します。 Microsoft Graphは、いくつかのデータ ストアと処理コンポーネントで構成されています。

- テナント Graph ストアは、効率的な分析用に最適化された一括ストレージを提供します。
- アクティブ コンテンツ キャッシュは、アクティブなノードとエッジにすばやくランダムにアクセスして、ユーザー エクスペリエンスを促進します。
- 入力ルーターは、テナント グラフへの変更の内部と外部のコンポーネントに通知します。

各ワークロード内の分析では、テナント全体の計算に関連する分析情報を推測し、それらをテナント グラフにプッシュします。 テナント分析は、テナント内のすべてのアクティビティに対して、動作パターンに関する分析情報を生成する理由です。 たとえば、Exchange Onlineは、各ユーザーのメールボックスを効率的に理由付けする分析を使用して、各ユーザーの受信者キャッシュを計算します。 これらのユーザーごとの分析では、各ユーザーに *対して RecipientCache エッジ* のセットが生成され、テナント グラフにプッシュされます。 これにより、可能な限り多くの分析処理がソース データの近くに保持されます。

## <a name="tenant-isolation-in-delve"></a>Delveのテナント分離

前述のように、Microsoft Graphは、企業内の現在のアクティビティを見つけて共同作業するのに役立つエクスペリエンスを提供し、分析のためのエンティティ中心のプラットフォームを提供し、ワークロード間やMicrosoft 365を超えてコンテンツやアクティビティを推論します。 Delveは、Microsoft Graphを搭載した最初のエクスペリエンスです。
Delveは、Microsoft Graphを介してコンテンツをMicrosoft 365およびYammer EnterpriseからユーザーにMicrosoft 365するMicrosoft 365 Web エクスペリエンスです。 Web エクスペリエンスでは、データが異なるボードとして表示され、それぞれに特定のトピックが表示されます 。たとえば、 *Trending around Me* や *Modified by Me* などです。 各ボードは、概要テキストとドキュメントの画像を表示する複数のドキュメント カードで構成されます。 このカードを使用すると、ユーザーはドキュメントやドキュメントのYammer ページを開くなどの操作を行うことができます。 このユーザーに最も関連するドキュメントを表示するMicrosoft 365 テナント内の各ユーザーのページと、そのユーザーと対話するためのExchange OnlineまたはSkype for Businessを呼び出すことができるアイコンがあります。 Delveは Microsoft Graph APIに基づいているため、その API のテナント ベースの分離によってバインドされます。