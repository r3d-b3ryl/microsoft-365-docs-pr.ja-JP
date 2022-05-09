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
ms.openlocfilehash: 83f0f53e2d2376975f853d826531e749732416b7
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754319"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointへのインターネット アクセスのないデバイスのオンボード

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


インターネット にアクセスできないデバイスをオンボードするには、次の一般的な手順を実行する必要があります。

> [!IMPORTANT] 
> 次の手順は、MMA ベースのソリューションを使用して以前のバージョンのWindowsを実行しているデバイスにのみ適用されます。 詳細については、「[Windows サーバーをMicrosoft Defender for Endpoint サービスにオンボードする](/microsoft-365/security/defender-endpoint/configure-server-endpoints)」を参照してください。

> [!NOTE]
> - OMS ゲートウェイ サーバーは、"TelemetryProxyServer" レジストリまたは GPO を使用して構成した場合、切断されたWindowsまたはWindowsサーバー デバイスのプロキシとして使用できません。
> - WindowsサーバーまたはWindows サーバーの場合は、TelemetryProxyServer を使用できますが、標準のプロキシ デバイスまたはアプライアンスを指す必要があります。
> - さらに、非接続環境のWindowsサーバーまたはWindows サーバーは、内部ファイルまたは Web サーバーを介して証明書信頼リストをオフラインで更新できる必要があります。
> - オフラインで CCTL を更新する方法の詳細については、「 [CTL ファイルをダウンロードするようにファイルまたは Web サーバーを構成する](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)」を参照してください。

オンボード方法の詳細については、次の記事を参照してください。
- [以前のバージョンの Windows をオンボードする](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Microsoft Defender for Endpoint サービスにサーバーをオンボードする](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [デバイス プロキシとインターネット接続の設定を構成する](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="devices-running-the-previous-mma-based-solution"></a>以前の MMA ベースのソリューションを実行しているデバイス

- プロキシまたはハブとして機能するように Azure Log Analytics (旧称 OMS ゲートウェイ) を設定します。
  - [Azure Log Analytics エージェント](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - Microsoft Monitoring Agent [(MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) ポイントから Defender for Endpoint Workspace キー & ID をインストールして構成する

[以前のバージョンの Windows をオンボードする](onboard-downlevel.md)

- Azure Log Analytics の同じネットワーク内のオフライン デバイス
  - 次を指すように MMA を構成します。
    - プロキシとしての Azure Log Analytics IP
    - Defender for Endpoint ワークスペース キー & ID

### <a name="azure-virtual-machines"></a>Azure 仮想マシン

- 前の MMA ベースのソリューションを実行しているデバイスの場合は、プロキシまたはハブとして機能するように Azure Log Analytics Gateway (以前は OMS ゲートウェイと呼ばられていました) を設定します。
    - [Azure Log Analytics Gateway](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - Microsoft Monitoring Agent [(MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) ポイントから Defender for Endpoint Workspace キー & ID をインストールして構成する
- OMS ゲートウェイの同じネットワーク内のオフライン Azure VM
    - Azure Log Analytics IP をプロキシとして構成する
    - Azure Log Analytics ワークスペース キー & ID
- Microsoft Defender for Cloud
    - [セキュリティ ポリシー \> Log Analytics ワークスペース](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [脅威検出 \> により Defender for Endpoint が自分のデータにアクセスできるようにする](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    詳細については、「 [セキュリティ ポリシーの操作](/azure/security-center/tutorial-security-policy)」を参照してください。
