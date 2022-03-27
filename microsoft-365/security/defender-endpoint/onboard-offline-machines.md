---
title: Microsoft Defender for Endpoint へのインターネット アクセスのないオンボード デバイス
ms.reviewer: ''
description: センサー データを Microsoft Defender for Endpoint センサーに送信できるよう、インターネット にアクセスしないオンボード デバイス
keywords: オンボード、サーバー、VM、オンプレミス、oms ゲートウェイ、ログ分析、Azure ログ分析、mma
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
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint へのインターネット アクセスのないオンボード デバイス

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


インターネット にアクセスせずにデバイスをオンボードするには、次の一般的な手順を実行する必要があります。

> [!IMPORTANT] 
> 次の手順は、MMA ベースのソリューションを使用して以前Windowsを実行しているデバイスにのみ適用されます。 詳細については、「オンボード サーバー [Windows Microsoft Defender for Endpoint サービス」を参照してください](/microsoft-365/security/defender-endpoint/configure-server-endpoints)。

> [!NOTE]
> - OMS ゲートウェイ サーバーは、"TelemetryProxyServer" レジストリまたは GPO を介して構成されている場合、Windows または Windows Server デバイスの切断されたデバイスのプロキシとして使用できません。
> - サーバー WindowsまたはWindows - TelemetryProxyServer を使用する場合は、標準のプロキシ デバイスまたはアプライアンスを指している必要があります。
> - さらに、接続されていないWindowsまたはWindowsサーバーで、内部ファイルまたは Web サーバーを介して証明書信頼リストをオフラインで更新できる必要があります。
> - オフラインでの CTL の更新の詳細については、「CTL ファイルをダウンロードするファイルまたは Web サーバーを構成する [」を参照してください](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。

オンボーディング方法の詳細については、次の記事を参照してください。
- [以前のバージョンの Windows をオンボードする](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Microsoft Defender for Endpoint サービスへのオンボード サーバー](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [デバイス プロキシとインターネット接続の設定を構成する](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="devices-running-the-previous-mma-based-solution"></a>以前の MMA ベースのソリューションを実行しているデバイス

- プロキシまたはハブとして機能するように Azure Log Analytics (以前は OMS Gateway と呼ばれる) をセットアップします。
  - [Azure Log Analytics エージェント](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [エンドポイント ワークスペース キー id Microsoft Monitoring Agent Defender をポイントするコンピューター (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) ポイントをインストール&する

[以前のバージョンの Windows をオンボードする](onboard-downlevel.md)

- Azure Log Analytics の同じネットワーク内のオフライン デバイス
  - 次の点を示す MMA を構成します。
    - プロキシとしての Azure Log Analytics IP
    - Defender for Endpoint workspace key & ID

### <a name="azure-virtual-machines"></a>Azure 仮想マシン

- 以前の MMA ベースのソリューションを実行しているデバイスの場合、プロキシまたはハブとして機能するように Azure Log Analytics Gateway (以前は OMS ゲートウェイと呼ばれる) をセットアップします。
    - [Azure Log Analytics Gateway](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [エンドポイント ワークスペース キー id Microsoft Monitoring Agent Defender をポイントするコンピューター (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) ポイントをインストール&する
- OMS ゲートウェイの同じネットワーク内のオフライン Azure VM
    - Azure Log Analytics IP をプロキシとして構成する
    - Azure Log Analytics Workspace Key & ID
- Microsoft Defender for Cloud
    - [セキュリティ ポリシー \> ログ分析ワークスペース](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [脅威検出 エンドポイント \> の Defender が自分のデータにアクセスできる](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    詳細については、「セキュリティ ポリシーの [操作」を参照してください](/azure/security-center/tutorial-security-policy)。
