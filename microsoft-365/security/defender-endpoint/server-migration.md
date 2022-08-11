---
title: 新しいバージョンのMicrosoft Defender for Endpointのサーバー移行シナリオ
description: 前の MMA ベースのソリューションから現在の Defender for Endpoint 統合ソリューション パッケージにサーバーを移行する方法の概要については、この記事を参照してください。
keywords: migrate server, server, 2012r2, 2016, サーバー移行, デバイス管理, Microsoft Defender for Endpoint サーバーの構成, Microsoft Defender for Endpoint サーバーのオンボード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
ms.date: 08/10/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c9eff6831f08a243aad830d258c9d9277a89531
ms.sourcegitcommit: 34910ea9318289d78c35b0e7990238467c05384b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67306420"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>前の MMA ベースのMicrosoft Defender for Endpoint ソリューションからのサーバー移行シナリオ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> インストールまたはアップグレードを続行する前に、常にオペレーティング システムとWindows Server 2016の Microsoft Defender ウイルス対策が完全に更新されていることを確認してください。 EDR センサー コンポーネントの定期的な製品の機能強化と修正プログラムを受け取るには、インストール後Windows Update [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277) が適用または承認されていることを確認します。 さらに、保護コンポーネントを更新し続けるためには、 [Microsoft Defender ウイルス対策の更新プログラムの管理に関するページを参照し、ベースラインを適用してください](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

これらの手順は、Windows Server 2012 R2 およびWindows Server 2016用のMicrosoft Defender for Endpointの新しい統合ソリューションとインストーラー (MSI) パッケージに適用されます。 この記事では、前のソリューションから現在のソリューションまで、さまざまな移行シナリオに関する高度な手順について説明します。 これらの高レベルの手順は、環境で使用可能なデプロイ ツールと構成ツールに合わせて調整するためのガイドラインとして意図されています。 

**Microsoft Defender for Cloud を使用してデプロイを実行している場合は、インストールとアップグレードを自動化できます。[Defender for Servers プラン 2 と MDE 統合ソリューションの統合](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534)を参照してください**

> [!NOTE]
> Microsoft Defender for Endpointがインストールされているオペレーティング システムのアップグレードはサポートされていません。 オフボードでアンインストールし、オペレーティング システムをアップグレードしてから、インストールを続行してください。

> [!NOTE]
> 自動化されたアップグレードを実行するための完全な Microsoft Endpoint Configuration Manager自動化と統合は、MECM の後のリリースで利用できます。 最新の修正プログラム ロールアップを使用した 2107 リリースから、構成だけでなく、グループ ポリシー、PowerShell、Microsoft エンドポイント マネージャー テナントのアタッチ、またはローカル構成にも Endpoint Protection ノードを使用できます。 さらに、Microsoft Endpoint Configuration Managerの既存の機能を利用して、手動アップグレード手順を自動化できます。この方法については、以下で説明します。

## <a name="installer-script"></a>インストーラー スクリプト

>[!NOTE]
>スクリプトを実行するマシンがスクリプトの実行をブロックしていないことを確認します。 PowerShell の推奨実行ポリシー設定は Allsigned です。 スクリプトがエンドポイントで SYSTEM として実行されている場合は、スクリプトの署名証明書をローカル コンピューターの信頼された発行元ストアにインポートする必要があります。

自動アップグレードを実行するために Microsoft Endpoint Configuration Managerがまだ利用できない場合や更新されていない場合は、アップグレードを容易にするために、この[アップグレード スクリプト](https://github.com/microsoft/mdefordownlevelserver)を使用できます。 [コード] ボタンを選択し、.zip ファイルをダウンロードし、install.ps1を抽出してダウンロードします。 次の必要な手順を自動化するのに役立ちます。

1. Microsoft Defender for Endpointの OMS ワークスペースを削除します (省略可能)。
2. インストールされている場合は、System Center Endpoint Protection (SCEP) クライアントを削除します。
3. 必要に応じて、(Windows Server 2012 R2) [前提条件を](configure-server-endpoints.md#prerequisites)ダウンロードしてインストールします。
4. Microsoft Defender for Endpointをインストールします。
5. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。

スクリプトを使用するには、インストール パッケージとオンボード パッケージを配置したインストール ディレクトリにダウンロードします ( [サーバー エンドポイントの構成](configure-server-endpoints.md)に関するページを参照してください。

例: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager移行シナリオ 

>[!NOTE]
>Endpoint Protection ポリシーの構成を実行するには、Microsoft Endpoint Configuration Manager バージョン 2107 以降が必要です。

Microsoft Endpoint Configuration Managerバージョン 2207 より前のバージョンを使用して移行する方法については、「[Microsoft Monitoring Agent から統合ソリューションへのサーバーの移行](/microsoft-365/security/defender-endpoint/application-deployment-via-mecm)」を参照してください。

## <a name="if-you-are-running-a-non-microsoft-antivirus-solution"></a>Microsoft 以外のウイルス対策ソリューションを実行している場合

1. Microsoft Defender ウイルス対策 (Windows Server 2016) を含むコンピューターを完全に更新し[、前提条件](configure-server-endpoints.md#prerequisites)が満たされていることを確認します。 満たす必要がある前提条件の詳細については、「[Windows Server 2016の前提条件」を参照してください](configure-server-endpoints.md#prerequisites-for-windows-server-2016)。
2. サード パーティのウイルス対策管理で、これらのマシンにウイルス対策エージェントがプッシュされなくなったことを確認します。
3. Microsoft Defender for Endpointの保護機能に対するポリシーを作成し、任意のツールでコンピューターにターゲットを設定します。
4. Windows Server 2012 R2 および 2016 パッケージのMicrosoft Defender for Endpointをインストールし、**パッシブ モードを有効にします**。 [コマンド ラインを使用した Microsoft Defender ウイルス対策のインストールに関するページを](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)参照してください。
   a. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。
5. 更新プログラムを適用します。
6. Microsoft 以外のウイルス対策コンソールを使用するか、必要に応じて Microsoft Endpoint Configuration Managerを使用して、Microsoft 以外のウイルス対策ソフトウェアを削除します。 必ずパッシブ モード構成を削除してください。*

> [!TIP]
> [インストーラー スクリプト](server-migration.md#installer script)をアプリケーションの一部として使用して、上記の手順を自動化できます。 パッシブ モードを有効にするには、-Passive フラグを適用します。 たとえば、.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*これらの手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 Microsoft [Defender ウイルス対策とMicrosoft Defender for Endpointに関](why-use-microsoft-defender-antivirus.md)するページを参照してください。

パッシブ モードからマシンを移動するには、次のキーを 0 に設定します。

パス: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode 型: REG_DWORD値: 0

## <a name="if-you-are-running-system-center-endpoint-protection-but-are-not-managing-the-machine-using-microsoft-endpoint-configuration-manager-mecmconfigmgr"></a>System Center Endpoint Protectionを実行しているが、Microsoft Endpoint Configuration Manager (MECM/ConfigMgr) を使用してコンピューターを管理していない場合

1. Microsoft Defender ウイルス対策 (Windows Server 2016) を含むコンピューターを完全に更新し[、前提条件](configure-server-endpoints.md#prerequisites)が満たされていることを確認します。
2. グループ ポリシー、PowerShell、またはサード パーティの管理ソリューションを使用してポリシーを作成して適用します。
3. System Center Endpoint Protectionをアンインストールします (R2 Windows Server 2012)。
5. Microsoft Defender for Endpointをインストールする ([サーバー エンドポイントの構成に関するページを](configure-server-endpoints.md)参照)。
6. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。 
7. 更新プログラムを適用します。

> [!TIP]
> インストーラー スクリプトを使用して、上記の手順を自動化できます。

## <a name="microsoft-defender-for-cloud-scenarios"></a>Microsoft Defender for Cloud のシナリオ

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Microsoft Defender for Cloud を使用しています。 Azure (SCEP) 用の Microsoft Monitoring Agent (MMA) またはMicrosoft Antimalwareがインストールされ、アップグレードする必要があります。
Microsoft Defender for Cloud を使用している場合は、自動アップグレード プロセスを利用できます。 [Defender for Cloud の統合 EDR ソリューションを使用してエンドポイントを保護する:Microsoft Defender for Endpoint](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)を参照してください。

## <a name="group-policy-configuration"></a>グループ ポリシー構成
グループ ポリシーを使用して構成する場合は、中央ストアで最新の ADMX ファイルを使用して、適切な Defender for Endpoint ポリシー オプションにアクセスしていることを確認します。 Windows で グループ ポリシー [管理用テンプレート用のセントラル ストアを作成および管理する方法](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)と、**Windows 10で使用する** 最新のファイルをダウンロードする方法を参照してください。
