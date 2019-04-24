---
title: Microsoft 365 Enterprise テスト環境のデータ分類
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 エンタープライズテスト環境のドキュメントに対して Office 365 保持ラベルを作成して使用します。
ms.openlocfilehash: 3d64cd245e117813cb4c81a6e9099cd1a0120317
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283540"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ddb99-103">Microsoft 365 Enterprise テスト環境のデータ分類</span><span class="sxs-lookup"><span data-stu-id="ddb99-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ddb99-104">この記事の手順を使用して、Microsoft 365 エンタープライズテスト環境で Office 365 の保持ラベルを使用してデータ分類を構成します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ddb99-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ddb99-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ddb99-107">フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="ddb99-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ddb99-108">最小要件での軽量な方法で Office 365 の保持ラベルを構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ddb99-108">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ddb99-109">シミュレートされたエンタープライズで Office 365 の保持ラベルを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ddb99-109">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddb99-110">Office 365 の保持ラベルのテストでは、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ddb99-110">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ddb99-111">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="ddb99-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="ddb99-112">フェーズ 2: Office 365 の保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="ddb99-112">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="ddb99-113">このフェーズでは、SharePoint Online ドキュメントフォルダーのさまざまな保持レベルの保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-113">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="ddb99-114">全体管理者アカウントで、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-114">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="ddb99-115">ブラウザーの **[ホーム - Microsoft 365 コンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-115">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="ddb99-116">**[保持ラベル] > [ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-116">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="ddb99-117">**[ラベルに名前をつける]** ウィンドウで、**[ラベルに名前をつける]** のところに「**内部パブリック**」と入力してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-117">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="ddb99-118">**[ファイル計画記述子]** ウィンドウで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-118">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="ddb99-119">**[ラベルの設定]** ウィンドウで、必要に応じて **[保持]** を **[オン]** にして **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-119">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="ddb99-120">**[設定の確認]** ウィンドウで、**[ラベルを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-120">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="ddb99-121">次の名前のラベルについて、手順3-7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-121">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="ddb99-122">プライベート</span><span class="sxs-lookup"><span data-stu-id="ddb99-122">Private</span></span>
    
  - <span data-ttu-id="ddb99-123">機密</span><span class="sxs-lookup"><span data-stu-id="ddb99-123">Sensitive</span></span>
    
  - <span data-ttu-id="ddb99-124">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="ddb99-124">Highly Confidential</span></span>
  
9. <span data-ttu-id="ddb99-125">**[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-125">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="ddb99-126">**[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-126">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="ddb99-127">**[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-127">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="ddb99-128">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-128">Click **Done**.</span></span>
    
13. <span data-ttu-id="ddb99-129">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-129">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="ddb99-130">**[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-130">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="ddb99-131">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-131">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="ddb99-132">**[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-132">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="ddb99-133">保持ラベルが公開されるまでに数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ddb99-133">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="ddb99-134">フェーズ 3: ドキュメントに Office 365 の保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="ddb99-134">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="ddb99-135">このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-135">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="ddb99-136">最初に、機密レベルの SharePoint Online チームサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-136">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="ddb99-137">ローカル コンピューターのブラウザーを使用して、全体管理者アカウントで [Office 365 ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="ddb99-138">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-138">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="ddb99-139">ブラウザーの新しい [ **SharePoint** ] タブで、[**サイトの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-139">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="ddb99-140">**[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-140">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="ddb99-141">[**チームサイト名**] に、「 **SensitiveFiles**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-141">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="ddb99-142">[**チームサイトの説明**] に、「**機密ファイル用の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-142">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="ddb99-143">**[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-143">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ddb99-144">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-144">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="ddb99-145">次に、機密保持ラベル用に SensitiveFiles チームサイトのドキュメントフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-145">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="ddb99-146">ブラウザーの [ **SensitiveFiles** ] タブで、[**ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-146">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="ddb99-147">[設定] アイコンをクリックしてから、 **[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-147">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="ddb99-148">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-148">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="ddb99-149">[**設定-ラベルの適用**] で、ドロップダウンボックスで [**機密**] を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-149">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="ddb99-150">次に、SensitiveFiles サイトで新しいドキュメントを作成し、そのアイテム保持ラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-150">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="ddb99-151">documents フォルダーで、[ **New > Word document**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-151">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="ddb99-152">空白のドキュメントにテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-152">Type some text in the blank document.</span></span> <span data-ttu-id="ddb99-153">テキストが保存されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-153">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="ddb99-154">メニューバーで、[**共有ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-154">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="ddb99-155">**文書の .docx**ファイル名の横にある Word アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-155">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="ddb99-156">右側のウィンドウの [**プロパティ**] セクションの [**保持ラベルの適用**] で、ドキュメントに**機密**ラベルが自動的に適用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ddb99-156">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="ddb99-157">[**すべて編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-157">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="ddb99-158">文書の **.docx**ウィンドウの [ラベルの**適用**] で [**高機密**] ラベルを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb99-158">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="ddb99-159">Office 365 保持ラベルを運用環境に展開する方法の詳細とリンクについては、**情報保護**フェーズの「[環境の分類を構成](infoprotect-configure-classification.md)する」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddb99-159">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="ddb99-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="ddb99-160">Next step</span></span>

<span data-ttu-id="ddb99-161">テスト環境でのその他の[情報保護](m365-enterprise-test-lab-guides.md#information-protection)機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb99-161">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddb99-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddb99-162">See also</span></span>

[<span data-ttu-id="ddb99-163">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="ddb99-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ddb99-164">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="ddb99-164">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ddb99-165">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="ddb99-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 