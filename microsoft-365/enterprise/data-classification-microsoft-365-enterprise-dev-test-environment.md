---
title: Microsoft 365 for enterprise テスト環境のデータ分類
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
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境のドキュメントに対して保持ラベルを作成して使用します。
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487734"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e019c-103">Microsoft 365 for enterprise テスト環境のデータ分類</span><span class="sxs-lookup"><span data-stu-id="e019c-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e019c-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="e019c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e019c-105">この記事では、エンタープライズテスト環境の Microsoft 365 で保持ラベルを使用してデータ分類を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e019c-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e019c-106">テスト環境でデータを分類するには、3つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="e019c-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="e019c-107">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="e019c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e019c-108">フェーズ 2: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="e019c-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="e019c-109">フェーズ 3: ドキュメントに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="e019c-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e019c-111">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e019c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e019c-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="e019c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e019c-113">最小要件での軽量な方法で保持ラベルを構成する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="e019c-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e019c-114">シミュレートされたエンタープライズで保持ラベルを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e019c-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e019c-115">保持ラベルをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e019c-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e019c-116">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="e019c-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="e019c-117">フェーズ 2: 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="e019c-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="e019c-118">このフェーズでは、SharePoint Online ドキュメントフォルダーのさまざまな保持レベルの保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e019c-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="e019c-119">グローバル管理者アカウントを使用して、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e019c-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="e019c-120">ブラウザーの [**ホーム-Microsoft 365 セキュリティ**] タブで、[**分類**  >  **保持ラベル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="e019c-121">[**ラベルを作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="e019c-122">[**ラベルに名前**をつける] ウィンドウで、[**ラベルに名前**を付ける] に「 **Internal Public** 」と入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="e019c-123">**ファイルプラン記述子**ウィンドウで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="e019c-124">必要に応じて、[ **ラベル設定** ] ウィンドウで、[ **保持** ] を **[オン**] に設定し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="e019c-125">[ **設定の確認** ] ウィンドウで、[ **ラベルの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="e019c-126">次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e019c-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="e019c-127">プライベート</span><span class="sxs-lookup"><span data-stu-id="e019c-127">Private</span></span>
  - <span data-ttu-id="e019c-128">機密</span><span class="sxs-lookup"><span data-stu-id="e019c-128">Sensitive</span></span>
  - <span data-ttu-id="e019c-129">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="e019c-129">Highly Confidential</span></span>
1. <span data-ttu-id="e019c-130">[ **保持ラベル** ] ウィンドウで、[ **ラベルの発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="e019c-131">[ **発行するラベルを選択** ] ウィンドウで、[ **発行するラベル**を選択] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="e019c-132">[ **ラベルの選択** ] ウィンドウで、[ **追加** ] を選択し、4つすべてのラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="e019c-133">[ **追加**] を選択し、[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="e019c-134">[ **発行するラベルを選択** ] ウィンドウで、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="e019c-135">[ **場所の選択** ] ウィンドウで、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="e019c-136">[**ポリシーに名前**をつける] ウィンドウで、[**名前**] に「 **Example organization** 」と入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="e019c-137">[ **設定の確認** ] ウィンドウで、[ **ラベルの発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="e019c-138">保持ラベルが公開されるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e019c-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="e019c-139">フェーズ 3: ドキュメントに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="e019c-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="e019c-140">このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="e019c-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="e019c-141">最初に、機密レベルの SharePoint Online チームサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e019c-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="e019c-142">ブラウザーのプライベートインスタンスを使用して、グローバル管理者アカウントを使用して [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e019c-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="e019c-143">タイルの一覧で、[ **SharePoint**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="e019c-144">ブラウザーの新しい [ **SharePoint** ] タブで、[ **サイトの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="e019c-145">**[サイトの作成]** ページで、**[チーム サイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="e019c-146">[ **チームサイト名** ] ボックスに「 **SensitiveFiles**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e019c-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="e019c-147">[ **チームサイトの説明** ] ボックスに、「 **機密ファイル用の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e019c-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="e019c-148">[ **プライバシー設定**] で、[ **プライベート-メンバーのみがこのサイトにアクセス可能**] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="e019c-149">[ **誰を追加** しますか] ウィンドウで、[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="e019c-150">次に、機密保持ラベル用に SensitiveFiles チームサイトのドキュメントフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e019c-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="e019c-151">ブラウザーの [ **SensitiveFiles** ] タブで、[ **ドキュメント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="e019c-152">[ **設定** ] アイコンを選択してから、[ **ライブラリの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="e019c-153">[ **権限と管理**] で、[ **このリストまたはライブラリ内のアイテムにラベルを適用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="e019c-154">このオプションが表示されない場合、保持ラベルはまだ公開されていません。</span><span class="sxs-lookup"><span data-stu-id="e019c-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="e019c-155">後でこの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="e019c-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="e019c-156">[ **設定-ラベルの適用**] で、ドロップダウンボックスで [ **機密** ] を選択し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="e019c-157">次に、SensitiveFiles サイトで新しいドキュメントを作成し、そのアイテム保持ラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="e019c-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="e019c-158">Documents フォルダーで、[**新しい**  >  **Word 文書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="e019c-159">空白のドキュメントに何らかのテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="e019c-159">Enter some text in the blank document.</span></span> <span data-ttu-id="e019c-160">テキストが保存されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="e019c-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="e019c-161">メニューバーで、[ **共有ドキュメント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="e019c-162">**Document.docx**ファイル名の横にある縦の省略記号を選択し、[**詳細**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="e019c-163">右ウィンドウの [ **プロパティ** ] セクションの [ **保持ラベルの適用**] で、ドキュメントに **機密** 保持ラベルが自動的に適用されている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e019c-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="e019c-164">[**すべて編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e019c-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="e019c-165">**Document.docx**ウィンドウで、[**保持ラベルの適用**] の下の [**高機密**] ラベルを選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e019c-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="e019c-166">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e019c-166">Next step</span></span>

<span data-ttu-id="e019c-167">テスト環境でのその他の [情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e019c-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e019c-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="e019c-168">See also</span></span>

[<span data-ttu-id="e019c-169">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e019c-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e019c-170">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="e019c-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e019c-171">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e019c-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
