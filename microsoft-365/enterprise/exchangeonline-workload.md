---
title: Microsoft 365 Enterprise の Exchange Online の展開
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 組織全体で Microsoft 365 Enterprise の Exchange Online の価値を計画、ロールアウト、および促進するプロセスについて順を追って説明します。
ms.openlocfilehash: 30ba71fbf2af684afbbffe0a2e2b1720a8eeec2c
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453863"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="0ccc3-103">Microsoft 365 Enterprise の Exchange Online の展開</span><span class="sxs-lookup"><span data-stu-id="0ccc3-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0ccc3-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="0ccc3-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="0ccc3-105">Exchange Online は、ユーザーがリアルタイムのチャットや一元化されたドキュメントの保存を必要としない方法で共同作業を行うことができるようにする、メールおよび予定表用のプライマリ クラウド サービスです。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="0ccc3-106">Exchange Online は、Microsoft 365 Enterprise のチームワークのために構築されたの重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-106">Exchange Online is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="0ccc3-107">Exchange Online を使用すると、使用しているデバイスに関係なく、既知の Outlook アプリケーションでより効果的に作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="0ccc3-108">また、Exchange Online には、メールボックスを保護するためのマルウェア対策およびスパム対策フィルター、ユーザーが機密情報を誤って許可のないユーザーに送信することを防ぐデータ損失防止機能を含む高度なセキュリティ機能もあります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="0ccc3-109">Exchange Online のセキュリティは、Microsoft 365 Enterprise のインテリジェントセキュリティ価値の重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="0ccc3-110">Exchange online を初めて使用する場合は、「[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="0ccc3-111">次のフェーズと手順に従って、組織内の Exchange Online の役割を構想し、組織を一連の段階的な展開によって Exchange Online にオンボードし、Exchange Online およびそのエンドユーザーへの値。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="0ccc3-112">これらの展開手順は[、Microsoft 365 Enterprise foundation インフラストラクチャのフェーズ2の id](identity-infrastructure.md)を完了した後にのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity of the Microsoft 365 Enterprise foundation infrastructure](identity-infrastructure.md).</span></span>
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a><span data-ttu-id="0ccc3-113">フェーズ 1: Exchange Online の展開の構想を作成する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-113">Phase 1: Envision your Exchange Online deployment</span></span>

<span data-ttu-id="0ccc3-114">このフェーズでは、Exchange Online の展開に関するユーザーを収集し、組織が Exchange Online を使用してビジネスニーズに対処する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="0ccc3-115">手順 1: Exchange Online の展開メンバーを収集する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="0ccc3-116">Microsoft 365 Enterprise foundation インフラストラクチャの[フェーズ 2-id](identity-infrastructure.md)の上に Exchange Online を正常に展開するには、入力とフィードバックのための適切な人物を集める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to gather the right people for input and feedback.</span></span> <span data-ttu-id="0ccc3-117">主要な人物としては、ビジネス意思決定者、アーキテクトや実装者などの IT スタッフ、およびエンドユーザーの支持者が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="0ccc3-118">これら3つのグループにより、Exchange Online の展開には、ビジネスニーズ、メールボックスの移行とセキュリティの技術的な側面についての考慮事項、および一般的なユーザーが使用するような結果が得られることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result is something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="0ccc3-119">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-119">Result</span></span>

<span data-ttu-id="0ccc3-120">組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="0ccc3-121">手順 2: Exchange Online のビジネスシナリオを決定し、優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="0ccc3-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="0ccc3-122">Exchange Online はさまざまな目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="0ccc3-123">組織のさまざまなレベル、ビジネスグループ、部門、または個別の作業およびプロジェクトチームについて、ビジネスニーズに対応する目的を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="0ccc3-124">個人および小規模グループの短時間の通信およびスケジュールのニーズを解決するには、Exchange Online を対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="0ccc3-125">Exchange Online の利点を確認する方法の1つは、個人、チーム、または v チームが現在どのように連携しているかを調べて、より簡単にコミュニケーションを行い、会議を計画し、共同作業を行うための適切なシナリオを見つけることです。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="0ccc3-126">グループ作業のシナリオによっては、 [Microsoft Teams](teams-workload.md)が適している場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="0ccc3-127">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-127">Result</span></span>
<span data-ttu-id="0ccc3-128">コミュニケーション、スケジュール、および短時間のコラボレーションに関する組織のニーズに対応する Exchange Online のシナリオの一覧。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-128">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="0ccc3-129">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="0ccc3-129">Phase 2: Onboard</span></span>

<span data-ttu-id="0ccc3-130">このフェーズでは、Exchange Online 展開の技術的な側面を計画し、選択したユーザーグループへのロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-130">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="0ccc3-131">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="0ccc3-131">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="0ccc3-132">Exchange Online メールボックスへのアクセスを保護するには、 [id とデバイスのアクセスポリシー](identity-access-policies.md)と、推奨される[exchange online アクセスポリシー](secure-email-recommended-policies.md)を構成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-132">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="0ccc3-133">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-133">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="0ccc3-134">技術計画を始める前に、FastTrack を使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-134">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="0ccc3-135">組織が50を超える座席を持ち、対象となる[プラン](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)に参加している場合は、計画、展開、およびサービスの導入に関する*追加費用*をかけずに、 [Microsoft 365 に fasttrack](https://fasttrack.microsoft.com/microsoft365)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-135">If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="0ccc3-136">また、この作業をお客様自身で完了することもできます。その場合は、Microsoft 365 アカウントでサインインすると [FastTrack](https://fasttrack.microsoft.com/) から利用できるようになる FastTrack オンボーディング ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-136">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="0ccc3-137">独自の計画を行っている場合や、FastTrack と連携している場合は、ネットワークと組織が Exchange Online の準備ができているかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-137">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="0ccc3-138">組織のネットワークに接続しているユーザーのために、基礎インフラストラクチャにおける[ネットワーク](networking-infrastructure.md)の終了条件を満たすことは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-138">It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network.</span></span> <span data-ttu-id="0ccc3-139">Exchange Online ベースの電子メールおよび添付ファイルに対する追加のトラフィックのパフォーマンスを最大にするために、インターネット帯域幅、スループット、トラフィック遅延に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-139">Pay special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="0ccc3-140">これらのリソースを使用して、Exchange Online ロールアウトの技術的な側面を準備します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-140">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="0ccc3-141">複数のメール アカウントを Office 365 に移行する方法</span><span class="sxs-lookup"><span data-stu-id="0ccc3-141">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [<span data-ttu-id="0ccc3-142">Exchange Server のパブリックフォルダーを Exchange Online に移行する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-142">Migrate Exchange Server public folders to Exchange Online</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [<span data-ttu-id="0ccc3-143">Exchange Server のパブリックフォルダーを Office 365 グループに移行する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-143">Migrate Exchange Server public folders to Office 365 Groups</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [<span data-ttu-id="0ccc3-144">Exchange Online でのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="0ccc3-144">Collaboration in Exchange Online</span></span>](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [<span data-ttu-id="0ccc3-145">Exchange Online の受信者</span><span class="sxs-lookup"><span data-stu-id="0ccc3-145">Recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [<span data-ttu-id="0ccc3-146">iOS 版および Android 版 Outlook</span><span class="sxs-lookup"><span data-stu-id="0ccc3-146">Outlook for iOS and Android</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

<span data-ttu-id="0ccc3-147">Exchange Online のセキュリティをより深く理解するには、次のリソースを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-147">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- [<span data-ttu-id="0ccc3-148">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ccc3-148">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [<span data-ttu-id="0ccc3-149">Exchange Online のセキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="0ccc3-149">Security and compliance for Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [<span data-ttu-id="0ccc3-150">スパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="0ccc3-150">Anti-spam and anti-malware protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

<span data-ttu-id="0ccc3-151">次に、これらのリソースを使用して Exchange Online メールボックス管理について理解します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-151">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- [<span data-ttu-id="0ccc3-152">Exchange Online でユーザーメールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-152">Create user mailboxes in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [<span data-ttu-id="0ccc3-153">ユーザー メールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="0ccc3-153">Manage user mailboxes</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [<span data-ttu-id="0ccc3-154">配布グループを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-154">Create and manage distribution groups</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a><span data-ttu-id="0ccc3-155">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-155">Result</span></span>

<span data-ttu-id="0ccc3-156">メールボックスの移行、セキュリティ、および管理について理解し、組織内の選択したグループへの Exchange Online のロールアウトを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-156">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="0ccc3-157">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-157">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="0ccc3-158">中規模および大規模な組織では、通常、フェーズ1、初期採用者、テクニカル愛好家から、関係者と共に IT パイロットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-158">For most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="0ccc3-159">IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-159">During the IT pilot:</span></span>

- <span data-ttu-id="0ccc3-160">パイロットに Microsoft 365 のライセンスを付与し、オンプレミスのメールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-160">Give your pilot participants Microsoft 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="0ccc3-161">パイロット参加者に、Exchange Online の電子メール、スケジュール、およびその他の機能をテストするための一連の実習を用意します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-161">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="0ccc3-162">変更管理戦略を決定し、組織全体のユーザーによる Outlook および Exchange Online の導入を促進するための資料を作成します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-162">Determine your change management strategy and produce materials to drive organization-wide user adoption of Outlook and Exchange Online.</span></span> 
 
  <span data-ttu-id="0ccc3-163">変更管理に関する資料には、メールによる発表テキスト、社内トレーニング プラン、廊下のポスター、プレゼンテーションを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-163">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="0ccc3-164">これらの資料は、組織に Exchange Online に関する情報を提供し、認識を向上させ、使用を推進することの目標を達成したものとします。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-164">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="0ccc3-165">いくつかのアイデアについては、 [Microsoft Teams の変更管理戦略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-165">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>

- <span data-ttu-id="0ccc3-166">IT パイロットの参加者には、自信の体験に基づいて変更管理の資料をレビューしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-166">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="0ccc3-167">これらのヒントには、Outlook と Exchange Online の利点についての最適な説明と、コミュニケーションとスケジュール設定に使用する方法についてのヒントが提供されています。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-167">They can provide tips on best practices and advice on how to best describe the benefits of Outlook and Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="0ccc3-168">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-168">Result</span></span>

<span data-ttu-id="0ccc3-169">Exchange Online IT パイロットは完成し、最初の変更管理資料が開発、レビュー、および調整されています。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-169">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="0ccc3-170">手順 3: ビジネス グループに展開する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-170">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="0ccc3-171">IT パイロットを完了した後、組織内のビジネスグループまたは部署に Exchange Online をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-171">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="0ccc3-172">組織が Exchange Server などの社内電子メールサービスを使用している場合、このロールアウトはメールボックスの移行で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-172">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="0ccc3-173">この展開では、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-173">This rollout should include:</span></span>

- <span data-ttu-id="0ccc3-174">ビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-174">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="0ccc3-175">部署や作業またはプロジェクトチームのための、Exchange Online の使用状況についての要望とタイムラインをユーザーに通知するアナウンスアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-175">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="0ccc3-176">ビジネスグループのメンバーの社内メールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-176">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="0ccc3-177">Outlook で[ユーザートレーニングを実施](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)するか、outlook およびその使用方法を紹介するリソースへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-177">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="0ccc3-178">ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-178">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="0ccc3-179">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-179">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="0ccc3-180">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-180">Result</span></span>

<span data-ttu-id="0ccc3-181">ビジネスグループは Outlook と Exchange Online を使用して稼働しており、変更管理資料のテストと調整が行われています。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-181">A business group is up and running with Outlook and Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="0ccc3-182">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="0ccc3-182">Phase 3: Drive value</span></span>

<span data-ttu-id="0ccc3-183">このフェーズでは、Exchange Online のロールアウトを完了し、ユーザーによるメリットの実現を支援するためにユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-183">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="0ccc3-184">手順 1: 組織の他の部分に Exchange Online をロールアウトする</span><span class="sxs-lookup"><span data-stu-id="0ccc3-184">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="0ccc3-185">組織の残りの部分へのロールアウトには、以下を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-185">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="0ccc3-186">個別のビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-186">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="0ccc3-187">Exchange Online の使用状況に関する期待値とタイムラインを組織に通知するために、改訂の変更管理資料をアナウンス活動に使用します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-187">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="0ccc3-188">組織の残りの部分のメールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-188">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="0ccc3-189">Outlook で[ユーザートレーニング](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)を実施するか、outlook およびその使用方法を紹介するリソースへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-189">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or provide links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="0ccc3-p112">組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="0ccc3-193">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-193">Result</span></span>

<span data-ttu-id="0ccc3-194">組織が稼働しており、ユーザーが Exchange Online を使用できるようにするために、変更管理戦略が実施されています。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-194">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="0ccc3-195">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-195">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="0ccc3-196">Exchange Online を組織全体にロールアウトした後、次のことを行うために、変更管理戦略を引き続き採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-196">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="0ccc3-197">リーダーシップを発揮して、個々の、および短期間のコミュニケーションとスケジューリングのための主要なツールとして Exchange Online を促進します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-197">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="0ccc3-198">ビジネスグループ、部門、作業、およびプロジェクトチームのコミュニケーション、予定表作成、グループ作業に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-198">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="0ccc3-199">推奨されるアクティビティの一部をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-199">Here are some suggested activities:</span></span>

- <span data-ttu-id="0ccc3-200">「[Office 365 の成功要因](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-200">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="0ccc3-p113">「[Office 365 アクティビティ レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="0ccc3-203">Exchange Online でのエクスペリエンスに関する問題とフィードバックについて、フィードバック会場 (中央チームのチームまたは Yammer のパブリックチャネル) を監視します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-203">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="0ccc3-204">ユーザーの不満を防ぎ、展開のサポートを実施できるように、質問と問題にすばやく対処します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-204">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="0ccc3-205">各ビジネスグループのエキスパートを特定して育成、Outlook を使用してベストプラクティスを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-205">Identify and nurture champions in each business group and highlight their best practices using Outlook.</span></span> <span data-ttu-id="0ccc3-206">組織に彼らの成果を反映させて、プロジェクトの成功と導入を示します。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-206">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="0ccc3-207">ビジネスグループ内の技術リーダーによる裏書は、リーダーとピアに大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-207">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="0ccc3-208">結果</span><span class="sxs-lookup"><span data-stu-id="0ccc3-208">Result</span></span>

<span data-ttu-id="0ccc3-209">組織は、Exchange Online と Outlook を、短時間の主要なコミュニケーションとスケジューリングツールとして採用しています。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-209">Your organization has adopted Exchange Online and Outlook as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="0ccc3-210">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="0ccc3-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0ccc3-211">Microsoft の内部を見て、exchange Online に移行し、Exchange Online Protection を使用してサイバー攻撃から保護する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-211">To peek inside Microsoft and learn how we migrated to Exchange Online and are using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="0ccc3-212">Microsoft では 150,000 のメールボックスを Exchange Online に移行</span><span class="sxs-lookup"><span data-stu-id="0ccc3-212">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="0ccc3-213">Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する</span><span class="sxs-lookup"><span data-stu-id="0ccc3-213">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="0ccc3-214">Microsoft の Office 365 を使用したフィッシング阻止の試み</span><span class="sxs-lookup"><span data-stu-id="0ccc3-214">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="0ccc3-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="0ccc3-215">Next steps</span></span>

<span data-ttu-id="0ccc3-216">Exchange Online の継続的なメンテナンスについては、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccc3-216">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- [<span data-ttu-id="0ccc3-217">Exchange Online の Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="0ccc3-217">Exchange admin center in Exchange Online</span></span>](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [<span data-ttu-id="0ccc3-218">Exchange Online での監視、レポート、メッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="0ccc3-218">Monitoring, reporting, and message tracing in Exchange Online</span></span>](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [<span data-ttu-id="0ccc3-219">Exchange Online の電子メールのバックアップ</span><span class="sxs-lookup"><span data-stu-id="0ccc3-219">Backing up email in Exchange Online</span></span>](https://docs.microsoft.com/exchange/back-up-email) 
