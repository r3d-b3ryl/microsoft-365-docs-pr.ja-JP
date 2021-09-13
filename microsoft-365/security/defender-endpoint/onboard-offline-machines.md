---
title: Microsoft Defender for Endpoint へのインターネット アクセスのないオンボード デバイス
ms.reviewer: ''
description: センサー データを Microsoft Defender for Endpoint センサーに送信できるよう、インターネット にアクセスしないオンボード デバイス
keywords: オンボード、サーバー、VM、オンプレミス、oms ゲートウェイ、ログ分析、Azure ログ分析、mma
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
ms.openlocfilehash: d8e509aee364c54d1231c1a58115f65777022afb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192701"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint へのインターネット アクセスのないオンボード デバイス

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


インターネット にアクセスせずにデバイスをオンボードするには、次の一般的な手順を実行する必要があります。

> [!IMPORTANT] 
> 以下の手順は、以前のバージョンのデバイス (Windows以前または以前のバージョンWindows Server 2016デバイスWindows 8.1適用されます。

> [!NOTE]
> - 「TelemetryProxyServer」レジストリまたは GPO を使用して構成されている場合、接続されていない Windows 10 または Windows Server 2019 デバイスのプロキシとして OMS ゲートウェイ サーバーを使用することはできません。
> - サーバー 2019 Windows 10またはWindowsサーバー 2019 では、TelemetryProxyServer を使用する場合は、標準のプロキシ デバイスまたはアプライアンスを指している必要があります。
> - さらに、接続Windows 10環境Windowsサーバー 2019 の証明書信頼リストを、内部ファイルまたは Web サーバーを介してオフラインで更新できる必要があります。
> - オフラインでの CTL の更新の詳細については、「CTL ファイルをダウンロードするファイルまたは Web サーバーを構成する [」を参照してください](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files)。

オンボーディング方法の詳細については、次の記事を参照してください。
- [以前のバージョンの Windows をオンボードする](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Microsoft Defender for Endpoint サービスへのオンボード サーバー](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [デバイス プロキシとインターネット接続の設定を構成する](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a>オンプレミス デバイス

- プロキシまたはハブとして機能するように Azure Log Analytics (以前は OMS Gateway と呼ばれる) をセットアップします。
  - [Azure Log Analytics エージェント](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - エンドポイント ワークスペースキー id Microsoft Monitoring Agent Defender をポイントするコンピューター [(MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)ポイントをインストール&する

- Azure Log Analytics の同じネットワーク内のオフライン デバイス
  -  次の点を示す MMA を構成します。
     - プロキシとしての Azure Log Analytics IP
     - Defender for Endpoint workspace key & ID

## <a name="azure-virtual-machines"></a>Azure 仮想マシン
- [Azure Log Analytics ワークスペースの構成と有効化](/azure/azure-monitor/platform/gateway)

    - プロキシまたはハブとして機能するように Azure Log Analytics Gateway (以前は OMS ゲートウェイと呼ばれる) をセットアップします。
      - [Azure Log Analytics Gateway](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - エンドポイント ワークスペースキー id Microsoft Monitoring Agent Defender をポイントするコンピューター [(MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)ポイントをインストール&する
    - OMS ゲートウェイの同じネットワーク内のオフライン Azure VM
      - Azure Log Analytics IP をプロキシとして構成する
      - Azure Log Analytics Workspace Key & ID

    - Azure Defender
      - [セキュリティ ポリシー \> ログ分析ワークスペース](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [脅威検出 \> エンドポイントの Defender が自分のデータにアクセスできる](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        詳細については、「セキュリティ ポリシーの [操作」を参照してください](/azure/security-center/tutorial-security-policy)。
