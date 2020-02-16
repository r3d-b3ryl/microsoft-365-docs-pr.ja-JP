---
title: Microsoft Threat Protection のインシデントに優先順位を付ける
description: Microsoft Threat Protection のインシデント キューからインシデントに優先順位を付ける方法の詳細
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 90f7aaf7eb4425dadeb27699654656c86d2b6263
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087303"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Microsoft Threat Protection のインシデントに優先順位を付ける

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection は、相関分析を適用し、さまざまな製品からのすべての関連する通知と調査を 1 つのインシデントに集約します。 また、Microsoft Threat Protection は、Microsoft Threat Protection が資産全体および製品スイート全体にわたってエンドツーエンドの可視性を備えているため、悪意があると識別できるアクティビティにのみ一意の警告をトリガーします。 そうすることで、Microsoft Threat Protection はより広範な攻撃事例を説明し、セキュリティ運用アナリストが組織全体の複雑な脅威を理解して対処できるようにします。


**インシデント キュー**には、デバイス、ユーザー、メールボックス全体からフラグが付けられたインシデントのコレクションが表示されます。 これにより、インシデントを分類して優先順位を付け、情報に基づいたサイバーセキュリティ対応の決定を作成できます。


![インシデント キューの画像](../../media/incidents-queue.png) 

既定では、Microsoft 365 セキュリティ センターのキューには過去 30 日間に発生したインシデントが表示され、最新のインシデントがリストの一番上に表示されるため、最新のインシデントを最初に確認できます。

インシデント キューには、カスタマイズ可能な列が表示され、インシデントまたは含まれているエンティティのさまざまな特性を確認できます。これにより、処理するインシデントの優先順位付けに関する情報に基づいて意思決定ができます。 

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
さまざまなソース (Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP) からのアラートを含むインシデントのみを表示するようにフィルター処理する
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
