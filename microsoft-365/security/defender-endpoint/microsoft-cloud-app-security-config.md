---
title: Microsoft Defender for Cloud Apps を統合のために構成する
ms.reviewer: ''
description: 設定をオンにして、Microsoft Defender for Cloud AppsとのMicrosoft Defender for Endpoint統合を有効にする方法について説明します。
keywords: クラウド, アプリ, セキュリティ, 設定, 統合, 検出, レポート
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
ms.openlocfilehash: bd90c31ef961653e166672d1417003df2707e4c6
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560214"
---
# <a name="configure-microsoft-defender-for-cloud-apps-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for EndpointでMicrosoft Defender for Cloud Appsを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

クラウド アプリ検出シグナルMicrosoft Defender for Endpoint活用するには、Microsoft Defender for Cloud Apps統合を有効にします。

> [!NOTE]
> この機能は、[Windows 10とWindows 11](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)を実行しているデバイスでEnterprise Mobility + Security用の E5 ライセンスで使用できます。

> [!TIP]
> [Microsoft Defender for EndpointとMicrosoft Defender for Cloud Appsの詳細な統合については、Microsoft Defender for EndpointのMicrosoft Defender for Cloud Appsとの統合](/cloud-app-security/mde-integration)に関するページを参照してください。Microsoft Defender for Cloud Apps。

## <a name="enable-microsoft-defender-for-cloud-apps-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for EndpointでMicrosoft Defender for Cloud Appsを有効にする

1. ナビゲーション ウィンドウで、[基本設定] の **[** \> **詳細設定] 機能** を選択します。
2. **Microsoft Defender for Cloud Apps** を選択し、トグルを **[オン]** に切り替えます。
3. [ **保存] 環境設定をクリックします**。

アクティブ化されると、Microsoft Defender for EndpointはすぐにDefender for Cloud Apps への検出シグナルの転送を開始します。

## <a name="view-the-data-collected"></a>収集されたデータを表示する

Microsoft Cloud Apps Security でMicrosoft Defender for Endpointデータを表示してアクセスするには、「[Defender for Cloud Apps のデバイスを調査](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)する」を参照してください。

クラウド検出の詳細については、「検出 [されたアプリの操作](/cloud-app-security/discovered-apps)」を参照してください。

Microsoft Defender for Cloud Appsを試したい場合は、「Microsoft Defender for Cloud Apps[試用版」を](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)参照してください。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Cloud Apps統合](microsoft-cloud-app-security-integration.md)
