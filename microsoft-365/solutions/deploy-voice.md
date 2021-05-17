---
title: 音声をネットワークに展開Microsoft 365
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
description: 組織に適切な音声ソリューションを選択Teams展開する方法について学習します。
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918384"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="28352-103">Teams 音声ソリューションを計画し展開する</span><span class="sxs-lookup"><span data-stu-id="28352-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="28352-104">音声Teamsを使用すると、組織内のユーザーが組織内外の両方で通話を行える。</span><span class="sxs-lookup"><span data-stu-id="28352-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="28352-105">完全な音声ソリューションは、Teams、Microsoft 電話、および公衆交換電話網 (PSTN) に接続するためのオプションの選択で構成されます。</span><span class="sxs-lookup"><span data-stu-id="28352-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams音声ソリューションの概要](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="28352-107">電話システム組織に完全なプライベート ブランチ Exchange (PBX) 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="28352-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="28352-108">組織内のユーザー間の呼び出し (地理的な場所に関係なく) は、電話システム 内で内部的に処理され、これらの内部通話の長距離コストが削減されます。</span><span class="sxs-lookup"><span data-stu-id="28352-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="28352-109">ユーザーは電話システム公衆交換電話網 (PSTN) に接続することで、ユーザー Teams組織外にも通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="28352-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="28352-110">このソリューション ガイダンスは、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28352-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="28352-111">組織に合った音声ソリューションを選択する</span><span class="sxs-lookup"><span data-stu-id="28352-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="28352-112">選択した音声ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="28352-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="28352-113">音声ソリューションを選択、計画、および構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="28352-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![音声ソリューションを選択する](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="28352-115">音声ソリューションを選択する</span><span class="sxs-lookup"><span data-stu-id="28352-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="28352-116">電話システムをセットアップする</span><span class="sxs-lookup"><span data-stu-id="28352-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="28352-117">次のいずれかを選択するか、組み合わせて PSTN 接続をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="28352-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="28352-118">[通話プラン](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - MICROSOFT を PSTN キャリアとして使用する Microsoft のクラウド内すべてソリューション</span><span class="sxs-lookup"><span data-stu-id="28352-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="28352-119">[ダイレクト ルーティング](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)- ダイレクト ルーティングを使用して、独自の PSTN キャリアを接続Teams</span><span class="sxs-lookup"><span data-stu-id="28352-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="28352-120">さらに、大規模な多国籍企業が Contoso のケース スタディで、Teams音声ソリューションに移行した方法について[説明します](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="28352-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="28352-121">必要なライセンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28352-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="28352-122">Teams アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="28352-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="28352-123">ダイレクト ルーティング のライセンス要件</span><span class="sxs-lookup"><span data-stu-id="28352-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)