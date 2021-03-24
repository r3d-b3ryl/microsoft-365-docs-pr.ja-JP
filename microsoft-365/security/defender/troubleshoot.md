---
title: Microsoft 365 Defender サービスの問題のトラブルシューティング
description: 既知の Microsoft 365 Defender の問題に関する解決策を見つけて回避する
keywords: Microsoft Threat Protection のトラブルシューティング、トラブルシューティング、Azure ATP、問題、アドオン、設定ページ
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
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065899"
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

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>サービスを有効にする設定ページはどこに表示されますか?

Microsoft 365 Defender を有効にするには、Microsoft 365 セキュリティ センターのナビゲーション ウィンドウから [設定] にアクセスします。 このナビゲーション アイテムは、前提条件のアクセス許可とライセンスを持 [っている場合にのみ表示されます](m365d-enable.md#check-license-eligibility-and-required-permissions)。
