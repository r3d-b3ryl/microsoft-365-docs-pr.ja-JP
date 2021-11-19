---
title: Microsoft Defender for Cloud Apps の統合を構成する
ms.reviewer: ''
description: Microsoft Defender for Endpoint と Microsoft Defender for Cloud Apps との統合を有効にする設定を有効にする方法について説明します。
keywords: クラウド、アプリ、セキュリティ、設定、統合、検出、レポート
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 88952a3f2c8173b20b8ee81322a0312144197ad5
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111605"
---
# <a name="configure-microsoft-defender-for-cloud-apps-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で Microsoft Defender for Cloud Apps を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint クラウド アプリ検出シグナルのメリットを得る場合は、Microsoft Defender for Cloud Apps の統合を有効にしてください。

> [!NOTE]
> この機能は、Windows 10 バージョン 1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)、Windows 10 バージョン 1803 (OS ビルド 17134.704 [KB449344)](https://support.microsoft.com/help/4493464)、Windows 10 Version 1809 [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) (OS ビルド 17763.379[および KB4489899)](https://support.microsoft.com/help/4489899)以降のバージョンWindows 10します。

> Microsoft Defender for Endpoint と Microsoft Defender for Cloud Apps の詳細な統合については [、「Microsoft Defender for](/cloud-app-security/mde-integration) Cloud Apps とのエンドポイント統合」を参照してください。

## <a name="enable-microsoft-defender-for-cloud-apps-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で Microsoft Defender for Cloud Apps を有効にする

1. ナビゲーション ウィンドウで、[基本設定] **セットアップの [高度な** \> **機能] を選択します**。
2. [Microsoft **Defender for Cloud Apps] を選択し** 、トグルを [オン] に **切り替えます**。
3. [設定 **の保存] をクリックします**。

アクティブ化されると、Microsoft Defender for Endpoint は検出信号の Defender for Cloud Apps への転送を直ちに開始します。

## <a name="view-the-data-collected"></a>収集されたデータを表示する

Microsoft Cloud Apps Security で Microsoft Defender for Endpoint データを表示およびアクセスするには、「Defender for Cloud Apps のデバイスを調査 [する」を参照してください](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。

クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](/cloud-app-security/discovered-apps)。

Microsoft Defender for Cloud Apps の試用に興味がある場合は [、「Microsoft Defender for Cloud Apps Trial」を参照してください](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Cloud Apps の統合](microsoft-cloud-app-security-integration.md)
