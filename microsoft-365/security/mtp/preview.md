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
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288127"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender プレビュー機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> プレビュー バージョンはサービス レベルアグリーメントなしで提供され、実稼働ワークロードにはお勧めしません。 一部の機能がサポートされていないか、機能が制限されている可能性があります。

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender サービスは常に更新され、新しい機能拡張と機能が含まれます。

Microsoft 365 Defender プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして今後の機能を最初に試してみてください。

一般に利用可能な新機能について詳しくは [、Microsoft 365 Defender の新機能に関するページをご覧ください](whats-new.md)。

## <a name="required-permissions"></a>必要なアクセス許可

次の Azure Active Directory (Azure AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender Preview 機能を有効にできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター

## <a name="turn-on-preview-features"></a>プレビュー機能を有効にする

機能が一般提供される前に、全体的なエクスペリエンスを向上させるためにフィードバックを提供できる今後の機能にアクセスできます。

プレビュー機能設定をオンにして、今後の機能をいち早く試します。

1. ナビゲーション ウィンドウで、**[設定]** を選びます。
2. **Microsoft 365 Defender を選択します**。
3. **[プレビュー機能]** > **を選択し、プレビュー機能をオンにします**。 
4. **[保存]** を選択します。

**[プレビュー機能をオンにする]** チェックボックスが選択されていると、プレビュー機能がオンになっていることがわかります。 

## <a name="preview-features"></a>プレビュー機能

現在、次の機能と拡張機能がプレビューで利用できます:

### <a name="improved-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの強化
改善された [Microsoft 365 セキュリティ センター](https://security.microsoft.com)がパブリック プレビューで利用できるようになりました。 この新しいエクスペリエンスにより、Defender for Endpoint、Defender for Office 365、Microsoft 365 Defender、その他が Microsoft 365 セキュリティ センターに追加されます。 これは、セキュリティ制御を管理するための新しいホームです。 [新機能について説明します](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。

- **[Microsoft 365 Defender 脅威分析](threat-analytics.md)** レポート - 脅威分析は、アクティブな攻撃への対応と影響の最小化に役立ちます。 また、Microsoft 365 Defender ソリューションによってブロックされる攻撃の試みについて学習し、さらなる露出のリスクを軽減し、回復性を高める予防的なアクションを実行できます。 統合されたセキュリティ エクスペリエンスの一環として、Microsoft Defender for Endpoint および Microsoft Defender for Office E5 ライセンス所有者向け脅威分析が利用できます。
- **[Microsoft 365 Defender API](api-overview.md)** - Microsoft 365 Defender のトップ レベル API を使用すると、共有インシデントと高度な検索テーブルに基づいてワークフローを自動化できます。 
- **[高度な検索でアクションを実行](advanced-hunting-take-action.md)** する — 高度な検索で見つけた脅威を迅速に含むか、侵害された資産 [に対処します](advanced-hunting-overview.md)。
- **[ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— 高度な検索スキーマ テーブルに関する情報をセキュリティ センターで直接取得します。 このリファレンスには、テーブルと列の説明に加えて、サポートされているイベントの種類 ( `ActionType` 値) とサンプル クエリが含まれています。
- **[DeviceFromIP() 関数](advanced-hunting-devicefromip-function.md)**—特定の時間範囲で特定の IP アドレスが割り当てられているデバイスに関する情報を取得します。
