---
title: Microsoft 365 Defender でのインシデントの優先順位付け
description: Microsoft 365 Defender のインシデント キューからインシデントをフィルター処理する方法について説明します。
keywords: インシデント、キュー、概要、デバイス、ID、ユーザー、メールボックス、メール、インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5aba1ab4bed0eeb5f6127ab865ceea674e8d5902
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501000"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でのインシデントの優先順位付け

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



Microsoft 365 Defender は相関分析を適用し、異なる製品からのすべての関連するアラートと調査を 1 つのインシデントに集約します。 また、Microsoft 365 Defender は、Microsoft 365 Defender が製品の全資産とスイート全体で持っているエンドツーエンドの可視性を考えると、悪意のあるものとしてのみ識別できるアクティビティに関する一意のアラートをトリガーします。 このビューは、セキュリティ運用アナリストに広範な攻撃ストーリーを提供し、組織全体の複雑な脅威をよりよく理解し、対処するのに役立ちます。


**インシデント キュー** には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。


![インシデント キューの画像](../../media/incidents-queue.png) 

既定では、Microsoft 365 セキュリティ センターのキューには、過去 30 日間に発生したインシデントが表示されます。 最新のインシデントはリストの一番上にあるので、最初に確認できます。

インシデント キューはカスタマイズ可能な列を公開し、インシデントまたは含まれているエンティティの異なる特性を表示できます。 これにより、処理するインシデントの事前設定に関する情報に基づいた意思決定を行う際に役立ちます。

一目で見える表示を追加するために、インシデントの自動名前付けにより、影響を受けるエンドポイントの数、影響を受けるユーザー、検出元、カテゴリなどのアラート属性に基づいてインシデント名が生成されます。 これにより、インシデントの範囲をすばやく理解できます。

たとえば、複数 *のソースによって報告された複数のエンドポイントに対するマルチステージ インシデント。*

> [!NOTE]
> 自動インシデント名前付けのロールアウトの前に存在していたインシデントは、その名前は変更されません。

インシデント キューでは、複数のフィルター オプションも公開されます。適用すると、環境内のすべての既存のインシデントの広範なスイープを実行したり、特定のシナリオや脅威に集中することができます。 インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。 

## <a name="available-filters"></a>利用可能なフィルター

### <a name="assigned-to"></a>割り当て先
自分に割り当てられているアラート、または自動化によって処理されたアラートを表示できます。

### <a name="categories"></a>Categories
カテゴリを選択して、見られる特定の戦術、テクニック、または攻撃コンポーネントに焦点を当てる。 

### <a name="classification"></a>分類
関連するアラートの一連の分類に基づいてインシデントをフィルター処理します。 値には、true アラート、false アラート、または設定されていないが含まれます。

### <a name="data-sensitivity"></a>データの機密性
一部の攻撃では、機密データや貴重なデータを排除することを目的としています。 機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。

>[!NOTE]
>Microsoft Information Protection が有効になっている場合にのみ適用されます。

### <a name="device-group"></a>デバイス グループ
定義済みのデバイス グループでフィルター処理します。

### <a name="investigation-state"></a>調査の状態
自動調査の状態によってインシデントをフィルター処理します。 

### <a name="multiple-categories"></a>複数のカテゴリ 
複数のカテゴリにマップされたインシデントのみを表示し、より多くの損害を引き起こす可能性がある場合に選択できます。 

### <a name="multiple-service-sources"></a>複数のサービス ソース 
フィルターを適用して、さまざまなソースからの通知を含むインシデントのみを表示します (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365)。

### <a name="os-platform"></a>OS プラットフォーム
オペレーティング システムによってインシデント キュー ビューを制限します。

### <a name="service-sources"></a>サービス ソース
特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。 

### <a name="severity"></a>重要度
インシデントの重大度は、資産に与える影響を示しています。 重大度が高いほど、影響は大きく、通常は最も迅速な注意が必要です。 

### <a name="status"></a>状態
状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。




## <a name="next-steps"></a>次の手順
どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。
- [インシデントの調査](investigate-incidents.md)


## <a name="see-also"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
