---
title: Microsoft Defender for Endpoint への切り替えに関する移行ガイド
description: 非セキュリティ ソリューションから Microsoft Defender for Endpoint への切りMicrosoft 365 Defenderする方法について説明します。
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
ms.openlocfilehash: 010cea14bebd4e29822b1826c0ec4577d53baca7
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964863"
---
# <a name="make-the-switch-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f1b7d-103">エンドポイント用 Microsoft Defender への切り替え</span><span class="sxs-lookup"><span data-stu-id="f1b7d-103">Make the switch to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f1b7d-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f1b7d-104">**Applies to:**</span></span>
- [<span data-ttu-id="f1b7d-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1b7d-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1b7d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1b7d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f1b7d-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="f1b7d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1b7d-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="migration-guides"></a><span data-ttu-id="f1b7d-109">移行ガイド</span><span class="sxs-lookup"><span data-stu-id="f1b7d-109">Migration guides</span></span>

<span data-ttu-id="f1b7d-110">Defender for Endpoint への移行を検討している場合は、ヘルプを提供するガイダンスがあります。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-110">If you're considering moving to Defender for Endpoint, we have guidance to help.</span></span> <span data-ttu-id="f1b7d-111">次の表で、シナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-111">In the following table, review the scenarios.</span></span> <span data-ttu-id="f1b7d-112">状況を最も適切に表すシナリオを選択し、推奨されるガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-112">Select the scenario that best represents your situation, and see the recommended guidance.</span></span>

| <span data-ttu-id="f1b7d-113">シナリオ</span><span class="sxs-lookup"><span data-stu-id="f1b7d-113">Scenario</span></span> | <span data-ttu-id="f1b7d-114">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="f1b7d-114">Guidance</span></span> |
|:----|:----|
| <span data-ttu-id="f1b7d-115">エンドポイント保護ソリューションがまだ提供されていないので、Defender for Endpoint について詳しくはお知りください。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-115">You don't have an endpoint protection solution in place yet, and you want to know more about Defender for Endpoint.</span></span> <span data-ttu-id="f1b7d-116">環境で展開する前に、Defender for Endpoint の動作を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-116">You want to see how Defender for Endpoint works before rolling it out in your environment.</span></span>  | [<span data-ttu-id="f1b7d-117">Microsoft Defender for Endpoint 評価ラボ</span><span class="sxs-lookup"><span data-stu-id="f1b7d-117">Microsoft Defender for Endpoint evaluation lab</span></span>](evaluation-lab.md)   |
| <span data-ttu-id="f1b7d-118">Defender for Endpoint が既に存在し、すべての設定と構成に役立つ情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-118">You already have Defender for Endpoint, and you want some help getting everything set up and configured.</span></span>  | [<span data-ttu-id="f1b7d-119">Microsoft Defender for Endpoint 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="f1b7d-119">Microsoft Defender for Endpoint deployment guide</span></span>](deployment-phases.md)  |
| <span data-ttu-id="f1b7d-120">Microsoft 以外のエンドポイント保護ソリューションから Defender for Endpoint に切り替え、Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-120">You're planning to switch from a non-Microsoft endpoint protection solution to Defender for Endpoint and Microsoft Defender Antivirus.</span></span> <span data-ttu-id="f1b7d-121">移行プロセスの概要と切り替え方法を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-121">You want to get an overview of the migration process and how to make the switch.</span></span> |[<span data-ttu-id="f1b7d-122">エンドポイント用 Microsoft Defender への切り替え</span><span class="sxs-lookup"><span data-stu-id="f1b7d-122">Make the switch to Microsoft Defender for Endpoint</span></span>](switch-to-microsoft-defender-migration.md)   |
| <span data-ttu-id="f1b7d-123">Defender for Endpoint に移行またはオンボード済みです。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-123">You've already migrated or onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="f1b7d-124">セキュリティ設定の管理、その他の機能の構成、セキュリティ ポリシーの微調整など、次の手順に関するヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-124">You want some help with next steps, such as managing your security settings, configuring more features, or fine-tuning your security policies.</span></span> | [<span data-ttu-id="f1b7d-125">移行後の Microsoft Defender for Endpoint の管理</span><span class="sxs-lookup"><span data-stu-id="f1b7d-125">Manage Microsoft Defender for Endpoint, post-migration</span></span>](manage-atp-post-migration.md) |


## <a name="do-you-have-feedback-for-us"></a><span data-ttu-id="f1b7d-126">フィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-126">Do you have feedback for us?</span></span>

<span data-ttu-id="f1b7d-127">ご意見をお知らせください。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-127">Let us know what you think!</span></span> <span data-ttu-id="f1b7d-128">ページの下部にフィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-128">Submit your feedback at the bottom of the page.</span></span> <span data-ttu-id="f1b7d-129">引き続き改善し、移行ガイダンスに追加する場合は、フィードバックを考慮します。</span><span class="sxs-lookup"><span data-stu-id="f1b7d-129">We'll take your feedback into account as we continue to improve and add to our migration guidance.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1b7d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1b7d-130">See also</span></span>

- [<span data-ttu-id="f1b7d-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1b7d-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
- [<span data-ttu-id="f1b7d-132">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f1b7d-132">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="f1b7d-133">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1b7d-133">Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection?) 
