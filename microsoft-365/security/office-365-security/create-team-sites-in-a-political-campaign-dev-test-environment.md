---
title: チーム サイトを作成する - 選挙運動用の開発環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: '概要: 選挙運動用の開発/テスト環境で、パブリック、プライベート、機密、および高機密の SharePoint Online チーム サイトを作成します。'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4f680cfb30de5b6904e5fa489cca368550195b4f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205979"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a><span data-ttu-id="cad6f-103">選挙運動用の開発/テスト環境でチーム サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="cad6f-103">Create team sites in a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cad6f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="cad6f-104">**Applies to**</span></span>

- [<span data-ttu-id="cad6f-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="cad6f-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- 
 <span data-ttu-id="cad6f-106">**概要:** 選挙運動用の開発/テスト環境で、パブリック、プライベート、機密、および高機密の SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-106">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in your political campaign dev/test environment.</span></span> 
   
<span data-ttu-id="cad6f-p101">この記事に示した手順を使用して、「[選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)」のソリューションに対応した 4 種類の SharePoint Online チーム サイトを含む開発/テスト環境を作成してください。これらのサイトについての詳細は、トピック 10 のタイトル「**SharePoint および OneDrive for Business**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p101">Use the instructions in this article to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution. These sites are described in detail on Topic 10, titled **SharePoint and OneDrive for Business**.</span></span>

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a><span data-ttu-id="cad6f-109">フェーズ 1: 選挙運動用の開発/テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="cad6f-109">Phase 1: Create your political campaign dev/test environment</span></span>

<span data-ttu-id="cad6f-110">最初に、「[選挙運動の開発/テスト環境用にグループとユーザーを構成する](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)」の手順に従って、サブスクリプション、ユーザー、およびグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-110">First, follow the instructions in [Configure groups and users for a political campaign dev/test environment](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) to create your subscriptions, users, and groups.</span></span>

## <a name="phase-2-create-labels"></a><span data-ttu-id="cad6f-111">フェーズ 2: ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="cad6f-111">Phase 2: Create labels</span></span>

<span data-ttu-id="cad6f-112">このフェーズでは、SharePoint Online チーム サイトのドキュメント フォルダーに対してさまざまなセキュリティ レベルのラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-112">In this phase, you create the labels for the different levels of security for SharePoint Online team site document folders.</span></span>

1. <span data-ttu-id="cad6f-113">必要に応じて、試用版サブスクリプション用の全体管理者アカウントの資格情報で管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-113">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="cad6f-114">詳細については、「[一般法人向け Microsoft 365 にサインインする場所](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad6f-114">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="cad6f-115">**[Microsoft Office Home]** タブで、**[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-115">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>

3. <span data-ttu-id="cad6f-116">ブラウザーの新しい **[Microsoft 365 管理センター]** タブで、**[管理センター] > [セキュリティとコンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-116">From the new **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>

4. <span data-ttu-id="cad6f-117">ブラウザーの新しい **[ホーム – セキュリティとコンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-117">From the new **Home - Security & Compliance** tab of your browser, click **Classifications > Labels**.</span></span>

5. <span data-ttu-id="cad6f-118">**[ホーム] > [ラベル]** ウィンドウで、**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-118">From the **Home > Labels** pane, click **Create a label**.</span></span>

6. <span data-ttu-id="cad6f-119">**[ラベルに名前をつける]** ウィンドウで、「**内部**」と入力してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-119">On the **Name your label** pane, type **Internal**, and then click **Next**.</span></span>

7. <span data-ttu-id="cad6f-120">**[ラベル設定]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-120">On the **Label settings** pane, click **Next**.</span></span>

8. <span data-ttu-id="cad6f-121">**[設定の確認]** ウィンドウで、 **[このラベルを作成する]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-121">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>

9. <span data-ttu-id="cad6f-122">次の追加ラベルについて手順 5 から 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-122">Repeat steps 5-8 for these additional labels:</span></span>

   - <span data-ttu-id="cad6f-123">Kirkland</span><span class="sxs-lookup"><span data-stu-id="cad6f-123">Private</span></span>
   - <span data-ttu-id="cad6f-124">機密</span><span class="sxs-lookup"><span data-stu-id="cad6f-124">Sensitive</span></span>
   - <span data-ttu-id="cad6f-125">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="cad6f-125">Highly Confidential</span></span>

10. <span data-ttu-id="cad6f-126">**[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-126">From the **Home > Labels** pane, click **Publish labels**.</span></span>

11. <span data-ttu-id="cad6f-127">**[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-127">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

12. <span data-ttu-id="cad6f-128">**[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-128">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

13. <span data-ttu-id="cad6f-129">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-129">Click **Done**.</span></span>

14. <span data-ttu-id="cad6f-130">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-130">On the **Choose labels to publish** pane, click **Next**.</span></span>

15. <span data-ttu-id="cad6f-131">**[場所の選択]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-131">On the **Choose locations** pane, click **Next**.</span></span>

16. <span data-ttu-id="cad6f-132">**[ポリシーに名前をつける]** ウィンドウで、**[名前]** に「**キャンペーン**」と入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-132">On the **Name your policy** pane, type **Campaign** in **Name**, and then click **Next**.</span></span>

17. <span data-ttu-id="cad6f-133">**[設定の確認]** ウィンドウで、**[ラベルの発行]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-133">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="cad6f-134">フェーズ 3:SharePoint Online チーム サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="cad6f-134">Phase 3: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="cad6f-135">このフェーズでは、SharePoint Online チーム サイトを作成し、4 つのタイプの SharePoint Online チーム サイトに対応する選挙運動用に構成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-135">In this phase, you create and configure SharePoint Online team sites for your political campaign corresponding to the four types of SharePoint Online team sites.</span></span>

### <a name="campaign-wide-team-site"></a><span data-ttu-id="cad6f-136">キャンペーン全体のチーム サイト</span><span class="sxs-lookup"><span data-stu-id="cad6f-136">Campaign wide team site</span></span>

<span data-ttu-id="cad6f-137">ベースラインのパブリック SharePoint Online チーム サイトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cad6f-137">To create a baseline public SharePoint Online team site, do the following:</span></span>

1. <span data-ttu-id="cad6f-138">必要に応じて、ローカル コンピューターのブラウザーを使用し、全体管理者アカウントで管理センター (<https://admin.microsoft.com>) にサイン インします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-138">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="cad6f-139">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-139">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="cad6f-140">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-140">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="cad6f-141">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-141">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="cad6f-142">**[サイト名]** に、「**キャンペーン全体**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-142">In **Site name**, type **Campaign wide**.</span></span>

6. <span data-ttu-id="cad6f-143">**[チーム サイトの説明]** に、「**キャンペーン全体の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-143">In **Team site description**, type **SharePoint site for the entire campaign**.</span></span>

7. <span data-ttu-id="cad6f-144">**[プライバシー設定]** で、**[パブリック - 組織の全ユーザーがこのサイトにアクセス可能]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-144">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="cad6f-145">**[誰を追加しますか]** ウィンドウで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-145">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="cad6f-146">次に、キャンペーン全体のチーム サイトのドキュメント フォルダーを [内部] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-146">Next, configure the documents folder of the Campaign wide team site for the Internal label.</span></span>

1. <span data-ttu-id="cad6f-147">ブラウザーの **[キャンペーン全体 – ホーム]** タブをクリックして、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-147">In the **Campaign wide-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="cad6f-148">[設定] アイコンをクリックしてから、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-148">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="cad6f-149">**[権限と管理]** をクリックして、**[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-149">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="cad6f-150">**[設定 - ラベルの適用]** で **[内部]** をクリックし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-150">In **Settings-Apply Label**, select **Internal**, and then click **Save**.</span></span>

### <a name="campaign-project-1-team-site"></a><span data-ttu-id="cad6f-151">キャンペーン プロジェクト 1 のチーム サイト</span><span class="sxs-lookup"><span data-stu-id="cad6f-151">Campaign project 1 team site</span></span>

<span data-ttu-id="cad6f-152">キャンペーン内のプロジェクト用にベースラインのプライベート SharePoint Online チーム サイトを作成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-152">To create a baseline private SharePoint Online team site for a project within the campaign, do the following:</span></span>

1. <span data-ttu-id="cad6f-153">必要に応じて、ローカル コンピューターのブラウザーを使用し、全体管理者アカウントで管理センター (<https://admin.microsoft.com>) にサイン インします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-153">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="cad6f-154">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-154">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="cad6f-155">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-155">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="cad6f-156">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-156">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="cad6f-157">**[サイト名]** に、「**キャンペーン プロジェクト 1**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-157">In **Site name**, type **Campaign project 1**.</span></span>

6. <span data-ttu-id="cad6f-158">**[チーム サイトの説明]** に、「**キャンペーン プロジェクト 1 の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-158">In **Team site description,** type **SharePoint site for Campaign project 1**.</span></span>

7. <span data-ttu-id="cad6f-159">**[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-159">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="cad6f-160">**[誰を追加しますか]** ウィンドウで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-160">On the **Who do you want to add?** pane, click **Finish**.</span></span>

<span data-ttu-id="cad6f-161">次に、キャンペーン プロジェクト 1 チーム サイトのドキュメント フォルダーを [プライベート] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-161">Next, configure the documents folder of the Campaign project 1 team site for the Private label.</span></span>

1. <span data-ttu-id="cad6f-162">ブラウザーの **[キャンペーン プロジェクト 1 – ホーム]** タブをクリックして、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-162">In the **Campaign project 1-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="cad6f-163">[設定] アイコンをクリックしてから、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-163">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="cad6f-164">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-164">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="cad6f-165">**[設定 - ラベルの適用]** で **[プライベート]** をクリックし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-165">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>

### <a name="campaign-marketing-team-site"></a><span data-ttu-id="cad6f-166">キャンペーン マーケティング チーム サイト</span><span class="sxs-lookup"><span data-stu-id="cad6f-166">Campaign marketing team site</span></span>

<span data-ttu-id="cad6f-167">キャンペーン マーケティング リソース用の機密レベルの分離した SharePoint Online チーム サイトを作成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-167">To create a sensitive-level isolated SharePoint Online team site for campaign marketing resources, do the following:</span></span>

1. <span data-ttu-id="cad6f-168">ローカル コンピューターのブラウザーを使用し、全体管理者アカウントで管理センター (<https://admin.microsoft.com>) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-168">Using a browser on your local computer, sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="cad6f-169">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-169">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="cad6f-170">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-170">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="cad6f-171">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-171">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="cad6f-172">**[チーム サイト名]** に、「**キャンペーン マーケティング**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-172">In **Team site name**, type **Campaign marketing**.</span></span>

6. <span data-ttu-id="cad6f-173">**[チーム サイトの説明]** に、「**キャンペーン マーケティングの SharePoint サイト (機密)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-173">In **Team site description**, type **SharePoint site for campaign marketing (sensitive)**.</span></span>

7. <span data-ttu-id="cad6f-174">**[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-174">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="cad6f-175">**[誰を追加しますか]** ウィンドウで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-175">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="cad6f-176">ブラウザーの新しい **[キャンペーン マーケティング]** タブのツール バーで、設定アイコンをクリックし、**[サイトのアクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-176">On the new **Campaign marketing** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="cad6f-177">**[サイトの権限]** ウィンドウで、**[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-177">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="cad6f-178">ブラウザーの新しい **[アクセス許可]** タブで、 **[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-178">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="cad6f-179">**[アクセス要求の設定]** ダイアログ ボックスで、**[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可する]** および **[メンバーが、他のユーザーをサイト メンバー グループに招待することを許可する]** チェック ボックスをクリアし、**[すべてのアクセス要求を送信する]** に「**ITAdmin1@**\<your organization name\>**.onmicrosoft.com**」と入力し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-179">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name\>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>

13. <span data-ttu-id="cad6f-180">一覧にある **[キャンペーン マーケティング メンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-180">Click **Campaign marketing Members** in the list.</span></span>

14. <span data-ttu-id="cad6f-181">**[ユーザーとグループ]** ページで、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-181">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="cad6f-182">**[共有]** ダイアログ ボックスに「**戦略的シニア スタッフ**」と入力し、それを選択して、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-182">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="cad6f-183">**[分析スタッフ]** グループおよび **Regular1** ユーザー アカウントで手順 14 と 15 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-183">Repeat steps 14 and 15 for the **Analytics staff** group and the **Regular1** user account.</span></span>

17. <span data-ttu-id="cad6f-184">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-184">Click the back button on your browser.</span></span>

18. <span data-ttu-id="cad6f-185">一覧にある **[キャンペーン マーケティングの所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-185">Click **Campaign marketing Owners** in the list.</span></span>

19. <span data-ttu-id="cad6f-186">**[ユーザーとグループ]** ページで、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-186">On the **People and Groups** page, click **New**.</span></span>

20. <span data-ttu-id="cad6f-187">**[共有]** ダイアログ ボックスに「 **IT スタッフ**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-187">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

21. <span data-ttu-id="cad6f-188">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-188">Click the back button on your browser.</span></span>

22. <span data-ttu-id="cad6f-189">ブラウザーの **[ユーザーとグループ]** タブを閉じ、ブラウザーの **[キャンペーン マーケティング - ホーム]** タブをクリックし、**[サイトのアクセス許可]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-189">Close the **People and Groups** tab in your browser, click the **Campaign marketing-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="cad6f-190">権限を構成した結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-190">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="cad6f-191">**[キャンペーン マーケティング - メンバー]** SharePoint グループには、**[戦略的シニア スタッフ]** グループ (Candidate、ChiefOfStaff、および Strategic1 ユーザー アカウントを含む)、**[キャンペーン マーケティング]** グループ (グローバル管理者ユーザー アカウントを含む)、**[分析スタッフ]** グループ (DataScientist1 ユーザー アカウントを含む)、および **Regular1** ユーザー アカウントのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-191">The **Campaign marketing-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains the Candidate, ChiefOfStaff, and Strategic1 user accounts), the **Campaign marketing** group (which contains the global administrator user account), the **Analytics staff** group (which contains the DataScientist1 user account), and the **Regular1** user account.</span></span>

- <span data-ttu-id="cad6f-192">**[キャンペーン マーケティング - 所有者]** SharePoint グループには、**[IT スタッフ]** グループ (ITAdmin1 と ITAdmin2 ユーザー アカウントのみを含む) のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-192">The **Campaign marketing-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="cad6f-193">**[マーケティング キャンペーン - 閲覧者]** SharePoint グループには、グループまたはユーザー アカウントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="cad6f-193">The **Campaign marketing-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="cad6f-194">メンバーはサイト レベルのアクセス許可を変更できません (これを実行できるのは、**[キャンペーン マーケティング- 所有者]** グループのメンバーだけです)。</span><span class="sxs-lookup"><span data-stu-id="cad6f-194">Members cannot modify site-level permissions (this can only be done by members of the **Campaign marketing-Owners** group).</span></span>

- <span data-ttu-id="cad6f-195">他のユーザー アカウントは、サイトやそのリソースにアクセスできませんが、サイトへのアクセスを要求することができます。これにより、ITAdmin1 ユーザー アカウントのメールボックスに電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-195">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>

<span data-ttu-id="cad6f-196">次に、キャンペーン マーケティング チーム サイトのドキュメント フォルダーを [機密] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-196">Next, configure the documents folder of the Campaign marketing team site for the Sensitive label.</span></span>

1. <span data-ttu-id="cad6f-197">ブラウザーの **[キャンペーン マーケティング - ホーム]** タブをクリックして、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-197">In the **Campaign marketing-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="cad6f-198">[設定] アイコンをクリックしてから、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-198">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="cad6f-199">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="cad6f-200">**[設定 - ラベルの適用]** で **[機密]** をクリックし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-200">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="cad6f-p103">次に、機密ラベルの付いた SharePoint Online チーム サイト上のドキュメントを組織の外部と共有しようとしているユーザーに通知するデータ損失防止 (DLP) ポリシーを構成します。この DLP ポリシーは、キャンペーン マーケティング サイトのリソースに適用します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p103">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label outside the organization. This DLP policy will apply to resources in the Campaign marketing site.</span></span>

1. <span data-ttu-id="cad6f-203">ブラウザーの **Microsoft Office ホーム** のタブで、**[セキュリティとコンプライアンス]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-203">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

2. <span data-ttu-id="cad6f-204">ブラウザーの新しい **[Security & Compliance]** タブで、**[データ損失対策] > [ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-204">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

3. <span data-ttu-id="cad6f-205">
            \*\*[データ損失防止]\*\* ウィンドウで、**[+ ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-205">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

4. <span data-ttu-id="cad6f-206">**[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、 **[カスタム]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-206">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="cad6f-207">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **機密ラベル SharePoint Online チーム サイト**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-207">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="cad6f-208">**[場所の選択]** ウィンドウで、 **[自分で特定の場所を選択する]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-208">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="cad6f-209">場所の一覧で、 **Exchange メール** と **OneDrive アカウント** の場所を無効にし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-209">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="cad6f-210">**[保護する機密性の高い情報の種類をカスタマイズする]** ウィンドウで、 **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-210">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="cad6f-211">**[保護するコンテンツの種類を選択する]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、 **[ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-211">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

10. <span data-ttu-id="cad6f-212">**[ラベル]** ウィンドウで、 **[+ 追加]** をクリックして、 **[機密]** ラベルを選択し、 **[追加]** をクリックしてから、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-212">In the **Labels** pane, click **+ Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="cad6f-213">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-213">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="cad6f-214">**保護する機密情報の種類のカスタマイズ** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-214">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="cad6f-215">**機密情報が検出された場合の処理** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-215">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="cad6f-216">**ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-216">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="cad6f-217">次の内容をテキスト ボックスに入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-217">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="cad6f-p104">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="cad6f-221">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-221">Click **OK**.</span></span>

17. <span data-ttu-id="cad6f-222">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、 **[ユーザーが共有できないようにし、共有コンテンツへのアクセスを制限する]** チェックボックスをクリアしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-222">In the **What do you want to do if we detect sensitive info?** pane, clear the **Block people from sharing, and restrict access to shared content** check box, and then click **Next**.</span></span>

18. <span data-ttu-id="cad6f-223">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-223">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="cad6f-224">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-224">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="campaign-strategy-team-site"></a><span data-ttu-id="cad6f-225">キャンペーン戦略チーム サイト</span><span class="sxs-lookup"><span data-stu-id="cad6f-225">Campaign strategy team site</span></span>

<span data-ttu-id="cad6f-226">キャンペーン戦略リソース用に機密性の高いレベルで分離された SharePoint Online チーム サイトを作成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-226">To create an isolated SharePoint Online team site at the highly confidential level for campaign strategy resources, do the following:</span></span>

1. <span data-ttu-id="cad6f-227">必要に応じて、ローカル コンピューターのブラウザーを使用し、全体管理者アカウントで管理センター (<https://admin.microsoft.com>) にサイン インします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-227">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="cad6f-228">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-228">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="cad6f-229">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-229">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="cad6f-230">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-230">On the **Create a site** page, click **Team site**.</span></span>

5. <span data-ttu-id="cad6f-231">**[チーム サイト名]** に、「**キャンペーン戦略**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-231">In **Team site name**, type **Campaign strategy**.</span></span>

6. <span data-ttu-id="cad6f-232">**[チーム サイトの説明]** に、「**キャンペーン戦略の SharePoint サイト (高機密)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-232">In **Team site description**, type **SharePoint site for campaign strategy (highly confidential)**.</span></span>

7. <span data-ttu-id="cad6f-233">**[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-233">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>

8. <span data-ttu-id="cad6f-234">**[誰を追加しますか]** ウィンドウで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-234">On the **Who do you want to add?** pane, click **Finish**.</span></span>

9. <span data-ttu-id="cad6f-235">ブラウザーの新しい **[キャンペーン戦略]** タブのツール バーで、設定アイコンをクリックし、**[サイトのアクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-235">On the new **Campaign strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

10. <span data-ttu-id="cad6f-236">**[サイトの権限]** ウィンドウで、**[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-236">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

11. <span data-ttu-id="cad6f-237">ブラウザーの新しい **[アクセス許可]** タブで、 **[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-237">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>

12. <span data-ttu-id="cad6f-238">**[アクセス要求の設定]** ダイアログ ボックスの **[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可します]** と **[メンバーが、他のユーザーをサイト メンバー グループに招待することを許可します]** をクリアし (これによって、3 つのチェック ボックスがすべてクリアされる)、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-238">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>

13. <span data-ttu-id="cad6f-239">一覧にある **[キャンペーン戦略のメンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-239">Click **Campaign strategy Members** in the list.</span></span>

14. <span data-ttu-id="cad6f-240">**[ユーザーとグループ]** ページで、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-240">On the **People and Groups** page, click **New**.</span></span>

15. <span data-ttu-id="cad6f-241">**[共有]** ダイアログ ボックスに「**戦略的シニア スタッフ**」と入力し、それを選択して、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-241">In the **Share** dialog box, type **Senior and strategic staff**, select it, and then click **Share**.</span></span>

16. <span data-ttu-id="cad6f-242">一覧にある **[キャンペーン戦略の所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-242">Click **Campaign strategy Owners** in the list.</span></span>

17. <span data-ttu-id="cad6f-243">**[ユーザーとグループ]** ページで、**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-243">On the **People and Groups** page, click **New**.</span></span>

18. <span data-ttu-id="cad6f-244">**[共有]** ダイアログ ボックスに「 **IT スタッフ**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-244">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>

19. <span data-ttu-id="cad6f-245">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-245">Click the back button on your browser.</span></span>

20. <span data-ttu-id="cad6f-246">ブラウザーの **[ユーザーとグループ]** タブを閉じ、ブラウザーの **[キャンペーン戦略 - ホーム]** タブをクリックし、**[サイトのアクセス許可]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-246">Close the **People and Groups** tab in your browser, click the **Campaign strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="cad6f-247">権限を構成した結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-247">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="cad6f-248">**[キャンペーン戦略 - メンバー]** SharePoint グループには、**[戦略的シニア スタッフ]** グループ (Candidate、ChiefOfStaff、および Strategic1 ユーザー アカウントのみを含む)、**[キャンペーン戦略]** グループ (グローバル管理者ユーザー アカウントのみを含む) のみが含まれます。
</span><span class="sxs-lookup"><span data-stu-id="cad6f-248">The **Campaign strategy-Members** SharePoint group contains only the **Senior and strategic staff** group (which contains only the Candidate, ChiefOfStaff, and Strategic1 user accounts) and the **Campaign strategy** group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="cad6f-249">**[キャンペーン戦略 - 所有者]** SharePoint グループには、**[IT スタッフ]** グループ (ITAdmin1 と ITAdmin2 ユーザー アカウントのみを含む) のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-249">The **Campaign strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>

- <span data-ttu-id="cad6f-250">**[キャンペーン戦略 - 閲覧者]** SharePoint グループには、グループまたはユーザー アカウントは含まれていません。	</span><span class="sxs-lookup"><span data-stu-id="cad6f-250">The **Campaign strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>

- <span data-ttu-id="cad6f-251">メンバーはサイト レベルのアクセス許可を変更できません (これを実行できるのは、**[キャンペーン戦略 - 所有者]** グループのメンバーだけです)。</span><span class="sxs-lookup"><span data-stu-id="cad6f-251">Members cannot modify site-level permissions (this can only be done by members of the **Campaign strategy-Owners** group).</span></span>

- <span data-ttu-id="cad6f-p105">その他のユーザー アカウントは、サイトやそのリソースにアクセスすることも、そのサイトへのアクセスを要求することもできません。サイトへの追加のアクセス許可は、グローバル管理者または **[キャンペーン戦略 - 所有者]** グループのメンバーが行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Campaign strategy-Owners** group.</span></span>

<span data-ttu-id="cad6f-254">次に、キャンペーン戦略チーム サイトのドキュメント フォルダーを [高機密] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-254">Next, configure the documents folder of the Campaign strategy team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="cad6f-255">ブラウザーの **[キャンペーン戦略 - ホーム]** タブをクリックして、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-255">In the **Campaign strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="cad6f-256">[設定] アイコンをクリックしてから、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-256">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="cad6f-257">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-257">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="cad6f-258">**[設定 - ラベルの適用]** で **[高機密]** をクリックし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-258">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="cad6f-p106">次に、高機密ラベルの付いた SharePoint Online チーム サイト上のドキュメントをユーザーが組織の外部と共有するのをブロックする DLP ポリシーを構成します。この PLD は、キャンペーン戦略サイトのリソースに適用します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p106">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label outside the organization. This DLP policy will apply to resources in the Campaign strategy site.</span></span>

1. <span data-ttu-id="cad6f-261">必要に応じて、ローカル コンピューターのブラウザーを使用して、セキュリティ管理者または会社管理者の役割のアカウントで、管理センター (<https://admin.microsoft.com>) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-261">If needed, use a browser on your local computer and sign in to the admin center (<https://admin.microsoft.com>) with an account that has the Security Administrator or Company Administrator role.</span></span>

2. <span data-ttu-id="cad6f-262">ブラウザーの **Microsoft Office ホーム** のタブで、**[セキュリティとコンプライアンス]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-262">From the **Microsoft Office Home** tab in your browser, click the **Security & Compliance** tile.</span></span>

3. <span data-ttu-id="cad6f-263">ブラウザーの新しい **[Security & Compliance]** タブで、**[データ損失対策] > [ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-263">On the new **Security & Compliance** tab in your browser, click **Data loss prevention > Policy**.</span></span>

4. <span data-ttu-id="cad6f-264">
            \*\*[データ損失防止]\*\* ウィンドウで、**[+ ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-264">In the **Data loss prevention** pane, click **+ Create a policy**.</span></span>

5. <span data-ttu-id="cad6f-265">**[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、 **[カスタム]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-265">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

6. <span data-ttu-id="cad6f-266">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **高機密ラベル SharePoint Online チーム サイト**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-266">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>

7. <span data-ttu-id="cad6f-267">**[場所の選択]** ウィンドウで、 **[自分で特定の場所を選択する]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-267">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

8. <span data-ttu-id="cad6f-268">場所の一覧で、 **Exchange メール** と **OneDrive アカウント** の場所を無効にし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-268">In the list of locations, disable the **Exchange email** and **OneDrive accounts** locations, and then click **Next**.</span></span>

9. <span data-ttu-id="cad6f-269">**[保護する機密性の高い情報の種類をカスタマイズする]** ウィンドウで、 **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-269">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>

10. <span data-ttu-id="cad6f-270">**[保護するコンテンツの種類を選択する]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、 **[ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-270">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Labels**.</span></span>

11. <span data-ttu-id="cad6f-271">**[ラベル]** ウィンドウで、 **[+ 追加]** をクリックして、 **[高機密]** ラベルを選択し、 **[追加]** をクリックしてから、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-271">In the **Labels** pane, click **+ Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

12. <span data-ttu-id="cad6f-272">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-272">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

13. <span data-ttu-id="cad6f-273">**保護する機密情報の種類のカスタマイズ** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-273">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>

14. <span data-ttu-id="cad6f-274">**機密情報が検出された場合の処理** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-274">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

15. <span data-ttu-id="cad6f-275">**ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-275">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

16. <span data-ttu-id="cad6f-276">次の内容をテキスト ボックスに入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-276">In the text box, type or paste in the following:</span></span>

    - <span data-ttu-id="cad6f-p107">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p107">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

17. <span data-ttu-id="cad6f-280">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-280">Click **OK**.</span></span>

18. <span data-ttu-id="cad6f-281">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、 **[業務の妥当性を要求してオーバーライドする]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-281">In the **What do you want to do if we detect sensitive info?** pane, select **Require a business justification to override**, and then click **Next**.</span></span>

19. <span data-ttu-id="cad6f-282">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-282">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

20. <span data-ttu-id="cad6f-283">**[設定の確認]** ウィンドウで、 **[作成]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-283">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="cad6f-284">「[Microsoft 365 管理センターから Azure Rights Management をアクティブ化する方法](/information-protection/deploy-use/activate-office365)」にある指示に従います。</span><span class="sxs-lookup"><span data-stu-id="cad6f-284">Use the instructions in [Activate Azure RMS with the Microsoft 365 admin center](/information-protection/deploy-use/activate-office365).</span></span>

<span data-ttu-id="cad6f-285">次に、以下の手順に従い、保護とアクセス許可用の新しいスコープ付きポリシーとサブラベルを使用して、Azure Information Protection を構成します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-285">Next, configure Azure Information Protection with a new scoped policy and sub-label for protection and permissions with the following steps:</span></span>

1. <span data-ttu-id="cad6f-286">セキュリティ管理者または会社管理者のロールのアカウントを使用して、管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-286">Sign in to the admin center with an account that has the Security Administrator or Company Administrator role.</span></span> <span data-ttu-id="cad6f-287">詳細については、「[一般法人向け Office 365 にサインインする場所](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad6f-287">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="cad6f-288">ブラウザーで別のタブを開き、Azure portal (<https://portal.azure.com>) に移動します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-288">In a separate tab of your browser, go to the Azure portal (<https://portal.azure.com>).</span></span>

3. <span data-ttu-id="cad6f-289">検索ウィンドウで「**information**」と入力し、[**Azure Information Protection**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-289">In the search pane, type **information**, and then click **Azure Information Protection**.</span></span>

4. <span data-ttu-id="cad6f-290">**[ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-290">Click **Labels**.</span></span>

5. <span data-ttu-id="cad6f-291">**[非常に機密性の高い社外秘]** ラベルを右クリックしてから、**[サブラベルの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-291">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>

6. <span data-ttu-id="cad6f-292">**[名前]** に「**CampaignStrategy**」と入力し、**[説明]** に「**キャンペーン戦略チーム サイトのドキュメントのラベル**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-292">Type **CampaignStrategy** in **Name** and **Label for documents in the Campaign strategy team site** in **Description**.</span></span>

7. <span data-ttu-id="cad6f-293">**[このラベルを含むドキュメントやメールに対するアクセス許可の設定]** で、**[保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-293">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>

8. <span data-ttu-id="cad6f-294">**[保護]** セクションで **[Azure (クラウド キー)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-294">In the **Protection** section, click **Azure (cloud key)**.</span></span>

9. <span data-ttu-id="cad6f-295">**[保護]** ブレードで **[保護設定]** の **[+ アクセス許可の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-295">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>

10. <span data-ttu-id="cad6f-296">**[アクセス許可を追加する]** ブレードの **[ユーザーとグループの指定]** で、**[+ ディレクトリを参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-296">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>

11. <span data-ttu-id="cad6f-297">**[AAD ユーザーとグループ]** ウィンドウで、**[戦略的シニア スタッフ]** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-297">On the **AAD Users and Groups** pane, select **Senior and strategic staff**, and then click **Select**.</span></span>

12. <span data-ttu-id="cad6f-298">**[事前設定またはカスタムの設定からアクセス許可を選択する]** の **[カスタム]** をクリックし、次に **[権限の表示]**、**[コンテンツの編集]**、**[保存]**、**[返信]**、**[全員へ返信]** の各チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-298">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>

13. <span data-ttu-id="cad6f-299">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-299">Click **OK** twice.</span></span>

14. <span data-ttu-id="cad6f-300">**[サブラベル]** ブレードで **[保存]** をクリックし、次に **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-300">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

15. <span data-ttu-id="cad6f-301">**[Azure Information Protection]** ブレードで **[ポリシー] > [+ 新しいポリシーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-301">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>

16. <span data-ttu-id="cad6f-302">**[名前]** に「**CampaignStrategy**」と入力し、**[説明]** に「**キャンペーン戦略チーム サイトのドキュメント**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-302">Type **CampaignStrategy** in **Name** and **Documents in the Campaign strategy team site** in **Description**.</span></span>

17. <span data-ttu-id="cad6f-303">**[このポリシーを取得するユーザーまたはグループを選択してください] > [ユーザー/グループ]** をクリックし、**[戦略的シニア スタッフ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cad6f-303">Click **Select which users or groups get this policy > User/Groups**, and then select **Senior and strategic staff**.</span></span>

18. <span data-ttu-id="cad6f-304">**[選択]\>[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-304">Click **Select \> OK**.</span></span>

19. <span data-ttu-id="cad6f-p109">**[ラベルの追加または削除]** をクリックします。**[ポリシー: ラベルの追加または削除]** ウィンドウで、**[CampaignStrategy]** をクリックしてから、**[OK]** をクリックます。</span><span class="sxs-lookup"><span data-stu-id="cad6f-p109">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **CampaignStrategy**, and then click **OK**.</span></span>

20. <span data-ttu-id="cad6f-307">**[保存]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad6f-307">Click **Save**, and then click **OK**.</span></span>

<span data-ttu-id="cad6f-308">これで、この 4 つのサイトでドキュメントの作成を開始し、さまざまなユーザー アカウントを使用してサイトへのアクセスをテストする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="cad6f-308">You are now ready to begin creating documents in these four sites and test access to them with various user accounts.</span></span>

<span data-ttu-id="cad6f-309">Azure Information Protection とこの新しいラベルでドキュメントを保護するには、テスト マシンに [Azure Information Protection クライアントをインストール](/information-protection/rms-client/install-client-app)し、管理センターから Office をインストールしてから、試用版サブスクリプションの **[戦略的シニア スタッフ]** グループのアカウントを使用して Microsoft Word からサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cad6f-309">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **Senior and strategic staff** group of your trial subscription.</span></span>

## <a name="see-also"></a><span data-ttu-id="cad6f-310">関連項目</span><span class="sxs-lookup"><span data-stu-id="cad6f-310">See Also</span></span>

[<span data-ttu-id="cad6f-311">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="cad6f-311">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="cad6f-312">選挙運動の開発/テスト環境用にグループとユーザーを構成する</span><span class="sxs-lookup"><span data-stu-id="cad6f-312">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="cad6f-313">クラウド導入のテスト ラボ ガイド (TLG)</span><span class="sxs-lookup"><span data-stu-id="cad6f-313">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="cad6f-314">Microsoft 365 ソリューションおよびアーキテクチャ センター</span><span class="sxs-lookup"><span data-stu-id="cad6f-314">Microsoft 365 solution and architecture center</span></span>](../../solutions/index.yml)