---
title: Microsoft 365 Defender サービスに関する問題のトラブルシューティング
description: 既知の Microsoft 365 Defender に関する問題の解決策と回避策を見つける
keywords: Microsoft の脅威保護、トラブルシューティング、Azure ATP、問題、アドオン、設定ページのトラブルシューティング
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844670"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Microsoft 365 Defender サービスに関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

このセクションでは、Microsoft 365 Defender サービスの使用時に発生する可能性のある問題について取り上げます。


## <a name="i-dont-see-microsoft-365-defender-content"></a>Microsoft 365 Defender コンテンツが表示されない
ポータルでインシデント、アクションセンター、探している機能など、ナビゲーションウィンドウに機能が表示されない場合は、テナントに適切なライセンスがあることを確認する必要があります。 

詳細については、「[前提条件](prerequisites.md)」をご覧ください。

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender の Id 通知は Microsoft 365 Defender インシデントに表示されません。
お客様の環境に展開されている Id に対して Microsoft Defender を使用しているが、Microsoft 365 Defender インシデントの一部として Id 通知の Defender が表示されていない場合は、Microsoft Cloud App Security と Identity 統合の Defender が有効になっていることを確認する必要があります。 

詳細については、「 [id 統合のための Microsoft Defender](https://docs.microsoft.com/cloud-app-security/aatp-integration)」を参照してください。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>サービスをオンにするための設定ページはどこにありますか。
Microsoft 365 Defender を有効にするには、Microsoft 365 セキュリティセンターのナビゲーションウィンドウの **設定** にアクセスします。 このナビゲーション項目は、 [必要なアクセス許可とライセンス](mtp-enable.md#check-license-eligibility-and-required-permissions)がある場合にのみ表示されます。
 

