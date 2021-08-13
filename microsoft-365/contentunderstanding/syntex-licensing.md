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
localization_priority: Priority
description: SharePoint Syntex のライセンスの詳細
ms.openlocfilehash: 08c3b078feb96f988fdf267246fb68356860677fbb00421b5322e9f6aa1904c2
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824276"
---
# <a name="licensing-for-sharepoint-syntex"></a>SharePoint Syntex のライセンス

SharePoint Syntex を使用するには、組織に SharePoint Syntex のサブスクリプションが必要であり、各 Syntex ユーザーにライセンスが必要です。 将来 SharePoint Syntex サブスクリプションを解約すると (または試用期間が終了すると)、ユーザーはドキュメントの理解またはフォーム処理モデルを作成、公開、または実行できなくなります。 さらに、用語ストア レポート、SKOS 分類インポート、およびコンテンツの種類のプッシュは使用できなくなります。 モデル、コンテンツ、メタデータが削除されたり、サイトのアクセス許可が変更されたりすることはありません。
 
## <a name="tasks-requiring-a-license"></a>ライセンスが必要なタスク
 
次のタスクを実行するユーザーには、SharePoint Syntex ライセンスが必要です。
 
- 文書理解モデルが関連付けられているドキュメント ライブラリにコンテンツをアップロードする
- 文書理解モデルを手動で実行する
- SharePoint ライブラリのエントリ ポイントを介してフォーム処理モデルを作成する
- フォーム処理モデルが適用されているライブラリへコンテンツをアップロードする
- 文書理解またはフォーム処理モデルを使用してファイルから抽出されたメタデータを表示する
 
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
