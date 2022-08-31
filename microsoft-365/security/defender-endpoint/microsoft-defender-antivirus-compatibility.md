---
title: Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性
description: 他のセキュリティ製品を使用した Microsoft Defender ウイルス対策とオペレーティング システムについて説明します。
keywords: Windows Defender、Defender for Endpoint、次世代、ウイルス対策、互換性、パッシブ モード
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.date: 08/30/2022
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 642f3294304d6cd0aadd3ead44a61f17d0e61ad3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67478213"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性

**適用対象:**

- Microsoft Defender ウイルス対策
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策は、次のバージョンの Windows を実行しているエンドポイントに自動的にインストールされます:

- Windows 10 以降
- Windows Server 2022
- Windows Server 2019
- Windows Server バージョン 1803 以降
- Windows Server 2016

Microsoft 以外の別のウイルス対策/マルウェア対策ソリューションが使用されるとどうなりますか? Microsoft Defender ウイルス対策を別のウイルス対策製品と共に実行できますか? 回答は、オペレーティング システムや、ウイルス対策保護と共に [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) を使用しているかどうかなど、いくつかの要因によって異なります。

この記事では、Microsoft Defender ウイルス対策と Microsoft 以外のウイルス対策/マルウェア対策ソリューションとで、Defender for Endpoint を使用した場合と使用しない場合に何が起こるかを説明します。

> [!IMPORTANT]
> - Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server、バージョン 1803 以降、および Windows Server 2016 を実行しているデバイスで使用できます。 
> - Microsoft Defender ウイルス対策は、[最新の統合ソリューション](/microsoft-365/security/defender-endpoint/configure-server-endpoints)を使用してオンボードされた Windows Server 2012 R2 でも利用できます。
> - Windows 8.1では、エンタープライズ レベルのエンドポイントウイルス対策保護が[System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))として提供されます。これは、Microsoft Endpoint Configuration Managerを通じて管理されます。
> - Windows Defender は、[Windows 8.1 上のコンシューマー デバイス](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)にも提供されますが、Windows Defender ではエンタープライズ レベルの管理は提供されません。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Defender for Endpoint を使用しないウイルス対策保護

このセクションでは、Defender for Endpoint にオンボードされていないエンドポイントで Microsoft Defender ウイルス対策と Microsoft 以外のウイルス対策/マルウェア対策製品を使用した場合の動作について説明します。 

> [!NOTE]
> 一般に、Microsoft Defender ウイルス対策は、Defender for Endpoint にオンボードされていないデバイスではパッシブ モードでは実行されません。

次の表に、期待する内容を示します:

|Windows バージョン|プライマリ ウイルス対策/マルウェア対策ソリューション|Microsoft Defender ウイルス対策|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Microsoft Defender ウイルス対策|アクティブ モード|
|Windows 10 <br/> Windows 11|Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効モード (自動的に発生)|
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows Server バージョン 1803 以降 <br/> Windows Server 2016 <br/> Windows Server 2012 R2 |Microsoft Defender ウイルス対策|アクティブ モード|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows Server バージョン 1803 以降 <br/> Windows Server 2016 |Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効 (手動で設定) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) Windows Server で、Microsoft 以外のウイルス対策製品を実行している場合は、Microsoft Defender ウイルス対策をアンインストールして競合を防ぐことができます。 デバイスが Microsoft Defender for Endpoint にオンボードされている場合は、パッシブ モードで Microsoft Defender ウイルス対策を使用できます (以下を参照)。

> [!TIP]
> Windows Server 2016 では、*Microsoft Defender ウイルス対策* ではなく *Windows Defender ウイルス対策* が表示される場合があります。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender ウイルス対策および Microsoft 以外のウイルス対策/マルウェア対策ソリューション

> [!NOTE]
> 一般に、Microsoft Defender ウイルス対策は、Defender for Endpoint にオンボードされているエンドポイントでのみパッシブ モードに設定できます。

Microsoft Defender ウイルス対策がアクティブ モード、パッシブ モード、または無効のどちらで実行されるかは、次のようないくつかの要因によって異なります:

- エンドポイントにインストールされている Windows のバージョン
- Microsoft Defender ウイルス対策がエンドポイントのプライマリ ウイルス対策/マルウェア対策ソリューションであるかどうか
- エンドポイントが Defender for Endpoint にオンボードされているかどうか

次の表は、いくつかのシナリオでの Microsoft Defender ウイルス対策の状態をまとめたものです。 

| Windows バージョン   | ウイルス対策/マルウェア対策ソリューション  | Defender for Endpoint に <br/> オンボードしますか? | Microsoft Defender ウイルス対策     |
|:------|:------|:-------|:-------|
| Windows 10 <br/> Windows 11| Microsoft Defender ウイルス対策 | はい  | アクティブ モード | 
| Windows 10 <br/> Windows 11 | Microsoft Defender ウイルス対策 | いいえ   | アクティブ モード |
| Windows 10 <br/> Windows 11  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | パッシブ モード (自動) |
| Windows 10 <br/> Windows 11  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ   | 無効モード (自動)    |
| Windows Server 2022 <br/> Windows Server 2019 <br/>Windows Server バージョン 1803 以降  | Microsoft Defender ウイルス対策  | はい |         アクティブ モード  |
| Windows Server 2022 <br/> Windows Server 2019 <br/> Windows Server バージョン 1803 以降   | Microsoft Defender ウイルス対策 | いいえ  | アクティブ モード |
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server バージョン 1803 以降  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | Microsoft Defender ウイルス対策をパッシブ モードに設定する必要があります (手動) <sup>[[2](#fn2)]<sup>  | 
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server バージョン 1803 以降  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ  | Microsoft Defender ウイルス対策を (手動で) 無効にする必要があります <sup>[[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br/> Windows Server 2012 R2   | Microsoft Defender ウイルス対策 | はい | アクティブ モード |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft Defender ウイルス対策 | いいえ | アクティブ モード |
| Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい | Microsoft Defender ウイルス対策をパッシブ モードに設定する必要があります (手動) <sup>[[2](#fn2)]<sup> |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ | Microsoft Defender ウイルス対策を (手動で) 無効にする必要があります <sup>[[3](#fn3)]<sup> |

(<a id="fn2">2</a>) Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、または R2 Windows Server 2012、Microsoft Defender ウイルス対策は、Microsoft 以外のウイルス対策製品をインストールしても自動的にパッシブ モードに入りません。 このような場合、Microsoft Defender ウイルス対策をパッシブ モードに設定 して、サーバーに複数のウイルス対策製品がインストールされることによる問題を防ぎます。 次のように、レジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- 種類`REG_DWORD`
- 値: `1`

PowerShell で保護状態を表示するには、 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) コマンドを使用します。 の値を確認します `AMRunningMode`。 Microsoft Defender ウイルス対策がエンドポイントで有効になっている場合は、 **標準**、 **パッシブ**、または **EDR ブロック モード** が表示されます。 

 > [!NOTE]
 > Windows Server 2016 および Windows Server 2012 R2 を実行しているエンドポイントでパッシブ モードを機能させるには、「[Windows サーバーのオンボード](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)」で説明されている最新の統合ソリューションを使用して、これらのエンドポイントをオンボードする必要があります。 

(<a id="fn3">3</a>) Windows Server 2016、Windows Server 2012 R2、Windows Server バージョン 1803 以降、Windows Server 2019、および Windows Server 2022 では、Microsoft Defender for Endpoint にオンボード *されていない* エンドポイントで Microsoft 以外のウイルス対策製品を使用している場合は、Microsoft Defender ウイルス対策を手動で無効またはアンインストールして、サーバーに複数のウイルス対策製品がインストールされていることが原因で生じる問題を発生を防ぎます。

> [!TIP]
> Windows Server 2016 では、*Microsoft Defender ウイルス対策* ではなく *Windows Defender ウイルス対策* が表示される場合があります。

Defender for Endpoint には、エンドポイントにインストールされているウイルス対策保護をさらに拡張する機能が含まれています。 別のウイルス対策ソリューションと共に Microsoft Defender ウイルス対策を実行するとメリットがあります。

たとえば、ブロック モードの[エンドポイントでの検出と対応 (EDR)](edr-in-block-mode.md) は、Microsoft Defender ウイルス対策がプライマリ ウイルス対策製品でない場合でも、悪意のあるアーティファクトからの保護を強化します。 このような機能を使用するには、Microsoft Defender ウイルス対策をパッシブ モードまたはアクティブ モードでインストールして実行する必要があります。

## <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>パッシブ モードで実行する Microsoft Defender ウイルス対策の要件

Microsoft Defender ウイルス対策をパッシブ モードで実行するには、エンドポイントが次の要件を満たしている必要があります:

- オペレーティング システム: Windows 10 以降。Windows Server 2022、Windows Server 2019、Windows Server バージョン 1803 以降
- Microsoft Defender ウイルス対策をインストールする必要があります
- Microsoft 以外の別のウイルス対策/マルウェア対策製品をインストールし、プライマリ ウイルス対策ソリューションとして使用する必要があります。
- エンドポイントは Defender for Endpoint にオンボードする必要があります

> [!IMPORTANT]
> - Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、および Windows Server 2012 R2 を実行しているデバイスでのみ使用できます。
> - パッシブ モードは、[最新の統合ソリューション](/microsoft-365/security/defender-endpoint/configure-server-endpoints)を使用してデバイスがオンボードされている場合、Windows Server 2012 R2 & 2016 でのみサポートされます。 
> - Windows 8.1 では、エンタープライズ レベルのエンドポイントウイルス対策保護は [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)) として提供され、Microsoft Endpoint Configuration Manager によって管理されます。
> - Windows Defender は、[Windows 8.1 上のコンシューマー デバイス](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)にも提供されますが、Windows Defender ではエンタープライズ レベルの管理は提供されません。

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender ウイルス対策が Defender for Endpoint 機能に影響を与えるしくみ

Defender for Endpoint は、Microsoft Defender ウイルス対策がパッシブ モードで実行できるかどうかに影響します。 また、Microsoft Defender ウイルス対策の状態は、Defender for Endpoint の特定の機能に影響を与える可能性があります。 たとえば、リアルタイム保護は、Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードのときに機能しますが、Microsoft Defender ウイルス対策が無効またはアンインストールされている場合には機能しません。

> [!IMPORTANT]
> - このセクションの表は、Microsoft Defender ウイルス対策がアクティブ モード、パッシブ モード、無効/アンインストールのいずれであるかに応じて、アクティブに動作している機能をまとめたものです。 この表は、情報提供のみを目的として設計されています。   
> - パッシブ モードでMicrosoft Defender ウイルス対策を使用している場合、または [ブロック モードで EDR](edr-in-block-mode.md) を使用している場合は、リアルタイム保護、クラウドによる保護、制限付き定期的なスキャンなどの **機能をオフにしないでください**。これは、侵害後に検出された悪意のある成果物を検出して修復するためにバックグラウンドで動作します。

| 保護 | Microsoft Defender ウイルス対策 <br/>(*アクティブ モード*) | Microsoft Defender ウイルス対策 <br/>(*パッシブ モード*) | Microsoft Defender ウイルス対策 <br/>(*無効またはアンインストール済み*) | [ブロック モードの EDR](edr-in-block-mode.md) | 
|:---|:---|:---|:---|:---| 
| [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md): | はい | メモ <sup>[[4](#fn4)]</sup> を参照してください | いいえ | 不要 | 
| [クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | 不要  | 不要 | 不要 | 
| [ネットワーク保護](network-protection.md)  | はい | 不要 | 不要 | 不要 | 
| [攻撃面の減少ルール](attack-surface-reduction.md)  | はい | 不要 | 不要  | いいえ | 
| [限定された定期的なスキャンの可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | 不要 | はい | 不要 | 
| [スキャン中ファイルと検出情報](review-scan-results-microsoft-defender-antivirus.md) | はい | はい <sup>[[5](#fn5)]</sup> | 不要 | はい | 
| [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup>[[6](#fn6)]</sup>を参照してください | 不要 | はい | 
| [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい <sup>[[7](#fn7)]</sup> | 不要 | はい <sup>[[7](#fn7)]</sup> | 
| [データ損失防止](../../compliance/endpoint-dlp-learn-about.md) | はい | はい | 不要 | 不要 |
| [制御されたフォルダー アクセス](controlled-folders.md) | はい |不要 | 不要 | 不要 |
| [Web コンテンツ フィルタリング](web-content-filtering.md) | はい | メモ <sup>[[8](#fn8)]</sup> を参照してください | 不要 | 不要 |
| [デバイス コントロール](device-control-report.md) | はい | はい | 不要 | 不要 |
| [PUA 保護](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | はい | 不要 | 不要 | 不要 |

(<a id="fn4">4</a>) 一般に、Microsoft Defender ウイルス対策がパッシブ モードの場合、リアルタイム保護では、有効になっていてパッシブ モードであっても、ブロックや強制は提供されません。

(<a id="fn5">5</a>) Microsoft Defender ウイルス対策がパッシブ モードの場合、スキャンはスケジュールされません。

(<a id="fn6">6</a>) Microsoft Defender ウイルス対策がパッシブ モードの場合、脅威は修復されません。 ただし、[ブロック モードのエンドポイントの検出と応答 (EDR)](edr-in-block-mode.md) によって脅威を修復できます。 この場合、Microsoft Defender ウイルス対策がパッシブ モードの場合でも、ソースとして Microsoft Defender ウイルス対策を示すアラートが表示される場合があります。

(<a id="fn7">7</a>)セキュリティ インテリジェンスの更新間隔は、Windows Update 設定によってのみ制御されます。 Defender 固有の更新スケジューラ (特定の時刻に毎日/毎週、間隔ベース) の設定は、Microsoft Defender ウイルス対策がアクティブ モードの場合にのみ機能します。 パッシブ モードでは無視されます。

(<a id="fn8">8</a>) Microsoft Defender ウイルス対策がパッシブ モードの場合、Web コンテンツ フィルターは Microsoft Edge ブラウザーでのみ機能します。 

> [!IMPORTANT]
> - [Endpoint データ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about) 保護は、Microsoft Defender ウイルス対策がアクティブ モードであってもパッシブ モードであっても、正常に動作し続けます。
>
> - Microsoft Defender ウイルス対策、Defender for Endpoint、またはWindows セキュリティ アプリで使用される関連サービスを無効、停止、または変更しないでください。 この推奨事項には、*wscsvc*、*SecurityHealthService*、*MsSense*、*Sense*、*WinDefend*、または *MsMpEng* へのサービスとプロセスが含まれます。 これらのサービスを手動で変更すると、デバイスが深刻な不安定状態になり、ネットワークが脆弱になることがあります。 これらのサービスを無効、停止、または変更すると、Microsoft 以外のウイルス対策ソリューションを使用する場合に問題が発生したり、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md) での情報の表示方法にも問題が発生したりすることがあります。
>
> - Defender for Endpoint では、Microsoft Defender ウイルス対策がプライマリウイルス対策ソリューションではない場合でも、ブロック モードで EDR を有効にすることができます。 ブロック モードの EDR は、デバイスで検出された悪意のあるアイテムを検出して修復します (侵害後)。 詳細については、「[ブロック モードでの EDR](edr-in-block-mode.md)」を参照してください。

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の状態を確認する方法

いくつかの方法のいずれかを使用して、Microsoft Defender ウイルス対策の状態を確認できます。 次の操作を行うことができます:

- [Windows セキュリティ アプリを使用して、ウイルス対策アプリを識別します](#use-the-windows-security-app-to-identify-your-antivirus-app)。
- [タスク マネージャーを使用して、Microsoft Defender ウイルス対策が実行されていることを確認します](#use-task-manager-to-confirm-that-microsoft-defender-antivirus-is-running)。
- [Windows PowerShellを使用して、Microsoft Defender ウイルス対策が実行されていることを確認します](#use-windows-powershell-to-confirm-that-microsoft-defender-antivirus-is-running)。
- [Windows PowerShellを使用して、ウイルス対策保護が実行されていることを確認します](#use-windows-powershell-to-confirm-that-antivirus-protection-is-running)。

### <a name="use-the-windows-security-app-to-identify-your-antivirus-app"></a>Windows セキュリティ アプリを使用してウイルス対策アプリを識別する

1. Windows デバイスで、Windows セキュリティ アプリを開きます。

2. **[ウイルスと脅威の防止]** を選択します。

3. [自分 **を保護するユーザー] で** 、[ **プロバイダーの管理**] を選択します。

4. [ **セキュリティ プロバイダー** ] ページの [ **ウイルス対策**] で、 **Microsoft Defender ウイルス対策が有効になっている** ことがわかります。

### <a name="use-task-manager-to-confirm-that-microsoft-defender-antivirus-is-running"></a>タスク マネージャーを使用して Microsoft Defender ウイルス対策が実行されていることを確認する

1. Windows デバイスで、タスク マネージャー アプリを開きます。

2. [ **詳細** ] タブを選択します。

3. 一覧で **MsMpEng.exe** を探します。

### <a name="use-windows-powershell-to-confirm-that-microsoft-defender-antivirus-is-running"></a>Windows PowerShellを使用して Microsoft Defender ウイルス対策が実行されていることを確認する

> [!NOTE]
> この手順は、Microsoft Defender Antirivus がエンドポイントで実行されているかどうかを確認する場合にのみ使用します。

1. Windows デバイスで、Windows PowerShellを開きます。 

2. 次の PowerShell コマンドレットを実行します `Get-Process`。

3. 結果を確認します。 Microsoft Defender ウイルス対策が有効になっている場合 **MsMpEng.exe** が表示されます。

### <a name="use-windows-powershell-to-confirm-that-antivirus-protection-is-running"></a>Windows PowerShellを使用して、ウイルス対策保護が実行されていることを確認する

> [!NOTE]
> この手順は、エンドポイントでウイルス対策保護が有効になっているかどうかを確認する場合にのみ使用します。

1. Windows デバイスで、Windows PowerShellを開きます。

2. 次の PowerShell コマンドレットを実行します `Get-MpComputerStatus | select AMRunningMode`。

3. 結果を確認します。 エンドポイントでウイルス対策保護が有効になっている場合は、 **標準**、 **パッシブ**、または **EDR ブロック モード** が表示されます。 

> [!NOTE]
> この手順は、エンドポイントでウイルス対策保護が有効になっているかどうかを確認するためだけに注意してください。

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Microsoft Defender ウイルス対策状態の詳細

次のセクションでは、Microsoft Defender ウイルス対策がどのような場合に必要かを説明します。

- [アクティブ モード](#active-mode)
- [パッシブ モードの場合、またはブロック モードの EDR がオンになっている場合](#passive-mode-or-edr-block-mode)
- [無効またはアンインストール済み](#disabled-or-uninstalled)

### <a name="active-mode"></a>アクティブ モード

アクティブ モードでは、Microsoft Defender ウイルス対策はマシン上のウイルス対策アプリとして使用されます。 Configuration Manager、グループ ポリシー、Microsoft Intune、またはその他の管理製品を使って構成された設定が適用されます。 ファイルはスキャンされ、脅威は修復され、検出情報は構成ツール (エンドポイントの Microsoft エンドポイント マネージャー管理センターや Microsoft Defender ウイルス対策アプリなど) で報告されます。  

### <a name="passive-mode-or-edr-block-mode"></a>パッシブ モードまたは EDR ブロック モード

パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されず、脅威は Microsoft Defender ウイルス対策によって修復 *されません* 。 ただし、[ブロック モードのエンドポイントの検出と応答 (EDR)](edr-in-block-mode.md) によって脅威を修復できます。 ファイルは EDR によってスキャンされ、脅威の検出に関するレポートが提供され、Defender for Endpoint サービスと共有されます。 Microsoft Defender ウイルス対策がパッシブ モードの場合でも、ソースとして Microsoft Defender ウイルス対策を示すアラートが表示される場合があります。 

Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[Microsoft Defender ウイルス対策の更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)をすることができますが、デバイスに Microsoft 以外のウイルス対策製品があり、マルウェアからリアルタイムで保護されている場合、Microsoft Defender ウイルス対策をアクティブ モードにすることはできません。

**Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも、必ずウイルス対策とマルウェア対策の更新プログラムを入手** してください。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。<br/><br/>マシンが[最新の統合ソリューション](/microsoft-365/security/defender-endpoint/configure-server-endpoints)を使ってオンボードされている場合、パッシブ モードは、Windows Server 2012 R2 および 2016 でのみサポートされることに注意してください。 

### <a name="disabled-or-uninstalled"></a>無効またはアンインストール済み

無効またはアンインストールすると、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されません。 ファイルはスキャンされず、脅威は修復されません。 Microsoft Defender ウイルス対策の無効化またはアンインストールは、一般的には推奨されません。Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、可能であれば、Microsoft Defender ウイルス対策をパッシブ モードのままにします。

Microsoft Defender ウイルス対策が自動的に無効になっている場合は、Microsoft 以外のウイルス対策/マルウェア対策製品の有効期限が切れた場合、アンインストールされた場合、またはウイルス、マルウェア、またはその他の脅威からのリアルタイム保護の提供を停止した場合に、自動的に再度有効にすることができます。 Microsoft Defender ウイルス対策の自動再有効化を使用すると、ウイルス対策保護をデバイス上で確実に維持することができます。

また、Microsoft Defender ウイルス対策エンジンと連携して、Microsoft 以外のウイルス対策アプリを使用している場合は、定期的に脅威をチェックする [限られた定期的なスキャン](limited-periodic-scanning-microsoft-defender-antivirus.md)を使用することもできます。  | 

## <a name="what-about-non-windows-devices"></a>Windows 以外のデバイスについてはどうでしょうか?

 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。

- [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
- [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
- [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
- [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
- [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
- [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [エンドポイント データ損失防止について](/microsoft-365/compliance/endpoint-dlp-learn-about)
