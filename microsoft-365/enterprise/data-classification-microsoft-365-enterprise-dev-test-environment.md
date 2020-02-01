---
title: Microsoft 365 Enterprise テスト環境のデータ分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 エンタープライズテスト環境のドキュメントに対して Office 365 保持ラベルを作成して使用します。
ms.openlocfilehash: 3bda79236b2c6bc1022e9c590f50bc2bdaec2aea
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597054"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b4410-103">Microsoft 365 Enterprise テスト環境のデータ分類</span><span class="sxs-lookup"><span data-stu-id="b4410-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b4410-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="b4410-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b4410-105">この記事の手順を使用して、Microsoft 365 エンタープライズテスト環境で Office 365 の保持ラベルを使用してデータ分類を構成します。</span><span class="sxs-lookup"><span data-stu-id="b4410-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b4410-107">[ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b4410-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b4410-108">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="b4410-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b4410-109">最小要件での軽量な方法で Office 365 の保持ラベルを構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b4410-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b4410-110">シミュレートされたエンタープライズで Office 365 の保持ラベルを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b4410-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b4410-111">Office 365 の保持ラベルのテストでは、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4410-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b4410-112">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="b4410-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="b4410-113">フェーズ 2: Office 365 の保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="b4410-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="b4410-114">このフェーズでは、SharePoint Online ドキュメントフォルダーのさまざまな保持レベルの保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4410-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="b4410-115">グローバル管理者アカウントを使用して、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4410-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="b4410-116">ブラウザーの [**ホーム-Microsoft 365 セキュリティ**] タブで、[ **> 保持ラベルの分類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="b4410-117">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="b4410-118">[**ラベルに名前**をつける] ウィンドウで、[**ラベルに名前**を付ける] に「 **Internal Public** 」と入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="b4410-119">[**ファイル計画記述子**] ウィンドウで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="b4410-120">[**ラベル設定**] ウィンドウで必要に応じて、[**保持**] を **[オン**] に設定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b4410-121">[**設定の確認**] ウィンドウで、[**ラベルの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="b4410-122">次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b4410-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="b4410-123">プライベート</span><span class="sxs-lookup"><span data-stu-id="b4410-123">Private</span></span>
    
  - <span data-ttu-id="b4410-124">機密</span><span class="sxs-lookup"><span data-stu-id="b4410-124">Sensitive</span></span>
    
  - <span data-ttu-id="b4410-125">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="b4410-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="b4410-126">[**保持ラベル**] ウィンドウで、[**ラベルの発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="b4410-127">[**発行するラベルを選択**] ウィンドウで、[**発行するラベルを選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="b4410-128">[**ラベルの選択**] ウィンドウで、[**追加**] をクリックして4つすべてのラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4410-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="b4410-129">[**追加**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="b4410-130">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="b4410-131">**[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="b4410-132">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="b4410-133">[**設定の確認**] ウィンドウで、[**ラベルの発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="b4410-134">保持ラベルが公開されるまでに数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b4410-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="b4410-135">フェーズ 3: ドキュメントに Office 365 の保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="b4410-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="b4410-136">このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="b4410-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="b4410-137">最初に、機密レベルの SharePoint Online チームサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4410-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="b4410-138">ブラウザーのプライベートインスタンスを使用して、グローバル管理者アカウントを使用して[Office 365 ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b4410-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="b4410-139">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="b4410-140">ブラウザーの新しい [ **SharePoint** ] タブで、[**サイトの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="b4410-141">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="b4410-142">[**チームサイト名**] に、「 **SensitiveFiles**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b4410-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="b4410-143">[**チームサイトの説明**] に、「**機密ファイル用の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b4410-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="b4410-144">**[プライバシー設定]** で、**[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b4410-145">[**誰を追加**しますか] ウィンドウで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="b4410-146">次に、機密保持ラベル用に SensitiveFiles チームサイトのドキュメントフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b4410-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="b4410-147">ブラウザーの [ **SensitiveFiles** ] タブで、[**ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="b4410-148">[設定] アイコンをクリックしてから、**[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="b4410-149">[**権限と管理**] で、[**このリストまたはライブラリ内のアイテムにラベルを適用] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="b4410-150">このオプションが表示されない場合、保持ラベルはまだ公開されていません。</span><span class="sxs-lookup"><span data-stu-id="b4410-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="b4410-151">後でこの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="b4410-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="b4410-152">[**設定-ラベルの適用**] で、ドロップダウンボックスで [**機密**] を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="b4410-153">次に、SensitiveFiles サイトで新しいドキュメントを作成し、そのアイテム保持ラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="b4410-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="b4410-154">Documents フォルダーで、[**新しい > Word 文書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="b4410-155">空白のドキュメントにテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="b4410-155">Type some text in the blank document.</span></span> <span data-ttu-id="b4410-156">テキストが保存されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b4410-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="b4410-157">メニューバーで、[**共有ドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="b4410-158">**文書の .docx**ファイル名の横にある縦の省略記号をクリックし、[**詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="b4410-159">右側のウィンドウの [**プロパティ**] セクションの [**保持ラベルの適用**] で、ドキュメントに**機密**保持ラベルが自動的に適用されている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b4410-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="b4410-160">[**すべて編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="b4410-161">文書の **.docx**ウィンドウで、[**保持ラベルの適用**] の下の [**高機密**] ラベルを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4410-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="b4410-162">Office 365 保持ラベルを運用環境に展開する方法の詳細とリンクについては、**情報保護**フェーズの「[環境の分類を構成](infoprotect-configure-classification.md)する」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4410-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4410-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="b4410-163">Next step</span></span>

<span data-ttu-id="b4410-164">テスト環境でのその他の[情報保護](m365-enterprise-test-lab-guides.md#information-protection)機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4410-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4410-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4410-165">See also</span></span>

[<span data-ttu-id="b4410-166">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="b4410-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b4410-167">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="b4410-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b4410-168">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="b4410-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 