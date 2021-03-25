---
title: Microsoft Cloud App Security の統合を構成する
ms.reviewer: ''
description: 設定を有効にして、Microsoft Defender for Endpoint と Microsoft Cloud App Security の統合を有効にする方法について説明します。
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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068532"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で Microsoft Cloud App Security を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Microsoft Defender for Endpoint クラウド アプリ検出シグナルの恩恵を受けるには、Microsoft Cloud App Security 統合を有効にしてください。

>[!NOTE]
>この機能は、Windows 10 バージョン[](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)、Windows 10 を実行しているデバイスの E5 ライセンスで利用できます。 バージョン 1803 (OS ビルド 17134.704 [KB4493464)](https://support.microsoft.com/help/4493464)、Windows 10 バージョン 1809 (OS ビルド 17763.379 および[KB4489899)](https://support.microsoft.com/help/4489899)以降の Windows 10 バージョン。

> Microsoft Defender for Endpoint と Microsoft Cloud App Security の詳細な統合については、「Microsoft Defender for Endpoint integration with Microsoft Cloud App [Security」](https://docs.microsoft.com/cloud-app-security/mde-integration) を参照してください。 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>エンドポイント向け Microsoft Defender で Microsoft Cloud App Security を有効にする

1. ナビゲーション ウィンドウで、[基本設定]**セットアップの [高度な**  >  **機能] を選択します**。
2. [Microsoft **Cloud App Security] を選択** し、トグルを [オン] に **切り替えます**。
3. [設定 **の保存] をクリックします**。

アクティブ化されると、Microsoft Defender for Endpoint は検出信号のクラウド アプリ セキュリティへの転送を直ちに開始します。

## <a name="view-the-data-collected"></a>収集されたデータを表示する

Microsoft Cloud Apps Security で Microsoft Defender for Endpoint データを表示およびアクセスするには、「Cloud App Security でデバイスを調査する [」を参照してください](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。


クラウド検出の詳細については、「検出されたアプリを操作 [する」を参照してください](https://docs.microsoft.com/cloud-app-security/discovered-apps)。

Microsoft Cloud App Security の試用に興味がある場合は [、「Microsoft Cloud App Security Trial」を参照してください](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。

## <a name="related-topic"></a>関連トピック
- [Microsoft Cloud App Security の統合](microsoft-cloud-app-security-integration.md)
