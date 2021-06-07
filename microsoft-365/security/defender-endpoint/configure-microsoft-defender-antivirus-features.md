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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789029"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="30906-104">Microsoft Defender ウイルス対策機能を構成する</span><span class="sxs-lookup"><span data-stu-id="30906-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="30906-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="30906-105">**Applies to:**</span></span>

- [<span data-ttu-id="30906-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="30906-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="30906-107">次のようなMicrosoft Defender ウイルス対策ツールを使用して、構成を構成できます。</span><span class="sxs-lookup"><span data-stu-id="30906-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="30906-108">Microsoft エンドポイント マネージャー (これには、Microsoft IntuneとMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="30906-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="30906-109">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="30906-109">Group Policy</span></span>
- <span data-ttu-id="30906-110">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="30906-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="30906-111">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="30906-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="30906-112">次の広範なカテゴリの機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="30906-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="30906-113">クラウドによる保護。</span><span class="sxs-lookup"><span data-stu-id="30906-113">Cloud-delivered protection.</span></span> <span data-ttu-id="30906-114">[「Cloud-delivered protection and Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="30906-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="30906-115">行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護。</span><span class="sxs-lookup"><span data-stu-id="30906-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="30906-116">「 [動作、ヒューリスティック、およびリアルタイム保護を構成する」を参照してください](configure-protection-features-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="30906-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="30906-117">エンド ユーザーが個々のエンドポイントでクライアントとやり取りする方法。</span><span class="sxs-lookup"><span data-stu-id="30906-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="30906-118">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="30906-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="30906-119">ユーザーがユーザー インターフェイスを表示または操作Microsoft Defender ウイルス対策防止する</span><span class="sxs-lookup"><span data-stu-id="30906-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="30906-120">ユーザーがポリシー設定をローカルで変更Microsoft Defender ウイルス対策または許可する</span><span class="sxs-lookup"><span data-stu-id="30906-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="30906-121">管理 [ツールと構成ツールのリファレンス トピックを確認します](configuration-management-reference-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="30906-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>