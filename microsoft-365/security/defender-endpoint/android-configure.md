---
title: Android の機能でエンドポイント用 Microsoft Defender を構成する
description: Android のエンドポイント用 Microsoft Defender を構成する方法について説明します。
keywords: microsoft、 defender, atp, mde, android, configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8ec4a19bdd641c721bfcd7be2ceb59de1de92963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688035"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>Android の機能用に Defender for Endpoint を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Android 用エンドポイントの Defender を使用した条件付きアクセス  
Microsoft Defender for Endpoint on Android と Microsoft Intune、Azure Active Directory を組み合わせ、デバイスのリスク レベルに基づいてデバイスコンプライアンスと条件付きアクセス ポリシーを適用できます。 Defender for Endpoint は、Intune を介してこの機能を活用するために展開できるモバイル脅威防御 (MTD) ソリューションです。

Defender for Endpoint for Android および条件付きアクセスをセットアップする方法の詳細については [、「Defender for Endpoint and Intune」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。

## <a name="configure-custom-indicators"></a>カスタム インジケーターの構成  

> [!NOTE]
> Defender for Endpoint for Android では、IP アドレスと URL/ドメインのカスタム インジケーターの作成のみをサポートしています。

Defender for Endpoint for Android を使用すると、管理者は Android デバイスをサポートするカスタム インジケーターを構成できます。 カスタム インジケーターを構成する方法の詳細については、「指標の管理」 [を参照してください](manage-indicators.md)。

## <a name="configure-web-protection"></a>Web 保護の構成
Defender for Endpoint for Android では、IT 管理者は Web 保護機能を構成できます。 この機能は、Microsoft Endpoint Manager 管理センター内で使用できます。

> [!NOTE]
> Android 用エンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。 詳細については、「Android を実行 [するデバイスで Web 保護を構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。

## <a name="related-topics"></a>関連項目
- [Android 上のエンドポイント向け Microsoft Defender の概要](microsoft-defender-endpoint-android.md)
- [Microsoft Intune を使用して Android に Microsoft Defender for Endpoint を展開する](android-intune.md)
