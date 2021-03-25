---
title: Symantec to Microsoft Defender for Endpoint - フェーズ 1, Preparing
description: これは、シマンテックから Microsoft Defender for Endpoint への移行のフェーズ 1 準備です。
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
ms.openlocfilehash: 8784c8d608666946461ddc27aa2e7f2b740276a0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185493"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Symantec からの移行 - フェーズ 1: 移行の準備

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![フェーズ 1: 準備](images/phase-diagrams/prepare.png)<br/>フェーズ 1: 準備 |[![フェーズ 2: セットアップ](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[フェーズ 2: セットアップ](symantec-to-microsoft-defender-atp-setup.md) |[![フェーズ 3: オンボード](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[フェーズ 3: オンボード](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*お前はここにいる!*| | |


**Symantec から [Microsoft Defender](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)** for Endpoint への移行の準備フェーズへようこそ。 

この移行フェーズには、次の手順が含まれます。
1. [エンドポイントの Microsoft Defender を取得します](#get-microsoft-defender-for-endpoint)。
2. [Microsoft Defender セキュリティ センターへのアクセスを許可します](#grant-access-to-the-microsoft-defender-security-center)。
3. [デバイス プロキシとインターネット接続の設定を構成します](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender を取得する

開始するには、ライセンスが割り当ておよびプロビジョニングされた Microsoft Defender for Endpoint が必要です。

1. Microsoft Defender for Endpoint を今すぐ購入または試してみてください。 [Microsoft Defender for Endpoint にアクセスして無料試用版を開始するか、見積もりを要求します](https://aka.ms/mdatp)。 
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
2. RBAC を設定して構成します。 Intune を使用 [して RBAC](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) を構成することをお勧めします。特に、組織で Windows 10、macOS、iOS、および Android デバイスの組み合わせを使用している場合。 Intune を [使用した RBAC のセットアップを参照してください](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)。<br/>
   組織で Intune 以外の方法が必要な場合は、次のいずれかのオプションを選択します。
    - [構成マネージャー](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [高度なグループ ポリシーの管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows 管理センター](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. Microsoft Defender セキュリティ センターへのアクセスを許可します。 (ヘルプが必要ですか? 「RBAC [を使用したポータル アクセスの管理」を参照](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)してください。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>デバイス プロキシとインターネット接続の設定を構成する

デバイスと Microsoft Defender for Endpoint 間の通信を有効にするには、プロキシとインターネットの設定を構成します。 次の表に、さまざまなオペレーティング システムと機能のプロキシとインターネット設定を構成するために使用できるリソースへのリンクを示します。

|機能  | オペレーティング システム | リソース |
|:----|:----|:---|
|[エンドポイントの検出と応答](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 以降](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[コンピューター プロキシとインターネット接続の設定を構成する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[プロキシとインターネット接続の設定を構成する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint for Mac: ネットワーク接続](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 以降](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|ウイルス対策 |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra) |[Microsoft -Defender for Endpoint for Mac: ネットワーク接続](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|ウイルス対策 |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS 以上の LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender for Endpoint for Linux: ネットワーク接続](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>次の手順

**おめでとう** ございます! Symantec から **Microsoft** Defender for Endpoint への移行の [準備フェーズが完了しました](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)。
- [[エンドポイント用 Microsoft Defender のセットアップ] に進みます](symantec-to-microsoft-defender-atp-setup.md)。
