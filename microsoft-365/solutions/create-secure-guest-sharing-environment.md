---
title: セキュリティで保護されたゲスト共有環境を作成する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: セキュリティで保護されたゲスト共有環境を Microsoft 365 で作成するための使用可能なオプションについては、こちらを参照してください。ゲスト アクセスによって共同作業を改善します。
ms.openlocfilehash: 0eb999d48bc0976d7c2bb32ff1bdba8d63409d81
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918468"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="d3d26-103">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="d3d26-104">この記事では、Microsoft 365 でセキュリティで保護されたゲスト共有環境を作成するためのさまざまなオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="d3d26-105">これらの例は、使用可能なオプションの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="d3d26-105">These are examples to give you an idea of the options available.</span></span> <span data-ttu-id="d3d26-106">これらの手順は、組織のセキュリティとコンプライアンスのニーズに合わせて、いろいろ組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span>

<span data-ttu-id="d3d26-107">この文書には、以下の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-107">This article includes:</span></span>

- <span data-ttu-id="d3d26-108">ゲスト用の多要素認証を設定する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-108">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="d3d26-109">ゲスト用の利用規約を設定する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-109">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="d3d26-110">ゲストがチームやサイトに対するアクセス許可をまだ必要としているか定期的に確認するため、四半期ごとのゲスト アクセス レビューを設定する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-110">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="d3d26-111">アンマネージド デバイスに対するゲストのアクセスを Web のみに制限する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-111">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="d3d26-112">ゲストを毎日認証するようにセッション タイムアウト ポリシーを構成する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-112">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="d3d26-113">高度機密プロジェクト向けの機密情報の種類を作成する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-113">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="d3d26-114">機密情報の種類を含むドキュメントに、機密ラベルを自動的に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="d3d26-114">Automatically assigning a sensitivity label to documents that contain a sensitive information type.</span></span>
- <span data-ttu-id="d3d26-115">機密ラベルの付いたファイルからゲストアクセスを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-115">Automatically removing guest access from files with a sensitivity label.</span></span>

<span data-ttu-id="d3d26-116">この記事で説明するオプションの一部には、ゲストが Azure Active Directory のアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-116">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="d3d26-117">ファイルやフォルダーをゲストと共有する際、ゲストがそのディレクトリに含まれていることを確認するには、[SharePoint および OneDrive の Azure AD B2B (プレビュー) との統合](/sharepoint/sharepoint-azureb2b-integration-preview)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-117">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="d3d26-118">この記事ではゲスト共有設定を有効化する方法については扱いません。</span><span class="sxs-lookup"><span data-stu-id="d3d26-118">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="d3d26-119">さまざまなシナリオでゲスト共有を有効化する方法の詳細については、「[組織外のユーザーとの共同作業](collaborate-with-people-outside-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-119">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="d3d26-120">ゲスト用の多要素認証を設定する</span><span class="sxs-lookup"><span data-stu-id="d3d26-120">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="d3d26-121">多要素認証を行うと、アカウントが漏洩する可能性が大幅に軽減されます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-121">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="d3d26-122">ゲストはガバナンス ポリシーやベスト プラクティスに準拠していない個人用メール アカウントを使用している可能性があるため、ゲストに対して多要素認証を必須にすることは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="d3d26-122">Since guests may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="d3d26-123">ゲストのユーザー名とパスワードが盗難された場合でも、2 番目の認証要素が要求されるため、不明なユーザーがサイトやファイルにアクセスする可能性を大幅に減少できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-123">If a guest's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="d3d26-124">この例では、Azure Active Directory で条件付きアクセス ポリシーを使用して、ゲスト用の多要素認証を設定します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-124">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="d3d26-125">ゲスト用の多要素認証を設定するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-125">To set up multi-factor authentication for guests</span></span>

1. <span data-ttu-id="d3d26-126">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-126">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d3d26-127">**[条件付きアクセス|ポリシー]** ブレードで、**[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-127">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d3d26-128">**[名前]** フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-128">In the **Name** field, type a name.</span></span>
4. <span data-ttu-id="d3d26-129">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-129">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d3d26-130">**[ユーザーとグループ]** ブレードで、**[ユーザーとグループの選択]** を選択し、**[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-130">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d3d26-131">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-131">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d3d26-132">**[クラウド アプリまたは操作]** ブレードで、**[対象]** タブの **[すべてのクラウド アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-132">On the **Cloud apps or actions** blade, select **All cloud apps** on the **Include** tab.</span></span>
8. <span data-ttu-id="d3d26-133">**[アクセス制御]** で、**[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-133">Under **Access controls**, click **Grant**.</span></span>
9. <span data-ttu-id="d3d26-134">**[許可]** ブレードで、**[多要素認証を要求する]** チェック ボックスをオンにし、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select**.</span></span>
10. <span data-ttu-id="d3d26-135">**[新規]** ブレードの **[ポリシーの有効化]** で、**[オン]** をクリックして、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-135">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="d3d26-136">これで、ゲストは、多要素認証に登録してからでなければ共有コンテンツ、サイト、チームにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="d3d26-137">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3d26-137">More information</span></span>

[<span data-ttu-id="d3d26-138">Azure AD 多要素認証 の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="d3d26-138">Planning an Azure AD Multi-Factor Authentication deployment</span></span>](/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="d3d26-139">ゲスト用の利用規約を設定する</span><span class="sxs-lookup"><span data-stu-id="d3d26-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="d3d26-140">ゲストは、お客様の組織との機密保持契約その他の法的契約に署名していないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-140">In some situations guests may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="d3d26-141">ゲストが共有ファイルにアクセスできるようにする前に、利用規約への同意をゲストに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="d3d26-142">この利用規約は、ゲストが初めて共有ファイルやサイトにアクセスしようとしたときに表示されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="d3d26-143">利用規約を作成するには、そのドキュメントを Word などのオーサリング プログラムでまず作成し、.pdf ファイルとして保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="d3d26-144">次に、このファイルを Azure AD にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="d3d26-145">Azure AD の利用規約を作成するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-145">To create an Azure AD terms of use</span></span>

1. <span data-ttu-id="d3d26-146">Azure にグローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="d3d26-147">[[利用規約]](https://aka.ms/catou) に移動します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="d3d26-148">**[新しい利用規約]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-148">Click **New terms**.</span></span>

   ![Azure AD の新しい利用規約設定のスクリーンショット](../media/azure-ad-guest-terms-of-use.png)

4. <span data-ttu-id="d3d26-150">**名前** と **表示名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-150">Type a **Name** and **Display name**.</span></span>
6. <span data-ttu-id="d3d26-151">**[利用規約のドキュメント]** には、作成した PDF ファイルを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-151">For **Terms of use document**, browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="d3d26-152">利用規約のドキュメントの言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="d3d26-153">**[ユーザーは使用条件を展開する必要があります]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-153">Set **Require users to expand the terms of use** to **On**.</span></span>
9. <span data-ttu-id="d3d26-154">**[条件付きアクセス]** の下にある **[Enforce with conditional access policy template] (条件付きアクセス ポリシーのテンプレートの適用)** リストから、**[後で条件付きアクセス ポリシーを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-154">Under **Conditional Access**, in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later**.</span></span>
10. <span data-ttu-id="d3d26-155">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-155">Click **Create**.</span></span>

<span data-ttu-id="d3d26-156">利用規約の作成が完了したら、次に、ゲストにその利用規約を表示する条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guests.</span></span>

<span data-ttu-id="d3d26-157">条件付きアクセス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-157">To create a conditional access policy</span></span>

1. <span data-ttu-id="d3d26-158">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-158">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d3d26-159">**[条件付きアクセス|ポリシー]** ブレードで、**[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-159">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d3d26-160">[**名前**] ボックスに、名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-160">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d3d26-161">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-161">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d3d26-162">**[ユーザーとグループ]** ブレードで、**[ユーザーとグループの選択]** を選択し、**[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-162">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d3d26-163">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-163">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d3d26-164">**[含める]** タブで、**[アプリを選択]** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-164">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="d3d26-165">**[選択]** ブレードで、**Microsoft Teams**、**Office 365 SharePoint Online**、**Outlook Groups** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-165">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="d3d26-166">**[アクセス制御]** で、**[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-166">Under **Access controls**, click **Grant**.</span></span>
10. <span data-ttu-id="d3d26-167">**[許可]** ブレードで、「**ゲストの利用規約**」と入力し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-167">On the **Grant** blade, select **Guest terms of use**, and then click **Select**.</span></span>
11. <span data-ttu-id="d3d26-168">**[新規]** ブレードの **[ポリシーの有効化]** で、**[オン]** をクリックして、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-168">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="d3d26-169">これで、ゲストがお客様の組織のコンテンツ、チームやサイトに初めてアクセスしようとしたときに、利用規約への同意を要求されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-169">Now, the first time a guest attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

> [!NOTE]
> <span data-ttu-id="d3d26-170">条件付きアクセスを使用するには、Azure AD Premium P1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d3d26-170">Using Conditional Access requires an Azure AD Premium P1 license.</span></span> <span data-ttu-id="d3d26-171">詳細については、[「条件付きアクセスとは」](/azure/active-directory/conditional-access/overview) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-171">For more information, see [What is Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="more-information"></a><span data-ttu-id="d3d26-172">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3d26-172">More information</span></span>

[<span data-ttu-id="d3d26-173">Azure Active Directory の利用規約</span><span class="sxs-lookup"><span data-stu-id="d3d26-173">Azure Active Directory terms of use</span></span>](/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="d3d26-174">ゲスト アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="d3d26-174">Set up guest access reviews</span></span>

<span data-ttu-id="d3d26-175">Azure AD のアクセス レビューを使用すると、さまざまなチームやグループに対するユーザー アクセスの定期的なレビューを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-175">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="d3d26-176">特に、ゲストのアクセス レビューを必須にすることにより、ゲストが必要以上に長く組織の機密情報へのアクセス権を保持しないようにできます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-176">By requiring an access review for guests specifically, you can help ensure guests do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="d3d26-177">ゲスト アクセス レビューを設定するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-177">To set up a guest access review</span></span>

1. <span data-ttu-id="d3d26-178">[[Identity Governance]](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) ページの左側のメニューで、**[アクセス レビュー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-178">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews**.</span></span>
2. <span data-ttu-id="d3d26-179">**[新しいアクセス レビュー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-179">Click **New access review**.</span></span>
3. <span data-ttu-id="d3d26-180">**[Teams + グループ]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-180">Choose the **Teams + Groups** option.</span></span>
4. <span data-ttu-id="d3d26-181">**[ゲスト ユーザーがいるすべての Microsoft 365 グループ]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-181">Choose the **All Microsoft 365 groups with guest users** option.</span></span> <span data-ttu-id="d3d26-182">グループを除外する場合は、**[除外するグループの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-182">Click **Select group(s) to exclude** if you want to exclude any groups.</span></span>
5. <span data-ttu-id="d3d26-183">**[ゲスト ユーザーのみ]** オプションを選択し、**[次へ: レビュー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-183">Choose the **Guest users only** option, and then click **Next: Reviews**.</span></span>
6. <span data-ttu-id="d3d26-184">**[レビュー担当者の選択]** で、**[グループ所有者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-184">Under **Select reviewers**, choose **Group Owner(s)**.</span></span>
7. <span data-ttu-id="d3d26-185">**[フォールバック レビュー担当者の選択]** をクリックし、フォールバック レビュー担当者を選択して、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-185">Click **Select fallback reviewers**, choose who should be the fallback reviewers, and then click **Select**.</span></span>
8. <span data-ttu-id="d3d26-186">**[レビューの繰り返しを指定する]** で、**[四半期ごと]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-186">Under **Specify recurrence of review**, choose **Quarterly**.</span></span>
9. <span data-ttu-id="d3d26-187">開始日と期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-187">Select a start date and duration.</span></span>
10. <span data-ttu-id="d3d26-188">**[終了]** で、**[しない]** を選択し、**[次へ: 設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-188">For **End**, choose **Never**, and then click **Next: Settings**.</span></span>

    ![Azure AD のアクセス レビュー タブのスクリーンショット](../media/azure-ad-create-access-review.png)

11. <span data-ttu-id="d3d26-190">**[設定]** タブで、ビジネス ルールに準拠しているかどうかの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-190">On the **Settings** tab, review the settings for compliance with your business rules.</span></span>

    ![Azure AD のアクセス レビュー設定タブのスクリーンショット](../media/azure-ad-create-access-review-settings.png)

12. <span data-ttu-id="d3d26-192">**[次へ: 確認 + 作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-192">Click **Next: Review + Create**.</span></span>
13. <span data-ttu-id="d3d26-193">**レビュー名** を入力し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-193">Type a **Review name** and review the settings.</span></span>
14. <span data-ttu-id="d3d26-194">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-194">Click **Create**.</span></span>

<span data-ttu-id="d3d26-195">重要な点として、ゲストにはチームやグループに対するアクセス権か、個々のファイルやフォルダーに対するアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-195">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="d3d26-196">ファイルやフォルダーに対するアクセス権を与えられているゲストは、特定のグループに追加できません。</span><span class="sxs-lookup"><span data-stu-id="d3d26-196">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="d3d26-197">チームやグループに属していないゲストに対してアクセス レビューを実行する場合は、Azure AD ですべてのゲストが含まれる動的グループを作成して、そのグループに対するアクセス レビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-197">If you want to do access reviews on guests who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span> <span data-ttu-id="d3d26-198">サイト所有者は、[サイトのゲスト の有効期限](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-198">Site owners can also manage [guest expiration for the site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span></span>

### <a name="more-information"></a><span data-ttu-id="d3d26-199">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3d26-199">More information</span></span>

[<span data-ttu-id="d3d26-200">Azure AD のアクセス レビューでゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="d3d26-200">Manage guest access with Azure AD access reviews</span></span>](/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="d3d26-201">グループまたはアプリケーションのアクセス レビューを Azure AD アクセス レビューで作成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-201">Create an access review of groups or applications in Azure AD access reviews</span></span>](/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guests"></a><span data-ttu-id="d3d26-202">ゲスト用の Web 専用アクセスを設定する</span><span class="sxs-lookup"><span data-stu-id="d3d26-202">Set up web-only access for guests</span></span>

<span data-ttu-id="d3d26-203">ゲストが Web ブラウザーのみを使用してチーム、サイト、ファイルにアクセスするように要求することにより、攻撃面を減少させて、管理を容易にできます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-203">You can reduce your attack surface and ease administration by requiring guests to access your teams, sites, and files by using a web browser only.</span></span>

<span data-ttu-id="d3d26-204">Microsoft 365 グループとTeamsの場合は、Azure AD の条件付きアクセスポリシーで行います。</span><span class="sxs-lookup"><span data-stu-id="d3d26-204">For Microsoft 365 Groups and Teams, this is done with an Azure AD conditional access policy.</span></span> <span data-ttu-id="d3d26-205">SharePointについては、SharePoint 管理センターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-205">For SharePoint, this is configured in the SharePoint admin center.</span></span> <span data-ttu-id="d3d26-206">( [機密ラベルを使用して、ゲストのアクセスを web のみに制限する](../compliance/sensitivity-labels-teams-groups-sites.md)ことができます)</span><span class="sxs-lookup"><span data-stu-id="d3d26-206">(You can also [use sensitivity labels to restrict guests to web-only access](../compliance/sensitivity-labels-teams-groups-sites.md).)</span></span>

<span data-ttu-id="d3d26-207">グループとチームに対して、ゲストのアクセスを 　Web のみに制限する方法</span><span class="sxs-lookup"><span data-stu-id="d3d26-207">To restrict guests to web-only access for Groups and Teams:</span></span>

1. <span data-ttu-id="d3d26-208">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-208">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d3d26-209">**[条件付きアクセス - ポリシー]** ブレードで、**[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-209">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d3d26-210">[**名前**] ボックスに、名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-210">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="d3d26-211">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-211">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d3d26-212">**[ユーザーとグループ]** ブレードで、**[ユーザーとグループの選択]** を選択し、**[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-212">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d3d26-213">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-213">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d3d26-214">**[含める]** タブで、**[アプリを選択]** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-214">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="d3d26-215">**[選択]** ブレードで、**Microsoft Teams**、**Outlookグループ** を選択し、 **選択** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-215">On the **Select** blade, select **Microsoft Teams** and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="d3d26-216">**[割り当て]** の下の **[条件]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-216">Under **Assignments**, click **Conditions**.</span></span>
10. <span data-ttu-id="d3d26-217">**[条件]** ブレードで、**[クライアント アプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-217">On the **Conditions** blade, click **Client apps**.</span></span>
11. <span data-ttu-id="d3d26-218">**[クライアント アプリ]** ブレードで、**[構成する]** の **[はい]** をクリックし、**[モバイル アプリとデスクトップ クライアント]** と **[Exchange ActiveSyncクライアント]**、および **その他のクライアント** 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-218">On the **Client apps** blade, click **Yes** for **Configure**, and then select the **Mobile apps and desktop clients**, **Exchange ActiveSync clients**, and **Other clients** settings.</span></span> <span data-ttu-id="d3d26-219">**ブラウザー** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-219">Clear the **Browser** check box.</span></span>

    ![Azure AD の条件付きアクセス クライアント アプリ設定のスクリーンショット](../media/azure-ad-conditional-access-client-mobile.png)

12. <span data-ttu-id="d3d26-221">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-221">Click **Done**.</span></span>
13. <span data-ttu-id="d3d26-222">**[アクセス制御]** で、**[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-222">Under **Access controls**, click **Grant**.</span></span>
14. <span data-ttu-id="d3d26-223">**[許可]** ブレードで、**[デバイスは準拠としてマーク済みである必要がある]** および **[Hybrid Azure AD 参加済みデバイスが必要]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-223">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device**.</span></span>
15. <span data-ttu-id="d3d26-224">**[複数のコントロールの場合]** の下の **[選択したコントロールのいずれかが必要]** を選択して、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-224">Under **For multiple controls**, select **Require one of the selected controls**, and then click **Select**.</span></span>
16. <span data-ttu-id="d3d26-225">**[新規]** ブレードの **[ポリシーの有効化]** で、**[オン]** をクリックして、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-225">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

<span data-ttu-id="d3d26-226">SharePointでゲストのアクセスを Web のみに制限するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-226">To restrict guests to web-ony access for SharePoint</span></span>

1. <span data-ttu-id="d3d26-227">[ [SharePoint 管理センター](https://admin.microsoft.com/sharepoint)で **ポリシー** を展開し、[ **アクセス制御**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-227">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), expand **Policies** and click **Access control**.</span></span>
2. <span data-ttu-id="d3d26-228">**非管理対象デバイス** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-228">Click **Unmanaged devices**.</span></span>
3. <span data-ttu-id="d3d26-229">**制限付きの web のみのアクセスを許可する** オプションを選択して、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-229">Select the **Allow limited, web-only access** option, and then click **Save**.</span></span>

<span data-ttu-id="d3d26-230">SharePoint 管理センターのこの設定では、Azure AD の条件付きアクセスポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d3d26-230">Note that this setting in the SharePoint admin center creates a supporting conditional access policy in Azure AD.</span></span>

## <a name="configure-a-session-timeout-for-guests"></a><span data-ttu-id="d3d26-231">ゲストにセッション タイムアウトを構成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-231">Configure a session timeout for guests</span></span>

<span data-ttu-id="d3d26-232">ゲストに定期的な認証を要求することにより、ゲストのデバイスがセキュリティで保護されていない場合も、不明なユーザーがお客様の組織のコンテンツにアクセスする可能性を減少できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-232">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest's device isn't kept secure.</span></span> <span data-ttu-id="d3d26-233">ゲスト用のセッション タイムアウト条件付きアクセス ポリシーを、Azure AD で設定できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-233">You can configure a session timeout conditional access policy for guests in Azure AD.</span></span>

<span data-ttu-id="d3d26-234">ゲスト セッション タイムアウト ポリシーを設定するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-234">To configure a guest session timeout policy</span></span>

1. <span data-ttu-id="d3d26-235">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="d3d26-235">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="d3d26-236">**[条件付きアクセス - ポリシー]** ブレードで、**[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-236">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="d3d26-237">**[名前]** ボックスに「*ゲスト セッション タイムアウト*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-237">In the **Name** box, type *Guest session timeout*.</span></span>
4. <span data-ttu-id="d3d26-238">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-238">Under **Assignments**, click **Users and groups**.</span></span>
5. <span data-ttu-id="d3d26-239">**[ユーザーとグループ]** ブレードで、**[ユーザーとグループの選択]** を選択し、**[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-239">On the **Users and groups** blade, select **Select users and groups**, select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="d3d26-240">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-240">Under **Assignments**, click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="d3d26-241">**[含める]** タブで、**[アプリを選択]** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-241">On the **Include** tab, select **Select apps**, and then click **Select**.</span></span>
8. <span data-ttu-id="d3d26-242">**[選択]** ブレードで、**Microsoft Teams**、**Office 365 SharePoint Online**、**Outlook Groups** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-242">On the **Select** blade, select **Microsoft Teams**, **Office 365 SharePoint Online**, and **Outlook Groups**, and then click **Select**.</span></span>
9. <span data-ttu-id="d3d26-243">**[アクセス制御]** で、**[セッション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-243">Under **Access controls**, click **Session**.</span></span>
10. <span data-ttu-id="d3d26-244">**[セッション]** ブレードで、**[サインイン頻度]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-244">On the **Session** blade, select **Sign-in frequency**.</span></span>
11. <span data-ttu-id="d3d26-245">期間として **[1]** および **[日]** を選択し、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-245">Select **1** and **Days** for the time period, and then click **Select**.</span></span>
12. <span data-ttu-id="d3d26-246">**[新規]** ブレードの **[ポリシーの有効化]** で、**[オン]** をクリックして、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-246">On the **New** blade, under **Enable policy**, click **On**, and then click **Create**.</span></span>

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="d3d26-247">極秘プロジェクト向けの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-247">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="d3d26-248">機密情報の種類は、コンプライアンス要件を適用するためにポリシー ワークフローで使用できる定義済みの文字列です。</span><span class="sxs-lookup"><span data-stu-id="d3d26-248">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="d3d26-249">Microsoft 365 コンプライアンス センターには、運転免許証番号、クレジット カード番号、銀行口座番号など、100 を超える機密情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d3d26-249">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="d3d26-250">カスタムの機密情報の種類を作成して、お客様の組織に固有のコンテンツを管理するために利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-250">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="d3d26-251">この例では、機密プロジェクト向けにカスタムの機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-251">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="d3d26-252">そのようにすると、この機密情報の種類を使用して、機密ラベルを自動的に適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-252">We can then use this sensitive information type to automatically apply a sensitivity label.</span></span>

<span data-ttu-id="d3d26-253">機密情報の種類を作成するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-253">To create a sensitive information type</span></span>

1. <span data-ttu-id="d3d26-254">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)の左側のナビゲーションで、**[分類]** を展開し、**[機密情報の種類]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-254">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification**, and then click **Sensitive info types**.</span></span>
2. <span data-ttu-id="d3d26-255">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-255">Click **Create**.</span></span>
3. <span data-ttu-id="d3d26-256">**[名前]** と **[説明]** に「**Project Saturn**」と入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-256">For **Name** and **Description**, type **Project Saturn**, and then click **Next**.</span></span>
4. <span data-ttu-id="d3d26-257">**[要素の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-257">Click **Add an element**.</span></span>
5. <span data-ttu-id="d3d26-258">**[次が含まれているコンテンツを検出する]** リストで **[キーワード]** を選択して、キーワード ボックスに「*Project Saturn*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-258">On the **Detect content containing** list, select **Keywords**, and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="d3d26-259">**[次へ]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-259">Click **Next**, and then click **Finish**.</span></span>
7. <span data-ttu-id="d3d26-260">機密情報の種類をテストするかどうかをたずねられたら、**[いいえ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-260">If asked if you would like to test the sensitive information type, click **No**.</span></span>

### <a name="more-information"></a><span data-ttu-id="d3d26-261">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3d26-261">More information</span></span>

[<span data-ttu-id="d3d26-262">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="d3d26-262">Custom sensitive information types</span></span>](/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="d3d26-263">機密情報の種類に基づいて、機密情報ラベルを割り当てる自動ラベル付けポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-263">Create an auto-labeling policy to assign a sensitivity label based on a sensitive information type</span></span>

<span data-ttu-id="d3d26-264">組織で機密情報のラベルを使用している場合、定義された機密情報の種類を含むファイルにラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-264">If you are using sensitivity labels in your organization, you can automatically apply a label to files that contain defined sensitive information types.</span></span> 

<span data-ttu-id="d3d26-265">新しい自動ラベル付けポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="d3d26-265">To create an auto-labeling policy</span></span>

1. <span data-ttu-id="d3d26-266">[Microsoft 365 コンプライアンス管理センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-266">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="d3d26-267">左側のナビゲーションで、[ **情報の保護**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-267">In the left navigation, click **Information protection**.</span></span>
3. <span data-ttu-id="d3d26-268">[**オートラベル**] タブで、[**自動ラベル付けポリシーの作成** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-268">On the **Auto-labeling** tab, click **Create auto-labeling policy**.</span></span>
4. <span data-ttu-id="d3d26-269">[ **[このラベルを適用する情報を選択** ] ページで、[ **カスタム** ] を選び、 **次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-269">On the **Choose info you want this label applied to** page, choose **Custom** and click **Next**.</span></span>
5. <span data-ttu-id="d3d26-270">ポリシーの名前と説明を入力して、**次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-270">Type a name and description for the policy and click **Next**.</span></span>
6. <span data-ttu-id="d3d26-271">[ **ラベル を適用する場所を選択する**] ページで、**SharePoint サイト** をオンにして、**サイト の選択** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-271">On the **Choose locations where you want to apply the label** page, turn on **SharePoint sites** and click **Choose sites**.</span></span>
7. <span data-ttu-id="d3d26-272">オートラベル機能を有効にするサイトの URLを追加し、**完了** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-272">Add the URLs for the sites where you want to turn on auto-labeling and click **Done**.</span></span>
8. <span data-ttu-id="d3d26-273">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-273">Click **Next**.</span></span>
9. <span data-ttu-id="d3d26-274">[**共通 または高度なルールの設定**] ページで、[**共通のルール**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-274">On the **Set up common or advanced rules** page, choose **Common rules** and click **Next**.</span></span>
10. <span data-ttu-id="d3d26-275">[**すべての場所のコンテンツのルールを定義する]** ページで、**新しいルール** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-275">On the **Define rules for content in all locations** page, click **New rule**.</span></span>
11. <span data-ttu-id="d3d26-276">[**新しいルール**]の ページで、ルールに名前を付けて、**条件の追加** をクリックし、[**コンテンツに機密情報の種類が含まれている** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-276">On the **New rule** page, give the rule a name, click **Add condition**, and then click **Content contains sensitive info types**.</span></span>
12. <span data-ttu-id="d3d26-277">[ **追加**] をクリックし、[ **機密情報の種類**] をクリックして、使用する機密情報の種類を選び、 **追加** をクリックし、[ **保存** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-277">Click **Add**, click **Sensitive info types**, choose the sensitive info types that you want to use, click **Add**, and then click **Save**.</span></span>
13. <span data-ttu-id="d3d26-278">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-278">Click **Next**.</span></span>
14. <span data-ttu-id="d3d26-279">**ラベルの選択** をクリックして、使用するラベルを選び、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-279">Click **Choose a label**, select the label you want to use, and then click **Add**.</span></span>
15. <span data-ttu-id="d3d26-280">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-280">Click **Next**.</span></span>
16. <span data-ttu-id="d3d26-281">ポリシーを [シミュレーションモード] にして、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-281">Leave the policy in simulation mode and click **Next**.</span></span>
17. <span data-ttu-id="d3d26-282">[ **ポリシーの作成**] をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-282">Click **Create policy**, and then click **Done**.</span></span>

<span data-ttu-id="d3d26-283">ポリシーが設定されている状態でユーザーがドキュメントに「Project Saturn」と入力すると、自動ラベル付けポリシーがファイルをスキャンする際に特定のラベルが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-283">With the policy in place, when a user types "Project Saturn" into a document, the auto-labeling policy will automatically apply the specified label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="d3d26-284">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d3d26-284">More information</span></span>

[<span data-ttu-id="d3d26-285">機密情報ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="d3d26-285">Apply a sensitivity label to content automatically</span></span>](../compliance/apply-sensitivity-label-automatically.md)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="d3d26-286">高度な機密ファイルへのゲスト アクセスを削除するDLPポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-286">Create a DLP policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="d3d26-287">[データ損失防止 (DLP)](../compliance/data-loss-prevention-policies.md) を使用して、機密コンテンツの不要なゲスト共有を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-287">You can use [data loss prevention (DLP)](../compliance/data-loss-prevention-policies.md) to prevent unwanted guest sharing of sensitive content.</span></span> <span data-ttu-id="d3d26-288">データ損失防止は、ファイルの機密情報ラベルに基づき、ゲストアクセスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-288">Data loss prevention can take action based on a file's sensitivity label and remove guest access.</span></span>

<span data-ttu-id="d3d26-289">DLP ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="d3d26-289">To create a DLP rule</span></span>

1. <span data-ttu-id="d3d26-290">Microsoft 365 コンプライアンス管理センターで、[[データ損失防止] ページ](https://compliance.microsoft.com/datalossprevention)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-290">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="d3d26-291">**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-291">Click **Create policy**.</span></span>
3. <span data-ttu-id="d3d26-292">**[カスタム]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-292">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="d3d26-293">ポリシーの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-293">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="d3d26-294">**[ポリシーを適用する場所]** ページで、**SharePoint サイト** と **OneDrive アカウント** 以外のすべての設定をオフにし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-294">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="d3d26-295">**[ポリシーの設定を定義]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-295">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="d3d26-296">**[高度な DLP ルールのカスタマイズ]** ページで **[ルールの作成]** をクリックし、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-296">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="d3d26-297">[ **条件** で、[ **条件の追加**] をクリックし、[ **コンテンツを含む** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-297">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="d3d26-298">[ **追加**] をクリックし、**機密度ラベル** を選択し、使用するラベルを選択して、 **追加** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-298">Click **Add**, choose **Sensitivity labels**, choose the labels you want to use, and click **Add**.</span></span>

   ![条件オプション、機密情報の種類、機密情報ラベル、保持ラベルのスクリーンショット。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="d3d26-300">[ **アクション** ] で、[ **アクションの追加**] をクリックし [ **アクセスを制限する、またはMicrosoft 365のロケーションでコンテンツを暗号化する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3d26-300">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="d3d26-301">**Microsoft 365 の保存場所でのコンテンツのアクセスを制限する、またはコンテンツを暗号化する** チェックボックスをオンにしてから、[ **組織外のユーザーにのみ**] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-301">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people outside your organization** option.</span></span>

      ![DLP ルールのアクションオプションのスクリーンショット](../media/dlp-remove-guest-access-sensitive-files.png)

12. <span data-ttu-id="d3d26-303">**[保存]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-303">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="d3d26-304">テスト オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-304">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="d3d26-305">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d26-305">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="d3d26-306">ゲストがサイトまたはチーム全体のメンバーである場合、このポリシーはゲストのアクセスを削除しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-306">It's important to note that this policy doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="d3d26-307">ゲスト メンバーのいるサイトやチームに機密ドキュメントを作成する場合は、[チーム内の非公開チャネル](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)を使用して、その非公開チャネル内でお客様の組織のメンバーのみに許可することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-307">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) and only allowing members of your organization in the private channels.</span></span>

## <a name="additional-options"></a><span data-ttu-id="d3d26-308">追加オプション</span><span class="sxs-lookup"><span data-stu-id="d3d26-308">Additional options</span></span>

<span data-ttu-id="d3d26-309">Microsoft 365 および Azure Active Directory には、ゲスト共有環境のセキュリティ保護に役立つ追加オプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d3d26-309">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="d3d26-310">許可または拒否された共有ドメインの一覧を作成して、ユーザーが共有できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-310">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="d3d26-311">詳細については、「[Restrict sharing of SharePoint and OneDrive content by domain (ドメインによる SharePoint および OneDrive コンテンツの共有の制限)](/sharepoint/restricted-domains-sharing)」および「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-311">See [Restrict sharing of SharePoint and OneDrive content by domain](/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="d3d26-312">ユーザーが接続できる他の Azure Active Directory テナントを制限できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-312">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="d3d26-313">詳細については、「[テナント制限使用による SaaS クラウド アプリケーションへのアクセスの管理](/azure/active-directory/manage-apps/tenant-restrictions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-313">See [Use tenant restrictions to manage access to SaaS cloud applications](/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="d3d26-314">パートナーがゲスト アカウントの管理を支援できる、管理された環境を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d3d26-314">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="d3d26-315">詳細については、「[Create a B2B extranet with managed guests (管理されたゲストで B2B エクストラネットを作成する)](/Office365/Enterprise/b2b-extranet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d26-315">See [Create a B2B extranet with managed guests](/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3d26-316">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3d26-316">See Also</span></span>

[<span data-ttu-id="d3d26-317">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="d3d26-317">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="d3d26-318">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d3d26-318">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="d3d26-319">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="d3d26-319">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)