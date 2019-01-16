---
title: Microsoft 365 Enterprise 用 Exchange Online を展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: 計画、展開、および Exchange Online の値を Microsoft 365 エンタープライズで、組織全体で推進のプロセスをステップ実行します。
ms.openlocfilehash: aafa1b28546eb77938bb3e4a5ebe9ccd60b9a60b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869621"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="0f264-103">Microsoft 365 Enterprise 用 Exchange Online を展開する</span><span class="sxs-lookup"><span data-stu-id="0f264-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0f264-p101">Exchange Online は、電子メールの主要なクラウド サービスと、そのことを予定表作成、リアルタイム チャットを必要としない、またはドキュメントのストレージを集中管理するための方法で共同作業ユーザー。Exchange オンライン個々 および小さいグループの短時間通信とスケジュール設定の操作方法は、Microsoft 365 エンタープライズのチームワークの値の組み込みの重要な要素です。Exchange のオンラインより多くを達成し、どのようなデバイスであっても、よく知られている Outlook アプリケーションをより効率的に作業できます。</span><span class="sxs-lookup"><span data-stu-id="0f264-p101">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage. Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise. Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="0f264-p102">Exchange オンラインも、高度なメールボックスを保護するため、マルウェア対策とスパム対策フィルターを含むセキュリティ機能とデータ損失の防止の機能には、ユーザーが誤って許可されていないユーザーに機密情報を送信することを防ぐ。Exchange オンラインのセキュリティは、Microsoft 365 エンタープライズのインテリジェントなセキュリティ値の重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="0f264-p102">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people. Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="0f264-109">Exchange Online を使用する場合は、 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-109">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="0f264-110">次の段階と手順に従って、一連のプログレッシブの展開を Exchange Online 組織、組織では、契約時に Exchange Online のロールを予見し、Exchange Online の使用を促進するプロセスとは、エンド ・ ユーザの値です。</span><span class="sxs-lookup"><span data-stu-id="0f264-110">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="0f264-111">展開手順は、Microsoft 365 エンタープライズ基盤インフラストラクチャの[フェーズ 2-識別情報](identity-infrastructure.md)を完了した後にのみ従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f264-111">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="0f264-112">フェーズ 1: 想定</span><span class="sxs-lookup"><span data-stu-id="0f264-112">Phase 1: Envision</span></span>

<span data-ttu-id="0f264-113">このフェーズでは、「Exchange Online を展開するため人々 を収集し、、どのように組織が Exchange Online を使用、ビジネス ニーズに対応するを決定します。</span><span class="sxs-lookup"><span data-stu-id="0f264-113">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="0f264-114">手順 1: Exchange のオンライン展開メンバーを収集します。</span><span class="sxs-lookup"><span data-stu-id="0f264-114">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="0f264-p103">[フェーズ 2-識別情報](identity-infrastructure.md)を Microsoft 365 エンタープライズ基盤インフラストラクチャの上に Exchange Online の展開を成功させる、入力とフィードバックのための適切な担当者を取得する必要があります。主要な人物には、ビジネスの意思決定者、設計者と実装者、エンドユーザーの支持者などの IT スタッフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f264-p103">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="0f264-117">これら 3 つのグループは、オンラインの Exchange の展開にはでのビジネス ・ ニーズ、メールボックスの移行、セキュリティの技術的な側面と結果はである一般的なユーザーが使用するものに対応するための考慮事項が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f264-117">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="0f264-118">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-118">Result</span></span>

<span data-ttu-id="0f264-119">組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="0f264-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="0f264-120">手順 2: を確認し、Exchange のオンライン ビジネス シナリオでは、優先順位を</span><span class="sxs-lookup"><span data-stu-id="0f264-120">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="0f264-p104">Exchange Online はさまざまな目的で使用できます。目的のマップ、組織、ビジネス グループ、部門、または個々 の作業とプロジェクト チームの別のレベルでビジネス ニーズを把握する必要があります。個々 および小さいグループ、短時間通信とスケジューリング ニーズに対応する Exchange Online をターゲットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f264-p104">Exchange Online can be used for different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams. You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="0f264-p105">Exchange オンラインのメリットを確認する方法の 1 つは、個人、チーム、または v チームが今日では、相互作用し、通信、会議のスケジュール作成、および共同作業を簡単な方法を提供する適切なシナリオを検索し、方法を調べることです。[マイクロソフトのチーム](teams-workload.md)での共同作業シナリオでは、いくつかの方が適して可能性があることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-p105">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

<span data-ttu-id="0f264-126">Exchange Online を使用すると、Microsoft 365 Enterprise の次の戦略的なビジネス シナリオを実現可能にします:</span><span class="sxs-lookup"><span data-stu-id="0f264-126">Exchange Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="0f264-127">リアルタイムまたは好きな時間にドキュメント上で共同作業を行って、共同作成プロセスを簡略化します</span><span class="sxs-lookup"><span data-stu-id="0f264-127">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="0f264-128">プロジェクト、タスク、期限を管理して、ビジネス目標を達成します</span><span class="sxs-lookup"><span data-stu-id="0f264-128">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="0f264-129">業務の習慣を理解して、影響力を増します</span><span class="sxs-lookup"><span data-stu-id="0f264-129">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="0f264-130">チーム内でコミュニケーションを図って、最新の情報に精通し、意見を求め、団結力と考えの一致を高めます</span><span class="sxs-lookup"><span data-stu-id="0f264-130">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="0f264-131">組織内外でファイルを保存および共有して、組織の境界を越えてシームレスに作業を行います</span><span class="sxs-lookup"><span data-stu-id="0f264-131">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="0f264-132">柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます</span><span class="sxs-lookup"><span data-stu-id="0f264-132">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="0f264-133">情報を保護して、データ損失のリスクを軽減します</span><span class="sxs-lookup"><span data-stu-id="0f264-133">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="0f264-134">検出し、外部の脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="0f264-134">Detect and protect against external threats</span></span> 
- <span data-ttu-id="0f264-135">監視、レポート、および組織のセキュリティを提供するのには迅速に対応する利用状況を分析</span><span class="sxs-lookup"><span data-stu-id="0f264-135">Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="0f264-136">一般データ保護規則 (GDPR) に適合するように、強化されたプライバシーと法令遵守によって組織をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0f264-136">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="0f264-137">詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-137">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="result"></a><span data-ttu-id="0f264-138">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-138">Result</span></span>
<span data-ttu-id="0f264-139">通信、スケジュール、および共同作業を短時間で、組織のニーズに対応する Exchange Online のシナリオの一覧です。</span><span class="sxs-lookup"><span data-stu-id="0f264-139">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="0f264-140">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="0f264-140">Phase 2: Onboard</span></span>

<span data-ttu-id="0f264-141">このフェーズでは、オンラインの Exchange 展開の技術的な側面の計画し、ユーザーの選択したグループにロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="0f264-141">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="0f264-142">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="0f264-142">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="0f264-143">Exchange Online のメールボックスへのアクセスを保護するには、 [id とデバイスのアクセス ポリシー](identity-access-policies.md)と[アクセス ポリシーが Exchange Online をお勧め](secure-email-recommended-policies.md)するを構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f264-143">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="0f264-144">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="0f264-144">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="0f264-p106">技術的な計画を開始する前に、FastTrack を使用するかどうかを決定します。組織が接続クライアント数が 50 を超えるには、[対象となる計画](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合は、 [Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)、計画、展開、およびサービスの導入を進めることは追加コストなしで利用可能なを使用できます。または、 [FastTrack](https://fasttrack.microsoft.com/)から利用可能なは、Office 365 アカウントでサインインする fasttrack という契約時のウィザードを使用して自分でこの作業を完了できます。</span><span class="sxs-lookup"><span data-stu-id="0f264-p106">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="0f264-p107">独自の計画を実行する場合または FastTrack と共に、ネットワークおよび組織は、Exchange オンラインの準備ができたかどうかを決定する必要があります。インターネットの帯域幅、スループット、およびその他のトラフィックには、Exchange のパフォーマンスを最大化するトラフィックの遅延に注意して、基盤インフラストラクチャのネットワークの終了基準を満たしていることが特に重要です。オンライン ベースの電子メールと添付ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0f264-p107">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="0f264-150">オンラインの Exchange の展開の技術的な側面を準備するには、これらのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f264-150">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="0f264-151">複数のメール アカウントを Office 365 に移行する方法</span><span class="sxs-lookup"><span data-stu-id="0f264-151">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- <span data-ttu-id="0f264-152">[Office 365 のメール移行アドバイザー](https://portal.office.com/onboarding/mailsetupadvisor#/)(署名が必要、Office 365 サブスクリプションを)</span><span class="sxs-lookup"><span data-stu-id="0f264-152">[Office 365 mail migration advisor](https://portal.office.com/onboarding/mailsetupadvisor#/) (must be signed in to your Office 365 subscription)</span></span>
- <span data-ttu-id="0f264-153">[Exchange Online でのコラボレーション](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-153">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="0f264-154">[Exchange Online の受信者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-154">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="0f264-155">について理解を深める Exchange Online 内のセキュリティでは、次のリソースを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f264-155">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="0f264-156">[Exchange Online のアクセス許可](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-156">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="0f264-157">[Exchange Online のセキュリティとコンプライアンス](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-157">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="0f264-158">[スパム対策とマルウェア対策の保護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-158">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="0f264-159">次に、Exchange Online のメールボックスの管理を理解するのにはこれらのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f264-159">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="0f264-160">[Exchange Online でユーザーのメールボックスを作成します。](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-160">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="0f264-161">[ユーザー メールボックスの管理](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-161">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="0f264-162">配布グループの作成と管理</span><span class="sxs-lookup"><span data-stu-id="0f264-162">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="0f264-163">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-163">Result</span></span>

<span data-ttu-id="0f264-164">メールボックスの移行、セキュリティ、および管理を理解し、組織内の選択したグループに Exchange Online を展開を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="0f264-164">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="0f264-165">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="0f264-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="0f264-p108">中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="0f264-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="0f264-168">IT パイロット参加者の練習に使用できる Exchange オンラインのビジネス シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f264-168">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="0f264-169">パイロット参加者の Office 365 のライセンスを付与し、オンプレミスのメールボックスを Exchange Online に移行します。</span><span class="sxs-lookup"><span data-stu-id="0f264-169">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="0f264-170">パイロット参加者の Exchange Online の電子メール、スケジュール、およびその他の機能をテストするための演習のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="0f264-170">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="0f264-p109">変更管理戦略の決定し、オンラインの Exchange の組織全体のユーザーの採用を推進する資料を作成します。変更管理の資料には、電子メールのお知らせのテキスト、内部のトレーニング ・ プラン、廊下のポスター、およびプレゼンテーションを含めることができます。これらの資料は、Exchange オンラインおよび発生の認識と推進の使用率の目標とそのメリットについて、組織に通知されます。[マイクロソフトのチームの管理戦略を変更する](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)この資料は、いくつかのアイデアを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-p109">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage. See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="0f264-p110">IT パイロット参加者の経験に基づく変更の管理に関する資料を参照があります。最適な Exchange のオンラインの利点を説明する方法と通信し、スケジュール設定に使用する方法で、ベスト ・ プラクティスに関するヒントやアドバイスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0f264-p110">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="0f264-177">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-177">Result</span></span>

<span data-ttu-id="0f264-178">Exchange のオンライン IT パイロットが完了し、最初の変更の管理資料が開発、検討、および調整します。</span><span class="sxs-lookup"><span data-stu-id="0f264-178">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="0f264-179">手順 3: ビジネス グループへロールアウトする</span><span class="sxs-lookup"><span data-stu-id="0f264-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="0f264-p111">IT パイロットを完了すると、ビジネス グループまたは組織内の部門 Exchange Online を展開します。組織は、Exchange Server などのオンプレミス電子メール サービスで使用されている場合はメールボックスの移行のこのロールアウトで構成されます。このロールアウトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f264-p111">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization. If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration. This rollout should include:</span></span>

- <span data-ttu-id="0f264-183">ビジネス グループ内で Exchange のオンラインの主要なビジネス シナリオの id です。</span><span class="sxs-lookup"><span data-stu-id="0f264-183">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="0f264-184">期待し、部署やチームの作業やプロジェクトの Exchange Online を使用するためのタイムラインのユーザーに通知する活動をお知らせします。</span><span class="sxs-lookup"><span data-stu-id="0f264-184">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="0f264-185">Exchange Online には、ビジネス グループのメンバーのオンプレミスのメールボックスの移行。</span><span class="sxs-lookup"><span data-stu-id="0f264-185">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="0f264-186">Exchange Online とその使用方法を紹介するリソースを Exchange Online またはリンク上のユーザーのトレーニングを提供しています。</span><span class="sxs-lookup"><span data-stu-id="0f264-186">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="0f264-187">ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。</span><span class="sxs-lookup"><span data-stu-id="0f264-187">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="0f264-188">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="0f264-188">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="0f264-189">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-189">Result</span></span>

<span data-ttu-id="0f264-190">ビジネス グループとは、Exchange オンラインで実行して、変更管理資料がテストされ洗練されています。</span><span class="sxs-lookup"><span data-stu-id="0f264-190">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="0f264-191">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="0f264-191">Phase 3: Drive value</span></span>

<span data-ttu-id="0f264-192">このフェーズでは、オンラインの Exchange の展開を完了し、そのメリットを実現するためにユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0f264-192">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="0f264-193">手順 1: 展開 Exchange Online 組織の残りの部分に</span><span class="sxs-lookup"><span data-stu-id="0f264-193">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="0f264-194">組織の残りの部分へのロールアウトには、以下を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f264-194">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="0f264-195">個別のビジネス グループ内で Exchange のオンラインの主要なビジネス シナリオの id です。</span><span class="sxs-lookup"><span data-stu-id="0f264-195">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="0f264-196">期待の組織に通知するお知らせの活動についての高度な変更管理の資料と Exchange Online を使用するためのタイムラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f264-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="0f264-197">オンラインの Exchange 組織の残りのメールボックスの移行。</span><span class="sxs-lookup"><span data-stu-id="0f264-197">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="0f264-198">ユーザーのトレーニングを提供することをオンラインで交換するか Exchange Online とその使用方法を紹介するリソースへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="0f264-198">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="0f264-p112">組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="0f264-202">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-202">Result</span></span>

<span data-ttu-id="0f264-203">組織は、通知、トレーニング、および Exchange Online を使用するユーザーを有効にするのには、実行し、変更管理戦略です。</span><span class="sxs-lookup"><span data-stu-id="0f264-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="0f264-204">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="0f264-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="0f264-205">組織全体には、Exchange Online を展開後、に、変更管理の戦略を採用する続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f264-205">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="0f264-206">個人および短時間の通信のための主要なツールとして Exchange Online を昇格させる、リーダーシップがあり、スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f264-206">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="0f264-207">プロジェクト チームのコミュニケーション、予定表機能、およびコラボレーションやビジネス グループ、部門、作業中、使用する個人を推奨します。</span><span class="sxs-lookup"><span data-stu-id="0f264-207">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="0f264-208">推奨されるアクティビティの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f264-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="0f264-209">「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="0f264-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="0f264-p113">「[Office 365 アクティビティ レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0f264-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="0f264-p114">フィードバックの会場 (中央チームのチームまたは Yammer にパブリック チャネル) の問題および Exchange のオンラインでの経験についてのユーザーからのフィードバックを監視します。個人の不満を防止し、展開のサポートを示すことができます速やかに疑問や問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="0f264-p114">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="0f264-p115">識別し、各ビジネス グループのエキスパートの進展しの実績とベスト ・ プラクティスが Exchange Online を使用して強調表示します。プロジェクトの成功と採用を表示するのには組織をその成功を反映します。裏書ビジネス グループ内の技術のリーダーでは、リーダーとのピアの上に大きな影響を与えることのできます。</span><span class="sxs-lookup"><span data-stu-id="0f264-p115">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="0f264-217">結果</span><span class="sxs-lookup"><span data-stu-id="0f264-217">Result</span></span>

<span data-ttu-id="0f264-218">組織は、個人および小グループの主な短時間の通信に、スケジュール作成ツールとして Exchange オンライン採用しています。</span><span class="sxs-lookup"><span data-stu-id="0f264-218">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="0f264-219">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="0f264-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0f264-220">マイクロソフトの内部を見るし、会社が Exchange Online に移行し、サイバー攻撃から保護するために Exchange のオンライン保護を使用する方法を学ぶを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-220">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="0f264-221">Microsoft では 150,000 のメールボックスを Exchange Online に移行</span><span class="sxs-lookup"><span data-stu-id="0f264-221">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="0f264-222">Microsoft は脅威からの保護、脅威の検出、脅威への対応に脅威インテリジェンスを使用する</span><span class="sxs-lookup"><span data-stu-id="0f264-222">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="0f264-223">Microsoft の Office 365 を使用したフィッシング阻止の試み</span><span class="sxs-lookup"><span data-stu-id="0f264-223">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="0f264-224">次の手順</span><span class="sxs-lookup"><span data-stu-id="0f264-224">Next steps</span></span>

<span data-ttu-id="0f264-225">Exchange オンラインの継続的なメンテナンスのため、これらのリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f264-225">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="0f264-226">[Exchange Online の Exchange 管理センター](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-226">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="0f264-227">[Exchange Online での監視、レポート、メッセージ追跡](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-227">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="0f264-228">[Exchange Online での電子メールのバックアップ](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f264-228">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
