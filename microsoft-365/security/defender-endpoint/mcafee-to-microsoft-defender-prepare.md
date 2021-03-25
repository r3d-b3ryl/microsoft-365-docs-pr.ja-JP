---
title: McAfee to Microsoft Defender for Endpoint - Prepare
description: これはフェーズ 1 の準備で、McAfee から Microsoft Defender ATP に移行します。
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: adc8c1259be1e226bf1c2592090cf6008c976cf8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186631"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>McAfee からの移行 - フェーズ 1: 移行の準備

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![フェーズ 1: 準備](images/phase-diagrams/prepare.png)<br/>フェーズ 1: 準備 |[![フェーズ 2: セットアップ](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[フェーズ 2: セットアップ](mcafee-to-microsoft-defender-setup.md) |[![フェーズ 3: オンボード](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[フェーズ 3: オンボード](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*お前はここにいる!*| | |


**McAfee Endpoint [Security (McAfee)](mcafee-to-microsoft-defender-migration.md#the-migration-process)** から Microsoft Defender for Endpoint への移行の準備フェーズへようこそ。 

この移行フェーズには、次の手順が含まれます。
1. [組織のデバイス全体で更新プログラムを取得して展開する](#get-and-deploy-updates-across-your-organizations-devices)
2. [エンドポイントの Microsoft Defender を取得します](#get-microsoft-defender-for-endpoint)。
3. [Microsoft Defender セキュリティ センターへのアクセスを許可します](#grant-access-to-the-microsoft-defender-security-center)。
4. [デバイス プロキシとインターネット接続の設定を構成します](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>組織のデバイス全体で更新プログラムを取得して展開する

ベスト プラクティスとして、組織のデバイスとエンドポイントを最新の状態に保ちます。 McAfee Endpoint Security (McAfee) ソリューションが最新であり、組織のオペレーティング システムとアプリにも最新の更新プログラムが含まれています。 これで、後で Microsoft Defender for Endpoint および Microsoft Defender Antivirus に移行する際に問題を防ぐのに役立ちます。

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>McAfee ソリューションが最新の情報に更新されていないことを確認する

McAfee を最新の状態に保ち、組織のデバイスに最新のセキュリティ更新プログラムがインストールされている必要があります。 サポートが必要な場合 McAfee のリソースの一部を次に示します。

- [McAfee Enterprise 製品ドキュメント: エンドポイント セキュリティのしくみ](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [McAfee Knowledge Center テクニカル 記事: Windows セキュリティ センターが Windows 10 で実行するときにエンドポイント セキュリティが無効になっていると断続的に間違って報告する](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [McAfee Knowledge Center テクニカル 記事: Windows セキュリティ センターは、エンドポイント セキュリティの実行中にエンドポイント セキュリティが無効になっていると報告します](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- McAfee サポート ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>組織のデバイスが最新の情報を提供する

組織のデバイスの更新に関するヘルプが必要ですか? 以下のリソースを参照してください。

|OS | リソース |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Mac でソフトウェアを更新する方法](https://support.apple.com/HT201541)|
|iOS |[iPhone、iPad、または iPod touch を更新する](https://support.apple.com/HT204204)|
|Android |[Android &更新する方法を確認する](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: システムの更新](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender を取得する

組織のデバイスを更新したので、次の手順は、Microsoft Defender for Endpoint を取得し、ライセンスを割り当て、サービスがプロビジョニングされているのを確認します。

1. Microsoft Defender for Endpoint を今すぐ購入または試してみてください。 [無料試用版を開始するか、見積もりを要求します](https://aka.ms/mdatp)。 

2. ライセンスが適切にプロビジョニングされていることを確認します。 [ライセンスの状態を確認します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)。

3. グローバル管理者またはセキュリティ管理者として、Microsoft Defender for Endpoint の専用クラウド インスタンスをセットアップします。 「Microsoft [Defender for Endpoint setup: Tenant configuration」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration)。

4. 組織内のエンドポイント (デバイスなど) がプロキシを使用してインターネットにアクセスする場合は [、「Microsoft Defender for Endpoint setup: Network configuration」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)。
 
この時点で、Microsoft Defender セキュリティ センター () を使用するセキュリティ管理者およびセキュリティオペレーターにアクセス権を付与する準備ができました [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。 

> [!NOTE]
> Microsoft Defender セキュリティ センターは、Microsoft Defender for Endpoint ポータルと呼ばれる場合があります。 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Microsoft Defender セキュリティ センターへのアクセスを許可する

Microsoft Defender セキュリティ センター ( ) は、Microsoft Defender for Endpoint の機能にアクセスして構成 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) する場所です。 詳細については [、「Microsoft Defender セキュリティ センターの概要」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。

Microsoft Defender セキュリティ センターへのアクセス許可は、基本的なアクセス許可または役割ベースのアクセス制御 (RBAC) を使用して付与できます。 アクセス許可を細かく制御するには、RBAC を使用することをお勧めします。

1. セキュリティ管理者とセキュリティオペレーターの役割とアクセス許可を計画します。 「 [役割ベースのアクセス制御」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control)。

2. RBAC を設定して構成します。 Intune を使用 [して RBAC](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) を構成することをお勧めします。特に、組織で Windows 10、macOS、iOS、および Android デバイスの組み合わせを使用している場合。 Intune を [使用した RBAC のセットアップを参照してください](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。

    組織で Intune 以外の方法が必要な場合は、次のいずれかのオプションを選択します。
    - [構成マネージャー](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高度なグループ ポリシーの管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows 管理センター](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. Microsoft Defender セキュリティ センターへのアクセスを許可します。 (ヘルプが必要ですか? 「RBAC [を使用したポータル アクセスの管理」を参照](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)してください。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>デバイス プロキシとインターネット接続の設定を構成する

デバイスと Microsoft Defender for Endpoint 間の通信を有効にするには、プロキシとインターネットの設定を構成します。 次の表に、さまざまなオペレーティング システムと機能のプロキシとインターネット設定を構成するために使用できるリソースへのリンクを示します。

|機能  | オペレーティング システム | リソース |
|--|--|--|
|[エンドポイントの検出と応答](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 以降](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[コンピューター プロキシとインターネット接続の設定を構成する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[プロキシとインターネット接続の設定を構成する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint for Mac: ネットワーク接続](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 以降](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|ウイルス対策 |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra) |[Microsoft Defender for Endpoint for Mac: ネットワーク接続](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|ウイルス対策 |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 以上の LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender for Endpoint for Linux: ネットワーク接続](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a>次の手順

**おめでとう** ございます! McAfee からMicrosoft Defender for Endpoint への移行の[準備フェーズが完了しました](mcafee-to-microsoft-defender-migration.md#the-migration-process)。

- [[エンドポイント用 Microsoft Defender のセットアップ] に進みます](mcafee-to-microsoft-defender-setup.md)。
