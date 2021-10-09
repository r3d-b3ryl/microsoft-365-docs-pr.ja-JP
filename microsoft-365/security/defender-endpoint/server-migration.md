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
ms.openlocfilehash: 6d40ed80bdbf77e6cbc2c9489462c734840755cd
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240608"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>以前の MMA ベースの Microsoft Defender for Endpoint ソリューションからのサーバー移行シナリオ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- Windows Server 2012 R2
- Windows Server 2016

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> インストールまたはアップグレードMicrosoft Defender ウイルス対策する前に、Windows Server 2016が完全に更新されている必要があります。 EDR センサー コンポーネントの製品の定期的な改善と修正を受け取る場合は、Windows [KB5005292](https://go.microsoft.com/fwlink/?linkid=2168277)の更新プログラムが適用または承認されます。 さらに、保護コンポーネントを更新し続ける場合は、「更新プログラムの管理Microsoft Defender ウイルス対策ベースラインを適用する」を[参照してください](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。

これらの手順は、Microsoft Defender for Endpoint for Windows Server 2012 R2 および Windows Server 2016 の新しい統合ソリューションとインストーラー パッケージに適用されます。 この記事では、前のソリューションから現在のソリューションへのさまざまな移行シナリオに関する高レベルの手順について説明します。 これらの高レベルの手順は、環境で使用可能な展開および構成ツールに合わせて調整するためのガイドラインとして意図されています。

> [!NOTE]
> Microsoft Defender for Endpoint がインストールされているオペレーティング システムのアップグレードはサポートされていません。 アップグレードを進む前にオフボードをアンインストールしてください。

> [!NOTE]
> プレビュー中に、Microsoft Endpoint Configuration Managerアップグレードを実行するための完全な自動化と統合は、MECM の 2111 リリースで利用できます。 2107 リリースでは、Endpoint Protection ノードを構成に使用したり、グループ ポリシー、PowerShell、Microsoft エンドポイント マネージャー テナント接続またはローカル構成を使用できます。 さらに、手動アップグレード手順を自動化するために、Microsoft Endpoint Configuration Manager機能を活用できます。以下に説明するメソッドを指定します。

## <a name="installer-script"></a>インストーラー スクリプト

アップグレードを実行するために、Microsoft Endpoint Configuration Managerまたは Azure Defender が使用されていないか、まだ使用できない場合にアップグレードを容易にするために、このアップグレード スクリプトを[使用できます](https://github.com/microsoft/mdefordownlevelserver)。 これは、次の必要な手順を自動化するのに役立ちます。

1. エンドポイント用 Microsoft Defender の OMS ワークスペースを削除する (省略可能)
2. インストールされているSystem Center Endpoint Protectionクライアントを削除する
3. 必要に応じて、(Windows Server 2012 R2)[の前提条件](configure-server-endpoints.md#prerequisites)をダウンロードしてインストールする
4. エンドポイント用 Microsoft Defender のインストール
5. [グループ ポリシー] からダウンロードしたグループ **ポリシーで使用** するオンボーディング [スクリプト](https://securitycenter.microsoft.com)をMicrosoft Defender セキュリティ センター。

スクリプトを使用するには、インストール パッケージとオンボーディング パッケージを配置したインストール ディレクトリにスクリプトをダウンロードします (「サーバー エンドポイントの構成 [」を参照してください](configure-server-endpoints.md))。

例: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager移行シナリオ 

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-including-system-center-endpoint-protection-scep-and-are-running-the-microsoft-monitoring-agent-mma-based-sensor-you-want-to-upgrade-to-the-microsoft-defender-for-endpoint-unified-solution-preview"></a>現在、MICROSOFT ENDPOINT CONFIGURATION MANAGER System Center Endpoint Protection (SCEP) を含むサーバーを管理するためにMicrosoft Monitoring Agentを使用しています。このセンサーは MMA ベースのセンサーを実行しています。 Microsoft Defender for Endpoint 統合ソリューション プレビューにアップグレード **する** 場合。

移行手順: 

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. 移行するコンピューターを含めるメンバーシップ ルールを含む新しいコレクションを作成します。
3. [次のタスクを](/mem/configmgr/apps/deploy-use/create-applications) 実行するアプリケーションを作成します。 
   1. Microsoft Defender for Endpoint の MMA ワークスペース構成を削除します。 [「PowerShell を使用してワークスペースを削除する」を参照してください](/azure/azure-monitor/agents/agent-manage)。 この手順は省略可能です。以前のEDRセンサーは、新しいセンサーがアクティブになった後に実行を停止します (これには数時間かかる場合があります)。
   2. SCEP をアンインストールします。
   3. 該当する [場合は、前提条件](configure-server-endpoints.md#prerequisites) をインストールします。
   4. Microsoft Defender for Endpoint をインストールする (「 [サーバー エンドポイントの構成」を参照](configure-server-endpoints.md))。
   5. [グループ ポリシー] からダウンロードしたグループ **ポリシーで使用** するオンボーディング [スクリプト](https://securitycenter.microsoft.com)をMicrosoft Defender セキュリティ センター。 

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
   3. Microsoft Defender for Endpoint for Windows Server 2012 R2 および 2016 パッケージをインストールし、**パッシブ モードを有効にします**。 「コマンド[ラインをMicrosoft Defender ウイルス対策インストールする」を参照してください](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line)。
   4. [グループ ポリシー] からダウンロードしたグループ **ポリシーで使用** するオンボーディング [スクリプト](https://securitycenter.microsoft.com)をMicrosoft Defender セキュリティ センター。
6. 更新プログラムを適用します。
7. Microsoft 以外のウイルス対策コンソールを使用するか、必要に応じて Microsoft 以外のウイルス対策Microsoft Endpoint Configuration Manager削除します。 パッシブ モード構成を削除してください。*

ヒント: 上記の手順を自動化 [するには](server-migration.md#installer script) 、アプリケーションの一部としてインストーラー スクリプトを使用できます。 パッシブ モードを有効にするには、-Passive フラグを適用します。 例: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*これらの手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 「Better [together: Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint」を参照してください](why-use-microsoft-defender-antivirus.md)。

## <a name="other-migration-scenarios"></a>その他の移行シナリオ 

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-azure-defender-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>MMA ベースの Microsoft Defender for Endpoint を使用してオンボードされているサーバーがあります。 SCEP がインストールされている (Windows Server 2012 R2) または Microsoft Defender ウイルス対策 (Windows Server 2016)。 このコンピューターは **、Azure** Defender、Microsoft エンドポイント マネージャー、またはMicrosoft Endpoint Configuration Manager。

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. Microsoft Defender for Endpoint の MMA ワークスペース構成を削除します。 [「PowerShell を使用してワークスペースを削除する」を参照してください](/azure/azure-monitor/agents/agent-manage)。
3. アンインストールSystem Center Endpoint Protection (Windows Server 2012 R2)。
4. 該当する [場合は、前提条件](configure-server-endpoints.md#prerequisites) をインストールします。 
5. Microsoft Defender for Endpoint のインストール (「 [サーバー エンドポイントの構成」を参照](configure-server-endpoints.md))
6. [グループ ポリシー] からダウンロードしたグループ **ポリシーで使用** するオンボーディング [スクリプト](https://securitycenter.microsoft.com)をMicrosoft Defender セキュリティ センター。 
7. 更新プログラムを適用します。
8. グループ ポリシー、PowerShell、またはサードパーティの管理ソリューションを使用してポリシーを作成して適用します。

> [!TIP]
> インストーラー スクリプトを使用して、上記の手順を自動化できます。

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-azure-defender-you-use-your-own-deployment-mechanism"></a>Microsoft Defender for Endpoint をインストールするサーバーがあります。 Microsoft 以外のエンドポイント保護またはエンドポイント検出および応答ソリューションがインストールされています。 アプリまたは Azure Defender をMicrosoft Endpoint Configuration Managerする予定ではありません。 独自の展開メカニズムを使用します。 

1. コンピューターを完全に更新します 。Microsoft Defender ウイルス対策 (Windows Server 2016)。
2. Microsoft Defender for Endpoint for Windows Server 2012 R2 & 2016 パッケージをインストールし、パッシブ **モードを有効にします**。 「コマンド[ラインをMicrosoft Defender ウイルス対策インストールする」を参照してください](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line)。
3. 環境に適したオンボーディング スクリプトを適用し、Microsoft Defender セキュリティ センター から[ダウンロードします](https://securitycenter.microsoft.com)。 
4. Microsoft 以外のエンドポイント保護ソリューションまたはエンドポイント検出および応答ソリューションを削除し、パッシブ モードを削除します。*
5. 更新プログラムを適用します。
6. グループ ポリシー、PowerShell、またはサードパーティの管理ソリューションを使用してポリシーを作成して適用します。

> [!TIP]
> インストーラー スクリプトを使用すると [、](server-migration.md#installer-script) 手順 1 ~ 4 の自動化に役立ちます。 パッシブ モードを有効にするには、-Passive フラグを適用します。 例: `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive`

*この手順は、Microsoft 以外のウイルス対策ソリューションを置き換える場合にのみ適用されます。 Microsoft Defender for Endpoint にMicrosoft Defender ウイルス対策、完全な一連の機能を提供するために、Microsoft Defender for Endpoint に含まれるアプリを使用することをお勧めします。 「Better [together: Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint」を参照してください](why-use-microsoft-defender-antivirus.md)。 

## <a name="azure-defender-scenarios"></a>Azure Defender のシナリオ

### <a name="youre-using-azure-defender-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Azure Defender を使用しています。 Azure (SCEP) Microsoft Monitoring Agent (MMA) および/または Microsoft Antimalwareがインストールされ、アップグレードする必要があります。
Azure Defender を使用している場合は、自動アップグレード プロセスを利用できます。 「[セキュリティ センターの統合ソリューションを使用してエンドポイントを保護する:エンドポイントEDR Microsoft Defender for Endpoint」を参照してください](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)。

## <a name="group-policy-configuration"></a>グループ ポリシーの構成
グループ ポリシーを使用した構成については、中央ストアで最新の ADMX ファイルを使用して、正しい Microsoft Defender ポリシー オプションにアクセスしていることを確認してください。 「グループ [ポリシー管理](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)用中央ストア管理用テンプレートを作成および管理する方法」を参照し、Windows で使用する最新のファイルをダウンロード **Windows 10。** 
