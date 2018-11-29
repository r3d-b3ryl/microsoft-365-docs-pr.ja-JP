---
title: Microsoft 365 企業のデータのクラス分けのテスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: ガイドを使用してこのテスト ラボを作成し、Microsoft 365 エンタープライズ テスト環境でドキュメントを Office 365 のラベルを使用します。
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869613"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a30b0-103">Microsoft 365 企業のデータのクラス分けのテスト環境</span><span class="sxs-lookup"><span data-stu-id="a30b0-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a30b0-104">この資料の手順についてで Microsoft 365 エンタープライズ テスト環境で Office 365 のラベルを使用してデータのクラス分けを構成します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a30b0-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a30b0-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a30b0-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a30b0-108">最小要件で軽量な方法で Office 365 のラベルを設定する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a30b0-109">シミュレートされた企業で Office 365 のラベルを設定する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a30b0-p101">Office 365 のラベルのテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="a30b0-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="a30b0-112">フェーズ 2: Office 365 のラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="a30b0-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="a30b0-113">このフェーズでは、SharePoint Online のドキュメント フォルダーのセキュリティのさまざまなレベルのラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="a30b0-p102">必要な場合プライベート インターネット ブラウザーのインスタンスを使用し、グローバル管理者アカウントを使用して Office 365 ポータルにサインインします。ヘルプについては、 [Office 365 にサインインするための場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a30b0-p102">If needed, use a private instance of your Internet browser and sign in to the Office 365 portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a30b0-116">**[Microsoft Office Home]** タブで、**[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="a30b0-117">ブラウザーの新しい **[Office 管理者センター]** タブで、**[管理センター] > [セキュリティとコンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="a30b0-118">ブラウザーの新しい **[ホーム – セキュリティとコンプライアンス]** タブをクリックして、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="a30b0-119">**[ホーム] > [ラベル]** ウィンドウで、 **[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="a30b0-120">**[ラベルに名前をつける]** ウィンドウで、「 **内部パブリック**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="a30b0-121">**[ラベル設定]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="a30b0-122">**[設定の確認]** ウィンドウで、 **[このラベルを作成する]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="a30b0-123">次の追加ラベルについて手順 5 から 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="a30b0-124">Kirkland</span><span class="sxs-lookup"><span data-stu-id="a30b0-124">Private</span></span>
    
  - <span data-ttu-id="a30b0-125">機密</span><span class="sxs-lookup"><span data-stu-id="a30b0-125">Sensitive</span></span>
    
  - <span data-ttu-id="a30b0-126">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="a30b0-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="a30b0-127">**[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="a30b0-128">**[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="a30b0-129">**[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="a30b0-130">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="a30b0-131">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="a30b0-132">**[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="a30b0-133">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="a30b0-134">**[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="a30b0-135">メモを公開するのには、ラベルには数分をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a30b0-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="a30b0-136">フェーズ 3: Office 365 のラベルをドキュメントに適用します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="a30b0-137">このフェーズでは、SharePoint Online サイトの [ドキュメント] フォルダー内のファイルの既定のラベルの動作を検出し、ドキュメントのラベルを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="a30b0-138">最初に、機密レベルの SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="a30b0-p103">ローカル コンピューターのブラウザーを使用し、全体管理者アカウントで Office 365 ポータルにサインインします。ヘルプについては、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a30b0-p103">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a30b0-141">タイルのリストで、 **[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="a30b0-142">お使いのブラウザーで新しい**SharePoint** ] タブ、[**サイトを作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="a30b0-143">**[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="a30b0-144">**チームのサイト名**、 **SensitiveFiles**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="a30b0-145">**チーム サイトの説明**] には、**機密性の高いファイルを SharePoint サイト**を入力します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="a30b0-146">**[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="a30b0-147">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="a30b0-148">次に、機密性の高いラベルの SensitiveFiles のチーム サイトの [ドキュメント] フォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="a30b0-149">お使いのブラウザーの [ **SensitiveFiles** ] タブで [**ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="a30b0-150">設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="a30b0-151">**[権限と管理]** をクリックして、**[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="a30b0-152">**ラベルの設定の適用**] で、ドロップ ダウン ボックスで、**重要な**選択し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="a30b0-153">次に、SensitiveFiles サイトに新しいドキュメントを作成し、そのラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="a30b0-154">[ドキュメント] フォルダーをクリックして**新規 > Word 文書**。</span><span class="sxs-lookup"><span data-stu-id="a30b0-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="a30b0-p104">白紙の文書でテキストを入力します。テキストを保存するを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a30b0-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="a30b0-157">メニュー バーの [**共有ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="a30b0-158">**Document.docx**ファイル名の横にある Word のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="a30b0-159">[**プロパティ**] セクションの [**ラベルの適用**] の右側のペインでドキュメントが自動的に適用される**機密**ラベルにあったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="a30b0-160">**すべてを編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="a30b0-161">**Document.docx**ウィンドウで、[**ラベルの適用**] は、**機密度の高い**ラベルを選択し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a30b0-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="a30b0-162">情報と実稼働環境で Office 365 のラベルへのリンクの**情報の保護**の段階では、[環境内の分類を構成する](data-classification-microsoft-365-enterprise-dev-test-environment.md)手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a30b0-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a30b0-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="a30b0-163">Next step</span></span>

<span data-ttu-id="a30b0-164">追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a30b0-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a30b0-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="a30b0-165">See also</span></span>

[<span data-ttu-id="a30b0-166">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="a30b0-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a30b0-167">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="a30b0-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a30b0-168">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="a30b0-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 