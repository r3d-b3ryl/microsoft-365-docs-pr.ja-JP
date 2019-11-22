---
title: Microsoft コンプライアンススコアの設定
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
description: サインインする方法、アクセス許可を設定する方法、および Microsoft コンプライアンススコアのダッシュボードを理解する方法について説明します。これにより、リスク評価を簡素化および自動化できます。
ms.openlocfilehash: 7bff479d4cd7e3f200f7fc169eb351299eec8a39
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793651"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="b1e8f-103">Microsoft コンプライアンススコア (プレビュー) の設定</span><span class="sxs-lookup"><span data-stu-id="b1e8f-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b1e8f-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="b1e8f-104">Before you begin</span></span>

<span data-ttu-id="b1e8f-105">通常、コンプライアンススコアにアクセスする最初のユーザーは、組織の Microsoft 365 グローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="b1e8f-106">初めてコンプライアンススコアを参照する場合は、グローバル管理者サインインを推奨し、以下の説明に従ってユーザー権限を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="b1e8f-107">サインイン</span><span class="sxs-lookup"><span data-stu-id="b1e8f-107">Sign in</span></span>

1. <span data-ttu-id="b1e8f-108">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)に移動し、microsoft 365 のグローバル管理者アカウントで**サインイン**します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="b1e8f-109">左側のナビゲーションウィンドウで [**コンプライアンススコア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="b1e8f-110">その後、[コンプライアンススコアダッシュボードにスコアを](#understand-the-compliance-score-dashboard)表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="b1e8f-111">ユーザーのアクセス許可を設定して役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b1e8f-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="b1e8f-112">コンプライアンススコアは、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="b1e8f-113">コンプライアンススコアにアクセスできるのは、役割が割り当てられているユーザーだけで、各ユーザーが許可する操作は、役割の種類によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="b1e8f-114">アクセス許可を設定する場所</span><span class="sxs-lookup"><span data-stu-id="b1e8f-114">Where to set permissions</span></span>

<span data-ttu-id="b1e8f-115">組織のグローバル管理者は、Microsoft 365 コンプライアンスセンターまたは Azure Active Directory (Azure AD) でユーザーのアクセス許可を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b1e8f-116">これらのいずれかの場所で役割が設定されると、ユーザーはコンプライアンススコア (およびコンプライアンスマネージャー) にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="b1e8f-117">既存のコンプライアンスマネージャーの役割は、コンプライアンススコアに移行**されない**ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="b1e8f-118">これは、コンプライアンスマネージャーで以前に役割が割り当てられていた場合、その役割はコンプライアンススコアへのアクセスを許可しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="b1e8f-119">グローバル管理者は、コンプライアンススコアにアクセスできるように、Microsoft 365 コンプライアンスセンターまたは Azure AD でアクセス許可とロールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="b1e8f-120">役割の種類</span><span class="sxs-lookup"><span data-stu-id="b1e8f-120">Role types</span></span>

<span data-ttu-id="b1e8f-121">次の表は、各 Microsoft 365 コンプライアンスセンターの役割と、各役割によって許可される機能を、既存のコンプライアンスマネージャーの役割にマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="b1e8f-122">ユーザーは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-122">User can:</span></span> | <span data-ttu-id="b1e8f-123">Microsoft 365 コンプライアンスセンターの役割</span><span class="sxs-lookup"><span data-stu-id="b1e8f-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="b1e8f-124">コンプライアンスマネージャーの役割</span><span class="sxs-lookup"><span data-stu-id="b1e8f-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="b1e8f-125">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="b1e8f-125">**Read but not edit data**</span></span>| <span data-ttu-id="b1e8f-126">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="b1e8f-126">Azure AD global reader</span></span>  | <span data-ttu-id="b1e8f-127">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="b1e8f-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="b1e8f-128">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="b1e8f-128">**Read but not edit data**</span></span>| <span data-ttu-id="b1e8f-129">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-129">Security reader</span></span> | <span data-ttu-id="b1e8f-130">コンプライアンスマネージャーリーダー</span><span class="sxs-lookup"><span data-stu-id="b1e8f-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="b1e8f-131">**データを編集する**</span><span class="sxs-lookup"><span data-stu-id="b1e8f-131">**Edit data**</span></span>| <span data-ttu-id="b1e8f-132">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-132">Compliance administrator</span></span> | <span data-ttu-id="b1e8f-133">コンプライアンスマネージャー共同作成者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="b1e8f-134">**テスト結果を編集する**</span><span class="sxs-lookup"><span data-stu-id="b1e8f-134">**Edit test results**</span></span>| <span data-ttu-id="b1e8f-135">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-135">Compliance administrator</span></span> | <span data-ttu-id="b1e8f-136">コンプライアンスマネージャーの査定者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="b1e8f-137">**評価、およびテンプレートとテナントデータを管理する**</span><span class="sxs-lookup"><span data-stu-id="b1e8f-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="b1e8f-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-138">Compliance administrator</span></span><br><span data-ttu-id="b1e8f-139">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-139">Compliance data administrator</span></span><br><span data-ttu-id="b1e8f-140">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-140">Security administrator</span></span> | <span data-ttu-id="b1e8f-141">コンプライアンスマネージャー管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="b1e8f-142">**ユーザーを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="b1e8f-142">**Assign users**</span></span>| <span data-ttu-id="b1e8f-143">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-143">Global administrator</span></span> | <span data-ttu-id="b1e8f-144">ポータル管理者</span><span class="sxs-lookup"><span data-stu-id="b1e8f-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="b1e8f-145">コンプライアンススコアからコンプライアンスマネージャーに移行してタスクを完了すると (たとえば、評価を管理する場合)、ブラウザーで新しいタブが開き、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="b1e8f-146">上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="b1e8f-147">アカウントにサインインし、[コンプライアンスマネージャーにアクセスするには**サインイン**] を選択します。資格情報を再入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="b1e8f-148">Microsoft 365 コンプライアンスセンターでアクセス許可と役割を設定する方法</span><span class="sxs-lookup"><span data-stu-id="b1e8f-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="b1e8f-149">Microsoft 365 コンプライアンスセンターでアクセス許可を設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="b1e8f-150">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)に移動し、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="b1e8f-151">左側のナビゲーションウィンドウで [**アクセス許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="b1e8f-152">ここから、役割を表示し、アクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-152">From here, you can view roles and assign permissions.</span></span>

<span data-ttu-id="b1e8f-153">詳細については、「 [Microsoft 365 コンプライアンスセンターでの役割とアクセス許可](../security/office-365-security/microsoft-security-and-compliance.md#required-licenses-and-permissions)の読み取り」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-153">For details, read [roles and permissions in the Microsoft 365 compliance center](../security/office-365-security/microsoft-security-and-compliance.md#required-licenses-and-permissions).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="b1e8f-154">コンプライアンススコアダッシュボードを理解する</span><span class="sxs-lookup"><span data-stu-id="b1e8f-154">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="b1e8f-155">コンプライアンススコアダッシュボードは、現在のコンプライアンス状況を一目で確認できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-155">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="b1e8f-156">![コンプライアンススコア-ダッシュボード](media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="b1e8f-156">![Compliance Score - dashboard](media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="b1e8f-157">総合コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="b1e8f-157">Overall compliance score</span></span>

<span data-ttu-id="b1e8f-158">コンプライアンススコアは、上部に強調表示されており、キーデータ保護の標準および規制に対処する改善アクションを完了するために達成可能なポイントに基づいてパーセンテージを示しています。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-158">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span> 

<span data-ttu-id="b1e8f-159">初めてコンプライアンススコアを取得すると、最初のスコアは 365 Microsoft の組み込みのデータ保護基準 (一般的な業界の規制と標準を含む一連のコントロール) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-159">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="b1e8f-160">コンプライアンススコアは既存の Microsoft 365 ソリューションのシステムをスキャンするので、現在組織で有効になっているプライバシーとセキュリティの設定に基づいて、コンプライアンスに関する最初の評価を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-160">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="b1e8f-161">組織に関連する評価を追加すると、スコアがよりわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-161">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="b1e8f-162">[スコアの計算方法](compliance-score-methodology.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-162">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="b1e8f-163">重要な改善アクション</span><span class="sxs-lookup"><span data-stu-id="b1e8f-163">Key improvement actions</span></span>

<span data-ttu-id="b1e8f-164">このセクションでは、全体的なコンプライアンススコアに最大の効果を得るために、今すぐに実行できる主な改善アクションを示します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-164">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="b1e8f-165">高リスクの評価で完了または失敗したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-165">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="b1e8f-166">スコアに影響を与えるソリューション</span><span class="sxs-lookup"><span data-stu-id="b1e8f-166">Solutions that affect your score</span></span>

<span data-ttu-id="b1e8f-167">このセクションでは、スコアにプラスの影響を与える可能性のあるアクションを含むソリューション、および各ソリューションでの未解決の改善アクションの数を示します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-167">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="b1e8f-168">コンプライアンススコアの内訳</span><span class="sxs-lookup"><span data-stu-id="b1e8f-168">Compliance Score breakdown</span></span>

<span data-ttu-id="b1e8f-169">このセクションでは、次の2つの異なる方法でスコアの詳細な表示を示します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-169">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="b1e8f-170">[**カテゴリ**]: [情報を保護] や [デバイスの管理] など、データ保護カテゴリ内の全体的なスコアの割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-170">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="b1e8f-171">**評価**: GDPR または NIST 800-53 など、特定のコンプライアンスおよびデータ保護の標準、規制、法律の評価を管理する際の進捗状況の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-171">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="b1e8f-172">ダッシュボードビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="b1e8f-172">Filtering your dashboard view</span></span>

<span data-ttu-id="b1e8f-173">特定の規制や基準、ソリューション、アクションの種類、グループ、またはデータ保護カテゴリに関連するアイテムのみを表示するように、ダッシュボードビューをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-173">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, groups, or data protection categories.</span></span> <span data-ttu-id="b1e8f-174">この方法でビューをフィルター処理すると、フィルター条件に基づいて、使用可能なポイントの合計数が表示されたダッシュボードのスコアのフィルター処理も行われます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-174">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="b1e8f-175">フィルターを適用するには</span><span class="sxs-lookup"><span data-stu-id="b1e8f-175">To apply filters:</span></span>

1. <span data-ttu-id="b1e8f-176">ダッシュボードの右上にある [**フィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-176">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="b1e8f-177">[フライアウト**フィルター** ] ウィンドウからフィルター条件を選択し、[**適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-177">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="b1e8f-178">スコアはリアルタイムで調整され、フィルター条件に対応する向上したアクション、ソリューション、およびスコア内訳情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-178">You will see your score adjusted in real-time, and you will only see improvement actions, solutions, and score breakdown information that correspond to your filter criteria.</span></span> <span data-ttu-id="b1e8f-179">コンプライアンススコアからサインアウトすると、再度サインインしたときに、フィルター処理されたビューが残ります。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-179">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="b1e8f-180">フィルターを削除するには</span><span class="sxs-lookup"><span data-stu-id="b1e8f-180">To remove filters:</span></span>

- <span data-ttu-id="b1e8f-181">コンプライアンススコアの上にある [**適用されたフィルター** ] 見出しで、削除する個々のフィルターの横にある [ **X** ] を選択します。や</span><span class="sxs-lookup"><span data-stu-id="b1e8f-181">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="b1e8f-182">ダッシュボードの右上にある [**フィルター** ] を選択し、[**フィルターのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-182">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="b1e8f-183">次の手順</span><span class="sxs-lookup"><span data-stu-id="b1e8f-183">Next step</span></span>

<span data-ttu-id="b1e8f-184">「[コンプライアンススコアの処理](working-with-compliance-score.md)」にアクセスして、スコアを改善するためのアクションを実行する方法のワークフローを理解します。</span><span class="sxs-lookup"><span data-stu-id="b1e8f-184">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>