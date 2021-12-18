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
ms.date: 10/26/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: c7a4060bde3ab9e46a52713a3d4b9409f149ca0c
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560374"
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
- Windows サーバー、バージョン 1803 以降
- Windows Server 2016

別の Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用すると、どうなるでしょうか。 Microsoft Defender ウイルス対策を別のウイルス対策製品と共に実行できますか? 答えは、オペレーティング システムや [、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) とウイルス対策保護を組み合わせて使用するかどうかなど、いくつかの要因に依存します。

この記事では、Defender for Endpoint のMicrosoft Defender ウイルス対策、Microsoft 以外のウイルス対策/マルウェア対策ソリューションで発生する問題について説明します。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server、バージョン 1803 以降、Windows Server 2016、およびWindows Server 2012 R2.
>
> このWindows 8.1、エンタープライズ レベルのエンドポイントウイルス対策保護は、System Center Endpoint Protectionによって[](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))管理されるMicrosoft Endpoint Configuration Manager。
>
> Windows Defenderは、エンタープライズ レベルの管理を[](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)提供Windows 8.1、Windows Defenderコンシューマー デバイスにも提供されます。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Defender for Endpoint のないウイルス対策保護

このセクションでは、Defender for Endpoint Microsoft Defender ウイルス対策オンボーディングされていないエンドポイント上の Microsoft ウイルス対策/マルウェア対策製品以外の製品について説明します。 次の表に、期待する内容を示します。

<br/><br/>

|Windows バージョン|プライマリ ウイルス対策/マルウェア対策ソリューション|Microsoft Defender ウイルス対策|
|---|---|---|
|Windows 10 <p> Windows 11|Microsoft Defender ウイルス対策|アクティブ モード|
|Windows 10 <p> Windows 11|Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効モード (自動的に発生)|
|Windows Server 2022 <p> Windows Server 2019<p> Windows サーバー、バージョン 1803 以降 <p> Windows Server 2016 |Microsoft Defender ウイルス対策|アクティブ モード|
|Windows Server 2022<p>Windows Server 2019<p>Windows サーバー、バージョン 1803 以降 <p> Windows Server 2016 <p>  |Microsoft 以外のウイルス対策/マルウェア対策ソリューション|無効 (手動で設定) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1</a>) Windows Server で Microsoft 以外のウイルス対策製品を実行している場合は、グループ ポリシーを使用して Microsoft Defender ウイルス対策 を無効にするか[、DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーを使用して Microsoft Defender ウイルス対策 を無効にできます。 レジストリ キーを使用するには、に移動し、 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` という名前の DWORD エントリを設定または作成します `DisableAntiSpyware` 。 その値を (レジストリ キーの値を true に設定する) に設定し、ベースに `1` **[16** 進数] を選択します。 

> [!TIP]
> このWindows Server 2016の代 *わりに、Windows Defender ウイルス対策**が表示* Microsoft Defender ウイルス対策。

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender ウイルス対策および Microsoft 以外のウイルス対策/マルウェア対策ソリューション

次の表は、Microsoft 以外のウイルス対策/マルウェア対策ソリューションを一緒に使用した場合の Microsoft Defender ウイルス対策の動作と Microsoft Defender for Endpoint を使用しない Microsoft Defender ウイルス対策の動作をまとめたものです。 

| Windows バージョン   | ウイルス対策/マルウェア対策ソリューション  | Defender for Endpoint に <br/> オンボードしますか? | Microsoft Defender ウイルス対策     |
|------|------|-------|-------|
| Windows 10 <p> Windows 11| Microsoft Defender ウイルス対策 | はい  | アクティブ モード | 
| Windows 10 <p> Windows 11 | Microsoft Defender ウイルス対策 | いいえ   | アクティブ モード |
| Windows 10 <p> Windows 11  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | パッシブ モード (自動) |
| Windows 10 <p> Windows 11  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ   | 無効モード (自動)    |
| Windows Server 2019 <p>Windows Server バージョン 1803 以降  | Microsoft Defender ウイルス対策  | はい |         アクティブ モード  |
| Windows Server 2019 <p> Windows Server バージョン 1803 以降   | Microsoft Defender ウイルス対策 | いいえ  | アクティブ モード |
| Windows Server 2019 <p> Windows Server バージョン 1803 以降  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい  | Microsoft Defender ウイルス対策パッシブ モードに設定する必要があります (手動) <sup> [[2](#fn2)]<sup>  | 
| Windows Server 2019 <p> Windows Server バージョン 1803 以降  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ  | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup> [[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br><br> Windows Server 2012 R2   | Microsoft Defender ウイルス対策 | はい | アクティブ モード |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft Defender ウイルス対策 | いいえ | アクティブ モード |
| Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | はい | Microsoft Defender ウイルス対策パッシブ モードに設定する必要があります (手動) <sup> [[2](#fn2)]<sup> |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | いいえ | Microsoft Defender ウイルス対策無効にする必要があります (手動) <sup> [[3](#fn3)]<sup> |

(<a id="fn2">2</a>) Windows Server 2019、Windows Server、バージョン 1803 以降、Windows Server 2016、または Windows Server 2012 R2 では、Microsoft 以外のウイルス対策ソフトウェアをインストールしても、Microsoft Defender ウイルス対策 はパッシブ モードに自動的に入らない製品。 このような場合、Microsoft Defender ウイルス対策をパッシブ モードに設定 して、サーバーに複数のウイルス対策製品がインストールされることによる問題を防ぎます。 PowerShell、グループ ポリシー、またはレジストリ キーを使用して Microsoft Defender ウイルス対策をパッシブ モードに設定することができます。 

  次のレジストリ Microsoft Defender ウイルス対策をパッシブ モードに設定できます。
- パス: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 名前: `ForceDefenderPassiveMode`
- 種類`REG_DWORD`
- 値: `1`

 > [!NOTE]
 > Windows Server 2016 および Windows Server 2012 R2 を実行しているエンドポイントでパッシブ モードが動作するには、オンボード Windows サーバーの指示に従って、これらのエンドポイント[をオンボードする必要があります](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)。 

(<a id="fn3">3</a>) Windows Server 2016 または Windows Server 2012 R2 で、Microsoft 以外のウイルス対策製品を使用している場合、そのエンドポイントが Microsoft Defender for Endpoint にオンボードされていない場合は、エンドポイントを無効またはアンインストールMicrosoft Defender ウイルス対策 サーバーに複数のウイルス対策製品がインストールされている場合に発生する問題を防ぐために手動で実行します。

> [!TIP]
> このWindows Server 2016の代 *わりに、Windows Defender ウイルス対策**が表示* Microsoft Defender ウイルス対策。

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、Windows 10 および 11、Windows Server 2022、Windows Server 2019、Windows Server、バージョン 1803 以降、Windows Server 2016、およびWindows Server 2012 R2.
>
> このWindows 8.1、エンタープライズ レベルのエンドポイントウイルス対策保護は、System Center Endpoint Protectionによって[](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))管理されるMicrosoft Endpoint Configuration Manager。
>
> Windows Defenderは、エンタープライズ レベルの管理を[](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)提供Windows 8.1、Windows Defenderコンシューマー デバイスにも提供されます。

Defender for Endpoint には、エンドポイントにインストールされているウイルス対策保護をさらに拡張する機能が含まれています。 別のウイルス対策ソリューションとMicrosoft Defender ウイルス対策を実行するメリットがあります。

たとえば、ブロック モードのエンドポイント検出と応答[(EDR)](edr-in-block-mode.md)は、プライマリ ウイルス対策製品ではない場合でも、悪意のあるMicrosoft Defender ウイルス対策保護を提供します。 このような機能では、Microsoft Defender ウイルス対策モードまたはアクティブ モードでインストールおよび実行する必要があります。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>パッシブ モードでMicrosoft Defender ウイルス対策の要件

パッシブ モードでMicrosoft Defender ウイルス対策するには、エンドポイントが次の要件を満たす必要があります。

- オペレーティング システム: Windows 10以降。Windows Server 2022、Windows Server 2019、Windows バージョン 1803 以降
- Microsoft Defender ウイルス対策インストールする必要があります
- Microsoft 以外のウイルス対策/マルウェア対策製品をインストールし、プライマリ ウイルス対策ソリューションとして使用する必要があります。
- エンドポイントは Defender for Endpoint にオンボードする必要があります

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender ウイルス対策が Defender for Endpoint 機能に影響を与えるしくみ

Defender for Endpoint は、パッシブ モードMicrosoft Defender ウイルス対策実行できるかどうかに影響します。 Microsoft Defender ウイルス対策 Defender for Endpoint の特定の機能にも影響を与える可能性があります。 たとえば、リアルタイム保護は、アクティブまたはパッシブ Microsoft Defender ウイルス対策モードの場合は動作しますが、Microsoft Defender ウイルス対策が無効またはアンインストールされている場合は機能しません。

このセクションの表は、Microsoft Defender ウイルス対策 がアクティブ モード、パッシブ モード、または無効/アンインストールの各機能に従って、アクティブに動作するかどうかの概要を示します。

> [!IMPORTANT]
> 次の表は、情報のみを提供するように設計されています。 パッシブ モードで Microsoft Defender ウイルス対策 を使用している場合、またはブロック モードで[EDR](edr-in-block-mode.md)を使用している場合は、リアルタイム保護、クラウド配信保護、制限付き定期的なスキャンなどの機能をオフにしません。侵害後に検出された悪意のあるアーティファクトを検出して修復するために、舞台裏で動作します。

<br/><br/>

 | 保護 | Microsoft Defender ウイルス対策 <br/>(*アクティブ モード*) | Microsoft Defender ウイルス対策 <br/>(*パッシブ モード*) | Microsoft Defender ウイルス対策 <br/>(*無効またはアンインストール*) | [ブロック モードの EDR](edr-in-block-mode.md) | 
 |---|---|---|---|---| 
 | [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md) | はい | いいえ <sup>[[4](#fn4)]</sup> | いいえ | いいえ | 
 | [クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | いいえ  | いいえ | いいえ | 
 | [ネットワーク保護](network-protection.md)  | はい | いいえ | いいえ | いいえ | 
 | [攻撃面の減少ルール](attack-surface-reduction.md)  | 必要 | いいえ | いいえ  | いいえ | 
 | [限定された定期的なスキャンの可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | いいえ | はい | いいえ | 
 | [スキャン中ファイルと検出情報](review-scan-results-microsoft-defender-antivirus.md) | はい | はい | いいえ | はい | 
 | [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup>[ 5 ][を参照してください](#fn5)。</sup> | いいえ | はい | 
 | [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい | いいえ | はい | 

(<a id="fn4">4</a>) 一般に、Microsoft Defender ウイルス対策 がパッシブ モードの場合、リアルタイム保護は、有効でパッシブ モードの場合でも、ブロックや強制を提供しません。

(<a id="fn5">5</a>) Microsoft Defender ウイルス対策モードの場合、脅威修復機能はスケジュールされたスキャンまたはオンデマンド スキャン中にのみアクティブになります。

> [!NOTE]
> [Microsoft 365エンドポイントのデータ](/microsoft-365/compliance/endpoint-dlp-learn-about)損失防止保護は、アクティブモードまたはパッシブ モードの場合Microsoft Defender ウイルス対策正常に動作し続ける。

## <a name="important-notes"></a>重要事項

- Microsoft Defender ウイルス対策、Defender for Endpoint、またはアプリで使用される関連サービスを無効、停止、または変更Windows セキュリティできません。 この推奨事項には、*wscsvc*、*SecurityHealthService*、*MsSense*、*Sense*、*WinDefend*、または *MsMpEng* へのサービスとプロセスが含まれます。 これらのサービスを手動で変更すると、デバイスが深刻な不安定状態になり、ネットワークが脆弱になることがあります。 これらのサービスを無効、停止、または変更すると、Microsoft 以外のウイルス対策ソリューションを使用する場合に問題が発生したり、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md) での情報の表示方法にも問題が発生したりすることがあります。

- Defender for Endpoint で、EDRウイルス対策ソリューションではない場合でも、Microsoft Defender ウイルス対策モードで無効にします。 EDRモードでは、デバイスで検出された悪意のあるアイテム (侵害後) を検出して修復します。 詳細については、「ブロック モード[EDR」を参照してください](edr-in-block-mode.md)。

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>データの状態を確認するMicrosoft Defender ウイルス対策

次の表で説明するように、いくつかの方法のいずれかを使用して、Microsoft Defender ウイルス対策の状態を確認できます。

<br/><br/>

 | Method | Procedure | 
 |---|---| 
 | Windows セキュリティアプリ |  1. デバイスでWindowsアプリをWindows セキュリティします。<br/>2. [ **ウイルス対策] &を選択します**。<br/>3. [プロバイダー **Who保護しますか?** [プロバイダーの管理 **] を選択します**。<br/>4. [セキュリティ **プロバイダー] ページ** の [ウイルス対策]**の下** に、[セキュリティ プロバイダー **Microsoft Defender ウイルス対策がオンになっている必要があります**。 | 
 | タスク マネージャー |  1. デバイスWindowsタスク マネージャー アプリを開きます。<br/>2. [詳細] タブ **を選択** します。<br/>3. リストで **MsMpEng.exe** を探します。 | 
 | Windows PowerShell <br/><br/> (ユーザーが実行Microsoft Defender ウイルス対策確認するには) |  1. デバイスで、Windowsを開Windows PowerShell。 <br/>2. 次の PowerShell コマンドレットを実行します `Get-Process` 。<br/>3. 結果を確認します。 有効になっている場合 **MsMpEng.exe** がMicrosoft Defender ウイルス対策表示されます。 | 
 | Windows PowerShell <br/><br/> (ウイルス対策保護が実行されているのを確認するには) |  [Get-MpComputerStatus PowerShell コマンドレットを使用できます](/powershell/module/defender/get-mpcomputerstatus)。 <br/><br/>1. デバイスで、Windowsを開Windows PowerShell。<br/>2. 次の PowerShell コマンドレットを実行します `Get-MpComputerStatus | select AMRunningMode` 。<br/>3. 結果を確認します。 エンドポイントで有効になっている場合は **、[** 標準] または **[パッシブ** Microsoft Defender ウイルス対策が表示されます。  | 
 | コマンド プロンプト |  1. デバイスで、Windowsを開きます。<br/>2. と `sc query windefend` 入力し、Enter キーを押します。<br/>3. 結果を確認して、Microsoft Defender ウイルス対策モードで実行されている状態を確認します。  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>データの状態のMicrosoft Defender ウイルス対策詳細

このセクションの表では、このセクションで表示されるさまざまな状態Microsoft Defender ウイルス対策。

<br/><br/>

 |  State  |  動作  | 
 |---|---| 
 |  アクティブ モード  |  アクティブ モードでは、Microsoft Defender ウイルス対策はマシン上のウイルス対策アプリとして使用されます。 設定、グループ ポリシー、グループ ポリシー、その他の管理Microsoft Intuneを使用して構成されているユーザーが適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (エンドポイント自体の構成マネージャーやMicrosoft Defender ウイルス対策 アプリなど) で報告されます。  | 
 |  パッシブ モード  |  パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されず、Microsoft Defender ウイルス対策によって脅威の修復を行われることは *ありません*。 ただし、ブロック モードではエンドポイントの検出と応答[(EDR)](edr-in-block-mode.md)によって脅威を修復できます。 <br/><br/> ファイルがスキャンされ、Defender for Endpoint サービスと共有される脅威検出のレポートが提供されます。 Defender [for Cloud](microsoft-defender-security-center.md)にアラートが表示Microsoft Defender ウイルス対策ソースとして表示される場合Microsoft Defender ウイルス対策がパッシブ モードの場合でも発生します。 <br/><br/> Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[Microsoft Defender ウイルス対策の更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)をすることができますが、デバイスに Microsoft 以外のウイルス対策製品があり、マルウェアからリアルタイムで保護されている場合、Microsoft Defender ウイルス対策をアクティブ モードにすることはできません。 <br/><br/> セキュリティの多層防御と検出の有効性を最適化するには、Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも、ウイルス対策とマルウェア対策の更新プログラムを取得してください。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。 <br/><br/> **注**: パッシブ モードは、デバイスでWindows Server 2016。  | 
 |  無効 <br/><br/> または <br/><br/> アンインストール  |  無効またはアンインストールされた場合、Microsoft Defender ウイルス対策ウイルス対策アプリとして使用されません。 ファイルのスキャン、脅威の修復は行われません。 <br/><br/> Microsoft Defender ウイルス対策の無効化/アンインストールは一般的にお勧めしません。Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、できたら　Microsoft Defender ウイルス対策をパッシブにしてください。 <br/><br/> Microsoft Defender ウイルス対策 が自動的に無効になっている場合は、Microsoft 以外のウイルス対策/マルウェア対策製品の有効期限が切れた場合や、ウイルス、マルウェア、その他の脅威からのリアルタイム保護が停止した場合に自動的に再び有効にすることができます。 Microsoft Defender ウイルス対策の自動再有効化を使用すると、ウイルス対策保護をデバイス上で確実に維持することができます。 <br/><br/> また、Microsoft[以外のウイルス](limited-periodic-scanning-microsoft-defender-antivirus.md)対策アプリを使用している場合は、Microsoft Defender ウイルス対策 エンジンと一緒に動作する限られた定期的なスキャンを使用して、定期的に脅威を確認することもできます。  | 


## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](/microsoft-365/compliance/endpoint-dlp-learn-about)
