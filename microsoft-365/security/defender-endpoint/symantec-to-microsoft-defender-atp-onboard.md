---
title: Symantec to Microsoft Defender for Endpoint - Phase 3, Onboarding
description: これは、シマンテックから Microsoft Defender for Endpoint への移行のフェーズ 3 オンボーディングです。
keywords: 移行、 Windows Defender Advanced Threat Protection, atp, edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 1d332f6b0d6338d18c5a85dcf737f968f00f275f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689523"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Symantec から移行する - フェーズ 3: オンボードから Microsoft Defender for Endpoint

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![フェーズ 1: 準備](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[フェーズ 1: 準備](symantec-to-microsoft-defender-atp-prepare.md) |[![フェーズ 2: 設定](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[フェーズ 2: 設定](symantec-to-microsoft-defender-atp-setup.md) |![フェーズ 3: オンボード](images/phase-diagrams/onboard.png)<br/>フェーズ 3: オンボード |
|--|--|--|
|| |*お前はここにいる!* |


**シマンテックからエンドポイント用 Microsoft Defender への移行 [のフェーズ](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)3 へようこそ**。 この移行フェーズには、次の手順が含まれます。

1. [デバイスを Microsoft Defender for Endpoint にオンボードします](#onboard-devices-to-microsoft-defender-for-endpoint)。
2. [検出テストを実行します](#run-a-detection-test)。
3. [Symantec をアンインストールします](#uninstall-symantec)。
4. [Microsoft Defender for Endpoint がアクティブ モードに設定されている必要があります](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

1. Microsoft Defender セキュリティ センター ( ) に移動 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) し、サインインします。
2. [設定 **]**  >  **[デバイス管理**  >  **オンボーディング] を選択します**。 
3. [オンボード **プロセスを開始するオペレーティング システムの選択] ボックスの一覧で** 、オペレーティング システムを選択します。 
4. [ **展開方法] で**、オプションを選択します。 リンクとプロンプトに従って、組織のデバイスをオンボードします。 サポートが必要な場合 [「Onboarding メソッド (この](#onboarding-methods)記事)」を参照してください。

### <a name="onboarding-methods"></a>オンボーディングメソッド
 
展開方法は、選択されているオペレーティング システムによって異なります。 オンボーディングのヘルプについては、以下の表に示すリソースを参照してください。

|オペレーティング システム  |Method  |
|---------|---------|
|Windows 10     |- [グループ ポリシー](configure-endpoints-gp.md)<br/>- [Configuration Manager](configure-endpoints-sccm.md)<br/>- [モバイル デバイス管理 (Intune)](configure-endpoints-mdm.md)<br/>- [ローカル スクリプト](configure-endpoints-script.md) <br/><br/>**注**: ローカル スクリプトは概念実証に適していますが、実稼働環境での展開には使用できません。 実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Intune を使用することをお勧めします。         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1エンタープライズ <br/>- Windows 7 SP1 Pro     | [Microsoft 監視エージェント](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**注**: Microsoft 監視エージェントは Azure Log Analytics エージェントです。 詳細については [、「Log Analytics エージェントの概要」を参照してください](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。        |
|- Windows Server 2019 以降 <br/>- Windows Server 2019 コア エディション <br/>- Windows Server バージョン 1803 以降 |- [ローカル スクリプト](configure-endpoints-script.md) <br/>- [グループ ポリシー](configure-endpoints-gp.md) <br/>- [Configuration Manager](/configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [永続的でないデバイスの VDI オンボーディング スクリプト](configure-endpoints-vdi.md) <br/><br/>**注**: ローカル スクリプトは概念実証に適していますが、実稼働環境での展開には使用できません。 実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Intune を使用することをお勧めします。    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender セキュリティ センター](configure-server-endpoints.md)<br/>- [Azure セキュリティ センター](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 以上の LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Windows 以外のデバイスをオンボードする](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>検出テストを実行する

オンボードデバイスが Microsoft Defender for Endpoint に正しく接続されていることを確認するには、検出テストを実行できます。

|オペレーティング システム  |ガイダンス  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server バージョン 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |「 [検出テストを実行する」を参照してください](run-detection-test.md)。 <br/><br/>Microsoft Defender for Endpoint デモ シナリオ サイト ( ) にアクセス [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) し、1 つ以上のシナリオを試してください。 たとえば、クラウド配信の **保護デモ シナリオを** 試してみてください。         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |で DIY アプリをダウンロードして使用します [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。 <br/><br/>詳細については [、「Microsoft Defender for Endpoint on macOS」を参照してください](microsoft-defender-endpoint-mac.md)。        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 以上の LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. 次のコマンドを実行し、1 の結果 **を探します**。 <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. ターミナル ウィンドウを開き、次のコマンドを実行します。 <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. 次のコマンドを実行して、検出された脅威を一覧表示します。 <br/>`mdatp threat list`. <br/><br/>詳細については [、「Microsoft Defender for Endpoint on Linux」を参照してください](microsoft-defender-endpoint-linux.md)。 |

## <a name="uninstall-symantec"></a>Symantec のアンインストール

組織のデバイスを Microsoft Defender for Endpoint にオンボードしたので、次にシマンテック社をアンインストールします。

1. [シマンテックでタン](https://knowledge.broadcom.com/external/article?legacyId=tech192023) パープロテクションを無効にします。
2. Symantec のアンインストール パスワードを削除します。<br/>
   1. Windows デバイスで、管理者としてレジストリ エディターを開きます。
   2. `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC` に移動します。
   3. **SmcInstData という名前のエントリを探します**。 
   4. アイテムを右クリックし、[削除] を **選択します**。 
3. デバイスからシマンテックを削除します。 このヘルプが必要な場合は、Broadcom のドキュメントを参照してください。 Broadcom のリソースを次に示します。 
   - [Symantec エンドポイント保護のアンインストール](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - Windows デバイス: Windows [でエンドポイント保護 14 クライアントを手動でアンインストールする](https://knowledge.broadcom.com/external/article?articleId=170040)
   - macOS コンピューター: [RemoveSymantecMacFiles を使用して Mac 用の Symantec ソフトウェアを削除する](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Linux デバイス: Linux のエンドポイント保護に関 [するよく寄せられる質問](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Microsoft Defender for Endpoint がアクティブ モードにあるか確認する

Symantec をアンインストールしたので、次の手順では、Microsoft Defender Antivirus と Microsoft Defender for Endpoint が有効でアクティブ モードになっているか確認します。

これを行うには、Microsoft Defender for Endpoint デモ シナリオ サイト () をご覧ください [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 。 少なくとも次を含む、そのページで 1 つ以上のデモ シナリオを試してみてください。
- クラウドによる保護
- 望ましくない可能性のあるアプリケーション (PUA)
- ネットワーク保護 (NP)

> [!IMPORTANT]
> Windows Server 2016 を使用している場合は、Microsoft Defender ウイルス対策を手動で開始する必要があります。 これを行うには、デバイスで PowerShell コマンドレット `mpcmdrun.exe -wdenable` を使用します。

## <a name="next-steps"></a>次のステップ

**おめでとう** ございます! Symantec から [Microsoft Defender for Endpoint への移行が完了しました](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)。 
- Microsoft Defender[セキュリティ センター ()](security-operations-dashboard.md)のセキュリティ操作ダッシュボードにアクセスします [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 
- [Microsoft Defender for Endpoint の管理、移行後](manage-atp-post-migration.md)。
