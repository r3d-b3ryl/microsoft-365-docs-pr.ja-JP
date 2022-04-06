---
title: '[ファイルに切りMicrosoft Defender for Endpoint - 準備]'
description: ユーザーに切り替える準備をMicrosoft Defender for Endpoint。 デバイスを更新し、ネットワーク接続を構成します。
keywords: 移行、Microsoft Defender for Endpoint、ベスト プラクティス
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-mcafeemigrate
- m365solution-symantecmigrate
ms.topic: article
ms.custom:
- migrationguides
- admindeeplinkDEFENDER
ms.date: 04/01/2022
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 33ad09cb87c80aecbaa72ebe9fb2b6523962498f
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634429"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>[次のMicrosoft Defender for Endpoint - フェーズ 1: 準備] に切り替えます。

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![フェーズ 1: 準備します。](images/phase-diagrams/prepare.png#lightbox)<br/>フェーズ 1: 準備 | [![フェーズ 2: 設定](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[フェーズ 2: 設定](switch-to-mde-phase-2.md) | [![フェーズ 3: オンボード](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[フェーズ 3: オンボード](switch-to-mde-phase-3.md) |
|--|--|--|
|*お前はここにいる!*| | |

**Defender for Endpoint への切り [替えの準備フェーズへようこそ](switch-to-mde-overview.md#the-migration-process)**。

この移行フェーズには、次の手順が含まれます。

1. [組織のデバイス全体で更新プログラムを取得して展開する](#get-and-deploy-updates-across-your-organizations-devices)
2. [エンドポイントの Defender を取得します](#get-microsoft-defender-for-endpoint)。
3. [ポータルへのアクセス権をMicrosoft 365 Defenderします](#grant-access-to-the-microsoft-365-defender-portal)。
4. [デバイス プロキシとインターネット接続の設定を構成します](#configure-device-proxy-and-internet-connectivity-settings)。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>組織のデバイス全体で更新プログラムを取得して展開する

ベスト プラクティスとして、組織のデバイスとエンドポイントを最新の状態に保ちます。 既存のエンドポイント保護とウイルス対策ソリューションが最新であり、組織のオペレーティング システムとアプリにも最新の更新プログラムが含まれています。 この機能を使用すると、Defender for Endpoint に移行した後で問題が発生Microsoft Defender ウイルス対策。

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>既存のソリューションが最新の情報を提供する

既存のエンドポイント保護ソリューションを最新の状態に保ち、組織のデバイスに最新のセキュリティ更新プログラムが含まれています。

お困りの際は、 ソリューション プロバイダーのドキュメントを参照してください。

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>組織のデバイスが最新の情報を提供する

組織のデバイスの更新に関するヘルプが必要ですか? 以下のリソースを参照してください。

|OS|リソース|
|---|---|
|Windows|[Microsoft Update](https://www.update.microsoft.com)|
|macOS|[Mac でソフトウェアを更新する方法](https://support.apple.com/HT201541)|
|iOS|[ユーザーのiPhone、iPad、または iPod touch を更新する](https://support.apple.com/HT204204)|
|Android|[Android &更新する方法を確認する](https://support.google.com/android/answer/7680439)|
|Linux|[Linux 101: システムの更新](https://www.linux.com/training-tutorials/linux-101-updating-your-system)|

## <a name="get-microsoft-defender-for-endpoint"></a>Get Microsoft Defender for Endpoint

組織のデバイスを更新したので、次の手順では、Defender for Endpoint を取得し、ライセンスを割り当て、サービスがプロビジョニングされているのを確認します。

1. Defender for Endpoint を今すぐ購入または試してみてください。 [無料試用版を開始するか、見積もりを要求します](https://aka.ms/mdatp)。

2. ライセンスが適切にプロビジョニングされていることを確認します。 [ライセンスの状態を確認します](production-deployment.md#check-license-state)。

3. Defender for Endpoint の専用クラウド インスタンスをセットアップします。 「 [Defender for Endpoint setup: Tenant configuration」を参照してください](production-deployment.md#tenant-configuration)。

4. 組織内のエンドポイント (デバイスなど) がプロキシを使用してインターネットにアクセスする場合は、「 [Defender for Endpoint setup: Network configuration」を参照してください](production-deployment.md#network-configuration)。

この時点で、管理者ポータルを使用するセキュリティ管理者とセキュリティオペレーターにアクセス権を付与<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderできます</a>。

> [!NOTE]
> ポータルMicrosoft 365 Defender Defender for Endpoint <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>ポータルと呼ばれる場合があります。. 前のMicrosoft Defender セキュリティ センター ( はhttps://securitycenter.windows.com)、すぐにポータルにMicrosoft 365 Defenderされます。 詳細については、「ポータルの概要Microsoft 365 Defender[」を参照してください](portal-overview.md)。

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>ポータルへのアクセス権をMicrosoft 365 Defenderする

この<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderは、</a>Defender for Endpoint の機能にアクセスして構成する場所です。 詳細については、「ポータルの[概要」をMicrosoft 365 Defenderしてください](use.md)。

基本的なアクセス許可Microsoft 365 Defenderロール ベースのアクセス制御 (RBAC) を使用して、ポータルへのアクセス許可を付与できます。 アクセス許可を細かく制御するには、RBAC を使用することをお勧めします。

1. セキュリティ管理者とセキュリティオペレーターの役割とアクセス許可を計画します。 「 [役割ベースのアクセス制御」を参照してください](prepare-deployment.md#role-based-access-control)。

2. RBAC を設定して構成します。 特に、組織[で](/mem/intune/fundamentals/what-is-intune) Intune、macOS、iOS、および Android デバイスの組み合わせを使用している場合は、WINDOWS 10を使用して RBAC を構成することをお勧めします。 詳細については[、「RBAC のセットアップ」を参照Intune](/mem/intune/fundamentals/role-based-access-control)。

    組織で他の方法が必要なIntune、次のいずれかのオプションを選択します。

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [高度なグループ ポリシーの管理](/microsoft-desktop-optimization-pack/agpm)
    
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. ポータルへのアクセス権をMicrosoft 365 Defenderします。 (ヘルプが必要ですか? 「 [RBAC を使用したポータル アクセスの管理」を参照してください](rbac.md)。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>デバイス プロキシとインターネット接続の設定を構成する

デバイスと Defender for Endpoint 間の通信を有効にするには、プロキシとインターネットの設定を構成します。 次の表に、さまざまなオペレーティング システムと機能のプロキシとインターネット設定を構成するために使用できるリソースへのリンクを示します。

|機能|オペレーティング システム|リソース|
|---|---|---|
|[エンドポイントの検出と応答](overview-endpoint-detection-response.md) (EDR)|[Windows 10](/windows/release-health/release-information)以降<br/><br/>Windows Server 2022 <br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/>[Windows Server 1803 以降](/windows-server/get-started/whats-new-in-windows-server-1803)|[コンピューター プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)|
|EDR|[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|[プロキシとインターネット接続の設定を構成する](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings)|
|EDR|macOS (「 [システム要件」を参照)](microsoft-defender-endpoint-mac.md)|[macOS 上のエンドポイントの Defender: ネットワーク接続](microsoft-defender-endpoint-mac.md#network-connections)|
|[Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)|[Windows 10](/windows/release-health/release-information)以降 <br/><br/>Windows Server 2022 <br/><br/> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/> [Windows Server 1803 以降](/windows-server/get-started/whats-new-in-windows-server-1803) <br/><br/> [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)|[Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](configure-network-connections-microsoft-defender-antivirus.md)|
|ウイルス対策|macOS (「 [システム要件」を参照)](microsoft-defender-endpoint-mac.md)|[macOS 上のエンドポイントの Defender: ネットワーク接続](microsoft-defender-endpoint-mac.md#network-connections)|
|ウイルス対策|Linux (「 [システム要件」を参照](microsoft-defender-endpoint-linux.md#system-requirements))|[Defender for Endpoint on Linux: Network connections](microsoft-defender-endpoint-linux.md#network-connections)|

## <a name="next-step"></a>次のステップ

**おめでとう** ございます! Defender for Endpoint への **切り替** えの [準備フェーズが完了しました](switch-to-mde-overview.md#the-migration-process)。

- [[Defender for Endpoint] のセットアップに進みます](switch-to-mde-phase-2.md)。
