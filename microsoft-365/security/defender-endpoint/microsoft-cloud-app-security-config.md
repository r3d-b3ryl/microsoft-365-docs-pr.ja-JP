---
title: Microsoft Cloud App Security との統合を構成する
ms.reviewer: ''
description: Microsoft Defender for Endpoint との統合を有効にする設定を有効にする方法についてMicrosoft Cloud App Security。
keywords: クラウド、アプリ、セキュリティ、設定、統合、検出、レポート
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f5e2919ae3fcbbb443f6d160c68633ee3427ae5a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187531"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Microsoft Defender Microsoft Cloud App Securityエンドポイントの構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Microsoft Defender for Endpoint クラウド アプリ検出シグナルの恩恵を受けるには、統合を有効Microsoft Cloud App Securityしてください。

>[!NOTE]
>この機能は[、Windows 10](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)バージョン 1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)を実行しているデバイスで Enterprise Mobility + Security の E5 ライセンスで使用できますWindows 10 バージョン 1803 (OS ビルド 17134.704 [KB4493464)](https://support.microsoft.com/help/4493464)、Windows 10 バージョン 1809 (OS ビルド 17763.379 および[KB4489899)](https://support.microsoft.com/help/4489899)以降の Windows 10 バージョン。

> [Microsoft Defender for Endpoint とエンドポイント](https://docs.microsoft.com/cloud-app-security/mde-integration)の詳細Microsoft Cloud App Security統合については、「Microsoft Defender for Endpoint integration with Microsoft Cloud App Security」を参照してください。 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>エンドポイントMicrosoft Cloud App Security Microsoft Defender でアプリを有効にする

1. ナビゲーション ウィンドウで、[基本設定]**セットアップの [高度な**  >  **機能] を選択します**。
2. **[Microsoft Cloud App Security] を** 選択し、[オン] に切り替 **えます**。
3. [設定 **の保存] をクリックします**。

アクティブ化されると、Microsoft Defender for Endpoint は検出信号の転送を直ちに開始し、Cloud App Security。

## <a name="view-the-data-collected"></a>収集されたデータを表示する

Microsoft Cloud Apps Security で Microsoft Defender for Endpoint データを表示およびアクセスするには、「デバイスを調査する」を参照[Cloud App Security。](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)


クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

試しに興味がある場合は、「Microsoft Cloud App Security試用版[」をMicrosoft Cloud App Securityしてください](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>関連トピック
- [Microsoft Cloud App Security統合](microsoft-cloud-app-security-integration.md)
