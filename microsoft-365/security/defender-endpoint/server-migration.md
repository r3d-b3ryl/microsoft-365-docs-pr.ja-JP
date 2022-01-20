---
title: 新しいバージョンの Microsoft Defender for Endpoint のサーバー移行シナリオ
description: この記事では、以前の MMA ベースのソリューションから現在の Defender for Endpoint 統合ソリューション パッケージにサーバーを移行する方法の概要を説明します。
keywords: migrate server, server, 2012r2, 2016, server migration, device management, Configure Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint server
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1a78d99650015aa0da92e35787a164b5c5a07b71
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156258"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>以前の MMA ベースの Microsoft Defender for Endpoint ソリューションからのサーバー移行シナリオ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> インストールまたはアップグレードMicrosoft Defender ウイルス対策する前に、Windows Server 2016が完全に更新されている必要があります。 EDR センサー コンポーネントの製品の定期的な改善と修正を受け取る場合は、Windows [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277)の更新プログラムが適用または承認されます。 さらに、保護コンポーネントを更新し続ける場合は、「更新プログラムの管理Microsoft Defender ウイルス対策ベースラインを適用する」を[参照してください](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

これらの手順は、Microsoft Defender for Endpoint for Windows Server 2012 R2 および Windows Server 2016 の新しい統合ソリューションとインストーラー パッケージに適用されます。 この記事では、前のソリューションから現在のソリューションへのさまざまな移行シナリオに関する高レベルの手順について説明します。 これらの高レベルの手順は、環境で使用可能な展開および構成ツールに合わせて調整するためのガイドラインとして意図されています。

> [!NOTE]
> Microsoft Defender for Endpoint がインストールされているオペレーティング システムのアップグレードはサポートされていません。 アップグレードを進む前にオフボードをアンインストールしてください。

> [!NOTE]
> プレビュー中に、Microsoft Endpoint Configuration Managerアップグレードを実行するための完全な自動化と統合は、後のリリースの MECM で利用できます。 最新の修正プログラム ロールアップを含む 2107 リリースから、Endpoint Protection ノードを構成に使用したり、グループ ポリシー、PowerShell、Microsoft エンドポイント マネージャー テナント接続またはローカル構成を使用できます。 さらに、既存の機能を使用して、手動Microsoft Endpoint Configuration Manager手順を自動化できます。この方法については、以下で説明します。


## <a name="installer-script"></a>インストーラー スクリプト

Microsoft Endpoint Configuration Managerまたは Microsoft Defender for Cloud が使用されていないか、まだアップグレードを実行できない場合にアップグレードを容易にするために、このアップグレード スクリプトを[使用できます](https://github.com/microsoft/mdefordownlevelserver)。 これは、次の必要な手順を自動化するのに役立ちます。

1. エンドポイント用 Microsoft Defender の OMS ワークスペースを削除します (省略可能)。
2. インストールされているSystem Center Endpoint Protectionクライアントを削除します。
3. 必要に応じて、(Windows Server 2012 R2)[の前提条件を](configure-server-endpoints.md#prerequisites)ダウンロードしてインストールします。
4. Microsoft Defender for Endpoint をインストールします。
5. グループ ポリシーからダウンロードしたグループ ポリシーで **使用** するオンボーディング スクリプトを [Microsoft 365 Defender。](https://security.microsoft.com)

スクリプトを使用するには、インストール パッケージとオンボーディング パッケージを配置したインストール ディレクトリにスクリプトをダウンロードします (「サーバー エンドポイントの構成 [」を参照してください](configure-server-endpoints.md))。

例: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager移行シナリオ 

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-including-system-center-endpoint-protection-scep-and-are-running-the-microsoft-monitoring-agent-mma-based-sensor-you-want-to-upgrade-to-the-microsoft-defender-for-endpoint-unified-solution-preview"></a>現在、MICROSOFT ENDPOINT CONFIGURATION MANAGER System Center Endpoint Protection (SCEP) を含むサーバーを管理するためにMicrosoft Monitoring Agentを使用しています。このセンサーは MMA ベースのセンサーを実行しています。 Microsoft Defender for Endpoint 統合ソリューション プレビューにアップグレード **する** 場合。

>[!NOTE]
>バージョン 2107 Microsoft Endpoint Configuration Managerが必要です。


移行手順: 

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. 移行するコンピューターを含めるメンバーシップ ルールを含む新しいコレクションを作成します。
3. [次のタスクを](/mem/configmgr/apps/deploy-use/create-applications) 実行するアプリケーションを作成します。 
   1. Microsoft Defender for Endpoint の MMA ワークスペース構成を削除します。 [「PowerShell を使用してワークスペースを削除する」を参照してください](/azure/azure-monitor/agents/agent-manage)。 この手順は省略可能です。以前のEDRセンサーは、新しいセンサーがアクティブになった後に実行を停止します (これには数時間かかる場合があります)。
   2. SCEP をアンインストールします。
   3. 該当する [場合は、前提条件](configure-server-endpoints.md#prerequisites) をインストールします。
   4. Microsoft Defender for Endpoint のインストール (「[サーバー エンドポイントの構成」を参照)。](configure-server-endpoints.md)
   5. グループ ポリシーからダウンロードしたグループ ポリシーで **使用** するオンボーディング スクリプトを [Microsoft 365 Defender。](https://security.microsoft.com) 

   > [!TIP]
   > インストーラー スクリプトをアプリケーション [の一](server-migration.md#installer-script) 部として使用して、上記の手順を自動化できます。
4. アプリケーションを新しいコレクションに展開します。
5. コレクションにポリシーを作成または割りEndpoint Protection (既存の) ポリシーを割り当てる。
6. 更新プログラムを適用します。

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>現在、サーバーを管理Microsoft Endpoint Configuration Manager、Microsoft 以外のウイルス対策ソリューションと MMA ベースのセンサーを実行しています。 新しい Microsoft Defender for Endpoint にアップグレードする場合。

移行手順:

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. 移行するコンピューターを含めるメンバーシップ ルールを含む新しいコレクションを作成します。 
3. サードパーティのウイルス対策管理がウイルス対策をこれらのコンピューターにプッシュしなくなったか確認します。*
4. MECM の Endpoint Protectionノードでポリシーを作成し、新しく作成したコレクションをターゲットにします。*
5. 次のタスクを実行するアプリケーションを作成します。
   1. Microsoft Defender for Endpoint の MMA ワークスペース構成を削除します。 [「PowerShell を使用してワークスペースを削除する」を参照してください](/azure/azure-monitor/agents/agent-manage)。 この手順は省略可能です。以前のEDRセンサーは、新しいセンサーがアクティブになった後に実行を停止します (これには数時間かかる場合があります)。
   2. 該当する [場合は、前提条件](configure-server-endpoints.md#prerequisites) をインストールします。
   3. Microsoft Defender for Endpoint for Windows Server 2012 R2 および 2016 パッケージをインストールし、**パッシブ モードを有効にします**。 「コマンド[ラインをMicrosoft Defender ウイルス対策インストールする」を参照してください](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)。
   4. グループ ポリシーからダウンロードしたグループ ポリシーで **使用** するオンボーディング スクリプトを [Microsoft 365 Defender。](https://security.microsoft.com)
6. 更新プログラムを適用します。
7. Microsoft 以外のウイルス対策コンソールを使用するか、必要に応じて Microsoft 以外のウイルス対策Microsoft Endpoint Configuration Manager削除します。 パッシブ モード構成を削除してください。*

> [!TIP]
> インストーラー スクリプトを [アプリケーションの一部](server-migration.md#installer script) として使用して、上記の手順を自動化できます。 パッシブ モードを有効にするには、-Passive フラグを適用します。 たとえば、.\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*これらの手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 「Better [together: Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint」を参照してください](why-use-microsoft-defender-antivirus.md)。

パッシブ モードからコンピューターを移動するには、次のキーを 0 に設定します。

パス: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD 値: 0


## <a name="other-migration-scenarios"></a>その他の移行シナリオ

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-microsoft-defender-for-cloud-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>MMA ベースの Microsoft Defender for Endpoint を使用してオンボードされているサーバーがあります。 SCEP がインストールされている (Windows Server 2012 R2) または Microsoft Defender ウイルス対策 (Windows Server 2016)。 このコンピューターは **、Microsoft** Defender for Cloud、Microsoft エンドポイント マネージャー、またはMicrosoft Endpoint Configuration Manager。

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. Microsoft Defender for Endpoint の MMA ワークスペース構成を削除します。 [「PowerShell を使用してワークスペースを削除する」を参照してください](/azure/azure-monitor/agents/agent-manage)。
3. アンインストールSystem Center Endpoint Protection (Windows Server 2012 R2)。
4. 該当する [場合は、前提条件](configure-server-endpoints.md#prerequisites) をインストールします。 
5. Microsoft Defender for Endpoint のインストール (「 [サーバー エンドポイントの構成」を参照](configure-server-endpoints.md))
6. グループ ポリシーからダウンロードしたグループ ポリシーで **使用** するオンボーディング スクリプトを [Microsoft 365 Defender。](https://security.microsoft.com) 
7. 更新プログラムを適用します。
8. グループ ポリシー、PowerShell、またはサードパーティの管理ソリューションを使用してポリシーを作成して適用します。

> [!TIP]
> インストーラー スクリプトを使用して、上記の手順を自動化できます。

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-microsoft-defender-for-cloud-you-use-your-own-deployment-mechanism"></a>Microsoft Defender for Endpoint をインストールするサーバーがあります。 Microsoft 以外のエンドポイント保護またはエンドポイント検出および応答ソリューションがインストールされています。 クラウドまたは Microsoft Defender for Cloud をMicrosoft Endpoint Configuration Managerする予定はない。 独自の展開メカニズムを使用します。 

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. Microsoft Defender for Endpoint for Windows Server 2012 R2 & 2016 パッケージをインストールし、パッシブ **モードを有効にします**。 「コマンド[ラインをMicrosoft Defender ウイルス対策インストールする」を参照してください](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-the-command-line)。
3. 環境に適したオンボーディング スクリプトを適用し、Microsoft 365 Defender から[ダウンロードします](https://security.microsoft.com)。 
4. Microsoft 以外のエンドポイント保護ソリューションまたはエンドポイント検出および応答ソリューションを削除し、パッシブ モードを削除します。*
5. 更新プログラムを適用します。
6. グループ ポリシー、PowerShell、またはサードパーティの管理ソリューションを使用してポリシーを作成して適用します。

> [!TIP]
> インストーラー スクリプトを使用すると [、](server-migration.md#installer-script) 手順 1 ~ 4 の自動化に役立ちます。 パッシブ モードを有効にするには、-Passive フラグを適用して、オンボード前に Defender Antivirus がパッシブ モードに入り、Microsoft 以外のマルウェア対策ソリューションに干渉しないようにします。 その後、EDR ブロックなどの EDR 機能をサポートするためにオンボーディング後に Defender Antivirus がパッシブ モードのままである場合は、必ず "ForceDefenderPassiveMode" レジストリ キーを設定してください。 例: `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`


*この手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 Microsoft Defender for Endpoint にMicrosoft Defender ウイルス対策、完全な一連の機能を提供するために、Microsoft Defender for Endpoint に含まれるアプリを使用することをお勧めします。 「Better [together: Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint」を参照してください](why-use-microsoft-defender-antivirus.md)。

パッシブ モードからコンピューターを移動するには、次のキーを 0 に設定します。

パス: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection Name: ForceDefenderPassiveMode Type: REG_DWORD 値: 0


## <a name="microsoft-defender-for-cloud-scenarios"></a>Microsoft Defender for Cloud シナリオ

### <a name="youre-using-microsoft-defender-for-cloud-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Microsoft Defender for Cloud を使用しています。 Azure (SCEP) Microsoft Monitoring Agent (MMA) および/または Microsoft Antimalwareがインストールされ、アップグレードする必要があります。
Microsoft Defender for Cloud を使用している場合は、自動アップグレード プロセスを利用できます。 「Defender [for Cloud の統合アプリケーション ソリューション:Microsoft Defender for Endpoint EDRエンドポイントを保護する」を参照してください](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)。

## <a name="group-policy-configuration"></a>グループ ポリシーの構成
グループ ポリシーを使用した構成の場合は、中央ストアの最新の ADMX ファイルを使用して、エンドポイント ポリシー オプションの適切な Defender にアクセスしていることを確認します。 「グループ [ポリシー管理](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)用中央ストア管理用テンプレートを作成および管理する方法」を参照し、Windows で使用する最新のファイルをダウンロード **Windows 10。**
