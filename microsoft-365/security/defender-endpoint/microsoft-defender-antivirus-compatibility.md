---
title: Microsoft Defender ウイルス対策の他のセキュリティ製品との互換性
description: 他のセキュリティ製品を使用した Microsoft Defender ウイルス対策とオペレーティング システムについて説明します。
keywords: Windows Defender、Defender for Endpoint、次世代、ウイルス対策、互換性、パッシブ モード
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 08/05/2021
ms.openlocfilehash: 9d00b4a3342a075f71b95163fc2312253ea06b50a12a737a97609658b46d5e11
ms.sourcegitcommit: 4f074a8598a430344a2361728a64b8b8c0e1d215
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54520593"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender ウイルス対策互換性

**適用対象:**

- Microsoft Defender ウイルス対策
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Microsoft Defender ウイルス対策のバージョンを実行しているエンドポイントに自動的にインストールWindows。

- Windows 10以降
- Windows Server 2016
- Windowsサーバー、バージョン 1803 以降
- Windows Server 2019

しかし、別の (Microsoft 以外の) ウイルス対策/マルウェア対策ソリューションを使用するとどうなるでしょうか。 Microsoft Defender ウイルス対策を別のウイルス対策製品と共に実行できますか? 答えは、オペレーティング システムや [、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) とウイルス対策保護を組み合わせて使用するかどうかなど、いくつかの要因に依存します。 

この記事では、Defender for Endpoint のMicrosoft Defender ウイルス対策、Microsoft 以外のウイルス対策/マルウェア対策ソリューションで発生する問題について説明します。

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Defender for Endpoint のないウイルス対策保護

このセクションでは、Defender for Endpoint Microsoft Defender ウイルス対策オンボーディングされていないエンドポイント上の Microsoft ウイルス対策/マルウェア対策製品以外の製品について説明します。 次の表に、期待する内容を示します。 <br/><br/>

| Windows バージョン   | プライマリ ウイルス対策/マルウェア対策ソリューション  | Microsoft Defender ウイルス対策 |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender ウイルス対策  | アクティブ モード |
| Windows 10  | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | 無効モード (自動的に発生)    |
| Windows Server 2016 <br/><br/> Windows Server バージョン 1803 以降 <br/><br/> Windows Server 2019 | Microsoft Defender ウイルス対策  | アクティブ モード |
| Windows Server 2016 <br/><br/> Windows Server バージョン 1803 以降 <br/><br/> Windows Server 2019 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | 無効 (手動で設定) <sup> [[1](#fn1)]<sup></sup>  |

(<a id="fn1">1</a>) Windows Server で Microsoft 以外のウイルス対策製品を実行している場合は、グループ ポリシーを使用して Microsoft Defender ウイルス対策 をオフにするか[、DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーを使用して Microsoft Defender ウイルス対策 を無効にできます。 レジストリ キーを使用するには、に移動し、 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` という名前の DWORD エントリを設定または作成します `DisableAntiSpyware` 。 その値を `1` (レジストリ キーの値を true に設定します) に設定します。 

> [!TIP]
> Windows Server インストールの主な相違点と管理オプションについては、「[Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)」 を参照します。 このWindows Server 2016の代 *わりに、Windows Defender ウイルス対策**が表示* Microsoft Defender ウイルス対策。

## <a name="antivirus-protection-with-defender-for-endpoint"></a>Defender for Endpoint によるウイルス対策保護

組織が Defender for Endpoint と共に Microsoft 以外のウイルス対策/マルウェア対策ソリューションを使用している場合、Microsoft Defender ウイルス対策 はオペレーティング システムに応じてパッシブ モードで実行できます。 <br/><br/>

| Windows バージョン   | プライマリ ウイルス対策/マルウェア対策ソリューション  | Microsoft Defender ウイルス対策 |
|------|------|-------|-------|
| Windows 10以降 | Microsoft Defender ウイルス対策 | アクティブ モード |
| Windows 10以降 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | パッシブ モード (自動的に行われます) |
| Windows Server 2016 <br/><br/> Windows Server バージョン 1803 以降 <br/><br/> Windows Server 2019 | Microsoft Defender ウイルス対策  | アクティブ モード |
| Windows Server バージョン 1803 以降 <br/><br/> Windows Server 2019 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | パッシブ モード (手動で設定) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft 以外のウイルス対策/マルウェア対策ソリューション | 無効 (手動で設定) <sup> [[3](#fn3)]<sup> |

(<a id="fn2">2</a>) Windows Server、バージョン 1803 以降、または Windows Server 2019 では、Microsoft 以外のウイルス対策製品をインストールするときに、Microsoft Defender ウイルス対策 をパッシブ モードに手動で設定できます。 **ForceDefenderPassiveMode** レジストリ キーを使用して、このタスクを実行できます。 レジストリ キーを使用するには、に移動し、 `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` という名前の DWORD エントリを設定または作成します `ForceDefenderPassiveMode` 。 その値を `1` (レジストリ キーの値を true に設定する) に *設定します*。 詳細については、「パッシブ モードと[パッシブ サーバー」をWindowsしてください](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server)。

(<a id="fn3">3</a>) Windows Server 2016では、グループ ポリシーを使用して Windows Defender ウイルス対策 を無効にするか[、DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)レジストリ キーを使用して、Microsoft Defender ウイルス対策 を無効にできます。 レジストリ キーを使用するには、に移動し、 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` という名前の DWORD エントリを設定または作成します `DisableAntiSpyware` 。 その値を `1` (レジストリ キーの値を true に設定する) に *設定します*。 

> [!TIP]
> Windows Server インストールの主な相違点と管理オプションについては、「[Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)」 を参照します。 このWindows Server 2016の代 *わりに、Windows Defender ウイルス対策**が表示* Microsoft Defender ウイルス対策。

### <a name="why-run-microsoft-defender-antivirus-in-passive-mode"></a>パッシブ モードでMicrosoft Defender ウイルス対策実行する理由

Defender for Endpoint には、エンドポイントにインストールされているウイルス対策保護をさらに拡張する機能が含まれています。 別のウイルス対策ソリューションとMicrosoft Defender ウイルス対策を実行するメリットがあります。 

たとえば、ブロック モードのエンドポイント検出と応答[(EDR)](edr-in-block-mode.md)は、プライマリ ウイルス対策製品ではない場合でも、悪意のあるMicrosoft Defender ウイルス対策保護を提供します。 このような機能では、Microsoft Defender ウイルス対策モードまたはアクティブ モードでインストールおよび実行する必要があります。

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>パッシブ モードでMicrosoft Defender ウイルス対策の要件

パッシブ モードでMicrosoft Defender ウイルス対策するには、エンドポイントが次の要件を満たす必要があります。

- オペレーティング システム: Windows 10以降。Windowsサーバー、バージョン 1803 以降。または Windows Server 2019
- Microsoft Defender ウイルス対策インストールする必要があります
- Microsoft 以外のウイルス対策/マルウェア対策製品をインストールし、プライマリ ウイルス対策ソリューションとして使用する必要があります。
- エンドポイントは Defender for Endpoint にオンボードする必要があります

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Microsoft Defender ウイルス対策が Defender for Endpoint 機能に影響を与えるしくみ

Defender for Endpoint は、パッシブ モードMicrosoft Defender ウイルス対策実行できるかどうかに影響します。 Microsoft Defender ウイルス対策 Defender for Endpoint の特定の機能にも影響を与える可能性があります。 たとえば、リアルタイム保護は、アクティブまたはパッシブ Microsoft Defender ウイルス対策モードの場合は動作しますが、Microsoft Defender ウイルス対策が無効またはアンインストールされている場合は機能しません。 

このセクションの表は、Microsoft Defender ウイルス対策 がアクティブ モード、パッシブ モード、または無効/アンインストールの各機能に従って、アクティブに動作するかどうかの概要を示します。 

> [!IMPORTANT]
> 次の表は、情報のみを提供するように設計されています。 パッシブ モードで Microsoft Defender ウイルス対策 を使用している場合、またはブロック モードで[EDR](edr-in-block-mode.md)を使用している場合は、リアルタイム保護、クラウド配信保護、制限付き定期的なスキャンなどの機能をオフにしません。侵害後に検出された悪意のあるアーティファクトを検出して修復するために、舞台裏で動作します。 
<br/><br/>

| 保護 | Microsoft Defender ウイルス対策 <br/> アクティブ モード | Microsoft Defender ウイルス対策 <br/> パッシブ モード |  Microsoft Defender ウイルス対策 <br/> 無効またはアンインストール済み | [ブロック モードの EDR](edr-in-block-mode.md) |
|:---|:---|:---|:---|:---|
| [リアルタイム保護](configure-real-time-protection-microsoft-defender-antivirus.md) と [クラウドによる保護](enable-cloud-protection-microsoft-defender-antivirus.md) | はい | No <sup> [[5](#fn5)]<sup> | いいえ | いいえ |
| [限定された定期的なスキャンの可用性](limited-periodic-scanning-microsoft-defender-antivirus.md) | いいえ | いいえ | はい | いいえ |
| [スキャン中ファイルと検出情報](review-scan-results-microsoft-defender-antivirus.md) | はい | はい | いいえ | はい |
|  [脅威の修復](configure-remediation-microsoft-defender-antivirus.md) | はい | メモ <sup> [ 6 ][を参照してください。](#fn6)<sup> | いいえ | はい |
| [セキュリティ インテリジェンスの更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md) | はい | はい | いいえ | はい |

(<a id="fn5">5</a>) 一般に、Microsoft Defender ウイルス対策 がパッシブ モードの場合、リアルタイム保護は、有効でパッシブ モードの場合でも、ブロックまたは強制を提供しません。 

(<a id="fn6">6</a>) Microsoft Defender ウイルス対策モードの場合、脅威修復機能はスケジュールされたスキャンまたはオンデマンド スキャン中にのみアクティブになります。

> [!NOTE]
> [Microsoft 365 Endpoint データ損失防止](/microsoft-365/compliance/endpoint-dlp-learn-about) 保護は、Microsoft Defender ウイルス対策がアクティブ モードまたはパッシブ モードの場合、正常に動作し続けます。

## <a name="important-notes"></a>重要事項

- Microsoft Defender ウイルス対策、Defender for Endpoint、またはアプリで使用される関連サービスを無効、停止、または変更Windows セキュリティできません。 この推奨事項には、*wscsvc*、*SecurityHealthService*、*MsSense*、*Sense*、*WinDefend*、または *MsMpEng* へのサービスとプロセスが含まれます。 これらのサービスを手動で変更すると、デバイスが深刻な不安定状態になり、ネットワークが脆弱になることがあります。 これらのサービスを無効、停止、または変更すると、Microsoft 以外のウイルス対策ソリューションを使用する場合に問題が発生したり、[Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md) での情報の表示方法にも問題が発生したりすることがあります。

- Defender for Endpoint で、EDRウイルス対策ソリューションではない場合でも、Microsoft Defender ウイルス対策モードで無効にします。 EDRモードでは、デバイスで検出された悪意のあるアイテム (侵害後) を検出して修復します。 詳細については、「ブロック モード[EDR」を参照してください](edr-in-block-mode.md)。

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>データの状態のMicrosoft Defender ウイルス対策詳細

このセクションの表では、このセクションで表示されるさまざまな状態Microsoft Defender ウイルス対策。 <br/><br/>

| Microsoft Defender ウイルス対策  | 動作  |
|---------|---------|
| アクティブ モード  | アクティブ モードでは、Microsoft Defender ウイルス対策はマシン上のウイルス対策アプリとして使用されます。 設定、グループ ポリシー、グループ ポリシー、その他の管理Microsoft Intuneを使用して構成されているユーザーが適用されます。 ファイルがスキャンされ、脅威が修復され、検出情報が構成ツール (エンドポイント自体の構成マネージャーやMicrosoft Defender ウイルス対策 アプリなど) で報告されます。   |
| パッシブ モード  | パッシブ モードでは、Microsoft Defender ウイルス対策はウイルス対策アプリとして使用されず、Microsoft Defender ウイルス対策によって脅威の修復を行われることは *ありません*。 ただし、ブロック モードではエンドポイントの検出と応答[(EDR)](edr-in-block-mode.md)によって脅威を修復できます。<br/><br/> ファイルがスキャンされ、Defender for Endpoint サービスと共有される脅威検出のレポートが提供されます。 Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[セキュリティ センター](microsoft-defender-security-center.md) で Microsoft Defender ウイルス対策がソースとして表示される警告を受け取る場合があります。 <br/><br/>Microsoft Defender ウイルス対策がパッシブ モードの場合でも、[Microsoft Defender ウイルス対策の更新プログラムの管理](manage-updates-baselines-microsoft-defender-antivirus.md)をすることができますが、デバイスに Microsoft 以外のウイルス対策製品があり、マルウェアからリアルタイムで保護されている場合、Microsoft Defender ウイルス対策をアクティブ モードにすることはできません。 <br/><br/>セキュリティの多層防御と検出の有効性を最適化するには、Microsoft Defender ウイルス対策がパッシブ モードで実行されている場合でも、ウイルス対策とマルウェア対策の更新プログラムを取得してください。 [Microsoft Defender ウイルス対策の更新の管理を行い、ベースラインを適用する方法](manage-updates-baselines-microsoft-defender-antivirus.md)を参照してください。 <br/><br/>**注**: パッシブ モードは、デバイスでWindows Server 2016。 |
| 無効 <br/>または<br/>アンインストール    | 無効またはアンインストールされた場合、Microsoft Defender ウイルス対策ウイルス対策アプリとして使用されません。 ファイルのスキャン、脅威の修復は行われません。<br/><br/> Microsoft Defender ウイルス対策の無効化/アンインストールは一般的にお勧めしません。Microsoft 以外のマルウェア対策/ウイルス対策ソリューションを使用している場合は、できたら　Microsoft Defender ウイルス対策をパッシブにしてください。 <br/><br/>Microsoft Defender ウイルス対策 が自動的に無効になっている場合は、Microsoft 以外のウイルス対策/マルウェア対策製品の有効期限が切れた場合や、ウイルス、マルウェア、その他の脅威からのリアルタイム保護が停止した場合に自動的に再び有効にすることができます。 Microsoft Defender ウイルス対策の自動再有効化を使用すると、ウイルス対策保護をデバイス上で確実に維持することができます。<br/><br/>また、Microsoft[以外のウイルス](limited-periodic-scanning-microsoft-defender-antivirus.md)対策アプリを使用している場合は、Microsoft Defender ウイルス対策 エンジンと一緒に動作する限られた定期的なスキャンを使用して、定期的に脅威を確認することもできます。       |

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [ブロック モードの EDR](edr-in-block-mode.md)
- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](/microsoft-365/compliance/endpoint-dlp-learn-about)
