---
title: Windows Management Instrumentation を使用してウイルス対策スキャンをスケジュールする
description: WMI を使用してウイルス対策スキャンをスケジュールする
keywords: クイック スキャン、フル スキャン、WMI、スケジュール、ウイルス対策
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
ms.openlocfilehash: 2b25876a43dea3b1598d4bdfa89cf4724c0fca14
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788922"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Windows Management Instrumentation (WMI) を使用してウイルス対策スキャンをスケジュールする

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

この記事では、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。 スキャンのスケジュール設定とスキャンの種類の詳細については、「[スケジュールされたクイック スキャンまたはフル Microsoft Defender ウイルス対策 スキャンの構成](schedule-antivirus-scans.md)」を参照してください。 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>Windows管理命令 (WMI) を使用してスキャンをスケジュールする

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

詳細と許可されるパラメーターについては、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていない場合のスキャンをスケジュールするための WMI

次のプロパティには [、MSFT_MpPreference クラスの Set メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) を使用します。

```WMI
ScanOnlyIfIdleEnabled
```

API と許可されるパラメーターの詳細については、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

> [!NOTE]
> エンドポイントが使用されていない時間にスキャンをスケジュールすると、スキャンは CPU 調整構成を受け入れず、使用可能なリソースを最大限に活用して、できるだけ早くスキャンを完了します。


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>修復を完了するためのスキャンをスケジュールするための WMI

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

詳細と許可されるパラメーターについては、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

## <a name="wmi-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールするための WMI

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85))を使用します。

```WMI
ScanScheduleQuickScanTime
```

詳細と許可されるパラメーターについては、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)