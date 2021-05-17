---
title: Microsoft Defender ウイルス対策機能を構成する
description: Intune、Microsoft Defender ウイルス対策、グループ ポリシー Microsoft Endpoint Configuration Manager PowerShell を使用して、これらの機能を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御者、構成、Microsoft Endpoint Configuration Manager、SCCM、Intune、MDM、モバイル デバイス管理、GP、グループ ポリシー、PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275110"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="cdce0-104">Microsoft Defender ウイルス対策機能を構成する</span><span class="sxs-lookup"><span data-stu-id="cdce0-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cdce0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cdce0-105">**Applies to:**</span></span>

- [<span data-ttu-id="cdce0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cdce0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cdce0-107">次に示すMicrosoft Defender ウイルス対策ツールを使用して、構成を構成できます。</span><span class="sxs-lookup"><span data-stu-id="cdce0-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="cdce0-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cdce0-108">Microsoft Intune</span></span>
- <span data-ttu-id="cdce0-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cdce0-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="cdce0-110">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="cdce0-110">Group Policy</span></span>
- <span data-ttu-id="cdce0-111">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="cdce0-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="cdce0-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="cdce0-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="cdce0-113">次の広範なカテゴリの機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="cdce0-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="cdce0-114">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="cdce0-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="cdce0-115">行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="cdce0-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="cdce0-116">エンド ユーザーが個々のエンドポイントでクライアントとやり取りする方法</span><span class="sxs-lookup"><span data-stu-id="cdce0-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="cdce0-117">次の記事では、タスクの構成時に主要なタスクを実行するMicrosoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="cdce0-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="cdce0-118">各記事には、該当する構成ツール (またはツール) の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdce0-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="cdce0-119">記事</span><span class="sxs-lookup"><span data-stu-id="cdce0-119">Article</span></span>  |<span data-ttu-id="cdce0-120">説明</span><span class="sxs-lookup"><span data-stu-id="cdce0-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="cdce0-121">Microsoft クラウド提供のセキュリティ保護Microsoft Defender ウイルス対策活用する</span><span class="sxs-lookup"><span data-stu-id="cdce0-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="cdce0-122">高度で高速で堅牢なウイルス対策の検出には、クラウドによる保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdce0-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="cdce0-123">行動、ヒューリスティック、リアルタイム保護を構成する</span><span class="sxs-lookup"><span data-stu-id="cdce0-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="cdce0-124">動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護を有効にする。</span><span class="sxs-lookup"><span data-stu-id="cdce0-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="cdce0-125">ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="cdce0-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="cdce0-126">組織内のエンド ユーザーがユーザーと対話する方法、Microsoft Defender ウイルス対策通知、および設定を上書きできるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="cdce0-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="cdce0-127">また、各ツールの概要 [と](configuration-management-reference-microsoft-defender-antivirus.md) 詳細なヘルプへのリンクについては、「管理および構成ツールのリファレンス トピック」トピックを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="cdce0-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>