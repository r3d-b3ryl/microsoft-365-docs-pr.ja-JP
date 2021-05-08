---
title: スキャンの除外をMicrosoft Defender ウイルス対策する
description: ファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを、ユーザーがスキャンMicrosoft Defender ウイルス対策。 PowerShell を使用して除外を検証します。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275122"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="83588-104">スキャンの除外を構成およびMicrosoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="83588-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="83588-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="83588-105">**Applies to:**</span></span>

- [<span data-ttu-id="83588-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="83588-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="83588-107">特定のファイル、フォルダー、プロセス、およびプロセスで開いたファイルを、特定のスキャンからMicrosoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="83588-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="83588-108">このような除外は、スケジュール[されたスキャン、](scheduled-catch-up-scans-microsoft-defender-antivirus.md)[オンデマンド](run-scan-microsoft-defender-antivirus.md)スキャン、および常時オンのリアルタイム保護と[監視に適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="83588-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="83588-109">プロセスで開いたファイルの除外は、リアルタイム保護にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="83588-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="83588-110">除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="83588-110">Configure and validate exclusions</span></span>

<span data-ttu-id="83588-111">除外を構成および検証するには、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83588-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="83588-112">[ファイル名、拡張子、およびフォルダーの場所に基づいて除外を構成および検証します](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="83588-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="83588-113">ファイル拡張子、ファイルMicrosoft Defender ウイルス対策場所に基づいて、ファイルをスキャンから除外できます。</span><span class="sxs-lookup"><span data-stu-id="83588-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="83588-114">[プロセスによって開いたファイルの除外を構成および検証します](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="83588-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="83588-115">特定のプロセスで開いたスキャンからファイルを除外できます。</span><span class="sxs-lookup"><span data-stu-id="83588-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="83588-116">除外を定義するための推奨事項</span><span class="sxs-lookup"><span data-stu-id="83588-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83588-117">Microsoft Defender ウイルス対策には、既知のオペレーティング システムの動作や一般的な管理ファイル (エンタープライズ管理、データベース管理、その他のエンタープライズ シナリオや状況で使用されるファイルなど) に基づく多くの自動除外が含まれます。</span><span class="sxs-lookup"><span data-stu-id="83588-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="83588-118">除外を定義すると、ユーザーが提供する保護がMicrosoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="83588-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="83588-119">除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83588-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="83588-120">除外を定義する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="83588-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="83588-121">除外は技術的には保護のギャップです。</span><span class="sxs-lookup"><span data-stu-id="83588-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="83588-122">除外を定義する場合は、常に軽減策を検討してください。</span><span class="sxs-lookup"><span data-stu-id="83588-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="83588-123">その他の軽減策は、除外された場所に適切なアクセス制御リスト (ACL)、監査ポリシー、最新のソフトウェアなどによって処理されるのを確認するのと同じほど簡単です。</span><span class="sxs-lookup"><span data-stu-id="83588-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="83588-124">除外を定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="83588-124">Review the exclusions periodically.</span></span> <span data-ttu-id="83588-125">レビュー プロセスの一環として軽減策を再確認し、再適用します。</span><span class="sxs-lookup"><span data-stu-id="83588-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="83588-126">予防的な除外を定義しないようにするのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="83588-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="83588-127">たとえば、将来問題になる可能性があるからといって、何かを除外しない。</span><span class="sxs-lookup"><span data-stu-id="83588-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="83588-128">除外は、除外が軽減する可能性のあるパフォーマンスやアプリケーションの互換性に関連する問題など、特定の問題にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="83588-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="83588-129">除外リストの変更を監査します。</span><span class="sxs-lookup"><span data-stu-id="83588-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="83588-130">セキュリティ管理者は、特定の除外が追加された理由に関する十分なコンテキストを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83588-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="83588-131">特定のパスが除外された理由について、特定の理由で回答を提供できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83588-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="83588-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="83588-132">Related articles</span></span>

- [<span data-ttu-id="83588-133">Microsoft Defender ウイルス対策の除外Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="83588-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83588-134">除外を定義する際に避ける必要のある一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="83588-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
