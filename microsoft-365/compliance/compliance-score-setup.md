---
title: Microsoft コンプライアンススコアの設定
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
ms.openlocfilehash: 7a0030ed417e21484717b6edf12406d2f5e760e5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140862"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="72e9f-103">Microsoft コンプライアンススコア (プレビュー) の設定</span><span class="sxs-lookup"><span data-stu-id="72e9f-103">Microsoft Compliance Score (preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="72e9f-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="72e9f-104">Before you begin</span></span>

<span data-ttu-id="72e9f-105">通常、コンプライアンススコアにアクセスする最初のユーザーは、組織の Microsoft 365 グローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="72e9f-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="72e9f-106">初めてコンプライアンススコアを参照する場合は、グローバル管理者サインインをお勧めし、以下の説明に従ってユーザー権限を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="72e9f-106">We recommend the global admin sign-in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="72e9f-107">サインイン</span><span class="sxs-lookup"><span data-stu-id="72e9f-107">Sign in</span></span>

1. <span data-ttu-id="72e9f-108">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)に移動し、microsoft 365 のグローバル管理者アカウントで**サインイン**します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="72e9f-109">左側のナビゲーション ウィンドウで、[**コンプライアンス スコア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="72e9f-110">その後、[自分のスコアとともにコンプライアンス スコアのダッシュボード](#understand-the-compliance-score-dashboard)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

<span data-ttu-id="72e9f-111">Access コンプライアンススコアへの直接リンクは次[https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore)のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72e9f-111">The direct link to access Compliance Score is: [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="72e9f-112">ユーザーのアクセス許可を設定して役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="72e9f-112">Set user permissions and assign roles</span></span>

<span data-ttu-id="72e9f-113">コンプライアンススコアは、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-113">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="72e9f-114">コンプライアンススコアにアクセスできるのは、役割が割り当てられているユーザーだけで、各ユーザーが許可する操作は、役割の種類によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-114">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="72e9f-115">アクセス許可を設定する場所</span><span class="sxs-lookup"><span data-stu-id="72e9f-115">Where to set permissions</span></span>

<span data-ttu-id="72e9f-116">組織のグローバル管理者は、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)または[コンプライアンスマネージャー](compliance-manager-overview.md#permissions)でユーザー権限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-116">The global admin for your organization can set user permissions in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) or in [Compliance Manager](compliance-manager-overview.md#permissions).</span></span> <span data-ttu-id="72e9f-117">これらのいずれかの場所で役割が設定されると、ユーザーはコンプライアンスのスコアとコンプライアンスマネージャーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="72e9f-117">Once roles are set in either of these locations, users can access Compliance Score as well as Compliance Manager.</span></span>

### <a name="role-types"></a><span data-ttu-id="72e9f-118">役割の種類</span><span class="sxs-lookup"><span data-stu-id="72e9f-118">Role types</span></span>

<span data-ttu-id="72e9f-119">次の表に、各[AZURE AD の役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)を既存のコンプライアンスマネージャーの役割にマップする方法と、各役割によって許可される機能を示します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-119">The table below shows how each [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span> <span data-ttu-id="72e9f-120">コンプライアンススコアにアクセスするには、少なくとも Azure AD グローバルリーダーの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="72e9f-120">Users will need at least the Azure AD global reader role to access Compliance Score.</span></span>


| <span data-ttu-id="72e9f-121">ユーザーは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-121">User can:</span></span> | <span data-ttu-id="72e9f-122">Azure AD の役割</span><span class="sxs-lookup"><span data-stu-id="72e9f-122">Azure AD role</span></span> | <span data-ttu-id="72e9f-123">コンプライアンスマネージャーの役割</span><span class="sxs-lookup"><span data-stu-id="72e9f-123">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="72e9f-124">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="72e9f-124">**Read but not edit data**</span></span>| <span data-ttu-id="72e9f-125">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="72e9f-125">Azure AD global reader</span></span>  | <span data-ttu-id="72e9f-126">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="72e9f-126">Azure AD global reader</span></span> | 
| <span data-ttu-id="72e9f-127">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="72e9f-127">**Read but not edit data**</span></span>| <span data-ttu-id="72e9f-128">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="72e9f-128">Security reader</span></span> | <span data-ttu-id="72e9f-129">コンプライアンスマネージャーリーダー</span><span class="sxs-lookup"><span data-stu-id="72e9f-129">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="72e9f-130">**データを編集する**</span><span class="sxs-lookup"><span data-stu-id="72e9f-130">**Edit data**</span></span>| <span data-ttu-id="72e9f-131">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-131">Compliance administrator</span></span> | <span data-ttu-id="72e9f-132">コンプライアンスマネージャー共同作成者</span><span class="sxs-lookup"><span data-stu-id="72e9f-132">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="72e9f-133">**テスト結果を編集する**</span><span class="sxs-lookup"><span data-stu-id="72e9f-133">**Edit test results**</span></span>| <span data-ttu-id="72e9f-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-134">Compliance administrator</span></span> | <span data-ttu-id="72e9f-135">コンプライアンスマネージャーの査定者</span><span class="sxs-lookup"><span data-stu-id="72e9f-135">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="72e9f-136">**評価、およびテンプレートとテナントデータを管理する**</span><span class="sxs-lookup"><span data-stu-id="72e9f-136">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="72e9f-137">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-137">Compliance administrator</span></span><br><span data-ttu-id="72e9f-138">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-138">Compliance data administrator</span></span><br><span data-ttu-id="72e9f-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-139">Security administrator</span></span> | <span data-ttu-id="72e9f-140">コンプライアンスマネージャー管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-140">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="72e9f-141">**ユーザーを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="72e9f-141">**Assign users**</span></span>| <span data-ttu-id="72e9f-142">全体管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-142">Global administrator</span></span> | <span data-ttu-id="72e9f-143">ポータル管理者</span><span class="sxs-lookup"><span data-stu-id="72e9f-143">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="72e9f-144">コンプライアンススコアからコンプライアンスマネージャーに移行してタスクを完了すると (たとえば、評価を管理する場合)、ブラウザーで新しいタブが開き、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-144">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="72e9f-145">上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="72e9f-145">In the top section with the header, "Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="72e9f-146">アカウントにサインインし、[コンプライアンスマネージャーにアクセスするには**サインイン**] を選択します。資格情報を再入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="72e9f-146">Sign in to your account," select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="72e9f-147">セキュリティで保護されたスコアの自動更新を構成する</span><span class="sxs-lookup"><span data-stu-id="72e9f-147">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="72e9f-148">既定では、すべての新しいテナントには、[セキュリティで保護さ](../security/mtp/microsoft-secure-score.md)れたスコア自動更新が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-148">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="72e9f-149">セキュリティで保護されたスコアで監視されているすべてのアクションは、コンプライアンススコアの同じアクションの状態を自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-149">All actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="72e9f-150">全体管理者はこの設定を管理して、すべてのアクションの自動更新をオフにしたり、操作の更新を個別に設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-150">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="72e9f-151">パブリックプレビューでは、Microsoft Service Trust Portal (コンプライアンスマネージャーが配置されている場合) にアクセスして、セキュリティで保護されたスコアの更新を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72e9f-151">During public preview, you'll need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="72e9f-152">セキュリティで保護されたスコアの自動更新を管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-152">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="72e9f-153">グローバル管理者アカウントを使用して、[サービス信頼ポータル](https://servicetrust.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="72e9f-153">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="72e9f-154">サービス信頼ポータルのトップメニューバーで、[**詳細**設定] の下の [**管理**] を選択し、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-154">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="72e9f-155">[ **Secure Score** ] タブで、対応するボタンを選択して、**すべてのアクション**に対してオンにするか、**すべてのアクションに対し**て無効にするか、または**アクションごとに設定します。**</span><span class="sxs-lookup"><span data-stu-id="72e9f-155">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="72e9f-156">[**アクションごとに設定**] を選択した場合は、個々のアクションについてセキュリティで保護されたスコア更新を有効にする追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-156">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="72e9f-157">上部のメニューから [**コンプライアンスマネージャー** ] を選択します (従来の製品である [コンプライアンスマネージャー (クラシック)] は選択しないでください)。</span><span class="sxs-lookup"><span data-stu-id="72e9f-157">Select **Compliance Manager** from the top menu (do not select "Compliance Manager (classic)," which is a legacy product).</span></span>

5. <span data-ttu-id="72e9f-158">画面の右上隅にある [**テナント管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-158">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="72e9f-159">[**顧客の操作**] ウィンドウで、[**影響を受ける操作**] 列の下に、省略記号 (**...**) を含む目的のアクションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-159">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="72e9f-160">省略記号をクリックして、[編集] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="72e9f-160">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="72e9f-161">**セキュリティで保護されたスコアの継続更新**の切り替えトグルスイッチをオンに切り替え**ます。**</span><span class="sxs-lookup"><span data-stu-id="72e9f-161">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="72e9f-162">[保存] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="72e9f-162">Select **Save.**</span></span> <span data-ttu-id="72e9f-163">セキュリティで保護されたスコア継続的監視は、そのアクションに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-163">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="72e9f-164">**注:** すべてのアクションの自動更新をオンまたはオフにすることができるのは、全体管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="72e9f-164">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="72e9f-165">コンプライアンスマネージャー管理者は、個々のアクションに対して自動更新を有効にできますが、すべてのアクションに対してグローバルに行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="72e9f-165">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="72e9f-166">「[セキュリティで保護されたスコアの更新の管理](compliance-manager-release-notes.md#secure-score)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72e9f-166">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="72e9f-167">コンプライアンススコアダッシュボードを理解する</span><span class="sxs-lookup"><span data-stu-id="72e9f-167">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="72e9f-168">コンプライアンススコアダッシュボードは、現在のコンプライアンス状況を一目で確認できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-168">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="72e9f-169">![コンプライアンススコア-ダッシュボード](../media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="72e9f-169">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="72e9f-170">総合コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="72e9f-170">Overall compliance score</span></span>

<span data-ttu-id="72e9f-171">コンプライアンススコアは、トップレベルで強調されています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-171">Your compliance score is featured prominently at the top.</span></span> <span data-ttu-id="72e9f-172">この図は、主要なデータ保護の標準と規制に対応する向上したアクションを完了するために達成されたポイントに基づくパーセンテージを示しています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-172">It shows a percentage based on points achievable for completing improvement actions that address key data protection standards and regulations.</span></span>

<span data-ttu-id="72e9f-173">初めてコンプライアンススコアを取得すると、最初のスコアは 365 Microsoft の組み込みのデータ保護基準 (一般的な業界の規制と標準を含む一連のコントロール) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-173">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="72e9f-174">コンプライアンススコアは既存の Microsoft 365 ソリューションのシステムをスキャンするので、現在組織で有効になっているプライバシーとセキュリティの設定に基づいて、コンプライアンスに関する最初の評価を提供します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-174">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="72e9f-175">組織に関連する評価を追加すると、スコアがよりわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="72e9f-175">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="72e9f-176">[スコアの計算方法](compliance-score-methodology.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-176">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="72e9f-177">重要な改善アクション</span><span class="sxs-lookup"><span data-stu-id="72e9f-177">Key improvement actions</span></span>

<span data-ttu-id="72e9f-178">このセクションでは、全体的なコンプライアンススコアに最大の効果を得るために、今すぐに実行できる主な改善アクションを示します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-178">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="72e9f-179">スコアに影響を与えるソリューション</span><span class="sxs-lookup"><span data-stu-id="72e9f-179">Solutions that affect your score</span></span>

<span data-ttu-id="72e9f-180">このセクションでは、スコアにプラスの影響を与える最大の機会を得るアクションと、各ソリューションにおける未解決の改善アクションの数についての解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-180">This section shows solutions containing actions with the greatest opportunity to positively impact your score, and the number of outstanding improvement actions in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="72e9f-181">コンプライアンススコアの内訳</span><span class="sxs-lookup"><span data-stu-id="72e9f-181">Compliance Score breakdown</span></span>

<span data-ttu-id="72e9f-182">このセクションでは、次の2つの異なる方法でスコアの詳細な表示を示します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-182">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="72e9f-183">[**カテゴリ**]: [情報を保護] や [デバイスの管理] など、データ保護カテゴリ内の全体的なスコアの割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-183">**Categories**: shows the percentage of your overall score within data protection categories, such as "protect information" or "manage devices."</span></span>
- <span data-ttu-id="72e9f-184">**評価**: GDPR または NIST 800-53 など、特定のコンプライアンスおよびデータ保護の標準、規制、法律の評価を管理する際の進捗状況の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-184">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="72e9f-185">ダッシュボードビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="72e9f-185">Filtering your dashboard view</span></span>

<span data-ttu-id="72e9f-186">ダッシュボードビューをフィルター処理して、特定の規制や基準、ソリューション、アクションの種類、[設定した評価のグループ](working-with-compliance-manager.md#groups)、またはデータ保護カテゴリに関連するアイテムのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-186">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="72e9f-187">この方法でビューをフィルター処理すると、フィルター条件に基づいて、使用可能なポイントの合計数が表示されたダッシュボードのスコアのフィルター処理も行われます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-187">Filtering your view in this way will also filter the score on your dashboard, showing how many points you've achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="72e9f-188">フィルターを適用するには</span><span class="sxs-lookup"><span data-stu-id="72e9f-188">To apply filters:</span></span>

1. <span data-ttu-id="72e9f-189">ダッシュボードの右上にある [**フィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-189">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="72e9f-190">**フィルターのフライアウト**ウィンドウからフィルター条件を選択し、[**適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-190">Select your filter criteria from the **Filters** flyout pane, then select **Apply**.</span></span>

<span data-ttu-id="72e9f-191">フィルターを適用すると、リアルタイムで調整されたスコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72e9f-191">After you apply a filter, you'll see your score adjusted in real time.</span></span> <span data-ttu-id="72e9f-192">コンプライアンススコアの割合と内訳の情報、および改善のアクションとソリューションは、現在、フィルター条件でカバーされるデータにのみ関連しています。</span><span class="sxs-lookup"><span data-stu-id="72e9f-192">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="72e9f-193">コンプライアンススコアからサインアウトすると、再度サインインしたときに、フィルター処理されたビューが残ります。</span><span class="sxs-lookup"><span data-stu-id="72e9f-193">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="72e9f-194">フィルターを削除するには</span><span class="sxs-lookup"><span data-stu-id="72e9f-194">To remove filters:</span></span>

- <span data-ttu-id="72e9f-195">コンプライアンススコアの上にある [**適用されたフィルター** ] 見出しで、削除する個々のフィルターの横にある [ **X** ] を選択します。や</span><span class="sxs-lookup"><span data-stu-id="72e9f-195">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="72e9f-196">ダッシュボードの右上にある [**フィルター** ] を選択し、[**フィルターのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-196">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="72e9f-197">次の手順</span><span class="sxs-lookup"><span data-stu-id="72e9f-197">Next step</span></span>

<span data-ttu-id="72e9f-198">「[コンプライアンススコアの処理](working-with-compliance-score.md)」にアクセスして、スコアを改善するためのアクションを実行する方法のワークフローを理解します。</span><span class="sxs-lookup"><span data-stu-id="72e9f-198">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>