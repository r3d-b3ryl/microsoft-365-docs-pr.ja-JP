---
title: 評価環境Microsoft 365 Defender作成します。 試用版ライセンスをアクティブ化または有効にし、Microsoft Defender for Identity (MDI) に進む。
description: 試用版のライセンスをMicrosoft 365 Defenderして、試用版ラボまたはパイロット環境をセットアップします。 次に、Microsoft Defender for Identity (MDI) と他のすべての M365D 評価をセットアップします。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458267"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="a9c2e-105">評価環境Microsoft 365 Defender作成する</span><span class="sxs-lookup"><span data-stu-id="a9c2e-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="a9c2e-106">評価では、この次の手順を実行する 2 つの一般的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="a9c2e-107">このドキュメントでは、実稼働 M365 テナントが既に存在し、E5 試用版ライセンスをアクティブ化して、現在の環境で M365 Defender を評価する必要 *があります*。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="a9c2e-108">インプレイス評価を使用すると、評価期間後にライセンスの購入に関するセキュリティ方法を保持できます。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="a9c2e-109">2 つ目は、[評価Microsoft 365 Defenderラボ環境](setup-m365deval.md)をセットアップする方法です。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="a9c2e-110">ビジネスからの実際のシグナルが多くはない可能性があります。その注意点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="a9c2e-111">E5 試用版ライセンスをアクティブ化して評価Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a9c2e-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="a9c2e-112">既存の M365 テナント管理ポータルにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="a9c2e-113">ナビゲーション *メニューから [サービス* の購入] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="a9c2e-114">[ライセンス] セクションまで *下Office 365* し、[ライセンス] の下にある [詳細] ボタンOffice 365 E5します。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="[Office 365] セクションには、クリックする [詳細] ボタンがあります。":::

4. <span data-ttu-id="a9c2e-116">[無料 *試用版の開始] リンクを* 選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="[無料試用版の開始] をクリックします (料金は 35$ です)。":::

5. <span data-ttu-id="a9c2e-118">要求を確認し、[今すぐ試 *す] ボタンを* クリックします。</span><span class="sxs-lookup"><span data-stu-id="a9c2e-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="[チェックアウトして、注文を確認する] パネルに [今すぐ試す] ボタンがあります (1 か月Office 365 E5 25 人のユーザーの場合)。":::

## <a name="next-steps"></a><span data-ttu-id="a9c2e-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="a9c2e-120">Next steps</span></span>
[<span data-ttu-id="a9c2e-121">Id のMicrosoft 365を有効にする</span><span class="sxs-lookup"><span data-stu-id="a9c2e-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="a9c2e-122">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a9c2e-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>