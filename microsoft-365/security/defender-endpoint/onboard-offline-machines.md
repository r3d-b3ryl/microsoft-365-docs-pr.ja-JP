---
title: Microsoft Defender for Endpointへのインターネット アクセスのないデバイスのオンボード
ms.reviewer: ''
description: センサー データをMicrosoft Defender for Endpoint センサーに送信できるように、インターネット にアクセスできないデバイスをオンボードする
keywords: オンボード, サーバー, VM, オンプレミス, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: 33b539018f479c1b023a656ab056ca892d27e526
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822183"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointへのインターネット アクセスのないデバイスのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

インターネットに直接接続されていないデバイスの場合は、プロキシ ソリューションを使用することをお勧めします。 前の MMA ベースのソリューションを使用してオンボードされた古い Windows デバイスの場合、OMS ゲートウェイ ソリューションを使用すると、別の方法が提供されます。 オンボード方法の詳細については、次の記事を参照してください。
- [以前のバージョンの Windows をオンボードする](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Microsoft Defender for Endpoint サービスにサーバーをオンボードする](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)

> [!IMPORTANT]
> - 切断された環境の Windows または Windows Server は、内部ファイルまたは Web サーバーを使用して証明書信頼リストをオフラインで更新できる必要があります。
> - オフラインで CCTL を更新する方法の詳細については、「 [CTL ファイルをダウンロードするようにファイルまたは Web サーバーを構成する](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)」を参照してください。

## <a name="devices-running-windows-10-or-later-windows-server-2012-r2-or-later-linux-and-macos"></a>Windows 10以降、Windows Server 2012 R2 以降、Linux および macOS を実行しているデバイス

オペレーティング システムに応じて、Microsoft Defender for Endpointに使用するプロキシは、通常、自動検出または自動構成ファイルを使用するか、デバイスで実行されている Defender for Endpoint サービスに静的に固有のプロキシを自動的に構成できます。

- Windows デバイスの場合は、「[デバイス プロキシとインターネット接続の設定を構成](/microsoft-365/security/defender-endpoint/configure-proxy-internet)する」を参照してください
- Linux デバイスの場合は、「[静的プロキシ検出用に Linux でMicrosoft Defender for Endpointを構成する」を](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration)参照してください
- macOS デバイスの場合は、[Mac のMicrosoft Defender for Endpointを](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac#network-connections)参照してください

## <a name="windows-devices-running-the-previous-mma-based-solution"></a>以前の MMA ベースのソリューションを実行している Windows デバイス

> [!NOTE]
> - OMS ゲートウェイ サーバーは、"TelemetryProxyServer" レジストリまたは GPO を使用して構成すると、切断された Windows デバイスまたは Windows Server デバイスのプロキシとして使用できません。
> - Windows または Windows Server の場合 - TelemetryProxyServer を使用できますが、標準のプロキシ デバイスまたはアプライアンスを指す必要があります。

- プロキシまたはハブとして機能するように Azure Log Analytics (旧称 OMS ゲートウェイ) を設定します。
  - [Azure Log Analytics エージェント](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) ポイントから Defender for Endpoint Workspace キー & ID をインストールして構成する

[以前のバージョンの Windows をオンボードする](onboard-downlevel.md)

### <a name="microsoft-defender-for-cloud"></a>Microsoft Defender for Cloud

- [Defender for Cloud の統合 EDR ソリューションでエンドポイントを保護する: Microsoft Defender for Endpoint](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows#prerequisites)
