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
ms.openlocfilehash: 02cceb0487f357e6b40b634dc6d3cd7349ec2d96
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350318"
---
# <a name="work-with-microsoft-compliance-manager-preview"></a><span data-ttu-id="a3f69-104">Microsoft コンプライアンスマネージャー (プレビュー) を使用する</span><span class="sxs-lookup"><span data-stu-id="a3f69-104">Work with Microsoft Compliance Manager (Preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3f69-105">Microsoft コンプライアンスマネージャーは、データ保護とコンプライアンスの stature と、データ保護とコンプライアンスを向上させるための推奨事項の概要を提供するダッシュボードおよび管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-105">Microsoft Compliance Manager is a dashboard and management tool that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance.</span></span> <span data-ttu-id="a3f69-106">コンプライアンスマネージャーで提供されるお客様のアクションは推奨事項です。実装の前に、それぞれの規制環境でこれらの推奨事項の有効性を評価することは、組織によって行われます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-106">The customer actions provided in Compliance Manager are recommendations; it is up to your organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation.</span></span> <span data-ttu-id="a3f69-107">コンプライアンスマネージャーの推奨事項は、コンプライアンスの保証として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-107">Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.</span></span>

## <a name="access-compliance-manager"></a><span data-ttu-id="a3f69-108">Access コンプライアンスマネージャー</span><span class="sxs-lookup"><span data-stu-id="a3f69-108">Access Compliance Manager</span></span>

<span data-ttu-id="a3f69-p103">コンプライアンス マネージャーには Service Trust Portal からアクセスします。Microsoft アカウントまたは Azure Active Directory の組織アカウントを持つすべてのユーザーがコンプライアンス マネージャーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-p103">You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.</span></span>
  
1. <span data-ttu-id="a3f69-111">[https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-111">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).</span></span>

2. <span data-ttu-id="a3f69-112">Microsoft サービスアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-112">Sign in with your Microsoft service account.</span></span> <span data-ttu-id="a3f69-113">これは、Office 365、Microsoft 365、または Azure Active Directory (Azure AD) のユーザーアカウントです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-113">This is your Office 365, Microsoft 365, or Azure Active Directory (Azure AD) user account.</span></span>

3. <span data-ttu-id="a3f69-114">Service Trust Portal で、[**コンプライアンスマネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-114">In the Service Trust Portal, select **Compliance Manager**.</span></span> <span data-ttu-id="a3f69-115">これは、コンプライアンスマネージャーのプレビューバージョンです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-115">This is the preview version of Compliance Manager.</span></span> <span data-ttu-id="a3f69-116">**コンプライアンスマネージャー (クラシック)** は、以前のバージョンのコンプライアンスマネージャーへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-116">**Compliance Manager (Classic)** is the link to the previous version of Compliance Manager.</span></span>

4. <span data-ttu-id="a3f69-117">機密保持契約が表示されたら、それを読んで、[**同意**] を選択して続行します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-117">When the Non-Disclosure Agreement is displayed, read it, and select **Agree** to continue.</span></span> <span data-ttu-id="a3f69-118">同意する必要があります。その後、コンプライアンスマネージャーダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-118">You must agree once, and then the Compliance Manager dashboard is displayed.</span></span>

<span data-ttu-id="a3f69-119">開始するには、組織に対して既定で ISO/IEC 27001:2103 の評価の Office 365 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-119">To get you started, an ISO/IEC 27001:2103 Assessment for Office 365 appears by default for your organization.</span></span>

## <a name="administration"></a><span data-ttu-id="a3f69-120">管理</span><span class="sxs-lookup"><span data-stu-id="a3f69-120">Administration</span></span>

<span data-ttu-id="a3f69-121">テナント管理者のみが使用でき、全体管理者アカウントでログインしている場合にのみ表示される特定の管理機能があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-121">There are specific administrative functions that are only available to the tenant administrator and only visible when logged in with a global administrator account.</span></span> <span data-ttu-id="a3f69-122">ただし、管理者がコンプライアンスマネージャーの役割をユーザーに割り当てるまで、コンプライアンスマネージャーのデータが組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-122">However, until the administrator assigns Compliance Manager roles to users, data in Compliance Manager is visible to all users in your organization.</span></span> <span data-ttu-id="a3f69-123">コンプライアンスマネージャーでアクセスしてアクションを実行できるユーザーを決定するには、役割ベースのアクセス制御を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-123">We recommend implementing role-based access control to determine who can access and perform actions in Compliance Manager.</span></span>
  
### <a name="assigning-compliance-manager-roles-to-users"></a><span data-ttu-id="a3f69-124">コンプライアンス マネージャーのロールをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a3f69-124">Assigning Compliance Manager roles to users</span></span>

<span data-ttu-id="a3f69-125">各コンプライアンスマネージャーの役割には、多少異なるアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-125">Each Compliance Manager role has slightly different permissions.</span></span> <span data-ttu-id="a3f69-126">各役割に割り当てられているアクセス許可を表示したり、どのユーザーがどの役割に所属しているかを確認したり、その役割に対してユーザーを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-126">You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal.</span></span> <span data-ttu-id="a3f69-127">[**管理**] メニュー項目を選択し、表示する**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-127">Select the **Admin** menu item, and choose **Settings** to view.</span></span>
  
![STP 管理メニュー: 設定が選択されている](media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
<span data-ttu-id="a3f69-129">コンプライアンス マネージャーのロールにユーザーを追加したり、ロールからユーザーを削除したりするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a3f69-129">To add or remove users from Compliance Manager roles.</span></span>
  
1. <span data-ttu-id="a3f69-130">[https://servicetrust.microsoft.com](https://servicetrust.microsoft.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-130">Go to [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).</span></span>

2. <span data-ttu-id="a3f69-131">Azure Active Directory 全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-131">Sign in with your Azure Active Directory global administrator account.</span></span>

3. <span data-ttu-id="a3f69-132">Service Trust Portal のトップメニューバーで、[**管理者**] を選択し、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-132">On the Service Trust Portal top menu bar, select **Admin** and then choose **Settings**.</span></span>

4. <span data-ttu-id="a3f69-133">**[役割の選択**] ドロップダウンリストで、管理する役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-133">In the **Select Role** drop-down list, select the role that you want to manage.</span></span>

5. <span data-ttu-id="a3f69-134">各役割に追加されたユーザーは、 **[役割の選択**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-134">Users added to each role are listed on the **Select Role** page.</span></span>

6. <span data-ttu-id="a3f69-135">この役割にユーザーを追加するには、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-135">To add users to this role, select **Add**.</span></span> <span data-ttu-id="a3f69-136">[**ユーザーの追加**] ダイアログで、[ユーザー] フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-136">In the **Add Users** dialog, select the user field.</span></span> <span data-ttu-id="a3f69-137">利用可能なユーザーの一覧をスクロールするか、ユーザー名の入力を開始して、検索用語に基づいてリストをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-137">You can scroll through the list of available users or begin typing the user name to filter the list based on your search term.</span></span> <span data-ttu-id="a3f69-138">そのアカウントを、その役割を使用してプロビジョニングされた**ユーザーの追加**リストに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-138">Select the user to add that account to the **Add Users** list provisioned with that role.</span></span> <span data-ttu-id="a3f69-139">複数のユーザーを同時に追加する場合は、リストにフィルターを適用するためのユーザー名の入力を開始してから、リストに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-139">If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then select the user to add to the list.</span></span> <span data-ttu-id="a3f69-140">[**保存**] を選択して、選択した役割をこれらのユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-140">Select **Save** to provision the selected role to these users.</span></span> 

    ![コンプライアンスマネージャー-ユーザーを追加する](media/compliance-manager-add-users.png)
  
7. <span data-ttu-id="a3f69-142">この役割からユーザーを削除するには、ユーザーを選択して [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-142">To remove users from this role, select the users and select **Delete**.</span></span>

    ![コンプライアンスマネージャー-ユーザーを削除する](media/compliance-manager-delete-users.png)

## <a name="groups"></a><span data-ttu-id="a3f69-144">グループ</span><span class="sxs-lookup"><span data-stu-id="a3f69-144">Groups</span></span>

<span data-ttu-id="a3f69-145">グループを使用すると、評価を論理的に整理し、同じまたは関連する顧客管理のコントロールがある評価間で共通の情報とワークフロータスクを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-145">Groups allow you to logically organize Assessments and that share common information and workflow tasks between Assessments that have the same or related customer-managed controls.</span></span> <span data-ttu-id="a3f69-146">カスタマーが管理するアクションを最小限に抑えるために、年、標準、サービス、チーム、部署、または組織内の省庁ごとに評価をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-146">You can group Assessments by year, standard, service, team, division, or agencies within your organization to help minimize customer-managed Actions:</span></span>
  
- <span data-ttu-id="a3f69-147">**FFIEC は評価2019**</span><span class="sxs-lookup"><span data-stu-id="a3f69-147">**FFIEC IS Assessments 2019**</span></span>
  - <span data-ttu-id="a3f69-148">Office 365 + FFIEC は</span><span class="sxs-lookup"><span data-stu-id="a3f69-148">Office 365 + FFIEC IS</span></span>
  - <span data-ttu-id="a3f69-149">Intune + FFIEC は</span><span class="sxs-lookup"><span data-stu-id="a3f69-149">Intune + FFIEC IS</span></span>
- <span data-ttu-id="a3f69-150">**データ セキュリティとプライバシー Assessment**</span><span class="sxs-lookup"><span data-stu-id="a3f69-150">**Data Security and Privacy Assessments**</span></span>
  - <span data-ttu-id="a3f69-151">Office 365 + ISO 27001:2013</span><span class="sxs-lookup"><span data-stu-id="a3f69-151">Office 365 + ISO 27001:2013</span></span>
  - <span data-ttu-id="a3f69-152">Office 365 + ISO 27018:2014</span><span class="sxs-lookup"><span data-stu-id="a3f69-152">Office 365 + ISO 27018:2014</span></span>

<span data-ttu-id="a3f69-153">新しい評価を作成する場合は、評価用に新しいグループを作成するか、既存のグループに評価を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-153">When you create a new Assessment, you must create a new group for the Assessment or assign the Assessment to an existing group.</span></span> <span data-ttu-id="a3f69-154">グループをスタンドアロンのエンティティとして作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-154">Groups cannot be created as stand-alone entities.</span></span> <span data-ttu-id="a3f69-155">新しい評価を追加*する前に*、組織のグループ戦略を決定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-155">It's recommended that you determine a grouping strategy for your organization *before* adding new assessments.</span></span> <span data-ttu-id="a3f69-156">既定では、最初の評価では "Default Group" という名前のグループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-156">By default, a Group named "Default Group" is available for your initial Assessments.</span></span> <span data-ttu-id="a3f69-157">グループにはセキュリティプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-157">Groups do not have any security properties.</span></span> <span data-ttu-id="a3f69-158">すべてのアクセス許可が評価に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-158">All permissions are associated with Assessments.</span></span>

<span data-ttu-id="a3f69-159">グループを操作するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3f69-159">When you work with groups, remember:</span></span>
  
- <span data-ttu-id="a3f69-160">同じグループ内の異なる評価に含まれる関連評価コントロールが、完了時に自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-160">Related assessment controls in different assessments within the same Group automatically update when completed.</span></span>
- <span data-ttu-id="a3f69-161">新しい評価を作成するときに、新しいグループは既存のグループから情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-161">New groups can copy information from an existing group when you create a new Assessment.</span></span> <span data-ttu-id="a3f69-162">コピー元のグループの評価から、お客様が管理するコントロールの実装の詳細とテスト計画および管理応答のフィールドに追加された情報は、新規にある同じ (または関連する) 顧客管理のコントロールにコピーされます。評価.</span><span class="sxs-lookup"><span data-stu-id="a3f69-162">Any information added to the Implementation Details and Test Plan and Management Response fields of customer-managed controls from Assessments in the group that you're copying from are copied to the same (or related) customer-managed controls in the new Assessment.</span></span> <span data-ttu-id="a3f69-163">既存のグループに新しい評価を追加している場合は、そのグループの評価からの共通情報が新しい評価にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-163">If you're adding a new Assessment to an existing group, common information from Assessments in that group are copied to the new Assessment.</span></span>
- <span data-ttu-id="a3f69-164">グループ名 (*グループ id*とも呼ばれます) は、組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-164">Group names (also called *Group IDs*) must be unique within your organization.</span></span>
- <span data-ttu-id="a3f69-165">グループには、同じ証明書/規制の評価を含めることができますが、各グループには、特定のクラウドサービス/証明書ペアの評価を1つだけ含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-165">Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair.</span></span> <span data-ttu-id="a3f69-166">たとえば、グループに Office 365 および NIST CSF の2つの評価を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-166">For example, a group can't contain two Assessments for Office 365 and NIST CSF.</span></span> <span data-ttu-id="a3f69-167">グループには、それぞれに対応する認定/規制が異なる場合にのみ、同じクラウドサービスに対して複数の評価を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-167">A group can contain multiple Assessments for the same cloud service only if the corresponding certification/regulation for each one is different.</span></span>
- <span data-ttu-id="a3f69-168">評価グループに評価が追加されると、グループを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-168">Once an assessment has been added to an assessment group, the grouping cannot be changed.</span></span> <span data-ttu-id="a3f69-169">評価グループの名前を変更することができます。これにより、そのグループに関連付けられているすべての評価の評価グループの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-169">You can rename the assessment group, which changes the name of the assessment grouping for all the assessments associated with that group.</span></span> <span data-ttu-id="a3f69-170">評価と新しい評価グループを作成し、既存の評価から情報をコピーすることができます。これにより、別の評価グループにその評価の複製が効率的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-170">You can create an assessment and a new assessment group and copy information from an existing assessment, which effectively creates a duplicate of that assessment in a different assessment group.</span></span>
- <span data-ttu-id="a3f69-171">アーカイブ評価は、評価とグループの間の関係を中断します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-171">Archiving an assessment breaks the relationship between that assessment and the group.</span></span> <span data-ttu-id="a3f69-172">その他の関連する評価に関するその他の更新プログラムは、アーカイブ評価に反映されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a3f69-172">Any further updates to other related assessments are no longer reflected in the archived assessment.</span></span>

## <a name="tenant-management"></a><span data-ttu-id="a3f69-173">テナント管理</span><span class="sxs-lookup"><span data-stu-id="a3f69-173">Tenant Management</span></span>

<span data-ttu-id="a3f69-174">コンプライアンスマネージャー (プレビュー) には、**テナント管理**と呼ばれる新しいデータ要素を管理するための新しいインターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-174">Compliance Manager (Preview) includes a new interface for managing new data elements called **Tenant Management**.</span></span> <span data-ttu-id="a3f69-175">このインターフェイスを使用すると、テナント全体の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-175">This interface enables you to manage tenant-wide settings:</span></span>

- <span data-ttu-id="a3f69-176">**次元:** テンプレート、評価、およびアクションアイテムのメタデータを表示して、フィルターのカスタムピボットを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-176">**Dimensions:** View metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
- <span data-ttu-id="a3f69-177">**所有者:** 各アクションアイテムの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-177">**Owners:** Specify an owner for each Action Item.</span></span>
- <span data-ttu-id="a3f69-178">**お客様のアクション:** コンプライアンスマネージャー (プレビュー) に含まれるアクションアイテムの完全なリストを管理し、セキュリティで保護されたスコアと統合されたアクションに対するセキュリティで保護されたスコア監視を有効/無効にします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-178">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Actions that are integrated with Secure Score.</span></span>

<span data-ttu-id="a3f69-179">[**テナント管理**] を選択して管理インターフェイスを開き、次の手順を使用して**ディメンション**、**所有者**、および**顧客の操作**を管理します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-179">Select **Tenant Management** to open the management interface, and use the following steps to manage **Dimensions**, **Owners**, and **Customer Actions**.</span></span>

### <a name="dimensions"></a><span data-ttu-id="a3f69-180">Dimensions</span><span class="sxs-lookup"><span data-stu-id="a3f69-180">Dimensions</span></span>

<span data-ttu-id="a3f69-181">ディメンションは、テンプレート、評価、またはアクションアイテムに関する情報を提供するメタデータのセットです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-181">Dimensions are sets of metadata that provide information about a Template, an Assessment, or an Action Item.</span></span> <span data-ttu-id="a3f69-182">次元は、キーと値の概念を使用します。次元キーはプロパティを表し、ディメンション値はプロパティの有効な値を表します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-182">Dimensions use the concept of Keys and Values, where the Dimension Key represents a property, and Dimension Value represents valid values for the property.</span></span> <span data-ttu-id="a3f69-183">たとえば、コンプライアンスマネージャーには、3種類のアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-183">For example, in Compliance Manager there are three types of Actions.</span></span> <span data-ttu-id="a3f69-184">これらは、**ドキュメント**、**運用**、**技術**の**アクションの種類**と分析コード値のディメンションキーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-184">They are defined by a Dimension Key of **Action Type** and Dimension Values of **Documentation**, **Operational**, and **Technical**.</span></span> <span data-ttu-id="a3f69-185">既存のディメンションを編集または削除できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-185">You can edit or delete existing Dimensions.</span></span>

### <a name="owners"></a><span data-ttu-id="a3f69-186">Owners</span><span class="sxs-lookup"><span data-stu-id="a3f69-186">Owners</span></span>

<span data-ttu-id="a3f69-187">所有者は、各コントロールの責任者を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-187">Owners are used to identify the responsible party for each control.</span></span> <span data-ttu-id="a3f69-188">すべての組み込みコントロールは、Microsoft、顧客、またはその両方によって所有されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-188">All built-in controls are owned by Microsoft, by customers, or by both.</span></span> <span data-ttu-id="a3f69-189">組織内でより詳細な責任を指定するために使用できる、所有者のカスタム値を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-189">You can create custom values for Owners that can be used to specify more granular responsibilities within your organization.</span></span> <span data-ttu-id="a3f69-190">たとえば、組織内の特定のグループ、チーム、またはビジネス単位を表す所有者を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-190">For example, you could create Owners that represent specific groups, teams, or business units within your organization.</span></span>

#### <a name="add-an-owner"></a><span data-ttu-id="a3f69-191">所有者を追加する</span><span class="sxs-lookup"><span data-stu-id="a3f69-191">Add an Owner</span></span>

1. <span data-ttu-id="a3f69-192">[**テナント管理**] を開き、[**所有者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-192">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="a3f69-193">[ **+ 所有者の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-193">Select **+ Add owner**.</span></span>
3. <span data-ttu-id="a3f69-194">所有者の名前と説明を入力し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-194">Provide a Name and Description for the Owner and select **Save**.</span></span> <span data-ttu-id="a3f69-195">説明は [所有者] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-195">The description is displayed in the Owner column.</span></span>

#### <a name="edit-an-owner"></a><span data-ttu-id="a3f69-196">所有者を編集する</span><span class="sxs-lookup"><span data-stu-id="a3f69-196">Edit an Owner</span></span>

<span data-ttu-id="a3f69-197">所有者名を編集することはできませんが、[所有者] 列に表示される説明を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-197">You can’t edit an Owner name, but you can modify the description that is displayed in the Owner column.</span></span>

1. <span data-ttu-id="a3f69-198">[**テナント管理**] を開き、[**所有者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-198">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="a3f69-199">編集する所有者を見つけ、その下にある省略記号 (...) を選択して、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-199">Locate the Owner you want to edit, select the ellipses (…) next to it, and select **Edit**.</span></span>
3. <span data-ttu-id="a3f69-200">必要に応じて説明を変更し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-200">Modify the Description as needed and select **Save**.</span></span>

#### <a name="delete-an-owner"></a><span data-ttu-id="a3f69-201">所有者を削除する</span><span class="sxs-lookup"><span data-stu-id="a3f69-201">Delete an Owner</span></span>

1. <span data-ttu-id="a3f69-202">[**テナント管理**] を開き、[**所有者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-202">Open **Tenant Management** and select **Owners**.</span></span>
2. <span data-ttu-id="a3f69-203">削除する所有者を見つけ、その下にある省略記号 (...) を選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-203">Locate the Owner you want to delete, select the ellipses (…) next to it, and select **Delete**.</span></span>
3. <span data-ttu-id="a3f69-204">確認メッセージが表示されたら、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-204">When the confirmation message appears, select **Delete**.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="a3f69-205">顧客のアクション</span><span class="sxs-lookup"><span data-stu-id="a3f69-205">Customer Actions</span></span>

<span data-ttu-id="a3f69-206">[顧客の操作] 領域には、コンプライアンスマネージャー (プレビュー) のすべてのテンプレートと評価に関するすべてのお客様のアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-206">The Customer Actions area shows all the customer actions for all Templates and Assessments in Compliance Manager (Preview).</span></span>

![コンプライアンスマネージャー-ユーザーを追加する](media/compliance-manager-customer-actions.png)

<span data-ttu-id="a3f69-208">概要には、アクションのタイトル、所有者、カテゴリ、強制、およびスコアが表示され、セキュリティで保護されたスコアと統合されているかどうかが確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-208">At-a-glance, you can see an Action’s title, owner, category, enforcement, and score, and determine if it is integrated with Secure Score.</span></span> <span data-ttu-id="a3f69-209">アクションを展開して、[**詳細の読み取り**] を選択すると、アクションの説明が読み込まれ、説明内のリンクにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-209">You can expand an Action and select **Read More** to read the Action’s description and access any links in the description.</span></span> <span data-ttu-id="a3f69-210">このインターフェイスを使用して、アクションごとにセキュリティで保護されたスコアの統合を有効または無効にしたり、カスタムアクションを追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-210">You can also use this interface to enable and disable Secure Score integration on a per-action basis, and to add custom actions.</span></span> <span data-ttu-id="a3f69-211">セキュリティで保護されたスコア統合機能を持つアクションの横には、省略記号 (...) が付いています (カスタムアクションにも、その横に省略記号 (...) があることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-211">Actions that have Secure Score integration capabilities have an ellipsis (…) next to them (note that custom actions also have an ellipsis next to them).</span></span>

#### <a name="enable-or-disable-secure-score-integration"></a><span data-ttu-id="a3f69-212">セキュリティで保護されたスコアの統合を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a3f69-212">Enable or disable Secure Score integration</span></span>

1. <span data-ttu-id="a3f69-213">変更するアクションの省略記号 ([...]) を選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-213">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="a3f69-214">セキュリティで保護されたスコアを使用して継続的監視を有効または無効にするためのスイッチをオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-214">Toggle the switch for Secure Score continuous update to On or Off to enable or disable continuous monitoring through Secure Score.</span></span>
3. <span data-ttu-id="a3f69-215">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-215">Select **Save**.</span></span>

#### <a name="add-a-customer-action"></a><span data-ttu-id="a3f69-216">顧客のアクションを追加する</span><span class="sxs-lookup"><span data-stu-id="a3f69-216">Add a customer action</span></span>

1. <span data-ttu-id="a3f69-217">[ **+ 顧客の追加] アクション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-217">Select **+ Add Customer Action**.</span></span>
2. <span data-ttu-id="a3f69-218">[**タイトル**] フィールドにアクションの一意のタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-218">Provide a unique title for the Action in the **Title** field.</span></span>
3. <span data-ttu-id="a3f69-219">[**最大コンプライアンススコア**] フィールドに、アクションのコンプライアンススコアを指定します (これは1-99 からの任意の数値になります)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-219">Provide a Compliance Score for the Action in the **Maximum Compliance Score** field (this can be any number from 1-99).</span></span>
4. <span data-ttu-id="a3f69-220">[**アクションの種類**] ドロップダウンを使用して、追加するアクションの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-220">Use the **Action Type** dropdown to specify the type of Action you are adding.</span></span> <span data-ttu-id="a3f69-221">アクションの種類が存在しない場合は、アクションの種類のディメンションキーに値を追加することで追加できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-221">If the Action Type does not exist, you can add it by adding the value to the Action Type dimension key.</span></span>
5. <span data-ttu-id="a3f69-222">[**ディメンション**] ドロップダウンを使用して、アクションのディメンションキーと値を指定または追加します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-222">Use the **Dimensions** dropdown to specify or add dimension keys and values for the Action.</span></span>
6. <span data-ttu-id="a3f69-223">**所有者**ドロップダウンを使用して、アクションの所有者を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-223">Use the **Owner** dropdown to specify the owner for Action.</span></span>
7. <span data-ttu-id="a3f69-224">アクション**+** の説明と説明のタイトルを追加するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-224">Select **+** to add a description and description title for the Action.</span></span>
8. <span data-ttu-id="a3f69-225">[ **X** ] を選択して説明のブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-225">Select the **X** to close the Description blade.</span></span>
9. <span data-ttu-id="a3f69-226">[**保存**] を選択して、顧客のアクションを保存します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-226">Select **Save** to save the Customer Action.</span></span>

#### <a name="edit-a-customer-action"></a><span data-ttu-id="a3f69-227">顧客のアクションを編集する</span><span class="sxs-lookup"><span data-stu-id="a3f69-227">Edit a customer action</span></span>

1. <span data-ttu-id="a3f69-228">変更するアクションの省略記号 ([...]) を選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-228">Select the ellipses (…) for the Action you want to modify and select **Edit**.</span></span>
2. <span data-ttu-id="a3f69-229">必要に応じてアクションを編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-229">Edit the Action as desired, and select **Save**.</span></span>

#### <a name="delete-a-customer-action"></a><span data-ttu-id="a3f69-230">顧客のアクションを削除する</span><span class="sxs-lookup"><span data-stu-id="a3f69-230">Delete a customer action</span></span>

1. <span data-ttu-id="a3f69-231">変更するアクションの省略記号 ([...]) を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-231">Select the ellipses (…) for the Action you want to modify and select **Delete**.</span></span>
2. <span data-ttu-id="a3f69-232">確認メッセージが表示されたら、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-232">When the confirmation message appears, select **Delete**.</span></span>

## <a name="assessments"></a><span data-ttu-id="a3f69-233">講習</span><span class="sxs-lookup"><span data-stu-id="a3f69-233">Assessments</span></span>

### <a name="add-an-assessment"></a><span data-ttu-id="a3f69-234">評価を追加する</span><span class="sxs-lookup"><span data-stu-id="a3f69-234">Add an Assessment</span></span>
  
1. <span data-ttu-id="a3f69-235">評価ダッシュボードで、[ **+ 評価の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-235">In the Assessments dashboard, select **+ Add Assessment**.</span></span>

2. <span data-ttu-id="a3f69-236">ブレードが開いたら、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-236">When the blade opens, enter the following information:</span></span>

    - <span data-ttu-id="a3f69-237">**タイトル (必須):** 評価のタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-237">**Title (required):** Enter a title for your Assessment</span></span>
    - <span data-ttu-id="a3f69-238">**テンプレートを選択してください (必須):** 標準またはカスタムテンプレートを選択する</span><span class="sxs-lookup"><span data-stu-id="a3f69-238">**Please select a template (required):** Select a standard or custom template</span></span>
    - <span data-ttu-id="a3f69-239">**グループを選択するか、新しいグループを追加してください (必須):** 既存のグループを選択するか、新しいグループを追加して、一意のグループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-239">**Please select a group or add a new group (required):** Select an existing group or choose to add a new group, and provide a unique group name</span></span>
    - <span data-ttu-id="a3f69-240">**既存のグループのデータをコピーしますか?(オプション):** グループコピーを有効にするようにコントロールを切り替え、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-240">**Would you like to copy the data from an existing group? (optional):** Toggle the control to enable group copy and then:</span></span>
        - <span data-ttu-id="a3f69-241">**グループを選択します (省略可能)。** グループコピーが有効になっている場合は、コピー元のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-241">**Select a group (optional):** If group copy is enabled, select the group to copy from</span></span>
            - <span data-ttu-id="a3f69-242">**実装の詳細 (オプション):** 実装の詳細を新しいグループにコピーする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-242">**Implementation Details (optional):** Select to copy implementation details to the new group</span></span>
            - <span data-ttu-id="a3f69-243">**テスト計画 & 追加情報 (オプション):** テスト計画と追加情報の詳細を新しいグループにコピーする場合に選択します</span><span class="sxs-lookup"><span data-stu-id="a3f69-243">**Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group</span></span>
            - <span data-ttu-id="a3f69-244">**ドキュメント (オプション):** 選択すると、新しいグループにドキュメントがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-244">**Documents (optional):** Select to copy documents to the new group</span></span>

3. <span data-ttu-id="a3f69-245">[**保存**] を選択して、評価を作成します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-245">Select **Save** to create the Assessment.</span></span>

 <span data-ttu-id="a3f69-246">新しい評価が評価ダッシュボードに表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-246">The new Assessment appears on the Assessment dashboard and displays the following information:</span></span>

- <span data-ttu-id="a3f69-247">評価のタイトル。</span><span class="sxs-lookup"><span data-stu-id="a3f69-247">The title of the Assessment.</span></span>
- <span data-ttu-id="a3f69-248">評価に適用される評価の大きさ (証明書、環境、および製品を含む)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-248">The dimensions of the Assessment, including certification, environment, and product applied to the Assessment.</span></span>
- <span data-ttu-id="a3f69-249">作成日時、および最終変更日時。</span><span class="sxs-lookup"><span data-stu-id="a3f69-249">The date it was created and date when it was last modified.</span></span>
- <span data-ttu-id="a3f69-250">評価スコアがパーセンテージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-250">The Assessment Score shown as a percentage.</span></span>
- <span data-ttu-id="a3f69-251">評価された Microsoft 管理および manged コントロールの数を示す進行状況インジケーター。</span><span class="sxs-lookup"><span data-stu-id="a3f69-251">Progress indicators that show the number of assessed Microsoft-managed and customer-manged controls.</span></span>

### <a name="copying-information-from-existing-assessments"></a><span data-ttu-id="a3f69-252">既存の Assessment から情報をコピーする</span><span class="sxs-lookup"><span data-stu-id="a3f69-252">Copying information from existing Assessments</span></span>

<span data-ttu-id="a3f69-253">評価を作成するときは、既存のグループから情報をコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-253">When you create an Assessment, you have the option to copy information from an existing group.</span></span> <span data-ttu-id="a3f69-254">これにより、コピーした評価に入力された情報を新しい評価の同じコントロールに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-254">This allows you to apply the information entered into the copied assessment to the same controls in the new Assessment.</span></span> <span data-ttu-id="a3f69-255">たとえば、組織内のすべての FFIEC に関連する評価のグループがある場合は、次の情報を既存の評価からコピーできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-255">For example, if you have a group for all FFIEC-related Assessments in your organization, you can copy the following information from existing assessments:</span></span>

- <span data-ttu-id="a3f69-256">実装の詳細</span><span class="sxs-lookup"><span data-stu-id="a3f69-256">Implementation Details</span></span>
- <span data-ttu-id="a3f69-257">テスト計画 & 追加情報</span><span class="sxs-lookup"><span data-stu-id="a3f69-257">Test Plan & Additional Information</span></span>
- <span data-ttu-id="a3f69-258">Documents</span><span class="sxs-lookup"><span data-stu-id="a3f69-258">Documents</span></span>

#### <a name="copy-information-from-an-existing-assessment-to-a-new-assessment"></a><span data-ttu-id="a3f69-259">既存の評価から新しい評価に情報をコピーする</span><span class="sxs-lookup"><span data-stu-id="a3f69-259">Copy information from an existing Assessment to a new Assessment</span></span>
  
1. <span data-ttu-id="a3f69-260">評価ダッシュボードで、[ **+ 評価の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-260">In the Assessment dashboard, select **+ Add Assessment**.</span></span>
    
2. <span data-ttu-id="a3f69-261">[**評価の追加**] ウィンドウで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-261">In the **Add an Assessment** window, complete the following information</span></span>

    - <span data-ttu-id="a3f69-262">**タイトル (必須):** 評価のタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-262">**Title (required):** Enter a title for your Assessment.</span></span>
    - <span data-ttu-id="a3f69-263">**テンプレートを選択してください (必須):** 標準またはカスタムテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-263">**Please select a template (required):** Select a standard or custom template.</span></span>
    - <span data-ttu-id="a3f69-264">**グループを選択するか、新しいグループを追加してください (必須):**[**新しいグループの追加**] を選択し、一意のグループ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-264">**Please select a group or add a new group (required):** Choose **Add a new group** and provide a unique group name.</span></span>
    - <span data-ttu-id="a3f69-265">**既存のグループのデータをコピーしますか?(オプション):** グループコピーを有効にするためにコントロールをオンに切り替え、[グループ**の選択**]: グループコピーが有効になっている場合は、コピー元のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-265">**Would you like to copy the data from an existing group? (optional):** Toggle the control to On to enable group copy and then: - **Select a group (optional):** If group copy is enabled, select the group to copy from.</span></span>
            <span data-ttu-id="a3f69-266">- **実装の詳細 (オプション):** 実装の詳細を新しいグループにコピーする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-266">- **Implementation Details (optional):** Select to copy implementation details to the new group.</span></span>
            <span data-ttu-id="a3f69-267">- **テスト計画 & 追加情報 (オプション):** テスト計画と追加情報の詳細を新しいグループにコピーする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-267">- **Test plan & additional information (optional):** Select to copy test plan and additional information details to the new group.</span></span>
            <span data-ttu-id="a3f69-268">- **ドキュメント (オプション):** 選択すると、新しいグループにドキュメントがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-268">- **Documents (optional):** Select to copy documents to the new group.</span></span>

3. <span data-ttu-id="a3f69-269">[**保存**] を選択して、評価を作成します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-269">Select **Save** to create the Assessment.</span></span>

### <a name="viewing-assessments"></a><span data-ttu-id="a3f69-270">Assessment の表示</span><span class="sxs-lookup"><span data-stu-id="a3f69-270">Viewing Assessments</span></span>

#### <a name="view-an-assessment"></a><span data-ttu-id="a3f69-271">評価を表示する</span><span class="sxs-lookup"><span data-stu-id="a3f69-271">View an Assessment</span></span>
  
1. <span data-ttu-id="a3f69-272">評価ダッシュボードで、評価名を選択して、アクションアイテムとコントロール情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-272">In the Assessments dashboard, select the assessment name to open it and view the Action Items and Controls Info.</span></span>

<span data-ttu-id="a3f69-273">Office 365 および ISO 27001 の評価の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-273">Here's an example of the Assessment for Office 365 and ISO 27001.</span></span> <span data-ttu-id="a3f69-274">最初のビューは、コンプライアンスマネージャー (プレビュー) の新しいアクションアイテムビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-274">The first view illustrates the new Action Items view in Compliance Manager (Preview).</span></span>

![コンプライアンスマネージャーのアクションアイテムビュー](media/compliance-manager-action-items.png)

<span data-ttu-id="a3f69-276">アクションはアルファベット順に一覧表示され、各アクションにスコアと所有者が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-276">The Actions are listed in alphabetical order, and each Action is assigned a score and an owner.</span></span> <span data-ttu-id="a3f69-277">各アクションの詳細については、「詳細情報の**読み取り**」リンクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="a3f69-277">Select  the **Read More** link to read the details of each Action.</span></span> 

![コンプライアンスマネージャーのアクションアイテムビュー](media/compliance-manager-actions-read-more.png)

<span data-ttu-id="a3f69-279">アクションを管理、割り当て、実装、およびテストするには、[**レビュー** ] リンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-279">Select the **Review** link to manage, assign, implement, and test the action.</span></span> <span data-ttu-id="a3f69-280">次に、アクションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-280">Below is an example Action.</span></span>

![コンプライアンスマネージャーのアクションビュー](media/compliance-manager-action.png)

<span data-ttu-id="a3f69-282">コンプライアンスマネージャーの以前のバージョンでは、要件を実装するワークフローが制御レベルで実行されました。</span><span class="sxs-lookup"><span data-stu-id="a3f69-282">In previous versions of Compliance Manager, the workflow for implementing requirements was performed at the Control level.</span></span> <span data-ttu-id="a3f69-283">コンプライアンス責任者は、コントロールを実装するユーザーにコントロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-283">A compliance officer would assign a control to someone to implement the control.</span></span> <span data-ttu-id="a3f69-284">これには、次の2つの欠点がありました。</span><span class="sxs-lookup"><span data-stu-id="a3f69-284">There were two drawbacks to this:</span></span>

- <span data-ttu-id="a3f69-285">多くの場合、コントロールに関連付けられた複数のアクションがあり、コントロールを割り当てられたユーザーは、コントロールを実装するために必要だったすべてのアクションを実行するための適切な担当者ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-285">Controls often had multiple actions associated with them, and the user to whom a control was assigned, might not be the right person to complete all actions that were required to implement the control</span></span>
- <span data-ttu-id="a3f69-286">個別のタスクを1つのアクションに結合することによって、コンプライアンスマネージャー (プレビュー) でテナント構成の変更を自動的に記録するために使用される信号とテレメトリのコレクションを実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a3f69-286">Combining separate tasks into a single Action prevented the collection of the signals and telemetry that is used to automatically record tenant configuration changes in Compliance Manager (Preview).</span></span>

<span data-ttu-id="a3f69-287">コンプライアンスマネージャー (プレビュー) では、ワークフロープロセスはコントロールレベルからアクションレベルに移動されました。</span><span class="sxs-lookup"><span data-stu-id="a3f69-287">In Compliance Manager (Preview), the workflow process has moved from the Control level to the Action level.</span></span> <span data-ttu-id="a3f69-288">アクションを確認するときは、アクションワークフローを管理するために、次のフィールドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-288">When reviewing an Action, the following fields can be used to manage the Action workflow:</span></span>

- <span data-ttu-id="a3f69-289">**ユーザーを割り当てる:** このアクションを割り当てるユーザーを選択または入力するには、このフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-289">**Assign User:** Select this field to choose or enter the user to whom this Action should be assigned.</span></span> <span data-ttu-id="a3f69-290">リストをスクロールするか、検索する名前を入力して、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-290">You can scroll through the list, or type a name to find it, and then select it.</span></span>
- <span data-ttu-id="a3f69-291">**ドキュメントの管理:** 実装の証拠は、Office ドキュメント、画像ファイル、スクリーンショット、CSV または TXT の PowerShell 出力、および Pdf の形式でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-291">**Manage Documents:** You can upload evidence of implementation in the form of Office documents, image files and screenshots, PowerShell output in CSV or TXT, and PDFs.</span></span>
- <span data-ttu-id="a3f69-292">**実装の状態:** アクションの現在の実装状態を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-292">**Implementation Status:** Used to indicate the Action’s current implementation status.</span></span> <span data-ttu-id="a3f69-293">使用可能な値は、実装、実装、代替実装、計画済み、スコープ内ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-293">Possible values are Not Implemented, Implemented, Alternative Implementation, Planned, and Not in Scope.</span></span>
- <span data-ttu-id="a3f69-294">**実装日:** アクションが実行された日付。</span><span class="sxs-lookup"><span data-stu-id="a3f69-294">**Implementation Date:** The date on which the Action was taken.</span></span>
- <span data-ttu-id="a3f69-295">**テスト結果:** 実装検証の結果を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-295">**Test Result:** Used to indicate the results of implementation validation.</span></span> <span data-ttu-id="a3f69-296">可能な値は、評価、合格、Failed-低リスク、失敗-中規模リスク、失敗-高リスク、範囲外。</span><span class="sxs-lookup"><span data-stu-id="a3f69-296">Possible values are Not Assessed, Passed, Failed-Low Risk, Failed-Medium Risk, Failed-High Risk, and Not in Scope.</span></span>
- <span data-ttu-id="a3f69-297">**テストの日付:** 検証が発生した日付。</span><span class="sxs-lookup"><span data-stu-id="a3f69-297">**Test Date:** The date on which validation occurred.</span></span>
- <span data-ttu-id="a3f69-298">**実装に関する注意事項:** 組織の実装の詳細と、含める必要のあるメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-298">**Implementation Notes:** Enter implementation details for your organization, along with any notes that you want to include.</span></span>
- <span data-ttu-id="a3f69-299">**テスト計画:** このアクションのテスト計画の詳細と、追加するメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-299">**Test Plan:** Enter the test plan details for this action, along with any notes that you want to include.</span></span>
- <span data-ttu-id="a3f69-300">**追加情報:** このアクションに関する追加情報を入力するか、組織内での実装方法、および必要なメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-300">**Additional Information:** Enter any additional information about this Action or how it was implemented in your organization, along with any notes you want to include.</span></span>

<span data-ttu-id="a3f69-301">コンプライアンスマネージャー (プレビュー) には、以前のバージョンで見つけたコントロールベースのピボットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-301">Compliance Manager (Preview) also includes the control-based pivot found in previous versions.</span></span> <span data-ttu-id="a3f69-302">[ **Controls Info** dashboard] を選択して表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-302">Select the **Controls Info** dashboard to view it.</span></span> <span data-ttu-id="a3f69-303">コントロールの情報は、評価およびテンプレートレベルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-303">You can view information for controls at the Assessment and Template level.</span></span> <span data-ttu-id="a3f69-304">評価用の Controls Info ダッシュボードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-304">Below is an example of the Controls Info dashboard for Assessments.</span></span>

![コンプライアンスマネージャーコントロールの情報ビュー](media/compliance-manager-controls-info.png)

<span data-ttu-id="a3f69-306">評価の場合、Controls Info dashboard には次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-306">For Assessments, the Controls Info dashboard displays:</span></span>

- <span data-ttu-id="a3f69-307">表示するグループを選択するための**グループ**ドロップダウン (複数のグループを使用する場合)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-307">A **Group** dropdown to select which Group to view (when using multiple groups).</span></span>
- <span data-ttu-id="a3f69-308">表示する評価を選択するための**評価**ドロップダウン</span><span class="sxs-lookup"><span data-stu-id="a3f69-308">An **Assessment** dropdown to select which Assessment to view.</span></span>
- <span data-ttu-id="a3f69-309">選択した評価に関するメタデータ (次のものが含まれます)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-309">Metadata about the selected Assessment, including:</span></span>
    - <span data-ttu-id="a3f69-310">評価されたコントロールの総数**を示す、評価さ**れたコントロールの進捗状況のインジケーター。</span><span class="sxs-lookup"><span data-stu-id="a3f69-310">A progress indicator for **Assessed Controls** showing the number of assessed controls over the total number of controls.</span></span>
    - <span data-ttu-id="a3f69-311">評価の現在の**コンプライアンススコア**。パーセンテージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-311">The current **Compliance Score** for the Assessment, shown as a percentage.</span></span>
    - <span data-ttu-id="a3f69-312">評価に使用された**証明書**と**製品**に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="a3f69-312">Details about the **Certification** and **Product** used in the Assessment.</span></span>
    - <span data-ttu-id="a3f69-313">評価の現在の**状態**と最終**更新**日。</span><span class="sxs-lookup"><span data-stu-id="a3f69-313">The current **Status** of and last **Modified** date for the Assessment.</span></span>
- <span data-ttu-id="a3f69-314">評価の対象となる**サービス**の一覧。</span><span class="sxs-lookup"><span data-stu-id="a3f69-314">A list of **In Scope Services** for the Assessment.</span></span>
- <span data-ttu-id="a3f69-315">コントロールファミリごとにグループ化されたコントロールの詳細。お客様のアクションと Microsoft 実装の詳細情報へのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-315">Details of the controls, grouped by Control Family, with links to customer actions and Microsoft implementation details:</span></span>
    - <span data-ttu-id="a3f69-316">**操作により**、一部またはすべてのコントロールの要件を満たすために実行できるユーザー操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-316">**Your Actions** displays the customer actions that you can perform to satisfy some or all the control’s requirements.</span></span> <span data-ttu-id="a3f69-317">多くのコントロールには複数のアクションが関連付けられており、コントロールに関連付けられたすべてのアクションがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-317">Many controls have multiple Actions associated with them, and all Actions associated with a control are displayed here.</span></span> <span data-ttu-id="a3f69-318">ここでのアクションは、アクションダッシュボードに一覧表示されている UI と同じです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-318">The Actions here have the same UI as those listed in the Actions dashboard.</span></span>
    - <span data-ttu-id="a3f69-319">**Microsoft アクション**では、選択した証明書コントロールに適用される microsoft の内部フレームワークからのコントロールの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-319">**Microsoft Actions** displays the list of controls from Microsoft’s internal framework that apply to the selected certification control.</span></span> <span data-ttu-id="a3f69-320">内部コントロールごとに、[**実装**済み] を選択して、次に示すように、Microsoft の実装とテストの詳細、およびテスト結果とテスト日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-320">For each internal control, select **Implemented** to see Microsoft’s implementation and test details, along with the test result and test date, as shown below.</span></span>

![コンプライアンスマネージャー Microsoft アクションビュー](media/compliance-manager-microsoft-action.png)

### <a name="export-an-assessment"></a><span data-ttu-id="a3f69-322">評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a3f69-322">Export an Assessment</span></span>

<span data-ttu-id="a3f69-323">組織内のコンプライアンスステークホルダーまたは外部の監査者や規制機関の評価を Excel ファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-323">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="a3f69-324">レポートは、レポートが作成された日時の時点での評価のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-324">The report is a snapshot of the Assessment as of the date and time that the report is created.</span></span> <span data-ttu-id="a3f69-325">このレポートには、評価のためのすべての Microsoft およびお客様が管理するコントロールの詳細、制御実装状態、コントロールのテスト日、テスト結果、アップロードされた証拠ドキュメントへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-325">The report contains the details for all Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and provides links to uploaded evidence documents.</span></span> <span data-ttu-id="a3f69-326">アーカイブされた評価はアップロードされたドキュメントへのリンクを保持しないため、評価レポートをアーカイブする前に、評価レポートをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-326">You should export the Assessment report prior to archiving an assessment because archived assessments do not retain links to uploaded documents.</span></span>
  
### <a name="export-an-assessment-report"></a><span data-ttu-id="a3f69-327">評価レポートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a3f69-327">Export an Assessment report</span></span>
  
1. <span data-ttu-id="a3f69-328">コンプライアンスマネージャーダッシュボードで、[**コントロールの情報**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-328">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="a3f69-329">エクスポートする評価のドロップダウンメニューで、**グループ**と**評価**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-329">Select the **Group** and **Assessment** in the drop-down menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="a3f69-330">[**エクスポート**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-330">Select the **Export** button.</span></span>

<span data-ttu-id="a3f69-331">評価レポートは、ブラウザーセッションで Excel ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-331">The assessment report is downloaded as an Excel file in your browser session.</span></span> <span data-ttu-id="a3f69-332">Excel ファイルのファイル名の既定値は、評価のタイトルです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-332">The files name for the Excel file defaults to the title of the Assessment.</span></span>

### <a name="archive-a-template-or-an-assessment"></a><span data-ttu-id="a3f69-333">テンプレートまたは評価をアーカイブする</span><span class="sxs-lookup"><span data-stu-id="a3f69-333">Archive a Template or an Assessment</span></span>

<span data-ttu-id="a3f69-334">テンプレートまたは評価が終了し、法令遵守のために必要でなくなったら、アーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-334">When you are finished with a Template or Assessment and no longer need it for compliance purposes, you can archive it.</span></span> <span data-ttu-id="a3f69-335">テンプレートまたは評価がアーカイブされている場合は、既定のビューから削除され、[アーカイブの表示] チェックボックスをオンにして表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-335">When a Template or Assessment is archived, it is removed from the default view, and you must check the Show Archived checkbox to display it.</span></span>

![コンプライアンスマネージャー Microsoft アクションビュー](media/compliance-manager-archive-assessment-view.png)
  
> [!IMPORTANT]
> <span data-ttu-id="a3f69-337">アーカイブされた評価は、アップロードされた証拠ドキュメントへのリンクを保持しません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-337">Archived Assessments do not retain their links to uploaded evidence documents.</span></span> <span data-ttu-id="a3f69-338">アーカイブの前に評価をエクスポートして、レポートの証拠ドキュメントへのリンクを保持することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-338">It is highly recommended that you export the Assessment before archiving to retain links to the evidence documents in the report.</span></span>
  
#### <a name="archive-a-template"></a><span data-ttu-id="a3f69-339">テンプレートをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="a3f69-339">Archive a Template</span></span>

1. <span data-ttu-id="a3f69-340">**テンプレート**ダッシュボードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-340">Open the **Templates** dashboard.</span></span>
2. <span data-ttu-id="a3f69-341">アーカイブするテンプレートを見つけて、[アーカイブ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-341">Locate the Template you want to archive and select the archive icon.</span></span>
3. <span data-ttu-id="a3f69-342">確認メッセージが表示されたら、[**アーカイブ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-342">When you see the confirmation message, select **Archive**.</span></span>

#### <a name="archive-an-assessment"></a><span data-ttu-id="a3f69-343">評価をアーカイブする</span><span class="sxs-lookup"><span data-stu-id="a3f69-343">Archive an Assessment</span></span>

1. <span data-ttu-id="a3f69-344">**評価**ダッシュボードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-344">Open the **Assessments** dashboard.</span></span>
2. <span data-ttu-id="a3f69-345">アーカイブする評価を含む**グループ**をドロップダウンから選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-345">Select the **Group** from the dropdown that contains the Assessment you want to archive.</span></span>
3. <span data-ttu-id="a3f69-346">アーカイブする評価を見つけて、[アーカイブ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-346">Locate the Assessment you want to archive and select the archive icon.</span></span>
4. <span data-ttu-id="a3f69-347">確認メッセージが表示されたら、[**アーカイブ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-347">When you see the confirmation message, select **Archive**.</span></span>

#### <a name="view-archived-assessments"></a><span data-ttu-id="a3f69-348">アーカイブされた評価の表示</span><span class="sxs-lookup"><span data-stu-id="a3f69-348">View archived Assessments</span></span>
  
1. <span data-ttu-id="a3f69-349">[**評価**ダッシュボード] タブを開き、[**アーカイブの表示**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-349">Open the **Assessments** dashboard tab and check the **Show Archived** checkbox.</span></span>
2. <span data-ttu-id="a3f69-350">アーカイブされた評価は、「アーカイブされた**評価**」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-350">The archived assessments appear in the **Archived Assessments** section.</span></span>
3. <span data-ttu-id="a3f69-351">[評価] の名前を選択して、評価を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-351">Select the Assessment name to open and view the Assessment.</span></span>

#### <a name="activate-an-archived-assessment"></a><span data-ttu-id="a3f69-352">アーカイブされた評価をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="a3f69-352">Activate an archived Assessment</span></span>

1. <span data-ttu-id="a3f69-353">[**評価**] タブで、[**アーカイブの表示**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-353">On the **Assessments** tab and select the **Show Archived** checkbox.</span></span>
2. <span data-ttu-id="a3f69-354">アーカイブされた評価は、「アーカイブされた**評価**」セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-354">The archived assessments appear in the **Archived Assessments** section.</span></span>
3. <span data-ttu-id="a3f69-355">アクティブ化する評価を見つけて、[アクティブ化] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-355">Locate the Assessment you want to activate and select the activate icon.</span></span>
4. <span data-ttu-id="a3f69-356">確認メッセージが表示されたら、[**アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-356">When you see the confirmation message, select **Activate**.</span></span>

## <a name="controls-and-actions"></a><span data-ttu-id="a3f69-357">コントロールとアクション</span><span class="sxs-lookup"><span data-stu-id="a3f69-357">Controls and Actions</span></span>

<span data-ttu-id="a3f69-358">コントロールとアクションは、コンプライアンスマネージャー (プレビュー) で使用される主要なデータのピボットです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-358">Controls and Actions are the primary data pivots used in Compliance Manager (Preview).</span></span> <span data-ttu-id="a3f69-359">以前のバージョンのコンプライアンスマネージャーに含まれていたコントロールピボットは、Microsoft とお客様のコントロールを同じコントロールファミリに表示するように強化されています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-359">The Control pivot, which existed in previous versions of Compliance Manager, has been enhanced to show the Microsoft and customer controls in the same control families.</span></span> <span data-ttu-id="a3f69-360">この統合ビューを使用すると、管理者ごとに完全な共有責任モデルを簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-360">This consolidated view makes it easier to see the complete shared responsibility model on a per-control basis.</span></span> <span data-ttu-id="a3f69-361">アクションピボットは、コンプライアンスマネージャー (プレビュー) で新しく追加されたものであり、Microsoft が推奨するすべての操作を合理化したビューを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-361">The Action pivot is new in Compliance Manager (Preview) and it is designed to provide a streamlined view of all of actions recommended by Microsoft.</span></span>

### <a name="controls"></a><span data-ttu-id="a3f69-362">コントロール</span><span class="sxs-lookup"><span data-stu-id="a3f69-362">Controls</span></span>

<span data-ttu-id="a3f69-363">コントロールは、コントロールの情報ダッシュボードから表示できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-363">Controls can be viewed from the Controls Info dashboard.</span></span> <span data-ttu-id="a3f69-364">コントロールは、標準、認定、規制、またはフレームワークからの要件を表します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-364">Controls represent the requirements from a standard, certification, regulation, or framework.</span></span> <span data-ttu-id="a3f69-365">これらの要件を複数の標準、規制などにマッピングし、それらをアクションに関連付けるには、すべての要件をコントロールフレームワークとして扱います。</span><span class="sxs-lookup"><span data-stu-id="a3f69-365">To map these requirements across multiple standards, regulations, etc., and to associate them with Actions, everything is treated as if it were a control framework.</span></span> <span data-ttu-id="a3f69-366">たとえば、次に示すように、法令規制 (HIPAA など) がセクションごとに分類されており、コンプライアンスマネージャーの HIPAA コントロールは、これらのセクションと同じ番号付けスキームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-366">For example, like a control framework, regulations, such as HIPAA, have been broken down by section, and the HIPAA controls in Compliance Manager use the same numbering scheme as those sections, as shown below:</span></span>

![コンプライアンスマネージャー Microsoft コントロールの詳細](media/compliance-manager-control-details.png)

<span data-ttu-id="a3f69-368">次の3種類のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-368">There are three types of controls:</span></span>

1. <span data-ttu-id="a3f69-369">**Microsoft 管理コントロール:** これらは microsoft のみが責任を持っているコントロールです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-369">**Microsoft-managed controls:** these are controls for which only Microsoft has responsibility.</span></span> <span data-ttu-id="a3f69-370">これらは、インボックステンプレートに表示され、Microsoft によってコンプライアンスマネージャーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-370">They appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span>
2. <span data-ttu-id="a3f69-371">**顧客管理コントロール:** 顧客のみが責任を持つコントロールです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-371">**Customer-managed controls:** these are controls for which only customers have responsibility.</span></span> <span data-ttu-id="a3f69-372">これらは、インボックステンプレートに表示され、顧客からコンプライアンスマネージャーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-372">They appear in the in-box Templates and are added to Compliance Manager by customers.</span></span>
3. <span data-ttu-id="a3f69-373">**共有管理コントロール:** これらは、Microsoft とお客様との間で責任を共有するコントロールです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-373">**Shared management controls:** these are controls where responsibility is shared between Microsoft and the customer.</span></span> <span data-ttu-id="a3f69-374">これらは、インボックステンプレートに表示され、Microsoft によってコンプライアンスマネージャーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-374">These appear in the in-box Templates and are added to Compliance Manager by Microsoft.</span></span> <span data-ttu-id="a3f69-375">お客様は、Microsoft 管理コントロールを編集または無効化することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-375">The customer can also edit or disable Microsoft-managed controls.</span></span>

### <a name="actions-items"></a><span data-ttu-id="a3f69-376">アクションアイテム</span><span class="sxs-lookup"><span data-stu-id="a3f69-376">Actions Items</span></span>

<span data-ttu-id="a3f69-377">[アクション] アイテムは、標準または規制の要件を実装したり、組織の実装要件をテスト、検証、および文書化したりするために推奨されるタスクです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-377">Actions Items are the recommended tasks for implementing the requirements of a standard or regulation, or to test, verify, and document your organization's implementation requirements.</span></span> <span data-ttu-id="a3f69-378">アクションは1つまたは複数のコントロールに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-378">Actions are associated with one or more Controls.</span></span> <span data-ttu-id="a3f69-379">各コントロールには1つ以上のアクションが関連付けられており、各アクションは1つまたは複数のコントロールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-379">Each Control has one or more Action associated with it, and each Action can be associated with one or more Controls.</span></span> <span data-ttu-id="a3f69-380">アクションは、組織によって割り当てられ、追跡され、検証されるオブジェクトであるため、コンプライアンスマネージャー (プレビュー) のコアワークフローの一部です。</span><span class="sxs-lookup"><span data-stu-id="a3f69-380">Actions are part of the core workflow in Compliance Manager (Preview), as they are the objects that are assigned, tracked, and validated by your organization.</span></span>

#### <a name="assign-action-items"></a><span data-ttu-id="a3f69-381">アクションアイテムを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a3f69-381">Assign Action Items</span></span>
  
1. <span data-ttu-id="a3f69-382">[**アクションアイテム**] ダッシュボードで、アクションを割り当てる対象の評価を含む**グループ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-382">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to assign.</span></span>
2. <span data-ttu-id="a3f69-383">[**評価**] ドロップダウンで、アクションを割り当てる対象の評価を選択するか、または [**すべて**] を選択して、使用可能なすべてのアクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-383">In the **Assessment** dropdown, select the Assessment whose Action you want to assign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="a3f69-384">割り当てるアクションを見つけ、[**所有者**] 列で、**レビュー**用のリンクを選択するか、**実装**するか**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-384">Locate the Action you want to assign, and in the **Owner** column, select the link for **Review**, **Implemented** or **Test**.</span></span>
4. <span data-ttu-id="a3f69-385">[**ユーザーの割り当て**] フィールドを選択し、組織内のユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-385">Select the **Assign User** field, and a list of users in your organization appear.</span></span> <span data-ttu-id="a3f69-386">リストをスクロールし、[ユーザー] または [リストにフィルターを適用] を選択して、ユーザーの名前を入力してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-386">Scroll the list and select user or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="a3f69-387">[実装メモ] フィールドに、割り当てられたユーザーに伝えたいメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-387">In the Implementation Notes field, enter any notes you wish to convey to the assigned user.</span></span>
6. <span data-ttu-id="a3f69-388">[**保存**] を選択して、アクションを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-388">Select **Save** to assign the Action.</span></span>

#### <a name="reassign-action-items"></a><span data-ttu-id="a3f69-389">アクションアイテムの再割り当て</span><span class="sxs-lookup"><span data-stu-id="a3f69-389">Reassign Action Items</span></span>

<span data-ttu-id="a3f69-390">この関数を使用すると、新しいユーザーにアクションを再割り当てすることで、ユーザーアカウントのアクティブまたは保留中の依存関係を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-390">This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning an Action to a new user.</span></span>

1. <span data-ttu-id="a3f69-391">[**アクションアイテム**] ダッシュボードで、アクションを再割り当てするアセスメントを含む**グループ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-391">On the **Action Items** dashboard, select the **Group** containing the Assessment(s) whose Action you want to reassign.</span></span>
2. <span data-ttu-id="a3f69-392">[**評価**] ドロップダウンで、アクションを再割り当てする評価を選択するか、または [**すべて**] を選択して、使用可能なすべてのアクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-392">In the **Assessment** dropdown, select the Assessment whose Action you want to reassign, or select **All** from the dropdown to see all available Actions.</span></span>
3. <span data-ttu-id="a3f69-393">再割り当てするアクションを見つけ、[**所有者**] 列で、**レビュー**、**実装**、または**テスト**用のリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-393">Locate the Action you want to reassign, and in the **Owner** column, select the link for **Review**, **Implemented**, or **Test**.</span></span>
4. <span data-ttu-id="a3f69-394">[**ユーザーの割り当て**] フィールドから既存のユーザーを削除し、ユーザーの一覧から別のユーザーを選択するか、または一覧をフィルター処理して、ユーザーの名前を入力してユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-394">Delete the existing user from the **Assign User** field, and either choose a different user from the list of users or filter the list to select a user by typing in the user’s name.</span></span>
5. <span data-ttu-id="a3f69-395">[実装メモ] フィールドに、ユーザーに伝えたいメモを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-395">In the Implementation Notes field, enter any notes you wish to convey to the user.</span></span>
6. <span data-ttu-id="a3f69-396">[**保存**] を選択して、アクションを再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-396">Select **Save** to reassign the Action.</span></span>

## <a name="templates"></a><span data-ttu-id="a3f69-397">テンプレート</span><span class="sxs-lookup"><span data-stu-id="a3f69-397">Templates</span></span>

<span data-ttu-id="a3f69-398">テンプレートは、製品と証明書に関連付けられているコンプライアンスマネージャー (プレビュー) の基本オブジェクトです (たとえば、標準、規制、制御フレームワークなど)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-398">A Template is the base object in Compliance Manager (Preview) that is associated with a Product and a Certification (for example, standard, regulation, control framework, etc.).</span></span> <span data-ttu-id="a3f69-399">テンプレートは、テンプレートダッシュボードから表示および追加できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-399">Templates can be viewed and added from the Templates dashboard.</span></span>

![コンプライアンスマネージャー Microsoft テンプレートダッシュボード](media/compliance-manager-template-dashboard.png)
 
<span data-ttu-id="a3f69-401">ダッシュボードには各テンプレートが表示され、テンプレートに関連付けられている証明書と製品、テンプレートが作成された日付、最終変更された日付、顧客および Microsoft 管理コントロールの数、およびの最大コンプライアンススコアテンプレート、およびテンプレートの状態 (承認済み、保留中の承認、インポートされたものなど)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-401">The dashboard displays each Template, along with the Certification and Product associated with the Template, the dates on which the Template was created and last modified, the number of customer and Microsoft-managed controls, the maximum Compliance Score for the Template, and the status of the Template (for example, Approved, Pending Approval, Imported).</span></span>

<span data-ttu-id="a3f69-402">組み込みテンプレートには、それぞれに関連付けられている組み込みの評価がありますが、組み込みのテンプレートに基づいて追加の評価を作成したり、独自のテンプレートをインポートしたり、それらを使用してカスタムの評価を作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-402">The built-in Templates each have a built-in Assessment associated with them, but you can create additional Assessments based on built-in Templates, and you can import your own Templates, and create custom Assessments based off those.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="a3f69-403">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="a3f69-403">Create a Template</span></span>

<span data-ttu-id="a3f69-404">テンプレートを作成するには、既存のテンプレートをコピーするか、カスタムテンプレートをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-404">You can create a Template by copying an existing Template or by importing a custom Template.</span></span> <span data-ttu-id="a3f69-405">テンプレートデータに使用する必要がある特定の形式とスキーマがありますが、コンプライアンスマネージャーにはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-405">There is a specific format and schema that must be used for Template data or it will not import into Compliance Manager.</span></span> <span data-ttu-id="a3f69-406">適切なスキーマとサンプルデータを含むファイルは、ここからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-406">A file with the correct schema and sample data can be downloaded from here.</span></span>
<span data-ttu-id="a3f69-407">各カスタムテンプレートは、次の5つのタブを含む個別の Excel ブック (.xls 形式または .xlsx 形式) に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-407">Each custom Template should be in a separate Excel workbook (in .xls or .xlsx format) that contains five tabs:</span></span>

1. <span data-ttu-id="a3f69-408">テンプレート-評価</span><span class="sxs-lookup"><span data-stu-id="a3f69-408">Template-Assessment</span></span>
2. <span data-ttu-id="a3f69-409">ControlFamily</span><span class="sxs-lookup"><span data-stu-id="a3f69-409">ControlFamily</span></span>
3. <span data-ttu-id="a3f69-410">アクション</span><span class="sxs-lookup"><span data-stu-id="a3f69-410">Actions</span></span>
4. <span data-ttu-id="a3f69-411">Ownership</span><span class="sxs-lookup"><span data-stu-id="a3f69-411">Ownership</span></span>
5. <span data-ttu-id="a3f69-412">Dimensions</span><span class="sxs-lookup"><span data-stu-id="a3f69-412">Dimensions</span></span>

<span data-ttu-id="a3f69-413">各タブ内で使用されるスキーマの詳細を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-413">The schema used within each tab is detailed below.</span></span>

#### <a name="template-assessment-tab"></a><span data-ttu-id="a3f69-414">[テンプレート-評価] タブ</span><span class="sxs-lookup"><span data-stu-id="a3f69-414">Template-Assessment tab</span></span>

<span data-ttu-id="a3f69-415">このタブには1つの列があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-415">This tab has a single column:</span></span>

- <span data-ttu-id="a3f69-416">**inScopeServices**: テンプレートの範囲内にある製品またはサービスのコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="a3f69-416">**inScopeServices**: Comma-delimited list of products or services that are in-scope for the Template.</span></span>

#### <a name="controlfamily-tab"></a><span data-ttu-id="a3f69-417">ControlFamily タブ</span><span class="sxs-lookup"><span data-stu-id="a3f69-417">ControlFamily tab</span></span>

<span data-ttu-id="a3f69-418">このタブには、[Actions] タブに表示されているアクションにマップされるコントロールを定義する列が含まれています。また、コントロール名、ファミリ、タイトル、説明などの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-418">This tab includes columns that define the controls that are mapped to the Actions listed on the Actions tab, and includes details like control name, family, title, and description.</span></span>  <span data-ttu-id="a3f69-419">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-419">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="a3f69-420">**controlName:** 証明/標準/規制などからのコントロール名。</span><span class="sxs-lookup"><span data-stu-id="a3f69-420">**controlName:** Control name from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="a3f69-421">**Controlfamily:** 認定/標準、規制などからファミリーを制御します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-421">**controlFamily:** Control family from certification/standard, regulation, etc.</span></span>
- <span data-ttu-id="a3f69-422">**Controltitle:** 資格/標準/規制などからタイトルを制御します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-422">**controlTitle:** Control title from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="a3f69-423">**Controldescription:** 認定/標準/規制などから、説明を制御します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-423">**controlDescription:** Control description from certification/standard/regulation, etc.</span></span>
- <span data-ttu-id="a3f69-424">**Controlversion:** オプションのコントロールバージョン情報。</span><span class="sxs-lookup"><span data-stu-id="a3f69-424">**controlVersion:** Optional control version info.</span></span>  <span data-ttu-id="a3f69-425">例: NIST 800-53 の場合、現在の値は Rev 4 なので、controlVersion は4です。</span><span class="sxs-lookup"><span data-stu-id="a3f69-425">Example: for NIST 800-53, the current value is Rev 4, so the controlVersion is 4.</span></span>  <span data-ttu-id="a3f69-426">CSA CCM の場合、これは3.0.1 です。</span><span class="sxs-lookup"><span data-stu-id="a3f69-426">For CSA CCM, it is 3.0.1.</span></span>
- <span data-ttu-id="a3f69-427">**isDisabled:** コントロールが無効にされているかどうかを示すには、TRUE または FALSE を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-427">**isDisabled:** Use TRUE or FALSE to indicate whether the control has been disabled.</span></span>
- <span data-ttu-id="a3f69-428">**controlType:** CC を使用して、顧客が管理するコントロールであることを示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-428">**controlType:** Use CC to indicate these are customer-managed controls.</span></span>
- <span data-ttu-id="a3f69-429">**controlComplianceScore:** コントロールに割り当てられているすべてのアクションのスコアの合計。</span><span class="sxs-lookup"><span data-stu-id="a3f69-429">**controlComplianceScore:** Sum of the score of all Actions assigned to the Control.</span></span>
- <span data-ttu-id="a3f69-430">**Controlactiontitle:**[操作] タブに表示されている、このコントロールのすべての actionTitles の二重セミコロンで区切られたリストです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-430">**controlActionTitle:** Double semi-colon-delimited list of all actionTitles for this control as listed on the Actions tab.</span></span> 

#### <a name="actions-tab"></a><span data-ttu-id="a3f69-431">[操作] タブ</span><span class="sxs-lookup"><span data-stu-id="a3f69-431">Actions tab</span></span>

<span data-ttu-id="a3f69-432">このタブには、個々のアクションを定義する列が含まれており、アクションタイトル、所有権、およびディメンションなどの詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-432">This tab includes columns that define individual Actions, and it includes details like action title, ownership, and dimensions.</span></span> <span data-ttu-id="a3f69-433">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-433">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span> 

- <span data-ttu-id="a3f69-434">**Actiontitle:** アクションのタイトル。</span><span class="sxs-lookup"><span data-stu-id="a3f69-434">**actionTitle:** Title of the action.</span></span> <span data-ttu-id="a3f69-435">各タイトルは一意である必要があり、Pascal ケースを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-435">Each title must be unique, and we recommend using Pascal case.</span></span>
- <span data-ttu-id="a3f69-436">**actionRelatedODVs:** Actiontitles 列に表示されている子の親である actionTitles の二重セミコロンで区切られたリストです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-436">**actionRelatedODVs:** Double semicolon-delimited list of actionTitles that are parents of the child listed in the actionTitle column.</span></span> <span data-ttu-id="a3f69-437">親/子リレーションシップでは、親はハイウォーターマークを表します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-437">In a parent/child relationship, the parent represents the high watermark.</span></span> <span data-ttu-id="a3f69-438">したがって、親アクションを完了した場合は、すべての子アクションも完了します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-438">Thus, if you complete a parent action, you also complete all child actions.</span></span> <span data-ttu-id="a3f69-439">たとえば、同じような要件があり、パスワードの長さなど、標準で定義された値が異なる場合は、少なくとも15文字が必要で、もう1つは少なくとも12または10が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3f69-439">For example, when you have similar requirements but different standard-defined values, such as password length, where one standard/regulation requires a minimum of 15 characters, and another requires a minimum of 12 or 10.</span></span> <span data-ttu-id="a3f69-440">この例では15が親になります。また、15文字以上を構成すると、他の評価で12文字または10文字が推奨されるアクションも満たされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-440">15 would be the parent in this example, and if you configure a minimum of 15 characters, you also satisfy the actions that recommend 12 or 10 characters in other assessments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3f69-441">ActionRelatedODVs 列はスキーマの必須の列です。ただし、機能 (関連アクション) はコンプライアンスマネージャー (プレビュー) では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-441">The actionRelatedODVs column is a required column for the schema; however, the feature (related actions) is not available in Compliance Manager (Preview).</span></span>  <span data-ttu-id="a3f69-442">今後のリリースで追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="a3f69-442">It is scheduled to be added in a later release.</span></span>

- <span data-ttu-id="a3f69-443">**Actiondimensionvalues:** 次の形式を使用して、[ディメンション] タブの該当するディメンションの二重セミコロンで区切られたリストです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-443">**actionDimensionValues:** Double semicolon-delimited list of applicable dimensions from the Dimensions tab, using the following format:</span></span>

    ```
    Dimension Key::Dimension Value;;Dimension Key::Dimension Value.
    ```
    
    <span data-ttu-id="a3f69-444">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-444">For example:</span></span>

    ```
    Product::Office 365;;Certification::NIST CSF
    ```

    <span data-ttu-id="a3f69-445">カスタムテンプレートで使用されているすべてのディメンションは、ディメンションダッシュボードに既に表示されている場合でも、インポートファイルの [ディメンション] タブに一覧表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-445">All Dimensions that are used in a custom Template must be listed on the Dimensions tab of the import file, even if they are already listed on the Dimensions dashboard.</span></span>
- <span data-ttu-id="a3f69-446">**Actionscore:** 各アクションの数値です。この値は、そのアクションのスコアを表します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-446">**actionScore:** Numeric value for each Action, which represents the score for that action.</span></span> <span data-ttu-id="a3f69-447">各アクションの目的と実施に基づいて、組み込み評価で使用されるスコアリングモデルをフォローすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-447">We recommend following the scoring model used by the built-in assessments, which is based on each Action’s purpose and enforcement.</span></span>
- <span data-ttu-id="a3f69-448">**アクションの所有権:** セミコロンで区切られた、二重引用符で囲まれた所有者のリスト。</span><span class="sxs-lookup"><span data-stu-id="a3f69-448">**actionOwnership:** Double semicolon-delimited list of Owners.</span></span> <span data-ttu-id="a3f69-449">一覧表示されたすべての所有者が [所有権] タブに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-449">All listed Owners must be included on the Ownership tab.</span></span>
- <span data-ttu-id="a3f69-450">**Actiondescription:** 各アクションのテキスト。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-450">**actionDescription:** Text of each Action, which must be unique.</span></span> <span data-ttu-id="a3f69-451">以下に示すように、このフィールドは Markdown Language をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-451">This field supports Markdown Language as described below.</span></span>

#### <a name="ownership-tab"></a><span data-ttu-id="a3f69-452">[所有権] タブ</span><span class="sxs-lookup"><span data-stu-id="a3f69-452">Ownership tab</span></span>

<span data-ttu-id="a3f69-453">このタブには、各アクションの所有者を定義する列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-453">This tab includes columns that define owners for each action.</span></span>  <span data-ttu-id="a3f69-454">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-454">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="a3f69-455">**所有の出荷先の所有者:** 所有者/責任者の一意の名前。</span><span class="sxs-lookup"><span data-stu-id="a3f69-455">**ownershipName:** Unique name of owner/responsible party.</span></span>
- <span data-ttu-id="a3f69-456">**ownershipDescription:** 所有者/責任者の説明。</span><span class="sxs-lookup"><span data-stu-id="a3f69-456">**ownershipDescription:** Description of the owner/responsible party.</span></span>

#### <a name="dimensions-tab"></a><span data-ttu-id="a3f69-457">[ディメンション] タブ</span><span class="sxs-lookup"><span data-stu-id="a3f69-457">Dimensions tab</span></span>

<span data-ttu-id="a3f69-458">このタブには、アクションに関連付けることができるディメンションを定義する列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-458">This tab includes columns that define the Dimensions that can be associated with an Action.</span></span>  <span data-ttu-id="a3f69-459">このタブの列は、次に示す順序で Excel 内で並べ替えられるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-459">The columns for this tab, which must be ordered within Excel in the order listed below, are:</span></span>

- <span data-ttu-id="a3f69-460">**Dimensionkey:** 次元で使用されるキーの一覧です。</span><span class="sxs-lookup"><span data-stu-id="a3f69-460">**dimensionKey:** List of Keys used for Dimensions.</span></span> <span data-ttu-id="a3f69-461">たとえば、製品、証明書など。</span><span class="sxs-lookup"><span data-stu-id="a3f69-461">For example, Product, Certification, etc.</span></span>
- <span data-ttu-id="a3f69-462">**Dimensionvalue:** 各次元キーの一意の値。</span><span class="sxs-lookup"><span data-stu-id="a3f69-462">**dimensionValue:** Unique value for each dimension key.</span></span> <span data-ttu-id="a3f69-463">たとえば、Office 365、Intune、Azure、カスタム製品など。</span><span class="sxs-lookup"><span data-stu-id="a3f69-463">For example, Office 365, Intune, Azure, Custom Product, etc.</span></span>
- <span data-ttu-id="a3f69-464">**allowmultiselect**の場合:TRUE または FALSE を使用して、1つのディメンションキーに対して複数の次元の値を選択できることを示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-464">**allowMultiSelect:** Use TRUE or FALSE to indicate that multiple dimension values can be selected for a single dimension key.</span></span>

#### <a name="using-markdown-language-in-description-fields"></a><span data-ttu-id="a3f69-465">説明フィールドで Markdown Language を使用する</span><span class="sxs-lookup"><span data-stu-id="a3f69-465">Using Markdown Language in Description Fields</span></span>

<span data-ttu-id="a3f69-466">テンプレートと評価では、一部のテキスト要素と書式設定に対して Markdown language の使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-466">Templates and Assessments support the use of Markdown language for some text elements and formatting.</span></span>  <span data-ttu-id="a3f69-467">コンプライアンスマネージャーで使用される Markdown 言語の3つの書式設定要素があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-467">There are three formatting elements of Markdown language that are used in Compliance Manager:</span></span>

- <span data-ttu-id="a3f69-468">箇条書きと段落番号</span><span class="sxs-lookup"><span data-stu-id="a3f69-468">Bullets and Numbered lists</span></span>
- <span data-ttu-id="a3f69-469">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="a3f69-469">Hyperlinks</span></span>
- <span data-ttu-id="a3f69-470">太字</span><span class="sxs-lookup"><span data-stu-id="a3f69-470">Boldface</span></span>

<span data-ttu-id="a3f69-471">行頭文字は、Word または Excel の行頭文字ではなく、アスタリスクで表されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-471">Bullets are represented as asterisks instead of Word or Excel bullets.</span></span> <span data-ttu-id="a3f69-472">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-472">For example:</span></span>

```
* Item A
* Item B
* Item C
```

<span data-ttu-id="a3f69-473">数字は数字として表されますが、インデントにスペースが含まれ (1 レベルに3スペース)、すべてのサブレベルで使用される数値のみ (たとえば、文字なし) になります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-473">Numbers are represented as numbers, but with spaces for indentation (three spaces per level) and only numbers used for all sublevels (for example, no letters).</span></span>  <span data-ttu-id="a3f69-474">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-474">For example:</span></span>
   1. <span data-ttu-id="a3f69-475">アイテム A</span><span class="sxs-lookup"><span data-stu-id="a3f69-475">Item A</span></span>
   2. <span data-ttu-id="a3f69-476">アイテム B</span><span class="sxs-lookup"><span data-stu-id="a3f69-476">Item B</span></span>
      1. <span data-ttu-id="a3f69-477">サブアイテム A</span><span class="sxs-lookup"><span data-stu-id="a3f69-477">Sub-item A</span></span>
      2. <span data-ttu-id="a3f69-478">サブアイテム B</span><span class="sxs-lookup"><span data-stu-id="a3f69-478">Sub-item B</span></span>
   3. <span data-ttu-id="a3f69-479">アイテム C</span><span class="sxs-lookup"><span data-stu-id="a3f69-479">Item C</span></span>
   4. <span data-ttu-id="a3f69-480">アイテム D</span><span class="sxs-lookup"><span data-stu-id="a3f69-480">Item D</span></span>
      1. <span data-ttu-id="a3f69-481">サブアイテム A</span><span class="sxs-lookup"><span data-stu-id="a3f69-481">Sub-item A</span></span>
      2. <span data-ttu-id="a3f69-482">サブアイテム B</span><span class="sxs-lookup"><span data-stu-id="a3f69-482">Sub-item B</span></span>
   5. <span data-ttu-id="a3f69-483">アイテム E</span><span class="sxs-lookup"><span data-stu-id="a3f69-483">Item E</span></span>

<span data-ttu-id="a3f69-484">ハイパーリンクを構成するには、ハイパーリンクテキストをかっこで囲み、角かっこの直後にハイパーリンク自体をかっこで囲んで記述します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-484">Hyperlinks are constructed by placing brackets around the hyperlink text and the hyperlink itself in parentheses immediately next to the close bracket.</span></span>  <span data-ttu-id="a3f69-485">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-485">For example:</span></span>

```
Click [here](https://www.microsoft.com) to go to Microsoft’s home page.
```
<span data-ttu-id="a3f69-486">このテキストは、次のようにレンダリングされます。 Microsoft のホームページに移動するに[は、ここ](https://www.microsoft.com)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-486">This text renders as follows:  Click [here](https://www.microsoft.com) to go to Microsoft’s home page.</span></span>
<span data-ttu-id="a3f69-487">上記の例のように、コンプライアンスマネージャーは、下線付きの Url を表示しません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-487">As shown in the above example, Compliance Manager does not render URLs with underlining.</span></span>

<span data-ttu-id="a3f69-488">太字のテキストは、太字で表示されるテキストの各側に2つのアスタリスクがあるだけです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-488">Boldface text is just two asterisks on each side of the text to be bolded.</span></span>  <span data-ttu-id="a3f69-489">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-489">For example:</span></span>

```
**This text will render in bold**
```
<span data-ttu-id="a3f69-490">**このテキストは太字で表示される**</span><span class="sxs-lookup"><span data-stu-id="a3f69-490">**This text renders in bold**</span></span>

### <a name="create-a-template"></a><span data-ttu-id="a3f69-491">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="a3f69-491">Create a Template</span></span>

<span data-ttu-id="a3f69-492">テンプレートを作成するには、既存のテンプレートをコピーするか、Excel からテンプレートデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a3f69-492">You can create a Template by copying an existing Template or by importing Template data from Excel.</span></span> <span data-ttu-id="a3f69-493">Excel からデータをインポートする場合、このテンプレートには、2つの異なるコンプライアンスマネージャー管理者がデータを発行する必要があります (1 つは発行し、もう1つは承認するため)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-493">When importing data from Excel, the Template requires two different Compliance Manager Administrators to publish the data (one to publish, and one to approve).</span></span>

#### <a name="create-a-template-by-copying-an-existing-template"></a><span data-ttu-id="a3f69-494">既存のテンプレートをコピーしてテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="a3f69-494">Create a Template by copying an existing Template</span></span>

1. <span data-ttu-id="a3f69-495">**テンプレート**ダッシュボードを開き、[ **+ テンプレートの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-495">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="a3f69-496">[**テンプレート名の入力**] フィールドに、テンプレートの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-496">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="a3f69-497">[**既存のテンプレートからコピー**する] チェックボックスをオンにして、ドロップダウンからコピーするテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-497">Check the **Copy from an existing template** checkbox and select the template you want to copy from the dropdown.</span></span>
4. <span data-ttu-id="a3f69-498">必要に応じて、追加のディメンションを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-498">Optionally add any additional Dimensions.</span></span>
5. <span data-ttu-id="a3f69-499">[**ダッシュボードに追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-499">Select **Add to Dashboard**.</span></span>

#### <a name="create-a-template-by-importing-data"></a><span data-ttu-id="a3f69-500">データをインポートすることでテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="a3f69-500">Create a Template by importing data</span></span>

1. <span data-ttu-id="a3f69-501">**テンプレート**ダッシュボードを開き、[ **+ テンプレートの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-501">Open the **Templates** dashboard and select **+ Add Template**.</span></span>
2. <span data-ttu-id="a3f69-502">[**テンプレート名の入力**] フィールドに、テンプレートの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-502">In the **Enter template name** field, provide a unique name for the Template.</span></span>
3. <span data-ttu-id="a3f69-503">利用可能なリストから少なくとも1つのディメンションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-503">Select at least one Dimension from the available list.</span></span>
4. <span data-ttu-id="a3f69-504">[**参照**] を選択して、インポートファイルの場所に移動し、それを選択して、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-504">Select **Browse** to navigate to the location of the import file, select it, and select **Open**.</span></span>
5. <span data-ttu-id="a3f69-505">インポートファイルが検証され、検出されたコントロールとコントロールファミリの数が示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-505">The import file will be validated and indicate the number of controls and control families that were detected.</span></span> <span data-ttu-id="a3f69-506">エラーがある場合は、エラーの詳細を含む、変更されたバージョンのインポートファイルにリンクが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-506">If there are errors, a link will be provided to a modified version of the import file that includes error details.</span></span> <span data-ttu-id="a3f69-507">データをインポートする前に、すべてのエラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-507">All errors must be resolved before the data will be imported.</span></span>
6. <span data-ttu-id="a3f69-508">データが検証に合格したら、[**ダッシュボードに追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-508">Once the data passes validation, select **Add to Dashboard**.</span></span>
7. <span data-ttu-id="a3f69-509">インポートされたテンプレートは**テンプレート**ダッシュボードに表示され、状態は [**インポート**済み] になります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-509">The imported Template appears on the **Templates** dashboard and it has a status of **Imported**.</span></span> <span data-ttu-id="a3f69-510">省略記号 ([...]) を選択し、[**発行**] を選択してテンプレートを発行します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-510">Select the ellipses (…) and select **Publish** to publish the Template.</span></span> <span data-ttu-id="a3f69-511">確認メッセージが表示されたら、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-511">When the confirmation message appears, select **Publish**.</span></span> <span data-ttu-id="a3f69-512">テンプレートの状態が [**承認待ち**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-512">The Template status changes to **Pending Approval**.</span></span>
8. <span data-ttu-id="a3f69-513">コンプライアンスマネージャー管理者の役割を持つ別のユーザーは、テンプレートダッシュボードでテンプレートを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-513">Another user with the Compliance Manager Administrator role must approve the Template in the Templates dashboard.</span></span> <span data-ttu-id="a3f69-514">省略記号 (...) を選択して、[**承認**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-514">They must select the ellipses (…) and select **Approve**.</span></span> <span data-ttu-id="a3f69-515">確認メッセージが表示されたら、[**承認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-515">When the confirmation message appears, select **Approve**.</span></span> <span data-ttu-id="a3f69-516">これで、テンプレートを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a3f69-516">The Template is now ready for use.</span></span>

### <a name="customize-a-template"></a><span data-ttu-id="a3f69-517">テンプレートをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="a3f69-517">Customize a Template</span></span>

<span data-ttu-id="a3f69-518">テンプレートは、カスタムコントロールの追加によってカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-518">Templates can be customized through the additional of custom controls.</span></span> <span data-ttu-id="a3f69-519">すべてのカスタムコントロールは、顧客が管理するコントロールと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-519">All custom controls are considered customer-managed Controls.</span></span>

#### <a name="add-a-custom-control-to-a-template"></a><span data-ttu-id="a3f69-520">テンプレートにカスタムコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a3f69-520">Add a custom control to a Template</span></span>

1. <span data-ttu-id="a3f69-521">変更する**テンプレート**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-521">Open the **Template** you want to modify.</span></span>
2. <span data-ttu-id="a3f69-522">[ **+** カスタムコントロールの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-522">Select **+ Add** custom control.</span></span>
3. <span data-ttu-id="a3f69-523">ドロップダウンから**コントロールファミリー**を選択するか、存在しない場合は新しいコントロールファミリーを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-523">Select a **Control Family** from the dropdown or enter a new control family if it does not exist.</span></span>
4. <span data-ttu-id="a3f69-524">コントロール**id**フィールドに、コントロールの一意の名前または id を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-524">Provide a unique name or ID for the control in the **Control ID** field.</span></span>
5. <span data-ttu-id="a3f69-525">[**タイトル**] フィールドにコントロールのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-525">Provide the control title in the **Title** field.</span></span>
6. <span data-ttu-id="a3f69-526">[**説明**] フィールドに、コントロールの要件およびその他の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-526">Provide the requirements and other information for the control in the **Description** field.</span></span>
7. <span data-ttu-id="a3f69-527">[**顧客**にアクションを割り当てる] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-527">Select **Assign Customer** Action.</span></span>
8. <span data-ttu-id="a3f69-528">コントロールに割り当てるアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-528">Locate the Action(s) you want to assign to the control:</span></span>
    - <span data-ttu-id="a3f69-529">[**ディメンションでフィルター** ] を使用して、アクションに割り当てられたディメンションを使用して、それらを検索して表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-529">Use **Filter by Dimension** to use dimensions assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="a3f69-530">**所有者によるフィルター**を使用して、アクションに割り当てられている所有者を検索して一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-530">Use **Filter by Owner** to use the owner(s) assigned to the Action(s) to locate and list them.</span></span>
    - <span data-ttu-id="a3f69-531">ドロップダウンから**アクションの種類**を選択して、種類別にアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-531">Select an **Action Type** from the dropdown to list Actions by type.</span></span>
    - <span data-ttu-id="a3f69-532">検索して一覧表示するアクションのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-532">Enter the title of the Action to locate and list it.</span></span>
9. <span data-ttu-id="a3f69-533">手順8の条件を使用すると、**一致するアクション**の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-533">Using the criteria in Step 8, a list of **Matching Action(s)** will appear.</span></span> <span data-ttu-id="a3f69-534">コントロールに割り当てる最初のアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-534">Select the first Action you want to assign to the control.</span></span>
10. <span data-ttu-id="a3f69-535">アクションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-535">The details of the Action appear.</span></span> <span data-ttu-id="a3f69-536">使用する**説明**を選択し、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-536">Select the **Description** you want to use and select **Done**.</span></span>
11. <span data-ttu-id="a3f69-537">割り当てる追加のアクションごとに、手順9と10を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-537">Repeat Steps 9 and 10 for each additional Action you want to assign.</span></span>
12. <span data-ttu-id="a3f69-538">該当するすべてのアクションを選択したら、[**割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-538">When all applicable Actions have been selected, select **Assign**.</span></span>
13. <span data-ttu-id="a3f69-539">[**保存**] を選択して、新しいコントロールを保存します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-539">Select **Save** to save the new control.</span></span>

### <a name="export-a-template-to-json"></a><span data-ttu-id="a3f69-540">JSON にテンプレートをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a3f69-540">Export a Template to JSON</span></span>

<span data-ttu-id="a3f69-541">また、コンプライアンスマネージャー (プレビュー) は、テンプレートを JavaScript Object Notation (JSON) 形式にエクスポートすることもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-541">Compliance Manager (Preview) also supports exporting Templates to JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="a3f69-542">これにより、コンプライアンスマネージャーのデータを JSON をサポートする他のシステムと交換することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-542">This enables you to exchange Compliance Manager data with other systems that support JSON.</span></span>

## <a name="reports"></a><span data-ttu-id="a3f69-543">レポート</span><span class="sxs-lookup"><span data-stu-id="a3f69-543">Reports</span></span>

<span data-ttu-id="a3f69-544">組織内のコンプライアンスステークホルダーまたは外部の監査者や規制機関の評価を Excel ファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-544">You can export an Assessment to an Excel file for compliance stakeholders in your organization or for external auditors and regulators.</span></span> <span data-ttu-id="a3f69-545">レポートは、エクスポートの日時の時点での評価のスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="a3f69-545">The report is a snapshot of the Assessment as of the date and time of the export.</span></span> <span data-ttu-id="a3f69-546">このレポートには、評価のための Microsoft およびお客様が管理する統制の詳細、コントロールの実装状態、コントロールのテスト日、テスト結果、アップロードされた証拠ドキュメントへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-546">The report contains the details for Microsoft and customer-managed controls for the Assessment, control implementation status, control test date, test results, and links to uploaded evidence documents.</span></span> <span data-ttu-id="a3f69-547">アーカイブされた評価はアップロードされたドキュメントへのリンクを保持しないので、アーカイブの前に評価をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3f69-547">You should export Assessments before archiving them because archived Assessments do not retain links to uploaded documents.</span></span>

### <a name="export-an-assessment"></a><span data-ttu-id="a3f69-548">評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a3f69-548">Export an Assessment</span></span>

1. <span data-ttu-id="a3f69-549">コンプライアンスマネージャーダッシュボードで、[**コントロールの情報**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-549">On the Compliance Manager dashboard, select **Controls Info** tab.</span></span>
2. <span data-ttu-id="a3f69-550">エクスポートする評価のドロップダウンメニューで、グループと評価を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-550">Select the Group and Assessment in the dropdown menus for the Assessment you want to export.</span></span>
3. <span data-ttu-id="a3f69-551">[エクスポート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-551">Select Export.</span></span> <span data-ttu-id="a3f69-552">評価エクスポートは、Excel ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-552">The Assessment export is downloaded as an Excel file.</span></span>

![コンプライアンスマネージャー評価 Excel レポート](media/compliance-manager-assessment-report.png)

## <a name="permissions"></a><span data-ttu-id="a3f69-554">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a3f69-554">Permissions</span></span>

<span data-ttu-id="a3f69-555">次の表では、各コンプライアンスマネージャーのアクセス許可と、ユーザーが実行できる操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3f69-555">The following table describes each Compliance Manager permission and what it allows the user do.</span></span> <span data-ttu-id="a3f69-556">この表は、各アクセス許可が割り当てられている役割も示しています。</span><span class="sxs-lookup"><span data-stu-id="a3f69-556">The table also indicates the role that each permission is assigned.</span></span>

||<span data-ttu-id="a3f69-557">**コンプライアンス マネージャー リーダー**</span><span class="sxs-lookup"><span data-stu-id="a3f69-557">**Compliance Manager Reader**</span></span>|<span data-ttu-id="a3f69-558">**コンプライアンス マネージャー投稿者**</span><span class="sxs-lookup"><span data-stu-id="a3f69-558">**Compliance Manager Contributor**</span></span>|<span data-ttu-id="a3f69-559">**コンプライアンス マネージャー評価者**</span><span class="sxs-lookup"><span data-stu-id="a3f69-559">**Compliance Manager Assessor**</span></span>|<span data-ttu-id="a3f69-560">**コンプライアンス マネージャー管理者**</span><span class="sxs-lookup"><span data-stu-id="a3f69-560">**Compliance Manager Administrator**</span></span>|<span data-ttu-id="a3f69-561">**ポータル管理者**</span><span class="sxs-lookup"><span data-stu-id="a3f69-561">**Portal Admin**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3f69-562">**データの読み取り:** ユーザーは、データの読み取りはできますが、編集はできません (テンプレートデータおよびテナント管理を除く)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-562">**Read data:** Users can read but not edit data (except for Template data and Tenant Management).</span></span>  <br> | <span data-ttu-id="a3f69-563">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-563">X</span></span> | <span data-ttu-id="a3f69-564">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-564">X</span></span> | <span data-ttu-id="a3f69-565">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-565">X</span></span> | <span data-ttu-id="a3f69-566">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-566">X</span></span>  | <span data-ttu-id="a3f69-567">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-567">X</span></span> |
|<span data-ttu-id="a3f69-568">**データの編集:** ユーザーは、テスト結果とテスト日付フィールド (テンプレートデータおよびテナント管理を除く) を除くすべてのフィールドを編集できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-568">**Edit data:** Users can edit all fields, except the Test Result and Test Date fields (except for Template data and Tenant Management).</span></span>  <br> || <span data-ttu-id="a3f69-569">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-569">X</span></span> | <span data-ttu-id="a3f69-570">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-570">X</span></span>  | <span data-ttu-id="a3f69-571">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-571">X</span></span> | <span data-ttu-id="a3f69-572">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-572">X</span></span> |
|<span data-ttu-id="a3f69-573">**テスト結果を編集します。** ユーザーは、テスト結果とテスト日付フィールドを編集できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-573">**Edit test results:** Users can edit the Test Result and Test Date fields.</span></span>  <br> ||| <span data-ttu-id="a3f69-574">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-574">X</span></span> | <span data-ttu-id="a3f69-575">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-575">X</span></span> | <span data-ttu-id="a3f69-576">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-576">X</span></span> |
|<span data-ttu-id="a3f69-577">**評価の管理:** ユーザーは評価を作成、アーカイブ、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-577">**Manage assessments:** Users can create, archive, and delete Assessments.</span></span>  <br> |||| <span data-ttu-id="a3f69-578">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-578">X</span></span> | <span data-ttu-id="a3f69-579">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-579">X</span></span> |
|<span data-ttu-id="a3f69-580">**マスタデータを管理します。** ユーザーは、テンプレートデータおよびテナント管理データを表示、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-580">**Manage master data:** Users can view, edit, and delete template data and tenant management data.</span></span>  <br> |||| <span data-ttu-id="a3f69-581">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-581">X</span></span> | <span data-ttu-id="a3f69-582">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-582">X</span></span> |
|<span data-ttu-id="a3f69-583">**ユーザーを管理する:** ユーザーは、組織内の他のユーザーを閲覧者、投稿者、査定人、および管理者の役割に追加できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-583">**Manage users:** Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles.</span></span> <span data-ttu-id="a3f69-584">組織内のグローバル管理者の役割を持つユーザーのみが、ポータル管理者の役割に対してユーザーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-584">Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.</span></span>  <br> ||||| <span data-ttu-id="a3f69-585">X</span><span class="sxs-lookup"><span data-stu-id="a3f69-585">X</span></span> |

### <a name="guest-access"></a><span data-ttu-id="a3f69-586">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="a3f69-586">Guest access</span></span>
  
<span data-ttu-id="a3f69-587">コンプライアンスマネージャーへのアクセスが構成されると、既定では、準備された役割を持たないユーザーはすべて**ゲストアクセス**の役割になります (これは、個人の Microsoft アカウントなど、組織でプロビジョニングされていないアカウントの場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="a3f69-587">After Compliance Manager access is configured, any user that does not have a provisioned role is in the **Guest access** role by default (which is also the experience of any non-organization-provisioned accounts like personal Microsoft Accounts).</span></span> <span data-ttu-id="a3f69-588">ゲストアクセスユーザーには、コンプライアンスマネージャーのすべての機能へのフルアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="a3f69-588">Guest Access users do not have full access to all Compliance Manager features.</span></span> <span data-ttu-id="a3f69-589">組織のコンプライアンス評価データを表示することはできませんが、コンプライアンスマネージャーを使用して、Microsoft のコンプライアンス評価レポートとサービス信頼ドキュメントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a3f69-589">They are not able to see any of the organization's compliance assessment data, however they are able to use Compliance Manager to view Microsoft's compliance assessment reports and Service Trust documents.</span></span>