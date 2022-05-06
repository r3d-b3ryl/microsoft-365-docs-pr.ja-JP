---
title: PowerShell を使用してウイルス対策スキャンをスケジュールする
description: PowerShell を使用してウイルス対策スキャンをスケジュールする
keywords: クイック スキャン, フル スキャン, ウイルス対策, スケジュール, PowerShell
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 8961428acee5d166b0cdad4982aa5f9ed48020af
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788834"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>PowerShell を使用してウイルス対策スキャンをスケジュールする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

この記事では、PowerShell コマンドレットを使用してスケジュールされたスキャンを構成する方法について説明します。 スキャンのスケジュール設定とスキャンの種類の詳細については、「[スケジュールされたクイック スキャンまたはフル Microsoft Defender ウイルス対策 スキャンの構成](schedule-antivirus-scans.md)」を参照してください。 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell コマンドレットを使用してスキャンをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

詳細については、「[PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策コマンドレットと](use-powershell-cmdlets-microsoft-defender-antivirus.md) [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成および実行する」を参照してください。Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「」を参照してください。

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていない場合のスキャンをスケジュールするための PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender ウイルス対策 コマンドレット ](/powershell/module/defender/)」を参照してください。

> [!NOTE]
> エンドポイントが使用されていない時間にスキャンをスケジュールすると、スキャンは CPU 調整構成を受け入れず、使用可能なリソースを最大限に活用して、できるだけ早くスキャンを完了します。

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>修復を完了するためのスキャンをスケジュールするための PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

[Microsoft Defender ウイルス対策で PowerShell を使用する](use-powershell-cmdlets-microsoft-defender-antivirus.md)方法の詳細については、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールするための PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「[PowerShell コマンドレットを使用して、Microsoft Defender ウイルス対策](use-powershell-cmdlets-microsoft-defender-antivirus.md)および [Defender ウイルス対策コマンドレット](/powershell/module/defender/)を構成して実行する」を参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)