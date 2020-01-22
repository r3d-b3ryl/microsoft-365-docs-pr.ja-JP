---
title: Microsoft の脅威保護で、空軍の誤検知または誤検知を報告する方法
description: Microsoft の脅威保護で、何らかの問題があるか、またはエアで誤って検出されましたか? 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
keywords: 自動化、調査、警告、トリガー、アクション、修復、誤検知、false 負
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260195"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="e50b8-105">自動調査および応答機能の誤検知/ネガを報告する方法</span><span class="sxs-lookup"><span data-stu-id="e50b8-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="e50b8-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e50b8-106">**Applies to:**</span></span>
- <span data-ttu-id="e50b8-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e50b8-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e50b8-108">Microsoft の脅威保護ミスの自動化された[調査と応答機能](mtp-autoir.md)を、誤って検出しましたか?</span><span class="sxs-lookup"><span data-stu-id="e50b8-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="e50b8-109">Microsoft に報告するか、通知を調整することができます (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="e50b8-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="e50b8-110">次の表を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="e50b8-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="e50b8-111">アイテム</span><span class="sxs-lookup"><span data-stu-id="e50b8-111">Item</span></span>  |<span data-ttu-id="e50b8-112">検出者</span><span class="sxs-lookup"><span data-stu-id="e50b8-112">Detected by</span></span>  |<span data-ttu-id="e50b8-113">レポート方法</span><span class="sxs-lookup"><span data-stu-id="e50b8-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e50b8-114">電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="e50b8-114">Email message</span></span> <br/><span data-ttu-id="e50b8-115">電子メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="e50b8-115">Email attachment</span></span> <br/><span data-ttu-id="e50b8-116">電子メールメッセージまたは Office ファイルの URL</span><span class="sxs-lookup"><span data-stu-id="e50b8-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="e50b8-117">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e50b8-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="e50b8-118">迷惑メールの疑いのあるスパム、フィッシング、Url、およびファイルを Office 365 スキャン用に Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="e50b8-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="e50b8-119">デバイス上のファイルまたはアプリ</span><span class="sxs-lookup"><span data-stu-id="e50b8-119">File or app on a device</span></span>    |[<span data-ttu-id="e50b8-120">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e50b8-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="e50b8-121">マルウェア分析のために Microsoft にファイルを提出する</span><span class="sxs-lookup"><span data-stu-id="e50b8-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="e50b8-122">正当な使用によってトリガーされるアラート</span><span class="sxs-lookup"><span data-stu-id="e50b8-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="e50b8-123">不正確な警告</span><span class="sxs-lookup"><span data-stu-id="e50b8-123">Inaccurate alert</span></span>    |[<span data-ttu-id="e50b8-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e50b8-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="e50b8-125">または</span><span class="sxs-lookup"><span data-stu-id="e50b8-125">or</span></span> <br/>[<span data-ttu-id="e50b8-126">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="e50b8-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="e50b8-127">Cloud App Security ポータルで通知を管理する</span><span class="sxs-lookup"><span data-stu-id="e50b8-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="e50b8-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e50b8-128">Next steps</span></span>

- [<span data-ttu-id="e50b8-129">自動調査と対応に関連するアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="e50b8-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="e50b8-130">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="e50b8-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="e50b8-131">Microsoft Threat Protection の高度な捜索により、脅威を積極的に捜索する</span><span class="sxs-lookup"><span data-stu-id="e50b8-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
