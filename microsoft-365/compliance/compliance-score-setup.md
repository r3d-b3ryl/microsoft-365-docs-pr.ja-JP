---
title: Microsoft コンプライアンススコア (プレビュー) の設定
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンススコアを設定および開始する方法について説明します。これにより、リスク評価が簡素化および自動化されます。
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016192"
---
# <a name="compliance-score-preview-setup"></a><span data-ttu-id="6bc2a-103">コンプライアンススコア (プレビュー) の設定</span><span class="sxs-lookup"><span data-stu-id="6bc2a-103">Compliance Score (preview) setup</span></span>

<span data-ttu-id="6bc2a-104">**この記事の内容**コンプライアンススコア**へのアクセス**方法、**役割とアクセス許可**の設定方法、および**自動セキュリティスコア更新**の構成方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-104">**In this article:** Understand how to **access** Compliance Score, set **roles and permissions**, and configure **automatic Secure Score updates**.</span></span> <span data-ttu-id="6bc2a-105">また、この記事では、メインのコンプライアンススコアページ (**ダッシュボード**、[改善アクション] ページ、[ソリューション] ページ、[評価] ページ) についても説明します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-105">This article also explains the main Compliance Score pages: **your dashboard**, the improvement actions page, the solutions page, and the assessments page.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6bc2a-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="6bc2a-106">Before you begin</span></span>

<span data-ttu-id="6bc2a-107">通常、コンプライアンススコアにアクセスする最初のユーザーは、組織の Microsoft 365 グローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-107">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="6bc2a-108">初めてコンプライアンススコアを参照する場合は、グローバル管理者サインインを推奨し、以下の説明に従ってユーザー権限を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-108">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="6bc2a-109">サインイン</span><span class="sxs-lookup"><span data-stu-id="6bc2a-109">Sign in</span></span>

1. <span data-ttu-id="6bc2a-110">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)に移動し、microsoft 365 のグローバル管理者アカウントで**サインイン**します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-110">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="6bc2a-111">左側のナビゲーション ウィンドウで、[**コンプライアンス スコア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-111">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="6bc2a-112">その後、[自分のスコアとともにコンプライアンス スコアのダッシュボード](#understand-the-compliance-score-dashboard)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-112">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="6bc2a-113">Access コンプライアンススコアへの直接リンクは、 [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) です。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-113">The direct link to access Compliance Score is [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="6bc2a-114">ユーザーのアクセス許可を設定して役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="6bc2a-114">Set user permissions and assign roles</span></span>

<span data-ttu-id="6bc2a-115">コンプライアンススコアは、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-115">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="6bc2a-116">コンプライアンススコアにアクセスできるのは、役割が割り当てられているユーザーだけで、各ユーザーが許可する操作は、役割の種類によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-116">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="6bc2a-117">アクセス許可を設定する場所</span><span class="sxs-lookup"><span data-stu-id="6bc2a-117">Where to set permissions</span></span>

<span data-ttu-id="6bc2a-118">組織のグローバル管理者ロールを持つユーザーは、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)または[コンプライアンスマネージャー](compliance-manager-overview.md#permissions)でユーザー権限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-118">The person holding the global admin role for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="6bc2a-119">これらのいずれかの場所で役割が設定されると、ユーザーはコンプライアンスのスコアとコンプライアンスマネージャーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-119">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="6bc2a-120">役割の種類</span><span class="sxs-lookup"><span data-stu-id="6bc2a-120">Role types</span></span>

<span data-ttu-id="6bc2a-121">次の表に、各[AZURE AD の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)を既存のコンプライアンスマネージャーの役割にマップする方法と、各役割によって許可される機能を示します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-121">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="6bc2a-122">コンプライアンススコアにアクセスするには、少なくとも Azure AD グローバルリーダーの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-122">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="6bc2a-123">ユーザーは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-123">User can:</span></span> | <span data-ttu-id="6bc2a-124">Azure AD の役割</span><span class="sxs-lookup"><span data-stu-id="6bc2a-124">Azure AD role</span></span> | <span data-ttu-id="6bc2a-125">コンプライアンスマネージャーの役割</span><span class="sxs-lookup"><span data-stu-id="6bc2a-125">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="6bc2a-126">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-126">**Read but not edit data**</span></span>| <span data-ttu-id="6bc2a-127">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="6bc2a-127">Azure AD global reader</span></span>  | <span data-ttu-id="6bc2a-128">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="6bc2a-128">Azure AD global reader</span></span> | 
| <span data-ttu-id="6bc2a-129">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-129">**Read but not edit data**</span></span>| <span data-ttu-id="6bc2a-130">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-130">Security reader</span></span> | <span data-ttu-id="6bc2a-131">コンプライアンスマネージャーリーダー</span><span class="sxs-lookup"><span data-stu-id="6bc2a-131">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="6bc2a-132">**データを編集する**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-132">**Edit data**</span></span>| <span data-ttu-id="6bc2a-133">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-133">Compliance administrator</span></span> | <span data-ttu-id="6bc2a-134">コンプライアンスマネージャー共同作成者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-134">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="6bc2a-135">**テスト結果を編集する**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-135">**Edit test results**</span></span>| <span data-ttu-id="6bc2a-136">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-136">Compliance administrator</span></span> | <span data-ttu-id="6bc2a-137">コンプライアンスマネージャーの査定者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-137">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="6bc2a-138">**評価、およびテンプレートとテナントデータを管理する**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-138">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="6bc2a-139">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-139">Compliance administrator</span></span><br><span data-ttu-id="6bc2a-140">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-140">Compliance data administrator</span></span><br><span data-ttu-id="6bc2a-141">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-141">Security administrator</span></span> | <span data-ttu-id="6bc2a-142">コンプライアンスマネージャー管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-142">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="6bc2a-143">**ユーザーを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-143">**Assign users**</span></span>| <span data-ttu-id="6bc2a-144">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-144">Global administrator</span></span> | <span data-ttu-id="6bc2a-145">ポータル管理者</span><span class="sxs-lookup"><span data-stu-id="6bc2a-145">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="6bc2a-146">パブリックプレビュー中にコンプライアンススコアからコンプライアンスマネージャーに移動してタスクを完了すると、ブラウザーに新しいタブが表示され、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-146">When you go from Compliance Score to Compliance Manager to complete a task during public preview, your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="6bc2a-147">上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-147">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="6bc2a-148">アカウントにサインインして、[コンプライアンスマネージャーにアクセスするには**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-148">Sign in to your account," select **Sign In** to access Compliance Manager.</span></span> <span data-ttu-id="6bc2a-149">資格情報を再入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-149">You won't need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="6bc2a-150">セキュリティで保護されたスコアの自動更新を構成する</span><span class="sxs-lookup"><span data-stu-id="6bc2a-150">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="6bc2a-151">既定では、すべての新しいテナントには、[セキュリティで保護さ](../security/mtp/microsoft-secure-score-new.md)れたスコア自動更新が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-151">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score-new.md) automatic updates turned on.</span></span> <span data-ttu-id="6bc2a-152">セキュリティで保護されたスコアで監視されているすべてのアクションは、コンプライアンススコアの同じアクションの状態を自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-152">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="6bc2a-153">全体管理者はこの設定を管理して、すべてのアクションの自動更新をオフにしたり、操作の更新を個別に設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-153">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="6bc2a-154">パブリックプレビューでは、Microsoft Service Trust Portal (コンプライアンスマネージャーが配置されている場合) にアクセスして、セキュリティで保護されたスコアの更新を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-154">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="6bc2a-155">セキュリティで保護されたスコアの自動更新を管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-155">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="6bc2a-156">グローバル管理者アカウントを使用して、[サービス信頼ポータル](https://servicetrust.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-156">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="6bc2a-157">サービス信頼ポータルのトップメニューバーで、[**詳細**設定] の下の [**管理**] を選択し、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-157">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="6bc2a-158">[ **Secure Score** ] タブで、対応するボタンを選択して、**すべてのアクション**に対してオンにするか、**すべてのアクションに対し**て無効にするか、または**アクションごとに設定します。**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-158">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="6bc2a-159">[**アクションごとに設定**] を選択した場合は、個々のアクションについてセキュリティで保護されたスコア更新を有効にする追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-159">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="6bc2a-160">上部のメニューから [**コンプライアンスマネージャー** ] を選択します ([コンプライアンスマネージャー (クラシック)] を選択しません)。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-160">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic),").</span></span>

5. <span data-ttu-id="6bc2a-161">画面の右上隅にある [**テナント管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-161">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="6bc2a-162">[**顧客の操作**] ウィンドウで、[**影響を受ける操作**] 列の下に、省略記号 (**...**) を含む目的のアクションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-162">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="6bc2a-163">省略記号をクリックして、[編集] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-163">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="6bc2a-164">**セキュリティで保護されたスコアの継続更新**の切り替えトグルスイッチをオンに切り替え**ます。**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-164">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="6bc2a-165">[保存] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-165">Select **Save.**</span></span> <span data-ttu-id="6bc2a-166">セキュリティで保護されたスコア継続的監視は、そのアクションに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-166">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="6bc2a-167">**注:** すべてのアクションの自動更新をオンまたはオフにすることができるのは、全体管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-167">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="6bc2a-168">コンプライアンスマネージャー管理者は、個々のアクションに対して自動更新を有効にできますが、すべてのアクションに対してグローバルに行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-168">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="6bc2a-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6bc2a-169">Learn more</span></span>

<span data-ttu-id="6bc2a-170">[「セキュリティで保護されたスコアの更新の管理](compliance-manager-release-notes.md#secure-score)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-170">[Read about managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="6bc2a-171">コンプライアンススコアダッシュボードを理解する</span><span class="sxs-lookup"><span data-stu-id="6bc2a-171">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="6bc2a-172">コンプライアンススコアダッシュボードは、現在のコンプライアンス状況を一目で確認できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-172">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="6bc2a-173">![コンプライアンススコア-ダッシュボード](../media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="6bc2a-173">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="6bc2a-174">総合コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="6bc2a-174">Overall compliance score</span></span>

<span data-ttu-id="6bc2a-175">コンプライアンススコアは、トップレベルで強調されています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-175">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="6bc2a-176">この図は、主要なデータ保護の標準と規制に対応する向上したアクションを完了するために達成されたポイントに基づくパーセンテージを示しています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-176">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="6bc2a-177">初めてコンプライアンススコアを取得すると、最初のスコアは 365 Microsoft の組み込みの[データ保護基準](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)(一般的な業界の規制と標準を含む一連のコントロール) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-177">When you come to Compliance Score for the first time, your initial score is based on the built-in [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="6bc2a-178">コンプライアンススコアは既存の Microsoft 365 ソリューションをスキャンし、現在のプライバシーとセキュリティの設定に基づく初期評価を提供します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-178">Compliance Score scans your existing Microsoft 365 solutions and gives you an initial assessment based on your current privacy and security settings.</span></span> <span data-ttu-id="6bc2a-179">組織に関連する評価を追加すると、スコアがよりわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-179">As you add assessments that are relevant to your organization, your score becomes more meaningful for you.</span></span>

#### <a name="learn-more"></a><span data-ttu-id="6bc2a-180">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6bc2a-180">Learn more</span></span>
<span data-ttu-id="6bc2a-181">[コンプライアンススコアの計算方法について理解](compliance-score-methodology.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-181">[Understand how your compliance score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="6bc2a-182">重要な改善アクション</span><span class="sxs-lookup"><span data-stu-id="6bc2a-182">Key improvement actions</span></span>

<span data-ttu-id="6bc2a-183">このセクションでは、全体的なコンプライアンススコアに最大の効果を得るために、今すぐに実行できる主な改善アクションを示します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="6bc2a-184">スコアに影響を与えるソリューション</span><span class="sxs-lookup"><span data-stu-id="6bc2a-184">Solutions that affect your score</span></span>

<span data-ttu-id="6bc2a-185">このセクションでは、スコアにプラスの影響を与える最大の機会を得るアクションと、各ソリューションにおける未解決の改善アクションの数についての解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-185">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="6bc2a-186">コンプライアンススコアの内訳</span><span class="sxs-lookup"><span data-stu-id="6bc2a-186">Compliance Score breakdown</span></span>

<span data-ttu-id="6bc2a-187">このセクションでは、次の2つの異なる方法でスコアの詳細な表示を示します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-187">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="6bc2a-188">[**カテゴリ**]: [情報を保護] や [デバイスの管理] など、データ保護カテゴリ内の全体的なスコアの割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-188">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="6bc2a-189">**評価**: GDPR または NIST 800-53 など、特定のコンプライアンスおよびデータ保護の標準、規制、法律の評価を管理する際の進捗状況の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-189">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="6bc2a-190">ダッシュボードビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="6bc2a-190">Filtering your dashboard view</span></span>

<span data-ttu-id="6bc2a-191">特定の規制や基準、ソリューション、アクションの種類、評価グループ、またはデータ保護カテゴリに関連するアイテムのみを表示するように、ダッシュボードビューをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-191">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, assessment groups, or data protection categories.</span></span> <span data-ttu-id="6bc2a-192">この方法でビューをフィルター処理すると、フィルター条件に基づいて、使用可能なポイントの合計数が表示されたダッシュボードのスコアのフィルター処理も行われます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-192">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="6bc2a-193">フィルターを適用するには</span><span class="sxs-lookup"><span data-stu-id="6bc2a-193">To apply filters:</span></span>

1. <span data-ttu-id="6bc2a-194">ダッシュボードの右上にある [**フィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-194">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="6bc2a-195">**フィルターのフライアウト**ウィンドウからフィルター条件を選択し、[**適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-195">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="6bc2a-196">フィルターを適用すると、リアルタイムで調整されたスコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-196">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="6bc2a-197">コンプライアンススコアの割合と内訳の情報、および改善のアクションとソリューションは、現在、フィルター条件でカバーされるデータにのみ関連しています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-197">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="6bc2a-198">コンプライアンススコアからサインアウトすると、再度サインインしたときに、フィルター処理されたビューが残ります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-198">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="6bc2a-199">フィルターを削除するには</span><span class="sxs-lookup"><span data-stu-id="6bc2a-199">To remove filters:</span></span>

- <span data-ttu-id="6bc2a-200">コンプライアンススコアの上にある [**適用されたフィルター** ] 見出しで、削除する個々のフィルターの横にある [ **X** ] を選択します。や</span><span class="sxs-lookup"><span data-stu-id="6bc2a-200">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="6bc2a-201">ダッシュボードの右上にある [**フィルター** ] を選択し、[**フィルターのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-201">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="improvement-actions-page"></a><span data-ttu-id="6bc2a-202">向上アクションページ</span><span class="sxs-lookup"><span data-stu-id="6bc2a-202">Improvement actions page</span></span>

<span data-ttu-id="6bc2a-203">[改善アクション](compliance-score-improvement-actions.md)により、コンプライアンスアクティビティが集中管理され、データ保護の規則や標準に沿った連携が容易になります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-203">[Improvement actions](compliance-score-improvement-actions.md) centralize your compliance activities and help you align with data protection regulations and standards.</span></span> <span data-ttu-id="6bc2a-204">各改善アクションには、詳細な実装ガイダンスと、適切なソリューションを起動するためのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-204">Each improvement action gives detailed implementation guidance and a link to launch you into the appropriate solution.</span></span> <span data-ttu-id="6bc2a-205">実装とテストの作業を実行するために、組織内のユーザーにアクションを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-205">Actions can be assigned to users in your organization to perform implementation and testing work.</span></span> <span data-ttu-id="6bc2a-206">また、ドキュメント、メモ、およびレコードの状態の更新を、改善アクションの中に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-206">You can also store documentation, notes, and record status updates within the improvement action.</span></span>

### <a name="view-your-improvement-actions"></a><span data-ttu-id="6bc2a-207">改善アクションを表示する</span><span class="sxs-lookup"><span data-stu-id="6bc2a-207">View your improvement actions</span></span>

<span data-ttu-id="6bc2a-208">コンプライアンススコアダッシュボードには、**主要な改善アクション**が表示されます。これは、最も重要な問題に対処する最も利用可能なポイントであるものです。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-208">The Compliance Score dashboard shows your **key improvement actions**, which are the ones with the most available points that address the most important issues.</span></span>

<span data-ttu-id="6bc2a-209">すべての改善アクションを表示するには、ダッシュボードの [**改善アクション**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-209">To view all of your improvement actions, select the **Improvement actions** tab on your dashboard.</span></span> <span data-ttu-id="6bc2a-210">または、ダッシュボードの主な改善アクションの一覧の下にある [**すべての改善アクションの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-210">Or, select **View all improvement actions** underneath the list of key improvement actions on your dashboard.</span></span>

<span data-ttu-id="6bc2a-211">アクションのリストが長い場合は、ビューをフィルター処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-211">If you have a long list of actions, it may be helpful to filter your view.</span></span> <span data-ttu-id="6bc2a-212">アクションリストの右上隅にある [**フィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-212">Select **Filter** at the upper-right corner of the actions list.</span></span> <span data-ttu-id="6bc2a-213">[**フィルター**の選択] ウィンドウが表示されたら、規制と基準、ソリューション、およびグループに基づいて条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-213">When the **Filters** flyout pane appears, select your criteria based on regulations and standards, solution, and group.</span></span> <span data-ttu-id="6bc2a-214">右上隅の [**グループ]** を選択して、ビューをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-214">You can also customize your view by selecting **Group** in the upper-right corner.</span></span> <span data-ttu-id="6bc2a-215">ドロップダウンメニューから、グループ、ソリューション、カテゴリ、アクションの種類、またはステータス別に表示するものを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-215">From the drop-down menu, select to view by group, solution, category, action type, or status.</span></span>

<span data-ttu-id="6bc2a-216">このページの既定のビューには、向上したアクションが [**成功**] テストの状態として表示されません。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-216">The default view for this page does not show improvement actions with a test status of **Passed**.</span></span> <span data-ttu-id="6bc2a-217">テストに合格したアクションを表示するには、[フィルター] ポップアップウィンドウの [**成功**] ボックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-217">To view actions that have passed testing, check the **Passed** box in the Filters flyout pane.</span></span> <span data-ttu-id="6bc2a-218">スコアに対して**通過**したカウントがテスト状態であるアクションのみ。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-218">Only actions with a test status of **Passed** count toward your score.</span></span>

<span data-ttu-id="6bc2a-219">[改善アクション] ページには、改善アクションごとに次のデータポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-219">The improvement actions page shows the following data points for each improvement action:</span></span>

- <span data-ttu-id="6bc2a-220">**スコアの影響**: アクションを完了すると、全体的なスコアが増加するポイント</span><span class="sxs-lookup"><span data-stu-id="6bc2a-220">**Score impact**: the points by which your overall score will increase when completing the action</span></span>
- <span data-ttu-id="6bc2a-221">**規制**: アクションに関連する規制または標準</span><span class="sxs-lookup"><span data-stu-id="6bc2a-221">**Regulations**: the regulation or standard pertaining to the action</span></span>
- <span data-ttu-id="6bc2a-222">**グループ**: アクションを割り当てたグループ。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-222">**Group**: the group to which you assigned the action</span></span>
- <span data-ttu-id="6bc2a-223">**解決策**: アクションを実行するために使用できるソリューション</span><span class="sxs-lookup"><span data-stu-id="6bc2a-223">**Solutions**: the solution where you can go to perform the action</span></span>
- <span data-ttu-id="6bc2a-224">**評価**: アクションが存在する評価 (特定のコンプライアンスの目標を達成するために統制したもの)</span><span class="sxs-lookup"><span data-stu-id="6bc2a-224">**Assessments**: the assessment (which organizes controls to meet a certain compliance objective) in which the action resides</span></span>
- <span data-ttu-id="6bc2a-225">**カテゴリ**: 関連データ保護カテゴリ ([情報の保護]、[デバイスの管理] など)</span><span class="sxs-lookup"><span data-stu-id="6bc2a-225">**Categories**: the related data protection category (such as, protect information, manage devices, etc.)</span></span>
- <span data-ttu-id="6bc2a-226">**テストの状態**:</span><span class="sxs-lookup"><span data-stu-id="6bc2a-226">**Test status**:</span></span>
    - <span data-ttu-id="6bc2a-227">**なし**–状態の更新は記録されません。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-227">**None** – no status update recorded</span></span>
    - <span data-ttu-id="6bc2a-228">**評価されません-テストが開始されていません**</span><span class="sxs-lookup"><span data-stu-id="6bc2a-228">**Not assessed** - testing hasn't started</span></span>
    - <span data-ttu-id="6bc2a-229">**成功した実装のテスト**が成功した</span><span class="sxs-lookup"><span data-stu-id="6bc2a-229">**Passed** - implementation successfully tested</span></span>
    - <span data-ttu-id="6bc2a-230">**失敗したリスクが低い**-テスト失敗、低リスク</span><span class="sxs-lookup"><span data-stu-id="6bc2a-230">**Failed low risk** - testing failed, low risk</span></span>
    - <span data-ttu-id="6bc2a-231">**失敗中の危険度**-テスト失敗、中程度のリスク</span><span class="sxs-lookup"><span data-stu-id="6bc2a-231">**Failed medium risk** - testing failed, medium risk</span></span>
    - <span data-ttu-id="6bc2a-232">**高リスクの失敗**-テスト失敗、高リスク</span><span class="sxs-lookup"><span data-stu-id="6bc2a-232">**Failed high risk** - testing failed, high risk</span></span>
    - <span data-ttu-id="6bc2a-233">**範囲内にない**-アクションは評価の対象外で、スコアに影響を与えません</span><span class="sxs-lookup"><span data-stu-id="6bc2a-233">**Not in scope** – the action is not in scope for the assessment and doesn't impact your score</span></span>
    - <span data-ttu-id="6bc2a-234">**検出対象**: 手動テストの場合は、アクションが実装されているが、テストされていないことを示します。自動テストの場合は、アクションが自動化の結果を待機していることを示します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-234">**To be detected** - for manual test, indicates an action has been implemented but not tested; for automated test, indicates an action is waiting for automation result</span></span>
    - <span data-ttu-id="6bc2a-235">**検出できませんでした**-自動状態を判別できません</span><span class="sxs-lookup"><span data-stu-id="6bc2a-235">**Could not be detected** - automated status can't be determined</span></span>
    - <span data-ttu-id="6bc2a-236">部分的な**テスト**–部分的な得点を与える自動スコアリング</span><span class="sxs-lookup"><span data-stu-id="6bc2a-236">**Partially tested** – automated scoring that awards partial points</span></span>
- <span data-ttu-id="6bc2a-237">**獲得**したポイント: 最大許容されるポイント数</span><span class="sxs-lookup"><span data-stu-id="6bc2a-237">**Points achieved**: number of points earned out of the maximum possible</span></span>

#### <a name="learn-more"></a><span data-ttu-id="6bc2a-238">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6bc2a-238">Learn more</span></span>
<span data-ttu-id="6bc2a-239">[「改善アクションに関する作業を割り当てて実行する」を参照してください](compliance-score-improvement-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-239">[See how to assign and perform work on improvement actions](compliance-score-improvement-actions.md).</span></span>

## <a name="solutions-page"></a><span data-ttu-id="6bc2a-240">ソリューションページ</span><span class="sxs-lookup"><span data-stu-id="6bc2a-240">Solutions page</span></span>

<span data-ttu-id="6bc2a-241">[ソリューション] ページには、ソリューションごとに構成された、獲得されたポイントと潜在的なポイントの比率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-241">The solutions page shows the share of earned and potential points as organized by solution.</span></span> <span data-ttu-id="6bc2a-242">このビューで残っているポイントと改善アクションを表示することで、より迅速に対処する必要があるソリューションを理解できます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-242">Viewing your remaining points and improvement actions from this view helps you understand which solutions need more immediate attention.</span></span>

<span data-ttu-id="6bc2a-243">[コンプライアンススコア] ダッシュボードの [**ソリューション**] タブを選択して、[ソリューション] ページを検索します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-243">Find the solutions page by selecting the **Solutions** tab on your Compliance Score dashboard.</span></span> <span data-ttu-id="6bc2a-244">ダッシュボードの右上のセクションにある**スコアに影響を与えるソリューション**の下にある [**すべてのソリューションの表示**] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-244">You can also select **View all solutions** underneath **Solutions that affect your score** in the upper-right section of your dashboard.</span></span>

### <a name="filtering-your-solutions-view"></a><span data-ttu-id="6bc2a-245">ソリューションビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="6bc2a-245">Filtering your solutions view</span></span>

<span data-ttu-id="6bc2a-246">ソリューションのビューをフィルター処理するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-246">To filter your view of solutions:</span></span>

1. <span data-ttu-id="6bc2a-247">評価リストの左上隅にある [ **Filter** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-247">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="6bc2a-248">[**フィルター** ] ポップアップウィンドウで、目的の条件 (標準および規制、ソリューション、アクションの種類、コンプライアンスマネージャーグループ、カテゴリ) の横にチェックマークを配置します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-248">On the **Filters** flyout pane, place a check next to the desired criteria (standards and regulations, solution, action type, Compliance Manager group, category).</span></span>
3. <span data-ttu-id="6bc2a-249">[**適用**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-249">Select the **Apply** button.</span></span> <span data-ttu-id="6bc2a-250">フィルターウィンドウが閉じ、フィルター処理されたビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-250">The filter pane will close and you’ll see your filtered view.</span></span>

<span data-ttu-id="6bc2a-251">また、評価リストの上にある [**グループ**] ドロップダウンメニューからグループ化の種類を選択することによって、グループ、製品、または規制によって評価を表示するようにビューを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-251">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="taking-actions-from-the-solution-page"></a><span data-ttu-id="6bc2a-252">[ソリューション] ページからアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="6bc2a-252">Taking actions from the solution page</span></span>

<span data-ttu-id="6bc2a-253">[ソリューション] ページには、改善アクションに接続されている組織のソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-253">The solutions page displays your organization’s solutions that are connected to improvement actions.</span></span> <span data-ttu-id="6bc2a-254">この表には、全体的なスコアに対する各ソリューションの貢献度、そのソリューション内で達成されているスコア向上ポイント、およびそのソリューションでグループ化された、スコアを増やすことができる改善アクションの残りの数が一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-254">The table lists each solution’s contribution to your overall score, the score-enhancing points achieved and possible within that solution, and the remaining number of improvement actions grouped in that solution that can increase your score.</span></span>

<span data-ttu-id="6bc2a-255">この画面からアクションを実行するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-255">There are two ways you can take action from this screen:</span></span>

1. <span data-ttu-id="6bc2a-256">目的のソリューションの行の [**残りの操作**] 列で、ハイパーリンクされた番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-256">On the row of your intended solution, under the **Remaining actions** column, select the hyperlinked number.</span></span> <span data-ttu-id="6bc2a-257">そのソリューションに対してテストされていない改善アクションが表示されている [機能向上のアクション] 画面のフィルターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-257">You’ll see a filtered view of the improvement actions screen showing untested improvement actions for that solution.</span></span>

2. <span data-ttu-id="6bc2a-258">目的のソリューションの行の [**ソリューションを開く**] 列で、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-258">On the row of your intended solution, under the **Open solution** column, select **Open**.</span></span> <span data-ttu-id="6bc2a-259">推奨されるアクションを実行できる、Microsoft 365 および Office 365 セキュリティ/コンプライアンスセンターのソリューションまたは場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-259">You’ll see the solution or location in the Microsoft 365 and Office 365 security and compliance centers where you can take the recommended action.</span></span>

## <a name="assessments-page"></a><span data-ttu-id="6bc2a-260">評価ページ</span><span class="sxs-lookup"><span data-stu-id="6bc2a-260">Assessments page</span></span>

<span data-ttu-id="6bc2a-261">[評価] ページには、組織に設定されているすべての[評価](compliance-score-assessments.md)が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-261">The assessments page lists all the [assessments](compliance-score-assessments.md) you set up for your organization.</span></span> <span data-ttu-id="6bc2a-262">コンプライアンススコアの分母は、追跡対象の評価すべてによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-262">Your Compliance Score denominator is determined by all your tracked assessments.</span></span> <span data-ttu-id="6bc2a-263">評価の数が多いほど、向上したアクションのページに表示される改善アクションが増え、スコアの分母が高くなります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-263">The more assessments you add, the more improvement actions you see on your improvement actions page, and the higher your score denominator is.</span></span>

<span data-ttu-id="6bc2a-264">このページでは、各評価に関する重要な情報を要約します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-264">This page summarizes key information about each assessment:</span></span>

- <span data-ttu-id="6bc2a-265">**評価**: 評価の名前</span><span class="sxs-lookup"><span data-stu-id="6bc2a-265">**Assessment**: name of the assessment</span></span>
- <span data-ttu-id="6bc2a-266">**状態**:</span><span class="sxs-lookup"><span data-stu-id="6bc2a-266">**Status**:</span></span>
    - <span data-ttu-id="6bc2a-267">**Complete** -すべてのコントロールの状態が "引き渡されました"、または少なくとも1つが渡され、残りの部分は "スコープ外" になります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-267">**Complete** -  all controls have a status of “passed,” or at least one is passed and the rest are “out of scope”</span></span>
    - <span data-ttu-id="6bc2a-268">**不完全**-少なくとも1つのコントロールの状態が "failed" になっています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-268">**Incomplete** – at least one control has a status of “failed"</span></span>
    - <span data-ttu-id="6bc2a-269">**None** -すべてのコントロールがテストされていません</span><span class="sxs-lookup"><span data-stu-id="6bc2a-269">**None** - all controls have have not been tested</span></span>
    - <span data-ttu-id="6bc2a-270">**進行**中の改善アクションには、「進行中」、「部分的なクレジット」、「未検出」などのその他のステータスがあります。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-270">**In progress** - improvement actions have any other status, including “in progress,” “partial credit,” or “undetected</span></span>
- <span data-ttu-id="6bc2a-271">**評価の進行状況**: テストに成功したコントロールの数によって測定された、完了までに行われた作業の割合</span><span class="sxs-lookup"><span data-stu-id="6bc2a-271">**Assessment progress**: the percentage of the work done toward completion, as measured by the number of controls successfully tested</span></span>
- <span data-ttu-id="6bc2a-272">**向上**したアクション: コントロールの実装を満たす完了したアクションの数</span><span class="sxs-lookup"><span data-stu-id="6bc2a-272">**Your improvement actions**: the number of completed actions to satisfy implementation of your controls</span></span>
- <span data-ttu-id="6bc2a-273">**Microsoft actions**: microsoft コントロールの実装を満たす完了したアクションの数</span><span class="sxs-lookup"><span data-stu-id="6bc2a-273">**Microsoft actions**: the number of completed actions to satisfy implementation of Microsoft controls</span></span>
- <span data-ttu-id="6bc2a-274">**グループ**: 評価が属するグループの名前</span><span class="sxs-lookup"><span data-stu-id="6bc2a-274">**Group**: name of the group the assessment belongs to</span></span>
- <span data-ttu-id="6bc2a-275">**製品**: 関連付けられている Microsoft 365 サービス</span><span class="sxs-lookup"><span data-stu-id="6bc2a-275">**Product**: associated Microsoft 365 service</span></span>
- <span data-ttu-id="6bc2a-276">**規制**: 評価に適用される標準、ポリシー、法規制</span><span class="sxs-lookup"><span data-stu-id="6bc2a-276">**Regulation**: the regulatory standard, policy, or law that applies to the assessment</span></span>

### <a name="filtering-your-assessments-view"></a><span data-ttu-id="6bc2a-277">評価ビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="6bc2a-277">Filtering your assessments view</span></span>

<span data-ttu-id="6bc2a-278">評価の表示をフィルター処理するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-278">To filter you view of assessments:</span></span>

1. <span data-ttu-id="6bc2a-279">評価リストの左上隅にある [ **Filter** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-279">Select **Filter** at the top-left corner of your assessments list.</span></span>
2. <span data-ttu-id="6bc2a-280">[**フィルター** ] ポップアップウィンドウで、目的の条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-280">On the **Filters** flyout pane, check your desired criteria.</span></span>
3. <span data-ttu-id="6bc2a-281">[適用] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-281">Select the Apply button.</span></span> <span data-ttu-id="6bc2a-282">フィルターウィンドウが閉じ、フィルター処理されたビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-282">The filter pane will close and you will see your filtered view.</span></span>

<span data-ttu-id="6bc2a-283">また、評価リストの上にある [**グループ**] ドロップダウンメニューからグループ化の種類を選択することによって、グループ、製品、または規制によって評価を表示するようにビューを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-283">You can also modify your view to see assessments by group, product, or regulation by selecting the type of grouping from the **Group** drop-down menu above your assessments list.</span></span>

### <a name="default-assessment"></a><span data-ttu-id="6bc2a-284">既定の評価</span><span class="sxs-lookup"><span data-stu-id="6bc2a-284">Default assessment</span></span>

<span data-ttu-id="6bc2a-285">既定では、[評価] ページに[Microsoft 365 データ保護のベースライン](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)評価が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-285">By default, you'll see the [Microsoft 365 data protection baseline](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) assessment on the assessments page.</span></span> <span data-ttu-id="6bc2a-286">また、コンプライアンススコアは、評価を構築するための[テンプレート](compliance-score-templates.md)を使用する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-286">Compliance Score also provides several ready to use [templates](compliance-score-templates.md) from which to build assessments.</span></span>

## <a name="next-step"></a><span data-ttu-id="6bc2a-287">次の手順</span><span class="sxs-lookup"><span data-stu-id="6bc2a-287">Next step</span></span>
<span data-ttu-id="6bc2a-288">[評価を設定](compliance-score-assessments.md)して、コンプライアンススコアをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6bc2a-288">Customize Compliance Score by [setting up assessments](compliance-score-assessments.md).</span></span>