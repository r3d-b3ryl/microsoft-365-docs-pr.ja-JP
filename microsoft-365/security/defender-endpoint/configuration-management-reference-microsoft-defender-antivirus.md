---
title: ビジネスWindows Defender管理する
description: グループ ポリシー、Configuration Manager、PowerShell、WMI、Intune、およびコマンド ラインを使用して Microsoft Defender AV を管理する方法について説明します。
keywords: グループ ポリシー、gpo、config manager、sccm、scep、powershell、wmi、intune、Defender、ウイルス対策、マルウェア対策、セキュリティ、保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2265f3680e425ade062d444685fbd8873eaa02ca
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274978"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="d94ff-104">ビジネスMicrosoft Defender ウイルス対策管理する</span><span class="sxs-lookup"><span data-stu-id="d94ff-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d94ff-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d94ff-105">**Applies to:**</span></span>

- [<span data-ttu-id="d94ff-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d94ff-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d94ff-107">次のツールを使用してMicrosoft Defender ウイルス対策を管理および構成できます。</span><span class="sxs-lookup"><span data-stu-id="d94ff-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="d94ff-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (現在は一部Microsoft エンドポイント マネージャー)</span><span class="sxs-lookup"><span data-stu-id="d94ff-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="d94ff-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (現在は一部Microsoft エンドポイント マネージャー)</span><span class="sxs-lookup"><span data-stu-id="d94ff-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="d94ff-110">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d94ff-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d94ff-111">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d94ff-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d94ff-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="d94ff-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="d94ff-113">[Microsoft Malware Protection コマンド ライン ユーティリティ](./command-line-arguments-microsoft-defender-antivirus.md)(このユーティリティとmpcmdrun.exeされます。 </span><span class="sxs-lookup"><span data-stu-id="d94ff-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="d94ff-114">次の記事では、これらのツールを使用してこれらのツールを管理および構成するための詳細な情報、リンク、およびリソースMicrosoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="d94ff-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="d94ff-115">記事</span><span class="sxs-lookup"><span data-stu-id="d94ff-115">Article</span></span> | <span data-ttu-id="d94ff-116">説明</span><span class="sxs-lookup"><span data-stu-id="d94ff-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="d94ff-117">ユーザー Microsoft Defender ウイルス対策とMicrosoft Intune管理Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d94ff-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="d94ff-118">Intune と Configuration Manager を使用して組織の展開、管理、レポート、および構成に関するMicrosoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="d94ff-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="d94ff-119">グループ Microsoft Defender ウイルス対策設定を使用して管理する</span><span class="sxs-lookup"><span data-stu-id="d94ff-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="d94ff-120">ADMX テンプレートにあるすべてのグループ ポリシー設定の一覧</span><span class="sxs-lookup"><span data-stu-id="d94ff-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="d94ff-121">PowerShell コマンドレットMicrosoft Defender ウイルス対策の管理</span><span class="sxs-lookup"><span data-stu-id="d94ff-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="d94ff-122">PowerShell コマンドレットを使用して、すべてのコマンドレットMicrosoft Defender ウイルス対策許可されたパラメーターのドキュメントへのリンクを管理する手順</span><span class="sxs-lookup"><span data-stu-id="d94ff-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="d94ff-123">管理Microsoft Defender ウイルス対策 (WMI) Windowsを使用して管理する</span><span class="sxs-lookup"><span data-stu-id="d94ff-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="d94ff-124">WMI を使用してドキュメントを管理Microsoft Defender ウイルス対策、WMIv2 API のドキュメントへのリンク (すべてのクラス、メソッド、およびプロパティを含む)</span><span class="sxs-lookup"><span data-stu-id="d94ff-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="d94ff-125">コマンド ライン Microsoft Defender ウイルス対策ツールmpcmdrun.exeを管理する</span><span class="sxs-lookup"><span data-stu-id="d94ff-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="d94ff-126">専用のコマンド ライン ツールを使用してコマンド ライン ツールを管理および使用するMicrosoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="d94ff-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |