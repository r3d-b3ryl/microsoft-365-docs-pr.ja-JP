---
title: エンドポイント用 Microsoft Defender に切り替える - オンボード
description: これは、Microsoft 以外のソリューションから Microsoft Defender for Endpoint に移行するフェーズ 3 オンボードです。
keywords: 移行, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 459a113bb28c4ae0fa7c4d4a0b004ad2badc0da8
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935919"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>エンドポイント向け Microsoft Defender への切り替え - フェーズ 3: オンボード

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![フェーズ 1: Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[フェーズ 1: 準備](switch-to-microsoft-defender-prepare.md) | [![フェーズ 2: 設定](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[フェーズ 2: 設定](switch-to-microsoft-defender-setup.md) | ![フェーズ 3: オンボード](images/phase-diagrams/onboard.png)<br/>フェーズ 3: オンボード |
|--|--|--|
|| |*お前はここにいる!* |


**エンドポイント用 Microsoft Defender への切り [替えのフェーズ](switch-to-microsoft-defender-migration.md#the-migration-process)3 へようこそ**。 この移行フェーズには、次の手順が含まれます。

1. [デバイスを Microsoft Defender for Endpoint にオンボードします](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [検出テストを実行します](#run-a-detection-test)。
3. [Microsoft 以外のソリューションをアンインストールします](#uninstall-your-non-microsoft-solution)。
4. [Microsoft Defender for Endpoint がアクティブ モードに設定されている必要があります](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

1. Microsoft Defender セキュリティ センター ( ) に移動 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) し、サインインします。
2. [設定 **]**  >  **[デバイス管理**  >  **オンボーディング] を選択します**。 
3. [オンボード **プロセスを開始するオペレーティング システムの選択] ボックスの一覧で** 、オペレーティング システムを選択します。 
4. [ **展開方法] で**、オプションを選択します。 リンクとプロンプトに従って、組織のデバイスをオンボードします。 サポートが必要な場合 [「Onboarding メソッド (この](#onboarding-methods)記事)」を参照してください。

### <a name="onboarding-methods"></a>オンボーディングメソッド
 
展開方法は、選択されているオペレーティング システムによって異なります。 オンボーディングのヘルプについては、以下の表に示すリソースを参照してください。

|オペレーティング システム  |メソッド  |
|---------|---------|
|Windows 10     |- [グループ ポリシー](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [モバイル デバイス管理 (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [ローカル スクリプト](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**注**: ローカル スクリプトは概念実証に適していますが、実稼働環境での展開には使用できません。 実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Intune を使用することをお勧めします。         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1エンタープライズ <br/>- Windows 7 SP1 Pro     | [Microsoft 監視エージェント](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**注**: Microsoft 監視エージェントは Azure Log Analytics エージェントです。 詳細については [、「Log Analytics エージェントの概要」を参照してください](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。        |
|- Windows Server 2019 以降 <br/>- Windows Server 2019 コア エディション <br/>- Windows Server バージョン 1803 以降 |- [ローカル スクリプト](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [グループ ポリシー](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [永続的でないデバイスの VDI オンボーディング スクリプト](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**注**: ローカル スクリプトは概念実証に適していますが、実稼働環境での展開には使用できません。 実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Intune を使用することをお勧めします。    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender セキュリティ センター](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 以上の LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Windows 以外のデバイスをオンボードする](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>検出テストを実行する

オンボードデバイスが Microsoft Defender for Endpoint に正しく接続されていることを確認するには、検出テストを実行できます。

|オペレーティング システム  |ガイダンス  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server バージョン 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |「 [検出テストを実行する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。 <br/><br/>Microsoft Defender for Endpoint デモ シナリオ サイト ( ) にアクセス [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) し、1 つ以上のシナリオを試してください。 たとえば、クラウド配信の **保護デモ シナリオを** 試してみてください。         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |で DIY アプリをダウンロードして使用します [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <br/><br/>詳細については [、「Microsoft Defender for Endpoint on macOS」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 以上の LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. 次のコマンドを実行し、1 の結果 **を探します**。 <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. ターミナル ウィンドウを開き、次のコマンドを実行します。 <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. 次のコマンドを実行して、検出された脅威を一覧表示します。 <br/>`mdatp threat list`. <br/><br/>詳細については [、「Microsoft Defender for Endpoint on Linux」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux)。 |

## <a name="uninstall-your-non-microsoft-solution"></a>Microsoft 以外のソリューションをアンインストールする

組織のデバイスを Microsoft Defender for Endpoint にオンボードしたので、次に、Microsoft 以外のエンドポイント保護ソリューションをアンインストールします。

この手順のヘルプを表示するには、ソリューション プロバイダーのテクニカル サポート チームに問い合わせください。

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Microsoft Defender for Endpoint がアクティブ モードにあるか確認する

Microsoft 以外のエンドポイント保護ソリューションをアンインストールしたので、次の手順では、Microsoft Defender Antivirus と Microsoft Defender for Endpoint が有効でアクティブ モードになっているか確認します。

これを行うには、Microsoft Defender for Endpoint デモ シナリオ サイト () をご覧ください [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 。 少なくとも次を含む、そのページで 1 つ以上のデモ シナリオを試してみてください。
- クラウドによる保護
- 望ましくない可能性のあるアプリケーション (PUA)
- ネットワーク保護 (NP)

> [!IMPORTANT]
> Windows Server 2016 を使用している場合は、Microsoft Defender ウイルス対策を手動で開始する必要があります。 これを行うには、デバイスで PowerShell コマンドレット `mpcmdrun.exe -wdenable` を使用します。

## <a name="next-steps"></a>次の手順

**おめでとう** ございます! エンドポイント用 Microsoft [Defender への移行が完了しました](switch-to-microsoft-defender-migration.md#the-migration-process)。 

- Microsoft Defender[セキュリティ センター ()](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)のセキュリティ操作ダッシュボードにアクセスします [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 
- [Microsoft Defender for Endpoint の管理、移行後](manage-atp-post-migration.md)。
