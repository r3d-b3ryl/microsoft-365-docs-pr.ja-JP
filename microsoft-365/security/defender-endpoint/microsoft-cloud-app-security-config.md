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
ms.openlocfilehash: f49050ff6ac4f283e8552073922517e9d59d6849
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213623"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Microsoft Defender Microsoft Cloud App Securityエンドポイントの構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint クラウド アプリ検出シグナルの恩恵を受けるには、統合を有効Microsoft Cloud App Securityしてください。

> [!NOTE]
> この機能は、E5 ライセンスを使用して[、Enterprise Mobility + Securityを実行](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)しているWindows 10 バージョン 1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)、Windows 10 バージョン 1803 (OS ビルド 17134.704 KB449364)、Windows 10 Version 1809 (OS ビルド 17763.379 および[KB4489899](https://support.microsoft.com/help/4489899)Windows 10 以降) [](https://support.microsoft.com/help/4493464)

> [Microsoft Defender for Endpoint とエンドポイント](/cloud-app-security/mde-integration)の詳細Microsoft Cloud App Security統合については、「Microsoft Defender for Endpoint integration with Microsoft Cloud App Security」を参照してください。

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>エンドポイントMicrosoft Cloud App Security Microsoft Defender でアプリを有効にする

1. ナビゲーション ウィンドウで、[基本設定] **セットアップの [高度な** \> **機能] を選択します**。
2. **[Microsoft Cloud App Security] を** 選択し、[オン] に切り替 **えます**。
3. [設定 **の保存] をクリックします**。

アクティブ化されると、Microsoft Defender for Endpoint は検出信号の転送を直ちに開始し、Cloud App Security。

## <a name="view-the-data-collected"></a>収集されたデータを表示する

Microsoft Cloud Apps Security で Microsoft Defender for Endpoint データを表示およびアクセスするには、「デバイスを調査する」を参照[Cloud App Security。](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)

クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](/cloud-app-security/discovered-apps)。

試しに興味がある場合は、「Microsoft Cloud App Security試用版[」をMicrosoft Cloud App Securityしてください](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>関連トピック

- [Microsoft Cloud App Security統合](microsoft-cloud-app-security-integration.md)
