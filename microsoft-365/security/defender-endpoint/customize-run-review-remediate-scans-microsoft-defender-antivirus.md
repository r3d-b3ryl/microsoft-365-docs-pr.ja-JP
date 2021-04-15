---
title: スケジュールされたスキャンとオンデマンド スキャンの実行とカスタマイズ
description: ネットワーク全体のエンドポイントで Microsoft Defender ウイルス対策スキャンをカスタマイズして開始します。
keywords: スキャン、スケジュール、カスタマイズ、除外、ファイルの除外、修復、スキャン結果、検疫、脅威の削除、クイック スキャン、フル スキャン、Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 115a8ee56ca5e9768b3aba11c37f8423ef31a67b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765697"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="e8091-104">Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する</span><span class="sxs-lookup"><span data-stu-id="e8091-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e8091-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e8091-105">**Applies to:**</span></span>

- [<span data-ttu-id="e8091-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e8091-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e8091-107">グループ ポリシー、PowerShell、および Windows 管理インストルメンテーション (WMI) を使用して、Microsoft Defender ウイルス対策スキャンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e8091-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="e8091-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e8091-108">In this section</span></span>

<span data-ttu-id="e8091-109">トピック</span><span class="sxs-lookup"><span data-stu-id="e8091-109">Topic</span></span> | <span data-ttu-id="e8091-110">説明</span><span class="sxs-lookup"><span data-stu-id="e8091-110">Description</span></span>
---|---
[<span data-ttu-id="e8091-111">Microsoft Defender ウイルス対策スキャンでファイル、フォルダー、およびプロセスで開いたファイルの除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="e8091-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="e8091-112">ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを、オンデマンド スキャン、スケジュールされたスキャン、および常時オンのリアルタイム保護監視とスキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="e8091-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="e8091-113">Microsoft Defender ウイルス対策スキャン オプションの構成</span><span class="sxs-lookup"><span data-stu-id="e8091-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="e8091-114">Microsoft Defender ウイルス対策を構成して、特定の種類の電子メール ストレージ ファイル、バックアップまたは再解析ポイント、およびアーカイブ ファイル (.zip ファイルなど) をスキャンに含めます。</span><span class="sxs-lookup"><span data-stu-id="e8091-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="e8091-115">ネットワーク ファイルのスキャンを有効にできます</span><span class="sxs-lookup"><span data-stu-id="e8091-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="e8091-116">スキャンの修復を構成する</span><span class="sxs-lookup"><span data-stu-id="e8091-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="e8091-117">脅威を検出した場合の Microsoft Defender ウイルス対策の実行方法と、検疫フォルダーに検疫されたファイルを保持する期間を構成する</span><span class="sxs-lookup"><span data-stu-id="e8091-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="e8091-118">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="e8091-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="e8091-119">定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)</span><span class="sxs-lookup"><span data-stu-id="e8091-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="e8091-120">スキャンの構成と実行</span><span class="sxs-lookup"><span data-stu-id="e8091-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="e8091-121">PowerShell、Windows 管理インストルメンテーション、または Windows セキュリティ アプリを使用してエンドポイントで個別にオンデマンド スキャンを実行および構成する</span><span class="sxs-lookup"><span data-stu-id="e8091-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="e8091-122">スキャン結果の確認</span><span class="sxs-lookup"><span data-stu-id="e8091-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="e8091-123">Microsoft Endpoint Configuration Manager、Microsoft Intune、または Windows セキュリティ アプリを使用してスキャンの結果を確認する</span><span class="sxs-lookup"><span data-stu-id="e8091-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>