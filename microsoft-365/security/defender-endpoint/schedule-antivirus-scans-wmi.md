---
title: 管理インストルメンテーションを使用してWindowsスキャンをスケジュールする
description: WMI を使用してウイルス対策スキャンをスケジュールする
keywords: クイック スキャン、フル スキャン、WMI、スケジュール、ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1aa174f4601fb57eebbc4fb7c78e1809b9f072c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879710"
---
# <a name="schedule-antivirus-scans-using-windows-management-instrumentation-wmi"></a><span data-ttu-id="5b257-104">管理インストルメンテーション (WMI) Windowsウイルス対策スキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="5b257-104">Schedule antivirus scans using Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="5b257-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5b257-105">**Applies to:**</span></span>

- [<span data-ttu-id="5b257-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5b257-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5b257-107">この記事では、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b257-107">This article describes how to configure scheduled scans using WMI.</span></span> <span data-ttu-id="5b257-108">スキャンのスケジュール設定とスキャンの種類の詳細については、「スケジュールされたクイック スキャンまたはフル スキャンの構成[」をMicrosoft Defender ウイルス対策してください](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="5b257-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="5b257-109">スキャンをWindowsする場合は、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b257-109">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="5b257-110">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b257-110">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="5b257-111">詳細および許可されるパラメーターについては[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5b257-111">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="wmi-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="5b257-112">エンドポイントが使用されていないときにスキャンをスケジュールする WMI</span><span class="sxs-lookup"><span data-stu-id="5b257-112">WMI for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="5b257-113">次の [プロパティに対して、MSFT_MpPreferenceクラスの](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b257-113">Use the [Set method of the MSFT_MpPreference class](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="5b257-114">API と許可パラメーターの詳細については[、「WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)のWindows Defender参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b257-114">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="5b257-115">エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。</span><span class="sxs-lookup"><span data-stu-id="5b257-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>


## <a name="wmi-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="5b257-116">修復を完了するためのスキャンをスケジュールするための WMI</span><span class="sxs-lookup"><span data-stu-id="5b257-116">WMI for scheduling scans to complete remediation</span></span>

<span data-ttu-id="5b257-117">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b257-117">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="5b257-118">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="5b257-118">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="wmi-for-scheduling-daily-scans"></a><span data-ttu-id="5b257-119">毎日のスキャンをスケジュールする WMI</span><span class="sxs-lookup"><span data-stu-id="5b257-119">WMI for scheduling daily scans</span></span>

<span data-ttu-id="5b257-120">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b257-120">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="5b257-121">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="5b257-121">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

