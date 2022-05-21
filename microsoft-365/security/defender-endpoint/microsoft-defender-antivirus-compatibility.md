---
title: Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性
description: 他のセキュリティ製品を使用した Microsoft Defender ウイルス対策とオペレーティング システムについて説明します。
keywords: Windows Defender、Defender for Endpoint、次世代、ウイルス対策、互換性、パッシブ モード
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
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
ms.openlocfilehash: 5a38ed6fbdcebf54dcd8bc34458733b5edefb850
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623163"
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
> - Windows 8.1 では、エンタープライズ レベルのエンドポイントウイルス対策保護が [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10) として提供されます。これは、Microsoft Endpoint Configuration Manager によって管理されます。
> - Windows Defender は、[Windows 8.1 上のコンシューマー デバイス](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)にも提供されますが、Windows Defender ではエンタープライズ レベルの管理は提供されません。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Defender for Endpoint を使用しないウイルス対策保護

このセクションでは、Defender for Endpoint にオンボードされていないエンドポイントで Microsoft 以外のウイルス対策/マルウェア対策製品と共に Microsoft Defender ウイルス対策を使用した場合の動作について説明します。 

> [!NOTE]
> 一般に、Microsoft Defender ウイルス対策は、Defender for Endpoint にオンボードされていないデバイスではパッシブ モードでは実行されません。

次の表に、期待する内容を示します:

|Windows バージョン|プライマリ ウイルス対策/マルウェア対策ソリューション|Microsoft Defender ウイルス対策|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Microsoft Defender ウイルス対策|アクティブ モード|
|Windows 10 <br/> Windows 11|Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効モード (自動的に発生)|
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows Server バージョン 1803 以降 <br/> Windows Server 2016 |Microsoft Defender ウイルス対策|アクティブ モード|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows Server バージョン 1803 以降 <br/> Windows Server 2016  |Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効 (手動で設定) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) Windowsサーバーで、Microsoft 以外のウイルス対策製品を実行している場合は、競合を防止するためにMicrosoft Defender ウイルス対策をアンインストールできます。 デバイスが Microsoft Defender for Endpoint にオンボードされている場合は、パッシブ モードで Microsoft Defender ウイルス対策を使用できます (以下を参照)。

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

(<a id="fn2">2</a>) Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、または Windows Server 2012 R2 では、Microsoft 以外のウイルス対策製品をインストールしても、Microsoft Defender ウイルス対策は自動的にパッシブ モードになりません。 このような場合、Microsoft Defender ウイルス対策をパッシブ モードに設定 して、サーバーに複数のウイルス対策製品がインストールされることによる問題を防ぎます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。 

  次のレジストリ キーを設定すると、Microsoft Defender ウイルス対策をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- 種類`REG_DWORD`
- 値: `1`

 > [!NOTE]
 > Windows Server 2016 および Windows Server 2012 R2 を実行しているエンドポイントでパッシブ モードを機能させるには、「[Windows サーバーのオンボード](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)」で説明されている最新の統合ソリューションを使用して、これらのエンドポイントをオンボードする必要があります。 

(<a id="fn3">3</a>) Windows Server 2016、Windows Server 2012 R2、Windows Server バージョン 1803 以降、Windows Server 2019、および Windows Server 2022 では、Microsoft Defender for Endpoint にオンボード *されていない* エンドポイントで Microsoft 以外のウイルス対策製品を使用している場合は、Microsoft Defender ウイルス対策を手動で無効またはアンインストールして、サーバーに複数のウイルス対策製品がインストールされていることが原因で生じる問題を発生を防ぎます。

> [!TIP]
> Windows Server 2016 では、*Microsoft Defender ウイルス対策* ではなく *Windows Defender ウイルス対策* が表示される場合があります。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server バージョン 1803 以降、Windows Server 2016、および Windows Server 2012 R2 を実行しているデバイスでのみ使用できます。
>
> Windows 8.1 では、エンタープライズ レベルのエンドポイントウイルス対策保護は [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)) として提供され、Microsoft Endpoint Configuration Manager によって管理されます。
>
> Windows Defender は、[Windows 8.1 上のコンシューマー デバイス](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)にも提供されますが、Windows Defender ではエンタープライズ レベルの管理は提供されません。

Defender for Endpoint には、エンドポイントにインストールされているウイルス対策保護をさらに拡張する機能が含まれています。 別のウイルス対策ソリューションと共に Microsoft Defender ウイルス対策を実行するとメリットがあります。

たとえば、ブロック モードの[エンドポイントでの検出と対応 (EDR)](edr-in-block-mode.md) は、Microsoft Defender ウイルス対策がプライマリ ウイルス対策製品でない場合でも、悪意のあるアーティファクトからの保護を強化します。 このような機能を使用するには、Microsoft Defender ウイルス対策をパッシブ モードまたはアクティブ モードでインストールして実行する必要があります。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>パッシブ モードで実行する Microsoft Defender ウイルス対策の要件

Microsoft Defender ウイルス対策をパッシブ モードで実行するには、エンドポイントが次の要件を満たしている必要があります:

- オペレーティング システム: Windows 10 以降。Windows Server 2022、Windows Server 2019、Windows Server バージョン 1803 以降
- Microsoft Defender ウイルス対策をインストールする必要があります
- Microsoft 以外の別のウイルス対策/マルウェア対策製品をインストールし、プライマリ ウイルス対策ソリューションとして使用する必要があります。
- エンドポイントは Defender for Endpoint にオンボードする必要があります

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender ウイルス対策が Defender for Endpoint 機能に影響を与えるしくみ

Defender for Endpoint は、Microsoft Defender ウイルス対策がパッシブ モードで実行できるかどうかに影響します。 Microsoft Defender ウイルス対策 Defender for Endpoint の特定の機能にも影響を与える可能性があります。 たとえば、リアルタイム保護は、Microsoft Defender ウイルス対策がアクティブモードまたはパッシブ モードのときに機能しますが、Microsoft Defender ウイルス対策が無効またはアンインストールされている場合には機能しません。

このセクションの表は、Microsoft Defender ウイルス対策がアクティブ モード、パッシブ モード、無効/アンインストールのいずれであるかに応じて、アクティブに動作している機能をまとめたものです。

> [!IMPORTANT]
> 表は情報提供だけを目的としています。 パッシブ モードでMicrosoft Defender ウイルス対策を使用している場合、または [ブロック モードで EDR](edr-in-block-mode.md) を使用している場合は、リアルタイム保護、クラウドによる保護、制限付き定期的なスキャンなどの **機能をオフにしないでください**。これは、侵害後に検出された悪意のある成果物を検出して修復するためにバックグラウンドで動作します。

| 保護 | Microsoft Defender ウイルス対策 <br/>(*アクティブ モード*) | Microsoft Defender ウイルス対策 <br/>(*パッシブ モード*) | Microsoft Defender ウイルス対策 <br/>(*無効またはアンインストール済み*) | [ブロック モードの EDR](edr-in-block-mode.md) | 
|:---|:---|:---|:---|:---| 
| [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md): | はい | メモ <sup>[[4](#fn4)]</sup> を参照してください | いいえ | 不要 | 
| [クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | いいえ  | いいえ | 不要 | 
| [ネットワーク保護](network-protection.md)  | はい | いいえ | いいえ | 不要 | 
| [攻撃面の減少ルール](attack-surface-reduction.md)  | はい | いいえ | いいえ  | いいえ | 
| [限定された定期的なスキャンの可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | いいえ | はい | 不要 | 
| [スキャン中ファイルと検出情報](review-scan-results-microsoft-defender-antivirus.md) | はい | はい<sup>[[5](#fn5)]</sup> | 不要 | はい | 
| [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup>[[6](#fn6)]</sup>を参照してください | 不要 | はい | 
| [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい <sup>[[7](#fn7)]</sup> | 不要 | はい <sup>[[7](#fn7)]</sup> | 
| [データ損失防止](../../compliance/endpoint-dlp-learn-about.md) | はい | 必要 | いいえ | 不要 |
| [制御されたフォルダー アクセス](controlled-folders.md) | はい |いいえ | いいえ | 不要 |
| [Web コンテンツ フィルタリング](web-content-filtering.md) | はい | メモ <sup>[[8](#fn8)]</sup> を参照してください | 不要 | 不要 |
| [デバイス コントロール](device-control-report.md) | はい | 必要 | いいえ | 不要 |
| [PUA 保護](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | はい | いいえ | いいえ | 不要 |

(<a id="fn4">4</a>) 一般に、Microsoft Defender ウイルス対策がパッシブ モードの場合、リアルタイム保護では、有効でパッシブ モードであっても、ブロックや強制は提供されません。

(<a id="fn5">5</a>) Microsoft Defender ウイルス対策モードの場合、スキャンはスケジュールされません。

(<a id="fn6">6</a>) Microsoft Defender ウイルス対策モードの場合、脅威を修復しません。 ただし、[ブロック モードのエンドポイントの検出と応答 (EDR)](edr-in-block-mode.md) によって脅威を修復できます。 この場合、Microsoft Defender ウイルス対策がパッシブ モードの場合でも、ソースとして Microsoft Defender ウイルス対策を示すアラートが表示される場合があります。

(<a id="fn7">7</a>)セキュリティ インテリジェンスの更新間隔は、Windows Update 設定によってのみ制御されます。 Defender 固有の更新スケジューラ (特定の時刻に毎日/毎週、間隔ベース) の設定は、Microsoft Defender ウイルス対策がアクティブ モードの場合にのみ機能します。 パッシブ モードでは無視されます。

(<a id="fn8">8</a>) Microsoft Defender ウイルス対策がパッシブ モードの場合、Web コンテンツ フィルターは Microsoft Edge ブラウザーでのみ機能します。 

> [!NOTE]
> [Endpoint データ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about) 保護は、Microsoft Defender ウイルス対策がアクティブ モードであってもパッシブ モードであっても、正常に動作し続けます。

## <a name="important-notes"></a>重要事項

- Microsoft Defender ウイルス対策、Microsoft Defender for Endpoint、Windows セキュリティ アプリで使用される関連サービスを無効化、停止、変更しないでください。 この推奨事項には、*wscsvc*、*SecurityHealthService*、*MsSense*、*Sense*、*WinDefend*、または *MsMpEng* へのサービスとプロセスが含まれます。 これらのサービスを手動で変更すると、デバイスが深刻な不安定状態になり、ネットワークが脆弱になることがあります。 これらのサービスを無効、停止、または変更すると、Microsoft 以外のウイルス対策ソリューションを使用する場合に問題が発生したり、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md) での情報の表示方法にも問題が発生したりすることがあります。

- Defender for Endpoint で、EDR ウイルス対策ソリューションではない場合でも、Microsoft Defender ウイルス対策モードで無効にします。 ブロック モードの EDR は、デバイスで検出された悪意のあるアイテムを検出して修復します (侵害後)。 詳細については、「[ブロック モードでの EDR](edr-in-block-mode.md)」を参照してください。

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の状態を確認する方法

次の表で説明するように、いくつかの方法のいずれかを使用して、Microsoft Defender ウイルス対策の状態を確認できます:

 | Method | プロシージャ | 
 |:---|:---| 
 | Windows セキュリティ アプリを開きます。 |  1. Windows デバイスで、Windows セキュリティ アプリを開きます。<br/>2. [**ウイルスと脅威の防止**] を選択します。<br/>3. "**自分を保護している人**" の下で [**プロバイダーの管理**] を選択します。<br/>4. [**セキュリティ プロバイダー**] ページの "**ウイルス対策**" で、 [**Microsoft Defender ウイルス対策が**] がオンになっているはずです。 | 
 | タスク マネージャー |  1. Windows デバイスで、タスク マネージャー アプリを開きます。<br/>2. [**詳細**] タブを選択します。<br/>3. リストで **MsMpEng.exe** を探します。 | 
 | Windows PowerShell <br/> (Microsoft Defender ウイルス対策が実行されていることを確認するには) |  1. Windows デバイスで、Windows PowerShell を開きます。 <br/>2. 次の PowerShell コマンドレットを実行します: `Get-Process`。<br/>3. 結果を確認します。Microsoft Defender ウイルス対策が有効になっている場合 **MsMpEng.exe** が表示されます。 | 
 | Windows PowerShell <br/>(ウイルス対策保護が実行されているのを確認するには) |  [Get-MpComputerStatus PowerShell コマンドレット](/powershell/module/defender/get-mpcomputerstatus)を使用できます。<br/>1. Windows デバイスで、Windows PowerShell を開きます。<br/>2. 次の PowerShell コマンドレットを実行します:<br/> Get-MpComputerStatus \| AMRunningMode の選択 <br/>3. 結果を確認します。エンドポイントで Microsoft Defender ウイルス対策が有効になっている場合は **通常** または **パッシブ** または **EDR ブロック モード** が表示されます。  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>Microsoft Defender ウイルス対策状態の詳細

このセクションの表では、Microsoft Defender ウイルス対策で表示される可能性があるさまざまな状態について説明します。

 |  状態  |  動作  | 
 |:---|:---| 
 |  アクティブ モード  |  アクティブ モードでは、Microsoft Defender ウイルス対策はマシン上のウイルス対策アプリとして使用されます。 Configuration Manager、グループ ポリシー、Microsoft Intune、またはその他の管理製品を使って構成された設定が適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (エンドポイント自体の構成マネージャーやMicrosoft Defender ウイルス対策 アプリなど) で報告されます。  | 
 |  パッシブ モード <br/><br/> or <br/><br/> EDR ブロック モード |  パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されず、Microsoft Defender ウイルス対策によって脅威の修復を行われることは *ありません*。 <br/><br/>ただし、EDR ブロック モードで実行している場合、[ブロック モードのエンドポイント検出と応答 (EDR)](edr-in-block-mode.md) によって脅威を修復できます。 <br/><br/> ファイルは EDR によってスキャンされ、脅威の検出に関するレポートが提供され、Defender for Endpoint サービスと共有されます。 Microsoft Defender ウイルス対策がパッシブ モードの場合でも、ソースとして Microsoft Defender ウイルス対策を示すアラートが表示される場合があります。 <br/><br/> Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[Microsoft Defender ウイルス対策の更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)をすることができますが、デバイスに Microsoft 以外のウイルス対策製品があり、マルウェアからリアルタイムで保護されている場合、Microsoft Defender ウイルス対策をアクティブ モードにすることはできません。 <br/><br/> セキュリティの多層防御と検出の有効性を最適化するには、Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも、ウイルス対策とマルウェア対策の更新プログラムを取得してください。「[Microsoft Defender ウイルス対策の更新を管理し、ベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)」に関するページを参照してください。 <br/><br/> マシンが[最新の統合ソリューション](/microsoft-365/security/defender-endpoint/configure-server-endpoints)を使ってオンボードされている場合、パッシブ モードは、Windows Server 2012 R2 および 2016 でのみサポートされることに注意してください。  | 
 |  無効 <br/><br/> または <br/><br/> アンインストール済み  |  無効またはアンインストールした場合、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されません。 ファイルのスキャン、脅威の修復は行われません。 <br/><br/> Microsoft Defender ウイルス対策の無効化/アンインストールは一般的にお勧めしません。Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、できたら　Microsoft Defender ウイルス対策をパッシブにしてください。 <br/><br/> Microsoft Defender ウイルス対策が自動的に無効になっている場合は、Microsoft 以外のウイルス対策製品によって提供される保護の有効期限が切れるか、ウイルス、マルウェア、またはその他の脅威からのリアルタイム保護が停止した場合に、Microsoft Defender ウイルス対策を自動的に再有効化できます。 Microsoft Defender ウイルス対策の自動再有効化を使用すると、ウイルス対策保護をデバイス上で確実に維持することができます。 <br/><br/> また、Microsoft 以外のウイルス対策アプリを使用している場合に、Microsoft Defender ウイルス対策エンジンを使用して、脅威を定期的にチェックする、[限られた定期的なスキャン](limited-periodic-scanning-microsoft-defender-antivirus.md)を有効にすることもできます。  | 

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [エンドポイント データ損失防止について](/microsoft-365/compliance/endpoint-dlp-learn-about)
