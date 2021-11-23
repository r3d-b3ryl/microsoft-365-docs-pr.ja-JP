---
title: PowerShell を使用してウイルス対策スキャンをスケジュールする
description: PowerShell を使用してウイルス対策スキャンをスケジュールする
keywords: クイック スキャン、フル スキャン、ウイルス対策、スケジュール、PowerShell
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
ms.openlocfilehash: 251c220ab8ede37f69e820e48af08495507504a6
ms.sourcegitcommit: 2e05865beeb2051fd9ece212a46179310b946a46
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2021
ms.locfileid: "61148832"
---
# <a name="schedule-antivirus-scans-using-powershell"></a>PowerShell を使用してウイルス対策スキャンをスケジュールする

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、PowerShell コマンドレットを使用してスケジュールされたスキャンを構成する方法について説明します。 スキャンのスケジュール設定とスキャンの種類の詳細については、「スケジュールされたクイック スキャンまたはフル スキャンの構成[」をMicrosoft Defender ウイルス対策してください](schedule-antivirus-scans.md)。 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a>PowerShell コマンドレットを使用してスキャンをスケジュールする

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して Microsoft Defender ウイルス対策 コマンドレットと Defender Microsoft Defender ウイルス対策[ウイルス](/powershell/module/defender/)対策コマンドレットを構成および実行する」を参照してください。

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていないときにスキャンをスケジュールする PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

詳細については[、「Use PowerShell コマンドレットを使用](use-powershell-cmdlets-microsoft-defender-antivirus.md)して、ウイルス対策コマンドレットと Defender ウイルス対策コマンドレットを構成Microsoft Defender ウイルス対策[実行する」を参照してください](/powershell/module/defender/)。

> [!NOTE]
> エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>修復を完了するためのスキャンをスケジュールするための PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender ウイルス](/powershell/module/defender/)対策コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールする PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

PowerShell を Microsoft Defender ウイルス対策 と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、Microsoft Defender ウイルス対策 Defender ウイルス対策コマンドレットを構成および実行する」を[参照してください](/powershell/module/defender/)。
