---
title: インシデント キューを CSV ファイルにエクスポートする
description: 新しく導入された [エクスポート] ボタンについて説明し、インシデント キュー関連のデータを CSV ファイルに移行する
keywords: インシデント, キュー, エクスポート, csv
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-smandalika
author: v-smandalika
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 5c9973674acd577bef44a2ceb73b6996da81b80b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483346"
---
# <a name="export-incidents-queue-to-csv-files"></a>インシデント キューを CSV ファイルにエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

**エクスポート** 機能を使用すると、適用されたフィルターと時間範囲に従って表示されるインシデント キュー内のデータをエクスポートできます。 次のスクリーンショットに示すように、[ **エクスポート]** という名前のボタンの形式で使用できます。

:::image type="content" source="../../media/defender/incidents-queue-with-export-button.png" alt-text="Microsoft 365 Defender ポータルの [インシデント] ページで [エクスポート] ボタンを表示します":::

**[エクスポート**] ボタンをクリックすると、データが CSV ファイルにエクスポートされます。 さまざまなフィルターと時間範囲をインシデント キューに適用できます (データをエクスポートするコンテキストだけでなく、汎用的なコンテキストで)。 **[エクスポート]** を選択すると、インシデント キューに適用されるフィルターや時間範囲が選択されると、そのようなデータが CSV ファイルにエクスポートされます。

インシデント キュー関連のデータを CSV ファイルにエクスポートしたら、要件に基づいてデータを分析し、さらにフィルター処理できます。

たとえば、CSV ファイルのデータにフィルターを適用して、次のデータを表示できます。
- 過去 30 日間に発生した重大度の高いインシデントの数に関するデータ。
- 最も生産性の高いアナリストであるユーザーに関するデータ。

> [!NOTE]
> CSV ファイルにエクスポートできるレコードの最大数は 10,000 です。 

インシデント キューの新しい **エクスポート** 機能 (**[エクスポート**] ボタン) に関する考えや提案がある場合は、Microsoft チームに問い合わせるか、Microsoft 365 Defender ポータルからフィードバックを送信してください。
