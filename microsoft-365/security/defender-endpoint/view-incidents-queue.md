---
title: インシデント キューを表示および整理する
ms.reviewer: ''
description: インシデントの一覧を参照し、フィルターを適用してリストを制限し、より集中したビューを取得する方法について学習します。
keywords: ビュー、整理、インシデント、集計、調査、キュー、ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: e287f9a4713ba0ad96fd4b1b7f51e0fee948ec28
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207681"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Microsoft Defender for Endpoint インシデント キューを表示して整理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

インシデント **キューには、** ネットワーク内のデバイスからフラグが設定されたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。

既定では、キューには過去 30 日間に発生したインシデントが表示され、最新のインシデントがリストの上部に表示され、最新のインシデントを最初に確認できます。

インシデント キュー ビューをカスタマイズするために選択できるオプションは複数あります。 

上部のナビゲーションでは、次の操作を実行できます。
- 列をカスタマイズして列を追加または削除する 
- ページごとに表示するアイテムの数を変更する
- ページごとに表示するアイテムを選択する
- 割り当てるインシデントをバッチ選択する 
- ページ間の移動
- フィルターの適用

![インシデント キューのイメージ。](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>インシデント キューの並べ替えとフィルター処理
次のフィルターを適用して、インシデントの一覧を制限し、より集中したビューを取得できます。

### <a name="severity"></a>重要度

インシデントの重大度 | 説明
:---|:---
高い </br>(赤) | 多くの場合、高度な永続的な脅威 (APT) に関連付けられている脅威。 これらのインシデントは、デバイスに与える損害の重大度が高いリスクを示しています。
中 </br>(オレンジ) | 異常なレジストリ変更、疑わしいファイルの実行、攻撃段階の一般的な動作など、組織でまれに観察される脅威。
低い </br>(黄色) | 組織を標的とする高度な脅威を必ずしも示すわけではない、一般的なマルウェアやハッキング ツールに関連する脅威。
情報 </br>(灰色) | 情報インシデントはネットワークに悪影響を及ぼすとは見なされませんが、追跡しておいた方が良い場合があります。

## <a name="assigned-to"></a>割り当て先
ユーザー割り当てられているものまたは自分に割り当てられているものを選択することで、リストをフィルター処理することを選択できます。

### <a name="category"></a>カテゴリ
インシデントは、サイバーセキュリティキル チェーンが含むステージの説明に基づいて分類されます。 このビューは、脅威アナリストがコンテキストに基づいて展開する優先度、緊急性、対応する対応戦略を決定するのに役立ちます。

### <a name="status"></a>状態
状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。

### <a name="data-sensitivity"></a>データの機密性
このフィルターを使用して、感度ラベルを含むインシデントを表示します。

## <a name="incident-naming"></a>インシデントの名前付け

インシデントの範囲を一目で把握するために、インシデント名は、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいて自動的に生成されます。

たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

> [!NOTE]
> 自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前を保持します。


## <a name="see-also"></a>関連項目
- [インシデント キュー](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)

