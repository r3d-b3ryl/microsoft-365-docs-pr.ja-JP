---
title: パイロット Microsoft 365 Defender プロジェクトの結果の概要
description: スコアカードを完了し、レポートの結果を分析し、前進する方法を決定することで、パイロット Microsoft 365 Defender プロジェクトを終了します。
keywords: Microsoft Threat Protection パイロットは、Microsoft Threat Protection のパイロット プロジェクトの後に何を行うのか、Microsoft Threat Protection の評価後に実行する操作、Microsoft Threat Protection パイロットから展開への移行、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜し方を決定します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f646fe7061fb0793fd9922068c9037be21a236cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920398"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="f5ac2-104">Microsoft 365 Defender パイロットの終了と概要</span><span class="sxs-lookup"><span data-stu-id="f5ac2-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5ac2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f5ac2-105">**Applies to:**</span></span>
- <span data-ttu-id="f5ac2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5ac2-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="f5ac2-107">[![計画](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="f5ac2-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="f5ac2-108">計画</span><span class="sxs-lookup"><span data-stu-id="f5ac2-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="f5ac2-109">[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="f5ac2-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="f5ac2-110">準備</span><span class="sxs-lookup"><span data-stu-id="f5ac2-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="f5ac2-111">[![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="f5ac2-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="f5ac2-112">攻撃のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="f5ac2-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![閉じて要約する](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="f5ac2-114">閉じて要約する</span><span class="sxs-lookup"><span data-stu-id="f5ac2-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="f5ac2-115">*お前はここにいる!*</span><span class="sxs-lookup"><span data-stu-id="f5ac2-115">*You are here!*</span></span>|


<span data-ttu-id="f5ac2-116">現在、閉じる段階と要約段階です。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="f5ac2-117">ドメイン コントローラーでコードをリモートで実行する高度なメモリ専用攻撃シミュレーションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="f5ac2-118">Microsoft Defender for Endpoint と Microsoft Defender for Identity が、ステルス的な悪意のあるアクティビティに関するアラートを検出して作成する方法を確認しました。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="f5ac2-119">また、Microsoft 365 セキュリティ センター ポータルで、さまざまなソースからのアラートが他のコンテキスト情報と共に 1 つのインシデントに配信される方法も確認しました。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="f5ac2-120">このような統合を経験すると、SOC アナリストは調査し、必要なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="f5ac2-121">また、ユーザーが添付ファイルを開いたか保存した受信メールを識別し、そのクエリに基づいて検出を作成する高度な検索クエリも作成しました。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="f5ac2-122">すべてのテストが終了した後、プロセスの終了に達しました。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="f5ac2-123">最終的な出力は次の値です。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-123">The final output should be:</span></span>

- <span data-ttu-id="f5ac2-124">完了したスコアカード</span><span class="sxs-lookup"><span data-stu-id="f5ac2-124">A completed scorecard</span></span>
- <span data-ttu-id="f5ac2-125">パイロットの調査結果の詳細なレポート</span><span class="sxs-lookup"><span data-stu-id="f5ac2-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="f5ac2-126">前進する方法に関する決定</span><span class="sxs-lookup"><span data-stu-id="f5ac2-126">A decision on how to move forward</span></span>

<span data-ttu-id="f5ac2-127">最終出力のレポートを内部関係者 (準備フェーズで特定した) と Microsoft[](./prepare-mtpeval.md)の連絡先に提示します。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-mtpeval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="f5ac2-128">このような取り組みにより、製品とドキュメントの改善にフィードバックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="f5ac2-129">このシミュレーションをお楽しみになって下さい。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="f5ac2-130">組織で学習した情報を大規模に実装し、統合セキュリティ ソリューションを最も役立て始める。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5ac2-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="f5ac2-131">Next step</span></span>
<span data-ttu-id="f5ac2-132">Microsoft 365 Defender の柱の詳細については、次の対話型ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5ac2-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="f5ac2-133">Microsoft Defender を使用して組織を保護Office 365</span><span class="sxs-lookup"><span data-stu-id="f5ac2-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="f5ac2-134">Microsoft Defender for Identity を使用して不審なアクティビティと潜在的な攻撃を検出する</span><span class="sxs-lookup"><span data-stu-id="f5ac2-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="f5ac2-135">Microsoft Cloud App Security を使用して脅威を検出し、アラートを管理する</span><span class="sxs-lookup"><span data-stu-id="f5ac2-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="f5ac2-136">Microsoft Defender for Endpoint を使用して脅威を調査および修復する</span><span class="sxs-lookup"><span data-stu-id="f5ac2-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)