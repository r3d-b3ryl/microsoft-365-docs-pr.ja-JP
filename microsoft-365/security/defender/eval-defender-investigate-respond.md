---
title: パイロット環境でMicrosoft 365 Defenderを使用して調査と対応を行い、攻撃シミュレーターを使用し、ユーザーに攻撃表面の検出、調査、セキュリティ体制の強化を教えます
description: Microsoft 365 Defender 試用版ラボまたはパイロット環境で攻撃シミュレーションをセットアップし、デバイス、ID、データ、およびアプリケーションを保護するようにユーザーに教えるために設計されたセキュリティ ソリューションを試します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 590b9445b08e3a786b32e7086f27b140934d22d0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458409"
---
# <a name="investigate-and-respond-using-microsoft-365-defender-in-a-pilot-environment"></a><span data-ttu-id="50398-103">パイロット環境で、Microsoft 365 Defenderを使用して調査と対応を行う</span><span class="sxs-lookup"><span data-stu-id="50398-103">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>

<span data-ttu-id="50398-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="50398-104">**Applies to:**</span></span>
- <span data-ttu-id="50398-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50398-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="50398-106">この記事では、攻撃シミュレーションとチュートリアルを使用してインシデントを作成し、Microsoft 365 Defenderして対応するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="50398-106">This article outlines the process to create incidents with attack simulations and tutorials and use Microsoft 365 Defender to investigate and respond.</span></span> <span data-ttu-id="50398-107">このプロセスを開始する前に、評価プロセス全体を確認し、Microsoft 365 Defender評価[](eval-overview.md)環境をMicrosoft 365 Defender[してください](eval-create-eval-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="50398-107">Before starting this process, be sure you've reviewed the overall process for [evaluating Microsoft 365 Defender](eval-overview.md) and you have [created the Microsoft 365 Defender evaluation environment](eval-create-eval-environment.md).</span></span>

<span data-ttu-id="50398-108">次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="50398-108">Use the following steps.</span></span>

![評価環境でシミュレートされたインシデント応答を実行Microsoft 365 Defender手順](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-steps.png)

<span data-ttu-id="50398-110">次の表に、図の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="50398-110">The following table describes the steps in the illustration.</span></span>

| |<span data-ttu-id="50398-111">手順</span><span class="sxs-lookup"><span data-stu-id="50398-111">Step</span></span>  |<span data-ttu-id="50398-112">説明</span><span class="sxs-lookup"><span data-stu-id="50398-112">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="50398-113">1</span><span class="sxs-lookup"><span data-stu-id="50398-113">1</span></span>|[<span data-ttu-id="50398-114">攻撃のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="50398-114">Simulate attacks</span></span>](eval-defender-investigate-respond-simulate-attack.md)     |   <span data-ttu-id="50398-115">評価環境に対する攻撃をシミュレートし、Microsoft 365 Defenderポータルを使用してインシデント対応を実行します。</span><span class="sxs-lookup"><span data-stu-id="50398-115">Simulate attacks on your evaluation environment and use the Microsoft 365 Defender portal to perform incident response.</span></span>      |
|<span data-ttu-id="50398-116">2</span><span class="sxs-lookup"><span data-stu-id="50398-116">2</span></span>|[<span data-ttu-id="50398-117">インシデント対応機能を試す </span><span class="sxs-lookup"><span data-stu-id="50398-117">Try incident response capabilities </span></span>](eval-defender-investigate-respond-additional.md)    |    <span data-ttu-id="50398-118">デバイスで機能を試Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="50398-118">Try features and capabilities in Microsoft 365 Defender.</span></span>     |
||||

### <a name="navigation-you-may-need"></a><span data-ttu-id="50398-119">必要なナビゲーション</span><span class="sxs-lookup"><span data-stu-id="50398-119">Navigation you may need</span></span>

[<span data-ttu-id="50398-120">評価環境Microsoft 365 Defender作成する</span><span class="sxs-lookup"><span data-stu-id="50398-120">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
