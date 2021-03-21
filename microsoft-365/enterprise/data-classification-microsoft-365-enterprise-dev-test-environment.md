---
title: エンタープライズ テスト環境向け Microsoft 365 のデータ分類
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
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境用の Microsoft 365 のドキュメントに保持ラベルを作成して使用します。
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919190"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="69ab4-103">エンタープライズ テスト環境向け Microsoft 365 のデータ分類</span><span class="sxs-lookup"><span data-stu-id="69ab4-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="69ab4-104">*このテスト ラボ ガイドは、Microsoft 365 for enterprise と 365 Enterprise テストOffice両方に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="69ab4-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="69ab4-105">この記事では、エンタープライズ テスト環境向け Microsoft 365 で保持ラベルを使用してデータ分類を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="69ab4-106">テスト環境でのデータの分類には、次の 3 つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="69ab4-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="69ab4-107">フェーズ 1: エンタープライズ テスト環境向け Microsoft 365 を構築する</span><span class="sxs-lookup"><span data-stu-id="69ab4-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="69ab4-108">フェーズ 2: 保持ラベルの作成</span><span class="sxs-lookup"><span data-stu-id="69ab4-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="69ab4-109">フェーズ 3: ドキュメントに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="69ab4-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="69ab4-111">Microsoft 365 for enterprise Test Lab Guide スタックのすべての記事へのビジュアル マップについては [、「Microsoft 365 for enterprise Test Lab Guide Stack」を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="69ab4-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="69ab4-112">フェーズ 1: エンタープライズ テスト環境向け Microsoft 365 を構築する</span><span class="sxs-lookup"><span data-stu-id="69ab4-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="69ab4-113">最小限の要件で保持ラベルを軽量な方法で構成する場合は、「Lightweight 基本構成」の手順 [に従ってください](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="69ab4-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="69ab4-114">シミュレートされたエンタープライズで保持ラベルを構成する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="69ab4-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69ab4-115">保持ラベルのテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="69ab4-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="69ab4-116">ここではオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。</span><span class="sxs-lookup"><span data-stu-id="69ab4-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="69ab4-117">フェーズ 2: 保持ラベルの作成</span><span class="sxs-lookup"><span data-stu-id="69ab4-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="69ab4-118">このフェーズでは、SharePoint Online ドキュメント フォルダーの異なるレベルの保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="69ab4-119">グローバル管理者アカウント [を使用して Microsoft 365](https://security.microsoft.com/homepage) セキュリティ センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="69ab4-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="69ab4-120">ブラウザーの **[ホーム - Microsoft 365 セキュリティ**] タブで、[分類保持ラベル]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="69ab4-121">[**ラベルを作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="69ab4-122">[ラベルに **名前を付け] ウィンドウで** 、[ラベルに名前を付け] に **「内部パブリック** 」と **入力** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="69ab4-123">[ファイルプラン **記述子] ウィンドウで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="69ab4-124">[ラベルの **設定] ウィンドウ** で、必要に応じて [保持] を **[オン**] に設定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="69ab4-125">[設定 **の確認] ウィンドウで** 、[ラベルの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="69ab4-126">次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="69ab4-127">プライベート</span><span class="sxs-lookup"><span data-stu-id="69ab4-127">Private</span></span>
  - <span data-ttu-id="69ab4-128">機密</span><span class="sxs-lookup"><span data-stu-id="69ab4-128">Sensitive</span></span>
  - <span data-ttu-id="69ab4-129">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="69ab4-129">Highly Confidential</span></span>
1. <span data-ttu-id="69ab4-130">[保持ラベル **] ウィンドウで** 、[ラベルの発行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="69ab4-131">[発行する **ラベルの選択] ウィンドウで** 、[発行 **するラベルの選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="69ab4-132">[ラベルの **選択] ウィンドウで** 、[追加] **を選択し** 、4 つのラベルすべてを選択します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="69ab4-133">[追加 **] を** 選択し、[完了] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="69ab4-134">[発行する **ラベルの選択] ウィンドウで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="69ab4-135">[場所の **選択] ウィンドウで、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="69ab4-136">[ポリシーに **名前を付け] ウィンドウで**、[名前] に「**組織の例**」と入力し、[次へ] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="69ab4-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="69ab4-137">[設定 **の確認] ウィンドウで、[** ラベルの発行] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="69ab4-138">保持ラベルが発行されるには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69ab4-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="69ab4-139">フェーズ 3: ドキュメントに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="69ab4-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="69ab4-140">このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="69ab4-141">まず、機密レベルの SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="69ab4-142">ブラウザーのプライベート インスタンスを使用して、グローバル管理者アカウントを使用して [Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="69ab4-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="69ab4-143">タイルの一覧で **、[SharePoint] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="69ab4-144">ブラウザーの新 **しい [SharePoint]** タブで、[サイトの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="69ab4-145">**[サイトの作成]** ページで、**[チーム サイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="69ab4-146">[チーム サイト **名] ボックスに\*\*\*\*「SensitiveFiles」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="69ab4-147">[チーム サイト **の説明] ボックス** に、「 **機密ファイルの SharePoint サイト」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="69ab4-148">[ **プライバシーの設定]** で、[ **プライベート] を選択し、メンバー** だけがこのサイトにアクセスし、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="69ab4-149">[追加 **するユーザー] ウィンドウで、[完了]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="69ab4-150">次に、SensitiveFiles チーム サイトの [ドキュメント] フォルダーを [機密性の高い保持] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="69ab4-151">ブラウザーの **[SensitiveFiles]** タブで、[ドキュメント] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="69ab4-152">[設定] **アイコンを** 選択し、[ライブラリの設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="69ab4-153">[ **アクセス許可と管理] で**、[このリスト **またはライブラリ内のアイテムにラベルを適用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="69ab4-154">このオプションが表示されない場合、保持ラベルはまだ発行されません。</span><span class="sxs-lookup"><span data-stu-id="69ab4-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="69ab4-155">後でこの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="69ab4-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="69ab4-156">[ **設定- ラベルの適用]** で、ドロップダウン ボックス **で [** 機密] を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="69ab4-157">次に、SensitiveFiles サイトに新しいドキュメントを作成し、保持ラベルを変更します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="69ab4-158">ドキュメント フォルダーで、[新しい Word 文書 **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="69ab4-159">空白の文書にテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-159">Enter some text in the blank document.</span></span> <span data-ttu-id="69ab4-160">テキストが保存されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="69ab4-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="69ab4-161">メニュー バーで、[共有ドキュメント] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="69ab4-162">ファイル名の **横Document.docx、** 垂直省略記号を選択し、[詳細] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69ab4-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="69ab4-163">右側のウィンドウの [プロパティ]**セクションの**[保持ラベルの適用] で、ドキュメントに [機密保持ラベル] が自動的に適用 **された点に** 注意してください。 </span><span class="sxs-lookup"><span data-stu-id="69ab4-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="69ab4-164">[**すべて編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69ab4-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="69ab4-165">[保存]**ウィンドウDocument.docx** [保持ラベルの **適用] で、[** 機密性の高いラベル] を選択し、[保存] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="69ab4-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="69ab4-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="69ab4-166">Next step</span></span>

<span data-ttu-id="69ab4-167">テスト環境 [の追加情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="69ab4-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="69ab4-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="69ab4-168">See also</span></span>

[<span data-ttu-id="69ab4-169">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="69ab4-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="69ab4-170">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="69ab4-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="69ab4-171">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="69ab4-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)