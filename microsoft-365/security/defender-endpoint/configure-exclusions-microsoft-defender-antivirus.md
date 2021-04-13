---
title: Microsoft Defender AV スキャンの除外を設定する
description: Microsoft Defender AV によってスキャンされるファイル (指定されたプロセスによって変更されたファイルを含む) とフォルダーを除外できます。 PowerShell を使用して除外を検証します。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691504"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="94b22-104">Microsoft Defender ウイルス対策スキャンの除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="94b22-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="94b22-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="94b22-105">**Applies to:**</span></span>

- [<span data-ttu-id="94b22-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="94b22-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="94b22-107">Microsoft Defender ウイルス対策スキャンから、特定のファイル、フォルダー、プロセス、およびプロセスで開いたファイルを除外できます。</span><span class="sxs-lookup"><span data-stu-id="94b22-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="94b22-108">このような除外は、スケジュール[されたスキャン、](scheduled-catch-up-scans-microsoft-defender-antivirus.md)[オンデマンド](run-scan-microsoft-defender-antivirus.md)スキャン、および常時オンのリアルタイム保護と[監視に適用されます](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="94b22-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="94b22-109">プロセスで開いたファイルの除外は、リアルタイム保護にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94b22-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="94b22-110">除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="94b22-110">Configure and validate exclusions</span></span>

<span data-ttu-id="94b22-111">除外を構成および検証するには、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94b22-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="94b22-112">[ファイル名、拡張子、およびフォルダーの場所に基づいて除外を構成および検証します](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="94b22-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="94b22-113">これにより、ファイル拡張子、ファイル名、または場所に基づいて、Microsoft Defender ウイルス対策スキャンからファイルを除外できます。</span><span class="sxs-lookup"><span data-stu-id="94b22-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="94b22-114">[プロセスによって開いたファイルの除外を構成および検証します](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="94b22-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="94b22-115">これにより、特定のプロセスで開いたスキャンからファイルを除外できます。</span><span class="sxs-lookup"><span data-stu-id="94b22-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="94b22-116">除外を定義するための推奨事項</span><span class="sxs-lookup"><span data-stu-id="94b22-116">Recommendations for defining exclusions</span></span>

<span data-ttu-id="94b22-117">除外を定義すると、Microsoft Defender ウイルス対策によって提供される保護が低下します。</span><span class="sxs-lookup"><span data-stu-id="94b22-117">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="94b22-118">除外の実装に関連付けられているリスクは常に評価する必要があります。悪意がないと確信しているファイルのみを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94b22-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="94b22-119">除外を定義する際に注意する必要がある推奨事項の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="94b22-119">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="94b22-120">除外は技術的には保護のギャップです。除外を定義する場合は、常に追加の軽減策を検討してください。</span><span class="sxs-lookup"><span data-stu-id="94b22-120">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="94b22-121">追加の軽減策は、除外された場所に適切なアクセス制御リスト (ACL)、監査ポリシー、最新のソフトウェアなどによって処理されるのを確認するのと同じほど簡単です。</span><span class="sxs-lookup"><span data-stu-id="94b22-121">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="94b22-122">除外を定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="94b22-122">Review the exclusions periodically.</span></span> <span data-ttu-id="94b22-123">レビュー プロセスの一環として軽減策を再確認し、再適用します。</span><span class="sxs-lookup"><span data-stu-id="94b22-123">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="94b22-124">予防的な除外を定義しないようにするのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="94b22-124">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="94b22-125">たとえば、将来問題になる可能性があるからといって、何かを除外しない。</span><span class="sxs-lookup"><span data-stu-id="94b22-125">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="94b22-126">除外は、特定の問題 (主にパフォーマンスに関する問題)、または除外が軽減できるアプリケーションの互換性に関する場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="94b22-126">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="94b22-127">除外リストの変更を監査します。</span><span class="sxs-lookup"><span data-stu-id="94b22-127">Audit the exclusion list changes.</span></span> <span data-ttu-id="94b22-128">セキュリティ管理者は、特定の除外が追加された理由に関する十分なコンテキストを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94b22-128">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="94b22-129">特定のパスが除外された理由について、特定の理由で回答を提供できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94b22-129">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="94b22-130">関連記事</span><span class="sxs-lookup"><span data-stu-id="94b22-130">Related articles</span></span>

- [<span data-ttu-id="94b22-131">Windows Server 2016 での Microsoft Defender ウイルス対策の除外</span><span class="sxs-lookup"><span data-stu-id="94b22-131">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="94b22-132">除外を定義するときに回避する一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="94b22-132">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)