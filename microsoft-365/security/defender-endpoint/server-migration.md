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
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ed31a629f6cde18af03c3c6102b821cb6a04dd96
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782672"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>前の MMA ベースのMicrosoft Defender for Endpoint ソリューションからのサーバー移行シナリオ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> インストールまたはアップグレードを続行する前に、常にオペレーティング システムとWindows Server 2016のMicrosoft Defender ウイルス対策が完全に更新されていることを確認してください。 EDR センサー コンポーネントの定期的な製品の機能強化と修正プログラムを受け取るには、インストール後に [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277) Windows Update適用または承認されていることを確認します。 さらに、保護コンポーネントを更新し続けるために、[Microsoft Defender ウイルス対策更新プログラムの管理とベースラインの適用](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)に関するページを参照してください。

これらの手順は、Windows Server 2012 R2 およびWindows Server 2016用のMicrosoft Defender for Endpointの新しい統合ソリューションとインストーラー (MSI) パッケージに適用されます。 この記事では、前のソリューションから現在のソリューションまで、さまざまな移行シナリオに関する高度な手順について説明します。 これらの高レベルの手順は、環境で使用可能なデプロイ ツールと構成ツールに合わせて調整するためのガイドラインとして意図されています。

> [!NOTE]
> Microsoft Defender for Endpointがインストールされているオペレーティング システムのアップグレードはサポートされていません。 アップグレードを続行する前に、オフボードでアンインストールしてください。

> [!NOTE]
> 自動化されたアップグレードを実行するための完全なMicrosoft Endpoint Configuration Managerの自動化と統合は、MECM の後のリリースで利用できます。 最新の修正プログラム ロールアップを使用した 2107 リリースから、グループ ポリシー、PowerShell、Microsoft エンドポイント マネージャー テナントのアタッチ、またはローカル構成だけでなく、構成にもEndpoint Protection ノードを使用できます。 さらに、Microsoft Endpoint Configuration Managerの既存の機能を利用して手動のアップグレード手順を自動化できます。この方法については、以下で説明します。


## <a name="installer-script"></a>インストーラー スクリプト

Microsoft Endpoint Configuration ManagerまたはMicrosoft Defender for Cloudが使用されていない場合やアップグレードを実行できない場合にアップグレードを容易にするには、この[アップグレード スクリプト](https://github.com/microsoft/mdefordownlevelserver)を使用できます。 次の必要な手順を自動化するのに役立ちます。

1. Microsoft Defender for Endpointの OMS ワークスペースを削除します (省略可能)。
2. インストールされている場合は、System Center Endpoint Protection (SCEP) クライアントを削除します。
3. 必要に応じて、(Windows Server 2012 R2) [前提条件を](configure-server-endpoints.md#prerequisites)ダウンロードしてインストールします。
4. Microsoft Defender for Endpointをインストールします。
5. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。

スクリプトを使用するには、インストール パッケージとオンボード パッケージを配置したインストール ディレクトリにダウンロードします ( [サーバー エンドポイントの構成](configure-server-endpoints.md)に関するページを参照してください。

例: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager移行シナリオ 

>[!NOTE]
>バージョン 2107 以降Microsoft Endpoint Configuration Manager必要があります。

移行手順: 

1. Microsoft Defender ウイルス対策 (Windows Server 2016) を含むコンピューターを完全に更新します。
2. 移行するマシンを含めるメンバーシップ規則を持つ新しいコレクションを作成します。
3. 次のタスクを実行する[アプリケーションを作成](/mem/configmgr/apps/deploy-use/create-applications)します。 
   1. SCEP をアンインストールします。
   2. 該当する場合 [は、前提条件をインストールします](configure-server-endpoints.md#prerequisites) 。
   3. Microsoft Defender for Endpointをインストールする ([サーバー エンドポイントの構成に関するページを](configure-server-endpoints.md)参照してください。
   4. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。 
   > [!TIP]
   > [インストーラー スクリプト](server-migration.md#installer-script)をアプリケーションの一部として使用して、上記の手順を自動化できます。
4. アプリケーションを新しいコレクションにデプロイします。
5. コレクションに (既存の) Endpoint Protection ポリシーを作成または割り当てます。
6. 更新プログラムを適用します。

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>現在、Microsoft Endpoint Configuration Managerを使用してサーバーを管理し、Microsoft 以外のウイルス対策ソリューションと MMA ベースのセンサーを実行しています。 新しいMicrosoft Defender for Endpointにアップグレードする必要があります。

移行手順:

1. Microsoft Defender ウイルス対策 (Windows Server 2016) を含むコンピューターを完全に更新します。
2. 移行するマシンを含めるメンバーシップ規則を持つ新しいコレクションを作成します。 
3. サードパーティのウイルス対策管理がこれらのマシンにウイルス対策をプッシュしないようにします。*
4. MECM のEndpoint Protection ノードでポリシーを作成し、新しく作成したコレクションをターゲットにします。*
5. 次のタスクを実行するアプリケーションを作成します。
   1. Microsoft Defender for Endpointの MMA ワークスペース構成を削除します。 [PowerShell を使用したワークスペースの削除に関するページを参照](/azure/azure-monitor/agents/agent-manage)してください。 この手順は省略可能です。前のEDR センサーは、新しいセンサーがアクティブになると実行を停止します。
   2. 該当する場合 [は、前提条件をインストールします](configure-server-endpoints.md#prerequisites) 。
   3. Windows Server 2012 R2 および 2016 パッケージのMicrosoft Defender for Endpointをインストールし、**パッシブ モードを有効にします**。 [コマンド ラインを使用したMicrosoft Defender ウイルス対策のインストールに関するページを](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)参照してください。
   4. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。
6. 更新プログラムを適用します。
7. Microsoft 以外のウイルス対策コンソールを使用するか、必要に応じてMicrosoft Endpoint Configuration Managerを使用して、Microsoft 以外のウイルス対策ソフトウェアを削除します。 必ずパッシブ モード構成を削除してください。*

> [!TIP]
> [インストーラー スクリプト](server-migration.md#installer script)をアプリケーションの一部として使用して、上記の手順を自動化できます。 パッシブ モードを有効にするには、-Passive フラグを適用します。 たとえば、.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*これらの手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 Microsoft Defender ウイルス対策[とMicrosoft Defender for Endpointに関](why-use-microsoft-defender-antivirus.md)する一緒の改善に関するMicrosoft Defender for Endpointを参照してください。

パッシブ モードからマシンを移動するには、次のキーを 0 に設定します。

パス: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode 型: REG_DWORD値: 0


## <a name="other-migration-scenarios"></a>その他の移行シナリオ

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-microsoft-defender-for-cloud-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>MMA ベースのMicrosoft Defender for Endpointを使用してオンボードされたサーバーがあります。 SCEP がインストールされている (R2 Windows Server 2012) またはMicrosoft Defender ウイルス対策 (Windows Server 2016)。 このマシンは、Microsoft Defender for Cloud、Microsoft エンドポイント マネージャー、またはMicrosoft Endpoint Configuration Managerによって管理 **されません**。

1. Microsoft Defender ウイルス対策 (Windows Server 2016) を含むコンピューターを完全に更新します。
2. Microsoft Defender for Endpointの MMA ワークスペース構成を削除します。 [PowerShell を使用したワークスペースの削除に関するページを参照](/azure/azure-monitor/agents/agent-manage)してください。
3. System Center Endpoint Protectionをアンインストールします (R2 Windows Server 2012)。
4. 該当する場合 [は、前提条件をインストールします](configure-server-endpoints.md#prerequisites) 。 
5. Microsoft Defender for Endpointをインストールする ([サーバー エンドポイントの構成に関するページを](configure-server-endpoints.md)参照)。
6. Microsoft 365 Defenderからダウンロードした **グループ ポリシーで使用する** オンボード スクリプト [を適用します](https://security.microsoft.com)。 
7. 更新プログラムを適用します。
8. グループ ポリシー、PowerShell、またはサード パーティの管理ソリューションを使用してポリシーを作成して適用します。

> [!TIP]
> インストーラー スクリプトを使用して、上記の手順を自動化できます。

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-microsoft-defender-for-cloud-you-use-your-own-deployment-mechanism"></a>Microsoft Defender for Endpointをインストールするサーバーがあります。 Microsoft 以外のエンドポイント保護またはエンドポイントでの検出と対応ソリューションがインストールされています。 Microsoft Endpoint Configuration ManagerまたはMicrosoft Defender for Cloudを使用する予定はありません。 独自のデプロイ メカニズムを使用します。 

1. Microsoft Defender ウイルス対策 (Windows Server 2016) を含むコンピューターを完全に更新します。
2. Windows Server 2012 R2 & 2016 パッケージのMicrosoft Defender for Endpointをインストールし、**パッシブ モードを有効にします**。 [コマンド ラインを使用したMicrosoft Defender ウイルス対策のインストールに関するページを](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)参照してください。
3. [Microsoft 365 Defender](https://security.microsoft.com)からダウンロードした環境に適したオンボード スクリプトを適用します。 
4. Microsoft 以外のエンドポイント保護またはエンドポイントでの検出と対応 ソリューションを削除し、パッシブ モードを削除します。
5. 更新プログラムを適用します。
6. グループ ポリシー、PowerShell、またはサード パーティの管理ソリューションを使用してポリシーを作成して適用します。

> [!TIP]
> [インストーラー スクリプト](server-migration.md#installer-script)を使用すると、手順 1 ~ 4 の自動化に役立ちます。 パッシブ モードを有効にするには、-Passive フラグを適用します。これにより、オンボード前に Defender ウイルス対策がパッシブ モードになり、Microsoft 以外のマルウェア対策ソリューションに干渉することはありません。 次に、EDR ブロックなどのEDR機能をサポートするためにオンボード後も Defender ウイルス対策がパッシブ モードのままになるようにするには、必ず "ForceDefenderPassiveMode" レジストリ キーを設定してください。 例： `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`


*この手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 Microsoft Defender for Endpointに含まれるMicrosoft Defender ウイルス対策を使用して、機能の完全なセットを提供することをお勧めします。 Microsoft Defender ウイルス対策[とMicrosoft Defender for Endpointに関](why-use-microsoft-defender-antivirus.md)する一緒の改善に関するMicrosoft Defender for Endpointを参照してください。

パッシブ モードからマシンを移動するには、次のキーを 0 に設定します。

パス: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode 型: REG_DWORD値: 0


## <a name="microsoft-defender-for-cloud-scenarios"></a>Microsoft Defender for Cloudシナリオ

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Microsoft Defender for Cloudを使用しています。 Azure (SCEP) のMicrosoft Monitoring Agent (MMA) またはMicrosoft Antimalwareがインストールされ、アップグレードする必要があります。
Microsoft Defender for Cloudを使用している場合は、自動アップグレード プロセスを利用できます。 [Defender for Cloudの統合EDR ソリューションを使用してエンドポイントを保護する:Microsoft Defender for Endpoint](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)を参照してください。

## <a name="group-policy-configuration"></a>グループ ポリシー構成
グループ ポリシーを使用して構成する場合は、中央ストアで最新の ADMX ファイルを使用して、適切な Defender for Endpoint ポリシー オプションにアクセスしていることを確認します。 [Windowsで グループ ポリシー 管理用のセントラル ストアを作成および管理する方法と、Windows 10](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)**で使用する** 最新のファイルをダウンロードする方法を参照してください。
