---
title: Windows デバイスのオンボード ツールと方法
description: Microsoft Defender for Endpoint センサーにセンサー データを送信できるように、Windows デバイスをオンボードする
keywords: Windows デバイスのオンボード, グループ ポリシー, エンドポイント構成マネージャー, モバイル デバイス管理, ローカル スクリプト, gp, sccm, mdm, intune
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
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fbc5a0981a6318d767252e968e45874d889aee85
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64949103"
---
# <a name="onboarding-tools-and-methods-for-windows-devices-in-defender-for-endpoint"></a>Defender for Endpoint でデバイスをWindowsするためのツールとメソッドのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [エンドポイントのデータ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [インサイダー リスク管理](/microsoft-365/compliance/insider-risk-management)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint サービスがセンサー データを取得できるように、組織内のデバイスを構成する必要があります。 組織内のデバイスを構成するために使用できるさまざまな方法と展開ツールがあります。

一般に、オンボードするWindowsデバイスを特定し、デバイスまたは環境に適した対応するツールに従います。

:::image type="content" source="images/onboarding-config-tools.png" alt-text="オンボード ツールと方法" lightbox="images/onboarding-config-tools.png":::

## <a name="endpoint-onboarding-tools"></a>エンドポイントオンボーディング ツール

オンボードするWindows エンドポイントに応じて、次の表に示す対応するツールまたは方法を使用します。

デバイスWindows | オンボード ツールまたは方法
:---|:---
|<ul><li> Windows 10</li> <li>Windows Server 1803 と 2019、および 2022</li> <li>Windows Server 2012 R2 と 2016<sup>[[1](#fn1)]<sup></li></ul>  |   [ローカル スクリプト (最大 10 台のデバイス)](configure-endpoints-script.md)<br>   [グループ ポリシー](configure-endpoints-gp.md)<br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Microsoft エンドポイント マネージャー/ モバイル デバイス管理 (Intune)](configure-endpoints-mdm.md)<br>    [VDI スクリプト](configure-endpoints-vdi.md) <br><br> **注**: ローカル スクリプトは概念実証に適していますが、運用環境のデプロイには使用しないでください。 運用環境のデプロイでは、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはIntuneを使用することをお勧めします。
|<ul><li> Windows Server 2008 R2 SP1 </li></ul>| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br>[以前のバージョンのWindowsまたはMicrosoft Defender for Cloudをオンボード](onboard-downlevel.md)する[](/azure/security-center/security-center-wdatp) <br><br> **注**: Microsoft Monitoring Agentは Azure Log Analytics エージェントになりました。 詳細については、 [Log Analytics エージェントの概要に関する](/azure/azure-monitor/platform/log-analytics-agent)ページを参照してください。  
|<ul><li> Windows 7 SP1 </li> <li>  Windows 7 SP1 Pro </li> <li>  Windows 8.1 Pro </li> <li> Windows 8.1 Enterprise</li></ul>  | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **注**: Microsoft Monitoring Agentは Azure Log Analytics エージェントになりました。 詳細については、 [Log Analytics エージェントの概要に関する](/azure/azure-monitor/platform/log-analytics-agent)ページを参照してください。

(<a id="fn1">1</a>) Windows Server 2016およびWindows Server 2012 R2 は、オンボード Windows サーバーの手順に従[ってオンボード](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)する必要があります。

>[!IMPORTANT]
>Microsoft Defender for Endpoint Server SKU を購入するためには、以下のいずれか、Windows E5/A5、Microsoft 365 E5/A5、Microsoft 365 E5 Security のサブスクリプションライセンスを組み合わせて購入しておくことが必要です。  ライセンスの詳細については、「[製品使用条件](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all)」 を参照してください。  

トピック|説明
:---|:---
[グループ ポリシーを使用してデバイスをオンボードする](configure-endpoints-gp.md)|グループ ポリシーを使用して構成パッケージをデバイスに展開します。
[Microsoft Endpoint Configuration Manager を使用したデバイスのオンボード](configure-endpoints-sccm.md)|Microsoft エンドポイント マネージャー (現在のブランチ) バージョン 1606 または Microsoft エンドポイント マネージャー (現在のブランチ) バージョン 1602 以前を使用して、デバイスに構成パッケージを展開できます。
[モバイル デバイス管理ツールを使用したデバイスのオンボード](configure-endpoints-mdm.md)|モバイル デバイス管理ツールまたは Microsoft Intune を使用して、構成パッケージをデバイスに展開します。
[ローカル スクリプトを使用したデバイスのオンボード](configure-endpoints-script.md)|ローカル スクリプトを使用してエンドポイントに構成パッケージを展開する方法について説明します。
[非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](configure-endpoints-vdi.md)|構成パッケージを使用して VDI デバイスを構成する方法について説明します。

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)

デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。 詳細については、「[新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](run-detection-test.md)」 を参照してください。
