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
description: サインインする方法、アクセス許可を設定する方法、および Microsoft コンプライアンススコアのダッシュボードを理解する方法について説明します。これにより、リスク評価を簡素化および自動化できます。
ms.openlocfilehash: 8233fb3174d822e4f71115cab2a1a174c1749810
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078614"
---
# <a name="microsoft-compliance-score-preview-setup"></a><span data-ttu-id="8640b-103">Microsoft コンプライアンススコア (プレビュー) の設定</span><span class="sxs-lookup"><span data-stu-id="8640b-103">Microsoft Compliance Score (Preview) setup</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8640b-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="8640b-104">Before you begin</span></span>

<span data-ttu-id="8640b-105">通常、コンプライアンススコアにアクセスする最初のユーザーは、組織の Microsoft 365 グローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="8640b-105">The Microsoft 365 global administrator for your organization will likely be the first user to access Compliance Score.</span></span> <span data-ttu-id="8640b-106">初めてコンプライアンススコアを参照する場合は、グローバル管理者サインインを推奨し、以下の説明に従ってユーザー権限を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8640b-106">We recommend the global admin sign in and set user permissions as outlined below when visiting Compliance Score for the first time.</span></span>

## <a name="sign-in"></a><span data-ttu-id="8640b-107">サインイン</span><span class="sxs-lookup"><span data-stu-id="8640b-107">Sign in</span></span>

1. <span data-ttu-id="8640b-108">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)に移動し、microsoft 365 のグローバル管理者アカウントで**サインイン**します。</span><span class="sxs-lookup"><span data-stu-id="8640b-108">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/) and **sign in** with your Microsoft 365 global admin account.</span></span>
2. <span data-ttu-id="8640b-109">左側のナビゲーションウィンドウで [**コンプライアンススコア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-109">Select **Compliance Score** on the left navigation pane.</span></span> <span data-ttu-id="8640b-110">その後、[コンプライアンススコアダッシュボードにスコアを](#understand-the-compliance-score-dashboard)表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8640b-110">You should then see your [Compliance Score dashboard with your score](#understand-the-compliance-score-dashboard).</span></span>

## <a name="set-user-permissions-and-assign-roles"></a><span data-ttu-id="8640b-111">ユーザーのアクセス許可を設定して役割を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8640b-111">Set user permissions and assign roles</span></span>

<span data-ttu-id="8640b-112">コンプライアンススコアは、役割ベースのアクセス制御 (RBAC) アクセス許可モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="8640b-112">Compliance Score uses a role-based access control (RBAC) permission model.</span></span> <span data-ttu-id="8640b-113">コンプライアンススコアにアクセスできるのは、役割が割り当てられているユーザーだけで、各ユーザーが許可する操作は、役割の種類によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="8640b-113">Only users who are assigned a role may access Compliance Score, and the actions allowed by each user are restricted by role type.</span></span>

### <a name="where-to-set-permissions"></a><span data-ttu-id="8640b-114">アクセス許可を設定する場所</span><span class="sxs-lookup"><span data-stu-id="8640b-114">Where to set permissions</span></span>

<span data-ttu-id="8640b-115">組織のグローバル管理者は、Microsoft 365 コンプライアンスセンターまたは Azure Active Directory (Azure AD) でユーザーのアクセス許可を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8640b-115">The global admin for your organization can set user permissions in the Microsoft 365 compliance center or in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8640b-116">これらのいずれかの場所で役割が設定されると、ユーザーはコンプライアンススコア (およびコンプライアンスマネージャー) にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8640b-116">Once roles are set in either of these locations, users will be able to access Compliance Score (as well as  Compliance Manager).</span></span>

<span data-ttu-id="8640b-117">既存のコンプライアンスマネージャーの役割は、コンプライアンススコアに移行**されない**ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8640b-117">Note that existing Compliance Manger roles **do not** transfer over to Compliance Score.</span></span>  <span data-ttu-id="8640b-118">これは、コンプライアンスマネージャーで以前に役割が割り当てられていた場合、その役割はコンプライアンススコアへのアクセスを許可しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="8640b-118">This means that if you were previously assigned a role in Compliance Manager, that role will not grant you access to Compliance Score.</span></span> <span data-ttu-id="8640b-119">グローバル管理者は、コンプライアンススコアにアクセスできるように、Microsoft 365 コンプライアンスセンターまたは Azure AD でアクセス許可とロールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8640b-119">Your global admin will need to set permissions and a role for you in the Microsoft 365 compliance center or Azure AD so that you can access Compliance Score.</span></span>

### <a name="role-types"></a><span data-ttu-id="8640b-120">役割の種類</span><span class="sxs-lookup"><span data-stu-id="8640b-120">Role types</span></span>

<span data-ttu-id="8640b-121">次の表は、各 Microsoft 365 コンプライアンスセンターの役割と、各役割によって許可される機能を、既存のコンプライアンスマネージャーの役割にマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8640b-121">The table below shows how each Microsoft 365 compliance center role maps to existing Compliance Manger roles, and the functions allowed by each role.</span></span>


| <span data-ttu-id="8640b-122">ユーザーは次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8640b-122">User can:</span></span> | <span data-ttu-id="8640b-123">Microsoft 365 コンプライアンスセンターの役割</span><span class="sxs-lookup"><span data-stu-id="8640b-123">Microsoft 365 compliance center role</span></span> | <span data-ttu-id="8640b-124">コンプライアンスマネージャーの役割</span><span class="sxs-lookup"><span data-stu-id="8640b-124">Compliance Manager role</span></span> | 
| :------------- | :-------------: | :------------: |
| <span data-ttu-id="8640b-125">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="8640b-125">**Read but not edit data**</span></span>| <span data-ttu-id="8640b-126">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="8640b-126">Azure AD global reader</span></span>  | <span data-ttu-id="8640b-127">Azure AD グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="8640b-127">Azure AD global reader</span></span> | 
| <span data-ttu-id="8640b-128">**データを読み取りますが、編集することはできません**</span><span class="sxs-lookup"><span data-stu-id="8640b-128">**Read but not edit data**</span></span>| <span data-ttu-id="8640b-129">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="8640b-129">Security reader</span></span> | <span data-ttu-id="8640b-130">コンプライアンスマネージャーリーダー</span><span class="sxs-lookup"><span data-stu-id="8640b-130">Compliance Manager reader</span></span>  | 
| <span data-ttu-id="8640b-131">**データを編集する**</span><span class="sxs-lookup"><span data-stu-id="8640b-131">**Edit data**</span></span>| <span data-ttu-id="8640b-132">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-132">Compliance administrator</span></span> | <span data-ttu-id="8640b-133">コンプライアンスマネージャー共同作成者</span><span class="sxs-lookup"><span data-stu-id="8640b-133">Compliance Manager contributor</span></span> | 
| <span data-ttu-id="8640b-134">**テスト結果を編集する**</span><span class="sxs-lookup"><span data-stu-id="8640b-134">**Edit test results**</span></span>| <span data-ttu-id="8640b-135">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-135">Compliance administrator</span></span> | <span data-ttu-id="8640b-136">コンプライアンスマネージャーの査定者</span><span class="sxs-lookup"><span data-stu-id="8640b-136">Compliance Manager assessor</span></span> | 
| <span data-ttu-id="8640b-137">**評価、およびテンプレートとテナントデータを管理する**</span><span class="sxs-lookup"><span data-stu-id="8640b-137">**Manage assessments, and template and tenant data**</span></span>| <span data-ttu-id="8640b-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-138">Compliance administrator</span></span><br><span data-ttu-id="8640b-139">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-139">Compliance data administrator</span></span><br><span data-ttu-id="8640b-140">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-140">Security administrator</span></span> | <span data-ttu-id="8640b-141">コンプライアンスマネージャー管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-141">Compliance Manager administrator</span></span> | 
| <span data-ttu-id="8640b-142">**ユーザーを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="8640b-142">**Assign users**</span></span>| <span data-ttu-id="8640b-143">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-143">Global administrator</span></span> | <span data-ttu-id="8640b-144">ポータル管理者</span><span class="sxs-lookup"><span data-stu-id="8640b-144">Portal admin</span></span> | 

> [!NOTE]
> <span data-ttu-id="8640b-145">コンプライアンススコアからコンプライアンスマネージャーに移行してタスクを完了すると (たとえば、評価を管理する場合)、ブラウザーで新しいタブが開き、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8640b-145">When you go from Compliance Score to Compliance Manager to complete a task (for example, to manage assessments), your browser will open a new tab and a dialog box appears.</span></span> <span data-ttu-id="8640b-146">上部のセクションに、「既に Microsoft cloud services のお客様である」というヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="8640b-146">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="8640b-147">アカウントにサインインし、[コンプライアンスマネージャーにアクセスするには**サインイン**] を選択します。資格情報を再入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8640b-147">Sign in to your account,” select **Sign In** to access Compliance Manager; you will not need to re-enter your credentials.</span></span>

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="8640b-148">Microsoft 365 コンプライアンスセンターでアクセス許可と役割を設定する方法</span><span class="sxs-lookup"><span data-stu-id="8640b-148">How to set permissions and roles in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="8640b-149">Microsoft 365 コンプライアンスセンターでアクセス許可を設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8640b-149">To set permissions in the Microsoft 365 compliance center:</span></span>

1. <span data-ttu-id="8640b-150">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)に移動し、グローバル管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="8640b-150">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com) and sign in with your global admin account.</span></span>
2. <span data-ttu-id="8640b-151">左側のナビゲーションウィンドウで [**アクセス許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-151">Select **Permissions** on the left navigation pane.</span></span> <span data-ttu-id="8640b-152">ここから、役割を表示し、アクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8640b-152">From here, you can view roles and assign permissions.</span></span>

## <a name="configure-automatic-secure-score-updates"></a><span data-ttu-id="8640b-153">セキュリティで保護されたスコアの自動更新を構成する</span><span class="sxs-lookup"><span data-stu-id="8640b-153">Configure automatic Secure Score updates</span></span>

<span data-ttu-id="8640b-154">既定では、すべての新しいテナントには、[セキュリティで保護さ](../security/mtp/microsoft-secure-score.md)れたスコア自動更新が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8640b-154">By default, all new tenants have [Secure Score](../security/mtp/microsoft-secure-score.md) automatic updates turned on.</span></span> <span data-ttu-id="8640b-155">これは、セキュリティで保護されたスコアによって監視されるすべてのアクションが、コンプライアンススコアの同じアクションの状態を自動的に更新することを意味します。</span><span class="sxs-lookup"><span data-stu-id="8640b-155">This means that all actions that are monitored by Secure Score will automatically update the status for the same action in Compliance Score.</span></span>

<span data-ttu-id="8640b-156">全体管理者はこの設定を管理して、すべてのアクションの自動更新をオフにしたり、操作の更新を個別に設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="8640b-156">Your global administrator can manage this setting to turn off automatic updates for all actions, or set updates for actions individually.</span></span>

<span data-ttu-id="8640b-157">パブリックプレビューでは、Microsoft Service Trust Portal (コンプライアンスマネージャーが配置されている場合) にアクセスして、セキュリティで保護されたスコアの更新を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8640b-157">During public preview, you will need to go to the Microsoft Service Trust Portal (where Compliance Manger is located) to manage Secure Score updates.</span></span>

<span data-ttu-id="8640b-158">セキュリティで保護されたスコアの自動更新を管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8640b-158">To manage automatic Secure Score updates, follow these steps:</span></span>

1. <span data-ttu-id="8640b-159">グローバル管理者アカウントを使用して、[サービス信頼ポータル](https://servicetrust.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8640b-159">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="8640b-160">サービス信頼ポータルのトップメニューバーで、[**詳細**設定] の下の [**管理**] を選択し、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-160">On the Service Trust Portal top menu bar, under **More**, select **Admin** and then choose **Settings**.</span></span>

3. <span data-ttu-id="8640b-161">[ **Secure Score** ] タブで、対応するボタンを選択して、**すべてのアクション**に対してオンにするか、**すべてのアクションに対し**て無効にするか、または**アクションごとに設定します。**</span><span class="sxs-lookup"><span data-stu-id="8640b-161">In the **Secure Score** tab, select the corresponding button to either **turn on for all actions**, **turn off for all actions**, or **set per action.**</span></span>

<span data-ttu-id="8640b-162">[**アクションごとに設定**] を選択した場合は、個々のアクションについてセキュリティで保護されたスコア更新を有効にする追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8640b-162">If you choose **set per action,** take these additional steps to turn on Secure Score updates for individual actions:</span></span>

4. <span data-ttu-id="8640b-163">上部のメニューから [**コンプライアンスマネージャー** ] を選択します (注: [コンプライアンスマネージャー (クラシック)] を選択しないでください)。</span><span class="sxs-lookup"><span data-stu-id="8640b-163">Select **Compliance Manager** from the top menu (note: do not select "Compliance Manager (classic)").</span></span>

5. <span data-ttu-id="8640b-164">画面の右上隅にある [**テナント管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-164">Select **Tenant Management** in the upper-right corner of your screen.</span></span>

6. <span data-ttu-id="8640b-165">[**顧客の操作**] ウィンドウで、[**影響を受ける操作**] 列の下に、省略記号 (**...**) を含む目的のアクションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8640b-165">On the **Customer Actions** pane, find your intended action with an ellipsis (**...**) under the **Affected Actions** column.</span></span> <span data-ttu-id="8640b-166">省略記号をクリックして、[編集] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="8640b-166">Click on the ellipses and select **Edit.**</span></span>

7. <span data-ttu-id="8640b-167">**セキュリティで保護されたスコアの継続更新**の切り替えトグルスイッチをオンに切り替え**ます。**</span><span class="sxs-lookup"><span data-stu-id="8640b-167">Switch the **Secure Score continuous update** toggle switch to **On.**</span></span>

8. <span data-ttu-id="8640b-168">[保存] を選択し**ます。**</span><span class="sxs-lookup"><span data-stu-id="8640b-168">Select **Save.**</span></span> <span data-ttu-id="8640b-169">セキュリティで保護されたスコア継続的監視は、そのアクションに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8640b-169">Secure Score continuous monitoring is now turned on for that action.</span></span>

<span data-ttu-id="8640b-170">**注:** すべてのアクションの自動更新をオンまたはオフにすることができるのは、全体管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="8640b-170">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="8640b-171">コンプライアンスマネージャー管理者は、個々のアクションに対して自動更新を有効にできますが、すべてのアクションに対してグローバルに行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="8640b-171">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

<span data-ttu-id="8640b-172">「[セキュリティで保護されたスコアの更新の管理](compliance-manager-release-notes.md#secure-score)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8640b-172">Read more about [managing Secure Score updates](compliance-manager-release-notes.md#secure-score).</span></span>

## <a name="understand-the-compliance-score-dashboard"></a><span data-ttu-id="8640b-173">コンプライアンススコアダッシュボードを理解する</span><span class="sxs-lookup"><span data-stu-id="8640b-173">Understand the Compliance Score dashboard</span></span>

<span data-ttu-id="8640b-174">コンプライアンススコアダッシュボードは、現在のコンプライアンス状況を一目で確認できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8640b-174">The Compliance Score dashboard is designed to provide you an at-a-glance view of your current compliance posture.</span></span>

<span data-ttu-id="8640b-175">![コンプライアンススコア-ダッシュボード](../media/compliance-score-dashboard.png "コンプライアンススコアダッシュボード")</span><span class="sxs-lookup"><span data-stu-id="8640b-175">![Compliance Score - dashboard](../media/compliance-score-dashboard.png "Compliance Score dashboard")</span></span>

### <a name="overall-compliance-score"></a><span data-ttu-id="8640b-176">総合コンプライアンススコア</span><span class="sxs-lookup"><span data-stu-id="8640b-176">Overall compliance score</span></span>

<span data-ttu-id="8640b-177">コンプライアンススコアは、上部に強調表示されており、キーデータ保護の標準および規制に対処する改善アクションを完了するために達成可能なポイントに基づいてパーセンテージを示しています。</span><span class="sxs-lookup"><span data-stu-id="8640b-177">Your compliance score, featured prominently at the top, shows a percentage based on points achievable for completing improvement actions addressing key data protection standards and regulations.</span></span>

<span data-ttu-id="8640b-178">初めてコンプライアンススコアを取得すると、最初のスコアは 365 Microsoft の組み込みのデータ保護基準 (一般的な業界の規制と標準を含む一連のコントロール) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="8640b-178">When you come to Compliance Score for the first time, your initial score is based on the built-in Microsoft 365 data protection baseline—a set of controls that includes common industry regulations and standards.</span></span> <span data-ttu-id="8640b-179">コンプライアンススコアは既存の Microsoft 365 ソリューションのシステムをスキャンするので、現在組織で有効になっているプライバシーとセキュリティの設定に基づいて、コンプライアンスに関する最初の評価を提供します。</span><span class="sxs-lookup"><span data-stu-id="8640b-179">Because Compliance Score scans your system of existing Microsoft 365 solutions, it gives an initial assessment of your compliance posture based on privacy and security settings currently enabled by your organization.</span></span>

<span data-ttu-id="8640b-180">組織に関連する評価を追加すると、スコアがよりわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8640b-180">As you add assessments that are relevant to your organization, your score becomes even more meaningful.</span></span> <span data-ttu-id="8640b-181">[スコアの計算方法](compliance-score-methodology.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="8640b-181">Learn more about [how your score is calculated](compliance-score-methodology.md).</span></span>

### <a name="key-improvement-actions"></a><span data-ttu-id="8640b-182">重要な改善アクション</span><span class="sxs-lookup"><span data-stu-id="8640b-182">Key improvement actions</span></span>

<span data-ttu-id="8640b-183">このセクションでは、全体的なコンプライアンススコアに最大の効果を得るために、今すぐに実行できる主な改善アクションを示します。</span><span class="sxs-lookup"><span data-stu-id="8640b-183">This section lists the top improvement actions you can take right now to make the largest positive impact on your overall compliance score.</span></span> <span data-ttu-id="8640b-184">高リスクの評価で完了または失敗したアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8640b-184">It lists actions that are not completed or failed with the assessment with high risks.</span></span>

### <a name="solutions-that-affect-your-score"></a><span data-ttu-id="8640b-185">スコアに影響を与えるソリューション</span><span class="sxs-lookup"><span data-stu-id="8640b-185">Solutions that affect your score</span></span>

<span data-ttu-id="8640b-186">このセクションでは、スコアにプラスの影響を与える可能性のあるアクションを含むソリューション、および各ソリューションでの未解決の改善アクションの数を示します。</span><span class="sxs-lookup"><span data-stu-id="8640b-186">This section shows which solutions contain actions with the greatest opportunity to positively impact your score, and how many outstanding improvement actions you have in each solution.</span></span>

### <a name="compliance-score-breakdown"></a><span data-ttu-id="8640b-187">コンプライアンススコアの内訳</span><span class="sxs-lookup"><span data-stu-id="8640b-187">Compliance Score breakdown</span></span>

<span data-ttu-id="8640b-188">このセクションでは、次の2つの異なる方法でスコアの詳細な表示を示します。</span><span class="sxs-lookup"><span data-stu-id="8640b-188">This section gives you a more detailed view of your score in two different ways:</span></span>

- <span data-ttu-id="8640b-189">[**カテゴリ**]: [情報を保護] や [デバイスの管理] など、データ保護カテゴリ内の全体的なスコアの割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8640b-189">**Categories**: shows the percentage of your overall score within data protection categories, such as “protect information” or “manage devices.”</span></span>
- <span data-ttu-id="8640b-190">**評価**: GDPR または NIST 800-53 など、特定のコンプライアンスおよびデータ保護の標準、規制、法律の評価を管理する際の進捗状況の割合を示します。</span><span class="sxs-lookup"><span data-stu-id="8640b-190">**Assessments**: shows the percentage of your progress in managing assessments for particular compliance and data protection standards, regulations, or laws, such as GDPR or NIST 800-53.</span></span>

### <a name="filtering-your-dashboard-view"></a><span data-ttu-id="8640b-191">ダッシュボードビューのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="8640b-191">Filtering your dashboard view</span></span>

<span data-ttu-id="8640b-192">ダッシュボードビューをフィルター処理して、特定の規制や基準、ソリューション、アクションの種類、[設定した評価のグループ](working-with-compliance-manager.md#groups)、またはデータ保護カテゴリに関連するアイテムのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="8640b-192">You can filter your dashboard view to see only the items related to particular regulations and standards, solutions, type of action, [groups of assessments you set up](working-with-compliance-manager.md#groups), or data protection categories.</span></span> <span data-ttu-id="8640b-193">この方法でビューをフィルター処理すると、フィルター条件に基づいて、使用可能なポイントの合計数が表示されたダッシュボードのスコアのフィルター処理も行われます。</span><span class="sxs-lookup"><span data-stu-id="8640b-193">Filtering your view in this way will also filter the score on your dashboard, showing how many points you’ve achieved out of total possible points based on your filter criteria.</span></span>

<span data-ttu-id="8640b-194">フィルターを適用するには</span><span class="sxs-lookup"><span data-stu-id="8640b-194">To apply filters:</span></span>

1. <span data-ttu-id="8640b-195">ダッシュボードの右上にある [**フィルター** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-195">Select **Filter** on the upper-right side of the dashboard.</span></span>
2. <span data-ttu-id="8640b-196">[フライアウト**フィルター** ] ウィンドウからフィルター条件を選択し、[**適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-196">Select your filter criteria from the flyout **Filters** pane, then select **Apply**.</span></span>

<span data-ttu-id="8640b-197">フィルターを適用すると、リアルタイムで調整したスコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8640b-197">Once a filter is applied, you will see your score adjusted in real-time.</span></span> <span data-ttu-id="8640b-198">コンプライアンススコアの割合と内訳の情報、および改善のアクションとソリューションは、現在、フィルター条件でカバーされるデータにのみ関連しています。</span><span class="sxs-lookup"><span data-stu-id="8640b-198">The compliance score percentage and breakdown information, and the improvement actions and solutions, now only pertain to data covered by your filter criteria.</span></span> <span data-ttu-id="8640b-199">コンプライアンススコアからサインアウトすると、再度サインインしたときに、フィルター処理されたビューが残ります。</span><span class="sxs-lookup"><span data-stu-id="8640b-199">If you sign out of Compliance Score, your filtered view remains when you sign back in.</span></span>

<span data-ttu-id="8640b-200">フィルターを削除するには</span><span class="sxs-lookup"><span data-stu-id="8640b-200">To remove filters:</span></span>

- <span data-ttu-id="8640b-201">コンプライアンススコアの上にある [**適用されたフィルター** ] 見出しで、削除する個々のフィルターの横にある [ **X** ] を選択します。や</span><span class="sxs-lookup"><span data-stu-id="8640b-201">At the **Applied filters** heading above your compliance score, select the **X** next to the individual filter you want to remove; or</span></span>
- <span data-ttu-id="8640b-202">ダッシュボードの右上にある [**フィルター** ] を選択し、[**フィルターのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8640b-202">Select **Filter** on the upper-right side of your dashboard, then select **Clear filters**.</span></span>

## <a name="next-step"></a><span data-ttu-id="8640b-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="8640b-203">Next step</span></span>

<span data-ttu-id="8640b-204">「[コンプライアンススコアの処理](working-with-compliance-score.md)」にアクセスして、スコアを改善するためのアクションを実行する方法のワークフローを理解します。</span><span class="sxs-lookup"><span data-stu-id="8640b-204">Visit [Working with Compliance Score](working-with-compliance-score.md) to understand the workflow of how to take actions to improve your score.</span></span>
