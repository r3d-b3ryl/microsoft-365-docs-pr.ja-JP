---
title: Microsoft 365 Enterprise の Microsoft Teams を展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft Teams について学習し、展開していきます。
ms.openlocfilehash: 8220d06fe90bc4bc793ab33d6121e93bb855f973
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801242"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="8e042-103">Microsoft 365 Enterprise の Microsoft Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="8e042-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8e042-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="8e042-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="8e042-p101">Microsoft Teams には、チャット、会議、ドキュメント共有、会話スレッド機能が組み込まれており、コンテンツの作成とグループ間でのコンテンツの共有を容易にします。Teams は、Microsoft 365 Enterprise でチーム作業と共同作業を行うためのコンポーネントであり、Microsoft 365 の Built for Teamwork の価値の重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="8e042-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365.</span></span> 

<span data-ttu-id="8e042-107">Teams を初めて利用する場合は、「[Microsoft Teams へようこそ](https://docs.microsoft.com/MicrosoftTeams/teams-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e042-107">If you're brand new to Teams, see [Welcome to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span> 


## <a name="roll-out-teams-to-your-organization"></a><span data-ttu-id="8e042-108">Teams を組織に展開する</span><span class="sxs-lookup"><span data-stu-id="8e042-108">Roll out Teams to your organization</span></span>

<span data-ttu-id="8e042-109">開始する前に:</span><span class="sxs-lookup"><span data-stu-id="8e042-109">Before you begin:</span></span>

- <span data-ttu-id="8e042-110">チームに必要なユーザー アカウントとセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-foundation-infrastructure.md)のフェーズが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e042-110">Make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the user accounts and security capabilities you need.</span></span> <span data-ttu-id="8e042-111">ID および情報保護のフェーズは、保持および機密ラベルが付いた安全な電子メールおよびファイルにサイン オンして使用するのに最も重要です。</span><span class="sxs-lookup"><span data-stu-id="8e042-111">The Identity and Information Protection phases are the most important for signing on and using securing email and files with retention and sensitivity labels.</span></span>
- <span data-ttu-id="8e042-112">[この記事](https://docs.microsoft.com/microsoftteams/security-compliance-overview)では、Teams のセキュリティとコンプライアンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8e042-112">Learn about security and compliance in Teams with [this article](https://docs.microsoft.com/microsoftteams/security-compliance-overview).</span></span>
- <span data-ttu-id="8e042-113">[この記事](https://docs.microsoft.com/microsoftteams/office-365-licensing)では、Teams 向け Office 365 のライセンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8e042-113">Learn about Office 365 licensing for Teams with [this article](https://docs.microsoft.com/microsoftteams/office-365-licensing).</span></span>

<span data-ttu-id="8e042-114">組織で Teams を展開するには、「[Teams のロールアウト方法](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8e042-114">To roll out Teams in your organization, read [How to roll out Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).</span></span>

<span data-ttu-id="8e042-115">Teams 機能の最初のセットについては、「[Microsoft Teams のチャット、チーム、チャネル、およびアプリ](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e042-115">For your first set of Teams capabilities, see [Chat, teams, channels, and apps in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).</span></span>

<span data-ttu-id="8e042-116">Teams のより高度な機能については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e042-116">For more advanced Teams capabilities, see:</span></span>

- [<span data-ttu-id="8e042-117">会議</span><span class="sxs-lookup"><span data-stu-id="8e042-117">Meetings and Conferencing</span></span>](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- <span data-ttu-id="8e042-118">[クラウド ボイス](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (Microsoft 365 E5 が必要です)</span><span class="sxs-lookup"><span data-stu-id="8e042-118">[Cloud voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requires Microsoft 365 Enterprise E5)</span></span>

<span data-ttu-id="8e042-119">組織の Teams の使用状況を監視するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e042-119">To monitor your organization's usage of Teams, see:</span></span>

- [<span data-ttu-id="8e042-120">Teams でチーム間およびチーム別に分析する</span><span class="sxs-lookup"><span data-stu-id="8e042-120">Cross-team and per-team analytics in Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [<span data-ttu-id="8e042-121">分析とレポート</span><span class="sxs-lookup"><span data-stu-id="8e042-121">Analytics and reporting</span></span>](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a><span data-ttu-id="8e042-122">Teams へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="8e042-122">Upgrade to Teams</span></span>

<span data-ttu-id="8e042-123">まだ行っていない場合は、まもなく Skype for Business から Microsoft Teams にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8e042-123">If it hasn’t happened already, you will soon upgrade from Skype for Business to Microsoft Teams.</span></span> <span data-ttu-id="8e042-124">Teams を始めたばかりでも、すでに Skype for Business とともに Teams を使用している場合でも、アップグレードの準備ができている場合でも、Teams への旅を成功させるために必要なもののすべてが揃っていることを確認したいと思います。</span><span class="sxs-lookup"><span data-stu-id="8e042-124">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we want to ensure you have everything you need to navigate a successful journey to Teams.</span></span>

<span data-ttu-id="8e042-125">Skype for Business Online から Teams にアップグレードする場合でも、Skype for Business オンプレミス環境から Teams にアップグレードする場合でも、アップグレード フレームワークは、ビジネス シナリオに基づいたプロセスをガイドします。</span><span class="sxs-lookup"><span data-stu-id="8e042-125">Whether you are upgrading from Skype for Business Online to Teams or from a Skype for Business on-premises environment to Teams, the upgrade framework will guide you through the process based on your business scenario.</span></span>
 
<span data-ttu-id="8e042-126">詳細情報については、「[Microsoft Teams へのアップグレードを開始する](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e042-126">See the [Getting started with your Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here) for more information.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="8e042-127">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="8e042-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="8e042-128">Microsoft がどのように Teams を展開し、共同作業に使用しているかについては下記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e042-128">To peek inside Microsoft and learn how we deployed and are using Teams for collaboration, see:</span></span>

- [<span data-ttu-id="8e042-129">Microsoft Teams の導入戦略により、従業員は新しい仕事文化に備えることができる</span><span class="sxs-lookup"><span data-stu-id="8e042-129">Microsoft Teams adoption strategy prepares employees for a new culture of work</span></span>](https://www.microsoft.com/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [<span data-ttu-id="8e042-130">Microsoft Teams ミーティングにより、グローバルにスケーラブルな最新の会議体験が実現できる</span><span class="sxs-lookup"><span data-stu-id="8e042-130">With Microsoft Teams Rooms, comes a globally scalable modern meeting experience</span></span>](https://www.microsoft.com/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a><span data-ttu-id="8e042-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="8e042-131">Next steps</span></span>

- [<span data-ttu-id="8e042-132">組織の Microsoft Teams の機能を管理する</span><span class="sxs-lookup"><span data-stu-id="8e042-132">Manage Microsoft Teams features for your organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="8e042-133">Microsoft Teams の管理者トレーニング</span><span class="sxs-lookup"><span data-stu-id="8e042-133">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

