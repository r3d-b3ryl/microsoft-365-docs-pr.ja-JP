---
title: SharePoint Online と OneDrive for Business を Microsoft 365 Enterprise 向けに展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/28/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft 365 Enterprise の SharePoint Online を計画、ロールアウトするプロセス、および SharePoint Online の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 9ceadbb0268d3a2aa82309d01933a8bd05429188
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981768"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a><span data-ttu-id="5417d-103">SharePoint Online と OneDrive for Business を Microsoft 365 Enterprise 向けに展開する</span><span class="sxs-lookup"><span data-stu-id="5417d-103">Deploy SharePoint Online and OneDrive for Business for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5417d-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="5417d-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5417d-105">SharePoint Online と Microsoft Teams は、ファイルの保存と共有、コンテンツ管理、コラボレーションの方法を提供するもので、Microsoft 365 Enterprise のチームワーク用ビルドの価値を引き出す重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="5417d-105">SharePoint Online and Microsoft Teams is how you do file storage and sharing, content management, and collaboration and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="5417d-p101">SharePoint Online には、アクセスの制御、アクセス許可、移動中および静的データの暗号化を含む、高度なセキュリティ機能も備わっています。SharePoint Online のセキュリティは、Microsoft 365 Enterprise のインテリジェント セキュリティの価値を引き出す重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="5417d-p101">SharePoint Online also has advanced security capabilities including access control and permissions and encryption in flight and at rest. SharePoint Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5417d-108">SharePoint Online を初めて使用する方は、「[SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software)」と「[SharePoint を使い始める](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-108">If you are brand new to SharePoint Online, see [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) and [Get Started with SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).</span></span>

<span data-ttu-id="5417d-109">次に示す各フェーズと手順では、組織における SharePoint Online の役割を想定し、段階的な一連のロールアウトにより組織の研修を行い、それらの使用とエンドユーザーに対する価値を促進するプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="5417d-109">The following phases and steps guide you through the process of envisioning the role of SharePoint Online in your organization, onboarding your organization through a series of progressive rollouts, and driving usage its value to your end users.</span></span> <span data-ttu-id="5417d-110">まず始める前に、SharePoint Online サイトに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-foundation-infrastructure.md)のフェーズが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5417d-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your SharePoint Online sites have the security capabilities you need.</span></span> 

<span data-ttu-id="5417d-111">OneDrive for Business を Microsoft 365 Enterprise 向けに展開する方法については、[エンタープライズ向けの OneDrive ガイド](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-111">To deploy OneDrive for Business for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="5417d-112">フェーズ 1: 想定</span><span class="sxs-lookup"><span data-stu-id="5417d-112">Phase 1: Envision</span></span>
<span data-ttu-id="5417d-113">このフェーズでは、SharePoint Online の展開にあたって関係者を招集し、組織でビジネス ニーズに対応するため、どのようにそれらを利用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5417d-113">In this phase, you gather the people for your SharePoint Online deployment and determine how your organization will use them to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a><span data-ttu-id="5417d-114">手順 1: SharePoint Online の展開メンバーを収集する</span><span class="sxs-lookup"><span data-stu-id="5417d-114">Step 1: Gather your SharePoint Online deployment members</span></span>

<span data-ttu-id="5417d-p103">[Microsoft 365 Enterprise の基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に SharePoint Online を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。</span><span class="sxs-lookup"><span data-stu-id="5417d-p103">For a successful deployment of SharePoint Online on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="5417d-117">この 3 つのグループを招集することにより、展開には、ビジネス ニーズを反映した考慮事項と、フォルダーとドキュメントの移行およびセキュリティの技術的側面が反映され、結果は標準的なユーザーが使用するものになります。</span><span class="sxs-lookup"><span data-stu-id="5417d-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="5417d-118">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-118">Result</span></span>

<span data-ttu-id="5417d-119">組織の事業、技術、エンドユーザーの各側面を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="5417d-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a><span data-ttu-id="5417d-120">手順 2: SharePoint Online のビジネス シナリオを決定し、優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="5417d-120">Step 2: Determine and prioritize your SharePoint Online business scenarios</span></span>

<span data-ttu-id="5417d-p104">SharePoint Online はさまざまな目的で使用できます。どの目的がビジネス ニーズに当てはまるかを確認する必要があります。SharePoint Online のターゲットとして、チーム、事業部、または組織全体のコラボレーションのニーズに対応する、ドキュメントの保存と共有、コンテンツ管理、コラボレーションを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5417d-p104">SharePoint Online can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint Online to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="5417d-124">[SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) のシナリオと機能の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-124">See the list of scenarios and capabilities at [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).</span></span>

<span data-ttu-id="5417d-125">ビジネスの柱となる次の要素を、組織のニーズに対応させることができます。</span><span class="sxs-lookup"><span data-stu-id="5417d-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="5417d-126">共有と共同作業</span><span class="sxs-lookup"><span data-stu-id="5417d-126">Share and Work Together</span></span> | <span data-ttu-id="5417d-127">チーム サイトの活用、コラボレーション サイト、および同期。</span><span class="sxs-lookup"><span data-stu-id="5417d-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="5417d-128">情報伝達と連携</span><span class="sxs-lookup"><span data-stu-id="5417d-128">Inform and Engage</span></span> | <span data-ttu-id="5417d-129">今後入ってくる情報。</span><span class="sxs-lookup"><span data-stu-id="5417d-129">Information coming in the future.</span></span> |
| <span data-ttu-id="5417d-130">変換</span><span class="sxs-lookup"><span data-stu-id="5417d-130">Transform</span></span> | <span data-ttu-id="5417d-131">フローを使って、ストアまたはワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="5417d-131">Uses Flow to create a store or workflow.</span></span> |
| <span data-ttu-id="5417d-132">集合的な知識の利用</span><span class="sxs-lookup"><span data-stu-id="5417d-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="5417d-133">検索を使用して、組織内で目的とする結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="5417d-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="5417d-134">保護</span><span class="sxs-lookup"><span data-stu-id="5417d-134">Protect</span></span> | <span data-ttu-id="5417d-135">組織がセキュリティで保護されており、適切なコンプライアンスを達成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5417d-135">Ensures your organization is secured and has the correct compliance.</span></span> |
| <span data-ttu-id="5417d-136">外部/開発</span><span class="sxs-lookup"><span data-stu-id="5417d-136">External/Develop</span></span> | <span data-ttu-id="5417d-137">開発組織により、SharePoint Framework を使用してソリューションやアプリをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="5417d-137">Lets your organization develop customize solutions and apps by using the SharePoint Framework.</span></span> |
|||

<span data-ttu-id="5417d-138">各自のニーズに合わせて SharePoint Online を構成する方法に関するリソースについては、「[SharePoint Online の管理](https://docs.microsoft.com/sharepoint/sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-138">See [SharePoint Online admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint Online for your needs.</span></span>

<span data-ttu-id="5417d-p105">SharePoint Online の利点を調べる 1 つの方法は、個人、チーム、部門、または組織全体が現在、どのようにやり取りしているかを調べたうえで、ファイルの保存と共有の共同作業をより簡単に行う適切なシナリオを探すことです。シナリオによっては、[Microsoft Teams](teams-workload.md) がより良い選択になり得ることを念頭においてください。</span><span class="sxs-lookup"><span data-stu-id="5417d-p105">One way to see the benefits of SharePoint Online is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a><span data-ttu-id="5417d-141">厳しく規制されたデータに対応した SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="5417d-141">SharePoint Online site for highly regulated data</span></span>

<span data-ttu-id="5417d-p106">厳しく規制されたデータとは、地域の規制の対象になっているデータや、組織にとって最も重要なデータ (営業秘密、財務や人事の情報、組織戦略など) のことです。SharePoint Online サイトは、この種のデータのアクセス制限、データ分類、データ損失保護、暗号化に対応するように構成できます。詳細については、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a SharePoint Online site for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="5417d-145">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-145">Result</span></span>
<span data-ttu-id="5417d-146">ドキュメントの保存と共有、コンテンツ管理、コラボレーションに関する組織のニーズに対応する SharePoint Online のシナリオの一覧。</span><span class="sxs-lookup"><span data-stu-id="5417d-146">A list of SharePoint Online scenarios that address your organization’s needs for document storage and sharing, content management, and collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="5417d-147">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="5417d-147">Phase 2: Onboard</span></span>

<span data-ttu-id="5417d-148">このフェーズでは、SharePoint Online の展開の技術的な側面を計画した後、選択したユーザー グループへのロールアウトを開始します。</span><span class="sxs-lookup"><span data-stu-id="5417d-148">In this phase, you plan for the technical aspects of a SharePoint Online deployment and start rolling then out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="5417d-149">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="5417d-149">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="5417d-150">SharePoint Online サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint Online アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5417d-150">To protect access to SharePoint Online sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="5417d-151">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="5417d-151">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="5417d-p107">技術計画を開始する前に、FastTrack を使用するかどうかを決定します。組織のシート数が 50 を超えており、組織が[対象となるプラン](https://technet.microsoft.com/library/dn783224.aspx)に参加している場合、無料で提供されている FastTrack の特典を使用して、計画、展開、サービス導入を順に実施できます。あるいは、FastTrack Onboarding Wizard を使用してこの作業を各自で実施することもできます。FastTrack Onboarding Wizard は、Office 365 アカウントでサインインした後、[FastTrack](https://fasttrack.microsoft.com/) から利用できます。</span><span class="sxs-lookup"><span data-stu-id="5417d-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use FastTrack benefits, available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="5417d-p108">各自で計画を策定している場合、または FastTrack を使用している場合には、ネットワークと組織が SharePoint Online を導入できる状態にあるかどうかを判断する必要があります。特に、基礎インフラストラクチャのネットワークの終了条件を満たしており、SharePoint Online ベースのドキュメントのための追加トラフィックのパフォーマンスを最大限に引き出すため、インターネット帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="5417d-p108">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint Online-based documents.</span></span>

<span data-ttu-id="5417d-157">SharePoint Online のロールアウトの技術的な側面に備えるには、以下のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="5417d-157">Use these resources to prepare for the technical aspects of a SharePoint Online rollout:</span></span> 

- [<span data-ttu-id="5417d-158">SharePoint Online の計画ガイド</span><span class="sxs-lookup"><span data-stu-id="5417d-158">SharePoint Online Planning Guide</span></span>](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [<span data-ttu-id="5417d-159">SharePoint Online に移行する</span><span class="sxs-lookup"><span data-stu-id="5417d-159">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

<span data-ttu-id="5417d-160">SharePoint Online でのセキュリティの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-160">For a better understanding of security in SharePoint Online, review the following resources:</span></span>

-   [<span data-ttu-id="5417d-161">SharePoint Online と OneDrive がクラウド内のデータを保護する方法</span><span class="sxs-lookup"><span data-stu-id="5417d-161">How SharePoint Online and OneDrive safeguard your data in the cloud</span></span>](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [<span data-ttu-id="5417d-162">OneDrive for Business および SharePoint Online におけるデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="5417d-162">Data Encryption in OneDrive for Business and SharePoint Online</span></span>](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a><span data-ttu-id="5417d-163">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-163">Result</span></span>

<span data-ttu-id="5417d-164">SharePoint Online サイトとオンプレミス フォルダーおよびドキュメントの移行とセキュリティについて理解し、組織内の選択したグループへの SharePoint Online のロールアウトを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5417d-164">You understand SharePoint Online sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="5417d-165">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="5417d-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="5417d-p109">中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="5417d-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="5417d-168">IT パイロット参加者の練習に使用できる SharePoint Online のビジネス シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="5417d-168">Choose a SharePoint Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="5417d-169">パイロット参加者に、SharePoint Online ドキュメントの保存/共有/コラボレーション、チーム ベースのスケジューリング、その他の能力をテストするための一連の演習を実施します。</span><span class="sxs-lookup"><span data-stu-id="5417d-169">Give your pilot participants a set of exercises to test SharePoint Online document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="5417d-p110">変更管理戦略を決定し、組織全体のユーザーによる SharePoint Online の受け入れを促進するための資料を作成します。変更管理資料には、電子メールの発表文、社内トレーニング計画、通路用ポスター、プレゼンテーションなどが含まれます。これらの資料は、SharePoint Online に対する関心を高め、利用を促進することを目標とし、組織全体に Team とそのメリットを伝達します。いくつかのアイディアについては、[Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) の変更管理戦略の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-p110">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about SharePoint Online and its benefits with the goals of raising awareness and driving usage. See the change management strategy for [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="5417d-p111">IT パイロットの参加者に、各自の経験に基づく変更管理の資料のレビューを依頼します。参加者から、ベスト プラクティスに関するヒントや、SharePoint Online のメリットを説明する最適な方法、およびコミュニケーションとスケジューリングに SharePoint Online を使用する方法に関するアドバイスを得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5417d-p111">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of SharePoint Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="5417d-176">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-176">Result</span></span>

<span data-ttu-id="5417d-177">SharePoint Online の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。</span><span class="sxs-lookup"><span data-stu-id="5417d-177">Your SharePoint Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="5417d-178">手順 3: ビジネス グループへロールアウトする</span><span class="sxs-lookup"><span data-stu-id="5417d-178">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="5417d-p112">IT パイロットの完了後に、SharePoint Online を組織内のビジネス グループまたは部門にロールアウトします。このロールアウトでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="5417d-p112">After completing your IT pilot, roll out SharePoint Online to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="5417d-181">ビジネス グループにおける SharePoint Online の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="5417d-181">Identification of key business scenarios for SharePoint Online within the business group.</span></span>
- <span data-ttu-id="5417d-182">部門、作業チーム、プロジェクト チームにおける SharePoint Online の用途の想定事項とタイムラインをユーザーに伝達する広報活動。</span><span class="sxs-lookup"><span data-stu-id="5417d-182">Announcement activities to inform users of the expectations and timelines for SharePoint Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="5417d-183">ビジネス グループのメンバーの、オンプレミスのフォルダーとドキュメントの SharePoint Online への移行。</span><span class="sxs-lookup"><span data-stu-id="5417d-183">Migration of on-premises folders and documents of your business group members to SharePoint Online.</span></span>
- <span data-ttu-id="5417d-p113">ユーザー トレーニングの実施、または SharePoint Online とその使用方法を紹介するリソースへのリンクの提供。[SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) のビデオ トレーニングを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-p113">Delivering user training or links to resources to introduce SharePoint Online and how to use it. See [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="5417d-186">ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。</span><span class="sxs-lookup"><span data-stu-id="5417d-186">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="5417d-187">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="5417d-187">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="5417d-188">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-188">Result</span></span>

<span data-ttu-id="5417d-189">ビジネス グループの 1 つは SharePoint Online を運用しており、変更管理資料のテストと調整が完了しています。</span><span class="sxs-lookup"><span data-stu-id="5417d-189">A business group is up and running with SharePoint Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="5417d-190">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="5417d-190">Phase 3: Drive value</span></span>

<span data-ttu-id="5417d-191">このフェーズでは、SharePoint Online のロールアウトを完了し、そのメリットの実現を支援するためにユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5417d-191">In this phase, you complete the rollout of SharePoint Online support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="5417d-192">手順 1: 組織の他の部分にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="5417d-192">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="5417d-193">組織の残りの部分へのロールアウトには、以下を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5417d-193">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="5417d-194">別のビジネス グループにおける SharePoint Online の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="5417d-194">Identification of key business scenarios for SharePoint Online Online within separate business groups.</span></span>
- <span data-ttu-id="5417d-195">使用上の想定事項とタイムラインを組織に伝達する広報活動での、調整した変更管理資料の使用。</span><span class="sxs-lookup"><span data-stu-id="5417d-195">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="5417d-196">組織の残りの部分のフォルダーとドキュメントの、SharePoint Online への移行。</span><span class="sxs-lookup"><span data-stu-id="5417d-196">Migration of folders and documents for the rest of your organization to SharePoint Online.</span></span>
- <span data-ttu-id="5417d-197">ユーザー トレーニングの実施、または SharePoint Online とその使用方法を紹介するリソースへのリンクの提供。</span><span class="sxs-lookup"><span data-stu-id="5417d-197">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span>
- <span data-ttu-id="5417d-p114">組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="5417d-201">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-201">Result</span></span>
<span data-ttu-id="5417d-202">組織は SharePoint Online を運用しており、SharePoint Online の使用を開始するための情報を伝達し、トレーニングを実施し、ユーザーが使用できるようにする変更管理戦略を実施しています。</span><span class="sxs-lookup"><span data-stu-id="5417d-202">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="5417d-203">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="5417d-203">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="5417d-204">組織全体にロールアウトした後、次の目的で変更管理戦略を引き続き採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5417d-204">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="5417d-205">指導力を発揮して、SharePoint Online をドキュメントの保存と共有、チーム、部署、または組織全体のコラボレーションのための主要なツールとして推進します。</span><span class="sxs-lookup"><span data-stu-id="5417d-205">Have your leadership promote SharePoint Online as the primary tool for document storage and sharing and team, division, or organization-wide collaboration.</span></span>
- <span data-ttu-id="5417d-206">ビジネス グループ、部門、作業チーム、プロジェクト チームでのコラボレーションおよび予定管理にそれを使用するよう、各従業員を促します。</span><span class="sxs-lookup"><span data-stu-id="5417d-206">Encourage individuals to use it for business group, departmental, work, and project team collaboration and calendaring.</span></span>

<span data-ttu-id="5417d-207">推奨されるアクティビティの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5417d-207">Here are some suggested activities:</span></span>

- <span data-ttu-id="5417d-208">「[Office 365 導入ガイド](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="5417d-208">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="5417d-p115">「[Office 365 アクティビティ レポート](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5417d-p115">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="5417d-p116">フィードバック機能 (中央チームまたは Yammer のパブリック チャネル) を監視し、各メンバーからの SharePoint Online を使用したうえでの問題の指摘やフィードバックがないか確認します。質問や問題には可能な限り迅速に対応してメンバーが不満を抱えるのを避け、ロールアウトをサポートすることを示します。</span><span class="sxs-lookup"><span data-stu-id="5417d-p116">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="5417d-p117">各ビジネス グループのチャンピオンを特定して育成し、SharePoint Online を使用することによって達成できた内容やベスト プラクティスを強調します。チャンピオンの成功事例を組織に反映し、プロジェクトの成功と導入を紹介します。ビジネス グループ内の技術リーダーからの支持は、他のリーダーや同僚に大きな影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="5417d-p117">Identify and nurture champions in each business group and highlight their accomplishments and best practices by using SharePoint Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="5417d-216">結果</span><span class="sxs-lookup"><span data-stu-id="5417d-216">Result</span></span>

<span data-ttu-id="5417d-217">組織は、SharePoint Online をドキュメントの保存とコラボレーションをサポートするサービスとして採用しています。</span><span class="sxs-lookup"><span data-stu-id="5417d-217">Your organization has adopted SharePoint Online as a service to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="5417d-218">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="5417d-218">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5417d-219">Microsoft が実施した SharePoint Online の展開方法についての詳しい説明は、「[SharePoint からクラウドへ: Microsoft が実施した移行方法](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-219">To peek inside Microsoft and learn how the company deployed SharePoint Online, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5417d-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="5417d-220">Next steps</span></span>

<span data-ttu-id="5417d-221">SharePoint Online の継続的なメンテナンスについては、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5417d-221">See these resources for the ongoing maintenance of SharePoint Online:</span></span> 

- [<span data-ttu-id="5417d-222">SharePoint でのアクセス許可レベルについて</span><span class="sxs-lookup"><span data-stu-id="5417d-222">Understanding permission levels in SharePoint</span></span>](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [<span data-ttu-id="5417d-223">SharePoint サイト権限をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="5417d-223">Customize SharePoint site permissions</span></span>](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [<span data-ttu-id="5417d-224">SharePoint Online の外部共有をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="5417d-224">Turn external sharing on or off for SharePoint Online</span></span>](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [<span data-ttu-id="5417d-225">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="5417d-225">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

