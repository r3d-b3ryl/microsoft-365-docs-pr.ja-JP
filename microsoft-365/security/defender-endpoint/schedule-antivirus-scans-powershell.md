---
title: PowerShell を使用してウイルス対策スキャンをスケジュールする
description: PowerShell を使用してウイルス対策スキャンをスケジュールする
keywords: クイック スキャン、フル スキャン、ウイルス対策、スケジュール、PowerShell
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
ms.openlocfilehash: 73ba654dd312c63651f0cf43244796e94e8ad55b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879713"
---
# <a name="schedule-antivirus-scans-using-powershell"></a><span data-ttu-id="32c60-104">PowerShell を使用してウイルス対策スキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="32c60-104">Schedule antivirus scans using PowerShell</span></span>

<span data-ttu-id="32c60-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="32c60-105">**Applies to:**</span></span>

- [<span data-ttu-id="32c60-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32c60-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="32c60-107">この記事では、PowerShell コマンドレットを使用してスケジュールされたスキャンを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32c60-107">This article describes how to configure scheduled scans using PowerShell cmdlets.</span></span> <span data-ttu-id="32c60-108">スキャンのスケジュール設定とスキャンの種類の詳細については、「スケジュールされたクイック スキャンまたはフル スキャンの構成[」をMicrosoft Defender ウイルス対策してください](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="32c60-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="32c60-109">PowerShell コマンドレットを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="32c60-109">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="32c60-110">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32c60-110">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="32c60-111">詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して powerShell コマンドレットを構成し、Microsoft Defender ウイルス対策 コマンドレットと Microsoft Defender ウイルス対策[Defender](/powershell/module/defender/)コマンドレットを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32c60-111">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="32c60-112">エンドポイントが使用されていないときにスキャンをスケジュールする PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="32c60-112">PowerShell cmdlets for scheduling scans when an endpoint is not in use</span></span>

<span data-ttu-id="32c60-113">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32c60-113">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="32c60-114">詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32c60-114">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

> [!NOTE]
> <span data-ttu-id="32c60-115">エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。</span><span class="sxs-lookup"><span data-stu-id="32c60-115">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="powershell-cmdlets-for-scheduling-scans-to-complete-remediation"></a><span data-ttu-id="32c60-116">修復を完了するためのスキャンをスケジュールするための PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="32c60-116">PowerShell cmdlets for scheduling scans to complete remediation</span></span>

<span data-ttu-id="32c60-117">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32c60-117">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="32c60-118">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="32c60-118">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="powershell-cmdlets-for-scheduling-daily-scans"></a><span data-ttu-id="32c60-119">毎日のスキャンをスケジュールする PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="32c60-119">PowerShell cmdlets for scheduling daily scans</span></span>

<span data-ttu-id="32c60-120">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32c60-120">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="32c60-121">PowerShell を Microsoft Defender ウイルス対策 と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成Microsoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="32c60-121">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>


