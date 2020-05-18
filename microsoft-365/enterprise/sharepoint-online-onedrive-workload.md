---
title: SharePoint と OneDrive を Microsoft 365 Enterprise 向けに展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: 組織全体で SharePoint を計画、ロールアウトするプロセス、および SharePoint Online の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 6b0483073a836f29b1faa5a30018848ef7b2df34
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268211"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a><span data-ttu-id="ed895-103">SharePoint と OneDrive を Microsoft 365 Enterprise 向けに展開する</span><span class="sxs-lookup"><span data-stu-id="ed895-103">Deploy SharePoint and OneDrive for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ed895-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="ed895-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="ed895-105">SharePoint と Microsoft Teams は、ファイルの保存と共有、コンテンツ管理、コラボレーションの方法を提供するもので、Microsoft 365 Enterprise のチームワーク用ビルドの価値を引き出す重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="ed895-105">SharePoint and Microsoft Teams are how you do file storage and sharing, content management, and collaboration and are key elements of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="ed895-p101">SharePoint には、アクセスの制御、アクセス許可、移動中および静的データの暗号化を含む、高度なセキュリティ機能も備わっています。SharePoint のセキュリティは、Microsoft 365 Enterprise のインテリジェント セキュリティの価値を引き出す重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="ed895-p101">SharePoint also has advanced security capabilities including access control with permissions and encryption in flight and at rest. SharePoint security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="ed895-108">SharePoint を初めて使用する方は、「[SharePoint](https://products.office.com/sharepoint/collaboration)」と「[SharePoint を使い始める](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-108">If you are brand new to SharePoint, see [SharePoint](https://products.office.com/sharepoint/collaboration) and [Get Started with SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).</span></span>

<span data-ttu-id="ed895-109">次に示す各フェーズと手順では、組織における SharePoint の役割を想定し、段階的な一連のロールアウトにより組織の研修を行い、それらの使用とエンドユーザーに対する価値を促進するプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="ed895-109">The following phases and steps guide you through the process of envisioning the role of SharePoint in your organization, onboarding your organization through a series of progressive rollouts, and driving usage and its value to your end users.</span></span> <span data-ttu-id="ed895-110">まず始める前に、SharePoint サイトに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-workloads.md#foundation-infrastructure-prerequisites)のフェーズが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed895-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-workloads.md#foundation-infrastructure-prerequisites) phases so that your SharePoint sites have the security capabilities you need.</span></span> 

<span data-ttu-id="ed895-111">OneDrive を Microsoft 365 Enterprise 向けに展開する方法については、「[エンタープライズ向けの OneDrive ガイド](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-111">To deploy OneDrive for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="ed895-112">フェーズ 1: 想定</span><span class="sxs-lookup"><span data-stu-id="ed895-112">Phase 1: Envision</span></span>
<span data-ttu-id="ed895-113">このフェーズでは、SharePoint の展開にあたって組織パートナーを招集し、組織でビジネス ニーズに対応するため、どのように SharePoint を利用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ed895-113">In this phase, you gather the organization partners for your SharePoint deployment and determine how your organization will use SharePoint to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-deployment-members"></a><span data-ttu-id="ed895-114">手順 1: SharePoint の展開メンバーを収集する</span><span class="sxs-lookup"><span data-stu-id="ed895-114">Step 1: Gather your SharePoint deployment members</span></span>

<span data-ttu-id="ed895-p103">[Microsoft 365 Enterprise の基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に SharePoint を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。</span><span class="sxs-lookup"><span data-stu-id="ed895-p103">For a successful deployment of SharePoint on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="ed895-117">この 3 つのグループを招集することにより、展開には、ビジネス ニーズを反映した考慮事項と、フォルダーとドキュメントの移行およびセキュリティの技術的側面が反映され、結果は標準的なユーザーが使用するものになります。</span><span class="sxs-lookup"><span data-stu-id="ed895-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="ed895-118">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-118">Result</span></span>

<span data-ttu-id="ed895-119">組織の事業、技術、エンドユーザーの各視点を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="ed895-119">A list of people that represent the business, technical, and end user perspectives of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a><span data-ttu-id="ed895-120">手順 2: SharePoint のビジネス シナリオを決定し、優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="ed895-120">Step 2: Determine and prioritize your SharePoint business scenarios</span></span>

<span data-ttu-id="ed895-p104">SharePoint はさまざまな目的で使用できます。どの目的がビジネス ニーズに当てはまるかを確認する必要があります。SharePoint のターゲットとして、チーム、事業部、または組織全体のコラボレーションのニーズに対応する、ドキュメントの保存と共有、コンテンツ管理、コラボレーションを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed895-p104">SharePoint can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="ed895-124">[SharePoint](https://products.office.com/sharepoint/collaboration ) のシナリオと機能のリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-124">See the list of scenarios and capabilities at [SharePoint](https://products.office.com/sharepoint/collaboration ).</span></span>

<span data-ttu-id="ed895-125">ビジネスの柱となる次の要素を、組織のニーズに対応させることができます。</span><span class="sxs-lookup"><span data-stu-id="ed895-125">The following business pillars can address your organization's needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="ed895-126">共有と共同作業</span><span class="sxs-lookup"><span data-stu-id="ed895-126">Share and Work Together</span></span> | <span data-ttu-id="ed895-127">チーム サイト、コミュニケーション サイト、および同期を活用します。</span><span class="sxs-lookup"><span data-stu-id="ed895-127">Take advantage of team sites, communication sites, and sync.</span></span> |
| <span data-ttu-id="ed895-128">情報伝達と連携</span><span class="sxs-lookup"><span data-stu-id="ed895-128">Inform and Engage</span></span> | <span data-ttu-id="ed895-129">今後入ってくる情報。</span><span class="sxs-lookup"><span data-stu-id="ed895-129">Information coming in the future.</span></span> |
| <span data-ttu-id="ed895-130">変換</span><span class="sxs-lookup"><span data-stu-id="ed895-130">Transform</span></span> | <span data-ttu-id="ed895-131">Flow を使用して、アプリとサービス間の自動化されたワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed895-131">Uses Flow to create automated workflows between apps and services.</span></span> |
| <span data-ttu-id="ed895-132">集合的な知識の利用</span><span class="sxs-lookup"><span data-stu-id="ed895-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="ed895-133">検索を使用して、組織内で目的とする結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ed895-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="ed895-134">保護</span><span class="sxs-lookup"><span data-stu-id="ed895-134">Protect</span></span> | <span data-ttu-id="ed895-135">組織がセキュリティで保護されており、適切なコンプライアンスを達成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed895-135">Ensures your organization is secured and has the correct compliance.</span></span> |
|||

<span data-ttu-id="ed895-136">各自のニーズに合わせて SharePoint を構成する方法に関するリソースについては、「[SharePoint の管理](https://docs.microsoft.com/sharepoint/sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-136">See [SharePoint admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint for your needs.</span></span>

<span data-ttu-id="ed895-p105">SharePoint の利点を調べる 1 つの方法は、個人、チーム、部門、または組織全体が現在、どのようにやり取りしているかを調べたうえで、ファイルの保存と共有をより簡単に行う適切なシナリオを探すことです。シナリオによっては、[Microsoft Teams](teams-workload.md) がより良い選択になり得ることを念頭においてください。</span><span class="sxs-lookup"><span data-stu-id="ed895-p105">One way to see the benefits of SharePoint is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="ed895-139">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-139">Result</span></span>
<span data-ttu-id="ed895-140">ドキュメントの保存と共有、コンテンツ管理、コラボレーション、セキュリティに関する組織のニーズに対応する SharePoint のシナリオのリスト。</span><span class="sxs-lookup"><span data-stu-id="ed895-140">A list of SharePoint scenarios that address your organization's needs for document storage and sharing, content management, collaboration, and security.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="ed895-141">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="ed895-141">Phase 2: Onboard</span></span>

<span data-ttu-id="ed895-142">このフェーズでは、SharePoint の展開の技術的な側面を計画した後、選択したユーザー グループへの展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="ed895-142">In this phase, you plan for the technical aspects of a SharePoint deployment and start rolling them out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="ed895-143">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="ed895-143">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="ed895-144">SharePoint サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed895-144">To protect access to SharePoint sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="ed895-145">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="ed895-145">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="ed895-146">技術計画を始める前に、FastTrack を使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ed895-146">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="ed895-147">所属する組織が所有しているライセンスが 50 シートを超えていて、[対象となるプラン](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)に参加している場合は、FastTrack の特典を利用することができます。この特典は、追加で費用がかからずに、計画、展開、サービス導入にいたるまでのガイドとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="ed895-147">If your organization has more than 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use FastTrack benefits, available at no additional cost to guide you through planning, migration, deployment, and service adoption.</span></span> <span data-ttu-id="ed895-148">また、この作業をお客様自身で完了することもできます。その場合は、Microsoft 365 アカウントでサインインすると [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) から利用できるようになる FastTrack オンボーディング ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed895-148">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="ed895-149">各自で計画を策定している場合、または FastTrack を使用している場合には、ネットワークと組織が SharePoint を導入できる状態にあるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed895-149">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint.</span></span> <span data-ttu-id="ed895-150">特に、基礎インフラストラクチャの[ネットワークの終了条件](networking-exit-criteria.md)を満たしており、SharePoint ベースのドキュメントのための追加トラフィックのパフォーマンスを最大限に引き出すため、インターネット帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="ed895-150">It is especially important that you meet the [exit criteria for networking](networking-exit-criteria.md) in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint-based documents.</span></span>

<span data-ttu-id="ed895-151">[[SharePoint に移行する](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)] を使用して、SharePoint ロールアウトを準備します。</span><span class="sxs-lookup"><span data-stu-id="ed895-151">Use [Migrate to SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) to prepare for your SharePoint rollout:</span></span> 

<span data-ttu-id="ed895-152">SharePoint でのセキュリティの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-152">For a better understanding of security in SharePoint, review the following resources:</span></span>

-     [<span data-ttu-id="ed895-153">SharePoint と OneDrive がクラウド内のデータを保護する方法</span><span class="sxs-lookup"><span data-stu-id="ed895-153">How SharePoint and OneDrive safeguard your data in the cloud</span></span>](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-     [<span data-ttu-id="ed895-154">OneDrive および SharePoint におけるデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="ed895-154">Data Encryption in OneDrive and SharePoint</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a><span data-ttu-id="ed895-155">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-155">Result</span></span>

<span data-ttu-id="ed895-156">SharePoint サイトとオンプレミス フォルダーおよびドキュメントの移行とセキュリティについて理解し、組織内の選択したグループへの SharePoint の展開を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="ed895-156">You understand SharePoint sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="ed895-157">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="ed895-157">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="ed895-158">中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed895-158">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="ed895-159">IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="ed895-159">During the IT pilot:</span></span>

- <span data-ttu-id="ed895-160">IT パイロット参加者の練習に使用できる SharePoint のビジネス シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed895-160">Choose a SharePoint business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="ed895-161">パイロット参加者に、SharePoint ドキュメントの保存、共有、共同作業、その他の能力をテストするための一連の演習を実施します。</span><span class="sxs-lookup"><span data-stu-id="ed895-161">Give your pilot participants a set of exercises to test SharePoint document storage, sharing, collaboration, and other capabilities.</span></span>
- <span data-ttu-id="ed895-162">変更管理戦略を決定し、資料を作成して、組織全体のユーザーによる SharePoint の導入を推進します。</span><span class="sxs-lookup"><span data-stu-id="ed895-162">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint.</span></span> <span data-ttu-id="ed895-163">変更管理に関する資料には、メールによる発表テキスト、社内トレーニング プラン、廊下のポスター、プレゼンテーションを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="ed895-163">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="ed895-164">この資料で、SharePoint と意識を高めて使用を推進するという目標によるメリットについて組織に伝えます。</span><span class="sxs-lookup"><span data-stu-id="ed895-164">These materials will inform your organization about SharePoint and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="ed895-165">開始するには、「[SharePoint 導入のためのリソース](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-165">See the [SharePoint adoption resources](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) to get started.</span></span>
- <span data-ttu-id="ed895-166">IT パイロットの参加者には、自信の体験に基づいて変更管理の資料をレビューしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="ed895-166">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="ed895-167">その資料にはベスト プラクティスに関するヒントが記載されており、SharePoint の利点とその使用方法についての最適な説明がされています。</span><span class="sxs-lookup"><span data-stu-id="ed895-167">They can provide tips on best practices and advice on how to best describe the benefits of SharePoint and how to use it.</span></span>

#### <a name="result"></a><span data-ttu-id="ed895-168">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-168">Result</span></span>

<span data-ttu-id="ed895-169">SharePoint の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。</span><span class="sxs-lookup"><span data-stu-id="ed895-169">Your SharePoint IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="ed895-170">手順 3: ビジネス グループに展開する</span><span class="sxs-lookup"><span data-stu-id="ed895-170">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="ed895-171">IT パイロットの完了後に、SharePoint を組織内のビジネス グループまたは部門に展開します。</span><span class="sxs-lookup"><span data-stu-id="ed895-171">After completing your IT pilot, roll out SharePoint to a business group or department in your organization.</span></span> <span data-ttu-id="ed895-172">この展開では、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="ed895-172">This rollout should include:</span></span>

- <span data-ttu-id="ed895-173">ビジネス グループにおける SharePoint の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="ed895-173">Identification of key business scenarios for SharePoint within the business group.</span></span>
- <span data-ttu-id="ed895-174">部門と作業チームやプロジェクト チームにおける SharePoint の用途の想定事項とタイムラインをユーザーに伝達する広報活動。</span><span class="sxs-lookup"><span data-stu-id="ed895-174">Announcement activities to inform users of the expectations and timelines for SharePoint usage for departments and for working or project teams.</span></span>
- <span data-ttu-id="ed895-175">ビジネス グループのメンバーの、オンプレミスのフォルダーとドキュメントの SharePoint への移行。</span><span class="sxs-lookup"><span data-stu-id="ed895-175">Migration of on-premises folders and documents of your business group members to SharePoint.</span></span>
- <span data-ttu-id="ed895-176">ユーザー トレーニングまたは SharePoint とその使用方法を紹介するリソースへのリンクの提供。</span><span class="sxs-lookup"><span data-stu-id="ed895-176">Delivering user training or links to resources to introduce SharePoint and how to use it.</span></span> <span data-ttu-id="ed895-177">[SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) のビデオ トレーニングを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-177">See [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="ed895-178">ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。</span><span class="sxs-lookup"><span data-stu-id="ed895-178">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="ed895-179">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="ed895-179">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="ed895-180">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-180">Result</span></span>

<span data-ttu-id="ed895-181">ビジネス グループの 1 つは SharePoint を運用しており、変更管理資料のテストと調整が完了しています。</span><span class="sxs-lookup"><span data-stu-id="ed895-181">A business group is up and running with SharePoint and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="ed895-182">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="ed895-182">Phase 3: Drive value</span></span>

<span data-ttu-id="ed895-183">このフェーズでは、SharePoint の展開を完了し、ユーザーがそのメリットを得られるようにします。</span><span class="sxs-lookup"><span data-stu-id="ed895-183">In this phase, you complete the rollout of SharePoint and help your users realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="ed895-184">手順 1: 組織の他の部分にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="ed895-184">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="ed895-185">組織の残りの部分へのロールアウトには、以下を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed895-185">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="ed895-186">別のビジネス グループにおける SharePoint の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="ed895-186">Identification of key business scenarios for SharePoint Online within separate business groups.</span></span>
- <span data-ttu-id="ed895-187">使用上の想定事項とタイムラインを組織に伝える広報活動に対し再定義した変更管理資料の使用。</span><span class="sxs-lookup"><span data-stu-id="ed895-187">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="ed895-188">組織の残りの部分のフォルダーとドキュメントの、SharePoint への移行。</span><span class="sxs-lookup"><span data-stu-id="ed895-188">Migration of folders and documents for the rest of your organization to SharePoint.</span></span>
- <span data-ttu-id="ed895-189">ユーザー トレーニングの実施、または SharePoint とその使用方法を紹介するリソースへのリンクの提供。</span><span class="sxs-lookup"><span data-stu-id="ed895-189">Delivering user training or provide links to resources to introduce SharePoint and how to use it.</span></span>
- <span data-ttu-id="ed895-p113">組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-p113">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="ed895-193">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-193">Result</span></span>
<span data-ttu-id="ed895-194">組織は SharePoint を運用しており、SharePoint の使用を開始するための情報を伝え、トレーニングを実施し、ユーザーが使用できるようにする変更管理戦略を実施しています。</span><span class="sxs-lookup"><span data-stu-id="ed895-194">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="ed895-195">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="ed895-195">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="ed895-196">組織全体にロールアウトした後、次の目的で変更管理戦略を引き続き採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed895-196">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="ed895-197">ドキュメントの保管と共有の主要ツールとして、リーダーに SharePoint を宣伝してもらいます。</span><span class="sxs-lookup"><span data-stu-id="ed895-197">Have your leadership promote SharePoint as the primary tool for document storage and sharing.</span></span>
- <span data-ttu-id="ed895-198">ビジネス グループ、部署、プロジェクト チームでのドキュメントの保管と共有に、SharePoint の使用を個人に促します。</span><span class="sxs-lookup"><span data-stu-id="ed895-198">Encourage individuals to use it for document storage and sharing among business groups, departments, and working and project teams.</span></span>

<span data-ttu-id="ed895-199">推奨されるアクティビティの一部をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="ed895-199">Here are some suggested activities:</span></span>

- <span data-ttu-id="ed895-200">「[Microsoft 365 の成功要因](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="ed895-200">See [Success factors for Microsoft 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="ed895-p114">「[管理センターの Microsoft 365 レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体でのサービスの使用について理解します。組織のグローバル管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ed895-p114">See [Microsoft 365 Reports in the admin center](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand service usage across your organization. If you aren't a global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="ed895-203">フィードバック会場 (セントラル Teams チームまたは Yammer のパブリック チャネル) に SharePoint での体験について、ユーザーからの問題とフィードバックがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed895-203">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint.</span></span> <span data-ttu-id="ed895-204">ユーザーの不満を防ぎ、展開のサポートを実施できるように、質問と問題にすばやく対処します。</span><span class="sxs-lookup"><span data-stu-id="ed895-204">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="ed895-205">SharePoint を使用している場合は、各ビジネス グループの優秀者を特定、育成し、その業績やベスト プラクティスを強く示します。</span><span class="sxs-lookup"><span data-stu-id="ed895-205">Identify and nurture champions in each business group and highlight their accomplishments and best practices when using SharePoint.</span></span> <span data-ttu-id="ed895-206">組織に彼らの成果を反映させて、プロジェクトの成功と導入を示します。</span><span class="sxs-lookup"><span data-stu-id="ed895-206">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="ed895-207">ビジネス グループの技術リーダーによる推奨は、リーダーと仲間に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="ed895-207">Endorsement by technical leaders within a business group can exert a powerful influence over leadership and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="ed895-208">結果</span><span class="sxs-lookup"><span data-stu-id="ed895-208">Result</span></span>

<span data-ttu-id="ed895-209">組織は Microsoft 365 Enterprise の SharePoint を採用し、ドキュメントの保存と共同作業をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ed895-209">Your organization has adopted SharePoint in Microsoft 365 Enterprise to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="ed895-210">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="ed895-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ed895-211">Microsoft が実施した SharePoint の展開方法についての詳しい説明は、「[SharePoint からクラウドへ: Microsoft が実施した移行方法](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-211">To peek inside Microsoft and learn how we deployed SharePoint, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed895-212">次の手順</span><span class="sxs-lookup"><span data-stu-id="ed895-212">Next steps</span></span>

<span data-ttu-id="ed895-213">SharePoint の継続的なメンテナンスについては、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed895-213">See these resources for the ongoing maintenance of SharePoint:</span></span> 

- [<span data-ttu-id="ed895-214">SharePoint でのアクセス許可レベルについて</span><span class="sxs-lookup"><span data-stu-id="ed895-214">Understanding permission levels in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [<span data-ttu-id="ed895-215">SharePoint サイト権限をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="ed895-215">Customize SharePoint site permissions</span></span>](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [<span data-ttu-id="ed895-216">SharePoint の外部共有をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="ed895-216">Turn external sharing on or off for SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [<span data-ttu-id="ed895-217">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="ed895-217">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
