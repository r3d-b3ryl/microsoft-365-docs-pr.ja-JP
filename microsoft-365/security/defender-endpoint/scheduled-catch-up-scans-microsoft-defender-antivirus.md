---
title: Microsoft Defender ウイルス対策で定期的なクイック スキャンとフル スキャンをスケジュールする
description: 定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)
keywords: クイック スキャン、フル スキャン、クイックスキャン、フル スキャン、スケジュール スキャン、毎日、毎週、時刻、スケジュール済み、定期的、定期的
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691300"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>スケジュールされたクイック スキャンまたはフル Microsoft Defender ウイルス対策スキャンを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> 既定では、Microsoft Defender ウイルス対策は、スケジュールされたスキャンの 15 分前に更新プログラムをチェックします。 保護更新 [プログラムをダウンロードして適用するスケジュール](manage-protection-update-schedule-microsoft-defender-antivirus.md) を管理して、この既定を上書きできます。 

常時オンのリアルタイム保護とオンデマンド スキャンに加[](run-scan-microsoft-defender-antivirus.md)えて、定期的にスケジュールされたスキャンを設定できます。 

スキャンの種類、スキャンが実行される時間、および保護更新後にスキャンが実行される場合、または[](manage-protection-updates-microsoft-defender-antivirus.md)エンドポイントが使用されている場合に構成できます。 修復を完了するための特別なスキャンがいつ行われるのかも指定できます。

この記事では、グループ ポリシー、PowerShell コマンドレット、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。 Microsoft Endpoint [Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) または Microsoft Intune を使用してスケジュール スキャンを [構成することもできます](/mem/intune/configuration/device-restrictions-windows-10)。

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a>この記事で説明されているグループ ポリシー設定を構成するには

1.  グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

3.  グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

4.  [管理 **用テンプレート] をクリックします**。

5.  ツリーを **Microsoft Defender** ウイルス対策> Windows コンポーネントに展開し、次の表で指定した場所を展開します。

6. 下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。 

7. **[OK] を** クリックし、他の設定を繰り返します。

また、「保護更新プログラム [をダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックも参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a>クイック スキャンとフル スキャン、およびカスタム スキャン

スケジュールされたスキャンをセットアップするときに、スキャンを完全スキャンとクイック スキャンのかどうかを設定できます。

クイック スキャンでは、レジストリ キーや既知の Windows スタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所を確認します。 

ファイルを[](configure-real-time-protection-microsoft-defender-antivirus.md)開いて閉じたときに確認する常時オンのリアルタイム保護機能と組み合わせると、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアの両方を強力にカバーできます。  

ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分な手段です。

フル スキャンは、マルウェアの脅威が発生したエンドポイントで、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含めらな場合に役立ちます。 この例では、オンデマンド スキャンを実行するときにフル スキャン [を使用できます](run-scan-microsoft-defender-antivirus.md)。

カスタム スキャンを使用すると、スキャンするファイルとフォルダー (USB ドライブなど) を指定できます。 

>[!NOTE]
>既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。

## <a name="set-up-scheduled-scans"></a>スケジュールされたスキャンのセットアップ

スケジュールされたスキャンは、指定した日と時刻に実行されます。 グループ ポリシー、PowerShell、WMI を使用して、スケジュールされたスキャンを構成できます。

>[!NOTE]
>予約済みフル スキャン中にコンピューターがプラグを抜いてバッテリーで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止し、完了前にスキャンが停止したと示されます。 Microsoft Defender ウイルス対策は、次回のスケジュールされた時刻にフル スキャンを実行します。

### <a name="use-group-policy-to-schedule-scans"></a>グループ ポリシーを使用してスキャンをスケジュールする

|場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | スケジュールされたスキャンに使用するスキャンの種類を指定する | クイック スキャン |
|スキャン | スケジュールされたスキャンを実行する週の日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
|スキャン | スケジュールされたスキャンを実行する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |
|ルート | スケジュールされたタスク時間をランダム化する |Microsoft Defender ウイルス対策: スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。 <br>FEP/SCEP: 任意の間隔にプラスまたはマイナス 30 分にランダム化します。 これは、VM または VDI の展開で役立ちます。 | Enabled |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell コマンドレットを使用してスキャンをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Windows 管理命令 (WMI) を使用してスキャンをスケジュールする

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a>エンドポイントが使用されていない場合にのみ、スケジュールされたスキャンを開始する

スケジュールされたスキャンは、エンドポイントがオンになっているが、グループ ポリシー、PowerShell、または WMI で使用されていない場合にのみ発生する設定できます。

> [!NOTE]
> これらのスキャンは、CPU 調整構成を尊重し、可能な限り速くスキャンを完了するために利用可能なリソースをフルに活用します。

### <a name="use-group-policy-to-schedule-scans"></a>グループ ポリシーを使用してスキャンをスケジュールする

|場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する | コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。 | Enabled |

### <a name="use-powershell-cmdlets"></a>PowerShell コマンドレットの使用

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi"></a>Windows 管理命令 (WMI) の使用

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanOnlyIfIdleEnabled
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a>修復を完了するためにフル スキャンを実行する必要がある場合の構成

一部の脅威では、削除と修復を完了するためにフル スキャンが必要な場合があります。 これらのスキャンをグループ ポリシー、PowerShell、または WMI で実行するスケジュールを設定できます。

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a>グループ ポリシーを使用して修復に必要なスキャンをスケジュールする

| 場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|---|---|---|---|
|修復 | スケジュールされたフル スキャンを実行して修復を完了する日を指定する | スキャンを実行する日 (または実行しない) を指定します。 | Never |
|修復 | スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |

### <a name="use-powershell-cmdlets"></a>PowerShell コマンドレットの使用

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi"></a>Windows 管理命令 (WMI) の使用

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a>毎日のクイック スキャンをセットアップする

グループ ポリシー、PowerShell、または WMI を使用して、他のスケジュールされたスキャンに加えて実行できる毎日のクイック スキャンを有効にできます。


### <a name="use-group-policy-to-schedule-daily-scans"></a>グループ ポリシーを使用して毎日のスキャンをスケジュールする


|場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | 1 日あたりのクイック スキャンを実行する間隔を指定する | 次のクイック スキャンの前に経過する時間を指定します。 たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。 **0 と入力** すると、毎日のクイック スキャンは実行されません。 | Never |
|スキャン | 毎日のクイック スキャンの時間を指定する | 午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。 | 2 a.m. |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a>PowerShell コマンドレットを使用して毎日のスキャンをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a>Windows 管理命令 (WMI) を使用して毎日のスキャンをスケジュールする

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanScheduleQuickScanTime
```

詳細と許可されるパラメーターについては、以下を参照してください。
- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a>保護更新後にスキャンを有効にする

グループ ポリシーを使用してすべての保護更新後にスキャン [を強制的](manage-protection-updates-microsoft-defender-antivirus.md) に実行できます。

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a>グループ ポリシーを使用して保護の更新後にスキャンをスケジュールする

|場所 | 設定 | 説明 | 既定の設定 (構成されていない場合)|
|:---|:---|:---|:---|
|署名の更新 | セキュリティ インテリジェンスの更新後にスキャンを有効にする | 新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます | Enabled |

## <a name="see-also"></a>関連項目
- [ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンの構成と実行](run-scan-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャン オプションの構成](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md)
- [保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)