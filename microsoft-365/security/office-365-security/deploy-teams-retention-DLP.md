---
title: 保持ラベルと DLP を使用してチーム内のファイルを保護する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: '概要: 情報保護のレベルが多様なチーム内のファイルには、保持ラベルとデータ損失防止 (DLP) ポリシーを適用してください。'
ms.openlocfilehash: 94d8a02d0ea88fa8a05cd6a2c95a2db866d72fad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083407"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a><span data-ttu-id="7e95a-103">保持ラベルと DLP を使用してチーム内のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="7e95a-103">Protect files in teams with retention labels and DLP</span></span>

 
<span data-ttu-id="7e95a-104">ベースライン、機密、および高機密チームと、その基となる SharePoint サイトに対する保持ラベルとデータ損失防止 (DLP) ポリシーを設計し、展開するには、この記事の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="7e95a-104">Use the steps in this article to design and deploy retention labels and data loss prevention (DLP) policies for baseline, sensitive, and highly confidential teams and their underlying SharePoint sites.</span></span> <span data-ttu-id="7e95a-105">この 3 層の保護の詳細については、「[Microsoft Teams のファイルを保護する](secure-files-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e95a-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="7e95a-106">そのしくみ</span><span class="sxs-lookup"><span data-stu-id="7e95a-106">How this works</span></span>

1. <span data-ttu-id="7e95a-107">目的の保持ラベルを作成して、そのラベルを発行します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="7e95a-108">発行されるまでに最大 12 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7e95a-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="7e95a-109">目的の基となる SharePoint サイトで、ドキュメント ライブラリの設定を編集して、そのライブラリ内のアイテムに目的の保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-109">For the desired underlying SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="7e95a-110">保持ラベルに基づいてアクションを実行する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="7e95a-111">ユーザーが、チームの基となる SharePoint サイトのライブラリにドキュメントを追加すると、そのドキュメントには割り当てられた保持ラベルが既定で付けられます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-111">When users add a document to the underlying SharePoint site library for the team, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="7e95a-112">ユーザーは、このラベルを必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-112">Users can change the label, if needed.</span></span> <span data-ttu-id="7e95a-113">ユーザーが組織の外部とドキュメントを共有するときには、DLP によってラベルが割り当てられているかどうかが確認され、そのラベルと DLP ポリシーが一致するとアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="7e95a-114">DLP では、クレジット カード番号が含まれているファイルなど、その他のポリシーの一致も確認されます (この種のポリシーが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="7e95a-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="7e95a-115">基となる SharePoint サイトの保持ラベル</span><span class="sxs-lookup"><span data-stu-id="7e95a-115">Retention labels for your underlying SharePoint sites</span></span>

<span data-ttu-id="7e95a-116">保持ラベルを作成して、基となる SharePoint サイトに割り当てるためのフェーズは 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="7e95a-116">There are three phases to creating and then assigning retention labels to underlying SharePoint sites.</span></span>
  
### <a name="step-1-determine-the-retention-label-names"></a><span data-ttu-id="7e95a-117">ステップ 1: 保持ラベルの名前を決定する</span><span class="sxs-lookup"><span data-stu-id="7e95a-117">Step 1: Determine the retention label names</span></span>

<span data-ttu-id="7e95a-118">このフェーズでは、基となる SharePoint サイトに適用される情報保護の 4 つのレベルに応じた保持ラベルの名前を決定します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to underlying SharePoint sites.</span></span> <span data-ttu-id="7e95a-119">次の表は、各レベルに推奨される名前の一覧です。</span><span class="sxs-lookup"><span data-stu-id="7e95a-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="7e95a-120">**基となる SharePoint サイトの保護レベル**</span><span class="sxs-lookup"><span data-stu-id="7e95a-120">**underlying SharePoint sites protection level**</span></span>|<span data-ttu-id="7e95a-121">**ラベル名**</span><span class="sxs-lookup"><span data-stu-id="7e95a-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e95a-122">ベースライン - パブリック</span><span class="sxs-lookup"><span data-stu-id="7e95a-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="7e95a-123">内部パブリック</span><span class="sxs-lookup"><span data-stu-id="7e95a-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="7e95a-124">ベースライン - プライベート</span><span class="sxs-lookup"><span data-stu-id="7e95a-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="7e95a-125">プライベート</span><span class="sxs-lookup"><span data-stu-id="7e95a-125">Private</span></span>  <br/> |
|<span data-ttu-id="7e95a-126">機密</span><span class="sxs-lookup"><span data-stu-id="7e95a-126">Sensitive</span></span>  <br/> |<span data-ttu-id="7e95a-127">機密</span><span class="sxs-lookup"><span data-stu-id="7e95a-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="7e95a-128">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="7e95a-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="7e95a-129">極秘</span><span class="sxs-lookup"><span data-stu-id="7e95a-129">Highly Confidential</span></span>  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a><span data-ttu-id="7e95a-130">ステップ 2: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="7e95a-130">Step 2: Create the retention labels</span></span>

<span data-ttu-id="7e95a-131">このフェーズでは、情報保護の各レベルに応じて決定したラベルを作成して発行します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="7e95a-132">セキュリティ管理者または会社の管理者のロールが付与されたアカウントで [Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7e95a-133">ブラウザーの **[ホーム - Microsoft 365 コンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="7e95a-134">**[保持ラベル] > [ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="7e95a-135">**[ラベルの名前の設定]** ウィンドウで、ラベルの名前と、管理者およびユーザーの説明を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="7e95a-136">**[ファイル計画の記述子]** ウィンドウで、必要事項を入力してから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7e95a-137">**[ラベルの設定]** ウィンドウで、**[保持]** を **[オン]** にして保持設定を構成します (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="7e95a-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="7e95a-138">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="7e95a-139">**[設定の確認]** ウィンドウで、**[ラベルを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="7e95a-140">追加のラベルごとに、**[ラベルの作成]** をクリックして、必要に応じてこの手順のステップ 3 から 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 in this procedure as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="7e95a-141">新しいラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="7e95a-141">Publish your new labels</span></span>

<span data-ttu-id="7e95a-142">次は、新しい保持ラベルを発行するために、次に示す手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="7e95a-143">**[ラベル]** ウィンドウで、**[保持ラベル]** タブをクリックして、**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="7e95a-144">**[発行するラベルの選択]** ウィンドウで、**[発行するラベルの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="7e95a-145">**[ラベルの選択]** ウィンドウで **[追加]** をクリックして、4 つのラベルをすべて選択してから **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="7e95a-146">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="7e95a-147">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="7e95a-148">**[場所の選択]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="7e95a-149">**[ポリシーに名前をつける]** ウィンドウで、**[名前]** にラベルのセットの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7e95a-150">**[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a><span data-ttu-id="7e95a-151">ステップ 3: 基となる SharePoint サイトに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="7e95a-151">Step 3: Apply the retention labels to your underlying SharePoint sites</span></span>

<span data-ttu-id="7e95a-152">次の手順を使用して、基となる SharePoint サイトのドキュメント フォルダーに保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-152">Use these steps to apply the retention labels to the documents folders of your underlying SharePoint sites.</span></span>
  
1.  <span data-ttu-id="7e95a-153">チームから **[ファイル]** をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-153">From the team, click **Files**, and then click **Open in SharePoint**.</span></span>

2. <span data-ttu-id="7e95a-154">ブラウザーの新しい SharePoint サイト タブで、**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-154">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
3. <span data-ttu-id="7e95a-155">設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-155">Click the settings icon, and then click **Library settings**.</span></span>
    
4. <span data-ttu-id="7e95a-156">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-156">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
5. <span data-ttu-id="7e95a-157">**[設定 - ラベルの適用]** で、適切なラベルを選択してから **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-157">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
6. <span data-ttu-id="7e95a-158">SharePoint サイトのタブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-158">Close the tab for the SharePoint site.</span></span>
    
7. <span data-ttu-id="7e95a-159">ステップ 1 から 6 を繰り返して、追加の基となる SharePoint サイトに保持ラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-159">Repeat steps 1-6 to assign retention labels to your additional underlying SharePoint sites.</span></span>
    
<span data-ttu-id="7e95a-160">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-160">Here is your resulting configuration.</span></span>
  
![4 種類の基となる SharePoint サイト用の保持ラベル。](../../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a><span data-ttu-id="7e95a-162">基となる SharePoint サイトの DLP ポリシー</span><span class="sxs-lookup"><span data-stu-id="7e95a-162">DLP policies for your underlying SharePoint sites</span></span>

<span data-ttu-id="7e95a-163">以下の手順で、基となる SharePoint サイト上のドキュメントを組織外と共有するときにユーザーに通知する DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-163">Use these steps to configure a DLP policy that notifies users when they share a document on an underlying SharePoint site outside the organization.</span></span>

1. <span data-ttu-id="7e95a-164">セキュリティ管理者または社内管理者のロールが付与されたアカウントで [Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-164">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="7e95a-165">ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-165">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="7e95a-166">**[ホーム] > [データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-166">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="7e95a-167">**[テンプレートを利用するか、カスタム ポリシーを作成します]** ウィンドウで、**[カスタム]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-167">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7e95a-168">**[ポリシーに名前をつける]** ウィンドウの **[名前]** に機密レベル DLP ポリシーの名前を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-168">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7e95a-169">**[場所の選択]** ウィンドウで、**[特定の場所を選択]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-169">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7e95a-170">場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-170">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7e95a-171">**[保護するコンテンツの種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-171">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="7e95a-172">**[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-172">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="7e95a-173">**[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-173">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="7e95a-174">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-174">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7e95a-175">**保護するコンテンツの種類をカスタマイズする** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-175">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="7e95a-176">**機密性の高い情報が検出された場合に実行する操作** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-176">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7e95a-177">**ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-177">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7e95a-178">次のいずれかのヒントをテキスト ボックスに入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-178">In the text box, type or paste in one of the following tips:</span></span>
    
  - <span data-ttu-id="7e95a-p106">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="7e95a-p107">機密性の高いファイルは、暗号化によって保護されます。IT 部門によってこれらのファイルへのアクセス許可が与えられている外部ユーザーのみが、それらを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="7e95a-184">あるいは、ファイルを共有する方法について組織外のユーザーに指示する独自のポリシー ヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-184">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7e95a-185">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-185">Click **OK**.</span></span>
    
17. <span data-ttu-id="7e95a-186">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-186">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="7e95a-187">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-187">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7e95a-188">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-188">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7e95a-189">機密チームの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-189">Here is your resulting configuration for sensitive teams.</span></span>
  
![機密保持ラベルを使用した機密チーム向けの DLP ポリシー](../../media/retention-labels-sensitive-dlp.png)
  
<span data-ttu-id="7e95a-191">次に、以下の手順で、基となる SharePoint サイト上のドキュメントを組織外と共有するときにユーザーをブロックする DLP ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-191">Next, use these steps to configure a DLP policy that blocks users when they share a document on an underlying SharePoint site outside the organization.</span></span>
  
1. <span data-ttu-id="7e95a-192">ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-192">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="7e95a-193">**[データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-193">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="7e95a-194">**[テンプレートを使って開始するか、カスタム ポリシーを作成する]** ウィンドウで、 **[カスタム]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-194">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="7e95a-195">**[ポリシーに名前をつける]** ウィンドウの **[名前]** に高機密レベル DLP ポリシーの名前を入力して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-195">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="7e95a-196">**[場所の選択]** ウィンドウで、 **[自分で特定の場所を選択する]** をクリックしてから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-196">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7e95a-197">場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-197">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="7e95a-198">**[保護する機密情報の種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-198">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="7e95a-199">**[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-199">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="7e95a-200">**[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[高機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-200">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="7e95a-201">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-201">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="7e95a-202">**保護する機密情報の種類のカスタマイズ** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-202">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="7e95a-203">**機密情報が検出された場合の処理** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-203">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="7e95a-204">**ポリシー ヒントと電子メール通知のカスタマイズ** ウィンドウで、**ポリシー ヒントのテキストをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-204">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="7e95a-205">次の内容をテキスト ボックスに入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-205">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="7e95a-p108">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="7e95a-209">あるいは、ファイルを共有する方法について組織外のユーザーに指示する独自のポリシー ヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7e95a-209">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="7e95a-210">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-210">Click **OK**.</span></span>
    
17. <span data-ttu-id="7e95a-211">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[特定の量の機密情報が同時に共有されている場合に検出する]** の下で **[アクセスを制限する、またはコンテンツを暗号化する]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-211">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="7e95a-212">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-212">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="7e95a-213">**[設定の確認]** ウィンドウで、**[作成]** をクリックして、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e95a-213">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="7e95a-214">機密性の高いチームの最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="7e95a-214">Here is your resulting configuration for high confidentiality team.</span></span>
  
![高機密保持ラベルを使用した機密性の高いチーム向けの DLP ポリシー](../../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a><span data-ttu-id="7e95a-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="7e95a-216">Next step</span></span>

[<span data-ttu-id="7e95a-217">秘密度ラベルを使用してチーム内のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="7e95a-217">Protect files in teams with sensitivity labels</span></span>](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a><span data-ttu-id="7e95a-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e95a-218">See Also</span></span>

[<span data-ttu-id="7e95a-219">Microsoft Teams のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="7e95a-219">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="7e95a-220">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="7e95a-220">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


