---
title: Microsoft コンプライアンスマネージャー (プレビュー) を使用する
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
description: Microsoft コンプライアンスマネージャーは、Microsoft Service Trust Portal の無料のワークフローベースのリスク評価ツールです。 コンプライアンスマネージャーを使用すると、Microsoft クラウドサービスに関連する規制コンプライアンスアクティビティを追跡、割り当て、検証することができます。
ms.openlocfilehash: e8e1ae997bf48f38e66319aec6ee07d0a84768c8
ms.sourcegitcommit: 93cef4906c5495ae293450ceb52d6cc336f52b53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "38686780"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="04477-104">Microsoft コンプライアンスマネージャー (プレビュー) を使用する</span><span class="sxs-lookup"><span data-stu-id="04477-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04477-105">Microsoft コンプライアンスマネージャーは、データ保護とコンプライアンスの stature と、データ保護とコンプライアンスを向上させるための推奨事項の概要を提供するダッシュボードおよび管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="04477-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="04477-106">コンプライアンスマネージャーで提供されるお客様のアクションは推奨事項です。実装の前に、それぞれの規制環境でこれらの推奨事項の有効性を評価することは、組織によって行われます。</span><span class="sxs-lookup"><span data-stu-id="04477-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="04477-107">コンプライアンスマネージャーの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="04477-108">Access コンプライアンスマネージャー</span><span class="sxs-lookup"><span data-stu-id="04477-108">Access Compliance Manager</span></span>

<span data-ttu-id="04477-p103">コンプライアンス マネージャーには Service Trust Portal からアクセスします。Microsoft アカウントまたは Azure Active Directory の組織アカウントを持つすべてのユーザーがコンプライアンス マネージャーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04477-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="04477-111">[https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/) に移動します。</span><span class="sxs-lookup"><span data-stu-id="04477-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="04477-112">Microsoft サービスアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="04477-112">Sign in with your Microsoft service account.</span></span> <span data-ttu-id="04477-113">これは、Office 365、Microsoft 365、または Azure Active Directory (Azure AD) のユーザーアカウントです。</span><span class="sxs-lookup"><span data-stu-id="04477-113">This is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="04477-114">Service Trust Portal で、[**コンプライアンスマネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-114">In the Service Trust Portal, select **Compliance Manager**.</span></span> <span data-ttu-id="04477-115">これは、コンプライアンスマネージャーのプレビューバージョンです。</span><span class="sxs-lookup"><span data-stu-id="04477-115">This is the preview version of Compliance Manager.</span></span> <span data-ttu-id="04477-116">**コンプライアンスマネージャー (クラシック)** は、以前のバージョンのコンプライアンスマネージャーへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="04477-116">**Compliance Manager (Classic)** is the link to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="04477-117">機密保持契約が表示されたら、それを読んで、[**同意**] を選択して続行します。</span><span class="sxs-lookup"><span data-stu-id="04477-117">When the Non-Disclosure Agreement is displayed, read it, and select **Agree** to continue.</span></span> <span data-ttu-id="04477-118">同意する必要があります。その後、コンプライアンスマネージャーダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-118">You must agree once, and then the Compliance Manager dashboard is displayed.</span></span>

<span data-ttu-id="04477-119">開始するには、組織に対して既定で ISO/IEC 27001:2103 の評価の Office 365 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-119">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="04477-120">管理</span><span class="sxs-lookup"><span data-stu-id="04477-120">Administration</span></span>

<span data-ttu-id="04477-121">全体管理者のみが使用でき、全体管理者アカウントでログインしている場合にのみ表示される特定の管理機能があります。</span><span class="sxs-lookup"><span data-stu-id="04477-121">There are specific administrative functions that are only available to the global administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="04477-122">全体管理者はユーザーのアクセス許可を割り当てることができ、すべての操作に対して自動セキュリティスコア更新を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-122">The global administrator can assign user permissions, and can turn on automatic Secure Score updates for all actions.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="04477-123">コンプライアンス マネージャーのロールをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="04477-123">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="04477-124">管理者がコンプライアンスマネージャーの役割を他のユーザーに割り当てると、それらのユーザーはコンプライアンスマネージャーでデータを表示し、その役割によって決定されたアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="04477-124">Once the administrator assigns Compliance Manager roles to other users, those users can view data in Compliance Manager and perform actions determined by their role.</span></span> <span data-ttu-id="04477-125">管理者は、 [Azure Active Directory (AZURE AD) でユーザーにグローバルリーダーの役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)を割り当てることによって、コンプライアンスマネージャーへの読み取り専用アクセス権を付与することもできます。</span><span class="sxs-lookup"><span data-stu-id="04477-125">The administrator can also give read-only access to Compliance Manager by assigning the user the [Global Reader role in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).</span></span>

<span data-ttu-id="04477-126">各コンプライアンスマネージャーの役割には、多少異なるアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="04477-126">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="04477-127">各役割に割り当てられているアクセス許可を表示したり、どのユーザーがどの役割に所属しているかを確認したり、その役割に対してユーザーを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-127">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="04477-128">[**管理**] メニュー項目を選択し、表示する**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-128">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理メニュー: 設定が選択されている](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="04477-130">コンプライアンス マネージャーのロールにユーザーを追加したり、ロールからユーザーを削除したりするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="04477-130">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="04477-131">[https://servicetrust.microsoft.com](https://servicetrust.microsoft.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="04477-131">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="04477-132">Azure Active Directory 全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="04477-132">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="04477-133">Service Trust Portal のトップメニューバーで、[**管理者**] を選択し、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-133">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="04477-134">**[役割の選択**] ドロップダウンリストで、管理する役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-134">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="04477-135">各ロールに追加されたユーザーは、**[ロールの選択]** ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-135">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="04477-136">この役割にユーザーを追加するには、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-136">To add users to this role, select **Add**.</span></span> <span data-ttu-id="04477-137">[**ユーザーの追加**] ダイアログで、[ユーザー] フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-137">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="04477-138">利用可能なユーザーの一覧をスクロールするか、ユーザー名の入力を開始して、検索用語に基づいてリストをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-138">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="04477-139">そのアカウントを、その役割を使用してプロビジョニングされた**ユーザーの追加**リストに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-139">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="04477-140">複数のユーザーを同時に追加する場合は、リストにフィルターを適用するためのユーザー名の入力を開始してから、リストに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-140">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="04477-141">[**保存**] を選択して、選択した役割をこれらのユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="04477-141">Select **Save** to provision the selected role to these users.</span></span> 

    ![コンプライアンスマネージャー-ユーザーを追加する](media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="04477-143">この役割からユーザーを削除するには、ユーザーを選択して [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-143">To remove users from this role, select the users and select **Delete**.</span></span>

    ![コンプライアンスマネージャー-ユーザーを削除する](media/compliance-manager-delete-users.png)

### <a name="controlling-automatic-secure-score-updates"></a><span data-ttu-id="04477-145">セキュリティで保護された自動スコア更新の制御</span><span class="sxs-lookup"><span data-stu-id="04477-145">Controlling automatic Secure Score updates</span></span>

<span data-ttu-id="04477-146">セキュリティで保護されたスコア更新は、すべてのアクションに対して自動的に有効にすることも、すべてのアクションに対して無効にすることも、個々のアクションで設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="04477-146">Secure Score updates can be turned on automatically for all actions, can be turned off for all actions, or can be set by individual action.</span></span>

1. <span data-ttu-id="04477-147">グローバル管理者アカウントを使用して、[サービス信頼ポータル](https://servicetrust.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="04477-147">Sign in to the [Service Trust Portal](https://servicetrust.microsoft.com) with your global administrator account.</span></span>

2. <span data-ttu-id="04477-148">Service Trust Portal のトップメニューバーで、[**管理者**] を選択し、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-148">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="04477-149">[ **Secure Score** ] タブで、[設定] を選択した場合に該当するボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-149">In the **Secure Score** tab, select the appropriate button for you chosen setting.</span></span>

<span data-ttu-id="04477-150">**注:** すべてのアクションの自動更新をオンまたはオフにすることができるのは、全体管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="04477-150">**Note:** Only the global administrator can turn on or off automatic updates for all actions.</span></span> <span data-ttu-id="04477-151">コンプライアンスマネージャー管理者は、個々のアクションに対して自動更新を有効にできますが、すべてのアクションに対してグローバルに行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="04477-151">The Compliance Manager administrator can turn on automatic updates for individual actions, but not for all actions globally.</span></span>

## <a name="groups"></a><span data-ttu-id="04477-152">グループ</span><span class="sxs-lookup"><span data-stu-id="04477-152">Groups</span></span>

<span data-ttu-id="04477-153">グループを使用すると、評価を論理的に整理し、同じまたは関連する顧客管理のコントロールがある評価間で共通の情報とワークフロータスクを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-153">Groups allow you to logically organize Assessments and that share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="04477-154">カスタマーが管理するアクションを最小限に抑えるために、年、標準、サービス、チーム、部署、または組織内の省庁ごとに評価をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-154">You can group Assessments by year, standard, service, team, division, or agencies within your organization to help minimize customer-managed Actions:</span></span>
  
- <span data-ttu-id="04477-155">**FFIEC は評価2019**</span><span class="sxs-lookup"><span data-stu-id="04477-155">**FFIEC IS Assessments 2019**</span></span>
  - <span data-ttu-id="04477-156">Office 365 + FFIEC は</span><span class="sxs-lookup"><span data-stu-id="04477-156">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="04477-157">Intune + FFIEC は</span><span class="sxs-lookup"><span data-stu-id="04477-157">Intune + FFIEC IS</span></span>
- <span data-ttu-id="04477-158">**データ セキュリティとプライバシー Assessment**</span><span class="sxs-lookup"><span data-stu-id="04477-158">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="04477-159">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="04477-159">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="04477-160">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="04477-160">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="04477-161">新しい評価を作成する場合は、評価用に新しいグループを作成するか、既存のグループに評価を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-161">When you create a new Assessment, you must create a new group for the Assessment or assign the Assessment to an existing group.</span></span> <span data-ttu-id="04477-162">グループをスタンドアロンのエンティティとして作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="04477-162">Groups cannot be created as stand-alone entities.</span></span> <span data-ttu-id="04477-163">新しい評価を追加*する前に*、組織のグループ戦略を決定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04477-163">It's recommended that you determine a grouping strategy for your organization *before* adding new assessments.</span></span> <span data-ttu-id="04477-164">既定では、最初の評価では "Default Group" という名前のグループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04477-164">By default, a Group named "Default Group" is available for your initial Assessments.</span></span> <span data-ttu-id="04477-165">グループにはセキュリティプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="04477-165">Groups do not have any security properties.</span></span> <span data-ttu-id="04477-166">すべてのアクセス許可が評価に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="04477-166">All permissions are associated with Assessments.</span></span>

<span data-ttu-id="04477-167">グループを操作するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="04477-167">When you work with groups, remember:</span></span>
  
- <span data-ttu-id="04477-168">同じグループ内の異なる評価に含まれる関連評価コントロールが、完了時に自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="04477-168">Related assessment controls in different assessments within the same Group automatically update when completed.</span></span>
- <span data-ttu-id="04477-169">新しい評価を作成するときに、新しいグループは既存のグループから情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="04477-169">New groups can copy information from an existing group when you create a new Assessment.</span></span> <span data-ttu-id="04477-170">コピー元のグループの評価から、お客様が管理するコントロールの実装の詳細とテスト計画および管理応答のフィールドに追加された情報は、新規にある同じ (または関連する) 顧客管理のコントロールにコピーされます。評価.</span><span class="sxs-lookup"><span data-stu-id="04477-170">Any information added to the Implementation Details and Test Plan and Management Response fields of customer-managed controls from Assessments in the group that you're copying from are copied to the same (or related) customer-managed controls in the new Assessment.</span></span> <span data-ttu-id="04477-171">既存のグループに新しい評価を追加している場合は、そのグループの評価からの共通情報が新しい評価にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="04477-171">If you're adding a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="04477-172">グループ名 (*グループ id*とも呼ばれます) は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-172">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="04477-173">グループには、同じ証明書/規制の評価を含めることができますが、各グループには、特定のクラウドサービス/証明書ペアの評価を1つだけ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-173">Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair.</span></span> <span data-ttu-id="04477-174">たとえば、グループに Office 365 および NIST CSF の2つの評価を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="04477-174">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="04477-175">グループには、それぞれに対応する認定/規制が異なる場合にのみ、同じクラウドサービスに対して複数の評価を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-175">A group can contain multiple Assessments for the same cloud service only if the corresponding certification/regulation for each one is different.</span></span>
- <span data-ttu-id="04477-176">評価グループに評価が追加されると、グループを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="04477-176">Once an assessment has been added to an assessment group, the grouping cannot be changed.</span></span> <span data-ttu-id="04477-177">評価グループの名前を変更することができます。これにより、そのグループに関連付けられているすべての評価の評価グループの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="04477-177">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span> <span data-ttu-id="04477-178">評価と新しい評価グループを作成し、既存の評価から情報をコピーできます。これにより、その評価の複製が別の評価グループに効率よく作成されます。</span><span class="sxs-lookup"><span data-stu-id="04477-178">You can create an assessment and a new assessment group and copy information from an existing assessment, which effectively creates a duplicate of that assessment in a different assessment group.</span></span>
- <span data-ttu-id="04477-179">アーカイブ評価は、評価とグループの間の関係を中断します。</span><span class="sxs-lookup"><span data-stu-id="04477-179">Archiving an assessment breaks the relationship between that assessment and the group.</span></span> <span data-ttu-id="04477-180">他の関連する評価に対する更新プログラムは、アーカイブされた評価に反映されなくなります。</span><span class="sxs-lookup"><span data-stu-id="04477-180">Any further updates to other related assessments are no longer reflected in the archived assessment.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="04477-181">テナント管理</span><span class="sxs-lookup"><span data-stu-id="04477-181">Tenant Management</span></span>

<span data-ttu-id="04477-182">コンプライアンスマネージャー (プレビュー) には、**テナント管理**と呼ばれる新しいデータ要素を管理するための新しいインターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-182">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="04477-183">このインターフェイスを使用すると、テナント全体の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="04477-183">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="04477-184">**次元:** テンプレート、評価、およびアクションアイテムのメタデータを表示して、フィルターのカスタムピボットを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="04477-184">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="04477-185">**所有者:** 各アクションアイテムの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-185">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="04477-186">**お客様のアクション:** コンプライアンスマネージャー (プレビュー) に含まれるアクションアイテムの完全なリストを管理し、セキュリティで保護されたスコアと統合されたアクションに対するセキュリティで保護されたスコア監視を有効/無効にします。</span><span class="sxs-lookup"><span data-stu-id="04477-186">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="04477-187">[**テナント管理**] を選択して管理インターフェイスを開き、次の手順を使用して**ディメンション**、**所有者**、および**顧客の操作**を管理します。</span><span class="sxs-lookup"><span data-stu-id="04477-187">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="04477-188">Dimensions</span><span class="sxs-lookup"><span data-stu-id="04477-188">Dimensions</span></span>

<span data-ttu-id="04477-189">ディメンションは、テンプレート、評価、またはアクションアイテムに関する情報を提供するメタデータのセットです。</span><span class="sxs-lookup"><span data-stu-id="04477-189">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="04477-190">次元は、キーと値の概念を使用します。次元キーはプロパティを表し、ディメンション値はプロパティの有効な値を表します。</span><span class="sxs-lookup"><span data-stu-id="04477-190">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="04477-191">たとえば、コンプライアンスマネージャーには、3種類のアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="04477-191">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="04477-192">これらは、**ドキュメント**、**運用**、**技術**の**アクションの種類**と分析コード値のディメンションキーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="04477-192">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="04477-193">既存のディメンションを編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="04477-193">You can edit or delete existing Dimensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04477-194">新しいディメンションを追加して、既にインポートしたテンプレートに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-194">You can add new dimensions, and they can be assigned to Templates that you have already imported.</span></span> <span data-ttu-id="04477-195">作成した新しいテンプレートに新しいディメンションを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="04477-195">You can also add new dimensions to any new Templates you create.</span></span>

### <a name="owners"></a><span data-ttu-id="04477-196">所有者</span><span class="sxs-lookup"><span data-stu-id="04477-196">Owners</span></span>

<span data-ttu-id="04477-197">所有者は、各コントロールの責任者を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04477-197">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="04477-198">すべての組み込みコントロールは、Microsoft、顧客、またはその両方によって所有されます。</span><span class="sxs-lookup"><span data-stu-id="04477-198">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="04477-199">組織内でより詳細な責任を指定するために使用できる、所有者のカスタム値を作成できます。</span><span class="sxs-lookup"><span data-stu-id="04477-199">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="04477-200">たとえば、組織内の特定のグループ、チーム、またはビジネス単位を表す所有者を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-200">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="04477-201">所有者を追加する</span><span class="sxs-lookup"><span data-stu-id="04477-201">Add an Owner</span></span>

1. <span data-ttu-id="04477-202">[**テナント管理**] を開き、[**所有者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-202">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="04477-203">[ **+ 所有者の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-203">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="04477-204">所有者の名前と説明を入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-204">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="04477-205">説明は [所有者] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-205">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="04477-206">所有者を編集する</span><span class="sxs-lookup"><span data-stu-id="04477-206">Edit an Owner</span></span>

<span data-ttu-id="04477-207">所有者名を編集することはできませんが、[所有者] 列に表示される説明を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-207">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="04477-208">[**テナント管理**] を開き、[**所有者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-208">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="04477-209">編集する所有者を見つけ、その下にある省略記号 (...) を選択して、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-209">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="04477-210">必要に応じて説明を変更し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-210">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="04477-211">所有者を削除する</span><span class="sxs-lookup"><span data-stu-id="04477-211">Delete an Owner</span></span>

1. <span data-ttu-id="04477-212">[**テナント管理**] を開き、[**所有者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-212">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="04477-213">削除する所有者を見つけ、その下にある省略記号 (...) を選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-213">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="04477-214">確認メッセージが表示されたら、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-214">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="04477-215">顧客のアクション</span><span class="sxs-lookup"><span data-stu-id="04477-215">Customer Actions</span></span>

<span data-ttu-id="04477-216">[顧客の操作] 領域には、コンプライアンスマネージャー (プレビュー) のすべてのテンプレートと評価に関するすべてのお客様のアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-216">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

![コンプライアンスマネージャー-ユーザーを追加する](media/compliance-manager-customer-actions.png)

<span data-ttu-id="04477-218">概要には、アクションのタイトル、所有者、カテゴリ、強制、およびスコアが表示され、セキュリティで保護されたスコアと統合されているかどうかが確認できます。</span><span class="sxs-lookup"><span data-stu-id="04477-218">At-a-glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="04477-219">アクションを展開して、[**詳細の読み取り**] を選択すると、アクションの説明が読み込まれ、説明内のリンクにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04477-219">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="04477-220">このインターフェイスを使用して、アクションごとにセキュリティで保護されたスコアの統合を有効または無効にしたり、カスタムアクションを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="04477-220">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="04477-221">セキュリティで保護されたスコア統合機能を持つアクションの横には、省略記号 (...) が付いています (カスタムアクションにも、その横に省略記号 (...) があることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="04477-221">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="04477-222">セキュリティで保護されたスコアの統合を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="04477-222">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="04477-223">変更するアクションの省略記号 ([...]) を選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-223">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="04477-224">セキュリティで保護されたスコアを使用して継続的監視を有効または無効にするためのスイッチをオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="04477-224">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="04477-225">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-225">Select **Save**.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="04477-226">顧客のアクションを追加する</span><span class="sxs-lookup"><span data-stu-id="04477-226">Add a customer action</span></span>

1. <span data-ttu-id="04477-227">[ **+ 顧客の追加] アクション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-227">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="04477-228">[**タイトル**] フィールドにアクションの一意のタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-228">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="04477-229">[**最大コンプライアンススコア**] フィールドに、アクションのコンプライアンススコアを指定します (これは1-99 からの任意の数値になります)。</span><span class="sxs-lookup"><span data-stu-id="04477-229">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="04477-230">[**アクションの種類**] ドロップダウンを使用して、追加するアクションの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-230">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="04477-231">アクションの種類が存在しない場合は、アクションの種類のディメンションキーに値を追加することで追加できます。</span><span class="sxs-lookup"><span data-stu-id="04477-231">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="04477-232">[**ディメンション**] ドロップダウンを使用して、アクションのディメンションキーと値を指定または追加します。</span><span class="sxs-lookup"><span data-stu-id="04477-232">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="04477-233">**所有者**ドロップダウンを使用して、アクションの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-233">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="04477-234">アクション**+** の説明と説明のタイトルを追加するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04477-234">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="04477-235">[ **X** ] を選択して説明のブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="04477-235">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="04477-236">[**保存**] を選択して、顧客のアクションを保存します。</span><span class="sxs-lookup"><span data-stu-id="04477-236">Select **Save** to save the Customer Action.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="04477-237">顧客のアクションを削除する</span><span class="sxs-lookup"><span data-stu-id="04477-237">Delete a customer action</span></span>

1. <span data-ttu-id="04477-238">変更するアクションの省略記号 ([...]) を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-238">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="04477-239">確認メッセージが表示されたら、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-239">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="04477-240">講習</span><span class="sxs-lookup"><span data-stu-id="04477-240">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="04477-241">評価を追加する</span><span class="sxs-lookup"><span data-stu-id="04477-241">Add an Assessment</span></span>
  
1. <span data-ttu-id="04477-242">評価ダッシュボードで、[ **+ 評価の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-242">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="04477-243">ブレードが開いたら、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-243">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="04477-244">**タイトル (必須):** 評価のタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-244">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="04477-245">**テンプレートを選択してください (必須):** 標準またはカスタムテンプレートを選択する</span><span class="sxs-lookup"><span data-stu-id="04477-245">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="04477-246">**グループを選択するか、新しいグループを追加してください (必須):** 既存のグループを選択するか、新しいグループを追加して、一意のグループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-246">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="04477-247">**既存のグループのデータをコピーしますか?(オプション):** グループコピーを有効にするようにコントロールを切り替え、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="04477-247">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="04477-248">**グループを選択します (省略可能)。** グループコピーが有効になっている場合は、コピー元のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-248">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="04477-249">**実装の詳細 (オプション):** 実装の詳細を新しいグループにコピーする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-249">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="04477-250">**テスト計画 & 追加情報 (オプション):** テスト計画と追加情報の詳細を新しいグループにコピーする場合に選択します</span><span class="sxs-lookup"><span data-stu-id="04477-250">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="04477-251">**ドキュメント (オプション):** 選択すると、新しいグループにドキュメントがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="04477-251">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="04477-252">[**保存**] を選択して、評価を作成します。</span><span class="sxs-lookup"><span data-stu-id="04477-252">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="04477-253">新しい評価が評価ダッシュボードに表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-253">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="04477-254">評価のタイトル。</span><span class="sxs-lookup"><span data-stu-id="04477-254">The title of the Assessment.</span></span>
- <span data-ttu-id="04477-255">評価に適用される評価の大きさ (証明書、環境、および製品を含む)。</span><span class="sxs-lookup"><span data-stu-id="04477-255">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="04477-256">作成日時、および最終変更日時。</span><span class="sxs-lookup"><span data-stu-id="04477-256">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="04477-257">評価スコアがパーセンテージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-257">The Assessment Score shown as a percentage.</span></span> <span data-ttu-id="04477-258">このスコアには、Microsoft 管理コントロールからのスコアと、セキュリティで保護されたスコアが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="04477-258">This score automatically includes your scores from Microsoft-managed controls and from Secure Score.</span></span>
- <span data-ttu-id="04477-259">評価された Microsoft 管理および manged コントロールの数を示す進行状況インジケーター。</span><span class="sxs-lookup"><span data-stu-id="04477-259">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="04477-260">既存の Assessment から情報をコピーする</span><span class="sxs-lookup"><span data-stu-id="04477-260">Copying information from existing Assessments</span></span>

<span data-ttu-id="04477-261">評価を作成するときは、既存のグループから情報をコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="04477-261">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="04477-262">これにより、コピーした評価に入力された情報を新しい評価の同じコントロールに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-262">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="04477-263">たとえば、組織内のすべての FFIEC に関連する評価のグループがある場合は、次の情報を既存の評価からコピーできます。</span><span class="sxs-lookup"><span data-stu-id="04477-263">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="04477-264">実装の詳細</span><span class="sxs-lookup"><span data-stu-id="04477-264">Implementation Details</span></span>
- <span data-ttu-id="04477-265">テスト計画 & 追加情報</span><span class="sxs-lookup"><span data-stu-id="04477-265">Test Plan & Additional Information</span></span>
- <span data-ttu-id="04477-266">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="04477-266">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="04477-267">既存の評価から新しい評価に情報をコピーする</span><span class="sxs-lookup"><span data-stu-id="04477-267">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="04477-268">評価ダッシュボードで、[ **+ 評価の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-268">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="04477-269">[**評価の追加**] ウィンドウで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-269">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="04477-270">**タイトル (必須):** 評価のタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-270">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="04477-271">**テンプレートを選択してください (必須):** 標準またはカスタムテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-271">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="04477-272">**グループを選択するか、新しいグループを追加してください (必須):**[**新しいグループの追加**] を選択し、一意のグループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-272">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="04477-273">**既存のグループのデータをコピーしますか?(オプション):** グループコピーを有効にするためにコントロールをオンに切り替え、[グループ**の選択**]: グループコピーが有効になっている場合は、コピー元のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-273">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="04477-274">- **実装の詳細 (オプション):** 実装の詳細を新しいグループにコピーする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-274">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="04477-275">- **テスト計画 & 追加情報 (オプション):** テスト計画と追加情報の詳細を新しいグループにコピーする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-275">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="04477-276">- **ドキュメント (オプション):** 選択すると、新しいグループにドキュメントがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="04477-276">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="04477-277">[**保存**] を選択して、評価を作成します。</span><span class="sxs-lookup"><span data-stu-id="04477-277">Select **Save** to create the Assessment.</span></span>

### <a name="view-an-assessment"></a><span data-ttu-id="04477-278">評価を表示する</span><span class="sxs-lookup"><span data-stu-id="04477-278">View an Assessment</span></span>
  
1. <span data-ttu-id="04477-279">評価ダッシュボードで、評価名を選択して、アクションアイテムとコントロール情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-279">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="04477-280">Office 365 および ISO 27001 の評価の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="04477-280">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="04477-281">最初のビューは、コンプライアンスマネージャー (プレビュー) の新しいアクションアイテムビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="04477-281">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![コンプライアンスマネージャーのアクションアイテムビュー](media/compliance-manager-action-items.png)

<span data-ttu-id="04477-283">アクションはアルファベット順に一覧表示され、各アクションにスコアと所有者が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="04477-283">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="04477-284">各アクションの詳細については、「詳細情報の**読み取り**」リンクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="04477-284">Select  the **Read More** link to read the details of each Action.</span></span> 

![コンプライアンスマネージャーのアクションアイテムビュー](media/compliance-manager-actions-read-more.png)

<span data-ttu-id="04477-286">アクションを管理、割り当て、実装、およびテストするには、[**レビュー** ] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-286">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="04477-287">次に、アクションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="04477-287">Below is an example Action.</span></span>

![コンプライアンスマネージャーのアクションビュー](media/compliance-manager-action.png)

<span data-ttu-id="04477-289">コンプライアンスマネージャーの以前のバージョンでは、要件を実装するワークフローが制御レベルで実行されました。</span><span class="sxs-lookup"><span data-stu-id="04477-289">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="04477-290">コンプライアンス責任者は、コントロールを実装するユーザーにコントロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="04477-290">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="04477-291">これには、次の2つの欠点がありました。</span><span class="sxs-lookup"><span data-stu-id="04477-291">There were two drawbacks to this:</span></span>

- <span data-ttu-id="04477-292">多くの場合、コントロールに関連付けられた複数のアクションがあり、コントロールを割り当てられたユーザーは、コントロールを実装するために必要だったすべてのアクションを実行するための適切な担当者ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="04477-292">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="04477-293">個別のタスクを1つのアクションに結合することによって、コンプライアンスマネージャー (プレビュー) でテナント構成の変更を自動的に記録するために使用される信号とテレメトリのコレクションを実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="04477-293">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="04477-294">コンプライアンスマネージャー (プレビュー) では、ワークフロープロセスはコントロールレベルからアクションレベルに移動されました。</span><span class="sxs-lookup"><span data-stu-id="04477-294">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="04477-295">アクションを確認するときは、アクションワークフローを管理するために、次のフィールドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04477-295">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="04477-296">**ユーザーを割り当てる:** このアクションを割り当てるユーザーを選択または入力するには、このフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-296">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="04477-297">リストをスクロールするか、検索する名前を入力して、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-297">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="04477-298">**ドキュメントの管理:** 実装の証拠は、Office ドキュメント、画像ファイル、スクリーンショット、CSV または TXT の PowerShell 出力、および Pdf の形式でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="04477-298">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="04477-299">**実装の状態:** アクションの現在の実装状態を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04477-299">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="04477-300">使用可能な値は、実装、実装、代替実装、計画済み、スコープ内ではありません。</span><span class="sxs-lookup"><span data-stu-id="04477-300">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="04477-301">**実装日:** アクションが実行された日付。</span><span class="sxs-lookup"><span data-stu-id="04477-301">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="04477-302">**テスト結果:** 実装検証の結果を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="04477-302">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="04477-303">可能な値は、評価、合格、Failed-低リスク、失敗-中規模リスク、失敗-高リスク、範囲外。</span><span class="sxs-lookup"><span data-stu-id="04477-303">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="04477-304">**テストの日付:** 検証が発生した日付。</span><span class="sxs-lookup"><span data-stu-id="04477-304">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="04477-305">**実装に関する注意事項:** 組織の実装の詳細と、含める必要のあるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-305">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="04477-306">**テスト計画:** このアクションのテスト計画の詳細と、追加するメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-306">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="04477-307">**追加情報:** このアクションに関する追加情報を入力するか、組織内での実装方法、および必要なメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-307">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="04477-308">コンプライアンスマネージャー (プレビュー) には、以前のバージョンで見つけたコントロールベースのピボットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-308">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="04477-309">[ **Controls Info** dashboard] を選択して表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-309">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="04477-310">コントロールの情報は、評価およびテンプレートレベルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="04477-310">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="04477-311">評価用の Controls Info ダッシュボードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="04477-311">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![コンプライアンスマネージャーコントロールの情報ビュー](media/compliance-manager-controls-info.png)

<span data-ttu-id="04477-313">評価の場合、Controls Info dashboard には次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-313">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="04477-314">表示するグループを選択するための**グループ**ドロップダウン (複数のグループを使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="04477-314">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="04477-315">表示する評価を選択するための**評価**ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="04477-315">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="04477-316">選択した評価に関するメタデータ (次のものが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="04477-316">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="04477-317">評価されたコントロールの総数**を示す、評価さ**れたコントロールの進捗状況のインジケーター。</span><span class="sxs-lookup"><span data-stu-id="04477-317">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="04477-318">評価の現在の**コンプライアンススコア**。パーセンテージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-318">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="04477-319">評価に使用された**証明書**と**製品**に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="04477-319">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="04477-320">評価の現在の**状態**と最終**更新**日。</span><span class="sxs-lookup"><span data-stu-id="04477-320">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="04477-321">評価の対象となる**サービス**の一覧。</span><span class="sxs-lookup"><span data-stu-id="04477-321">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="04477-322">コントロールファミリごとにグループ化されたコントロールの詳細。お客様のアクションと Microsoft 実装の詳細情報へのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="04477-322">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="04477-323">**操作により**、一部またはすべてのコントロールの要件を満たすために実行できるユーザー操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-323">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="04477-324">多くのコントロールには複数のアクションが関連付けられており、コントロールに関連付けられたすべてのアクションがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-324">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="04477-325">ここでのアクションは、アクションダッシュボードに一覧表示されている UI と同じです。</span><span class="sxs-lookup"><span data-stu-id="04477-325">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="04477-326">**Microsoft アクション**では、選択した証明書コントロールに適用される microsoft の内部フレームワークからのコントロールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-326">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="04477-327">内部コントロールごとに、[**実装**済み] を選択して、次に示すように、Microsoft の実装とテストの詳細、およびテスト結果とテスト日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-327">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![コンプライアンスマネージャー Microsoft アクションビュー](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="04477-329">評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="04477-329">Export an Assessment</span></span>

<span data-ttu-id="04477-330">組織内のコンプライアンスステークホルダーまたは外部の監査者や規制機関の評価を Excel ファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-330">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="04477-331">レポートは、レポートが作成された日時の時点での評価のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="04477-331">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="04477-332">このレポートには、評価のためのすべての Microsoft およびお客様が管理するコントロールの詳細、制御実装状態、コントロールのテスト日、テスト結果、アップロードされた証拠ドキュメントへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-332">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="04477-333">アーカイブされた評価はアップロードされたドキュメントへのリンクを保持しないため、評価レポートをアーカイブする前に、評価レポートをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-333">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="04477-334">評価レポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="04477-334">Export an Assessment report</span></span>
  
1. <span data-ttu-id="04477-335">コンプライアンスマネージャーダッシュボードで、[**コントロールの情報**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-335">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="04477-336">エクスポートする評価のドロップダウンメニューで、**グループ**と**評価**を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-336">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="04477-337">[**エクスポート**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-337">Select the **Export** button.</span></span>

<span data-ttu-id="04477-338">評価レポートは、ブラウザーセッションで Excel ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="04477-338">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="04477-339">Excel ファイルのファイル名の既定値は、評価のタイトルです。</span><span class="sxs-lookup"><span data-stu-id="04477-339">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="hide-a-template-or-an-assessment"></a><span data-ttu-id="04477-340">テンプレートまたは評価を非表示にする</span><span class="sxs-lookup"><span data-stu-id="04477-340">Hide a Template or an Assessment</span></span>

<span data-ttu-id="04477-341">テンプレートまたは評価が終了し、法令遵守のために必要でなくなったら、ビューから非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-341">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can hide it from your view.</span></span> <span data-ttu-id="04477-342">テンプレートまたは評価が非表示の場合は、既定のビューから削除されるので、表示するには [**非表示**] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-342">When a Template or Assessment is hidden, it is removed from the default view, and you must select **Include Hidden** checkbox to display it.</span></span>

<span data-ttu-id="04477-343">![コンプライアンスマネージャーの非表示テンプレートビュー](media/compliance-manager-hidden-template.png "コンプライアンスマネージャーの非表示テンプレート")</span><span class="sxs-lookup"><span data-stu-id="04477-343">![Compliance Manager Hidden Template View](media/compliance-manager-hidden-template.png "Compliance Manager hidden template")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04477-344">非表示の評価では、アップロードした証拠ドキュメントへのリンクは保持されません。</span><span class="sxs-lookup"><span data-stu-id="04477-344">Hidden Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="04477-345">評価を非表示にする前に、レポートの証拠ドキュメントへのリンクを保持するように評価をエクスポートすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04477-345">It is highly recommended that you export the Assessment before hiding it to retain links to the evidence documents in the report.</span></span>
  
#### <a name="hiding-a-template"></a><span data-ttu-id="04477-346">テンプレートを非表示にする</span><span class="sxs-lookup"><span data-stu-id="04477-346">Hiding a Template</span></span>

1. <span data-ttu-id="04477-347">**テンプレート**ダッシュボードを開きます。</span><span class="sxs-lookup"><span data-stu-id="04477-347">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="04477-348">非表示にするテンプレートを見つけ、その行の省略記号で、[**非表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-348">Locate the Template you want to hide and at the ellipses in its row, select **Hide**.</span></span>
3. <span data-ttu-id="04477-349">確認メッセージが表示されたら、[**非表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-349">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="hide-an-assessment"></a><span data-ttu-id="04477-350">評価を非表示にする</span><span class="sxs-lookup"><span data-stu-id="04477-350">Hide an Assessment</span></span>

1. <span data-ttu-id="04477-351">**評価**ダッシュボードを開きます。</span><span class="sxs-lookup"><span data-stu-id="04477-351">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="04477-352">非表示にする評価を含む**グループ**をドロップダウンから選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-352">Select the **Group** from the dropdown that contains the Assessment you want to hide.</span></span>
3. <span data-ttu-id="04477-353">非表示にする評価を見つけ、省略記号で [**非表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-353">Locate the Assessment you want to hide and at the ellipses, select **Hide**.</span></span>
4. <span data-ttu-id="04477-354">確認メッセージが表示されたら、[**非表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-354">When you see the confirmation message, select **Hide**.</span></span>

#### <a name="view-hidden-assessments"></a><span data-ttu-id="04477-355">非表示の評価の表示</span><span class="sxs-lookup"><span data-stu-id="04477-355">View hidden Assessments</span></span>
  
1. <span data-ttu-id="04477-356">[**評価**ダッシュボード] タブを開き、[**非表示**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04477-356">Open the **Assessments** dashboard tab and select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="04477-357">非表示の評価は、[**非表示の評価**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-357">The hidden assessments appear in the **Hidden Assessments** section.</span></span>

#### <a name="unhide-an-assessment"></a><span data-ttu-id="04477-358">評価を非表示にする</span><span class="sxs-lookup"><span data-stu-id="04477-358">Unhide an Assessment</span></span>

1. <span data-ttu-id="04477-359">[**評価**] タブで、[**非表示を含める**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04477-359">On the **Assessments** tab, select the **Include Hidden** checkbox.</span></span>
2. <span data-ttu-id="04477-360">非表示の評価は、[**非表示の評価**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-360">The hidden assessments appear in the **Hidden Assessments** section.</span></span>
3. <span data-ttu-id="04477-361">再表示する評価を見つけ、省略記号の [再表示]**を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="04477-361">Locate the Assessment you want to unhide and at the ellipses, select **Unhide**.</span></span>
4. <span data-ttu-id="04477-362">確認メッセージが表示されたら、[再表示]**を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="04477-362">When you see the confirmation message, select **Unhide**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="04477-363">コントロールとアクション</span><span class="sxs-lookup"><span data-stu-id="04477-363">Controls and Actions</span></span>

<span data-ttu-id="04477-364">コントロールとアクションは、コンプライアンスマネージャー (プレビュー) で使用される主要なデータのピボットです。</span><span class="sxs-lookup"><span data-stu-id="04477-364">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="04477-365">以前のバージョンのコンプライアンスマネージャーに含まれていたコントロールピボットは、Microsoft とお客様のコントロールを同じコントロールファミリに表示するように強化されています。</span><span class="sxs-lookup"><span data-stu-id="04477-365">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="04477-366">この統合ビューを使用すると、管理者ごとに完全な共有責任モデルを簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="04477-366">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="04477-367">アクションピボットは、コンプライアンスマネージャー (プレビュー) で新しく追加されたものであり、Microsoft が推奨するすべての操作を合理化したビューを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="04477-367">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="04477-368">コントロール</span><span class="sxs-lookup"><span data-stu-id="04477-368">Controls</span></span>

<span data-ttu-id="04477-369">コントロールは、コントロールの情報ダッシュボードから表示できます。</span><span class="sxs-lookup"><span data-stu-id="04477-369">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="04477-370">コントロールは、標準、認定、規制、またはフレームワークからの要件を表します。</span><span class="sxs-lookup"><span data-stu-id="04477-370">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="04477-371">これらの要件を複数の標準、規制などにマッピングし、それらをアクションに関連付けるには、すべての要件をコントロールフレームワークとして扱います。</span><span class="sxs-lookup"><span data-stu-id="04477-371">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="04477-372">たとえば、次に示すように、法令規制 (HIPAA など) がセクションごとに分類されており、コンプライアンスマネージャーの HIPAA コントロールは、これらのセクションと同じ番号付けスキームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="04477-372">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![コンプライアンスマネージャー Microsoft コントロールの詳細](media/compliance-manager-control-details.png)

<span data-ttu-id="04477-374">次の3種類のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="04477-374">There are three types of controls:</span></span>

1. <span data-ttu-id="04477-375">**Microsoft 管理コントロール:** これらは microsoft のみが責任を持っているコントロールです。</span><span class="sxs-lookup"><span data-stu-id="04477-375">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="04477-376">これらは、インボックステンプレートに表示され、Microsoft によってコンプライアンスマネージャーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="04477-376">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="04477-377">**顧客管理コントロール:** 顧客のみが責任を持つコントロールです。</span><span class="sxs-lookup"><span data-stu-id="04477-377">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="04477-378">これらは、インボックステンプレートに表示され、顧客からコンプライアンスマネージャーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="04477-378">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="04477-379">**共有管理コントロール:** これらは、Microsoft とお客様との間で責任を共有するコントロールです。</span><span class="sxs-lookup"><span data-stu-id="04477-379">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="04477-380">これらは、インボックステンプレートに表示され、Microsoft によってコンプライアンスマネージャーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="04477-380">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="04477-381">お客様は、Microsoft 管理コントロールを編集または無効化することもできます。</span><span class="sxs-lookup"><span data-stu-id="04477-381">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="04477-382">アクションアイテム</span><span class="sxs-lookup"><span data-stu-id="04477-382">Actions Items</span></span>

<span data-ttu-id="04477-383">[アクション] アイテムは、標準または規制の要件を実装したり、組織の実装要件をテスト、検証、および文書化したりするために推奨されるタスクです。</span><span class="sxs-lookup"><span data-stu-id="04477-383">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="04477-384">アクションは1つまたは複数のコントロールに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="04477-384">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="04477-385">各コントロールには1つ以上のアクションが関連付けられており、各アクションは1つまたは複数のコントロールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-385">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="04477-386">アクションは、組織によって割り当てられ、追跡され、検証されるオブジェクトであるため、コンプライアンスマネージャー (プレビュー) のコアワークフローの一部です。</span><span class="sxs-lookup"><span data-stu-id="04477-386">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="04477-387">アクションアイテムを割り当てる</span><span class="sxs-lookup"><span data-stu-id="04477-387">Assign Action Items</span></span>
  
1. <span data-ttu-id="04477-388">[**アクションアイテム**] ダッシュボードで、アクションを割り当てる対象の評価を含む**グループ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-388">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="04477-389">[**評価**] ドロップダウンで、アクションを割り当てる対象の評価を選択するか、または [**すべて**] を選択して、使用可能なすべてのアクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-389">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="04477-390">割り当てるアクションを見つけ、[**所有者**] 列で、**レビュー**用のリンクを選択するか、**実装**するか**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="04477-390">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="04477-391">[**ユーザーの割り当て**] フィールドを選択し、組織内のユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-391">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="04477-392">リストをスクロールし、[ユーザー] または [リストにフィルターを適用] を選択して、ユーザーの名前を入力してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-392">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="04477-393">[実装メモ] フィールドに、割り当てられたユーザーに伝えたいメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-393">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="04477-394">[**保存**] を選択して、アクションを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="04477-394">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="04477-395">アクションアイテムの再割り当て</span><span class="sxs-lookup"><span data-stu-id="04477-395">Reassign Action Items</span></span>

<span data-ttu-id="04477-396">この関数を使用すると、新しいユーザーにアクションを再割り当てすることで、ユーザーアカウントのアクティブまたは保留中の依存関係を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-396">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="04477-397">[**アクションアイテム**] ダッシュボードで、アクションを再割り当てするアセスメントを含む**グループ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-397">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="04477-398">[**評価**] ドロップダウンで、アクションを再割り当てする評価を選択するか、または [**すべて**] を選択して、使用可能なすべてのアクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-398">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="04477-399">再割り当てするアクションを見つけ、[**所有者**] 列で、**レビュー**、**実装**、または**テスト**用のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-399">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="04477-400">[**ユーザーの割り当て**] フィールドから既存のユーザーを削除し、ユーザーの一覧から別のユーザーを選択するか、または一覧をフィルター処理して、ユーザーの名前を入力してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-400">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="04477-401">[実装メモ] フィールドに、ユーザーに伝えたいメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-401">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="04477-402">[**保存**] を選択して、アクションを再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="04477-402">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="04477-403">テンプレート</span><span class="sxs-lookup"><span data-stu-id="04477-403">Templates</span></span>

<span data-ttu-id="04477-404">テンプレートは、製品と証明書に関連付けられているコンプライアンスマネージャー (プレビュー) の基本オブジェクトです (たとえば、標準、規制、制御フレームワークなど)。</span><span class="sxs-lookup"><span data-stu-id="04477-404">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="04477-405">テンプレートは、テンプレートダッシュボードから表示および追加できます。</span><span class="sxs-lookup"><span data-stu-id="04477-405">Templates can be viewed and added from the Templates dashboard.</span></span>

![コンプライアンスマネージャー Microsoft テンプレートダッシュボード](media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="04477-407">ダッシュボードには各テンプレートが表示され、テンプレートに関連付けられている証明書と製品、テンプレートが作成された日付、最終変更された日付、顧客および Microsoft 管理コントロールの数、およびの最大コンプライアンススコアテンプレート、およびテンプレートの状態 (承認済み、保留中の承認、インポートされたものなど)。</span><span class="sxs-lookup"><span data-stu-id="04477-407">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="04477-408">組み込みテンプレートには、それぞれに関連付けられている組み込みの評価がありますが、組み込みのテンプレートに基づいて追加の評価を作成したり、独自のテンプレートをインポートしたり、それらを使用してカスタムの評価を作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-408">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="04477-409">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="04477-409">Create a Template</span></span>

<span data-ttu-id="04477-410">テンプレートを作成するには、既存のテンプレートをコピーするか、カスタムテンプレートをインポートします。</span><span class="sxs-lookup"><span data-stu-id="04477-410">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="04477-411">テンプレートデータに使用する必要がある特定の形式とスキーマがありますが、コンプライアンスマネージャーにはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="04477-411">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="04477-412">適切なスキーマとサンプルデータを含むファイルは、ここからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="04477-412">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="04477-413">各カスタムテンプレートは、次の5つのタブを含む個別の Excel ブック (.xls 形式または .xlsx 形式) に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-413">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="04477-414">テンプレート-評価</span><span class="sxs-lookup"><span data-stu-id="04477-414">Template-Assessment</span></span>
2. <span data-ttu-id="04477-415">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="04477-415">ControlFamily</span></span>
3. <span data-ttu-id="04477-416">Actions</span><span class="sxs-lookup"><span data-stu-id="04477-416">Actions</span></span>
4. <span data-ttu-id="04477-417">Ownership</span><span class="sxs-lookup"><span data-stu-id="04477-417">Ownership</span></span>
5. <span data-ttu-id="04477-418">Dimensions</span><span class="sxs-lookup"><span data-stu-id="04477-418">Dimensions</span></span>

<span data-ttu-id="04477-419">各タブ内で使用されるスキーマの詳細を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="04477-419">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="04477-420">[テンプレート-評価] タブ</span><span class="sxs-lookup"><span data-stu-id="04477-420">Template-Assessment tab</span></span>

<span data-ttu-id="04477-421">このタブには1つの列があります。</span><span class="sxs-lookup"><span data-stu-id="04477-421">This tab has a single column:</span></span>

- <span data-ttu-id="04477-422">**inScopeServices**: テンプレートの範囲内にある製品またはサービスのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="04477-422">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="04477-423">ControlFamily タブ</span><span class="sxs-lookup"><span data-stu-id="04477-423">ControlFamily tab</span></span>

<span data-ttu-id="04477-424">このタブには、[Actions] タブに表示されているアクションにマップされるコントロールを定義する列が含まれています。また、コントロール名、ファミリ、タイトル、説明などの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-424">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="04477-425">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-425">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="04477-426">**controlName:** 証明/標準/規制などからのコントロール名。</span><span class="sxs-lookup"><span data-stu-id="04477-426">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="04477-427">**Controlfamily:** 認定/標準、規制などからファミリーを制御します。</span><span class="sxs-lookup"><span data-stu-id="04477-427">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="04477-428">**Controltitle:** 資格/標準/規制などからタイトルを制御します。</span><span class="sxs-lookup"><span data-stu-id="04477-428">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="04477-429">**Controldescription:** 認定/標準/規制などから、説明を制御します。</span><span class="sxs-lookup"><span data-stu-id="04477-429">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="04477-430">**Controlversion:** オプションのコントロールバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="04477-430">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="04477-431">例: NIST 800-53 の場合、現在の値は Rev 4 なので、controlVersion は4です。</span><span class="sxs-lookup"><span data-stu-id="04477-431">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="04477-432">CSA CCM の場合、これは3.0.1 です。</span><span class="sxs-lookup"><span data-stu-id="04477-432">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="04477-433">**isDisabled:** コントロールが無効にされているかどうかを示すには、TRUE または FALSE を使用します。</span><span class="sxs-lookup"><span data-stu-id="04477-433">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="04477-434">**controlType:** CC を使用して、顧客が管理するコントロールであることを示します。</span><span class="sxs-lookup"><span data-stu-id="04477-434">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="04477-435">**controlComplianceScore:** コントロールに割り当てられているすべてのアクションのスコアの合計。</span><span class="sxs-lookup"><span data-stu-id="04477-435">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="04477-436">**Controlactiontitle:**[操作] タブに表示されている、このコントロールのすべての actionTitles の二重セミコロンで区切られたリストです。</span><span class="sxs-lookup"><span data-stu-id="04477-436">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="04477-437">[操作] タブ</span><span class="sxs-lookup"><span data-stu-id="04477-437">Actions tab</span></span>

<span data-ttu-id="04477-438">このタブには、個々のアクションを定義する列が含まれており、アクションタイトル、所有権、およびディメンションなどの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-438">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="04477-439">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-439">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="04477-440">**Actiontitle:** アクションのタイトル。</span><span class="sxs-lookup"><span data-stu-id="04477-440">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="04477-441">各タイトルは一意である必要があり、Pascal ケースを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04477-441">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="04477-442">**actionRelatedODVs:** Actiontitles 列に表示されている子の親である actionTitles の二重セミコロンで区切られたリストです。</span><span class="sxs-lookup"><span data-stu-id="04477-442">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="04477-443">親/子リレーションシップでは、親はハイウォーターマークを表します。</span><span class="sxs-lookup"><span data-stu-id="04477-443">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="04477-444">したがって、親アクションを完了した場合は、すべての子アクションも完了します。</span><span class="sxs-lookup"><span data-stu-id="04477-444">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="04477-445">たとえば、同じような要件があり、パスワードの長さなど、標準で定義された値が異なる場合は、少なくとも15文字が必要で、もう1つは少なくとも12または10が必要です。</span><span class="sxs-lookup"><span data-stu-id="04477-445">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="04477-446">この例では15が親になります。また、15文字以上を構成すると、他の評価で12文字または10文字が推奨されるアクションも満たされます。</span><span class="sxs-lookup"><span data-stu-id="04477-446">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04477-447">ActionRelatedODVs 列はスキーマの必須の列です。ただし、機能 (関連アクション) はコンプライアンスマネージャー (プレビュー) では使用できません。</span><span class="sxs-lookup"><span data-stu-id="04477-447">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="04477-448">今後のリリースで追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="04477-448">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="04477-449">**Actiondimensionvalues:** 次の形式を使用して、[ディメンション] タブの該当するディメンションの二重セミコロンで区切られたリストです。</span><span class="sxs-lookup"><span data-stu-id="04477-449">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="04477-450">例:</span><span class="sxs-lookup"><span data-stu-id="04477-450">For example:</span></span>

    ```
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="04477-451">カスタムテンプレートで使用されているすべてのディメンションは、ディメンションダッシュボードに既に表示されている場合でも、インポートファイルの [ディメンション] タブに一覧表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-451">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="04477-452">**Actionscore:** 各アクションの数値です。この値は、そのアクションのスコアを表します。</span><span class="sxs-lookup"><span data-stu-id="04477-452">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="04477-453">各アクションの目的と実施に基づいて、組み込み評価で使用されるスコアリングモデルをフォローすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04477-453">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="04477-454">**アクションの所有権:** セミコロンで区切られた、二重引用符で囲まれた所有者のリスト。</span><span class="sxs-lookup"><span data-stu-id="04477-454">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="04477-455">一覧表示されたすべての所有者が [所有権] タブに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-455">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="04477-456">**Actiondescription:** 各アクションのテキスト。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-456">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="04477-457">以下に示すように、このフィールドは Markdown Language をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="04477-457">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="04477-458">[所有権] タブ</span><span class="sxs-lookup"><span data-stu-id="04477-458">Ownership tab</span></span>

<span data-ttu-id="04477-459">このタブには、各アクションの所有者を定義する列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-459">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="04477-460">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-460">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="04477-461">**所有の出荷先の所有者:** 所有者/責任者の一意の名前。</span><span class="sxs-lookup"><span data-stu-id="04477-461">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="04477-462">**ownershipDescription:** 所有者/責任者の説明。</span><span class="sxs-lookup"><span data-stu-id="04477-462">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="04477-463">[ディメンション] タブ</span><span class="sxs-lookup"><span data-stu-id="04477-463">Dimensions tab</span></span>

<span data-ttu-id="04477-464">このタブには、アクションに関連付けることができるディメンションを定義する列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-464">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="04477-465">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-465">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="04477-466">**Dimensionkey:** 次元で使用されるキーの一覧です。</span><span class="sxs-lookup"><span data-stu-id="04477-466">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="04477-467">たとえば、製品、証明書など。</span><span class="sxs-lookup"><span data-stu-id="04477-467">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="04477-468">**Dimensionvalue:** 各次元キーの一意の値。</span><span class="sxs-lookup"><span data-stu-id="04477-468">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="04477-469">たとえば、Office 365、Intune、Azure、カスタム製品など。</span><span class="sxs-lookup"><span data-stu-id="04477-469">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="04477-470">**allowmultiselect**の場合:TRUE または FALSE を使用して、1つのディメンションキーに対して複数の次元の値を選択できることを示します。</span><span class="sxs-lookup"><span data-stu-id="04477-470">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="04477-471">説明フィールドで Markdown Language を使用する</span><span class="sxs-lookup"><span data-stu-id="04477-471">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="04477-472">テンプレートと評価では、一部のテキスト要素と書式設定に対して Markdown language の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="04477-472">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="04477-473">コンプライアンスマネージャーで使用される Markdown 言語の3つの書式設定要素があります。</span><span class="sxs-lookup"><span data-stu-id="04477-473">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="04477-474">箇条書きと段落番号</span><span class="sxs-lookup"><span data-stu-id="04477-474">Bullets and Numbered lists</span></span>
- <span data-ttu-id="04477-475">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="04477-475">Hyperlinks</span></span>
- <span data-ttu-id="04477-476">太字</span><span class="sxs-lookup"><span data-stu-id="04477-476">Boldface</span></span>

<span data-ttu-id="04477-477">行頭文字は、Word または Excel の行頭文字ではなく、アスタリスクで表されます。</span><span class="sxs-lookup"><span data-stu-id="04477-477">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="04477-478">例:</span><span class="sxs-lookup"><span data-stu-id="04477-478">For example:</span></span>

```
* Item A
* Item B
* Item C
```

<span data-ttu-id="04477-479">数字は数字として表されますが、インデントにスペースが含まれ (1 レベルに3スペース)、すべてのサブレベルで使用される数値のみ (たとえば、文字なし) になります。</span><span class="sxs-lookup"><span data-stu-id="04477-479">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="04477-480">例:</span><span class="sxs-lookup"><span data-stu-id="04477-480">For example:</span></span>
   1. <span data-ttu-id="04477-481">アイテム A</span><span class="sxs-lookup"><span data-stu-id="04477-481">Item A</span></span>
   2. <span data-ttu-id="04477-482">アイテム B</span><span class="sxs-lookup"><span data-stu-id="04477-482">Item B</span></span>
      1. <span data-ttu-id="04477-483">サブアイテム A</span><span class="sxs-lookup"><span data-stu-id="04477-483">Sub-item A</span></span>
      2. <span data-ttu-id="04477-484">サブアイテム B</span><span class="sxs-lookup"><span data-stu-id="04477-484">Sub-item B</span></span>
   3. <span data-ttu-id="04477-485">アイテム C</span><span class="sxs-lookup"><span data-stu-id="04477-485">Item C</span></span>
   4. <span data-ttu-id="04477-486">アイテム D</span><span class="sxs-lookup"><span data-stu-id="04477-486">Item D</span></span>
      1. <span data-ttu-id="04477-487">サブアイテム A</span><span class="sxs-lookup"><span data-stu-id="04477-487">Sub-item A</span></span>
      2. <span data-ttu-id="04477-488">サブアイテム B</span><span class="sxs-lookup"><span data-stu-id="04477-488">Sub-item B</span></span>
   5. <span data-ttu-id="04477-489">アイテム E</span><span class="sxs-lookup"><span data-stu-id="04477-489">Item E</span></span>

<span data-ttu-id="04477-490">ハイパーリンクを構成するには、ハイパーリンクテキストをかっこで囲み、角かっこの直後にハイパーリンク自体をかっこで囲んで記述します。</span><span class="sxs-lookup"><span data-stu-id="04477-490">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="04477-491">例:</span><span class="sxs-lookup"><span data-stu-id="04477-491">For example:</span></span>

```
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="04477-492">このテキストは、次のようにレンダリングされます。 Microsoft のホームページに移動するに[は、ここ](https://www.microsoft.com)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04477-492">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>
<span data-ttu-id="04477-493">上記の例のように、コンプライアンスマネージャーは、下線付きの Url を表示しません。</span><span class="sxs-lookup"><span data-stu-id="04477-493">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="04477-494">太字のテキストは、太字で表示されるテキストの各側に2つのアスタリスクがあるだけです。</span><span class="sxs-lookup"><span data-stu-id="04477-494">Boldface text is just two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="04477-495">例:</span><span class="sxs-lookup"><span data-stu-id="04477-495">For example:</span></span>

```
**This text will render in bold**
```
<span data-ttu-id="04477-496">**このテキストは太字で表示される**</span><span class="sxs-lookup"><span data-stu-id="04477-496">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="04477-497">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="04477-497">Create a Template</span></span>

<span data-ttu-id="04477-498">テンプレートを作成するには、既存のテンプレートをコピーするか、Excel からテンプレートデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="04477-498">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="04477-499">Excel からデータをインポートする場合、このテンプレートには、2つの異なるコンプライアンスマネージャー管理者がデータを発行する必要があります (1 つは発行し、もう1つは承認するため)。</span><span class="sxs-lookup"><span data-stu-id="04477-499">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="04477-500">既存のテンプレートをコピーしてテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="04477-500">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="04477-501">**テンプレート**ダッシュボードを開き、[ **+ テンプレートの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-501">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="04477-502">[**テンプレート名の入力**] フィールドに、テンプレートの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-502">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="04477-503">[**既存のテンプレートからコピー**する] チェックボックスをオンにして、ドロップダウンからコピーするテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-503">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="04477-504">必要に応じて、追加のディメンションを追加します。</span><span class="sxs-lookup"><span data-stu-id="04477-504">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="04477-505">[**ダッシュボードに追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-505">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="04477-506">データをインポートすることでテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="04477-506">Create a Template by importing data</span></span>

1. <span data-ttu-id="04477-507">**テンプレート**ダッシュボードを開き、[ **+ テンプレートの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-507">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="04477-508">[**テンプレート名の入力**] フィールドに、テンプレートの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-508">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="04477-509">利用可能なリストから少なくとも1つのディメンションを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-509">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="04477-510">[**参照**] を選択して、インポートファイルの場所に移動し、それを選択して、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-510">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="04477-511">インポートファイルが検証され、検出されたコントロールとコントロールファミリの数が示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-511">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="04477-512">エラーがある場合は、エラーの詳細を含む、変更されたバージョンのインポートファイルにリンクが提供されます。</span><span class="sxs-lookup"><span data-stu-id="04477-512">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="04477-513">データをインポートする前に、すべてのエラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-513">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="04477-514">データが検証に合格したら、[**ダッシュボードに追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-514">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="04477-515">インポートされたテンプレートは**テンプレート**ダッシュボードに表示され、状態は [**インポート**済み] になります。</span><span class="sxs-lookup"><span data-stu-id="04477-515">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="04477-516">省略記号 ([...]) を選択し、[**発行**] を選択してテンプレートを発行します。</span><span class="sxs-lookup"><span data-stu-id="04477-516">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="04477-517">確認メッセージが表示されたら、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-517">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="04477-518">テンプレートの状態が [**承認待ち**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="04477-518">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="04477-519">コンプライアンスマネージャー管理者の役割を持つ別のユーザーは、テンプレートダッシュボードでテンプレートを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-519">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="04477-520">省略記号 (...) を選択して、[**承認**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-520">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="04477-521">確認メッセージが表示されたら、[**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-521">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="04477-522">これで、テンプレートを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="04477-522">The Template is now ready for use.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04477-523">テンプレートを作成する場合は、[コンプライアンススコア] にテンプレートが表示されるように、**製品**と**証明書**の両方のディメンションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-523">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="04477-524">テンプレートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="04477-524">Customize a Template</span></span>

<span data-ttu-id="04477-525">テンプレートは、カスタムコントロールの追加によってカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="04477-525">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="04477-526">すべてのカスタムコントロールは、顧客が管理するコントロールと見なされます。</span><span class="sxs-lookup"><span data-stu-id="04477-526">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="04477-527">テンプレートにカスタムコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="04477-527">Add a custom control to a Template</span></span>

1. <span data-ttu-id="04477-528">変更する**テンプレート**を開きます。</span><span class="sxs-lookup"><span data-stu-id="04477-528">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="04477-529">[ **+** カスタムコントロールの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-529">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="04477-530">ドロップダウンから**コントロールファミリー**を選択するか、存在しない場合は新しいコントロールファミリーを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-530">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="04477-531">コントロール**id**フィールドに、コントロールの一意の名前または id を指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-531">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="04477-532">[**タイトル**] フィールドにコントロールのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-532">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="04477-533">[**説明**] フィールドに、コントロールの要件およびその他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-533">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="04477-534">[**顧客**にアクションを割り当てる] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-534">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="04477-535">コントロールに割り当てるアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="04477-535">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="04477-536">[**ディメンションでフィルター** ] を使用して、アクションに割り当てられたディメンションを使用して、それらを検索して表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-536">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="04477-537">**所有者によるフィルター**を使用して、アクションに割り当てられている所有者を検索して一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-537">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="04477-538">ドロップダウンから**アクションの種類**を選択して、種類別にアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="04477-538">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="04477-539">検索して一覧表示するアクションのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="04477-539">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="04477-540">手順8の条件を使用すると、**一致するアクション**の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-540">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="04477-541">コントロールに割り当てる最初のアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-541">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="04477-542">アクションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="04477-542">The details of the Action appear.</span></span> <span data-ttu-id="04477-543">使用する**説明**を選択し、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-543">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="04477-544">割り当てる追加のアクションごとに、手順9と10を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="04477-544">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="04477-545">該当するすべてのアクションを選択したら、[**割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-545">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="04477-546">[**保存**] を選択して、新しいコントロールを保存します。</span><span class="sxs-lookup"><span data-stu-id="04477-546">Select **Save** to save the new control.</span></span>

> [!NOTE]
> <span data-ttu-id="04477-547">テンプレートに加えた変更は、既存の評価には反映されません。</span><span class="sxs-lookup"><span data-stu-id="04477-547">Any changes made to a template will not be reflected in existing assessments.</span></span> <span data-ttu-id="04477-548">変更を確認するために、最初にテンプレートの更新を行ってから、新しい評価に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-548">Template updates must be made first, and then applied to a new assessment, in order for the changes to be seen.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="04477-549">JSON にテンプレートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="04477-549">Export a Template to JSON</span></span>

<span data-ttu-id="04477-550">また、コンプライアンスマネージャー (プレビュー) は、テンプレートを JavaScript Object Notation (JSON) 形式にエクスポートすることもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="04477-550">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="04477-551">これにより、コンプライアンスマネージャーのデータを JSON をサポートする他のシステムと交換することができます。</span><span class="sxs-lookup"><span data-stu-id="04477-551">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="04477-552">レポート</span><span class="sxs-lookup"><span data-stu-id="04477-552">Reports</span></span>

<span data-ttu-id="04477-553">組織内のコンプライアンスステークホルダーまたは外部の監査者や規制機関の評価を Excel ファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="04477-553">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="04477-554">レポートは、エクスポートの日時の時点での評価のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="04477-554">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="04477-555">このレポートには、評価のための Microsoft およびお客様が管理する統制の詳細、コントロールの実装状態、コントロールのテスト日、テスト結果、アップロードされた証拠ドキュメントへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="04477-555">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="04477-556">アーカイブされた評価はアップロードされたドキュメントへのリンクを保持しないので、アーカイブの前に評価をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04477-556">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="04477-557">評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="04477-557">Export an Assessment</span></span>

1. <span data-ttu-id="04477-558">コンプライアンスマネージャーダッシュボードで、[**コントロールの情報**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-558">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="04477-559">エクスポートする評価のドロップダウンメニューで、グループと評価を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-559">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="04477-560">[エクスポート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="04477-560">Select Export.</span></span> <span data-ttu-id="04477-561">評価エクスポートは、Excel ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="04477-561">The Assessment export is downloaded as an Excel file.</span></span>

![コンプライアンスマネージャー評価 Excel レポート](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="04477-563">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="04477-563">Permissions</span></span>

<span data-ttu-id="04477-564">次の表では、各コンプライアンスマネージャーのアクセス許可と、ユーザーが実行できる操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="04477-564">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="04477-565">この表は、各アクセス許可が割り当てられている役割も示しています。</span><span class="sxs-lookup"><span data-stu-id="04477-565">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="04477-566">**Azure AD グローバルリーダー**</span><span class="sxs-lookup"><span data-stu-id="04477-566">**Azure AD Global Reader**</span></span>|<span data-ttu-id="04477-567">**コンプライアンス マネージャー リーダー**</span><span class="sxs-lookup"><span data-stu-id="04477-567">**Compliance Manager Reader**</span></span>|<span data-ttu-id="04477-568">**コンプライアンス マネージャー投稿者**</span><span class="sxs-lookup"><span data-stu-id="04477-568">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="04477-569">**コンプライアンス マネージャー評価者**</span><span class="sxs-lookup"><span data-stu-id="04477-569">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="04477-570">**コンプライアンス マネージャー管理者**</span><span class="sxs-lookup"><span data-stu-id="04477-570">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="04477-571">**ポータル管理者**</span><span class="sxs-lookup"><span data-stu-id="04477-571">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04477-572">**データの読み取り:** ユーザーは、データの読み取りはできますが、編集はできません (テンプレートデータおよびテナント管理を除く)。</span><span class="sxs-lookup"><span data-stu-id="04477-572">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="04477-573">X</span><span class="sxs-lookup"><span data-stu-id="04477-573">X</span></span> | <span data-ttu-id="04477-574">X</span><span class="sxs-lookup"><span data-stu-id="04477-574">X</span></span> | <span data-ttu-id="04477-575">X</span><span class="sxs-lookup"><span data-stu-id="04477-575">X</span></span> | <span data-ttu-id="04477-576">X</span><span class="sxs-lookup"><span data-stu-id="04477-576">X</span></span> | <span data-ttu-id="04477-577">X</span><span class="sxs-lookup"><span data-stu-id="04477-577">X</span></span>  | <span data-ttu-id="04477-578">X</span><span class="sxs-lookup"><span data-stu-id="04477-578">X</span></span> |
|<span data-ttu-id="04477-579">**データの編集:** ユーザーは、テスト結果とテスト日付フィールド (テンプレートデータおよびテナント管理を除く) を除くすべてのフィールドを編集できます。</span><span class="sxs-lookup"><span data-stu-id="04477-579">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> ||| <span data-ttu-id="04477-580">X</span><span class="sxs-lookup"><span data-stu-id="04477-580">X</span></span> | <span data-ttu-id="04477-581">X</span><span class="sxs-lookup"><span data-stu-id="04477-581">X</span></span>  | <span data-ttu-id="04477-582">X</span><span class="sxs-lookup"><span data-stu-id="04477-582">X</span></span> | <span data-ttu-id="04477-583">X</span><span class="sxs-lookup"><span data-stu-id="04477-583">X</span></span> |
|<span data-ttu-id="04477-584">**テスト結果を編集します。** ユーザーは、テスト結果とテスト日付フィールドを編集できます。</span><span class="sxs-lookup"><span data-stu-id="04477-584">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> |||| <span data-ttu-id="04477-585">X</span><span class="sxs-lookup"><span data-stu-id="04477-585">X</span></span> | <span data-ttu-id="04477-586">X</span><span class="sxs-lookup"><span data-stu-id="04477-586">X</span></span> | <span data-ttu-id="04477-587">X</span><span class="sxs-lookup"><span data-stu-id="04477-587">X</span></span> |
|<span data-ttu-id="04477-588">**評価の管理:** ユーザーは評価を作成、アーカイブ、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="04477-588">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> ||||| <span data-ttu-id="04477-589">X</span><span class="sxs-lookup"><span data-stu-id="04477-589">X</span></span> | <span data-ttu-id="04477-590">X</span><span class="sxs-lookup"><span data-stu-id="04477-590">X</span></span> |
|<span data-ttu-id="04477-591">**マスタデータを管理します。** ユーザーは、テンプレートデータおよびテナント管理データを表示、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="04477-591">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> ||||| <span data-ttu-id="04477-592">X</span><span class="sxs-lookup"><span data-stu-id="04477-592">X</span></span> | <span data-ttu-id="04477-593">X</span><span class="sxs-lookup"><span data-stu-id="04477-593">X</span></span> |
|<span data-ttu-id="04477-594">**ユーザーを管理する:** ユーザーは、組織内の他のユーザーを閲覧者、投稿者、査定人、および管理者の役割に追加できます。</span><span class="sxs-lookup"><span data-stu-id="04477-594">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="04477-595">組織内のグローバル管理者の役割を持つユーザーのみが、ポータル管理者の役割に対してユーザーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="04477-595">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> |||||| <span data-ttu-id="04477-596">X</span><span class="sxs-lookup"><span data-stu-id="04477-596">X</span></span> |
