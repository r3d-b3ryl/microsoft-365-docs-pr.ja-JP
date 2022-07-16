---
title: SharePoint Syntex のライセンス
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: high
description: SharePoint Syntex のライセンスの詳細
ms.openlocfilehash: 86776af3184e44cb88f17e0164859f0ba0e2f334
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822271"
---
# <a name="licensing-for-sharepoint-syntex"></a>SharePoint Syntex のライセンス

SharePoint Syntexを使用するには、各 Syntex ユーザーがそのライセンスを取得している必要があります。 将来 SharePoint Syntex ライセンスを解約すると (または試用期間が終了すると)、ユーザーはドキュメントの理解またはフォーム処理モデルを作成、公開、または実行できなくなります。 さらに、用語ストア レポート、SKOS 分類インポート、およびコンテンツの種類のプッシュは使用できなくなります。 モデル、コンテンツ、メタデータが削除されたり、サイトのアクセス許可が変更されたりすることはありません。
 
> [!NOTE] 
> SharePoint Syntex はアドオン ライセンスであり、ユーザーにはMicrosoft 365のライセンスも必要です。
 
## <a name="tasks-requiring-a-license"></a>ライセンスが必要なタスク
 
次のタスクを実行するユーザーには、[SharePoint Syntex ライセンス](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex)が必要です。
 
- 文書理解モデルをライブラリに適用する。(ライセンスのないユーザーは、コンテンツ センターへのアクセスを許可され、そこで文書理解モデルを作成できますが、それをドキュメント ライブラリに適用することはできません。)
- ライブラリのエントリ ポイントを介してフォーム処理モデルを作成する
- 文書理解またはフォーム処理モデルが適用されているライブラリへコンテンツをアップロードする
- 文書理解モデルをオンデマンドで実行する
- プレミアム分類サービスを使用します。(プレミアム分類サービスは、SKOS ベースの用語セットのインポート、エンタープライズ コンテンツ タイプのハブ関連サイトへのプッシュ、および用語ストア レポートで構成されます。)

ライセンスのないユーザーは、コンテンツ センターへのアクセスを許可され、そこで文書理解モデルを作成できますが、それをドキュメント ライブラリに適用することはできません。
 
## <a name="cost-of-training-and-running-models"></a>モデルのトレーニングと実行のコスト
 
文書理解モデルのトレーニングと実行のコストは、SharePoint Syntex ライセンスのコストに含まれています。 ただし、フォーム処理モデルは、トレーニングとランタイム処理の両方に AI ビルダーの容量を使用します。 AI ビルダーを使用する Power Apps 環境に容量を割り当てる必要があります。

SharePoint Syntex ライセンスごとに、1 ライセンスあたり 3,500 AI Builder クレジットが割り当てられ、テナント レベルでプールされた 1 か月あたり、最大 100 万クレジットが割り当てられます。 この割り当ては、アクティブな SharePoint Syntex ライセンスごとに毎月更新されます。 (未使用のクレジットは、月ごとにロールオーバーされません。) 

Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。

カスタム Power Platform 環境を使用する場合は、 [その環境にクレジット割り当てる](/power-platform/admin/capacity-add-on)必要があります。

「[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity)」 に移動して、クレジットと使用状況を確認します。
  
## <a name="additional-term-store-features"></a>追加の用語ストア機能

組織に 1 つ以上の SharePoint Syntex ライセンスがあると、SharePoint 管理者向けに次の追加の用語ストア機能が有効になります。
 
- SKOS ベースの用語セットのインポート
- エンタープライズ コンテンツの種類をハブ サイトにプッシュします。ハブ サイトは、それらを関連サイトや新しく作成されたリストまたはライブラリにも追加します。
- 公開された用語セットとテナント全体での使用に関する分析情報を提供する用語ストア レポート


## <a name="see-also"></a>関連項目

[Microsoft Power Platform のライセンスの概要](/power-platform/admin/pricing-billing-skus)

[Power Apps と Power Automate のライセンスに関する FAQ](/power-platform/admin/powerapps-flow-licensing-faq)
