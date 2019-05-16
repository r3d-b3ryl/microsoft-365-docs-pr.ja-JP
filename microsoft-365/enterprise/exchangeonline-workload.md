---
title: Microsoft 365 Enterprise の Exchange Online の展開
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 組織全体で Microsoft 365 Enterprise の Exchange Online の価値を計画、ロールアウト、および促進するプロセスについて順を追って説明します。
ms.openlocfilehash: c54c80a955d86028ac473857cbdcb8b1a8f272d3
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072287"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="15d8c-103">Microsoft 365 Enterprise の Exchange Online の展開</span><span class="sxs-lookup"><span data-stu-id="15d8c-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="15d8c-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="15d8c-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="15d8c-105">Exchange Online は、電子メールと予定表のプライマリクラウドサービスで、リアルタイムのチャットやドキュメント保存の集中管理を必要としない方法でユーザーを共同作業するのに役立つ情報を備えています。</span><span class="sxs-lookup"><span data-stu-id="15d8c-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="15d8c-106">Exchange Online は、個人および小規模なグループの短時間のコミュニケーションとスケジューリングをどのようにしているのかを示すものであり、Microsoft 365 Enterprise のチームワークの価値を構築するための重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="15d8c-106">Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="15d8c-107">Exchange Online を使用すると、使用しているデバイスに関係なく、既知の Outlook アプリケーションでより効果的に作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="15d8c-108">Exchange Online には、マルウェア対策とスパム対策フィルターを含む高度なセキュリティ機能があり、メールボックスと、ユーザーが誤って機密情報を権限のないユーザーに送信しないようにするデータ損失防止機能を保護します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="15d8c-109">Exchange Online のセキュリティは、Microsoft 365 Enterprise のインテリジェントセキュリティ価値の重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="15d8c-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="15d8c-110">Exchange Online を初めて使用する場合は、「 [Microsoft Exchange online](https://products.office.com/exchange/exchange-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="15d8c-111">次のフェーズと手順に従って、組織内の Exchange Online の役割を構想し、組織を一連の段階的な展開によって Exchange Online にオンボードし、Exchange Online およびそのエンドユーザーへの値。</span><span class="sxs-lookup"><span data-stu-id="15d8c-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="15d8c-112">これらの展開手順は、Microsoft 365 Enterprise foundation インフラストラクチャの[フェーズ2の id](identity-infrastructure.md)を完了した後にのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="15d8c-113">フェーズ 1: 想定</span><span class="sxs-lookup"><span data-stu-id="15d8c-113">Phase 1: Envision</span></span>

<span data-ttu-id="15d8c-114">このフェーズでは、Exchange Online の展開に関するユーザーを収集し、組織が Exchange Online を使用してビジネスニーズに対処する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="15d8c-115">手順 1: Exchange Online の展開メンバーを収集する</span><span class="sxs-lookup"><span data-stu-id="15d8c-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="15d8c-116">Microsoft 365 Enterprise foundation インフラストラクチャの[フェーズ 2-id](identity-infrastructure.md)の上に Exchange Online を正常に展開するには、入力とフィードバックのための適切な人物を入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to get the right people for input and feedback.</span></span> <span data-ttu-id="15d8c-117">主要な人物としては、ビジネス意思決定者、アーキテクトや実装者などの IT スタッフ、およびエンドユーザーの支持者が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="15d8c-118">これら3つのグループにより、Exchange Online の展開には、ビジネスニーズ、メールボックスの移行とセキュリティの技術的な側面についての考慮事項、および一般的なユーザーが使用するものになることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="15d8c-119">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-119">Result</span></span>

<span data-ttu-id="15d8c-120">組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="15d8c-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="15d8c-121">手順 2: Exchange Online のビジネスシナリオを決定し、優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="15d8c-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="15d8c-122">Exchange Online はさまざまな目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="15d8c-123">組織のさまざまなレベル、ビジネスグループ、部門、または個別の作業およびプロジェクトチームについて、ビジネスニーズに対応する目的を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="15d8c-124">個人および小規模グループの短時間の通信およびスケジュールのニーズを解決するには、Exchange Online を対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="15d8c-125">Exchange Online の利点を確認する方法の1つは、個人、チーム、または v チームが現在どのように連携しているかを調べて、より簡単にコミュニケーションを行い、会議を計画し、共同作業を行うための適切なシナリオを見つけることです。</span><span class="sxs-lookup"><span data-stu-id="15d8c-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="15d8c-126">グループ作業のシナリオによっては、 [Microsoft Teams](teams-workload.md)が適している場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

<span data-ttu-id="15d8c-127">Exchange Online では、Microsoft 365 Enterprise の次のような戦略的なビジネスシナリオが有効になります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-127">Exchange Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="15d8c-128">リアルタイムまたは好きな時間にドキュメントで共同作業を行って、共同作成プロセスを簡略化します</span><span class="sxs-lookup"><span data-stu-id="15d8c-128">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="15d8c-129">プロジェクト、タスク、期限を管理して、ビジネス目標を達成します</span><span class="sxs-lookup"><span data-stu-id="15d8c-129">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="15d8c-130">業務の習慣を理解して、影響力を増します</span><span class="sxs-lookup"><span data-stu-id="15d8c-130">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="15d8c-131">チーム内でコミュニケーションを図って、最新の情報に精通し、意見を求め、団結力と考えの一致を高めます</span><span class="sxs-lookup"><span data-stu-id="15d8c-131">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="15d8c-132">組織内外でファイルを保管および共有して、組織の境界を越えてシームレスに作業を行います</span><span class="sxs-lookup"><span data-stu-id="15d8c-132">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="15d8c-133">柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます</span><span class="sxs-lookup"><span data-stu-id="15d8c-133">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="15d8c-134">情報を保護して、データ損失のリスクを軽減します</span><span class="sxs-lookup"><span data-stu-id="15d8c-134">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="15d8c-135">外部の脅威を検出して保護する</span><span class="sxs-lookup"><span data-stu-id="15d8c-135">Detect and protect against external threats</span></span> 
- <span data-ttu-id="15d8c-136">アクティビティを監視、報告、および分析して、組織のセキュリティを迅速に提供する</span><span class="sxs-lookup"><span data-stu-id="15d8c-136">Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="15d8c-137">一般データ保護規則 (GDPR) に適合するように、強化されたプライバシーと法令遵守によって組織をサポートします。</span><span class="sxs-lookup"><span data-stu-id="15d8c-137">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="15d8c-138">詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-138">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="result"></a><span data-ttu-id="15d8c-139">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-139">Result</span></span>
<span data-ttu-id="15d8c-140">コミュニケーション、スケジュール、および短時間のコラボレーションに関する組織のニーズに対応する Exchange Online のシナリオの一覧。</span><span class="sxs-lookup"><span data-stu-id="15d8c-140">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="15d8c-141">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="15d8c-141">Phase 2: Onboard</span></span>

<span data-ttu-id="15d8c-142">このフェーズでは、Exchange Online 展開の技術的な側面を計画し、選択したユーザーグループへのロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-142">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="15d8c-143">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="15d8c-143">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="15d8c-144">Exchange Online メールボックスへのアクセスを保護するには、 [id とデバイスのアクセスポリシー](identity-access-policies.md)と、推奨される[exchange online アクセスポリシー](secure-email-recommended-policies.md)を構成していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-144">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="15d8c-145">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="15d8c-145">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="15d8c-146">技術的な計画を開始する前に、FastTrack を使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-146">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="15d8c-147">組織が50を超える座席を持ち、対象となる[プラン](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合は、計画、展開、およびサービスの導入に関する追加費用をかけずに、 [Microsoft 365 に fasttrack](https://fasttrack.microsoft.com/microsoft365)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-147">If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="15d8c-148">または、Office 365 アカウントでサインインした後に[fasttrack](https://fasttrack.microsoft.com/)から利用できる、Fasttrack のオンボードウィザードを使用して、この作業を自分で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-148">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="15d8c-149">独自の計画を行っている場合や、FastTrack と連携している場合は、ネットワークと組織が Exchange Online の準備ができているかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-149">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="15d8c-150">Exchange の追加のトラフィックに対するパフォーマンスを最大化するために、インターネット帯域幅、スループット、トラフィック遅延に特に注意を向けることで、基礎インフラストラクチャのネットワークの終了条件を満たすことは特に重要です。オンラインベースの電子メールと添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="15d8c-150">It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="15d8c-151">これらのリソースを使用して、Exchange Online ロールアウトの技術的な側面を準備します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-151">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="15d8c-152">複数のメール アカウントを Office 365 に移行する方法</span><span class="sxs-lookup"><span data-stu-id="15d8c-152">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- <span data-ttu-id="15d8c-153">[Exchange Online でのコラボレーション](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-153">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="15d8c-154">[Exchange Online の受信者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-154">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="15d8c-155">Exchange Online のセキュリティをより深く理解するには、次のリソースを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-155">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="15d8c-156">[Exchange Online でのアクセス許可](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-156">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="15d8c-157">[Exchange Online のセキュリティとコンプライアンス](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-157">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="15d8c-158">[スパム対策とマルウェア対策の保護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-158">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="15d8c-159">次に、これらのリソースを使用して Exchange Online メールボックス管理について理解します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-159">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="15d8c-160">[Exchange Online でユーザーメールボックスを作成する](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-160">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="15d8c-161">[ユーザー メールボックスの管理](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-161">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="15d8c-162">配布グループを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="15d8c-162">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="15d8c-163">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-163">Result</span></span>

<span data-ttu-id="15d8c-164">メールボックスの移行、セキュリティ、および管理について理解し、組織内の選択したグループへの Exchange Online のロールアウトを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="15d8c-164">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="15d8c-165">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="15d8c-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="15d8c-p108">中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="15d8c-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="15d8c-168">IT パイロットの参加者が実習できる Exchange Online ビジネスシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-168">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="15d8c-169">パイロット参加者に Office 365 のライセンスを付与し、オンプレミスのメールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-169">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="15d8c-170">パイロット参加者に、Exchange Online の電子メール、スケジュール、およびその他の機能をテストするための一連の実習を用意します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-170">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="15d8c-171">変更管理戦略を決定し、組織全体にわたるユーザーの Exchange Online の導入を促進するための資料を作成します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-171">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online.</span></span> <span data-ttu-id="15d8c-172">変更管理資料には、電子メールアナウンステキスト、内部トレーニングプラン、hallway ポスター、プレゼンテーションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-172">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="15d8c-173">これらの資料は、組織に Exchange Online に関する情報を提供し、認識を向上させ、使用を推進することの目標を達成したものとします。</span><span class="sxs-lookup"><span data-stu-id="15d8c-173">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="15d8c-174">いくつかのアイデアについては、 [Microsoft Teams の変更管理戦略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-174">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="15d8c-175">IT パイロット参加者に、エクスペリエンスに基づいて変更管理資料をレビューしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-175">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="15d8c-176">また、Exchange Online の利点について説明するためのヒントや、コミュニケーションやスケジュール設定に使用する方法についてのヒントを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-176">They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="15d8c-177">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-177">Result</span></span>

<span data-ttu-id="15d8c-178">Exchange Online IT パイロットは完成し、最初の変更管理資料が開発、レビュー、および調整されています。</span><span class="sxs-lookup"><span data-stu-id="15d8c-178">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="15d8c-179">手順 3: ビジネス グループへロールアウトする</span><span class="sxs-lookup"><span data-stu-id="15d8c-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="15d8c-180">IT パイロットを完了した後、組織内のビジネスグループまたは部署に Exchange Online をロールアウトします。</span><span class="sxs-lookup"><span data-stu-id="15d8c-180">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="15d8c-181">組織が Exchange Server などの社内電子メールサービスを使用している場合、このロールアウトはメールボックスの移行で構成されます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-181">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="15d8c-182">このロールアウトには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-182">This rollout should include:</span></span>

- <span data-ttu-id="15d8c-183">ビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。</span><span class="sxs-lookup"><span data-stu-id="15d8c-183">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="15d8c-184">部署や作業またはプロジェクトチームのための、Exchange Online の使用状況についての要望とタイムラインをユーザーに通知するアナウンスアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="15d8c-184">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="15d8c-185">ビジネスグループのメンバーの社内メールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-185">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="15d8c-186">Exchange Online でユーザートレーニングを実施するか、Exchange Online を紹介するリソースへのリンクを提供し、その使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-186">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="15d8c-187">ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。</span><span class="sxs-lookup"><span data-stu-id="15d8c-187">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="15d8c-188">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="15d8c-188">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="15d8c-189">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-189">Result</span></span>

<span data-ttu-id="15d8c-190">ビジネスグループは Exchange Online で稼働しており、変更管理資料のテストと調整が行われています。</span><span class="sxs-lookup"><span data-stu-id="15d8c-190">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="15d8c-191">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="15d8c-191">Phase 3: Drive value</span></span>

<span data-ttu-id="15d8c-192">このフェーズでは、Exchange Online のロールアウトを完了し、ユーザーによるメリットの実現を支援するためにユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="15d8c-192">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="15d8c-193">手順 1: 組織の他の部分に Exchange Online をロールアウトする</span><span class="sxs-lookup"><span data-stu-id="15d8c-193">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="15d8c-194">組織の残りの部分へのロールアウトには、以下を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-194">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="15d8c-195">個別のビジネスグループ内の Exchange Online の主要なビジネスシナリオの識別。</span><span class="sxs-lookup"><span data-stu-id="15d8c-195">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="15d8c-196">Exchange Online の使用状況に関する期待値とタイムラインを組織に通知するために、改訂の変更管理資料をアナウンス活動に使用します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="15d8c-197">組織の残りの部分のメールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-197">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="15d8c-198">Exchange Online でユーザートレーニングを実施するか、Exchange Online を紹介するリソースへのリンクとその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-198">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="15d8c-p112">組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="15d8c-202">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-202">Result</span></span>

<span data-ttu-id="15d8c-203">組織が稼働しており、ユーザーが Exchange Online を使用できるようにするために、変更管理戦略が実施されています。</span><span class="sxs-lookup"><span data-stu-id="15d8c-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="15d8c-204">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="15d8c-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="15d8c-205">Exchange Online を組織全体にロールアウトした後、次のことを行うために、変更管理戦略を引き続き採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-205">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="15d8c-206">リーダーシップを発揮して、個々の、および短期間のコミュニケーションとスケジューリングのための主要なツールとして Exchange Online を促進します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-206">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="15d8c-207">ビジネスグループ、部門、作業、およびプロジェクトチームのコミュニケーション、予定表作成、グループ作業に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15d8c-207">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="15d8c-208">推奨されるアクティビティの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="15d8c-209">「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="15d8c-p113">「[Office 365 アクティビティ レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="15d8c-212">Exchange Online でのエクスペリエンスに関する問題とフィードバックについて、フィードバック会場 (中央チームのチームまたは Yammer のパブリックチャネル) を監視します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-212">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="15d8c-213">問題の解決を防ぎ、ロールアウトのサポートをデモンストレーションできるように、質疑応答します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-213">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="15d8c-214">各ビジネスグループのチャンピオンを特定して育成し、Exchange Online を使用してその業績とベストプラクティスを強調します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-214">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online.</span></span> <span data-ttu-id="15d8c-215">プロジェクトの成功と導入を示すために、その成功を組織に反映します。</span><span class="sxs-lookup"><span data-stu-id="15d8c-215">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="15d8c-216">ビジネスグループ内の技術リーダーによる裏書は、リーダーとピアに大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="15d8c-216">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="15d8c-217">結果</span><span class="sxs-lookup"><span data-stu-id="15d8c-217">Result</span></span>

<span data-ttu-id="15d8c-218">組織は、プライマリ個人と小規模なグループの短時間のコミュニケーションとスケジューリングツールとして Exchange Online を採用しています。</span><span class="sxs-lookup"><span data-stu-id="15d8c-218">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="15d8c-219">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="15d8c-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="15d8c-220">Microsoft の内部をピークし、exchange Online に移行し、Exchange Online Protection を使用してサイバー攻撃から保護する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-220">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="15d8c-221">Microsoft では 150,000 のメールボックスを Exchange Online に移行</span><span class="sxs-lookup"><span data-stu-id="15d8c-221">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="15d8c-222">Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する</span><span class="sxs-lookup"><span data-stu-id="15d8c-222">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="15d8c-223">Microsoft の Office 365 を使用したフィッシング阻止の試み</span><span class="sxs-lookup"><span data-stu-id="15d8c-223">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="15d8c-224">次のステップ</span><span class="sxs-lookup"><span data-stu-id="15d8c-224">Next steps</span></span>

<span data-ttu-id="15d8c-225">Exchange Online の継続的なメンテナンスについては、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d8c-225">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="15d8c-226">[Exchange Online の Exchange 管理センター](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-226">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="15d8c-227">[Exchange Online での監視、レポート、メッセージ追跡](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-227">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="15d8c-228">[Exchange Online の電子メールのバックアップ](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="15d8c-228">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
