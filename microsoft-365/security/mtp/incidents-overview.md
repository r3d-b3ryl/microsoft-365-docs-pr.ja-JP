---
title: Microsoft Threat Protection のインシデントの概要
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
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
ms.openlocfilehash: 3c50bbfbfdad85283f6e366a32c126958467f4a0
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431113"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a>Microsoft Threat Protection のインシデントの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection



インシデントは、関連するアラートに基づいています。 アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。 個々のアラートは、進行中の攻撃に関する有益な手がかりを提供します。 ただし、攻撃では通常、違反を実行するためのさまざまなベクターと手法が使用されます。 Piecing 個別のヒントを一緒に使用することは困難で時間がかかることがあります。

この短いビデオは、Microsoft の脅威保護のインシデントの概要を示しています。
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

インシデントとは、攻撃のストーリーを構成する、相互に関連する警告のコレクションのことです。 ネットワーク内のさまざまなデバイス、ユーザー、およびメールボックスエンティティにある悪意のある疑わしいイベントは、Microsoft の脅威保護によって自動的に集計されます。 関連するアラートをインシデントにグループ化することにより、セキュリティ defenders が攻撃の包括的なビューになります。 

たとえば、セキュリティ defenders は、攻撃がどこで開始されたか、どのような戦術を使用したか、およびその攻撃がネットワークにどのくらいの時間が経過したかを確認できます。 また、デバイス、ユーザー、メールボックスの数、影響の深刻度、影響を受けるエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。

有効にした場合、Microsoft の脅威保護は自動化および人工知能によって個々の通知を自動的に調査および解決できます。 セキュリティ defenders は、インシデントビューから直接攻撃を解決するために、追加の修復手順を実行することもできます。 

過去30日間のインシデントは、インシデントキューに表示されます。 ここから、セキュリティ defenders は、リスクレベルやその他の要因に基づいて、どのインシデントに優先度を設定する必要があるかを確認できます。 

セキュリティ defenders は、インシデントの名前を変更したり、インシデントに対して個別のアナリストに割り当てたり、インシデントにタグを追加したりすることもできます。



## <a name="see-also"></a>関連項目
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
