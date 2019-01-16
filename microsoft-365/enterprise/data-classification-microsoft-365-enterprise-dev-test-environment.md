---
title: Microsoft 365 企業のデータのクラス分けのテスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: ガイドを使用してこのテスト ラボを作成し、Microsoft 365 エンタープライズ テスト環境でドキュメントを Office 365 のラベルを使用します。
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869613"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8e682-103">Microsoft 365 企業のデータのクラス分けのテスト環境</span><span class="sxs-lookup"><span data-stu-id="8e682-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8e682-104">この資料の手順についてで Microsoft 365 エンタープライズ テスト環境で Office 365 の保存期間のラベルを使用してデータのクラス分けを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e682-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="8e682-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e682-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8e682-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="8e682-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8e682-108">最小要件で軽量な方法で Office 365 のラベルを設定する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="8e682-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8e682-109">シミュレートされた企業で Office 365 のラベルを設定する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="8e682-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e682-p101">Office 365 のラベルのテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="8e682-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="8e682-112">フェーズ 2: Office 365 のラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="8e682-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="8e682-113">このフェーズでは、SharePoint Online のドキュメント フォルダーのアイテム保持ポリシーのさまざまなレベルのラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e682-113">In this phase, you create the labels for the different levels of retention for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="8e682-p102">必要な場合プライベート インターネット ブラウザーのインスタンスを使用し、グローバル管理者アカウントを使用して Office のポータルにサインインします。ヘルプについては、 [Office 365 にサインインするための場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e682-p102">If needed, use a private instance of your Internet browser and sign in to the Office portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="8e682-116">**[Microsoft Office Home]** タブで、**[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="8e682-117">ブラウザーの新しい **[Office 管理者センター]** タブで、**[管理センター] > [セキュリティとコンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="8e682-p103">新しいから**ホーム ・ セキュリティ&amp;準拠**タブ、ブラウザーのをクリックして**分類 > ラベル**。**ホーム > ラベル**ウィンドウで、[**保存**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-p103">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**. From the **Home > Labels** pane, click the **Retention** tab.</span></span>
    
5. <span data-ttu-id="8e682-120">**ラベルの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-120">Click **Create a label**.</span></span>
    
6. <span data-ttu-id="8e682-121">**[ラベルに名前をつける]** ウィンドウで、「 **内部パブリック**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-121">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="8e682-122">**[ラベル設定]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-122">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="8e682-123">**[設定の確認]** ウィンドウで、 **[このラベルを作成する]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-123">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="8e682-124">次の追加ラベルについて手順 5 から 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8e682-124">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="8e682-125">Kirkland</span><span class="sxs-lookup"><span data-stu-id="8e682-125">Private</span></span>
    
  - <span data-ttu-id="8e682-126">機密</span><span class="sxs-lookup"><span data-stu-id="8e682-126">Sensitive</span></span>
    
  - <span data-ttu-id="8e682-127">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="8e682-127">Highly Confidential</span></span>
    
10. <span data-ttu-id="8e682-128">**[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-128">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="8e682-129">**[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-129">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="8e682-130">**[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="8e682-130">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="8e682-131">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-131">Click **Done**.</span></span>
    
14. <span data-ttu-id="8e682-132">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-132">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="8e682-133">**[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-133">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="8e682-134">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-134">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="8e682-135">**[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-135">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="8e682-136">メモを公開するのには、ラベルには数分をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e682-136">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="8e682-137">フェーズ 3: Office 365 の保存期間のラベルをドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="8e682-137">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="8e682-138">このフェーズでは、SharePoint Online サイトの [ドキュメント] フォルダー内のファイルの既定のラベルの動作を検出し、ドキュメントのラベルを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="8e682-138">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="8e682-139">最初に、機密レベルの SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e682-139">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="8e682-p104">ブラウザーを使用して、ローカル コンピューター上で、グローバル管理者アカウントを使用して Office のポータルにサインインします。ヘルプについては、 [Office 365 にサインインするための場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e682-p104">Using a browser on your local computer, sign in to the Office portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="8e682-142">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-142">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="8e682-143">お使いのブラウザーで新しい**SharePoint** ] タブ、[**サイトを作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-143">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="8e682-144">**[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-144">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="8e682-145">**チームのサイト名**、 **SensitiveFiles**を入力します。</span><span class="sxs-lookup"><span data-stu-id="8e682-145">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="8e682-146">**チーム サイトの説明**] には、**機密性の高いファイルを SharePoint サイト**を入力します。</span><span class="sxs-lookup"><span data-stu-id="8e682-146">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="8e682-147">**[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-147">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="8e682-148">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-148">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="8e682-149">次に、機密性の高いラベルの SensitiveFiles のチーム サイトの [ドキュメント] フォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e682-149">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="8e682-150">お使いのブラウザーの [ **SensitiveFiles** ] タブで [**ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-150">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="8e682-151">設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-151">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="8e682-152">**[権限と管理]** をクリックして、**[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-152">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="8e682-153">**ラベルの設定の適用**] で、ドロップ ダウン ボックスで、**重要な**選択し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-153">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="8e682-154">次に、SensitiveFiles サイトに新しいドキュメントを作成し、そのラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="8e682-154">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="8e682-155">[ドキュメント] フォルダーをクリックして**新規 > Word 文書**。</span><span class="sxs-lookup"><span data-stu-id="8e682-155">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="8e682-p105">白紙の文書でテキストを入力します。テキストを保存するを待ちます。</span><span class="sxs-lookup"><span data-stu-id="8e682-p105">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="8e682-158">メニュー バーの [**共有ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-158">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="8e682-159">**Document.docx**ファイル名の横にある Word のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-159">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="8e682-160">[**プロパティ**] セクションの [**保存期間のラベルを適用**] の右側のペインでドキュメントが自動的に適用される**機密**ラベルをあったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e682-160">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="8e682-161">**すべてを編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-161">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="8e682-162">**Document.docx**ウィンドウで、[**ラベルの適用**] は、**機密度の高い**ラベルを選択し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e682-162">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="8e682-163">情報と実稼働環境で Office 365 の保存のラベルへのリンクの**情報の保護**の段階では、[環境内の分類を構成する](infoprotect-configure-classification.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e682-163">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8e682-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="8e682-164">Next step</span></span>

<span data-ttu-id="8e682-165">追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e682-165">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e682-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e682-166">See also</span></span>

[<span data-ttu-id="8e682-167">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="8e682-167">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8e682-168">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="8e682-168">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8e682-169">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="8e682-169">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 