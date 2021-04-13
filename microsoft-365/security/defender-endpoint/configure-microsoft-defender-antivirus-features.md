---
title: Microsoft Defender ウイルス対策機能の構成
description: Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell を使用して Microsoft Defender ウイルス対策機能を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、構成マネージャー、Microsoft Endpoint Configuration Manager、SCCM、Intune、MDM、モバイル デバイス管理、GP、グループ ポリシー、PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3dcf0ab24541a8837fbab91049fed0157b7f1fc9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690821"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="508f1-104">Microsoft Defender ウイルス対策機能の構成</span><span class="sxs-lookup"><span data-stu-id="508f1-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="508f1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="508f1-105">**Applies to:**</span></span>

- [<span data-ttu-id="508f1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="508f1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="508f1-107">Microsoft Defender ウイルス対策は、次のツールを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="508f1-107">You can configure Microsoft Defender Antivirus with a number of tools, including:</span></span>

- <span data-ttu-id="508f1-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="508f1-108">Microsoft Intune</span></span>
- <span data-ttu-id="508f1-109">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="508f1-109">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="508f1-110">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="508f1-110">Group Policy</span></span>
- <span data-ttu-id="508f1-111">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="508f1-111">PowerShell cmdlets</span></span>
- <span data-ttu-id="508f1-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="508f1-112">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="508f1-113">次の広範なカテゴリの機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="508f1-113">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="508f1-114">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="508f1-114">Cloud-delivered protection</span></span>
- <span data-ttu-id="508f1-115">行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="508f1-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection</span></span>
- <span data-ttu-id="508f1-116">エンド ユーザーが個々のエンドポイントでクライアントとやり取りする方法</span><span class="sxs-lookup"><span data-stu-id="508f1-116">How end users interact with the client on individual endpoints</span></span>

<span data-ttu-id="508f1-117">次の記事では、Microsoft Defender ウイルス対策を構成するときに重要なタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="508f1-117">The following articles describe how to perform key tasks when configuring Microsoft Defender Antivirus.</span></span> <span data-ttu-id="508f1-118">各記事には、該当する構成ツール (またはツール) の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="508f1-118">Each article includes instructions for the applicable configuration tool (or tools).</span></span>

|<span data-ttu-id="508f1-119">記事</span><span class="sxs-lookup"><span data-stu-id="508f1-119">Article</span></span>  |<span data-ttu-id="508f1-120">説明</span><span class="sxs-lookup"><span data-stu-id="508f1-120">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="508f1-121">Microsoft クラウド提供の Microsoft Defender ウイルス対策保護を利用する</span><span class="sxs-lookup"><span data-stu-id="508f1-121">Utilize Microsoft cloud-provided Microsoft Defender Antivirus protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)     | <span data-ttu-id="508f1-122">高度で高速で堅牢なウイルス対策の検出には、クラウドによる保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="508f1-122">Use cloud-delivered protection for advanced, fast, robust antivirus detection.</span></span>        |
|[<span data-ttu-id="508f1-123">動作、ヒューリスティック、およびリアルタイムの保護を構成する</span><span class="sxs-lookup"><span data-stu-id="508f1-123">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)     |<span data-ttu-id="508f1-124">動作ベース、ヒューリスティック、リアルタイムのウイルス対策保護を有効にする。</span><span class="sxs-lookup"><span data-stu-id="508f1-124">Enable behavior-based, heuristic, and real-time antivirus protection.</span></span>         |
|[<span data-ttu-id="508f1-125">Microsoft Defender ウイルス対策とのエンド ユーザー操作を構成する</span><span class="sxs-lookup"><span data-stu-id="508f1-125">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="508f1-126">組織内のエンド ユーザーが Microsoft Defender ウイルス対策とやり取りする方法、表示される通知、および設定を上書きできるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="508f1-126">Configure how end users in your organization interact with Microsoft Defender Antivirus, what notifications they see, and whether they can override settings.</span></span> |

> [!TIP]
> <span data-ttu-id="508f1-127">また、各ツールの概要 [と](configuration-management-reference-microsoft-defender-antivirus.md) 詳細なヘルプへのリンクについては、「管理および構成ツールのリファレンス トピック」トピックを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="508f1-127">You can also review the [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md) topic for an overview of each tool and links to further help.</span></span>