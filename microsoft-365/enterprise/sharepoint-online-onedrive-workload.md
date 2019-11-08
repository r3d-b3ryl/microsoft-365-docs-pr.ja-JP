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
ms.custom: ''
description: 組織全体で SharePoint を計画、ロールアウトするプロセス、および SharePoint Online の価値を引き出すプロセスについて、順を追って説明します。
ms.openlocfilehash: 74ab3b65597cdf1752dd5dbf9179724464c998a3
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031642"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a><span data-ttu-id="82188-103">SharePoint と OneDrive を Microsoft 365 Enterprise 向けに展開する</span><span class="sxs-lookup"><span data-stu-id="82188-103">Deploy SharePoint and OneDrive for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="82188-104">*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*</span><span class="sxs-lookup"><span data-stu-id="82188-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="82188-105">SharePoint と Microsoft Teams は、ファイルの保存と共有、コンテンツ管理、コラボレーションの方法を提供するもので、Microsoft 365 Enterprise のチームワーク用ビルドの価値を引き出す重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="82188-105">SharePoint and Microsoft Teams are how you do file storage and sharing, content management, and collaboration and are key elements of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="82188-p101">SharePoint には、アクセスの制御、アクセス許可、移動中および静的データの暗号化を含む、高度なセキュリティ機能も備わっています。SharePoint のセキュリティは、Microsoft 365 Enterprise のインテリジェント セキュリティの価値を引き出す重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="82188-p101">SharePoint also has advanced security capabilities including access control with permissions and encryption in flight and at rest. SharePoint security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="82188-108">SharePoint を初めて使用する方は、「[SharePoint](https://products.office.com/sharepoint/collaboration)」と「[SharePoint を使い始める](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-108">If you are brand new to SharePoint, see [SharePoint](https://products.office.com/sharepoint/collaboration) and [Get Started with SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).</span></span>

<span data-ttu-id="82188-109">次に示す各フェーズと手順では、組織における SharePoint の役割を想定し、段階的な一連のロールアウトにより組織の研修を行い、それらの使用とエンドユーザーに対する価値を促進するプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="82188-109">The following phases and steps guide you through the process of envisioning the role of SharePoint in your organization, onboarding your organization through a series of progressive rollouts, and driving usage and its value to your end users.</span></span> <span data-ttu-id="82188-110">まず始める前に、SharePoint サイトに必要なセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-workloads.md#foundation-infrastructure-prerequisites)のフェーズが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82188-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-workloads.md#foundation-infrastructure-prerequisites) phases so that your SharePoint sites have the security capabilities you need.</span></span> 

<span data-ttu-id="82188-111">OneDrive を Microsoft 365 Enterprise 向けに展開する方法については、「[エンタープライズ向けの OneDrive ガイド](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-111">To deploy OneDrive for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="82188-112">フェーズ 1: 想定</span><span class="sxs-lookup"><span data-stu-id="82188-112">Phase 1: Envision</span></span>
<span data-ttu-id="82188-113">このフェーズでは、SharePoint の展開にあたって組織パートナーを招集し、組織でビジネス ニーズに対応するため、どのように SharePoint を利用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="82188-113">In this phase, you gather the organization partners for your SharePoint deployment and determine how your organization will use SharePoint to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-deployment-members"></a><span data-ttu-id="82188-114">手順 1: SharePoint の展開メンバーを収集する</span><span class="sxs-lookup"><span data-stu-id="82188-114">Step 1: Gather your SharePoint deployment members</span></span>

<span data-ttu-id="82188-p103">[Microsoft 365 Enterprise の基礎インフラストラクチャ](deploy-foundation-infrastructure.md)に SharePoint を適切に展開するには、意見やフィードバックを得るために適切な関係者を招集する必要があります。主な関係者は、事業部門の意思決定者、IT 担当者 (アーキテクトや実装担当者など)、エンドユーザーの代表者です。</span><span class="sxs-lookup"><span data-stu-id="82188-p103">For a successful deployment of SharePoint on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="82188-117">この 3 つのグループを招集することにより、展開には、ビジネス ニーズを反映した考慮事項と、フォルダーとドキュメントの移行およびセキュリティの技術的側面が反映され、結果は標準的なユーザーが使用するものになります。</span><span class="sxs-lookup"><span data-stu-id="82188-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="82188-118">結果</span><span class="sxs-lookup"><span data-stu-id="82188-118">Result</span></span>

<span data-ttu-id="82188-119">組織の事業、技術、エンドユーザーの各視点を代表する関係者のリスト。</span><span class="sxs-lookup"><span data-stu-id="82188-119">A list of people that represent the business, technical, and end user perspectives of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a><span data-ttu-id="82188-120">手順 2: SharePoint のビジネス シナリオを決定し、優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="82188-120">Step 2: Determine and prioritize your SharePoint business scenarios</span></span>

<span data-ttu-id="82188-p104">SharePoint はさまざまな目的で使用できます。どの目的がビジネス ニーズに当てはまるかを確認する必要があります。SharePoint のターゲットとして、チーム、事業部、または組織全体のコラボレーションのニーズに対応する、ドキュメントの保存と共有、コンテンツ管理、コラボレーションを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82188-p104">SharePoint can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="82188-124">[SharePoint](https://products.office.com/sharepoint/collaboration ) のシナリオと機能のリストを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-124">See the list of scenarios and capabilities at [SharePoint](https://products.office.com/sharepoint/collaboration ).</span></span>

<span data-ttu-id="82188-125">ビジネスの柱となる次の要素を、組織のニーズに対応させることができます。</span><span class="sxs-lookup"><span data-stu-id="82188-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="82188-126">共有と共同作業</span><span class="sxs-lookup"><span data-stu-id="82188-126">Share and Work Together</span></span> | <span data-ttu-id="82188-127">チーム サイト、コミュニケーション サイト、および同期を活用します。</span><span class="sxs-lookup"><span data-stu-id="82188-127">Take advantage of team sites, communication sites, and sync.</span></span> |
| <span data-ttu-id="82188-128">情報伝達と連携</span><span class="sxs-lookup"><span data-stu-id="82188-128">Inform and Engage</span></span> | <span data-ttu-id="82188-129">今後入ってくる情報。</span><span class="sxs-lookup"><span data-stu-id="82188-129">Information coming in the future.</span></span> |
| <span data-ttu-id="82188-130">変換</span><span class="sxs-lookup"><span data-stu-id="82188-130">Transform</span></span> | <span data-ttu-id="82188-131">Flow を使用して、アプリとサービス間の自動化されたワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="82188-131">Uses Flow to create automated workflows between apps and services.</span></span> |
| <span data-ttu-id="82188-132">集合的な知識の利用</span><span class="sxs-lookup"><span data-stu-id="82188-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="82188-133">検索を使用して、組織内で目的とする結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="82188-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="82188-134">保護</span><span class="sxs-lookup"><span data-stu-id="82188-134">Protect</span></span> | <span data-ttu-id="82188-135">組織がセキュリティで保護されており、適切なコンプライアンスを達成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82188-135">Ensures your organization is secured and has the correct compliance.</span></span> |
|||

<span data-ttu-id="82188-136">各自のニーズに合わせて SharePoint を構成する方法に関するリソースについては、「[SharePoint の管理](https://docs.microsoft.com/sharepoint/sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-136">See [SharePoint admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint for your needs.</span></span>

<span data-ttu-id="82188-p105">SharePoint の利点を調べる 1 つの方法は、個人、チーム、部門、または組織全体が現在、どのようにやり取りしているかを調べたうえで、ファイルの保存と共有をより簡単に行う適切なシナリオを探すことです。シナリオによっては、[Microsoft Teams](teams-workload.md) がより良い選択になり得ることを念頭においてください。</span><span class="sxs-lookup"><span data-stu-id="82188-p105">One way to see the benefits of SharePoint is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="82188-139">厳しく規制されたデータ用の SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="82188-139">SharePoint site for highly regulated data</span></span>

<span data-ttu-id="82188-140">厳しく規制されたデータは地域の規制対象であるか、企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータです。</span><span class="sxs-lookup"><span data-stu-id="82188-140">Highly regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span> <span data-ttu-id="82188-141">このようなデータに対して、アクセスの制限、データの分類、データ損失の防止、暗号化を行うための SharePoint サイトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="82188-141">You can configure a SharePoint site for restricted access, data classification, data loss prevention, and encryption for this type of data.</span></span> <span data-ttu-id="82188-142">詳細については、「[Microsoft Teams および SharePoint サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-142">For the details, see [Microsoft Teams and SharePoint sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="82188-143">結果</span><span class="sxs-lookup"><span data-stu-id="82188-143">Result</span></span>
<span data-ttu-id="82188-144">ドキュメントの保存と共有、コンテンツ管理、コラボレーション、セキュリティに関する組織のニーズに対応する SharePoint のシナリオのリスト。</span><span class="sxs-lookup"><span data-stu-id="82188-144">A list of SharePoint scenarios that address your organization’s needs for document storage and sharing, content management, collaboration, and security.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="82188-145">フェーズ 2: 研修</span><span class="sxs-lookup"><span data-stu-id="82188-145">Phase 2: Onboard</span></span>

<span data-ttu-id="82188-146">このフェーズでは、SharePoint の展開の技術的な側面を計画した後、選択したユーザー グループへの展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="82188-146">In this phase, you plan for the technical aspects of a SharePoint deployment and start rolling them out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="82188-147">前提条件: ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="82188-147">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="82188-148">SharePoint サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82188-148">To protect access to SharePoint sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="82188-149">手順 1: 技術計画を実施する</span><span class="sxs-lookup"><span data-stu-id="82188-149">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="82188-150">技術計画を始める前に、FastTrack を使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="82188-150">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="82188-151">所属する組織が所有しているライセンスが 50 シートを超えていて、[対象となるプラン](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)に参加している場合は、FastTrack の特典を利用することができます。この特典は、追加で費用がかからずに、計画、展開、サービス導入にいたるまでのガイドとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="82188-151">If your organization has more than 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use FastTrack benefits, available at no additional cost to guide you through planning, migration, deployment, and service adoption.</span></span> <span data-ttu-id="82188-152">また、この作業をお客様自身で完了することもできます。その場合は、Microsoft 365 アカウントでサインインすると [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) から利用できるようになる FastTrack オンボーディング ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="82188-152">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="82188-153">各自で計画を策定している場合、または FastTrack を使用している場合には、ネットワークと組織が SharePoint を導入できる状態にあるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82188-153">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint.</span></span> <span data-ttu-id="82188-154">特に、基礎インフラストラクチャの[ネットワークの終了条件](networking-exit-criteria.md)を満たしており、SharePoint ベースのドキュメントのための追加トラフィックのパフォーマンスを最大限に引き出すため、インターネット帯域幅、スループット、トラフィック遅延に特別な注意を払うことが重要です。</span><span class="sxs-lookup"><span data-stu-id="82188-154">It is especially important that you meet the [exit criteria for networking](networking-exit-criteria.md) in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint-based documents.</span></span>

<span data-ttu-id="82188-155">[[SharePoint に移行する](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)] を使用して、SharePoint ロールアウトを準備します。</span><span class="sxs-lookup"><span data-stu-id="82188-155">Use [Migrate to SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) to prepare for your SharePoint rollout:</span></span> 

<span data-ttu-id="82188-156">SharePoint でのセキュリティの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-156">For a better understanding of security in SharePoint, review the following resources:</span></span>

-   [<span data-ttu-id="82188-157">SharePoint と OneDrive がクラウド内のデータを保護する方法</span><span class="sxs-lookup"><span data-stu-id="82188-157">How SharePoint and OneDrive safeguard your data in the cloud</span></span>](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [<span data-ttu-id="82188-158">OneDrive および SharePoint におけるデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="82188-158">Data Encryption in OneDrive and SharePoint</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a><span data-ttu-id="82188-159">結果</span><span class="sxs-lookup"><span data-stu-id="82188-159">Result</span></span>

<span data-ttu-id="82188-160">SharePoint サイトとオンプレミス フォルダーおよびドキュメントの移行とセキュリティについて理解し、組織内の選択したグループへの SharePoint の展開を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="82188-160">You understand SharePoint sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="82188-161">手順 2: IT パイロットを実施する</span><span class="sxs-lookup"><span data-stu-id="82188-161">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="82188-162">中規模～大規模な組織のほとんどでは、フェーズ 1 の関係者、早期導入者、熱心な技術者を集めて IT パイロットを実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82188-162">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="82188-163">IT パイロットでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="82188-163">During the IT pilot:</span></span>

- <span data-ttu-id="82188-164">IT パイロット参加者の練習に使用できる SharePoint のビジネス シナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="82188-164">Choose a SharePoint business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="82188-165">パイロット参加者に、SharePoint ドキュメントの保存、共有、共同作業、その他の能力をテストするための一連の演習を実施します。</span><span class="sxs-lookup"><span data-stu-id="82188-165">Give your pilot participants a set of exercises to test SharePoint document storage, sharing, collaboration, and other capabilities.</span></span>
- <span data-ttu-id="82188-166">変更管理戦略を決定し、資料を作成して、組織全体のユーザーによる SharePoint の導入を推進します。</span><span class="sxs-lookup"><span data-stu-id="82188-166">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint.</span></span> <span data-ttu-id="82188-167">変更管理に関する資料には、メールによる発表テキスト、社内トレーニング プラン、廊下のポスター、プレゼンテーションを入れることができます。</span><span class="sxs-lookup"><span data-stu-id="82188-167">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="82188-168">この資料で、SharePoint と意識を高めて使用を推進するという目標によるメリットについて組織に伝えます。</span><span class="sxs-lookup"><span data-stu-id="82188-168">These materials will inform your organization about SharePoint and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="82188-169">開始するには、「[SharePoint 導入のためのリソース](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-169">See the [SharePoint adoption resources](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) to get started.</span></span>
- <span data-ttu-id="82188-170">IT パイロットの参加者には、自信の体験に基づいて変更管理の資料をレビューしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="82188-170">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="82188-171">その資料にはベスト プラクティスに関するヒントが記載されており、SharePoint の利点とその使用方法についての最適な説明がされています。</span><span class="sxs-lookup"><span data-stu-id="82188-171">They can provide tips on best practices and advice on how to best describe the benefits of SharePoint and how to use it.</span></span>

#### <a name="result"></a><span data-ttu-id="82188-172">結果</span><span class="sxs-lookup"><span data-stu-id="82188-172">Result</span></span>

<span data-ttu-id="82188-173">SharePoint の IT パイロットが完了し、最初の変更管理資料の作成、レビュー、調整が行われます。</span><span class="sxs-lookup"><span data-stu-id="82188-173">Your SharePoint IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="82188-174">手順 3: ビジネス グループに展開する</span><span class="sxs-lookup"><span data-stu-id="82188-174">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="82188-175">IT パイロットの完了後に、SharePoint を組織内のビジネス グループまたは部門に展開します。</span><span class="sxs-lookup"><span data-stu-id="82188-175">After completing your IT pilot, roll out SharePoint to a business group or department in your organization.</span></span> <span data-ttu-id="82188-176">この展開では、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="82188-176">This rollout should include:</span></span>

- <span data-ttu-id="82188-177">ビジネス グループにおける SharePoint の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="82188-177">Identification of key business scenarios for SharePoint within the business group.</span></span>
- <span data-ttu-id="82188-178">部門と作業チームやプロジェクト チームにおける SharePoint の用途の想定事項とタイムラインをユーザーに伝達する広報活動。</span><span class="sxs-lookup"><span data-stu-id="82188-178">Announcement activities to inform users of the expectations and timelines for SharePoint usage for departments and for working or project teams.</span></span>
- <span data-ttu-id="82188-179">ビジネス グループのメンバーの、オンプレミスのフォルダーとドキュメントの SharePoint への移行。</span><span class="sxs-lookup"><span data-stu-id="82188-179">Migration of on-premises folders and documents of your business group members to SharePoint.</span></span>
- <span data-ttu-id="82188-180">ユーザー トレーニングまたは SharePoint とその使用方法を紹介するリソースへのリンクの提供。</span><span class="sxs-lookup"><span data-stu-id="82188-180">Delivering user training or links to resources to introduce SharePoint and how to use it.</span></span> <span data-ttu-id="82188-181">[SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) のビデオ トレーニングを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-181">See [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="82188-182">ビジネス グループのユーザーからコメントを収集し、問題点を指摘するフィードバック メカニズム (ビジネス グループのメンバー全員が含まれている中央の Microsoft Teams チームなど)。</span><span class="sxs-lookup"><span data-stu-id="82188-182">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="82188-183">ロールアウト中には、組織全体でのロールアウトに備えて変更管理資料を調整できます。</span><span class="sxs-lookup"><span data-stu-id="82188-183">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="82188-184">結果</span><span class="sxs-lookup"><span data-stu-id="82188-184">Result</span></span>

<span data-ttu-id="82188-185">ビジネス グループの 1 つは SharePoint を運用しており、変更管理資料のテストと調整が完了しています。</span><span class="sxs-lookup"><span data-stu-id="82188-185">A business group is up and running with SharePoint and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="82188-186">フェーズ 3: 価値を引き出す</span><span class="sxs-lookup"><span data-stu-id="82188-186">Phase 3: Drive value</span></span>

<span data-ttu-id="82188-187">このフェーズでは、SharePoint の展開を完了し、ユーザーがそのメリットを得られるようにします。</span><span class="sxs-lookup"><span data-stu-id="82188-187">In this phase, you complete the rollout of SharePoint and help your users realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="82188-188">手順 1: 組織の他の部分にロールアウトする</span><span class="sxs-lookup"><span data-stu-id="82188-188">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="82188-189">組織の残りの部分へのロールアウトには、以下を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="82188-189">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="82188-190">別のビジネス グループにおける SharePoint の重要なビジネス シナリオの決定。</span><span class="sxs-lookup"><span data-stu-id="82188-190">Identification of key business scenarios for SharePoint Online within separate business groups.</span></span>
- <span data-ttu-id="82188-191">使用上の想定事項とタイムラインを組織に伝える広報活動に対し再定義した変更管理資料の使用。</span><span class="sxs-lookup"><span data-stu-id="82188-191">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="82188-192">組織の残りの部分のフォルダーとドキュメントの、SharePoint への移行。</span><span class="sxs-lookup"><span data-stu-id="82188-192">Migration of folders and documents for the rest of your organization to SharePoint.</span></span>
- <span data-ttu-id="82188-193">ユーザー トレーニングの実施、または SharePoint とその使用方法を紹介するリソースへのリンクの提供。</span><span class="sxs-lookup"><span data-stu-id="82188-193">Delivering user training or provide links to resources to introduce SharePoint and how to use it.</span></span>
- <span data-ttu-id="82188-p114">組織のユーザーからのコメントや問題点を収集するフィードバック メカニズム (すべてのユーザーが含まれている中央チームなど)。組織の従業員数が 2500 人未満の場合は、Teams のパブリック チャネルを使用し、2500 人以上の場合は Yammer のパブリック グループを使用してください。</span><span class="sxs-lookup"><span data-stu-id="82188-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="82188-197">結果</span><span class="sxs-lookup"><span data-stu-id="82188-197">Result</span></span>
<span data-ttu-id="82188-198">組織は SharePoint を運用しており、SharePoint の使用を開始するための情報を伝え、トレーニングを実施し、ユーザーが使用できるようにする変更管理戦略を実施しています。</span><span class="sxs-lookup"><span data-stu-id="82188-198">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="82188-199">手順 2: 使用状況を測定し、満足度を管理し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="82188-199">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="82188-200">組織全体にロールアウトした後、次の目的で変更管理戦略を引き続き採用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82188-200">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="82188-201">ドキュメントの保管と共有の主要ツールとして、リーダーに SharePoint を宣伝してもらいます。</span><span class="sxs-lookup"><span data-stu-id="82188-201">Have your leadership promote SharePoint as the primary tool for document storage and sharing.</span></span>
- <span data-ttu-id="82188-202">ビジネス グループ、部署、プロジェクト チームでのドキュメントの保管と共有に、SharePoint の使用を個人に促します。</span><span class="sxs-lookup"><span data-stu-id="82188-202">Encourage individuals to use it for document storage and sharing among business groups, departments, and working and project teams.</span></span>

<span data-ttu-id="82188-203">推奨されるアクティビティの一部をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="82188-203">Here are some suggested activities:</span></span>

- <span data-ttu-id="82188-204">「[Office 365 の成功要因](https://aka.ms/successfactors)」を参照して、クラウド サービス導入の一般的なベスト プラクティスを理解します。</span><span class="sxs-lookup"><span data-stu-id="82188-204">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="82188-p115">「[Office 365 アクティビティ レポート](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)」を参照して、組織全体での Office 365 サービスの使用について理解します。組織の Office 365 全体管理者ではない場合は、ユーザー アカウントに Reports Reader 権限を付与できるグローバル管理者に権限の付与を依頼し、アクティビティ レポートにアクセスできるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="82188-p115">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="82188-207">フィードバック会場 (セントラル Teams チームまたは Yammer のパブリック チャネル) に SharePoint での体験について、ユーザーからの問題とフィードバックがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="82188-207">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint.</span></span> <span data-ttu-id="82188-208">ユーザーの不満を防ぎ、展開のサポートを実施できるように、質問と問題にすばやく対処します。</span><span class="sxs-lookup"><span data-stu-id="82188-208">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="82188-209">SharePoint を使用している場合は、各ビジネス グループの優秀者を特定、育成し、その業績やベスト プラクティスを強く示します。</span><span class="sxs-lookup"><span data-stu-id="82188-209">Identify and nurture champions in each business group and highlight their accomplishments and best practices when using SharePoint.</span></span> <span data-ttu-id="82188-210">組織に彼らの成果を反映させて、プロジェクトの成功と導入を示します。</span><span class="sxs-lookup"><span data-stu-id="82188-210">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="82188-211">ビジネス グループの技術リーダーによる推奨は、リーダーと仲間に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="82188-211">Endorsement by technical leaders within a business group can exert a powerful influence over leadership and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="82188-212">結果</span><span class="sxs-lookup"><span data-stu-id="82188-212">Result</span></span>

<span data-ttu-id="82188-213">組織は Microsoft 365 Enterprise の SharePoint を採用し、ドキュメントの保存と共同作業をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82188-213">Your organization has adopted SharePoint in Microsoft 365 Enterprise to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="82188-214">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="82188-214">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="82188-215">Microsoft が実施した SharePoint の展開方法についての詳しい説明は、「[SharePoint からクラウドへ: Microsoft が実施した移行方法](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-215">To peek inside Microsoft and learn how we deployed SharePoint, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="82188-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="82188-216">Next steps</span></span>

<span data-ttu-id="82188-217">SharePoint の継続的なメンテナンスについては、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82188-217">See these resources for the ongoing maintenance of SharePoint:</span></span> 

- [<span data-ttu-id="82188-218">SharePoint でのアクセス許可レベルについて</span><span class="sxs-lookup"><span data-stu-id="82188-218">Understanding permission levels in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [<span data-ttu-id="82188-219">SharePoint サイト権限をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="82188-219">Customize SharePoint site permissions</span></span>](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [<span data-ttu-id="82188-220">SharePoint の外部共有をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="82188-220">Turn external sharing on or off for SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [<span data-ttu-id="82188-221">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="82188-221">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
