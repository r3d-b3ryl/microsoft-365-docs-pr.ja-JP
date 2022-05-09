---
title: インシデント キューを表示および整理する
ms.reviewer: ''
description: インシデントの一覧を参照し、フィルターを適用してリストを制限し、より焦点を絞ったビューを取得する方法について説明します。
keywords: 表示、整理、インシデント、集計、調査、キュー、ttp
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: df5cbf5297a17dafb80a93ed49c7f7d81bc49d68
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474379"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Microsoft Defender for Endpoint インシデント キューを表示して整理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

**インシデント キューには、** ネットワーク内のデバイスからフラグが設定されたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。

既定では、過去 30 日間に発生したインシデントがキューに表示され、最新のインシデントが一覧の一番上に表示され、最新のインシデントが最初に表示されます。

インシデント キュー ビューをカスタマイズするには、いくつかのオプションを選択できます。 

上部のナビゲーションでは、次の操作を行うことができます。
- 列を追加または削除する列をカスタマイズする 
- ページごとに表示するアイテムの数を変更する
- ページごとに表示する項目を選択する
- 割り当てるインシデントを一括選択する 
- ページ間を移動する
- フィルターの適用

:::image type="content" source="images/atp-incident-queue.png" alt-text="インシデント キュー" lightbox="images/atp-incident-queue.png":::

## <a name="sort-and-filter-the-incidents-queue"></a>インシデント キューを並べ替え、フィルター処理する
次のフィルターを適用して、インシデントの一覧を制限し、より焦点を絞ったビューを取得できます。

### <a name="severity"></a>重要度

インシデントの重大度 | 説明
:---|:---
高 </br>(赤) | 多くの場合、高度な永続的な脅威 (APT) に関連付けられている脅威。 これらのインシデントは、デバイスに与える可能性のある損害の重大度に起因するリスクが高いことを示しています。
中 </br>(オレンジ) | 異常なレジストリの変更、疑わしいファイルの実行、攻撃ステージの典型的な観察された動作など、組織内ではほとんど観察されない脅威。
低 </br>(黄色) | 組織を対象とする高度な脅威を示すとは限らない、一般的なマルウェアやハッキング ツールに関連する脅威。
情報 </br>(灰色) | 情報インシデントはネットワークにとって有害であると見なされないかもしれませんが、追跡することをお勧めします。

## <a name="assigned-to"></a>割り当て先
ユーザー割り当てられているものまたは自分に割り当てられているものを選択することで、リストをフィルター処理することを選択できます。

### <a name="category"></a>カテゴリ
インシデントは、サイバーセキュリティのキル チェーンが存在するステージの説明に基づいて分類されます。 このビューは、脅威アナリストがコンテキストに基づいてデプロイする優先度、緊急度、対応する対応戦略を決定するのに役立ちます。

### <a name="status"></a>状態
状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。

### <a name="data-sensitivity"></a>データの機密性
秘密度ラベルを含むインシデントを表示するには、このフィルターを使用します。

## <a name="incident-naming"></a>インシデントの名前付け

インシデントのスコープを一目で把握するために、インシデント名は、影響を受けるエンドポイントの数、影響を受けたユーザー、検出ソース、カテゴリなどのアラート属性に基づいて自動的に生成されます。

たとえば、 *複数のソースによって報告された複数のエンドポイントに対する多段階インシデント。*

> [!NOTE]
> 自動インシデントの名前付けのロールアウト前に存在していたインシデントは、その名前を保持します。


## <a name="see-also"></a>関連項目
- [インシデント キュー](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)

