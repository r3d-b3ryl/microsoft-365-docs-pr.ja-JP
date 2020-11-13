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
ms.openlocfilehash: e0b943ce698cc6b93bd250a83b1c94eba406c484
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030019"
---
# <a name="create-a-secure-guest-sharing-environment"></a><span data-ttu-id="8c1b3-103">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-103">Create a secure guest sharing environment</span></span>

<span data-ttu-id="8c1b3-104">この記事では、Microsoft 365 でセキュリティで保護されたゲスト共有環境を作成するためのさまざまなオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-104">In this article, we'll walk through a variety of options for creating a secure guest sharing environment in Microsoft 365.</span></span> <span data-ttu-id="8c1b3-105">これらの例は、使用可能なオプションの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-105">These are examples to give you an idea of the options available.</span></span> <span data-ttu-id="8c1b3-106">これらの手順は、組織のセキュリティとコンプライアンスのニーズに合わせて、いろいろ組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-106">You can use these procedures in different combinations to meet the security and compliance needs of your organization.</span></span>

<span data-ttu-id="8c1b3-107">この文書には、以下の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-107">This article includes:</span></span>

- <span data-ttu-id="8c1b3-108">ゲスト用の多要素認証を設定する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-108">Setting up multi-factor authentication for guests.</span></span>
- <span data-ttu-id="8c1b3-109">ゲスト用の利用規約を設定する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-109">Setting up a terms of use for guests.</span></span>
- <span data-ttu-id="8c1b3-110">ゲストがチームやサイトに対するアクセス許可をまだ必要としているか定期的に確認するため、四半期ごとのゲスト アクセス レビューを設定する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-110">Setting up quarterly guest access reviews to periodically validate whether guests continue to need permissions to teams and sites.</span></span>
- <span data-ttu-id="8c1b3-111">アンマネージド デバイスに対するゲストのアクセスを Web のみに制限する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-111">Restricting guests to web-only access for unmanaged devices.</span></span>
- <span data-ttu-id="8c1b3-112">ゲストを毎日認証するようにセッション タイムアウト ポリシーを構成する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-112">Configuring a session timeout policy to ensure guests authenticate daily.</span></span>
- <span data-ttu-id="8c1b3-113">高度機密プロジェクト向けの機密情報の種類を作成する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-113">Creating a sensitive information type for a highly sensitive project.</span></span>
- <span data-ttu-id="8c1b3-114">機密情報の種類を含むドキュメントに、機密ラベルを自動的に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-114">Automatically assigning a sensitivity label to documents that contain a sensitive information type.</span></span>
- <span data-ttu-id="8c1b3-115">機密ラベルの付いたファイルからゲストアクセスを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-115">Automatically removing guest access from files with a sensitivity label.</span></span>

<span data-ttu-id="8c1b3-116">この記事で説明するオプションの一部には、ゲストが Azure Active Directory のアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-116">Some of the options discussed in this article require guests to have an account in Azure Active Directory.</span></span> <span data-ttu-id="8c1b3-117">ファイルやフォルダーをゲストと共有する際、ゲストがそのディレクトリに含まれていることを確認するには、[SharePoint および OneDrive の Azure AD B2B (プレビュー) との統合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-117">To ensure that guests are included in the directory when you share files and folders with them, use the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="8c1b3-118">この記事ではゲスト共有設定を有効化する方法については扱いません。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-118">Note that we won't discuss enabling guest sharing settings in this article.</span></span> <span data-ttu-id="8c1b3-119">さまざまなシナリオでゲスト共有を有効化する方法の詳細については、「[組織外のユーザーとの共同作業](collaborate-with-people-outside-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-119">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for details about enabling guest sharing for different scenarios.</span></span>

## <a name="set-up-multi-factor-authentication-for-guests"></a><span data-ttu-id="8c1b3-120">ゲスト用の多要素認証を設定する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-120">Set up multi-factor authentication for guests</span></span>

<span data-ttu-id="8c1b3-121">多要素認証を行うと、アカウントが漏洩する可能性が大幅に軽減されます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-121">Multi-factor authentication greatly reduces the chances of an account being compromised.</span></span> <span data-ttu-id="8c1b3-122">ゲスト ユーザーはガバナンス ポリシーやベスト プラクティスに準拠していない個人用メール アカウントを使用している可能性があるため、ゲストに対して多要素認証を必須にすることは特に重要です。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-122">Since guest users may be using personal email accounts that don't adhere to any governance policies or best practices, it's especially important to require multi-factor authentication for guests.</span></span> <span data-ttu-id="8c1b3-123">ゲスト ユーザーのユーザー名とパスワードが盗難された場合でも、2 番目の認証要素が要求されるため、不明なユーザーがサイトやファイルにアクセスする可能性を大幅に減少できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-123">If a guest user's username and password is stolen, requiring a second factor of authentication greatly reduces the chances of unknown parties gaining access to your sites and files.</span></span>

<span data-ttu-id="8c1b3-124">この例では、Azure Active Directory で条件付きアクセス ポリシーを使用して、ゲスト用の多要素認証を設定します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-124">In this example, we'll set up multi-factor authentication for guests by using a conditional access policy in Azure Active Directory.</span></span>

<span data-ttu-id="8c1b3-125">ゲスト用の多要素認証を設定するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-125">To set up multi-factor authentication for guests</span></span>

1. <span data-ttu-id="8c1b3-126">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-126">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="8c1b3-127">**[条件付きアクセス|ポリシー]** ブレードで、 **[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-127">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="8c1b3-128">**[名前]** フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-128">In the **Name** field, type a name.</span></span>
4. <span data-ttu-id="8c1b3-129">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-129">Under **Assignments** , click **Users and groups**.</span></span>
5. <span data-ttu-id="8c1b3-130">**[ユーザーとグループ]** ブレードで、 **[ユーザーとグループの選択]** を選択し、 **[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-130">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="8c1b3-131">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-131">Under **Assignments** , click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="8c1b3-132">**[クラウド アプリまたは操作]** ブレードで、 **[対象]** タブの **[すべてのクラウド アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-132">On the **Cloud apps or actions** blade, select **All cloud apps** on the **Include** tab.</span></span>
8. <span data-ttu-id="8c1b3-133">**[アクセス制御]** で、 **[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-133">Under **Access controls** , click **Grant**.</span></span>
9. <span data-ttu-id="8c1b3-134">**[許可]** ブレードで、 **[多要素認証を要求する]** チェック ボックスをオンにし、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-134">On the **Grant** blade, select the **Require multi-factor authentication** check box, and then click **Select**.</span></span>
10. <span data-ttu-id="8c1b3-135">**[新規]** ブレードの **[ポリシーの有効化]** で、 **[オン]** をクリックして、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-135">On the **New** blade, under **Enable policy** , click **On** , and then click **Create**.</span></span>

<span data-ttu-id="8c1b3-136">これで、ゲストは、多要素認証に登録してからでなければ共有コンテンツ、サイト、チームにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-136">Now, guest will be required to enroll in multi-factor authentication before they can access shared content, sites, or teams.</span></span>

### <a name="more-information"></a><span data-ttu-id="8c1b3-137">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8c1b3-137">More information</span></span>

[<span data-ttu-id="8c1b3-138"> Azure多要素認証 の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-138">Planning an Azure Multi-Factor Authentication deployment</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a><span data-ttu-id="8c1b3-139">ゲスト用の利用規約を設定する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-139">Set up a terms of use for guests</span></span>

<span data-ttu-id="8c1b3-140">ゲスト ユーザーは、お客様の組織との機密保持契約その他の法的契約に署名していないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-140">In some situations guest users may not have signed non-disclosure agreements or other legal agreements with your organization.</span></span> <span data-ttu-id="8c1b3-141">ゲストが共有ファイルにアクセスできるようにする前に、利用規約への同意をゲストに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-141">You can require guests to agree to a terms of use before accessing files that are shared with them.</span></span> <span data-ttu-id="8c1b3-142">この利用規約は、ゲストが初めて共有ファイルやサイトにアクセスしようとしたときに表示されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-142">The terms of use can be displayed the first time they attempt to access a shared file or site.</span></span>

<span data-ttu-id="8c1b3-143">利用規約を作成するには、そのドキュメントを Word などのオーサリング プログラムでまず作成し、.pdf ファイルとして保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-143">To create a terms of use, you first need to create the document in Word or another authoring program, and then save it as a .pdf file.</span></span> <span data-ttu-id="8c1b3-144">次に、このファイルを Azure AD にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-144">This file can then be uploaded to Azure AD.</span></span>

<span data-ttu-id="8c1b3-145">Azure AD の利用規約を作成するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-145">To create an Azure AD terms of use</span></span>

1. <span data-ttu-id="8c1b3-146">Azure にグローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-146">Sign in to Azure as a Global Administrator, Security Administrator, or Conditional Access Administrator.</span></span>
2. <span data-ttu-id="8c1b3-147">[[利用規約]](https://aka.ms/catou) に移動します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-147">Navigate to [Terms of use](https://aka.ms/catou).</span></span>
3. <span data-ttu-id="8c1b3-148">**[新しい利用規約]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-148">Click **New terms**.</span></span>

   ![Azure AD の新しい利用規約設定のスクリーンショット](../media/azure-ad-guest-terms-of-use.png)

4. <span data-ttu-id="8c1b3-150">**名前** と **表示名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-150">Type a **Name** and **Display name**.</span></span>
6. <span data-ttu-id="8c1b3-151">**[利用規約のドキュメント]** には、作成した PDF ファイルを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-151">For **Terms of use document** , browse to the pdf file that you created and select it.</span></span>
7. <span data-ttu-id="8c1b3-152">利用規約のドキュメントの言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-152">Select the language for your terms of use document.</span></span>
8. <span data-ttu-id="8c1b3-153">**[ユーザーは使用条件を展開する必要があります]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-153">Set **Require users to expand the terms of use** to **On**.</span></span>
9. <span data-ttu-id="8c1b3-154">**[条件付きアクセス]** の下にある **[Enforce with conditional access policy template] (条件付きアクセス ポリシーのテンプレートの適用)** リストから、 **[後で条件付きアクセス ポリシーを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-154">Under **Conditional Access** , in the **Enforce with Conditional Access policy template** list choose **Create conditional access policy later**.</span></span>
10. <span data-ttu-id="8c1b3-155">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-155">Click **Create**.</span></span>

<span data-ttu-id="8c1b3-156">利用規約の作成が完了したら、次に、ゲスト ユーザーにその利用規約を表示する条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-156">Once you've created the terms of use, the next step is to create a conditional access policy that displays the terms of use to guest users.</span></span>

<span data-ttu-id="8c1b3-157">条件付きアクセス ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-157">To create a conditional access policy</span></span>

1. <span data-ttu-id="8c1b3-158">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-158">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="8c1b3-159">**[条件付きアクセス|ポリシー]** ブレードで、 **[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-159">On the **Conditional Access | Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="8c1b3-160">[ **名前** ] ボックスに、名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-160">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="8c1b3-161">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-161">Under **Assignments** , click **Users and groups**.</span></span>
5. <span data-ttu-id="8c1b3-162">**[ユーザーとグループ]** ブレードで、 **[ユーザーとグループの選択]** を選択し、 **[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-162">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="8c1b3-163">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-163">Under **Assignments** , click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="8c1b3-164">**[含める]** タブで、 **[アプリを選択]** を選択し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-164">On the **Include** tab, select **Select apps** , and then click **Select**.</span></span>
8. <span data-ttu-id="8c1b3-165">**[選択]** ブレードで、 **Microsoft Teams** 、 **Office 365 SharePoint Online** 、 **Outlook Groups** を選択し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-165">On the **Select** blade, select **Microsoft Teams** , **Office 365 SharePoint Online** , and **Outlook Groups** , and then click **Select**.</span></span>
9. <span data-ttu-id="8c1b3-166">**[アクセス制御]** で、 **[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-166">Under **Access controls** , click **Grant**.</span></span>
10. <span data-ttu-id="8c1b3-167">**[許可]** ブレードで、「 **ゲストの利用規約** 」と入力し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-167">On the **Grant** blade, select **Guest terms of use** , and then click **Select**.</span></span>
11. <span data-ttu-id="8c1b3-168">**[新規]** ブレードの **[ポリシーの有効化]** で、 **[オン]** をクリックして、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-168">On the **New** blade, under **Enable policy** , click **On** , and then click **Create**.</span></span>

<span data-ttu-id="8c1b3-169">これで、ゲスト ユーザーがお客様の組織のコンテンツ、チームやサイトに初めてアクセスしようとしたときに、利用規約への同意を要求されるようになります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-169">Now, the first time a guest user attempts to access content or a team or site in your organization, they will be required to accept the terms of use.</span></span>

> [!NOTE]
> <span data-ttu-id="8c1b3-170">条件付きアクセスを使用するには、Azure AD Premium P1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-170">Using Conditional Access requires an Azure AD Premium P1 license.</span></span> <span data-ttu-id="8c1b3-171">詳細については、[「条件付きアクセスとは」](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-171">For more information, see [What is Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="more-information"></a><span data-ttu-id="8c1b3-172">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8c1b3-172">More information</span></span>

[<span data-ttu-id="8c1b3-173">Azure Active Directory の利用規約</span><span class="sxs-lookup"><span data-stu-id="8c1b3-173">Azure Active Directory terms of use</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a><span data-ttu-id="8c1b3-174">ゲスト アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-174">Set up guest access reviews</span></span>

<span data-ttu-id="8c1b3-175">Azure AD のアクセス レビューを使用すると、さまざまなチームやグループに対するユーザー アクセスの定期的なレビューを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-175">With access reviews in Azure AD, you can automate a periodic review of user access to various teams and groups.</span></span> <span data-ttu-id="8c1b3-176">特に、ゲストのアクセス レビューを必須にすることにより、ゲスト ユーザーが必要以上に長く組織の機密情報へのアクセス権を保持しないようにできます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-176">By requiring an access review for guests specifically, you can help ensure guest users do not retain access to your organization's sensitive information for longer than is necessary.</span></span>

<span data-ttu-id="8c1b3-177">アクセス レビューは、プログラムに整理できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-177">Access reviews can be organized into programs.</span></span> <span data-ttu-id="8c1b3-178">プログラムとは、類似したアクセス レビューをグループ化したもので、アクセス レビューをレポート作成や監査の目的で整理するのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-178">A program is a grouping of similar access reviews that can be used to organize access reviews for reporting and auditing purposes.</span></span>

<span data-ttu-id="8c1b3-179">プログラムを作成するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-179">To create a program</span></span>

1. <span data-ttu-id="8c1b3-180">Azure portal にログインして、[[Identity Governance]](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-180">Sign in to the Azure portal and open the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).</span></span>
2. <span data-ttu-id="8c1b3-181">左側のメニューで、 **[プログラム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-181">In the left menu, click **Programs**</span></span>
3. <span data-ttu-id="8c1b3-182">**[新しいプログラム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-182">Click **New program**.</span></span>
4. <span data-ttu-id="8c1b3-183">**名前** および **説明** を入力する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-183">Type a **Name**  and **Description**.</span></span>
5. <span data-ttu-id="8c1b3-184">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-184">Click **Create**.</span></span>

<span data-ttu-id="8c1b3-185">プログラムの作成が完了したら、ゲスト アクセス レビューを作成して、プログラムに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-185">Once the program has been created, we can create a guest access review and associate it with the program.</span></span>

<span data-ttu-id="8c1b3-186">ゲスト ユーザー アクセス レビューを設定するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-186">To set up a guest user access review</span></span>

1. <span data-ttu-id="8c1b3-187">[[Identity Governance]](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) ページの左側のメニューで、 **[アクセス レビュー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-187">On the [Identity Governance page](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade), in the left menu, click **Access reviews**.</span></span>
2. <span data-ttu-id="8c1b3-188">**[新しいアクセス レビュー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-188">Click **New access review**.</span></span>

   ![Azure AD のアクセス レビュー設定のスクリーンショット](../media/azure-ad-create-access-review.png)

3. <span data-ttu-id="8c1b3-190">[ **名前** ] ボックスに、名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-190">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="8c1b3-191">**[頻度]** は、 **[四半期に 1 回]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-191">For **Frequency** , choose **Quarterly**.</span></span>
5. <span data-ttu-id="8c1b3-192">**[終了]** は、 **[指定しない]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-192">For **End** , choose **Never**.</span></span>
6. <span data-ttu-id="8c1b3-193">**[スコープ]** は、 **[ゲスト ユーザーのみ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-193">For **Scope** , choose **Guest users only**.</span></span>
7. <span data-ttu-id="8c1b3-194">**[グループ]** をクリックし、アクセス レビューに含めるグループを選択したら、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-194">Click **Group** , select the groups that you want to include in the access review, and then click **Select**.</span></span>
8. <span data-ttu-id="8c1b3-195">**[プログラム]** の下の **[プログラムへのリンク]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-195">Under **Programs** , click **Link to program**.</span></span>
9. <span data-ttu-id="8c1b3-196">**[プログラムの選択]** ブレードで、 **[ゲスト アクセス レビュー プログラム]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-196">On the **Select a program** blade, choose **Guest access review program**</span></span>
10. <span data-ttu-id="8c1b3-197">**[開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-197">Click **Start**.</span></span>

<span data-ttu-id="8c1b3-198">指定したグループごとに、別個のアクセス レビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-198">A separate access review is created for each group that you specify.</span></span> <span data-ttu-id="8c1b3-199">各グループのグループ所有者は、四半期ごとにメールを受け取り、グループに対するゲスト アクセスを許可または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-199">Group owners of each group will be emailed quarterly to approve or deny guest access to their groups.</span></span>

<span data-ttu-id="8c1b3-200">重要な点として、ゲストにはチームやグループに対するアクセス権か、個々のファイルやフォルダーに対するアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-200">It's important to note that guests can be given access to teams or groups, or to individual files and folders.</span></span> <span data-ttu-id="8c1b3-201">ファイルやフォルダーに対するアクセス権を与えられているゲストは、特定のグループに追加できません。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-201">When given access to files and folders, guests may not be added to any particular group.</span></span> <span data-ttu-id="8c1b3-202">チームやグループに属していないゲスト ユーザーに対してアクセス レビューを実行する場合は、Azure AD ですべてのゲストが含まれる動的グループを作成して、そのグループに対するアクセス レビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-202">If you want to do access reviews on guest users who don't belong to a team or group, you can create a dynamic group in Azure AD to contain all guests and then create an access review for that group.</span></span> <span data-ttu-id="8c1b3-203">サイト所有者は、[サイトのゲスト の有効期限](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-203">Site owners can also manage [guest expiration for the site](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)</span></span>

### <a name="more-information"></a><span data-ttu-id="8c1b3-204">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8c1b3-204">More information</span></span>

[<span data-ttu-id="8c1b3-205">Azure AD のアクセス レビューでゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-205">Manage guest access with Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[<span data-ttu-id="8c1b3-206">グループまたはアプリケーションのアクセス レビューを Azure AD アクセス レビューで作成する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-206">Create an access review of groups or applications in Azure AD access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a><span data-ttu-id="8c1b3-207">ゲスト ユーザー用の Web 専用アクセスを設定する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-207">Set up web-only access for guest users</span></span>

<span data-ttu-id="8c1b3-208">ゲスト ユーザーが Web ブラウザーのみを使用してチーム、サイト、ファイルにアクセスするように要求することにより、攻撃面を減少させて、管理を容易にできます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-208">You can reduce your attack surface and ease administration by requiring guest users to access your teams, sites, and files by using a web browser only.</span></span>

<span data-ttu-id="8c1b3-209">Microsoft 365 グループとTeamsの場合は、Azure AD の条件付きアクセスポリシーで行います。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-209">For Microsoft 365 Groups and Teams, this is done with an Azure AD conditional access policy.</span></span> <span data-ttu-id="8c1b3-210">SharePointについては、SharePoint 管理センターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-210">For SharePoint, this is configured in the SharePoint admin center.</span></span> <span data-ttu-id="8c1b3-211">( [機密ラベルを使用して、ゲストのアクセスを web のみに制限する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)ことができます)</span><span class="sxs-lookup"><span data-stu-id="8c1b3-211">(You can also [use sensitivity labels to restrict guests to web-only access](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="8c1b3-212">グループとチームに対して、ゲストのアクセスを web のみに制限する方法</span><span class="sxs-lookup"><span data-stu-id="8c1b3-212">To restrict guests to web-ony access for groups and teams</span></span>

1. <span data-ttu-id="8c1b3-213">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-213">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="8c1b3-214">**[条件付きアクセス - ポリシー]** ブレードで、 **[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-214">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="8c1b3-215">[ **名前** ] ボックスに、名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-215">In the **Name** box, type a name.</span></span>
4. <span data-ttu-id="8c1b3-216">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-216">Under **Assignments** , click **Users and groups**.</span></span>
5. <span data-ttu-id="8c1b3-217">**[ユーザーとグループ]** ブレードで、 **[ユーザーとグループの選択]** を選択し、 **[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-217">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="8c1b3-218">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-218">Under **Assignments** , click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="8c1b3-219">**[含める]** タブで、 **[アプリを選択]** を選択し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-219">On the **Include** tab, select **Select apps** , and then click **Select**.</span></span>
8. <span data-ttu-id="8c1b3-220">**[選択]** ブレードで、 **Microsoft Teams** 、 **Outlookグループ** を選択し、 **選択** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-220">On the **Select** blade, select **Microsoft Teams** and **Outlook Groups** , and then click **Select**.</span></span>
9. <span data-ttu-id="8c1b3-221">**[割り当て]** の下の **[条件]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-221">Under **Assignments** , click **Conditions**.</span></span>
10. <span data-ttu-id="8c1b3-222">**[条件]** ブレードで、 **[クライアント アプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-222">On the **Conditions** blade, click **Client apps**.</span></span>
11. <span data-ttu-id="8c1b3-223">**[クライアント アプリ]** ブレードで、 **[構成する]** の **[はい]** をクリックし、 **[モバイル アプリとデスクトップ クライアント]** と **[Exchange ActiveSyncクライアント]** 、および **その他のクライアント** 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-223">On the **Client apps** blade, click **Yes** for **Configure** , and then select the **Mobile apps and desktop clients** , **Exchange ActiveSync clients** , and **Other clients** settings.</span></span> <span data-ttu-id="8c1b3-224">**ブラウザー** チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-224">Clear the **Browser** check box.</span></span>

    ![Azure AD の条件付きアクセス クライアント アプリ設定のスクリーンショット](../media/azure-ad-conditional-access-client-mobile.png)

12. <span data-ttu-id="8c1b3-226">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-226">Click **Done**.</span></span>
13. <span data-ttu-id="8c1b3-227">**[アクセス制御]** で、 **[許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-227">Under **Access controls** , click **Grant**.</span></span>
14. <span data-ttu-id="8c1b3-228">**[許可]** ブレードで、 **[デバイスは準拠としてマーク済みである必要がある]** および **[Hybrid Azure AD 参加済みデバイスが必要]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-228">On the **Grant** blade, select **Require device to be marked as compliant** and **Require Hybrid Azure AD joined device**.</span></span>
15. <span data-ttu-id="8c1b3-229">**[複数のコントロールの場合]** の下の **[選択したコントロールのいずれかが必要]** を選択して、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-229">Under **For multiple controls** , select **Require one of the selected controls** , and then click **Select**.</span></span>
16. <span data-ttu-id="8c1b3-230">**[新規]** ブレードの **[ポリシーの有効化]** で、 **[オン]** をクリックして、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-230">On the **New** blade, under **Enable policy** , click **On** , and then click **Create**.</span></span>

<span data-ttu-id="8c1b3-231">SharePointでゲストのアクセスを Web のみに制限するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-231">To restrict guests to web-ony access for SharePoint</span></span>

1. <span data-ttu-id="8c1b3-232">[ [SharePoint 管理センター](https://admin.microsoft.com/sharepoint)で **ポリシー** を展開し、[ **アクセス制御** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-232">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), expand **Policies** and click **Access control**.</span></span>
2. <span data-ttu-id="8c1b3-233">**非管理対象デバイス** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-233">Click **Unmanaged devices**.</span></span>
3. <span data-ttu-id="8c1b3-234">**制限付きの web のみのアクセスを許可する** オプションを選択して、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-234">Select the **Allow limited, web-only access** option, and then click **Save**.</span></span>

<span data-ttu-id="8c1b3-235">SharePoint 管理センターのこの設定では、Azure AD の条件付きアクセスポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-235">Note that this setting in the SharePoint admin center creates a supporting conditional access policy in Azure AD.</span></span>

## <a name="configure-a-session-timeout-for-guest-users"></a><span data-ttu-id="8c1b3-236">ゲスト ユーザー用のセッション タイムアウトを設定する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-236">Configure a session timeout for guest users</span></span>

<span data-ttu-id="8c1b3-237">ゲストに定期的な認証を要求することにより、ゲスト ユーザーのデバイスがセキュリティで保護されていない場合も、不明なユーザーがお客様の組織のコンテンツにアクセスする可能性を減少できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-237">Requiring guests to authenticate on a regular basis can reduce the possibility of unknown users accessing your organization's content if a guest user's device isn't kept secure.</span></span> <span data-ttu-id="8c1b3-238">ゲスト ユーザー用のセッション タイムアウト条件付きアクセス ポリシーを、Azure AD で設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-238">You can configure a session timeout conditional access policy for guest users in Azure AD.</span></span>

<span data-ttu-id="8c1b3-239">ゲスト セッション タイムアウト ポリシーを設定するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-239">To configure a guest session timeout policy</span></span>

1. <span data-ttu-id="8c1b3-240">[Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-240">Go to [Azure conditional access policies](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).</span></span>
2. <span data-ttu-id="8c1b3-241">**[条件付きアクセス - ポリシー]** ブレードで、 **[新しいポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-241">On the **Conditional Access - Policies** blade, click **New policy**.</span></span>
3. <span data-ttu-id="8c1b3-242">**[名前]** ボックスに「 *ゲスト セッション タイムアウト* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-242">In the **Name** box, type *Guest session timeout*.</span></span>
4. <span data-ttu-id="8c1b3-243">**[割り当て]** の下の **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-243">Under **Assignments** , click **Users and groups**.</span></span>
5. <span data-ttu-id="8c1b3-244">**[ユーザーとグループ]** ブレードで、 **[ユーザーとグループの選択]** を選択し、 **[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-244">On the **Users and groups** blade, select **Select users and groups** , select the **All guests and external users** check box.</span></span>
6. <span data-ttu-id="8c1b3-245">**[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-245">Under **Assignments** , click **Cloud apps or actions**.</span></span>
7. <span data-ttu-id="8c1b3-246">**[含める]** タブで、 **[アプリを選択]** を選択し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-246">On the **Include** tab, select **Select apps** , and then click **Select**.</span></span>
8. <span data-ttu-id="8c1b3-247">**[選択]** ブレードで、 **Microsoft Teams** 、 **Office 365 SharePoint Online** 、 **Outlook Groups** を選択し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-247">On the **Select** blade, select **Microsoft Teams** , **Office 365 SharePoint Online** , and **Outlook Groups** , and then click **Select**.</span></span>
9. <span data-ttu-id="8c1b3-248">**[アクセス制御]** で、 **[セッション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-248">Under **Access controls** , click **Session**.</span></span>
10. <span data-ttu-id="8c1b3-249">**[セッション]** ブレードで、 **[サインイン頻度]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-249">On the **Session** blade, select **Sign-in frequency**.</span></span>
11. <span data-ttu-id="8c1b3-250">期間として **[1]** および **[日]** を選択し、 **[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-250">Select **1** and **Days** for the time period, and then click **Select**.</span></span>
12. <span data-ttu-id="8c1b3-251">**[新規]** ブレードの **[ポリシーの有効化]** で、 **[オン]** をクリックして、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-251">On the **New** blade, under **Enable policy** , click **On** , and then click **Create**.</span></span>

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a><span data-ttu-id="8c1b3-252">極秘プロジェクト向けの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-252">Create a sensitive information type for a highly sensitive project</span></span>

<span data-ttu-id="8c1b3-253">機密情報の種類は、コンプライアンス要件を適用するためにポリシー ワークフローで使用できる定義済みの文字列です。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-253">Sensitive information types are predefined strings that can be used in policy workflows to enforce compliance requirements.</span></span> <span data-ttu-id="8c1b3-254">Microsoft 365 コンプライアンス センターには、運転免許証番号、クレジット カード番号、銀行口座番号など、100 を超える機密情報の種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-254">The Microsoft 365 Compliance Center comes with over one hundred sensitive information types, including driver's license numbers, credit card numbers, bank account numbers, etc.</span></span>

<span data-ttu-id="8c1b3-255">カスタムの機密情報の種類を作成して、お客様の組織に固有のコンテンツを管理するために利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-255">You can create custom sensitive information types to help manage content specific to your organization.</span></span> <span data-ttu-id="8c1b3-256">この例では、機密プロジェクト向けにカスタムの機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-256">In this example, we'll create a custom sensitive information type for a highly sensitive project.</span></span> <span data-ttu-id="8c1b3-257">そのようにすると、この機密情報の種類を使用して、機密ラベルを自動的に適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-257">We can then use this sensitive information type to automatically apply a sensitivity label.</span></span>

<span data-ttu-id="8c1b3-258">機密情報の種類を作成するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-258">To create a sensitive information type</span></span>

1. <span data-ttu-id="8c1b3-259">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)の左側のナビゲーションで、 **[分類]** を展開し、 **[機密情報の種類]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-259">In the [Microsoft 365 Compliance Center](https://compliance.microsoft.com), in the left navigation, expand **Classification** , and then click **Sensitive info types**.</span></span>
2. <span data-ttu-id="8c1b3-260">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-260">Click **Create**.</span></span>
3. <span data-ttu-id="8c1b3-261">**[名前]** と **[説明]** に「 **Project Saturn** 」と入力し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-261">For **Name** and **Description** , type **Project Saturn** , and then click **Next**.</span></span>
4. <span data-ttu-id="8c1b3-262">**[要素の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-262">Click **Add an element**.</span></span>
5. <span data-ttu-id="8c1b3-263">**[次が含まれているコンテンツを検出する]** リストで **[キーワード]** を選択して、キーワード ボックスに「 *Project Saturn* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-263">On the **Detect content containing** list, select **Keywords** , and then type *Project Saturn* in the keyword box.</span></span>
6. <span data-ttu-id="8c1b3-264">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-264">Click **Next** , and then click **Finish**.</span></span>
7. <span data-ttu-id="8c1b3-265">機密情報の種類をテストするかどうかをたずねられたら、 **[いいえ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-265">If asked if you would like to test the sensitive information type, click **No**.</span></span>

### <a name="more-information"></a><span data-ttu-id="8c1b3-266">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8c1b3-266">More information</span></span>

[<span data-ttu-id="8c1b3-267">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="8c1b3-267">Custom sensitive information types</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a><span data-ttu-id="8c1b3-268">機密情報の種類に基づいて、機密情報ラベルを割り当てる自動ラベル付けポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-268">Create an auto-labeling policy to assign a sensitivity label based on a sensitive information type</span></span>

<span data-ttu-id="8c1b3-269">組織で機密情報のラベルを使用している場合、定義された機密情報の種類を含むファイルにラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-269">If you are using sensitivity labels in your organization, you can automatically apply a label to files that contain defined sensitive information types.</span></span> 

<span data-ttu-id="8c1b3-270">新しい自動ラベル付けポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="8c1b3-270">To create an auto-labeling policy</span></span>

1. <span data-ttu-id="8c1b3-271">[Microsoft 365 コンプライアンス管理センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-271">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="8c1b3-272">左側のナビゲーションで、[ **情報の保護** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-272">In the left navigation, click **Information protection**.</span></span>
3. <span data-ttu-id="8c1b3-273">[ **オートラベル** ] タブで、[ **自動ラベル付けポリシーの作成** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-273">On the **Auto-labeling** tab, click **Create auto-labeling policy**.</span></span>
4. <span data-ttu-id="8c1b3-274">[ **[このラベルを適用する情報を選択** ] ページで、[ **カスタム** ] を選び、 **次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-274">On the **Choose info you want this label applied to** page, choose **Custom** and click **Next**.</span></span>
5. <span data-ttu-id="8c1b3-275">ポリシーの名前と説明を入力して、 **次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-275">Type a name and description for the policy and click **Next**.</span></span>
6. <span data-ttu-id="8c1b3-276">[ **ラベル を適用する場所を選択する** ] ページで、 **SharePoint サイト** をオンにして、 **サイト の選択** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-276">On the **Choose locations where you want to apply the label** page, turn on **SharePoint sites** and click **Choose sites**.</span></span>
7. <span data-ttu-id="8c1b3-277">オートラベル機能を有効にするサイトの URLを追加し、 **完了** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-277">Add the URLs for the sites where you want to turn on auto-labeling and click **Done**.</span></span>
8. <span data-ttu-id="8c1b3-278">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-278">Click **Next**.</span></span>
9. <span data-ttu-id="8c1b3-279">[ **共通 または高度なルールの設定** ] ページで、[ **共通のルール** ] を選択し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-279">On the **Set up common or advanced rules** page, choose **Common rules** and click **Next**.</span></span>
10. <span data-ttu-id="8c1b3-280">[ **すべての場所のコンテンツのルールを定義する]** ページで、 **新しいルール** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-280">On the **Define rules for content in all locations** page, click **New rule**.</span></span>
11. <span data-ttu-id="8c1b3-281">[ **新しいルール** ]の ページで、ルールに名前を付けて、 **条件の追加** をクリックし、[ **コンテンツに機密情報の種類が含まれている** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-281">On the **New rule** page, give the rule a name, click **Add condition** , and then click **Content contains sensitive info types**.</span></span>
12. <span data-ttu-id="8c1b3-282">[ **追加** ] をクリックし、[ **機密情報の種類** ] をクリックして、使用する機密情報の種類を選び、 **追加** をクリックし、[ **保存** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-282">Click **Add** , click **Sensitive info types** , choose the sensitive info types that you want to use, click **Add** , and then click **Save**.</span></span>
13. <span data-ttu-id="8c1b3-283">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-283">Click **Next**.</span></span>
14. <span data-ttu-id="8c1b3-284">**ラベルの選択** をクリックして、使用するラベルを選び、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-284">Click **Choose a label** , select the label you want to use, and then click **Add**.</span></span>
15. <span data-ttu-id="8c1b3-285">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-285">Click **Next**.</span></span>
16. <span data-ttu-id="8c1b3-286">ポリシーを [シミュレーションモード] にして、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-286">Leave the policy in simulation mode and click **Next**.</span></span>
17. <span data-ttu-id="8c1b3-287">[ **ポリシーの作成** ] をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-287">Click **Create policy** , and then click **Done**.</span></span>

<span data-ttu-id="8c1b3-288">ポリシーが設定されている状態でユーザーがドキュメントに「Project Saturn」と入力すると、自動ラベル付けポリシーがファイルをスキャンする際に特定のラベルが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-288">With the policy in place, when a user types "Project Saturn" into a document, the auto-labeling policy will automatically apply the specified label when it scans the file.</span></span>

### <a name="more-information"></a><span data-ttu-id="8c1b3-289">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8c1b3-289">More information</span></span>

[<span data-ttu-id="8c1b3-290">機密情報ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-290">Apply a sensitivity label to content automatically</span></span>](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a><span data-ttu-id="8c1b3-291">高度な機密ファイルへのゲスト アクセスを削除するDLPポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-291">Create a DLP policy to remove guest access to highly sensitive files</span></span>

<span data-ttu-id="8c1b3-292">[データ損失防止 (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) を使用して、機密コンテンツの不要なゲスト共有を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-292">You can use [data loss prevention (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to prevent unwanted guest sharing of sensitive content.</span></span> <span data-ttu-id="8c1b3-293">データ損失防止は、ファイルの機密情報ラベルに基づき、ゲストアクセスを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-293">Data loss prevention can take action based on a file's sensitivity label and remove guest access.</span></span>

<span data-ttu-id="8c1b3-294">DLP ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="8c1b3-294">To create a DLP rule</span></span>

1. <span data-ttu-id="8c1b3-295">Microsoft 365 コンプライアンス管理センターで、[[データ損失防止] ページ](https://compliance.microsoft.com/datalossprevention)に移動します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-295">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="8c1b3-296">**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-296">Click **Create policy**.</span></span>
3. <span data-ttu-id="8c1b3-297">**[カスタム]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-297">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="8c1b3-298">ポリシーの名前を入力し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-298">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="8c1b3-299">**[ポリシーを適用する場所]** ページで、 **SharePoint サイト** と **OneDrive アカウント** 以外のすべての設定をオフにし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-299">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts** , and then click **Next**.</span></span>
6. <span data-ttu-id="8c1b3-300">**[ポリシーの設定を定義]** ページで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-300">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="8c1b3-301">**[高度な DLP ルールのカスタマイズ]** ページで **[ルールの作成]** をクリックし、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-301">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="8c1b3-302">[ **条件** で、[ **条件の追加** ] をクリックし、[ **コンテンツを含む** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-302">Under **Conditions** , click **Add condition** , and choose **Content contains**.</span></span>
9. <span data-ttu-id="8c1b3-303">[ **追加** ] をクリックし、 **機密度ラベル** を選択し、使用するラベルを選択して、 **追加** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-303">Click **Add** , choose **Sensitivity labels** , choose the labels you want to use, and click **Add**.</span></span>

   ![条件オプション、機密情報の種類、機密情報ラベル、保持ラベルのスクリーンショット。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="8c1b3-305">[ **アクション** ] で、[ **アクションの追加** ] をクリックし [ **アクセスを制限する、またはMicrosoft 365のロケーションでコンテンツを暗号化する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-305">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="8c1b3-306">**Microsoft 365 の保存場所でのコンテンツのアクセスを制限する、またはコンテンツを暗号化する** チェックボックスをオンにしてから、[ **組織外のユーザーにのみ** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-306">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people outside your organization** option.</span></span>

      ![DLP ルールのアクションオプションのスクリーンショット](../media/dlp-remove-guest-access-sensitive-files.png)

12. <span data-ttu-id="8c1b3-308">**[保存]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-308">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="8c1b3-309">テスト オプションを選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-309">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="8c1b3-310">**[送信]** をクリックしてから、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-310">Click **Submit** , and then click **Done**.</span></span>

<span data-ttu-id="8c1b3-311">ゲストがサイトまたはチーム全体のメンバーである場合、このポリシーはゲストのアクセスを削除しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-311">It's important to note that this policy doesn't remove access if the guest is a member of the site or team as a whole.</span></span> <span data-ttu-id="8c1b3-312">ゲスト メンバーのいるサイトやチームに機密ドキュメントを作成する場合は、[チーム内の非公開チャネル](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)を使用して、その非公開チャネル内でお客様の組織のメンバーのみに許可することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-312">If you plan to have highly sensitive documents in a site or team with guest members, consider using [private channels in Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) and only allowing members of your organization in the private channels.</span></span>

## <a name="additional-options"></a><span data-ttu-id="8c1b3-313">追加オプション</span><span class="sxs-lookup"><span data-stu-id="8c1b3-313">Additional options</span></span>

<span data-ttu-id="8c1b3-314">Microsoft 365 および Azure Active Directory には、ゲスト共有環境のセキュリティ保護に役立つ追加オプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-314">There are some additional options in Microsoft 365 and Azure Active Directory that can help secure your guest sharing environment.</span></span>

- <span data-ttu-id="8c1b3-315">許可または拒否された共有ドメインの一覧を作成して、ユーザーが共有できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-315">You can create a list of allowed or denied sharing domains to limit who users can share with.</span></span> <span data-ttu-id="8c1b3-316">詳細については、「[Restrict sharing of SharePoint and OneDrive content by domain (ドメインによる SharePoint および OneDrive コンテンツの共有の制限)](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)」および「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-316">See [Restrict sharing of SharePoint and OneDrive content by domain](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) and [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) for more information.</span></span>
- <span data-ttu-id="8c1b3-317">ユーザーが接続できる他の Azure Active Directory テナントを制限できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-317">You can limit which other Azure Active Directory tenants your users can connect to.</span></span> <span data-ttu-id="8c1b3-318">詳細については、「[テナント制限使用による SaaS クラウド アプリケーションへのアクセスの管理](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-318">See [Use tenant restrictions to manage access to SaaS cloud applications](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions) for information.</span></span>
- <span data-ttu-id="8c1b3-319">パートナーがゲスト アカウントの管理を支援できる、管理された環境を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-319">You can create a managed environment where partners can help manage guest accounts.</span></span> <span data-ttu-id="8c1b3-320">詳細については、「[Create a B2B extranet with managed guests (管理されたゲストで B2B エクストラネットを作成する)](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c1b3-320">See [Create a B2B extranet with managed guests](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet) for information.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c1b3-321">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c1b3-321">See Also</span></span>

[<span data-ttu-id="8c1b3-322">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-322">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="8c1b3-323">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="8c1b3-323">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="8c1b3-324">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="8c1b3-324">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
