---
title: Defender サービスMicrosoft 365のトラブルシューティング
description: Defender の既知の問題に対する解決策とMicrosoft 365探す
keywords: Defender Microsoft 365トラブルシューティング、トラブルシューティング、Microsoft Defender for Identity、issues、アドオン、設定ページ
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
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782743"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Defender サービスMicrosoft 365のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

このセクションでは、Defender サービスを使用する際に発生する可能性のあるMicrosoft 365説明します。

## <a name="i-dont-see-microsoft-365-defender-content"></a>Defender コンテンツが表示Microsoft 365しない

ポータルでインシデント、アクション センター、ハンティングなどの機能がナビゲーション ウィンドウに表示されていない場合は、テナントに適切なライセンスが含まれています。

詳細については、[前提条件](prerequisites.md)をご覧ください。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender for Identity アラートが Defender インシデントのMicrosoft 365表示されない

環境に Microsoft Defender for Identity が展開されているが、Microsoft 365 Defender インシデントの一部として Defender for Identity アラートが表示されない場合は、Microsoft Cloud App Security と Defender for Identity の統合が有効になっている必要があります。

詳細については [、「Microsoft Defender for Identity integration」を参照してください](/cloud-app-security/mdi-integration)。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>サービスを有効にする設定ページはどこに表示されますか?

Defender を有効Microsoft 365、セキュリティ センター **設定** ナビゲーション ウィンドウからアクセスMicrosoft 365アクセスします。 このナビゲーション アイテムは、前提条件のアクセス許可とライセンスを持 [っている場合にのみ表示されます](m365d-enable.md#check-license-eligibility-and-required-permissions)。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>ファイル/URL の例外を作成する方法

誤検知とは、悪意のあるファイルまたは URL であり、脅威ではないと検出されます。 インジケーターを作成し、ブロックを解除して特定のファイル/URL を許可する除外を定義できます。 「Defender [for Endpoint」の「Address false positives/negatives」を参照してください](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。


