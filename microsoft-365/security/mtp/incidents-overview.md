---
title: Microsoft 365 Defender のインシデントの概要
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929284"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Microsoft 365 Defender のインシデントの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験したい場合 ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。
>


インシデントは、関連するアラートに基づいて行います。 アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。 個々のアラートは、攻撃が続く場合の貴重な手がかりを提供します。 ただし、攻撃は通常、侵害を実行するためにさまざまなベクトルと手法を使用します。 個々の手がかりを組み合わせてまとめる作業は、困難で時間がかかる場合があります。

この短いビデオでは、Microsoft 365 Defender のインシデントの概要を説明します。
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

インシデントとは、攻撃のストーリーを構成する関連付けされたアラートのコレクションです。 ネットワーク内の異なるデバイス、ユーザー、およびメールボックス エンティティで検出された悪意のあるイベントと疑わしいイベントは、Microsoft 365 Defender によって自動的に集約されます。 関連するアラートをインシデントにグループ化すると、セキュリティ防御側は攻撃の包括的なビューを提供します。 

たとえば、セキュリティ防御側は、攻撃の開始場所、使用された方法、および攻撃がネットワークにどこまで進むかを確認できます。 また、影響を受けたデバイス、ユーザー、メールボックスの数、影響の重大さ、影響を受けたエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。

有効にした場合、Microsoft 365 Defender は自動化と人工知能を通じて個々のアラートを自動的に調査して解決できます。 セキュリティ防御側は、インシデント ビューから直接攻撃を解決するための追加の修復手順を実行することもできます。 

過去 30 日間のインシデントがインシデント キューに表示されます。 ここから、セキュリティの防御側は、リスク レベルなどの要因に基づいて、どのインシデントに優先順位を付ける必要があるのか確認できます。 

セキュリティ防御側は、インシデントの名前を変更したり、インシデントを個々のアナリストに割り当て、インシデントにタグを分類したり、インシデントにタグを追加したりして、より優れたカスタマイズされたインシデント管理エクスペリエンスを提供することもできます。



## <a name="see-also"></a>関連項目
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
