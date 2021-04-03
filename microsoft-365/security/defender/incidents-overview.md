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
ms.openlocfilehash: 6dd13c5f83d05be3c77e5f84608fb6aa5172d9a4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500921"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Microsoft 365 Defender のインシデントの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>


インシデントは、関連するアラートに基づいて行います。 アラートは、ネットワーク上で悪意のあるイベントまたはアクティビティが検出されたときに作成されます。 個々のアラートは、オンナ攻撃に関する貴重な手がかりを提供します。 ただし、攻撃は通常、侵害を実行するためにさまざまなベクトルと手法を使用します。 個々の手がかりを一緒にまとめる作業は、困難で時間のかかる場合があります。

この短いビデオでは、Microsoft 365 Defender でのインシデントの概要を示します。
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

インシデントとは、攻撃のストーリーを構成する相関アラートのコレクションです。 ネットワーク内の異なるデバイス、ユーザー、およびメールボックス エンティティで検出された悪意のあるイベントと疑わしいイベントは、Microsoft 365 Defender によって自動的に集計されます。 関連するアラートをインシデントにグループ化すると、セキュリティ防御者は攻撃の包括的なビューを提供します。 

たとえば、セキュリティ防御者は、攻撃の開始場所、使用された戦術、およびネットワークへの攻撃の行方を確認できます。 また、影響を受けたデバイス、ユーザー、メールボックスの数、影響を受けた影響の大きさ、影響を受けるエンティティに関するその他の詳細など、攻撃の範囲を確認することもできます。

有効にした場合、Microsoft 365 Defender は自動化と人工知能を通じて個々のアラートを自動的に調査して解決できます。 セキュリティ防御側は、インシデント ビューから直接攻撃を解決するための追加の修復手順を実行することもできます。 

過去 30 日間のインシデントがインシデント キューに表示されます。 ここから、セキュリティディフェンダーは、リスク レベルや他の要因に基づいて、どのインシデントを優先順位付けする必要があるのか確認できます。 

セキュリティ防御者は、インシデントの名前を変更したり、個々のアナリストに割り当て、分類したり、インシデントにタグを追加したりして、よりカスタマイズされたインシデント管理エクスペリエンスを提供することもできます。



## <a name="see-also"></a>関連項目
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)