---
title: Microsoft 365 Defender のプレビュー機能
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2f5b1a289f55b7237606782afb8e8f5acf6788a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918860"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender プレビュー機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> プレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。 一部の機能はサポートされていないか、制限された機能を持っている可能性があります。

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender サービスは常に更新され、新機能の強化と機能が含まれます。

Microsoft 365 Defender プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。

一般に利用可能な新機能の詳細については [、「Microsoft 365 Defender](whats-new.md)の新機能」を参照してください。

## <a name="required-permissions"></a>必要なアクセス許可

次の Azure Active Directory (Azure Active Directory AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender Preview 機能を有効にできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする

今後の機能にアクセスしてフィードバックを提供し、機能が一般提供される前に全体的なエクスペリエンスを向上させるのに役立ちます。

プレビュー機能設定をオンにして、今後の機能をいち早く試します。

1. ナビゲーション ウィンドウで、**[設定]** を選びます。
2. [Microsoft **365 Defender] を選択します**。
3. **[プレビュー機能]** > **を選択し、プレビュー機能をオンにします**。 
4. **[保存]** を選択します。

**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。 

## <a name="preview-features"></a>プレビュー機能

現在、次の機能と拡張機能がプレビューで利用できます:

### <a name="improved-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの強化
改善された [Microsoft 365 セキュリティ センター](https://security.microsoft.com)がパブリック プレビューで利用できるようになりました。 この新しいエクスペリエンスにより、Defender for Endpoint、Defender for Office 365、Microsoft 365 Defender などが Microsoft 365 セキュリティ センターに導入されます。 これは、セキュリティコントロールを管理するための新しいホームです。 [新機能について説明します](./overview-security-center.md)。

- **[Microsoft 365 Defender の脅威分析レポート](threat-analytics.md)** - 脅威分析は、アクティブな攻撃の影響に対応し、最小限に抑えるのに役立ちます。 また、Microsoft 365 Defender ソリューションによってブロックされる攻撃の試みについて説明し、さらなる暴露のリスクを軽減し、回復力を高める予防措置を講じてみることができます。 統合セキュリティ エクスペリエンスの一環として、Microsoft Defender for Endpoint および Microsoft Defender では、E5 ライセンス所有者向Office利用できます。
- **[Microsoft 365 Defender API](api-overview.md)** - Microsoft 365 Defender のトップ レベル API を使用すると、共有インシデントと高度なハンティング テーブルに基づいてワークフローを自動化できます。 
- **[高度な狩猟でアクションを](advanced-hunting-take-action.md)** 実行する -迅速に脅威を含むか、高度な狩猟で見つけた侵害された資産 [に対処します](advanced-hunting-overview.md)。
- **[ポータル内スキーマ参照](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**- セキュリティ センターで高度な検索スキーマ テーブルに関する情報を直接取得します。 テーブルと列の説明に加えて、この参照には、サポートされているイベントの種類 ( `ActionType` 値) とサンプル クエリが含まれます。
- **[DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)**—特定の時間範囲で特定の IP アドレスまたはアドレスが割り当てられているデバイスに関する情報を取得します。