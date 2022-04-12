---
title: Microsoft Defender for Endpointに切り替える - 準備
description: Microsoft Defender for Endpointに切り替える準備をします。 デバイスを更新し、ネットワーク接続を構成します。
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
ms.openlocfilehash: c08ab1c96adc2b9d83cc6869573f2f0dbe75ac78
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782921"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Microsoft Defender for Endpoint - フェーズ 1: 準備に切り替える

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![フェーズ 1: 準備します。](images/phase-diagrams/prepare.png#lightbox)<br/>フェーズ 1: 準備 | [![フェーズ 2: 設定](images/phase-diagrams/setup.png#lightbox)](switch-to-mde-phase-2.md)<br/>[フェーズ 2: 設定](switch-to-mde-phase-2.md) | [![フェーズ 3: オンボード](images/phase-diagrams/onboard.png#lightbox)](switch-to-mde-phase-3.md)<br/>[フェーズ 3: オンボード](switch-to-mde-phase-3.md) |
|--|--|--|
|*お客様はここにいます。*| | |

**[Defender for Endpoint に切り替える](switch-to-mde-overview.md#the-migration-process)準備フェーズへようこそ**。

この移行フェーズには、次の手順が含まれます。

1. [組織全体のデバイスに更新プログラムを取得して展開する](#get-and-deploy-updates-across-your-organizations-devices)
2. [Defender for Endpoint を取得します](#get-microsoft-defender-for-endpoint)。
3. [Microsoft 365 Defender ポータルへのアクセスを許可します](#grant-access-to-the-microsoft-365-defender-portal)。
4. [デバイス プロキシとインターネット接続の設定を構成](#configure-device-proxy-and-internet-connectivity-settings)します。

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>組織全体のデバイスに更新プログラムを取得して展開する

ベスト プラクティスとして、組織のデバイスとエンドポイントを最新の状態に保ちます。 既存のエンドポイント保護とウイルス対策ソリューションが最新であり、組織のオペレーティング システムとアプリにも最新の更新プログラムがあることを確認します。 これを行うと、後で Defender for Endpoint と Microsoft Defender ウイルス対策に移行するときに問題を防ぐのに役立ちます。

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>既存のソリューションが最新であることを確認する

既存のエンドポイント保護ソリューションを最新の状態に保ち、組織のデバイスに最新のセキュリティ更新プログラムが適用されていることを確認します。

お困りの際は、 ソリューション プロバイダーのドキュメントを参照してください。

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>組織のデバイスが最新であることを確認する

組織のデバイスの更新に関するヘルプが必要ですか? 以下のリソースを参照してください。

|OS|リソース|
|---|---|
|Windows|[Microsoft Update](https://www.update.microsoft.com)|
|macOS|[Mac でソフトウェアを更新する方法](https://support.apple.com/HT201541)|
|iOS|[iPhone、iPad、または iPod touch を更新する](https://support.apple.com/HT204204)|
|Android|[Android のバージョンを更新&確認する](https://support.google.com/android/answer/7680439)|
|Linux|[Linux 101: システムの更新](https://www.linux.com/training-tutorials/linux-101-updating-your-system)|

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointを取得する

組織のデバイスを更新したので、次の手順では Defender for Endpoint を取得し、ライセンスを割り当て、サービスがプロビジョニングされていることを確認します。

1. Defender for Endpoint を今すぐ購入または試してください。 [無料試用版を開始するか、見積もりを要求します](https://aka.ms/mdatp)。

2. ライセンスが適切にプロビジョニングされていることを確認します。 [ライセンスの状態を確認します](production-deployment.md#check-license-state)。

3. Defender for Endpoint の専用クラウド インスタンスを設定します。 [Defender for Endpoint のセットアップ: テナント構成に関するページを参照してください](production-deployment.md#tenant-configuration)。

4. 組織内のエンドポイント (デバイスなど) がプロキシを使用してインターネットにアクセスする場合は、「 [Defender for Endpoint のセットアップ: ネットワーク構成](production-deployment.md#network-configuration)」を参照してください。

この時点で、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>を使用するセキュリティ管理者とセキュリティオペレーターにアクセス権を付与する準備が整いました。

> [!NOTE]
> Microsoft 365 Defender ポータルは、Defender for Endpoint ポータルとも<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a>呼ばれ、. 以前のMicrosoft Defender セキュリティ センター (https://securitycenter.windows.com) 間もなくMicrosoft 365 Defender ポータルにリダイレクトされます。 詳細については、[ポータルの概要Microsoft 365 Defender](portal-overview.md)参照してください。

## <a name="grant-access-to-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルへのアクセスを許可する

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>では、Defender for Endpoint の機能にアクセスして構成します。 詳細については、「[Microsoft 365 Defender ポータルの概要](use.md)」を参照してください。

Microsoft 365 Defender ポータルへのアクセス許可は、基本的なアクセス許可またはロールベースのアクセス制御 (RBAC) を使用して付与できます。 アクセス許可をより細かく制御できるように、RBAC を使用することをお勧めします。

1. セキュリティ管理者とセキュリティオペレーターのロールとアクセス許可を計画します。 [「ロールベースのアクセス制御」](prepare-deployment.md#role-based-access-control)を参照してください。

2. RBAC を設定して構成します。 特に組織[で Windows 10](/mem/intune/fundamentals/what-is-intune)、macOS、iOS、Android デバイスの組み合わせを使用している場合は、Intuneを使用して RBAC を構成することをお勧めします。 [Intuneを使用した RBAC の設定](/mem/intune/fundamentals/role-based-access-control)に関するページを参照してください。

    組織でIntune以外の方法が必要な場合は、次のいずれかのオプションを選択します。

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [高度なグループ ポリシーの管理](/microsoft-desktop-optimization-pack/agpm)
    
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)

3. Microsoft 365 Defender ポータルへのアクセス権を付与します。 (ヘルプが必要ですか? [RBAC を使用したポータル アクセスの管理に関するページを](rbac.md)参照してください。

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>デバイス プロキシとインターネット接続の設定を構成する

デバイスと Defender for Endpoint 間の通信を有効にするには、プロキシとインターネットの設定を構成します。 次の表に、さまざまなオペレーティング システムと機能のプロキシとインターネットの設定を構成するために使用できるリソースへのリンクを示します。

|機能|オペレーティング システム|リソース|
|---|---|---|
|[エンドポイントの検出と応答](overview-endpoint-detection-response.md) (EDR)|[Windows 10](/windows/release-health/release-information) 以降<br/><br/>Windows Server 2022 <br/><br/>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/>[Windows Server 1803 以降](/windows-server/get-started/whats-new-in-windows-server-1803)<br/><br/>[Windows Server 2016*](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/><br/>[Windows Server 2012 R2*](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)|[マシン プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md)|
|EDR [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/><br/>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/><br/>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)|[プロキシとインターネット接続の設定を構成する](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings)|
|EDR|macOS ([システム要件を](microsoft-defender-endpoint-mac.md)参照してください)|[macOS 上の Defender for Endpoint: ネットワーク接続](microsoft-defender-endpoint-mac.md#network-connections)|
|[Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)|[Windows 10](/windows/release-health/release-information) <br/><br/> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/><br/> Windows Server 2022 <br/><br/> [Windows Server 1803 以降](/windows-server/get-started/whats-new-in-windows-server-1803) <br/><br/> [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)<br/><br/>[Windows Server 2012 R2*](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)|[Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する](configure-network-connections-microsoft-defender-antivirus.md)|
|ウイルス対策|macOS ([システム要件を](microsoft-defender-endpoint-mac.md)参照してください)|[macOS 上の Defender for Endpoint: ネットワーク接続](microsoft-defender-endpoint-mac.md#network-connections)|
|ウイルス対策|Linux ( [システム要件を](microsoft-defender-endpoint-linux.md#system-requirements)参照)|[Linux 上の Defender for Endpoint: ネットワーク接続](microsoft-defender-endpoint-linux.md#network-connections)|

*Windows Server 2012 R2 と 2016 用の最新の統合ソリューションをインストールする必要があります。 詳細については、「[Windows サーバーをMicrosoft Defender for Endpoint サービスにオンボードする](/microsoft-365/security/defender-endpoint/configure-server-endpoints)」を参照してください。

## <a name="next-step"></a>次のステップ

**おめでとうございます**。 [Defender for Endpoint に切り替える](switch-to-mde-overview.md#the-migration-process)**準備** フェーズが完了しました。

- [Defender for Endpoint のセットアップに進みます](switch-to-mde-phase-2.md)。
