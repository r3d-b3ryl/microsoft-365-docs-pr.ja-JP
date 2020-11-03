---
title: Microsoft 365 Defender のプレビュー機能
description: Microsoft 365 セキュリティの新機能について学ぶ
keywords: プレビュー、新規、m365 セキュリティ、セキュリティ、365、機能
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
ms.openlocfilehash: 4c731869d1ec1740f8c9173705f9af72b0e2fe53
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844754"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender プレビュー機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
>プレビューバージョンはサービスレベル契約なしで提供されるので、運用ワークロードにはお勧めしません。 一部の機能はサポートされていない場合や、制限された機能を備えている場合があります。

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender service は、新しい機能の拡張と機能を含むように常に更新されています。

Microsoft 365 Defender プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初の機能を試すことができます。

一般的に使用できる新機能の詳細については、「 [Microsoft の新機能 (365 Defender](whats-new.md))」を参照してください。

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする
機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。

プレビュー機能設定をオンにして、今後の機能をいち早く試します。

1. ナビゲーション ウィンドウで、 **[設定]** を選びます。

2. [ **Microsoft 365 Defender** ] を選択します。


3. **[プレビュー機能]** > **を選択し、プレビュー機能をオンにします** 。 

3. **[保存]** を選択します。

**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。 

## <a name="preview-features"></a>プレビュー機能
現在、次の機能と拡張機能がプレビューで利用できます:

- **[Microsoft 365 Defender api](api-overview.md)** -lop レベルの Microsoft 365 Defender api を使用すると、共有インシデントと高度な検索テーブルに基づいてワークフローを自動化することができます。 
- **[高度な検索でアクションを実行](advanced-hunting-take-action.md)** する: [高度な](advanced-hunting-overview.md)検索によって検出された脅威または侵害された資産への対処をすばやく行うことができます。
- **[ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : セキュリティセンターで、高度な検索スキーマテーブルに関する情報を直接取得します。 このリファレンスには、テーブルと列の説明に加えて、サポートされているイベントの種類 ( `ActionType` 値) とサンプルクエリが含まれています。

