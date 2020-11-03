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
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846714"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でインシデントの優先度を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



Microsoft 365 Defender は、関連付け分析を適用し、さまざまな製品からのすべての関連アラートと調査を1つのインシデントに集約します。 また、microsoft 365 Defender は、Microsoft 365 Defender が不動産および製品スイート全体で使用するエンドツーエンドの可視性を与えられた悪意のあるアクティビティに対して、固有のアラートをトリガーします。 これにより、Microsoft 365 Defender narrates によって、より広範な攻撃ストーリーが実現されます。これにより、セキュリティ運用アナリストは、組織全体にわたる複雑な脅威を理解し、扱うことができます。


**インシデント キュー** には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。


![インシデント キューの画像](../../media/incidents-queue.png) 

既定では、Microsoft 365 セキュリティ センターのキューには過去 30 日間に発生したインシデントが表示され、最新のインシデントがリストの一番上に表示されるため、最新のインシデントを最初に確認できます。

インシデント キューには、カスタマイズ可能な列が表示され、インシデントまたは含まれているエンティティのさまざまな特性を確認できます。これにより、処理するインシデントの優先順位付けに関する情報に基づいて意思決定ができます。

わかりやすくするために、自動インシデントの名前付けは、影響を受けるエンドポイント数、影響を受けるユーザー、検出ソースまたはカテゴリなどのアラート属性に基づいて、インシデント名を生成します。 これにより、インシデントの範囲をすばやく理解することができます。

例: 複数の *ソースによって報告された複数のエンドポイントのマルチステージインシデント* 。

> [!NOTE]
> 自動インシデントの名前の公開前に存在していたインシデントは、名前が変更されません。

また、インシデント キューには複数のフィルター処理オプションも表示されます。このオプションを適用すると、環境内の既存のすべてのインシデントを幅広く一括処理したり、特定のシナリオまたは脅威に焦点を当てたりすることができます。 インシデント キューにフィルターを適用すると、すぐに注意が必要なインシデントを特定できます。 

## <a name="available-filters"></a>利用可能なフィルター

### <a name="status"></a>状態
状態に基づいて表示されるインシデントのリストを制限して、アクティブなインシデントまたは解決されたインシデントを確認できます。

### <a name="severity"></a>重要度
インシデントの重大度は、資産に与える影響を示しています。 重大度が高いほど影響が大きく、通常は最も迅速な対応が必要になります。 

### <a name="assigned-to-owner"></a>割り当て先 (所有者)
ユーザー割り当てられているものまたは自分に割り当てられているものを選択することで、リストをフィルター処理することを選択できます。

### <a name="multiple-alerts"></a>複数のアラート 
複数のアラートを含むインシデントのみを表示するには、フィルター処理します。 これは、攻撃がキル チェーンでより複雑または進行していることを示している可能性があります。 


### <a name="multiple-service-sources"></a>複数のサービス ソース 
フィルターによって、さまざまなソースからのアラートを含むインシデントのみが表示されます (エンドポイントの Microsoft Defender、Microsoft Cloud App Security、Microsoft defender for Identity、microsoft Defender for Office 365)
### <a name="service-sources"></a>サービス ソース
特定のソースを選択すると、選択したソースから 1 つ以上のアラートを含むインシデントに焦点を当てることができます。 

### <a name="multiple-categories"></a>複数のカテゴリ 
キル チェーンの複数のカテゴリにマッピングされたインシデントのみを表示できます。この場合、より多くの損害を引き起こす可能性があります。 

### <a name="categories"></a>カテゴリ
キル チェーンの特定の手順に焦点を当てる特定のカテゴリを選択する

### <a name="data-sensitivity"></a>データの機密性
一部の攻撃では、機密データや貴重なデータを排除することを目的としています。 機密データがインシデントに関与しているかどうかを確認するためにフィルター処理を適用することにより、機密情報が侵害されている可能性があるかどうかを迅速に判断し、それらのインシデントへの対処に優先順位を付けることができます。

>[!NOTE]
>Microsoft Information Protection が有効になっている場合にのみ適用されます。


## <a name="next-steps"></a>次の手順
どのインシデントが最も重要かを判断したら、インシデントについてさらに調査を進めます。
- [インシデントの調査](investigate-incidents.md)


## <a name="related-topics"></a>関連項目
- [インシデントの概要](incidents-overview.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
