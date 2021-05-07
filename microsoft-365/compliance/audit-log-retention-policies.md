---
title: 監査ログの保持ポリシーを管理する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 監査ログの保持ポリシーは、Microsoft 365 の新しい高度な監査機能の一部です。 監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。
ms.openlocfilehash: 2ac95d9bb9c13b6bf0c0e31d17b4fb46c30c492a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687360"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="43964-104">監査ログの保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="43964-104">Manage audit log retention policies</span></span>

<span data-ttu-id="43964-105">セキュリティ/コンプライアンス センターで監査ログの保持ポリシーを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="43964-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="43964-106">監査ログの保持ポリシーは、Microsoft 365 の新しい高度な監査機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="43964-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="43964-107">監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="43964-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="43964-108">監査ログは、最大 10 年間保持できます。</span><span class="sxs-lookup"><span data-stu-id="43964-108">You can retain audit logs for up to 10 years.</span></span> <span data-ttu-id="43964-109">次の条件を基にしてポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="43964-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="43964-110">1 つまたは複数の Microsoft 365 サービスのすべてのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="43964-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="43964-111">すべてのユーザーまたは特定のユーザーによって実行された (Microsoft 365 サービス内の) 特定のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="43964-111">Specific activities (in a Microsoft 365 service) performed by all users or by specific users</span></span>

- <span data-ttu-id="43964-112">優先度レベルは、組織内に複数のポリシーがある場合に、どのポリシーが優先されるかを指定する</span><span class="sxs-lookup"><span data-stu-id="43964-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="43964-113">既定の監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="43964-113">Default audit log retention policy</span></span>

<span data-ttu-id="43964-114">Microsoft 365 の高度な監査には、すべての組織の既定の監査ログの保持ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="43964-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="43964-115">このポリシーは、Exchange Online、SharePoint Online、OneDrive for Business、および Azure Active Directory のすべての監査レコードを 1 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="43964-115">This policy retains all Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="43964-116">この既定のポリシーは、**Workload** プロパティ (アクティビティが発生したサービス) の **Exchange**、**SharePoint**、**OneDrive**、**AzureActiveDirectory** の値を含む監査レコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="43964-116">This default policy retains audit records that contain the value of **Exchange**, **SharePoint**, **OneDrive**, **AzureActiveDirectory** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="43964-117">既定のポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="43964-117">The default policy can't be modified.</span></span> <span data-ttu-id="43964-118">既定のポリシーに含まれている各ワークロードのレコード種類の一覧については、この記事の「[詳細情報](#more-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43964-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="43964-119">既定の監査ログの保持ポリシーは、Office 365 または Microsoft 365 E5 ライセンスが割り当てられているユーザー、または Microsoft 365 E5 コンプライアンスまたは Microsoft 365 E5 eDiscovery and Audit アドオン ライセンスを持つユーザーが実行したアクティビティの監査レコードにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="43964-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="43964-120">組織に E5 以外のユーザーまたはゲスト ユーザーがいる場合、こうしたユーザーに対応する監査レコードは 90 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="43964-120">If you have non-E5 users or guest users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="43964-121">監査ログの保持ポリシーを作成する前に</span><span class="sxs-lookup"><span data-stu-id="43964-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="43964-122">監査保持ポリシーを作成または変更するには、セキュリティ/コンプライアンス センターの組織構成の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="43964-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="43964-123">組織では、最大 50 個の監査ログの保持ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="43964-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="43964-124">監査ログを 90 日以上 (最大 1 年) 保持するには、(監査されるアクティビティの実行により) 監査ログを生成したユーザーに Office 365 E5 または Microsoft 365 E5 ライセンスを割り当てるか、または Microsoft 365 E5 Compliance または E5 eDiscovery および監査アドオン ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="43964-124">To retain an audit log for longer than 90 days (and up to 1 year), the user who generates the audit log (by performing an audited activity) must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="43964-125">監査ログを 10 年間保持するには、監査ログを生成するユーザーに対して、E5 ライセンスに加えて、10 年間の監査ログ保持のアドオン ライセンスも割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="43964-125">To retain audit logs for 10 years, the user who generates the audit log must also be assigned a 10-year audit log retention add-on license in addition to an E5 license.</span></span>

- <span data-ttu-id="43964-126">組織によって作成されるすべてのカスタム監査ログの保持ポリシーは、既定の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="43964-126">All custom audit log retention policies (created by your organization) take priority over the default retention policy.</span></span> <span data-ttu-id="43964-127">たとえば、保持期間が 1 年未満の Exchange メールボックス アクティビティに対して監査ログの保持ポリシーを作成すると、Exchange メールボックス アクティビティの監査レコードは、カスタム ポリシーで指定されている短い期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="43964-127">For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy"></a><span data-ttu-id="43964-128">PowerShell で監査ログの保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="43964-128">Create an audit log retention policy</span></span>

1. <span data-ttu-id="43964-129">[https://compliance.microsoft.com](https://compliance.microsoft.com) に移動し、セキュリティ/コンプライアンス センターの [アクセス許可] ページで組織構成の役割が割り当てられているユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="43964-129">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that's assigned the Organization Configuration role on the Permissions page in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="43964-130">Microsoft 365 コンプライアンス センターの左側のウィンドウで、[**すべてを表示**] をクリックし、[**監査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43964-130">In the left pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

3. <span data-ttu-id="43964-131">**[監査保持ポリシー]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="43964-131">Click the **Audit retention policies** tab.</span></span>

4. <span data-ttu-id="43964-132">[**監査保持ポリシーの作成**] をクリックし、ポップアップ ページの次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="43964-132">Click **Create audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![新しい監査保持ポリシーのポップアップ ページ](../media/CreateAuditLogRetentionPolicy.png)

   1. <span data-ttu-id="43964-134">**ポリシー名:** 監査ログの保持ポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="43964-134">**Policy name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="43964-135">この名前は組織内で一意である必要があり、ポリシーの作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="43964-135">This name must be unique in your organization, and it can't be change after the policy is created.</span></span>

   2. <span data-ttu-id="43964-136">**説明:** 省略可能ですが、レコードの種類やワークロード、ポリシーで指定されたユーザー、期間など、ポリシーに関する情報を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43964-136">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   3. <span data-ttu-id="43964-137">**ユーザー:** ポリシーを適用する 1 人以上のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="43964-137">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="43964-138">このボックスを空白のままにすると、ポリシーがすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="43964-138">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="43964-139">**レコードの種類** を空白のままにする場合は、ユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43964-139">If you leave the **Record type** blank, then you must select a user.</span></span>

   4. <span data-ttu-id="43964-140">**レコードの種類:** ポリシーの適用対象となる監査レコードの種類です。</span><span class="sxs-lookup"><span data-stu-id="43964-140">**Record type:** The audit record type the policy applies to.</span></span> <span data-ttu-id="43964-141">このプロパティを空白のままにする場合は、[**ユーザー**] ボックスでユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43964-141">If you leave this property blank, you must select a user in the **Users** box.</span></span> <span data-ttu-id="43964-142">1 つまたは複数のレコードの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="43964-142">You can select a single record type or multiple record types:</span></span>

   - <span data-ttu-id="43964-143">単一のレコードの種類を選択した場合は、[**アクティビティ**] フィールドが動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="43964-143">If you select a single record type, the **Activities** field is dynamically displayed.</span></span> <span data-ttu-id="43964-144">ドロップダウン リストを使用して、選択したレコードの種類からポリシーを適用するアクティビティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="43964-144">You can use the drop-down list to select activities from the selected record type to apply the policy to.</span></span> <span data-ttu-id="43964-145">特定のアクティビティを選択しない場合は、選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="43964-145">If you don't choose specific activities, the policy will apply to all activities of the selected record type.</span></span>

   - <span data-ttu-id="43964-146">複数のレコードの種類を選択した場合、アクティビティを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="43964-146">If you select multiple record types, you don't have the ability to select activities.</span></span> <span data-ttu-id="43964-147">選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="43964-147">The policy will apply to all activities of the selected record types.</span></span>

   5. <span data-ttu-id="43964-148">**期間:** ポリシーの条件を満たす監査ログの保持期間です。</span><span class="sxs-lookup"><span data-stu-id="43964-148">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   6. <span data-ttu-id="43964-149">**ポリシー:** この値は、組織内の監査ログの保持ポリシーが処理される順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="43964-149">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="43964-150">値が高いほど、高い優先度を示します。</span><span class="sxs-lookup"><span data-stu-id="43964-150">A higher value indicates a higher priority.</span></span> <span data-ttu-id="43964-151">たとえば、優先度の値が **5** のポリシーは、優先度の値が **0** のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="43964-151">For example, a policy with a priority value of **5** would take priority over a policy with a priority value of **0**.</span></span> <span data-ttu-id="43964-152">前述のとおり、カスタム監査ログの保持ポリシーは、組織の既定ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="43964-152">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

5. <span data-ttu-id="43964-153">[**保存**] をクリックして新しい監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="43964-153">Click **Save** to create the new audit log retention policy.</span></span>

   <span data-ttu-id="43964-154">新しいポリシーは、**[監査保持ポリシー]** タブの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="43964-154">The new policy is displayed in the list on the **Audit retention policies** tab.</span></span>

## <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="43964-155">監査ログの保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="43964-155">Manage audit log retention policies</span></span>

<span data-ttu-id="43964-156">監査ログの保持ポリシーは、**[監査保持ポリシー]** タブ (*ダッシュボード* とも呼ばれる) に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="43964-156">Audit log retention policies are listed on the **Audit retention policies** tab (also called the *dashboard*).</span></span> <span data-ttu-id="43964-157">ダッシュボードを使用して、監査保持ポリシーを表示、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="43964-157">You can use the dashboard to view, edit, and delete audit retention policies.</span></span>

### <a name="view-policies-in-the-dashboard"></a><span data-ttu-id="43964-158">ダッシュボードでポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="43964-158">View policies in the dashboard</span></span>

<span data-ttu-id="43964-159">監査ログの保持ポリシーはダッシュボードに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="43964-159">Audit log retention policies are listed in the dashboard.</span></span> <span data-ttu-id="43964-160">ダッシュボードにポリシーを表示する利点の 1 つは、**[優先度]** 列をクリックして、ポリシーが適用されている優先度のポリシーを一覧表示できることです。</span><span class="sxs-lookup"><span data-stu-id="43964-160">One advantage of viewing policies in the dashboard is that you can click the **Priority** column to list the policies in the priority in which they are applied.</span></span> <span data-ttu-id="43964-161">前に説明したように、値が高いほど、高い優先度を示します。</span><span class="sxs-lookup"><span data-stu-id="43964-161">As previously explained, a higher value indicates a higher priority.</span></span>

![監査保持ポリシー ダッシュボードの [優先度] 列](../media/AuditLogRetentionDashboardPriority.png)

<span data-ttu-id="43964-163">また、ポリシーを選択して、その設定をポップアップ ページに表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="43964-163">You can also select a policy to display its settings on the flyout page.</span></span>

> [!NOTE]
> <span data-ttu-id="43964-164">組織の既定の監査ログの保持ポリシーはダッシュボードに表示されません。</span><span class="sxs-lookup"><span data-stu-id="43964-164">The default audit log retention policy for your organization isn't displayed in the dashboard.</span></span>

### <a name="edit-policies-in-the-dashboard"></a><span data-ttu-id="43964-165">ダッシュボードでポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="43964-165">Edit policies in the dashboard</span></span>

<span data-ttu-id="43964-166">ポリシーを編集するには、ポリシーを選択してポップアップ ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="43964-166">To edit a policy, select it to display the flyout page.</span></span> <span data-ttu-id="43964-167">1 つ以上の設定を変更してから、変更を保存できます。</span><span class="sxs-lookup"><span data-stu-id="43964-167">You can modify one or more setting and then save your changes.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="43964-168">**New-UnifiedAuditLogRetentionPolicy** コマンドレットを使用すると、ダッシュボードの **[監査保持ポリシーの作成]** ツールでは使用できないレコードの種類またはアクティビティの監査ログ保持ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="43964-168">If you use the **New-UnifiedAuditLogRetentionPolicy** cmdlet, it's possible to create an audit log retention policy for record types or activities that aren't available in the **Create audit retention policy** tool in the dashboard.</span></span> <span data-ttu-id="43964-169">この場合、**[監査保持ポリシー]** ダッシュボードからポリシーを編集 (保持期間の変更やアクティビティの追加と削除など) することはできません。</span><span class="sxs-lookup"><span data-stu-id="43964-169">In this case, you won't be able to edit the policy (for example, change the retention duration or add and remove activities) from the **Audit retention policies** dashboard.</span></span> <span data-ttu-id="43964-170">コンプライアンス センターでは、ポリシーを表示したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="43964-170">You'll only be able to view and delete the policy in the compliance center.</span></span> <span data-ttu-id="43964-171">ポリシーを編集するには、セキュリティ/コンプライアンス センターの PowerShell で [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="43964-171">To edit the policy, you'll have to use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell.</span></span><br/><br/><span data-ttu-id="43964-172">**ヒント:** PowerShell を使用して編集する必要があるポリシーのメッセージがポップアップ ページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="43964-172">**Tip:** A message is displayed at the top of the flyout page for policies that have to be edited using PowerShell.</span></span>

### <a name="delete-policies-in-the-dashboard"></a><span data-ttu-id="43964-173">ダッシュボードでポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="43964-173">Delete policies in the dashboard</span></span>

<span data-ttu-id="43964-174">ポリシーを削除するには、**[削除]** ![[削除] アイコン](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) アイコンをクリックし、その後ポリシーの削除を確定します。</span><span class="sxs-lookup"><span data-stu-id="43964-174">To delete a policy, click the **Delete** ![Delete icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) icon and then confirm that you want to delete the policy.</span></span> <span data-ttu-id="43964-175">ポリシーはダッシュボードから削除されますが、ポリシーが組織から削除されるまでに最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="43964-175">The policy is removed from the dashboard, but it might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="create-and-manage-audit-log-retention-policies-in-powershell"></a><span data-ttu-id="43964-176">PowerShell で監査ログの保持ポリシーを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="43964-176">Create and manage audit log retention policies in PowerShell</span></span>

<span data-ttu-id="43964-177">セキュリティ/コンプライアンス センターの PowerShell を使用して監査ログの保持ポリシーを作成して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="43964-177">You can also use Security & Compliance Center PowerShell to create and manage audit log retention policies.</span></span> <span data-ttu-id="43964-178">PowerShell を使用する理由の 1 つは、UI で使用できないレコードの種類またはアクティビティのポリシーを作成することです。</span><span class="sxs-lookup"><span data-stu-id="43964-178">One reason to use PowerShell is to create a policy for a record type or activity that isn't available in the UI.</span></span>

### <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="43964-179">PowerShell で監査ログの保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="43964-179">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="43964-180">PowerShell で監査ログの保持ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43964-180">Follow these steps to create an audit log retention policy in PowerShell:</span></span>

1. <span data-ttu-id="43964-181">[セキュリティ/コンプライアンス センター PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="43964-181">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="43964-182">次のコマンドを実行して監査ログの保持ポリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="43964-182">Run the following command to create an audit log retention policy.</span></span>

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    <span data-ttu-id="43964-183">この例では、次の設定を使用して「Microsoft Teams 監査ポリシー」という名前の監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="43964-183">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="43964-184">ポリシーの説明。</span><span class="sxs-lookup"><span data-stu-id="43964-184">A description of the policy.</span></span>

   - <span data-ttu-id="43964-185">Microsoft Teams のすべてのアクティビティ (*RecordType* パラメーターで定義) を保持します。</span><span class="sxs-lookup"><span data-stu-id="43964-185">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="43964-186">Microsoft Teams 監査ログを 10 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="43964-186">Retains Microsoft Teams audit logs for 10 years.</span></span>

   - <span data-ttu-id="43964-187">優先度が 100 の場合。</span><span class="sxs-lookup"><span data-stu-id="43964-187">A priority of 100.</span></span>

<span data-ttu-id="43964-188">監査ログの保持ポリシーを作成するもう 1 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="43964-188">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="43964-189">このポリシーには、ユーザー「admin@contoso.onmicrosoft.com」の 6 か月間の「ユーザー ログイン」アクティビティの監査ログが保持されます。</span><span class="sxs-lookup"><span data-stu-id="43964-189">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="43964-190">詳細については、「[New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43964-190">For more information, see [New-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

### <a name="view-policies-in-powershell"></a><span data-ttu-id="43964-191">PowerShell でポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="43964-191">View policies in PowerShell</span></span>

<span data-ttu-id="43964-192">セキュリティ/コンプライアンス センターの PowerShell で [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) コマンドレットを使用して、監査ログの保持ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="43964-192">Use the [Get-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/get-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to view audit log retention policies.</span></span>

<span data-ttu-id="43964-193">組織においてすべての監査ログの保持ポリシーの設定を表示するコマンドの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="43964-193">Here's a sample command to display the settings for all audit log retention policies in your organization.</span></span> <span data-ttu-id="43964-194">このコマンドを実行すると、ポリシーが優先度の高い順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="43964-194">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="43964-195">**Get-UnifiedAuditLogRetentionPolicy** コマンドレットは、組織の既定の監査ログの保持ポリシーを返しません。</span><span class="sxs-lookup"><span data-stu-id="43964-195">The **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log retention policy for your organization.</span></span>

### <a name="edit-policies-in-powershell"></a><span data-ttu-id="43964-196">PowerShell でポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="43964-196">Edit policies in PowerShell</span></span>

<span data-ttu-id="43964-197">セキュリティ/コンプライアンス センターの PowerShell で[Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) コマンドレットを使用して、既存の監査ログの保持ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="43964-197">Use the [Set-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/set-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to edit an existing audit log retention policy.</span></span>

### <a name="delete-policies-in-powershell"></a><span data-ttu-id="43964-198">PowerShell でポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="43964-198">Delete policies in PowerShell</span></span>

<span data-ttu-id="43964-199">セキュリティ/コンプライアンス センターの PowerShell で[Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) コマンドレットを使用して、監査ログの保持ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="43964-199">Use the [Remove-UnifiedAuditLogRetentionPolicy](/powershell/module/exchange/remove-unifiedauditlogretentionpolicy) cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="43964-200">組織からポリシーが削除されるまで、最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="43964-200">It might take up to 30 minutes for the policy to be removed from your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="43964-201">詳細情報</span><span class="sxs-lookup"><span data-stu-id="43964-201">More information</span></span>

<span data-ttu-id="43964-202">前述のように、Azure Active Directory、Exchange Online、SharePoint Online、および OneDrive for Business での運用に関する監査レコードは、既定で 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="43964-202">As previously stated, audit records for operations in Azure Active Directory, Exchange Online, SharePoint Online, and OneDrive for Business, are retained for one year by default.</span></span> <span data-ttu-id="43964-203">次の表に、既定の監査ログの保持ポリシーに含まれるすべてのレコードの種類 (これらのサービスごと) を示します。</span><span class="sxs-lookup"><span data-stu-id="43964-203">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="43964-204">つまり、特定のレコードの種類、動作、またはユーザーに対してカスタム監査ログの保持ポリシーが優先されない限り、このレコードの種類の動作の監査ログは 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="43964-204">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="43964-205">各レコードの種類の Enum 値 (監査レコード内の RecordType プロパティの値として表示される) はかっこ内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="43964-205">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

|<span data-ttu-id="43964-206">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="43964-206">AzureActiveDirectory</span></span> |<span data-ttu-id="43964-207">Exchange</span><span class="sxs-lookup"><span data-stu-id="43964-207">Exchange</span></span>  |<span data-ttu-id="43964-208">SharePoint または OneDrive</span><span class="sxs-lookup"><span data-stu-id="43964-208">SharePoint or OneDrive</span></span>|
|:---------|:---------|:---------|
|<span data-ttu-id="43964-209">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="43964-209">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="43964-210">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="43964-210">ExchangeAdmin (1)</span></span>|<span data-ttu-id="43964-211">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="43964-211">ComplianceDLPSharePoint (11)</span></span>|
|<span data-ttu-id="43964-212">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="43964-212">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="43964-213">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="43964-213">ExchangeItem (2)</span></span>|<span data-ttu-id="43964-214">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="43964-214">ComplianceDLPSharePointClassification (33)</span></span>|
|<span data-ttu-id="43964-215">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="43964-215">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="43964-216">Campaign (62)</span><span class="sxs-lookup"><span data-stu-id="43964-216">Campaign (62)</span></span>|<span data-ttu-id="43964-217">Project (35)</span><span class="sxs-lookup"><span data-stu-id="43964-217">Project (35)</span></span>|
||<span data-ttu-id="43964-218">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="43964-218">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="43964-219">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="43964-219">SharePoint (4)</span></span>|
||<span data-ttu-id="43964-220">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="43964-220">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="43964-221">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="43964-221">SharePointCommentOperation (37)</span></span>|
||<span data-ttu-id="43964-222">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="43964-222">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="43964-223">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="43964-223">SharePointContentTypeOperation (55)</span></span>|
||<span data-ttu-id="43964-224">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="43964-224">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="43964-225">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="43964-225">SharePointFieldOperation (56)</span></span>|
||<span data-ttu-id="43964-226">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="43964-226">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="43964-227">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="43964-227">SharePointFileOperation (6)</span></span>|
||<span data-ttu-id="43964-228">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="43964-228">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="43964-229">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="43964-229">SharePointListOperation (36)</span></span>|
||<span data-ttu-id="43964-230">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="43964-230">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="43964-231">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="43964-231">SharePointSharingOperation (14)</span></span>|
||||
