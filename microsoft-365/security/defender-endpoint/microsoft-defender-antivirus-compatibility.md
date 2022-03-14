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
ms.date: 03/14/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 3a0701880a5712de4ec930e49397bf2ef4b8e637
ms.sourcegitcommit: 9af389e4787383cd97bc807f7799ef6ecf0664d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2022
ms.locfileid: "63468858"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性

**適用対象:**

- Microsoft Defender ウイルス対策
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

Microsoft Defender ウイルス対策のバージョンを実行しているエンドポイントに自動的にインストールWindows。

- Windows 10以降
- Windows Server 2022
- Windows Server 2019
- Windows Server バージョン 1803 以降
- Windows Server 2016

別の Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用すると、どうなるでしょうか。 Microsoft Defender ウイルス対策を別のウイルス対策製品と共に実行できますか? 答えは、オペレーティング システムや、ウイルス対策保護と [共に Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) を使用するかどうかなど、いくつかの要因によって異なっています。

この記事では、Defender for Endpoint のMicrosoft Defender ウイルス対策と、Microsoft 以外のウイルス対策/マルウェア対策ソリューションで何が起こるかを説明します。

> [!IMPORTANT]
> - Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server、バージョン 1803 以降、および Windows Server 2016 を実行しているデバイスで使用できます。 
> - Microsoft Defender ウイルス対策統合ソリューションを使用してオンボードWindows Server 2012 R2 でも使用[できます](/microsoft-365/security/defender-endpoint/configure-server-endpoints)。
> - Windows 8.1 では、エンタープライズ レベルのエンドポイントウイルス対策保護が [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10) として提供されます。Microsoft Endpoint Configuration Manager。
> - Windows Defenderは、エンタープライズ レベルの管理を提供[](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)Windows 8.1 Windows Defenderコンシューマー デバイス向けにも提供されます。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Defender for Endpoint のないウイルス対策保護

このセクションでは、Defender for Endpoint にオンボードされていないエンドポイントで microsoft 以外のウイルス対策/マルウェア対策製品とMicrosoft Defender ウイルス対策を使用する場合の機能について説明します。 

> [!NOTE]
> 一般に、Microsoft Defender ウイルス対策 Defender for Endpoint にオンボードされていないデバイスでは、パッシブ モードでは実行されません。

次の表に、期待する内容を示します。

|Windows バージョン|プライマリ ウイルス対策/マルウェア対策ソリューション|Microsoft Defender ウイルス対策|
|:---|:---|:---|
|Windows 10 <br/> Windows 11|Microsoft Defender ウイルス対策|アクティブ モード|
|Windows 10 <br/> Windows 11|Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効モード (自動的に発生)|
|Windows Server 2022 <br/> Windows Server 2019<br/> Windows Server バージョン 1803 以降 <br/> Windows Server 2016 |Microsoft Defender ウイルス対策|アクティブ モード|
|Windows Server 2022<br/>Windows Server 2019<br/>Windows Server バージョン 1803 以降 <br/> Windows Server 2016  |Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効 (手動で設定) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) Windowsサーバーで、Microsoft 以外のウイルス対策製品を実行している場合は、競合を防止するためにMicrosoft Defender ウイルス対策アンインストールできます。 デバイスが Microsoft Defender for Endpoint にオンボードされている場合は、パッシブ モードで Microsoft Defender ウイルス対策を使用できます (以下を参照)。

> [!TIP]
> このWindows Server 2016、*データの代* わりにWindows Defender ウイルス対策 *が表示Microsoft Defender ウイルス対策*。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender ウイルス対策および Microsoft 以外のウイルス対策/マルウェア対策ソリューション

> [!NOTE]
> 一般に、Microsoft Defender ウイルス対策 Defender for Endpoint にオンボードされているエンドポイントでのみパッシブ モードに設定できます。

アクティブ モードMicrosoft Defender ウイルス対策パッシブ モードで実行するか無効にするかは、次のようないくつかの要因によって異なります。

- エンドポイントにインストールWindowsバージョン
- エンドポイントMicrosoft Defender ウイルス対策ウイルス対策/マルウェア対策ソリューションのプライマリ ソリューションかどうか
- エンドポイントが Defender for Endpoint にオンボードされるかどうか

次の表に、複数のシナリオでのMicrosoft Defender ウイルス対策の概要を示します。 

| Windows バージョン   | ウイルス対策/マルウェア対策ソリューション  | Defender for Endpoint に <br/> オンボードしますか? | Microsoft Defender ウイルス対策     |
|:------|:------|:-------|:-------|
| Windows 10 <br/> Windows 11| Microsoft Defender ウイルス対策 | はい  | アクティブ モード | 
| Windows 10 <br/> Windows 11 | Microsoft Defender ウイルス対策 | いいえ   | アクティブ モード |
| Windows 10 <br/> Windows 11  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | パッシブ モード (自動) |
| Windows 10 <br/> Windows 11  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ   | 無効モード (自動)    |
| Windows Server 2022 <br/> Windows Server 2019 <br/>Windows Server バージョン 1803 以降  | Microsoft Defender ウイルス対策  | はい |         アクティブ モード  |
| Windows Server 2022 <br/> Windows Server 2019 <br/> Windows Server バージョン 1803 以降   | Microsoft Defender ウイルス対策 | いいえ  | アクティブ モード |
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server バージョン 1803 以降  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | Microsoft Defender ウイルス対策パッシブ モードに設定する必要があります (手動) <sup>[[2](#fn2)]<sup>  | 
| Windows Server 2022 <br/> Windows Server 2019 <p> Windows Server バージョン 1803 以降  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ  | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup>[[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br/> Windows Server 2012 R2   | Microsoft Defender ウイルス対策 | はい | アクティブ モード |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft Defender ウイルス対策 | いいえ | アクティブ モード |
| Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい | Microsoft Defender ウイルス対策パッシブ モードに設定する必要があります (手動) <sup>[[2](#fn2)]<sup> |
|Windows Server 2016 <br/> Windows Server 2012 R2  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup>[[3](#fn3)]<sup> |

(<a id="fn2">2</a>) Windows Server 2019、Windows Server、バージョン 1803 以降、Windows Server 2016、または Windows Server 2012 R2 では、microsoft 以外のウイルス対策ソフトウェアをインストールしても、Microsoft Defender ウイルス対策 はパッシブ モードに自動的に入らない製品。 このような場合、Microsoft Defender ウイルス対策をパッシブ モードに設定 して、サーバーに複数のウイルス対策製品がインストールされることによる問題を防ぎます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。 

  次のレジストリ Microsoft Defender ウイルス対策を設定すると、パッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- 種類`REG_DWORD`
- 値: `1`

 > [!NOTE]
 > Windows Server 2016 および Windows Server 2012 R2 を実行するエンドポイントでパッシブ モードが動作するには、「オンボード Windows サーバー」で説明されている最新の統合ソリューションを使用して、これらのエンドポイント[をオンボードする必要](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)があります。 

(<a id="fn3">3</a>) Windows Server 2016 または Windows Server 2012 R2 で、Microsoft 以外のウイルス対策製品を使用している場合、そのエンドポイントが Microsoft Defender for Endpoint にオンボードされていない場合は、エンドポイントを無効またはアンインストールMicrosoft Defender ウイルス対策 サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防ぐために手動で実行します。

> [!TIP]
> このWindows Server 2016、*データの代* わりにWindows Defender ウイルス対策 *が表示Microsoft Defender ウイルス対策*。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server、バージョン 1803 以降、Windows Server 2016、およびWindows Server 2012 R2.
>
> このWindows 8.1、エンタープライズ レベルのエンドポイントウイルス対策保護は、System Center Endpoint Protectionによって管理される[](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))Microsoft Endpoint Configuration Manager。
>
> Windows Defenderは、エンタープライズ レベルの管理を提供[](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)Windows 8.1 Windows Defenderコンシューマー デバイス向けにも提供されます。

Defender for Endpoint には、エンドポイントにインストールされているウイルス対策保護をさらに拡張する機能が含まれています。 別のウイルス対策ソリューションとMicrosoft Defender ウイルス対策を実行するメリットがあります。

たとえば、ブロック モードのエンドポイント検出と応答 [(EDR)](edr-in-block-mode.md) は、プライマリ ウイルス対策製品ではない場合でも、悪意のあるMicrosoft Defender ウイルス対策保護を提供します。 このような機能を使用するにはMicrosoft Defender ウイルス対策モードまたはアクティブ モードでインストールおよび実行する必要があります。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>パッシブ モードでMicrosoft Defender ウイルス対策する要件

パッシブ モードでMicrosoft Defender ウイルス対策するには、エンドポイントが次の要件を満たす必要があります。

- オペレーティング システム: Windows 10以降。Windows Server 2022、Windows Server 2019、Windows バージョン 1803 以降
- Microsoft Defender ウイルス対策インストールする必要があります
- Microsoft 以外のウイルス対策/マルウェア対策製品をインストールし、プライマリ ウイルス対策ソリューションとして使用する必要があります。
- エンドポイントは Defender for Endpoint にオンボードする必要があります

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender ウイルス対策が Defender for Endpoint 機能に影響を与えるしくみ

Defender for Endpoint は、パッシブ モードMicrosoft Defender ウイルス対策実行できるかどうかに影響します。 Microsoft Defender ウイルス対策 Defender for Endpoint の特定の機能にも影響を与える可能性があります。 たとえば、リアルタイム保護は、アクティブまたはパッシブ Microsoft Defender ウイルス対策モードの場合は動作しますが、無効またはアンインストールMicrosoft Defender ウイルス対策機能しません。

このセクションの表は、Microsoft Defender ウイルス対策 がアクティブ モード、パッシブ モード、または無効/アンインストールの状態にあるかどうかに応じて、アクティブに動作している機能と機能の概要を示します。

> [!IMPORTANT]
> 次の表は、情報のみを提供するように設計されています。 パッシブ モードで Microsoft Defender ウイルス対策 を使用している場合、またはブロック モードで [EDR](edr-in-block-mode.md) を使用している場合、侵害後に検出された悪意のあるアーティファクトを検出して修復する場合は、リアルタイム保護、クラウド配信保護、制限付き定期的スキャンなどの機能をオフにしません。

 | 保護 | Microsoft Defender ウイルス対策 <br/>(*アクティブ モード*) | Microsoft Defender ウイルス対策 <br/>(*パッシブ モード*) | Microsoft Defender ウイルス対策 <br/>(*無効またはアンインストール*) | [ブロック モードの EDR](edr-in-block-mode.md) | 
 |:---|:---|:---|:---|:---| 
 | [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md) | はい | メモ <sup>[[4] を参照](#fn4)してください。</sup> | いいえ | 不要 | 
 | [クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | 不要  | 不要 | 不要 | 
 | [ネットワーク保護](network-protection.md)  | はい | 不要 | 不要 | 不要 | 
 | [攻撃面の減少ルール](attack-surface-reduction.md)  | はい | 不要 | 不要  | いいえ | 
 | [限定された定期的なスキャンの可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | 不要 | はい | 不要 | 
 | [スキャン中ファイルと検出情報](review-scan-results-microsoft-defender-antivirus.md) | はい | はい | 不要 | はい | 
 | [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup>[[5] を参照](#fn5)してください。</sup> | 不要 | はい | 
 | [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい | 不要 | はい | 

(<a id="fn4">4</a>) 一般に、Microsoft Defender ウイルス対策 がパッシブ モードの場合、リアルタイム保護は、有効でパッシブ モードの場合でも、ブロックまたは強制を提供しません。

(<a id="fn5">5</a>) Microsoft Defender ウイルス対策モードの場合、脅威修復機能はスケジュールされたスキャンまたはオンデマンド スキャン中にのみアクティブになります。

> [!NOTE]
> [Microsoft 365エンドポイント のデータ](/microsoft-365/compliance/endpoint-dlp-learn-about)損失防止保護は、アクティブモードまたはパッシブ モードの場合Microsoft Defender ウイルス対策正常に動作し続ける。

## <a name="important-notes"></a>重要事項

- Microsoft Defender ウイルス対策、Defender for Endpoint、またはアプリで使用される関連サービスを無効、停止、またはWindows セキュリティしない。 この推奨事項には、*wscsvc*、*SecurityHealthService*、*MsSense*、*Sense*、*WinDefend*、または *MsMpEng* へのサービスとプロセスが含まれます。 これらのサービスを手動で変更すると、デバイスが深刻な不安定状態になり、ネットワークが脆弱になることがあります。 これらのサービスを無効、停止、または変更すると、Microsoft 以外のウイルス対策ソリューションを使用する場合に問題が発生したり、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md) での情報の表示方法にも問題が発生したりすることがあります。

- Defender for Endpoint で、EDRウイルス対策ソリューションではない場合でも、Microsoft Defender ウイルス対策モードで無効にします。 EDRモードでは、デバイスで検出された悪意のあるアイテム (侵害後) を検出して修復します。 詳細については、「ブロック モード[EDR」を参照してください](edr-in-block-mode.md)。

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>データの状態を確認するMicrosoft Defender ウイルス対策

次の表で説明するように、いくつかの方法のいずれかを使用して、Microsoft Defender ウイルス対策の状態を確認できます。

 | メソッド | Procedure | 
 |:---|:---| 
 | Windows セキュリティアプリ |  1. デバイスでWindowsアプリをWindows セキュリティします。<br/>2. [ **ウイルス対策&保護] を選択します**。<br/>3. [ユーザー **Who保護] の下** にある [プロバイダーの **管理] を選択します**。<br/>4. [セキュリティ **プロバイダー] ページの** [ウイルス対策] の下に、[セキュリティ プロバイダー **Microsoft Defender ウイルス対策がオンになっている必要があります**。 | 
 | タスク マネージャー |  1. デバイスWindowsタスク マネージャー アプリを開きます。<br/>2. [詳細] タブ **を選択** します。<br/>3. リストで **MsMpEng.exe** を探します。 | 
 | Windows PowerShell <br/> (ユーザーが実行Microsoft Defender ウイルス対策確認するには) |  1. デバイスでWindowsを開Windows PowerShell。 <br/>2. 次の PowerShell コマンドレットを実行します。 `Get-Process`<br/>3. 結果を確認します。 有効になっている場合 **MsMpEng.exe** がMicrosoft Defender ウイルス対策表示されます。 | 
 | Windows PowerShell <br/>(ウイルス対策保護が実行されているのを確認するには) |  [Get-MpComputerStatus PowerShell コマンドレットを使用できます](/powershell/module/defender/get-mpcomputerstatus)。<br/>1. デバイスでWindowsを開Windows PowerShell。<br/>2. 次の PowerShell コマンドレットを実行します。<br/> \|Get-MpComputerStatus [AMRunningMode] を選択します。 <br/>3. 結果を確認します。 エンドポイントで有効になっている場合 **は、[** 標準] または **[** パッシブMicrosoft Defender ウイルス対策が表示されます。  | 
 | コマンド プロンプト |  1. デバイスで、Windowsを開きます。<br/>2. と入力し `sc query windefend`、Enter キーを押します。<br/>3. 結果を確認して、Microsoft Defender ウイルス対策モードで実行されている状態を確認します。  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>データの状態のMicrosoft Defender ウイルス対策詳細

このセクションの表では、このセクションで表示される可能性のあるさまざまな状態Microsoft Defender ウイルス対策。

 |  状態  |  動作  | 
 |:---|:---| 
 |  アクティブ モード  |  アクティブ モードでは、Microsoft Defender ウイルス対策はマシン上のウイルス対策アプリとして使用されます。 設定、グループ ポリシー、グループ ポリシー、または他の管理製品を使用して構成Microsoft Intuneが適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (エンドポイント自体の構成マネージャーやMicrosoft Defender ウイルス対策 アプリなど) で報告されます。  | 
 |  パッシブ モード  |  パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されず、Microsoft Defender ウイルス対策によって脅威の修復を行われることは *ありません*。 ただし、ブロック モードではエンドポイントの検出と応答 [(EDR) によって脅威を](edr-in-block-mode.md)修復できます。 <br/><br/> ファイルは、エンドポイント EDRスキャンされ、Defender for Endpoint サービスと共有される脅威検出のレポートが提供されます。 パッシブ モードの場合でもMicrosoft Defender ウイルス対策ソースとして通知Microsoft Defender ウイルス対策表示される場合があります。 <br/><br/> Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[Microsoft Defender ウイルス対策の更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)をすることができますが、デバイスに Microsoft 以外のウイルス対策製品があり、マルウェアからリアルタイムで保護されている場合、Microsoft Defender ウイルス対策をアクティブ モードにすることはできません。 <br/><br/> セキュリティ層による防御と検出の有効性を最適に保つには、パッシブ モードで実行されている場合でも、ウイルス対策およびマルウェア対策Microsoft Defender ウイルス対策更新プログラムを取得してください。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。 <br/><br/> パッシブ モードは、最新の統合ソリューションを使用してWindows Server 2012 R2 & 2016 でのみ[サポート](/microsoft-365/security/defender-endpoint/configure-server-endpoints)されます。  | 
 |  無効 <br/><br/> または <br/><br/> アンインストール  |  無効またはアンインストールされた場合、Microsoft Defender ウイルス対策ウイルス対策アプリとして使用されません。 ファイルのスキャン、脅威の修復は行われません。 <br/><br/> Microsoft Defender ウイルス対策の無効化/アンインストールは一般的にお勧めしません。Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、できたら　Microsoft Defender ウイルス対策をパッシブにしてください。 <br/><br/> Microsoft Defender ウイルス対策 が自動的に無効になっている場合、Microsoft 以外のウイルス対策/マルウェア対策製品の有効期限が切れた場合や、ウイルス、マルウェア、その他の脅威からのリアルタイム保護が停止した場合は、自動的に再び有効にすることができます。 Microsoft Defender ウイルス対策の自動再有効化を使用すると、ウイルス対策保護をデバイス上で確実に維持することができます。 <br/><br/> また、Microsoft 以外[](limited-periodic-scanning-microsoft-defender-antivirus.md)のウイルス対策アプリを使用している場合は、Microsoft Defender ウイルス対策 エンジンで動作する限られた定期的なスキャンを使用して、定期的に脅威を確認することもできます。  | 


## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策クライアントWindowsする](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](/microsoft-365/compliance/endpoint-dlp-learn-about)
