---
title: Microsoft Threat Protection サービスに関する問題のトラブルシューティング
description: 既知の Microsoft Threat Protection の問題の解決策と対処方法を見つける
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844920"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Microsoft Threat Protection サービスに関する問題のトラブルシューティング

**適用対象:**
- Microsoft Threat Protection

このセクションでは、Microsoft Threat Protection サービスを使用するときに発生する可能性のある問題に対処します。


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Microsoft Threat Protection コンテンツが表示されない
ポータルでインシデント、アクションセンター、探している機能など、ナビゲーションウィンドウに機能が表示されない場合は、テナントに適切なライセンスがあることを確認する必要があります。 

詳細については、「[前提条件](prerequisites.md)」をご覧ください。

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Microsoft Threat Protection インシデントに Azure ATP アラートが表示されない
環境に Azure ATP が展開されていても、Microsoft Threat Protection インシデントの一部として Azure ATP アラートが表示されない場合は、Microsoft Cloud App Security および Azure ATP 統合が有効であることを確認する必要があります。 

詳細については、「[Azure ATP 統合](https://docs.microsoft.com/cloud-app-security/aatp-integration)」を参照してください。

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>サービスをオンにするための設定ページはどこにありますか。
Microsoft の脅威保護を有効にするには、Microsoft 365 セキュリティセンターのナビゲーションウィンドウの**設定**にアクセスします。 このナビゲーション項目は、[必要なアクセス許可とライセンス](mtp-enable.md#check-license-eligibility-and-required-permissions)がある場合にのみ表示されます。
 

