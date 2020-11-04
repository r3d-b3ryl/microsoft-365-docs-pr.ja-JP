---
title: Microsoft 365 Defender でインシデントの優先度を設定する
description: Microsoft 365 Defender でインシデントキューからインシデントの優先順位を設定する方法について説明します。
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、メール、インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877221"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でインシデントの優先度を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



Microsoft 365 Defender は、関連付け分析を適用し、さまざまな製品からのすべての関連アラートと調査を1つのインシデントに集約します。 また、microsoft 365 Defender は、Microsoft 365 Defender が不動産および製品スイート全体で使用するエンドツーエンドの可視性を与えられた悪意のあるアクティビティに対して、固有のアラートをトリガーします。 これにより、Microsoft 365 Defender narrates によって、より広範な攻撃ストーリーが実現されます。これにより、セキュリティ運用アナリストは、組織全体にわたる複雑な脅威を理解し、扱うことができます。


**インシデント キュー** には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。


![インシデント キューの画像](../../media/incidents-queue.png) 

既定では、Microsoft 365 セキュリティセンターのキューには過去30日間に表示されたインシデントが表示されます。 最新のインシデントは、リストの先頭に表示されるので、最初に確認できます。

インシデントキューは、インシデントまたは含まれているエンティティのさまざまな特性を表示できる、カスタマイズ可能な列を公開します。 これにより、処理するインシデントの優先度設定に関する情報による判断を行うことができます。

わかりやすくするために、自動インシデントの名前付けは、影響を受けるエンドポイント数、影響を受けたユーザー、検出ソース、カテゴリなどのアラート属性に基づいてインシデント名を生成します。 これにより、インシデントの範囲をすばやく理解することができます。

例: 複数の *ソースによって報告された複数のエンドポイントのマルチステージインシデント* 。

> [!NOTE]
> 自動インシデントの名前の公開前に存在していたインシデントは、名前が変更されません。

また、インシデントキューは、複数のフィルターオプションを公開すると、使用している環境内の既存のすべてのインシデントをさまざまな方法で実行したり、特定のシナリオや脅威に集中することができます。 インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。 

## <a name="available-filters"></a>利用可能なフィルター

### <a name="assigned-to"></a>割り当て先
自分に割り当てられた通知または自動化によって処理された通知を表示するように選択できます。

### <a name="categories"></a>Categories
表示される特定の戦術、手法、または攻撃コンポーネントに重点を置くカテゴリを選択します。 

### <a name="classification"></a>分類
関連するアラートの分類のセットに基づいてインシデントをフィルター処理します。 値には、true alerts、false alerts、未設定のいずれかが含まれます。

### <a name="data-sensitivity"></a>データの機密性
一部の攻撃では、機密データや貴重なデータを排除することを目的としています。 機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。

>[!NOTE]
>Microsoft Information Protection が有効になっている場合にのみ適用されます。

### <a name="device-group"></a>デバイスグループ
定義済みのデバイスグループでフィルター処理します。

### <a name="investigation-state"></a>調査の状態
自動調査の状態によってインシデントをフィルター処理します。 

### <a name="multiple-categories"></a>複数のカテゴリ 
複数の分類項目にマップされているインシデントのみを表示するように選択すると、それにより損害が発生する可能性が高くなります。 

### <a name="multiple-service-sources"></a>複数のサービス ソース 
フィルターを適用すると、さまざまなソースからのアラートを含むインシデントのみが表示されます (エンドポイントの Microsoft Defender、Microsoft Cloud App Security、Microsoft defender for Identity、microsoft Defender for Office 365)。

### <a name="os-platform"></a>OS プラットフォーム
インシデントキュービューをオペレーティングシステムごとに制限します。

### <a name="service-sources"></a>サービス ソース
特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。 

### <a name="severity"></a>重要度
インシデントの重要度は、資産に対する影響を示しています。 重要度が高くなるほど、影響が大きくなり、通常は最も近い注意が必要になります。 

### <a name="status"></a>状態
状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。

>[!IMPORTANT]
>現在、分類、デバイスグループ、調査状態、OS プラットフォームの各フィルターは、パブリックプレビューでのみ使用できます。


## <a name="next-steps"></a>次の手順
どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。
- [インシデントの調査](investigate-incidents.md)


## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
