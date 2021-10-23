---
title: 管理インストルメンテーションを使用してWindowsスキャンをスケジュールする
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
ms.openlocfilehash: 507bcd55dc04c86d98550da19f78486e64abf556
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555514"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a>Windows Management Instrumentation (WMI) を使用してウイルス対策スキャンをスケジュールする

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。 スキャンのスケジュール設定とスキャンの種類の詳細については、「スケジュールされたクイック スキャンまたはフル スキャンの構成[」をMicrosoft Defender ウイルス対策してください](schedule-antivirus-scans.md)。 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a>スキャンをWindowsする場合は、管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

詳細および許可されるパラメーターについては[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a>エンドポイントが使用されていないときにスキャンをスケジュールする WMI

次の [プロパティに対して、MSFT_MpPreferenceクラスの](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) Set メソッドを使用します。

```WMI
ScanOnlyIfIdleEnabled
```

API と許可パラメーターの詳細については[、「WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)のWindows Defender参照してください。

> [!NOTE]
> エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a>修復を完了するためのスキャンをスケジュールするための WMI

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

## <a name="wmi-for-scheduling-daily-scans"></a>毎日のスキャンをスケジュールする WMI

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。

```WMI
ScanScheduleQuickScanTime
```

詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。

