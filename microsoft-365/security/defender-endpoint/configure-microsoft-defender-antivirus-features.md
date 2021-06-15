---
title: Microsoft Defender ウイルス対策機能を構成する
description: Intune、Microsoft Defender ウイルス対策、グループ ポリシー Microsoft Endpoint Configuration Manager PowerShell を使用して、これらの機能を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御者、構成、Microsoft Endpoint Configuration Manager、SCCM、Intune、MDM、モバイル デバイス管理、GP、グループ ポリシー、PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7fa5959ede9f0c71c75cefafc0fcb0d4376a1a4f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925397"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="32867-104">Microsoft Defender ウイルス対策機能を構成する</span><span class="sxs-lookup"><span data-stu-id="32867-104">Configure Microsoft Defender Antivirus features</span></span>


<span data-ttu-id="32867-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="32867-105">**Applies to:**</span></span>

- [<span data-ttu-id="32867-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32867-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="32867-107">次のようなMicrosoft Defender ウイルス対策ツールを使用して、構成を構成できます。</span><span class="sxs-lookup"><span data-stu-id="32867-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="32867-108">Microsoft エンドポイント マネージャー (これには、Microsoft IntuneとMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="32867-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="32867-109">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="32867-109">Group Policy</span></span>
- <span data-ttu-id="32867-110">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="32867-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="32867-111">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="32867-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="32867-112">次の広範なカテゴリの機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="32867-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="32867-113">クラウドによる保護。</span><span class="sxs-lookup"><span data-stu-id="32867-113">Cloud-delivered protection.</span></span> <span data-ttu-id="32867-114">[「Cloud-delivered protection and Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="32867-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="32867-115">行動、ヒューリスティック、機械学習ベースの保護を含む、常時オンのリアルタイム保護。</span><span class="sxs-lookup"><span data-stu-id="32867-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="32867-116">「 [動作、ヒューリスティック、およびリアルタイム保護を構成する」を参照してください](configure-protection-features-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="32867-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="32867-117">エンド ユーザーが個々のエンドポイントでクライアントとやり取りする方法。</span><span class="sxs-lookup"><span data-stu-id="32867-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="32867-118">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32867-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="32867-119">ユーザーがユーザー インターフェイスを表示または操作Microsoft Defender ウイルス対策防止する</span><span class="sxs-lookup"><span data-stu-id="32867-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="32867-120">ユーザーがポリシー設定をローカルで変更Microsoft Defender ウイルス対策または許可する</span><span class="sxs-lookup"><span data-stu-id="32867-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="32867-121">管理 [ツールと構成ツールのリファレンス トピックを確認します](configuration-management-reference-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="32867-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>
