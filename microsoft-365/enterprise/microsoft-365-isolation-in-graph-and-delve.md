---
title: Microsoft 365Microsoft Graph および Delve
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
description: この記事では、テナントの分離Microsoft 365、およびテナントのOffice Graphについて説明Delve。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464087"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365Microsoft Graph および Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Microsoft サーバーでのテナントの分離Graph

[Microsoft Graph](https://developer.microsoft.com/graph)は、Exchange Online、SharePoint Online、Yammer、Skype for Business、Azure Active Directory などの Microsoft 365 サービス、および他の Microsoft サービス サービスやサードパーティ サービスなどの外部サービスでのアクティビティをモデル化します。 Microsoft Graphコンポーネントは、全体で使用Microsoft 365。 Microsoft Graphは、コンテンツとアクティビティのコレクション、およびコンテンツ スイート全体で発生するコンテンツとアクティビティのOfficeします。 高度な機械学習技術を使用して、関連するコンテンツ、会話、周囲の人々にユーザーを接続します。 たとえば、SharePoint Online のテナント インデックスには、Delve クエリの処理に使用される Microsoft Graph インデックス、SharePoint Online の分析処理エンジンを使用してシグナルを格納し、分析情報を計算し、Exchange Online はテナント分析への入力として各ユーザーの受信者キャッシュを計算します。

Microsoft Graphには、ユーザーやドキュメントなどのエンタープライズ オブジェクトに関する情報、およびこれらのオブジェクト間の関係と相互作用が含まれます。 関係とやり取りは、*エッジ* で表現されます。 Microsoft Graphはテナントによってセグメント化され、エッジは同じテナント内のノード間でのみ存在できます。 ノード *は* 、統一リソース識別子 (URI)、ノードの種類、アクセス制御リスト、およびメタデータとエッジを含むファセットのセットを持つ *エンティティ* です。 各ノードにはメタデータとエッジが関連付け、共通ナレッジ モデルのようにファセットに配置されます。 *メタデータ* は、Microsoft データベース内の検索、フィルター処理、または分析に使用できるノードに格納されている名前付きプロパティGraph。 ファセット *は* 、ノード上のメタデータとエッジの論理コレクションです。 各ファセットは、ノードの 1 つの側面を表します。 

Microsoft Graphは、すべてのデータを 1 つのリポジトリに取り込む必要があります。むしろ、他の場所に住んでいるデータに関するメタデータと関係を格納します。 Microsoft Graphは、いくつかのデータ ストアと処理コンポーネントで構成されます。

- テナント Graphは、効率的な分析のために最適化されたバルク ストレージを提供します。
- アクティブ コンテンツ キャッシュは、アクティブ なノードとエッジにすばやくランダムにアクセスし、ユーザー エクスペリエンスを向上します。
- 入力ルーターは、テナント グラフに対する変更の内部および外部のコンポーネントに通知します。

各ワークロード内の分析は、テナント全体の計算に関連する分析情報を除外し、テナント グラフにプッシュします。 テナントのテナント分析の理由は、テナント内のすべてのアクティビティで、動作のパターンに関する分析情報を生成します。 たとえば、Exchange Onlineユーザーのメールボックスを効率的に理由付けする分析を使用して、各ユーザーの受信者キャッシュを計算します。 これらのユーザーごとの分析では、各ユーザーに *RecipientCache エッジ* のセットが生成され、テナント グラフにプッシュされます。 これにより、分析処理の多くが可能な限りソース データに近い値になります。

## <a name="tenant-isolation-in-delve"></a>テナントの分離 (Delve

前述したように、Microsoft Graph は、ユーザーが企業内の現在のアクティビティを発見して共同作業するのに役立つエクスペリエンスを提供し、ワークロード全体および Microsoft 365 を超えてコンテンツとアクティビティを分析するためのエンティティ中心のプラットフォームを提供します。 Delveは、Microsoft のサービスを利用した最初のエクスペリエンスGraph。
Delveは、microsoft Microsoft 365を介して、Microsoft 365およびYammer Enterpriseユーザー Microsoft 365コンテンツをGraph。 Web エクスペリエンスでは、データが異なるボードとして表示され、それぞれに特定のトピック (私の周りの傾向や変更者など)*が表示されます*。 各ボードは、概要テキストとドキュメントの画像を表示する複数のドキュメント カードで構成されます。 このカードを使用すると、ユーザーはドキュメントを開く、またはドキュメントのYammerページを開くなどできます。 Microsoft 365 テナントには、このユーザーに最も関連性の高いドキュメントを表示するページと、そのユーザーと対話するために Exchange Online または Skype for Business を呼び出すアイコンがあります。 このDelveは Microsoft Graph API に基づくため、その API のテナント ベースの分離によってバインドされます。