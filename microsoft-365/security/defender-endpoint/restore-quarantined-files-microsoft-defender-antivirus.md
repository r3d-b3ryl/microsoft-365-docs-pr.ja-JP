---
title: Microsoft Defender AV で検疫済みファイルを復元する
description: Microsoft Defender AV によって検疫されたファイルとフォルダーを復元できます。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275386"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="14218-103">Microsoft Defender AV で検疫済みファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="14218-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="14218-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="14218-104">**Applies to:**</span></span>

- [<span data-ttu-id="14218-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="14218-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="14218-106">デバイスMicrosoft Defender ウイルス対策脅威を検出して修復するように構成されている場合は、疑わしいMicrosoft Defender ウイルス対策を検疫します。</span><span class="sxs-lookup"><span data-stu-id="14218-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="14218-107">検疫済みファイルが脅威ではないと思う場合は、復元できます。</span><span class="sxs-lookup"><span data-stu-id="14218-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="14218-108">[ファイル **Windows セキュリティ] を開きます**。</span><span class="sxs-lookup"><span data-stu-id="14218-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="14218-109">[ **ウイルス対策&保護] を選択し、[** 保護の履歴] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14218-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="14218-110">最近使用したアイテムの一覧で、[検疫済みアイテム **] をフィルター処理します**。</span><span class="sxs-lookup"><span data-stu-id="14218-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="14218-111">保持するアイテムを選択し、復元などのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="14218-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="14218-112">検疫からファイルを復元するには、コマンド プロンプトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="14218-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="14218-113">「検疫 [からファイルを復元する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)。</span><span class="sxs-lookup"><span data-stu-id="14218-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="14218-114">関連記事</span><span class="sxs-lookup"><span data-stu-id="14218-114">Related articles</span></span>

- [<span data-ttu-id="14218-115">スキャンの修復を構成する</span><span class="sxs-lookup"><span data-stu-id="14218-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="14218-116">スキャン結果の確認</span><span class="sxs-lookup"><span data-stu-id="14218-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="14218-117">ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="14218-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="14218-118">プロセスによって開いたファイルの除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="14218-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="14218-119">サーバー Microsoft Defender ウイルス対策の除外をWindowsする</span><span class="sxs-lookup"><span data-stu-id="14218-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)