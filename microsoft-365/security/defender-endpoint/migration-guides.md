---
title: Microsoft Defender for Endpoint への切り替えに関する移行ガイド
description: Microsoft 以外の脅威保護ソリューションから Microsoft Defender for Endpoint への切り替え方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.custom: migrationguides
ms.reviewer: chriggs, depicker, yongrhee
f1.keywords: NOCSH
ms.date: 09/24/2020
ms.technology: mde
ms.openlocfilehash: 0f9508038dd49e6c2d14d8e33a4fd40dfdfe83cb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198656"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="86527-103">エンドポイントと Microsoft Defender ウイルス対策の Microsoft Defender への切り替え</span><span class="sxs-lookup"><span data-stu-id="86527-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86527-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="86527-104">**Applies to:**</span></span>
- [<span data-ttu-id="86527-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="86527-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86527-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86527-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="86527-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="86527-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86527-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="86527-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="86527-109">移行ガイド</span><span class="sxs-lookup"><span data-stu-id="86527-109">Migration guides</span></span>

<span data-ttu-id="86527-110">Microsoft 以外の脅威保護ソリューションから Microsoft Defender ウイルス対策を使用した Microsoft Defender for Endpoint への切り替えをお考えの場合は、移行のガイダンスをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86527-110">If you're considering switching from a non-Microsoft threat protection solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="86527-111">展開プロセスの場所を最も適切に表すシナリオを選択し、ガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86527-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="86527-112">シナリオ</span><span class="sxs-lookup"><span data-stu-id="86527-112">Scenario</span></span> |<span data-ttu-id="86527-113">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="86527-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="86527-114">エンドポイント保護ソリューションはまだありませんが、Microsoft Defender for Endpoint &動作の詳細を知りたい場合。</span><span class="sxs-lookup"><span data-stu-id="86527-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="86527-115">Microsoft Defender for Endpoint 評価ラボ</span><span class="sxs-lookup"><span data-stu-id="86527-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="86527-116">Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策を使用し、すべてのセットアップと構成を行う上で役立つ情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="86527-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="86527-117">Microsoft Defender for Endpoint 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="86527-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="86527-118">McAfee Endpoint Security (McAfee) から Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策に移行する予定です。</span><span class="sxs-lookup"><span data-stu-id="86527-118">You're planning to migrate from McAfee Endpoint Security (McAfee) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="86527-119">McAfee から Microsoft Defender for Endpoint に切り替える</span><span class="sxs-lookup"><span data-stu-id="86527-119">Switch from McAfee to Microsoft Defender for Endpoint</span></span>](mcafee-to-microsoft-defender-migration.md) |
|<span data-ttu-id="86527-120">シマンテック エンドポイント保護 (Symantec) から Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策に移行する予定です。</span><span class="sxs-lookup"><span data-stu-id="86527-120">You're planning to migrate from Symantec Endpoint Protection (Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="86527-121">シマンテックから Microsoft Defender for Endpoint に切り替える</span><span class="sxs-lookup"><span data-stu-id="86527-121">Switch from Symantec to Microsoft Defender for Endpoint</span></span>](symantec-to-microsoft-defender-atp-migration.md) |
|<span data-ttu-id="86527-122">Microsoft 以外のエンドポイント保護ソリューション (McAfee または Symantec 以外) から Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策に移行する予定です。</span><span class="sxs-lookup"><span data-stu-id="86527-122">You're planning to migrate from a non-Microsoft endpoint protection solution (other than McAfee or Symantec) to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="86527-123">エンドポイント用 Microsoft Defender への切り替え</span><span class="sxs-lookup"><span data-stu-id="86527-123">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="86527-124">Microsoft Defender for Endpoint & Microsoft Defender Antivirus に移行し、追加機能の構成やセキュリティ設定の微調整など、次の手順に関するヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="86527-124">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="86527-125">移行後の Microsoft Defender for Endpoint の管理</span><span class="sxs-lookup"><span data-stu-id="86527-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="got-feedback"></a><span data-ttu-id="86527-126">フィードバックを受け取った場合</span><span class="sxs-lookup"><span data-stu-id="86527-126">Got feedback?</span></span>

<span data-ttu-id="86527-127">ご意見をお知らせください。</span><span class="sxs-lookup"><span data-stu-id="86527-127">Let us know what you think!</span></span> <span data-ttu-id="86527-128">ページの下部にフィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="86527-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="86527-129">引き続き改善し、移行ガイダンスに追加する場合は、フィードバックを考慮します。</span><span class="sxs-lookup"><span data-stu-id="86527-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="86527-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="86527-130">See also</span></span>

- [<span data-ttu-id="86527-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="86527-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
- [<span data-ttu-id="86527-132">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="86527-132">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="86527-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86527-133">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection?) 