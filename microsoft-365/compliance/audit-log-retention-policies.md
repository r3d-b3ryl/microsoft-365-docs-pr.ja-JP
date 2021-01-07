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
ms.openlocfilehash: c2449ab90d04fd44909999d25b940ee4d2758b15
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753336"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="99d64-104">監査ログの保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="99d64-104">Manage audit log retention policies</span></span>

<span data-ttu-id="99d64-105">セキュリティ/コンプライアンス センターで監査ログの保持ポリシーを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="99d64-106">監査ログの保持ポリシーは、Microsoft 365 の新しい高度な監査機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="99d64-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="99d64-107">監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="99d64-108">監査ログは、最大 10 年間保持できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-108">You can retain audit logs for up to 10 years.</span></span> <span data-ttu-id="99d64-109">次の条件を基にしてポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="99d64-110">1 つまたは複数の Microsoft 365 サービスのすべてのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="99d64-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="99d64-111">すべてのユーザーまたは特定のユーザーによって実行された (Microsoft 365 サービス内の) 特定のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="99d64-111">Specific activities (in a Microsoft 365 service) performed by all users or by specific users</span></span>

- <span data-ttu-id="99d64-112">優先度レベルは、組織内に複数のポリシーがある場合に、どのポリシーが優先されるかを指定する</span><span class="sxs-lookup"><span data-stu-id="99d64-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="99d64-113">既定の監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="99d64-113">Default audit log retention policy</span></span>

<span data-ttu-id="99d64-114">Microsoft 365 の高度な監査には、すべての組織の既定の監査ログの保持ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="99d64-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="99d64-115">このポリシーでは、Exchange、SharePoint、および Azure Active Directory の監査レコードを 1 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="99d64-115">This policy retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="99d64-116">この既定のポリシーは、**ワークロード** プロパティ (アクティビティが発生したサービス) の **AzureActiveDirectory**、**Exchange**、または **SharePoint** の値を含む監査レコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="99d64-116">This default policy retains audit records that contain the value of **AzureActiveDirectory**, **Exchange**, or **SharePoint** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="99d64-117">既定のポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="99d64-117">The default policy can't be modified.</span></span> <span data-ttu-id="99d64-118">既定のポリシーに含まれている各ワークロードのレコード種類の一覧については、この記事の「[詳細情報](#more-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d64-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="99d64-119">既定の監査ログの保持ポリシーは、Office 365 または Microsoft 365 E5 ライセンスが割り当てられているユーザー、または Microsoft 365 E5 コンプライアンスまたは Microsoft 365 E5 eDiscovery and Audit アドオン ライセンスを持つユーザーが実行したアクティビティの監査レコードにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span> <span data-ttu-id="99d64-120">組織に E5 以外のユーザーがいる場合、こうしたユーザーに対応する監査レコードは 90 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-120">If you have non-E5 users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-create-an-audit-log-retention-policy"></a><span data-ttu-id="99d64-121">監査ログの保持ポリシーを作成する前に</span><span class="sxs-lookup"><span data-stu-id="99d64-121">Before you create an audit log retention policy</span></span>

- <span data-ttu-id="99d64-122">監査保持ポリシーを作成または変更するには、セキュリティ/コンプライアンス センターの組織構成の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d64-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="99d64-123">組織では、最大 50 個の監査ログの保持ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="99d64-124">監査ログを 90 日以上保持するには、監査ログを生成したユーザーに Office 365 E5 または Microsoft 365 E5 ライセンスを割り当てるか、または Microsoft 365 E5 Compliance または E5 eDiscovery および監査アドオン ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="99d64-124">To retain an audit log for longer than 90 days, the user who generated the audit log must be assigned an Office 365 E5 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance or E5 eDiscovery and Audit add-on license.</span></span>

- <span data-ttu-id="99d64-125">組織によって作成されるすべてのカスタム監査ログの保持ポリシーは、既定の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-125">All custom audit log retention policies (created by your organization) take priority over the default retention policy.</span></span> <span data-ttu-id="99d64-126">たとえば、保持期間が 1 年未満の Exchange メールボックス アクティビティに対して監査ログの保持ポリシーを作成すると、Exchange メールボックス アクティビティの監査レコードは、カスタム ポリシーで指定されている短い期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-126">For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy-in-the-compliance-center"></a><span data-ttu-id="99d64-127">コンプライアンス センターで監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99d64-127">Create an audit log retention policy in the compliance center</span></span>

1. <span data-ttu-id="99d64-128">[https://compliance.microsoft.com](https://compliance.microsoft.com) に移動し、セキュリティ/コンプライアンス センターで組織構成の役割が割り当てられているユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="99d64-128">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with user account that's assigned the Organization Configuration role in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="99d64-129">Microsoft 365 コンプライアンス センターの左側のウィンドウで、[**すべてを表示**] をクリックし、[**監査**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99d64-129">In the left pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

    <span data-ttu-id="99d64-130">[**監査**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-130">The **Audit** page is displayed.</span></span>

    ![コンプライアンス センターの監査ログの検索ページ](../media/AuditLogRetentionPolicy1.png)

3. <span data-ttu-id="99d64-132">[**監査保持ポリシーの作成**] をクリックし、ポップアップ ページの次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="99d64-132">Click **Create audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![監査保持ポリシーのポップアップ ページ](../media/AuditLogRetentionPolicy2.png)

   1. <span data-ttu-id="99d64-134">**名前:** 監査ログの保持ポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="99d64-134">**Name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="99d64-135">この名前は組織で固有である必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d64-135">This name must be unique in your organization.</span></span>

   2. <span data-ttu-id="99d64-136">**説明:** 省略可能ですが、レコードの種類やワークロード、ポリシーで指定されたユーザー、期間など、ポリシーに関する情報を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99d64-136">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   3. <span data-ttu-id="99d64-137">**ユーザー:** ポリシーを適用する 1 人以上のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="99d64-137">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="99d64-138">このボックスを空白のままにすると、ポリシーがすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-138">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="99d64-139">**レコードの種類** を空白のままにする場合は、ユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d64-139">If you leave the **Record type** blank, then you must select a user.</span></span>

   4. <span data-ttu-id="99d64-140">**レコードの種類:** ポリシーの適用対象となる監査レコードの種類です。</span><span class="sxs-lookup"><span data-stu-id="99d64-140">**Record type:** The audit record type the policy applies to.</span></span> <span data-ttu-id="99d64-141">このプロパティを空白のままにする場合は、[**ユーザー**] ボックスでユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d64-141">If you leave this property blank, you must select a user in the **Users** box.</span></span> <span data-ttu-id="99d64-142">1 つまたは複数のレコードの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-142">You can select a single record type or multiple record types:</span></span>

   - <span data-ttu-id="99d64-143">単一のレコードの種類を選択した場合は、[**アクティビティ**] フィールドが動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-143">If you select a single record type, the **Activities** field is dynamically displayed.</span></span> <span data-ttu-id="99d64-144">ドロップダウン リストを使用して、選択したレコードの種類からポリシーを適用するアクティビティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-144">You can use the drop-down list to select activities from the selected record type to apply the policy to.</span></span> <span data-ttu-id="99d64-145">特定のアクティビティを選択しない場合は、選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-145">If you don't choose specific activities, the policy will apply to all activities of the selected record type.</span></span>

   - <span data-ttu-id="99d64-146">複数のレコードの種類を選択した場合、アクティビティを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="99d64-146">If you select multiple record types, you don't have the ability to select activities.</span></span> <span data-ttu-id="99d64-147">選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-147">The policy will apply to all activities of the selected record types.</span></span>

   5. <span data-ttu-id="99d64-148">**期間:** ポリシーの条件を満たす監査ログの保持期間です。</span><span class="sxs-lookup"><span data-stu-id="99d64-148">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   6. <span data-ttu-id="99d64-149">**ポリシー:** この値は、組織内の監査ログの保持ポリシーが処理される順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="99d64-149">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="99d64-150">値が高いほど、高い優先度を示します。</span><span class="sxs-lookup"><span data-stu-id="99d64-150">A higher value indicates a higher priority.</span></span> <span data-ttu-id="99d64-151">たとえば、優先度の値が **5** のポリシーは、優先度の値が **0** のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-151">For example, a policy with a priority value of **5** would take priority over a policy with a priority value of **0**.</span></span> <span data-ttu-id="99d64-152">前述のとおり、カスタム監査ログの保持ポリシーは、組織の既定ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-152">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

4. <span data-ttu-id="99d64-153">[**保存**] をクリックして新しい監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99d64-153">Click **Save** to create the new audit log retention policy.</span></span>

## <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="99d64-154">PowerShell で監査ログの保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="99d64-154">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="99d64-155">セキュリティ/コンプライアンス センターの PowerShell を使用して監査ログの保持ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="99d64-155">You can also use Security & Compliance Center PowerShell to create audit log retention policies.</span></span>

1. <span data-ttu-id="99d64-156">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="99d64-156">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="99d64-157">次のコマンドを実行して監査ログの保持ポリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99d64-157">Run the following command to create an audit log retention policy.</span></span>

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    <span data-ttu-id="99d64-158">この例では、次の設定を使用して「Microsoft Teams 監査ポリシー」という名前の監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99d64-158">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="99d64-159">ポリシーの説明。</span><span class="sxs-lookup"><span data-stu-id="99d64-159">A description of the policy.</span></span>

   - <span data-ttu-id="99d64-160">Microsoft Teams のすべてのアクティビティ (*RecordType* パラメーターで定義) を保持します。</span><span class="sxs-lookup"><span data-stu-id="99d64-160">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="99d64-161">Microsoft Teams 監査ログを 10 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="99d64-161">Retains Microsoft Teams audit logs for 10 years.</span></span>

   - <span data-ttu-id="99d64-162">優先度が 100 の場合。</span><span class="sxs-lookup"><span data-stu-id="99d64-162">A priority of 100.</span></span>

<span data-ttu-id="99d64-163">監査ログの保持ポリシーを作成するもう 1 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="99d64-163">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="99d64-164">このポリシーには、ユーザー「admin@contoso.onmicrosoft.com」の 6 か月間の「ユーザー ログイン」アクティビティの監査ログが保持されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-164">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="99d64-165">詳細については、「[New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d64-165">For more information, see [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy).</span></span>

## <a name="view-audit-log-retention-policies"></a><span data-ttu-id="99d64-166">監査ログの保持ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="99d64-166">View audit log retention policies</span></span>

<span data-ttu-id="99d64-167">現時点では、カスタム監査ログの保持ポリシーを表示する唯一の方法は、セキュリティ センターとコンプライアンス センターの PowerShell で **Get-UnifiedAuditRetentionPolicy** コマンドレットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="99d64-167">At this time, the only way to view custom audit log retention policies is to use the **Get-UnifiedAuditRetentionPolicy** cmdlet in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="99d64-168">組織の監査ログの保持ポリシーの設定 (前の手順で構成済み) を表示するサンプル コマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="99d64-168">Here's a sample command to display the settings (that you configured in the previous step) for the audit log retention policies in your organization.</span></span> <span data-ttu-id="99d64-169">このコマンドを実行すると、ポリシーが優先度の高い順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="99d64-169">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="99d64-170">現時点では、**Get-UnifiedAuditLogRetentionPolicy** コマンドレットは、組織の既定の監査ログのポリシーを返しません。</span><span class="sxs-lookup"><span data-stu-id="99d64-170">At this time, the **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log policy for your organization.</span></span>

<span data-ttu-id="99d64-171">詳細については、「[Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d64-171">For more information, see [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy).</span></span>

## <a name="some-audit-log-retention-policies-not-supported-in-the-ui"></a><span data-ttu-id="99d64-172">UI でサポートされていない一部の監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="99d64-172">Some audit log retention policies not supported in the UI</span></span>

<span data-ttu-id="99d64-173">**New-UnifiedAuditLogRetentionPolicy** コマンドレットを使用すると、Microsoft 365 コンプライアンス センターの **[監査保持ポリシーの作成]** ツールでは使用できないレコードの種類またはアクティビティの監査ログ保持ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="99d64-173">If you use the **New-UnifiedAuditLogRetentionPolicy** cmdlet, it's possible to create an audit log retention policy for record types or activities that aren't available in the **Create audit retention policy** tool in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="99d64-174">この場合、コンプライアンス センターの **[監査保持ポリシー]** タブからポリシーを編集 (保持期間の変更やアクティビティの追加と削除など) することはできません。</span><span class="sxs-lookup"><span data-stu-id="99d64-174">In this case, you won't be able to edit the policy (for example, change the retention duration or add and remove activities) from the **Audit retention policies** tab in the compliance center.</span></span> <span data-ttu-id="99d64-175">コンプライアンス センターでは、ポリシーを表示したり、削除したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="99d64-175">You'll only be able to view and delete the policy in the compliance center.</span></span> <span data-ttu-id="99d64-176">ポリシーを編集するには、セキュリティ/コンプライアンス センターの PowerShell で **Set-UnifiedAuditLogRetentionPolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="99d64-176">To edit the policy, you'll have to use the **Set-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell.</span></span>

## <a name="more-information"></a><span data-ttu-id="99d64-177">詳細情報</span><span class="sxs-lookup"><span data-stu-id="99d64-177">More information</span></span>

- <span data-ttu-id="99d64-178">セキュリティ センターとコンプライアンス センターの PowerShell で **Set-UnifiedAuditLogRetentionPolicy** コマンドレットを使用して、既存の監査ログの保持ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="99d64-178">Use the **Set-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to modify an existing audit log retention policy.</span></span> <span data-ttu-id="99d64-179">詳細については、「[Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d64-179">For more information, see [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="99d64-180">セキュリティ センターとコンプライアンス センターの PowerShell で **Remove-UnifiedAuditLogRetentionPolicy** コマンドレットを使用して、監査ログの保持ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="99d64-180">Use the **Remove-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="99d64-181">ポリシーが削除されるまで、最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="99d64-181">It might take up to 30 minutes for the policy to be removed.</span></span> <span data-ttu-id="99d64-182">詳細については、「[Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d64-182">For more information, see [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="99d64-183">前に説明したように、Azure Active Directory、Exchange、および SharePoint の運用に関する監査レコードは 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-183">As previously stated, audit records for operations in Azure Active Directory, Exchange, and SharePoint are retained for one year.</span></span> <span data-ttu-id="99d64-184">次の表に、既定の監査ログの保持ポリシーに含まれるすべてのレコードの種類 (これらのサービスごと) を示します。</span><span class="sxs-lookup"><span data-stu-id="99d64-184">The following table lists all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="99d64-185">つまり、特定のレコードの種類、動作、またはユーザーに対してカスタム監査ログの保持ポリシーが優先されない限り、このレコードの種類の動作の監査ログは 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-185">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="99d64-186">各レコードの種類の Enum 値 (監査レコード内の RecordType プロパティの値として表示される) はかっこ内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="99d64-186">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

   |<span data-ttu-id="99d64-187">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="99d64-187">AzureActiveDirectory</span></span> |<span data-ttu-id="99d64-188">Exchange</span><span class="sxs-lookup"><span data-stu-id="99d64-188">Exchange</span></span>  |<span data-ttu-id="99d64-189">SharePoint</span><span class="sxs-lookup"><span data-stu-id="99d64-189">SharePoint</span></span>|
   |:---------|:---------|:---------|
   |<span data-ttu-id="99d64-190">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="99d64-190">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="99d64-191">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="99d64-191">ExchangeAdmin (1)</span></span>|<span data-ttu-id="99d64-192">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="99d64-192">ComplianceDLPSharePoint (11)</span></span>|
   |<span data-ttu-id="99d64-193">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="99d64-193">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="99d64-194">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="99d64-194">ExchangeItem (2)</span></span>|<span data-ttu-id="99d64-195">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="99d64-195">ComplianceDLPSharePointClassification (33)</span></span>|
   |<span data-ttu-id="99d64-196">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="99d64-196">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="99d64-197">Campaign (62)</span><span class="sxs-lookup"><span data-stu-id="99d64-197">Campaign (62)</span></span>|<span data-ttu-id="99d64-198">Project (35)</span><span class="sxs-lookup"><span data-stu-id="99d64-198">Project (35)</span></span>|
   ||<span data-ttu-id="99d64-199">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="99d64-199">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="99d64-200">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="99d64-200">SharePoint (4)</span></span>|
   ||<span data-ttu-id="99d64-201">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="99d64-201">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="99d64-202">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="99d64-202">SharePointCommentOperation (37)</span></span>|
   ||<span data-ttu-id="99d64-203">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="99d64-203">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="99d64-204">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="99d64-204">SharePointContentTypeOperation (55)</span></span>|
   ||<span data-ttu-id="99d64-205">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="99d64-205">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="99d64-206">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="99d64-206">SharePointFieldOperation (56)</span></span>|
   ||<span data-ttu-id="99d64-207">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="99d64-207">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="99d64-208">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="99d64-208">SharePointFileOperation (6)</span></span>|
   ||<span data-ttu-id="99d64-209">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="99d64-209">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="99d64-210">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="99d64-210">SharePointListOperation (36)</span></span>|
   ||<span data-ttu-id="99d64-211">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="99d64-211">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="99d64-212">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="99d64-212">SharePointSharingOperation (14)</span></span>|
   ||||
