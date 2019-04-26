---
title: Microsoft 365 Enterprise の Microsoft Teams を展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft 365 Enterprise の Microsoft Teams を計画、ロールアウトするプロセス、および Microsoft Teams の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 646062babf525be176386264b4ef3c4a3a21647a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291661"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="f861f-103">Microsoft 365 Enterprise の Microsoft Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="f861f-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f861f-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="f861f-104">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="f861f-p101">Microsoft Teams には、チャット、会議、ドキュメント共有、会話スレッド機能が組み込まれており、コンテンツの作成とグループ間でのコンテンツの共有を容易にします。Teams は、Microsoft 365 Enterprise でチーム作業とコラボレーションを行うためのコンポーネントであり、Microsoft 365 の Built for Teamwork の価値を構成する重要な要素です。Teams を初めて利用する場合は、「[Microsoft Teams の概要](https://docs.microsoft.com/MicrosoftTeams/teams-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365. If you are brand new to Teams, see [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span>
 
<span data-ttu-id="f861f-p102">現在 Skype for Business を利用しているお客様には、現在 Microsoft は Teams への Skype for Business 機能の組み込みに取り組んでいることをお知らせします。少し時間をいただくことになるかもしれませんが、Teams は最終的にはシングル クライアント エクスペリエンスとなる予定です。Microsoft は、Skype for Business を利用しているお客様をサポートいたします。詳細については、「[Skype for Business から Microsoft Teams への移行](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p102">If you’re currently using Skype for Business, we’re building Skype for Business capabilities into Teams. This will happen over time, and ultimately Teams will become the single client experience. As a valued Skype for Business customer, Microsoft is here to support you. See the [Journey from Skype for Business to Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) for more information.</span></span>

<span data-ttu-id="f861f-112">次に示すフェーズと手順では、組織における Teams の役割を想定し、段階的な一連のロールアウトにより組織が Teams の研修を行い、Teams の用途とエンドユーザーに対する Teams の価値を促進するプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="f861f-112">The following phases and steps guide you through the process of envisioning the role of Teams in your organization, onboarding your organization to Teams through a series of progressive rollouts, and driving usage of Teams and its value to your end users.</span></span> 

<span data-ttu-id="f861f-113">まず始める前に、チームに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-foundation-infrastructure.md)のフェーズが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f861f-113">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your teams have the security capabilities you need.</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="f861f-114">フェーズ 1: 想定</span><span class="sxs-lookup"><span data-stu-id="f861f-114">Phase 1: Envision</span></span>

<span data-ttu-id="f861f-115">このフェーズでは、Teams の展開にあたって関係者を招集し、組織でビジネス ニーズに対応するためどのように Teams を利用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f861f-115">In this phase, you gather the people for your Teams deployment and determine how your organization will use Teams to address its business needs.</span></span>

### <a name="step-1-gather-your-teams-deployment-members"></a><span data-ttu-id="f861f-116">手順 1: Teams 展開メンバーを招集する</span><span class="sxs-lookup"><span data-stu-id="f861f-116">Step 1: Gather your Teams deployment members</span></span>
<span data-ttu-id="f861f-p103">Microsoft 365 [基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に Teams を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。</span><span class="sxs-lookup"><span data-stu-id="f861f-p103">For a successful deployment of Teams on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="f861f-119">この 3 つのグループを招集することにより、Teams の展開に、ビジネス ニーズを反映した考慮事項と、ライセンスおよびセキュリティの技術的側面が反映され、Teams は標準的なユーザーが使用するアプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="f861f-119">These three groups ensure that your Teams deployment includes considerations that address business needs, technical aspects of licensing and security, and that Teams will be something that your typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="f861f-120">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-120">Result</span></span>

<span data-ttu-id="f861f-121">組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="f861f-121">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a><span data-ttu-id="f861f-122">手順 2: Teams のビジネス シナリオを決定し優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="f861f-122">Step 2: Determine and prioritize your Teams business scenarios</span></span>
<span data-ttu-id="f861f-p104">Teams はさまざまな目的に使用できます。ビジネス グループ、部門、個々の作業チームとプロジェクト チームといった組織の各レベルのビジネス ニーズと目的の対応関係を特定する必要があります。Teams のシナリオの定義に役立つ例については、「[Microsoft 365 Productivity Library](https://www.microsoft.com/en-us/microsoft-365/success/?rtc=1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p104">Teams can be used for many different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, and individual working and project teams. Take a look at the [Microsoft 365 Productivity Library](https://www.microsoft.com/en-us/microsoft-365/success/?rtc=1) for examples to help you define Teams scenarios.</span></span> 

<span data-ttu-id="f861f-p105">機敏で極めてコラボレーティブであり、密接に連携し、Exchange Online のメールにとどまらずさまざまな機能 (履歴記録機能を備えたライブ グループ チャット、一般的で見つけやすいファイルとメモの保存場所など) を必要とするチームに対処することを、Teams の目標とします。</span><span class="sxs-lookup"><span data-stu-id="f861f-p105">You should target Teams to address fast-moving and highly collaborative teams that work closely together and require many more facilities than just email with Exchange Online can provide. Examples are live group chats with a recorded history and a common and easy-to-find place to store files and notes.</span></span> 

<span data-ttu-id="f861f-128">Teams のメリットを確認できる方法の 1 つとして、現在のチーム間のコミュニケーション方法を調べ、そのコミュニケーションを置き換えて共同作業を容易にする方法を提示する適切な Teams のシナリオを見つけ、追加機能を提供する方法があります。</span><span class="sxs-lookup"><span data-stu-id="f861f-128">One way to see the benefits of Teams is to examine how a team or v-team interacts today, and then find an appropriate Teams scenario that replaces the interaction and provides easier ways to collaborate and provide additional capabilities.</span></span>

<span data-ttu-id="f861f-129">Teams を使用すると、Microsoft 365 Enterprise の次の戦略的なビジネス シナリオを実現可能にします:</span><span class="sxs-lookup"><span data-stu-id="f861f-129">Teams enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="f861f-130">チーム内でコミュニケーションを図って、最新の情報に精通し、意見を求め、団結力と考えの一致を高めます</span><span class="sxs-lookup"><span data-stu-id="f861f-130">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="f861f-131">現場担当者を連携させて、デジタル改革を可能にします</span><span class="sxs-lookup"><span data-stu-id="f861f-131">Engage your firstline workers to enable your Digital Transformation</span></span>
- <span data-ttu-id="f861f-132">業務の習慣を理解して、影響力を増します</span><span class="sxs-lookup"><span data-stu-id="f861f-132">Understand your work habits to improve your influence and impact</span></span>

<span data-ttu-id="f861f-133">詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-133">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="microsoft-teams-for-highly-regulated-data"></a><span data-ttu-id="f861f-134">厳しく規制されたデータに対応した Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f861f-134">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="f861f-p106">厳しく規制されたデータとは、地域の規制の対象になっているデータや、組織にとって最も重要なデータ (営業秘密、財務や人事の情報、組織戦略など) のことです。チームは、この種のデータのアクセス制限、データ分類、データ損失保護、暗号化に対応するように構成できます。詳細については、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="f861f-138">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-138">Result</span></span>

<span data-ttu-id="f861f-139">組織における共同作業とチームワークのニーズに対応する一連の Teams のシナリオ。</span><span class="sxs-lookup"><span data-stu-id="f861f-139">A list of Teams scenarios that address your organization’s needs for collaboration and teamwork.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="f861f-140">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="f861f-140">Phase 2: Onboard</span></span>

<span data-ttu-id="f861f-141">このフェーズでは、Teams の展開の技術的な側面を計画し、一部のユーザー グループへの Teams のロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="f861f-141">In this phase, you plan for the technical aspects of a Teams deployment and start rolling out Teams to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="f861f-142">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="f861f-142">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="f861f-143">チームへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint Online アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f861f-143">To protect access to teams, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="f861f-144">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="f861f-144">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="f861f-p107">技術計画を開始する前に、FastTrack を使用するかどうかを決定します。組織のシート数が 50 を超えており、組織が[対象となるプラン](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合、無料で提供されている [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365) を使用して、計画、展開、サービス導入を順に実施できます。あるいは、FastTrack Onboarding Wizard を使用してこの作業を各自で実施することもできます。FastTrack Onboarding Wizard は、Office 365 アカウントでサインインした後、[FastTrack](https://fasttrack.microsoft.com/) から利用できます。</span><span class="sxs-lookup"><span data-stu-id="f861f-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment and service adoption. Or, you can complete this work yourself using our FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="f861f-p108">各自で計画を策定している場合 (または FastTrack を使用している場合) には、ネットワークと組織が Teams を導入できる状態にあるかどうかを判断する必要があります。特に、[基礎インフラストラクチャ](deploy-foundation-infrastructure.md)のネットワークの終了条件を満たしており、Teams を使用した会議のパフォーマンスを最大限に引き出すため、帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="f861f-p108">If you are doing your own planning (or in conjunction with FastTrack), you need to determine if your network and organization are ready for Teams. It is especially important that you meet the exit criteria for networking in your [foundation infrastructure](deploy-foundation-infrastructure.md), with special attention to bandwidth, throughput, and traffic delays to maximize performance for Teams-based meetings.</span></span>

<span data-ttu-id="f861f-150">次のリソースを使用して、Teams のロールアウトに向けた組織の技術的な側面を準備します。</span><span class="sxs-lookup"><span data-stu-id="f861f-150">Use these resources to prepare the technical aspects of your organization for a Teams rollout:</span></span> 

- [<span data-ttu-id="f861f-151">Teams の導入に向けた環境の準備を確認する</span><span class="sxs-lookup"><span data-stu-id="f861f-151">Check your environment's readiness for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [<span data-ttu-id="f861f-152">Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="f861f-152">Prepare your network for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [<span data-ttu-id="f861f-153">Office 365 の URL と IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="f861f-153">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

<span data-ttu-id="f861f-154">Teams のセキュリティについての理解を深めるには、次の追加リソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-154">For a better understanding of security in Teams, review the following additional resources:</span></span>

- [<span data-ttu-id="f861f-155">Teams のセキュリティとコンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="f861f-155">Overview of security and compliance in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [<span data-ttu-id="f861f-156">Office 365 グループと Teams</span><span class="sxs-lookup"><span data-stu-id="f861f-156">Office 365 groups and Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [<span data-ttu-id="f861f-157">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="f861f-157">Guest access in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

<span data-ttu-id="f861f-158">次に、以下のリソースを使用して、Team のライセンスを理解し、組織で Teams をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="f861f-158">Next, use these resources to understand Teams licensing and to perform the setup of Teams for your organization:</span></span>

- [<span data-ttu-id="f861f-159">Teams の Office 365 ライセンス</span><span class="sxs-lookup"><span data-stu-id="f861f-159">Office 365 licensing for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [<span data-ttu-id="f861f-160">Microsoft Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="f861f-160">Manage user access to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [<span data-ttu-id="f861f-161">Microsoft Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="f861f-161">Get clients for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [<span data-ttu-id="f861f-162">Office 365 の組織で Microsoft Teams を有効にする</span><span class="sxs-lookup"><span data-stu-id="f861f-162">Turn on Microsoft Teams in your Office 365 organization</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [<span data-ttu-id="f861f-163">Office 365 の組織で Microsoft Teams の機能を管理する</span><span class="sxs-lookup"><span data-stu-id="f861f-163">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a><span data-ttu-id="f861f-164">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-164">Result</span></span>

<span data-ttu-id="f861f-165">ネットワーク、セキュリティ、Office 365 ライセンスの計画が完了し、組織内の一部のグループへの Teams のロールアウトを開始する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="f861f-165">Your network, security, and Office 365 licensing planning is done and you are ready to begin rolling out Teams to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="f861f-166">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="f861f-166">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="f861f-p109">中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f861f-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="f861f-p110">IT パイロット参加者が試すことができる Teams ビジネス シナリオを選択します。アイディアについては、「[Microsoft Teams 作業開始キット](http://microsoft.com/download/56505)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p110">Choose a Teams business scenario in which your IT pilot participants can practice. See the [Microsoft Teams getting started kit](http://microsoft.com/download/56505) for ideas.</span></span>
- <span data-ttu-id="f861f-171">パイロット参加者に対し、Teams を使用したチャット、ファイル保存、会議などの機能をテストするための演習課題を提示します。</span><span class="sxs-lookup"><span data-stu-id="f861f-171">Give your pilot participants a set of exercises to test Teams-based chats, file storage, meetings, and other capabilities.</span></span>
- <span data-ttu-id="f861f-p111">変更管理戦略を決定し、組織全体のユーザーによる受け入れを促進するための資料を作成します。変更管理資料には、電子メールの発表文、社内トレーニング計画、通路用ポスター、プレゼンテーションなどが含まれます。これらの資料は、Teams に対する関心を高め、利用を促進することを目標とし、組織全体に Team とそのメリットを伝達します。いくつかのアイディアについては、「[Microsoft Teams の変更管理戦略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p111">Determine your change management strategy and produce materials to drive organization-wide user adoption. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Teams and its benefits with the goals of raising awareness and driving usage. See [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) for some ideas.</span></span>
- <span data-ttu-id="f861f-p112">IT パイロットの参加者に、各自の経験に基づく変更管理戦略の資料のレビューを依頼します。参加者から、ベスト プラクティスに関するヒントや、Teams のメリットを説明する最適な方法および共同作業とチームワークに Teams を使用する方法に関するアドバイスを得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f861f-p112">Have your IT pilot participants review the change management strategy materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Teams and how to use it for collaboration and teamwork.</span></span>

#### <a name="result"></a><span data-ttu-id="f861f-178">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-178">Result</span></span>

<span data-ttu-id="f861f-179">Teams の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。</span><span class="sxs-lookup"><span data-stu-id="f861f-179">Your Teams IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="f861f-180">手順 3: ビジネス グループへロールアウトする</span><span class="sxs-lookup"><span data-stu-id="f861f-180">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="f861f-p113">IT パイロットの完了後に、Teams を組織内のビジネス グループまたは部門にロールアウトします。このロールアウトでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f861f-p113">After completing your IT pilot, roll out Teams to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="f861f-183">ビジネス グループにおける Teams の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="f861f-183">Identification of key business scenarios for Teams within the business group.</span></span>
- <span data-ttu-id="f861f-184">部門、作業チーム、プロジェクト チームにおける Teams の用途の想定事項とタイムラインをユーザーに伝達するアナウンスメント アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="f861f-184">Announcement activities to inform users of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="f861f-185">Teams に関する直接的なユーザー トレーニング、または Teams とその使用法を紹介するリソースへのリンク。</span><span class="sxs-lookup"><span data-stu-id="f861f-185">Direct user training on Teams or links to resources to introduce Teams and how to use it.</span></span>
- <span data-ttu-id="f861f-186">ビジネス グループのユーザーからのコメントや問題点の指摘を収集するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央チームなど)。</span><span class="sxs-lookup"><span data-stu-id="f861f-186">A feedback mechanism, such as a central team containing everyone in the business group, to collect comments and issues from users in the business group.</span></span>

<span data-ttu-id="f861f-187">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="f861f-187">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="f861f-188">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-188">Result</span></span>

<span data-ttu-id="f861f-189">ビジネス グループの 1 つは Teams を運用しており、変更管理資料のテストと調整が完了しています。</span><span class="sxs-lookup"><span data-stu-id="f861f-189">A business group is up and running with Teams and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="f861f-190">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="f861f-190">Phase 3: Drive value</span></span>

<span data-ttu-id="f861f-191">このフェーズでは、組織への Teams のロールアウトを実施し、ユーザーが Teams のメリットを実感できるようにユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f861f-191">In this phase, you complete the rollout of Teams to your organization and support your users so that they are realizing its benefits.</span></span>

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a><span data-ttu-id="f861f-192">手順 1: 組織のその他の部分に Teams をロールアウトする</span><span class="sxs-lookup"><span data-stu-id="f861f-192">Step 1: Roll out Teams to the rest of your organization</span></span>

<span data-ttu-id="f861f-p114">対象となるビジネス グループへのロールアウトが完了したら、Teams を組織のその他の部分にロールアウトします。このロールアウトでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f861f-p114">After completing your rollout to a targeted business group, roll out Teams to the rest of your organization. This rollout should include:</span></span>

- <span data-ttu-id="f861f-195">個々のビジネス グループにおける Teams の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="f861f-195">Identification of key business scenarios for Teams within your separate business groups.</span></span>
- <span data-ttu-id="f861f-196">部門、作業チーム、プロジェクト チームにおける Teams の用途の想定事項とタイムラインをユーザーに伝達するアナウンスメント アクティビティに、調整した変更管理資料を使用する。</span><span class="sxs-lookup"><span data-stu-id="f861f-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="f861f-p115">Teams のユーザー トレーニングまたは Teams とその使用法を紹介するリソースへのリンクを提供する。「[Microsoft Teams のエンド ユーザー トレーニング](https://docs.microsoft.com/microsoftteams/enduser-training)」にあるトレーニング リソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p115">Delivering user training on Teams or links to resources to introduce Teams and how to use it. See the training resources at [End user training for Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training).</span></span>
- <span data-ttu-id="f861f-p116">組織のユーザーからのコメントや問題点の指摘を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p116">A feedback mechanism, such as a central team containing everyone, to collect comments and act on issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="f861f-202">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-202">Result</span></span>

<span data-ttu-id="f861f-203">組織は Teams を運用しており、Teams の使用を開始するための情報を伝達し、トレーニングを実施し、使用を開始できるようにする変更管理戦略を実施しています。</span><span class="sxs-lookup"><span data-stu-id="f861f-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to begin using Teams.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="f861f-204">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="f861f-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="f861f-205">Teams を組織全体にロールアウトしたら、次の目的で変更管理戦略を引き続き採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f861f-205">After rolling out Teams to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="f861f-206">Teams を組織のチームワークおよびコラボレーション ツールとして推進する点でリーダーシップを発揮する。</span><span class="sxs-lookup"><span data-stu-id="f861f-206">Have your leadership promote Teams as the teamwork and collaboration tool for the organization.</span></span>
- <span data-ttu-id="f861f-207">ビジネス グループ、部門、作業チーム、プロジェクト チームでのコミュニケーションおよびコラボレーションに Teams を使用するよう各従業員を促す。</span><span class="sxs-lookup"><span data-stu-id="f861f-207">Encourage individuals to use it for business group, departmental, work, and project team communications and collaboration.</span></span>

<span data-ttu-id="f861f-208">推奨されるアクティビティの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f861f-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="f861f-209">「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="f861f-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="f861f-p117">「[Office 365 アクティビティ レポート](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できる管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f861f-p117">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is to grant your user account Reports Reader permissions so you can access activity reports.</span></span>
- <span data-ttu-id="f861f-p118">フィードバック機能 (中央チームまたは Yammer のパブリック チャネル) を監視し、各メンバーからの Teams を使用した上での問題の指摘やフィードバックがないか確認します。質問や問題には可能な限り迅速に対応し、メンバーが Teams に対し不満を抱えたり Teams を放棄したりすることがないようにします。</span><span class="sxs-lookup"><span data-stu-id="f861f-p118">Monitor your feedback venue (a public channel in a central team or Yammer) for issues and feedback from individuals about their experiences with Teams. Address questions and issues as quickly as you can to prevent frustration and abandonment of Teams by individuals.</span></span>
- <span data-ttu-id="f861f-p119">各ビジネス グループのチャンピオンを特定して育成し、Teams を使用して達成できた内容やベスト プラクティスを強調します。チャンピオンの成功事例を組織に反映し、プロジェクトの成功と導入を紹介します。ビジネス グループ内の技術リーダーからの支持は、他のリーダーや同僚に大きな影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="f861f-p119">Identify and nurture your champions in each business group and highlight their accomplishments and best practices using Teams. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="f861f-217">結果</span><span class="sxs-lookup"><span data-stu-id="f861f-217">Result</span></span>

<span data-ttu-id="f861f-218">組織のコラボレーションおよびチームワーク ツールとして Teams が導入されます。</span><span class="sxs-lookup"><span data-stu-id="f861f-218">Your organization has adopted Teams as its collaboration and teamwork tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="f861f-219">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="f861f-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f861f-220">Microsoft がどのように Microsoft Teams を展開し、コラボレーションに使用しているかについては下記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f861f-220">To peek inside Microsoft and learn how the company deployed and is using Microsoft Teams for collaboration, see:</span></span>

- [<span data-ttu-id="f861f-221">Microsoft Teams の展開により、コラボレーションが効率化し、チームワークが向上する</span><span class="sxs-lookup"><span data-stu-id="f861f-221">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="f861f-222">Microsoft Teams は Microsoft の最新の職場でのコラボレーションを向上させる</span><span class="sxs-lookup"><span data-stu-id="f861f-222">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a><span data-ttu-id="f861f-223">次の手順</span><span class="sxs-lookup"><span data-stu-id="f861f-223">Next steps</span></span>

- [<span data-ttu-id="f861f-224">Office 365 の組織で Microsoft Teams の機能を管理する</span><span class="sxs-lookup"><span data-stu-id="f861f-224">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="f861f-225">Microsoft Teams の管理者トレーニング</span><span class="sxs-lookup"><span data-stu-id="f861f-225">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
