---
title: ビジネスWindows Defender管理する
description: グループ ポリシー、Configuration Manager、PowerShell、WMI、Intune、およびコマンド ラインを使用して Microsoft Defender AV を管理する方法について説明します。
keywords: グループ ポリシー、gpo、config manager、sccm、scep、powershell、wmi、intune、Defender、ウイルス対策、マルウェア対策、セキュリティ、保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad3e8d2fb61eb5a2a350d061f926dd7bff8ae109
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691072"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="adcb3-104">ビジネスで Microsoft Defender ウイルス対策を管理する</span><span class="sxs-lookup"><span data-stu-id="adcb3-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="adcb3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="adcb3-105">**Applies to:**</span></span>

- [<span data-ttu-id="adcb3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="adcb3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="adcb3-107">次のツールを使用して、Microsoft Defender ウイルス対策を管理および構成できます。</span><span class="sxs-lookup"><span data-stu-id="adcb3-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="adcb3-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (現在は Microsoft エンドポイント マネージャーの一部)</span><span class="sxs-lookup"><span data-stu-id="adcb3-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="adcb3-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (現在は Microsoft Endpoint Manager の一部)</span><span class="sxs-lookup"><span data-stu-id="adcb3-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="adcb3-110">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="adcb3-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adcb3-111">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="adcb3-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="adcb3-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="adcb3-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="adcb3-113">[Microsoft Malware Protection コマンド ライン ユーティリティ](./command-line-arguments-microsoft-defender-antivirus.md)(このユーティリティとmpcmdrun.exeされます。 </span><span class="sxs-lookup"><span data-stu-id="adcb3-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="adcb3-114">次の記事では、これらのツールを使用して Microsoft Defender Antivirus を管理および構成するための詳細な情報、リンク、およびリソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="adcb3-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="adcb3-115">記事</span><span class="sxs-lookup"><span data-stu-id="adcb3-115">Article</span></span> | <span data-ttu-id="adcb3-116">説明</span><span class="sxs-lookup"><span data-stu-id="adcb3-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="adcb3-117">Microsoft Intune と Microsoft Endpoint Configuration Manager を使用して Microsoft Defender ウイルス対策を管理する</span><span class="sxs-lookup"><span data-stu-id="adcb3-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="adcb3-118">Intune と Configuration Manager を使用した Microsoft Defender ウイルス対策の展開、管理、レポート、構成に関する情報</span><span class="sxs-lookup"><span data-stu-id="adcb3-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="adcb3-119">グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する</span><span class="sxs-lookup"><span data-stu-id="adcb3-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="adcb3-120">ADMX テンプレートにあるすべてのグループ ポリシー設定の一覧</span><span class="sxs-lookup"><span data-stu-id="adcb3-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="adcb3-121">PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を管理する</span><span class="sxs-lookup"><span data-stu-id="adcb3-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="adcb3-122">PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を管理する手順と、すべてのコマンドレットと許可されたパラメーターのドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="adcb3-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="adcb3-123">Windows 管理インストルメンテーション (WMI) を使用して Microsoft Defender ウイルス対策を管理する</span><span class="sxs-lookup"><span data-stu-id="adcb3-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="adcb3-124">WMI を使用して Microsoft Defender ウイルス対策を管理する手順、および WMIv2 API のドキュメントへのリンク (すべてのクラス、メソッド、およびプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="adcb3-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="adcb3-125">コマンド ライン ツールを使用して microsoft Defender ウイルスmpcmdrun.exeを管理する</span><span class="sxs-lookup"><span data-stu-id="adcb3-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="adcb3-126">専用のコマンド ライン ツールを使用して Microsoft Defender ウイルス対策を管理および使用する手順</span><span class="sxs-lookup"><span data-stu-id="adcb3-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |