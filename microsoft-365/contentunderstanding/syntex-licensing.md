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
ms.openlocfilehash: 2e252ba496d89d388b67330bd1106b5f82c9aeb2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198555"
---
# <a name="licensing-for-sharepoint-syntex"></a>SharePoint Syntex のライセンス

SharePoint Syntex を使用するには、組織に SharePoint Syntex のサブスクリプションが必要であり、各 Syntex ユーザーにライセンスが必要です。 将来 SharePoint Syntex サブスクリプションを解約すると (または試用期間が終了すると)、ユーザーはドキュメントの理解またはフォーム処理モデルを作成、公開、または実行できなくなります。 さらに、用語ストア レポート、SKOS 分類インポート、およびコンテンツの種類のプッシュは使用できなくなります。 モデル、コンテンツ、メタデータが削除されたり、サイトのアクセス許可が変更されたりすることはありません。
 
> [!NOTE] 
> SharePoint Syntex はアドオン ライセンスであり、ユーザーは Microsoft 365 のライセンスも持っている必要があります。
 
## <a name="tasks-requiring-a-license"></a>ライセンスが必要なタスク
 
次のタスクを実行するユーザーには、SharePoint Syntex ライセンスが必要です。
 
- 文書理解モデルをライブラリに適用する。(ライセンスのないユーザーは、コンテンツ センターへのアクセスを許可され、そこで文書理解モデルを作成できますが、それをドキュメント ライブラリに適用することはできません。)
- ライブラリのエントリ ポイントを介してフォーム処理モデルを作成する
- 文書理解またはフォーム処理モデルが適用されているライブラリへコンテンツをアップロードする
- 文書理解モデルをオンデマンドで実行する
- 文書理解またはフォーム処理モデルを使用してファイルから抽出されたメタデータを表示する。 (ユーザーは、ファイルの移動先に関係なく、処理されたファイルに関連付けられたメタデータにアクセスして使用するためのライセンスが必要です。)
- プレミアム分類サービスを使用します。(プレミアム分類サービスは、SKOS ベースの用語セットのインポート、エンタープライズ コンテンツ タイプのハブ関連サイトへのプッシュ、および用語ストア レポートで構成されます。)

ライセンスのないユーザーは、コンテンツ センターへのアクセスを許可され、そこで文書理解モデルを作成できますが、それをドキュメント ライブラリに適用することはできません。
 
## <a name="cost-of-running-models"></a>モデルの実行コスト
 
文書理解モデルの実行コストは、SharePoint Syntex ライセンスのコストに含まれています。 ただし、フォーム処理モデルは、トレーニングとランタイム処理の両方に AI ビルダーの容量を使用します。 AI ビルダーを使用する Power Apps 環境に容量を割り当てる必要があります。
 
組織に300以上のSharePoint Syntex用 SharePoint Syntexライセンスがある場合は、100万のAI Builder クレジットが割り当てられます。 この容量は、300 以上のライセンスを維持している場合、毎月更新されます。 (未使用のクレジットは月ごとに繰り越されません。) ライセンス数が 300 未満の場合、フォーム処理を使用するには、AI ビルダークレジットを購入する必要があります。
 
Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。

カスタム Power Platform 環境を使用する場合は、 [その環境にクレジット割り当てる](/power-platform/admin/capacity-add-on)必要があります。

「[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity)」 に移動して、クレジットと使用状況を確認します。
  
## <a name="additional-term-store-features"></a>追加の用語ストア機能
 
SharePoint Syntex のサブスクリプションには、次の追加の用語ストア機能があります。
 
- SKOS ベースの用語セットのインポート
- エンタープライズ コンテンツの種類をハブ サイトにプッシュします。ハブ サイトは、それらを関連サイトや新しく作成されたリストまたはライブラリにも追加します。
- 公開された用語セットとテナント全体での使用に関する分析情報を提供する用語ストア レポート


## <a name="see-also"></a>関連項目

[Microsoft Power Platform のライセンスの概要](/power-platform/admin/pricing-billing-skus)

[Power Apps と Power Automate のライセンスに関する FAQ](/power-platform/admin/powerapps-flow-licensing-faq)
