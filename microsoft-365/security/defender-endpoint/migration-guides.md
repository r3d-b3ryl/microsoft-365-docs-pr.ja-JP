---
title: Microsoft Defender for Endpoint への切り替えに関する移行ガイド
description: Microsoft Defender for Endpoint に対して、セキュリティ以外Microsoft 365 Defender ソリューションから切り替える方法について説明します。
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
ms.date: 06/14/2021
ms.technology: mde
ms.openlocfilehash: 4d10de35358d528f004ee11e931fc6f41ce20482
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930501"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint-and-microsoft-defender-antivirus"></a><span data-ttu-id="7fb97-103">エンドポイントとエンドポイントの Microsoft Defender に切り替Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="7fb97-103">Make the switch to Microsoft Defender for Endpoint and Microsoft Defender Antivirus</span></span>

<span data-ttu-id="7fb97-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7fb97-104">**Applies to:**</span></span>
- [<span data-ttu-id="7fb97-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7fb97-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7fb97-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fb97-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7fb97-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7fb97-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7fb97-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7fb97-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="7fb97-109">移行ガイド</span><span class="sxs-lookup"><span data-stu-id="7fb97-109">Migration guides</span></span>

<span data-ttu-id="7fb97-110">サポートされていない Defender ソリューションから Microsoft Defender for Endpoint への切り替Microsoft 365検討している場合は、Microsoft Defender ウイルス対策の移行ガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb97-110">If you're considering switching from a non-Microsoft 365 Defender solution to Microsoft Defender for Endpoint with Microsoft Defender Antivirus, check out our migration guidance.</span></span> <span data-ttu-id="7fb97-111">展開プロセスの場所を最も適切に表すシナリオを選択し、ガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fb97-111">Select the scenario that best represents where you are in your deployment process, and see the guidance.</span></span>

|<span data-ttu-id="7fb97-112">シナリオ</span><span class="sxs-lookup"><span data-stu-id="7fb97-112">Scenario</span></span> |<span data-ttu-id="7fb97-113">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="7fb97-113">Guidance</span></span> |
|:--|:--|
|<span data-ttu-id="7fb97-114">エンドポイント保護ソリューションはまだありませんが、Microsoft Defender for Endpoint の動作について詳& Microsoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="7fb97-114">You do not have an endpoint protection solution yet, and you want to know more about how Microsoft Defender for Endpoint & Microsoft Defender Antivirus work.</span></span>  |[<span data-ttu-id="7fb97-115">Microsoft Defender for Endpoint 評価ラボ</span><span class="sxs-lookup"><span data-stu-id="7fb97-115">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
|<span data-ttu-id="7fb97-116">Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策し、すべての設定と構成を行う上で役立つ情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="7fb97-116">You have Microsoft Defender for Endpoint & Microsoft Defender Antivirus and need some help getting everything set up and configured.</span></span>  |[<span data-ttu-id="7fb97-117">Microsoft Defender for Endpoint 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="7fb97-117">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
|<span data-ttu-id="7fb97-118">Microsoft 以外のエンドポイント保護ソリューションから Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策 に移行する予定です。</span><span class="sxs-lookup"><span data-stu-id="7fb97-118">You're planning to migrate from a non-Microsoft endpoint protection solution to Microsoft Defender for Endpoint & Microsoft Defender Antivirus.</span></span> |[<span data-ttu-id="7fb97-119">エンドポイント用 Microsoft Defender への切り替え</span><span class="sxs-lookup"><span data-stu-id="7fb97-119">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
|<span data-ttu-id="7fb97-120">Microsoft Defender for Endpoint & Microsoft Defender ウイルス対策 に移行し、追加機能の構成やセキュリティ設定の微調整など、次の手順に関するヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="7fb97-120">You've migrated to Microsoft Defender for Endpoint & Microsoft Defender Antivirus, and you need help with next steps, such as configuring additional features or fine-tuning your security settings.</span></span> | [<span data-ttu-id="7fb97-121">移行後の Microsoft Defender for Endpoint の管理</span><span class="sxs-lookup"><span data-stu-id="7fb97-121">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="7fb97-122">フィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="7fb97-122">Do you have feedback for us?</span></span>

<span data-ttu-id="7fb97-123">ご意見をお知らせください。</span><span class="sxs-lookup"><span data-stu-id="7fb97-123">Let us know what you think!</span></span> <span data-ttu-id="7fb97-124">ページの下部にフィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="7fb97-124">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="7fb97-125">引き続き改善し、移行ガイダンスに追加する場合は、フィードバックを考慮します。</span><span class="sxs-lookup"><span data-stu-id="7fb97-125">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fb97-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fb97-126">See also</span></span>

- [<span data-ttu-id="7fb97-127">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7fb97-127">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="7fb97-128">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7fb97-128">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="7fb97-129">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fb97-129">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
