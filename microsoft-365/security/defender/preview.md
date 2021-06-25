---
title: プレビュー機能のMicrosoft 365 Defender
description: Microsoft 365 セキュリティの新機能について学ぶ
keywords: プレビュー、新規、m365 セキュリティ、セキュリティ、365、機能
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b852071c3fbfe12aac62e1d309fa130a4cd81e9c
ms.sourcegitcommit: b42dd3e706ebf9638cd893b35f75eaa56dd8fd7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53125400"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defenderプレビュー機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> プレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。 一部の機能はサポートされていないか、制限された機能を持っている可能性があります。

**適用対象:**
- Microsoft 365 Defender

新Microsoft 365 Defender機能を含むサービスが常に更新されています。

プレビュー リリースの新機能Microsoft 365 Defender、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。

一般に利用可能な新機能の詳細については、「新機能」を参照[Microsoft 365 Defender。](whats-new.md)

## <a name="required-permissions"></a>必要なアクセス許可

次のロール (Azure Azure Active Directory) AD割り当てられたアカウントは、プレビュー機能Microsoft 365 Defender有効にできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする

今後の機能にアクセスしてフィードバックを提供し、機能が一般提供される前に全体的なエクスペリエンスを向上させるのに役立ちます。

プレビュー機能設定をオンにして、今後の機能をいち早く試します。

1. ナビゲーション ウィンドウで、**[設定]** を選びます。
2. [Microsoft 365 Defender]**を選択します**。
3. **[プレビュー機能]** > **を選択し、プレビュー機能をオンにします**。 
4. **[保存]** を選択します。

**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。 

## <a name="preview-features"></a>プレビュー機能

現在、次の機能と拡張機能がプレビューで利用できます:

- **[脅威タグごとにレポートを表示](threat-analytics.md#view-reports-per-threat-tags)** する - 脅威タグは、特定の脅威カテゴリに焦点を当て、最も関連性の高いレポートを確認するのに役立ちます。
- **[ストリーミング API](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender高度なハンティングを通じて利用可能なすべてのイベントをイベント ハブや Azure ストレージ アカウントにストリーミングできます。
- **[Microsoft 365 Defender API](api-overview.md)** - トップ レベルの Microsoft 365 Defender API を使用すると、共有インシデントテーブルと高度なハンティング テーブルに基づいてワークフローを自動化できます。 
- **[高度な狩猟でアクションを](advanced-hunting-take-action.md)** 実行する - 高度な狩猟で見つけた脅威を迅速に含むか、侵害された資産 [に対処します](advanced-hunting-overview.md)。
- **[ポータル内スキーマ参照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - セキュリティ センターで高度な検索スキーマ テーブルに関する情報を直接取得します。 テーブルと列の説明に加えて、この参照には、サポートされているイベントの種類 ( `ActionType` 値) とサンプル クエリが含まれます。
- **[DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)** - 特定の時間範囲で特定の IP アドレスまたはアドレスが割り当てられているデバイスに関する情報を取得します。
