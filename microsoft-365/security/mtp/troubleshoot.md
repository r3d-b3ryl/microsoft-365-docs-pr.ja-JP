---
title: Microsoft 365 Defender サービスの問題のトラブルシューティング
description: 既知の Microsoft 365 Defender の問題に対する解決策と回避方法を見つける
keywords: Microsoft Threat Protection のトラブルシューティング, トラブルシューティング, Azure ATP, 問題, アドオン, 設定ページ
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
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925720"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender サービスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

このセクションでは、Microsoft 365 Defender サービスを使用する際に発生する可能性のある問題について説明します。

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender コンテンツが表示できない

ポータルの [インシデント]、アクション センター、検索などの機能がナビゲーション ウィンドウに表示されていない場合は、テナントに適切なライセンスが設定されている必要があります。

詳細については、「[前提条件](prerequisites.md)」をご覧ください。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender のインシデントで、Id 用 Microsoft Defender のアラートが表示されない

環境に Microsoft Defender for Identity が展開されているが、Microsoft 365 Defender インシデントの一部として Id 用 Defender のアラートが表示されない場合は、Microsoft Cloud App Security と Defender for Identity の統合が有効になっている必要があります。

詳しくは [、Id 統合のための Microsoft Defender に関するページをご覧ください](https://docs.microsoft.com/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>サービスを有効にする設定ページの場所

Microsoft 365 Defender を有効にする場合は、Microsoft 365 セキュリティ センターのナビゲーション ウィンドウから [設定] にアクセスします。 このナビゲーション アイテムは、必要なアクセス許可とライセンスを持 [っている場合にのみ表示されます](mtp-enable.md#check-license-eligibility-and-required-permissions)。
