---
title: Microsoft Threat Protection のプレビュー機能
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
ms.openlocfilehash: f01f76ac591b4c2be9873fa87ec416939158acd3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195505"
---
# <a name="microsoft-threat-protection-preview-features"></a>Microsoft Threat Protection プレビュー機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection


Microsoft Threat Protection サービスは、常に新しい機能拡張と機能を含むように更新されています。

Microsoft Threat Protection プレビュー リリースの新機能について学習し、プレビュー機能を有効にして、新しい機能をいち早く試してください。

一般的に利用可能な新機能の詳細については、「[Microsoft Threat Protection の新機能](whats-new.md)」を参照してください。

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする
機能が一般に利用可能になる前に全体的な操作性を向上させるため、お客様がフィードバックを提供できる今後の機能にアクセスできます。

プレビュー機能設定をオンにして、今後の機能をいち早く試します。

1. ナビゲーション ウィンドウで、**[設定]** を選びます。

2. **[Microsoft Threat Protection]** を選択します。


3. **[プレビュー機能]** > ** を選択し、プレビュー機能をオンにします**。 

3. **[保存]** を選択します。

**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。 

## <a name="preview-features"></a>プレビュー機能
現在、次の機能と拡張機能がプレビューで利用できます:

- **[Microsoft Threat Protection API](api-overview.md)** - lop レベルの Microsoft Threat Protection API を使用すると、共有インシデントと高度な捜索テーブルに基づいてワークフローを自動化できます。 
- **[高度な捜索の IdentityDirectoryEvents テーブル](advanced-hunting-identitydirectoryevents-table.md)** — Active Directory （AD） を実行しているオンプレミス ドメイン コントローラーに関連するイベントを検索します。 このテーブルでは、ドメイン コントローラーのシステム イベントだけでなく、ID 関連のさまざまなイベントについても説明します。
- **[高度な捜索で行動を起こす](advanced-hunting-take-action.md)** — [高度な捜索](advanced-hunting-overview.md) で発見した脅威をすばやく阻止したり、侵害された資産に対処したりします。
- **[ポータル内スキーマ参照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — 高度な捜索のスキーマ テーブルに関する情報をセキュリティ センターで直接取得します。 この便利な参照では、テーブルと列の説明に加えて、サポートされているイベント タイプ （`ActionType` の値） とサンプル クエリに関する情報を提供します。

