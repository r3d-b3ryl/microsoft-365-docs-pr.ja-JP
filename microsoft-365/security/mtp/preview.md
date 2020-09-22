---
title: Microsoft の脅威保護のプレビュー機能
description: Microsoft 365 セキュリティの新機能について説明します。
keywords: preview、new、m365 security、security、365、capabilities
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195505"
---
# <a name="microsoft-threat-protection-preview-features"></a>Microsoft Threat Protection のプレビュー機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection


Microsoft Threat Protection サービスは、新しい機能の拡張と機能を含むように、絶えず更新されています。

Microsoft Threat Protection プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初に予定されている機能を試すことができます。

一般的に利用可能な新機能の詳細については、「[Microsoft Threat Protection の新機能](whats-new.md)」を参照してください。

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする
機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。

[プレビュー環境] 設定をオンにして、最初の機能を試すことができます。

1. ナビゲーションウィンドウで、[ **設定**] を選択します。

2. [ **Microsoft Threat Protection**] を選択します。


3. [**プレビュー機能の選択]**  >  **プレビュー機能を有効に**します。 

3. **[保存]** を選択します。

[ **プレビュー機能を有効に** する] チェックボックスがオンになっている場合は、プレビュー機能が有効になっていることを確認できます。 

## <a name="preview-features"></a>プレビュー機能
現在、次の機能と拡張機能をプレビューで利用できます。

- **[Microsoft Threat Protection api](api-overview.md)** -lop レベルの Microsoft 脅威保護 api を使用すると、共有インシデントと高度な検索の表に基づいてワークフローを自動化できます。 
- **[高度な検索の](advanced-hunting-identitydirectoryevents-table.md)** 場合は、Active DIRECTORY (AD) を実行しているオンプレミスのドメインコントローラーを含むイベントを検索します。 この表では、ドメインコントローラーの id 関連イベントの範囲とシステムイベントについて説明します。
- **[高度な検索でアクションを実行](advanced-hunting-take-action.md)** する: [高度な](advanced-hunting-overview.md)検索によって検出された脅威または侵害された資産への対処をすばやく行うことができます。
- **[ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : セキュリティセンターで、高度な検索スキーマテーブルに関する情報を直接取得します。 この便利なリファレンスでは、テーブルと列の説明に加えて、サポートされているイベントの種類 (値) とサンプルクエリに関する情報を提供して `ActionType` います。

