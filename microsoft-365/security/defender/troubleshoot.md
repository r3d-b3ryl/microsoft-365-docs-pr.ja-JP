---
title: Microsoft 365 Defender サービスの問題のトラブルシューティング
description: 既知の Microsoft 365 Defender の問題に対する解決策と回避策を見つける
keywords: Microsoft 365 Defender のトラブルシューティング、トラブルシューティング、Microsoft Defender for Identity、issues、アドオン、設定ページ
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
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933399"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender サービスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

このセクションでは、Microsoft 365 Defender サービスを使用する際に発生する可能性のある問題について説明します。

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender コンテンツが表示される

ポータルでインシデント、アクション センター、ハンティングなどの機能がナビゲーション ウィンドウに表示されていない場合は、テナントに適切なライセンスが含まれています。

詳細については、[前提条件](prerequisites.md)をご覧ください。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity アラートが Microsoft 365 Defender インシデントに表示されない

環境に Microsoft Defender for Identity が展開されているが、Microsoft 365 Defender インシデントの一部として Defender for Identity アラートが表示されない場合は、Microsoft Cloud App Security と Defender for Identity の統合が有効になっている必要があります。

詳細については [、「Microsoft Defender for Identity integration」を参照してください](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>サービスを有効にする設定ページはどこに表示されますか?

Microsoft 365 Defender を有効にするには、Microsoft 365 セキュリティ センターのナビゲーション ウィンドウから [設定] にアクセスします。 このナビゲーション アイテムは、前提条件のアクセス許可とライセンスを持 [っている場合にのみ表示されます](m365d-enable.md#check-license-eligibility-and-required-permissions)。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>ファイル/URL の例外を作成する方法

誤検知とは、悪意のあるファイルまたは URL であり、脅威ではないと検出されます。 インジケーターを作成し、ブロックを解除して特定のファイル/URL を許可する除外を定義できます。 「Defender [for Endpoint」の「Address false positives/negatives」を参照してください](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。


