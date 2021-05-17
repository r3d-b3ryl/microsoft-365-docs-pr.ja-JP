---
title: 定期的なクイック スキャンとフル スキャンのスケジュールを設定Microsoft Defender ウイルス対策
description: 定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)
keywords: クイック スキャン、フル スキャン、クイックスキャン、フル スキャン、スケジュール スキャン、毎日、毎週、時刻、スケジュール済み、定期的、定期的
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274690"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>スケジュールされたクイックまたは完全な Microsoft Defender ウイルス スキャンを構成する

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 既定では、Microsoft Defender ウイルス対策スキャンの時刻の 15 分前に更新プログラムがチェックされます。 保護更新 [プログラムをダウンロードして適用するスケジュール](manage-protection-update-schedule-microsoft-defender-antivirus.md) を管理して、この既定を上書きできます。 

常時オンのリアルタイム保護とオンデマンド スキャンに加[](run-scan-microsoft-defender-antivirus.md)えて、定期的にスケジュールされたスキャンを設定できます。 

スキャンの種類、スキャンが実行される時間、および保護更新後にスキャンが実行される場合、または[](manage-protection-updates-microsoft-defender-antivirus.md)エンドポイントが使用されている場合に構成できます。 修復を完了するための特別なスキャンがいつ行われるのかも指定できます。

この記事では、グループ ポリシー、PowerShell コマンドレット、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。 また、スケジュール スキャンを構成するには[、Microsoft Endpoint Configuration Managerまたは](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)Microsoft Intune。 [](/mem/intune/configuration/device-restrictions-windows-10)

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>この記事で説明されているグループ ポリシー設定を構成するには

1. グループ ポリシー管理マシンのグループ ポリシー エディターで、[コンピューター構成] [管理用テンプレート] Windows [スキャンMicrosoft Defender ウイルス対策  >    >    >    >  **します**。

2. 構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。

3. グループ ポリシー オブジェクトの設定を指定し **、[OK] を選択します**。 

4. 構成する設定ごとに手順 1 ~ 4 を繰り返します。

5. 通常と同じ方法でグループ ポリシー オブジェクトを展開します。 グループ ポリシー オブジェクトのヘルプが必要な場合は、「 [グループ ポリシー オブジェクトの作成」を参照してください](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。

また、「保護更新プログラム [をダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックも参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>クイック スキャンとフル スキャン、およびカスタム スキャン

スケジュールされたスキャンをセットアップするときに、スキャンを完全スキャンとクイック スキャンのかどうかを設定できます。


|クイック スキャン  |フル スキャン  | カスタム スキャン |
|---------|---------|---------|
|クイック スキャンでは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所Windowsします。 <p>ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されます。 |フル スキャンは、クイック スキャンを実行して開始し、すべてのマウントされた固定ディスクとリムーバブル/ネットワーク ドライブのシーケンシャル ファイル スキャンを続行します (フル スキャンが構成されている場合)。 <p>フル スキャンは、スキャンする必要があるデータの量と種類に応じて、完了に数時間または数日かかる場合があります。<p>完全スキャンが完了すると、新しいセキュリティ インテリジェンスが利用できます。新しいセキュリティ インテリジェンスで他の脅威が検出されない場合は、新しいスキャンが必要です。   | カスタム スキャンは、指定したファイルとフォルダーで実行されるクイック スキャンです。 たとえば、USB ドライブ、またはデバイスのローカル ドライブ上の特定のフォルダーをスキャンすることを選択できます。 <p> | 

>[!NOTE]
>既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。

### <a name="how-do-i-know-which-scan-type-to-choose"></a>選択するスキャンの種類を知る方法

次の表を使用して、スキャンの種類を選択します。


|シナリオ  |推奨されるスキャンの種類  |
|---------|---------|
|定期的なスケジュールされたスキャンを設定する     | クイック スキャン <p>クイック スキャンは、デバイス上のプロセス、メモリ、プロファイル、および特定の場所をチェックします。 常時オン [のリアルタイム保護と](configure-real-time-protection-microsoft-defender-antivirus.md)組み合わせると、クイック スキャンによって、システムから始まるマルウェアとカーネル レベルのマルウェアの両方に強力な範囲を提供できます。 リアルタイム保護は、ファイルを開いて閉じたときに、およびユーザーがフォルダーに移動するたびに、ファイルを確認します。         |
|マルウェアなどの脅威がデバイスで検出される     | フル スキャン <p>完全スキャンは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含されているかどうかを特定するのに役立ちます。         |
|オンデマンド スキャンを [実行する](run-scan-microsoft-defender-antivirus.md)     | フル スキャン  <p>フル スキャンでは、デバイス ディスク上のすべてのファイル (古いファイル、アーカイブ済みファイル、毎日アクセスされていないファイルなど) が検索されます。      |
| USB ドライブなどのポータブル デバイスにマルウェアが含まれているのを確認する | カスタム スキャン <p>カスタム スキャンを使用すると、特定の場所、フォルダー、またはファイルを選択し、クイック スキャンを実行できます。 |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>クイック スキャンとフル スキャンについて他に何を知る必要がありますか?

- 悪意のあるファイルは、クイック スキャンに含まれていない場所に保存できます。 ただし、常時オンのリアルタイム保護は、開いて閉じているすべてのファイルと、ユーザーがアクセスするフォルダー内のすべてのファイルを確認します。 リアルタイム保護とクイック スキャンの組み合わせは、マルウェアに対する強力な保護を提供するのに役立ちます。

- クラウドによる保護によるオン[](cloud-protection-microsoft-defender-antivirus.md)アクセス保護により、システム上でアクセスされるすべてのファイルが最新のセキュリティ インテリジェンスとクラウド 機械学習モデルでスキャンされます。

- リアルタイム保護でマルウェアが検出され、影響を受けるファイルの範囲が最初に決定されない場合、Microsoft Defender ウイルス対策 は修復プロセスの一環としてフル スキャンを開始します。

- フル スキャンでは、クイック スキャンなど、他のスキャンで検出されていない悪意のあるファイルを検出できます。 ただし、フル スキャンには時間がかかる場合があります。また、貴重なシステム リソースを使用して完了できます。

- デバイスがオフラインで長期に及ばない場合、フル スキャンの完了に時間がかかる場合があります。 

## <a name="set-up-scheduled-scans"></a>スケジュールされたスキャンのセットアップ

スケジュールされたスキャンは、指定した日と時刻に実行されます。 グループ ポリシー、PowerShell、WMI を使用して、スケジュールされたスキャンを構成できます。

> [!NOTE]
> スケジュールされたフル スキャン中にデバイスがプラグを抜いてバッテリーで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止し、完了前にスキャンが停止したと示されます。 Microsoft Defender ウイルス対策は、次にスケジュールされた時刻にフル スキャンを実行します。

### <a name="use-group-policy-to-schedule-scans"></a>グループ ポリシーを使用してスキャンをスケジュールする

|場所 | Setting | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | スケジュールされたスキャンに使用するスキャンの種類を指定する | クイック スキャン |
|スキャン | スケジュールされたスキャンを実行する週の日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
|スキャン | スケジュールされたスキャンを実行する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |
|ルート | スケジュールされたタスク時間をランダム化する |このMicrosoft Defender ウイルス対策、スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。 <p>[SCEP では](/mem/intune/protect/certificates-scep-configure)、スキャンを任意の間隔にプラスまたはマイナス 30 分にランダム化します。 これは、仮想マシンまたは VDI 展開で役立ちます。 | Enabled |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell コマンドレットを使用してスキャンをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して powerShell コマンドレットを構成し、Microsoft Defender ウイルス対策 コマンドレットと Microsoft Defender ウイルス対策[Defender](/powershell/module/defender/)コマンドレットを実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>スキャンをWindowsする場合は、管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

詳細および許可されるパラメーターについては[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>エンドポイントが使用されていない場合にのみ、スケジュールされたスキャンを開始する

スケジュールされたスキャンは、エンドポイントがオンになっているが、グループ ポリシー、PowerShell、または WMI で使用されていない場合にのみ発生する設定できます。

> [!NOTE]
> これらのスキャンは、CPU 調整構成を尊重し、可能な限り速くスキャンを完了するために利用可能なリソースをフルに活用します。

### <a name="use-group-policy-to-schedule-scans"></a>グループ ポリシーを使用してスキャンをスケジュールする

|場所 | Setting | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する | コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。 | Enabled |

### <a name="use-powershell-cmdlets"></a>PowerShell コマンドレットの使用

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/)」を参照してください。

### <a name="use-windows-management-instruction-wmi"></a>管理Windows使用 (WMI)

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanOnlyIfIdleEnabled
```

API と許可パラメーターの詳細については[、「WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)のWindows Defender参照してください。

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>修復を完了するためにフル スキャンを実行する必要がある場合の構成

一部の脅威では、削除と修復を完了するためにフル スキャンが必要になる場合があります。 これらのスキャンをグループ ポリシー、PowerShell、または WMI で実行する必要がある場合に指定できます。

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>グループ ポリシーを使用して修復に必要なスキャンをスケジュールする

| 場所 | Setting | 説明 | 既定の設定 (構成されていない場合) |
|---|---|---|---|
|修復 | スケジュールされたフル スキャンを実行して修復を完了する日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
|修復 | スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |

### <a name="use-powershell-cmdlets"></a>PowerShell コマンドレットの使用

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。

### <a name="use-windows-management-instruction-wmi"></a>管理Windows使用 (WMI)

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。


## <a name="set-up-daily-quick-scans"></a>毎日のクイック スキャンをセットアップする

グループ ポリシー、PowerShell、または WMI を使用して、他のスケジュールされたスキャンに加えて実行できる毎日のクイック スキャンを有効にできます。

### <a name="use-group-policy-to-schedule-daily-scans"></a>グループ ポリシーを使用して毎日のスキャンをスケジュールする

|場所 | Setting | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | 1 日あたりのクイック スキャンを実行する間隔を指定する | 次のクイック スキャンの前に経過する時間を指定します。 たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。 **0 と入力** すると、毎日のクイック スキャンは実行されません。 | Never |
|スキャン | 毎日のクイック スキャンの時間を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>PowerShell コマンドレットを使用して毎日のスキャンをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

PowerShell を Microsoft Defender ウイルス対策 と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成Microsoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>毎日のWindowsをスケジュールするには、WMI 管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanScheduleQuickScanTime
```

詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。


## <a name="enable-scans-after-protection-updates"></a>保護更新後にスキャンを有効にする

グループ ポリシーを使用してすべての保護更新後にスキャン [を強制的](manage-protection-updates-microsoft-defender-antivirus.md) に実行できます。

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>グループ ポリシーを使用して保護の更新後にスキャンをスケジュールする

|場所 | Setting | 説明 | 既定の設定 (構成されていない場合)|
|:---|:---|:---|:---|
|署名の更新 | セキュリティ インテリジェンスの更新後にスキャンを有効にする | 新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます | Enabled |

## <a name="see-also"></a>関連項目

- [ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)