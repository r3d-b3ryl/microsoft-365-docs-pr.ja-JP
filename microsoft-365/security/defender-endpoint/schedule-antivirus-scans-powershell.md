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
ms.openlocfilehash: 03978feb5a9d0ca98d432fbec91e0fd5ce83724e
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111257"
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

詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して Microsoft Defender ウイルス対策 コマンドレットと[Defender for](/powershell/module/defender/) Microsoft Defender ウイルス対策 Cloud コマンドレットを構成および実行する」を参照してください。

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていないときにスキャンをスケジュールする PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

詳細については[、「Use PowerShell コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)使用して、クラウドコマンドレットと Defender for Cloud コマンドレットを構成Microsoft Defender ウイルス対策実行する」[を参照してください](/powershell/module/defender/)。

> [!NOTE]
> エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a>修復を完了するためのスキャンをスケジュールするための PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

PowerShell コマンドレットを構成して実行する Microsoft Defender ウイルス対策 および[Defender for Cloud](/powershell/module/defender/)コマンドレットの詳細については、「PowerShell コマンドレットとクラウド コマンドレットを使用する」を参照Microsoft Defender ウイルス対策。 [](use-powershell-cmdlets-microsoft-defender-antivirus.md)

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールする PowerShell コマンドレット

次のコマンドレットを使用します。

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

PowerShell を Microsoft Defender ウイルス対策 と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、Microsoft Defender ウイルス対策および Defender for Cloud コマンドレットを構成および実行する」を[参照してください](/powershell/module/defender/)。
