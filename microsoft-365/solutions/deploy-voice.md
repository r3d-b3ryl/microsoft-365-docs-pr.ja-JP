---
title: Microsoft 365 での音声の展開
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 組織に適した Teams の音声ソリューションを選択して展開する方法について説明します。
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580901"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="c5450-103">Teams の音声ソリューションを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="c5450-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="c5450-104">Teams の音声ソリューションを使用すると、組織内のユーザーは組織の内部と外部の両方で電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="c5450-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="c5450-105">完全な音声ソリューションは、Teams、Microsoft Phone システム、および公衆交換電話網 (PSTN) に接続するためのオプションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c5450-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams の音声ソリューションの概要](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="c5450-107">電話システムは、組織のための完全な構内交換機 (PBX) 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5450-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="c5450-108">組織内のユーザー間での通話--地理的な場所に関係なく、電話システム内で内部的に処理され、これらの内部呼び出しで長距離のコストが排除されます。</span><span class="sxs-lookup"><span data-stu-id="c5450-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="c5450-109">電話システムを公衆交換電話網 (PSTN) に接続することで、Teams ユーザーは組織外でも電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="c5450-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="c5450-110">このソリューションガイダンスでは、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c5450-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="c5450-111">組織に適した音声ソリューションを選択する</span><span class="sxs-lookup"><span data-stu-id="c5450-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="c5450-112">選択した音声ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="c5450-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="c5450-113">次の手順に従って、音声ソリューションを選択、計画、および構成します。</span><span class="sxs-lookup"><span data-stu-id="c5450-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![音声ソリューションを選択する](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="c5450-115">音声ソリューションを選択する</span><span class="sxs-lookup"><span data-stu-id="c5450-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="c5450-116">電話システムをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c5450-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="c5450-117">次のいずれかを選択するか、または組み合わせを選択して、PSTN 接続をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="c5450-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="c5450-118">[通話プラン](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -microsoft のすべてのクラウドソリューションを PSTN キャリアとして microsoft と組み合わせて使用する</span><span class="sxs-lookup"><span data-stu-id="c5450-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="c5450-119">[直接ルーティング](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -直接ルーティングを使用して、自分の PSTN キャリアを Teams に接続します。</span><span class="sxs-lookup"><span data-stu-id="c5450-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="c5450-120">さらに、 [Contoso 社のケーススタディ](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)で、大規模な多国籍企業が Teams voice ソリューションに移行される方法についてお読みください。</span><span class="sxs-lookup"><span data-stu-id="c5450-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="c5450-121">必要なライセンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5450-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="c5450-122">Teams アドオンライセンス</span><span class="sxs-lookup"><span data-stu-id="c5450-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="c5450-123">直接ルーティングのライセンス要件</span><span class="sxs-lookup"><span data-stu-id="c5450-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
