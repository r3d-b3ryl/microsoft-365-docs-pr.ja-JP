---
title: Microsoft 365 Defender サービスに関する問題のトラブルシューティング
description: 既知のMicrosoft 365 Defenderの問題に対する解決策と回避策を見つける
keywords: Microsoft 365 Defenderのトラブルシューティング、トラブルシューティング、Microsoft Defender for Identity、問題、アドオン、設定ページ
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 1bc37191d83ebe4e2a6d483d4f490d96d195082b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67474954"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender サービスに関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

このセクションでは、Microsoft 365 Defender サービスを使用するときに発生する可能性がある問題に対処します。

## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defenderコンテンツが表示されない

ポータルのナビゲーション ウィンドウにインシデント、アクション センター、ハンティングなどの機能が表示されない場合は、テナントに適切なライセンスがあることを確認する必要があります。

詳細については、[前提条件](prerequisites.md)をご覧ください。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft 365 Defender インシデントにアラートが表示されないMicrosoft Defender for Identity

環境にデプロイMicrosoft Defender for Identityが、Microsoft 365 Defender インシデントの一部として Defender for Identity アラートが表示されない場合は、Microsoft Defender for Cloud Apps と Defender for Identity の統合が有効になっています。

詳細については、「[Microsoft Defender for Identity統合](/cloud-app-security/mdi-integration)」を参照してください。

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>サービスを有効にするための設定ページはどこにありますか?

Microsoft 365 Defenderを有効にするには、Microsoft 365 Defender ポータルのナビゲーション ウィンドウから **[設定]** にアクセスします。 このナビゲーション 項目は、 [前提条件のアクセス許可とライセンス](m365d-enable.md#check-license-eligibility-and-required-permissions)がある場合にのみ表示されます。

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>ファイル/URL の例外を作成操作方法?

偽陽性は、悪意のあるものとして検出されたが脅威ではないファイルまたは URL です。 インジケーターを作成し、除外を定義してブロックを解除し、特定のファイル/URL を許可することができます。 [Defender for Endpoint の「アドレス false positives/negatives」を参照してください](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。
