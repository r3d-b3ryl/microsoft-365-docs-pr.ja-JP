---
title: Microsoft Defender AV スキャンの結果を確認する
description: アプリ、アプリ、またはアプリを使用Microsoft Endpoint Configuration Manager、Microsoft Intuneスキャンの結果Windows セキュリティする
keywords: スキャン結果、修復、フル スキャン、クイック スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bc7c84e089b08c440512f8a8bf7583f41394f2ca
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007643"
---
# <a name="review-microsoft-defender-antivirus-scan-results"></a><span data-ttu-id="21bac-104">スキャンMicrosoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="21bac-104">Review Microsoft Defender Antivirus scan results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="21bac-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="21bac-105">**Applies to:**</span></span>

- [<span data-ttu-id="21bac-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="21bac-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="21bac-107">オンデマンドスキャンMicrosoft Defender ウイルス対策、スケジュールされたスキャンの実行が完了すると、結果が[](run-scan-microsoft-defender-antivirus.md)記録され、結果[](scheduled-catch-up-scans-microsoft-defender-antivirus.md)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="21bac-107">After a Microsoft Defender Antivirus scan completes, whether it is an [on-demand](run-scan-microsoft-defender-antivirus.md) or [scheduled scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md), the results are recorded and you can view the results.</span></span> 


## <a name="use-configuration-manager-to-review-scan-results"></a><span data-ttu-id="21bac-108">Configuration Manager を使用してスキャン結果を確認する</span><span class="sxs-lookup"><span data-stu-id="21bac-108">Use Configuration Manager to review scan results</span></span>

<span data-ttu-id="21bac-109">詳細については[、「ユーザーの状態をEndpoint Protectionする」を参照してください](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="21bac-109">See [How to monitor Endpoint Protection status](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span>

## <a name="use-powershell-cmdlets-to-review-scan-results"></a><span data-ttu-id="21bac-110">PowerShell コマンドレットを使用してスキャン結果を確認する</span><span class="sxs-lookup"><span data-stu-id="21bac-110">Use PowerShell cmdlets to review scan results</span></span>

<span data-ttu-id="21bac-111">次のコマンドレットは、エンドポイント上の各検出を返します。</span><span class="sxs-lookup"><span data-stu-id="21bac-111">The following cmdlet will return each detection on the endpoint.</span></span> <span data-ttu-id="21bac-112">同じ脅威の複数の検出がある場合、各検出は、各検出の時間に基づいて個別に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="21bac-112">If there are multiple detections of the same threat, each detection will be listed separately, based on the time of each detection:</span></span>

```PowerShell
Get-MpThreatDetection
```

:::image type="content" source="../../media/wdav-get-mpthreatdetection.png" alt-text="PowerShell コマンドレットと出力のスクリーンショット":::

<span data-ttu-id="21bac-114">特定の `-ThreatID` 脅威に対する検出のみを表示する出力を制限する場合に指定できます。</span><span class="sxs-lookup"><span data-stu-id="21bac-114">You can specify `-ThreatID` to limit the output to only show the detections for a specific threat.</span></span>

<span data-ttu-id="21bac-115">脅威検出を一覧表示するが、同じ脅威の検出を 1 つのアイテムに結合する場合は、次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="21bac-115">If you want to list threat detections, but combine detections of the same threat into a single item, you can use the following cmdlet:</span></span>

```PowerShell
Get-MpThreat
```

:::image type="content" source="../../media/wdav-get-mpthreat.png" alt-text="PowerShell コード":::

<span data-ttu-id="21bac-117">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="21bac-117">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-review-scan-results"></a><span data-ttu-id="21bac-118">スキャンWindows確認するには、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="21bac-118">Use Windows Management Instruction (WMI) to review scan results</span></span>

<span data-ttu-id="21bac-119">クラスと [**クラス** の Get **メソッド** MSFT_MpThreat使用MSFT_MpThreatDetection](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)します。</span><span class="sxs-lookup"><span data-stu-id="21bac-119">Use the [**Get** method of the **MSFT_MpThreat** and **MSFT_MpThreatDetection**](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) classes.</span></span>


## <a name="related-articles"></a><span data-ttu-id="21bac-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="21bac-120">Related articles</span></span>

- [<span data-ttu-id="21bac-121">スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="21bac-121">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="21bac-122">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="21bac-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)