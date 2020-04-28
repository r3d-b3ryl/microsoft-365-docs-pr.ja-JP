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
ms.openlocfilehash: 25fbabd4c7524702a985616797b31730b14a2d8f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636375"
---
# <a name="manage-audit-log-retention-policies"></a><span data-ttu-id="fe364-104">監査ログの保持ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="fe364-104">Manage audit log retention policies</span></span>

<span data-ttu-id="fe364-105">セキュリティ/コンプライアンス センターで監査ログの保持ポリシーを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="fe364-105">You can create and manage audit log retention policies in the Security & Compliance Center.</span></span> <span data-ttu-id="fe364-106">監査ログの保持ポリシーは、Microsoft 365 の新しい高度な監査機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="fe364-106">Audit log retention policies are part of the new Advanced Audit capabilities in Microsoft 365.</span></span> <span data-ttu-id="fe364-107">監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fe364-107">An audit log retention policy lets you specify how long to retain audit logs in your organization.</span></span> <span data-ttu-id="fe364-108">監査ログは、最大 1 年間保持できます。</span><span class="sxs-lookup"><span data-stu-id="fe364-108">You can retain audit logs for up to one year.</span></span> <span data-ttu-id="fe364-109">次の条件を基にしてポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe364-109">You can create policies based on the following criteria:</span></span>

- <span data-ttu-id="fe364-110">1 つまたは複数の Microsoft 365 サービスのすべてのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="fe364-110">All activities in one or more Microsoft 365 services</span></span>

- <span data-ttu-id="fe364-111">すべてのユーザーまたは特定のユーザーによって実行された (特定のサービスの) 特定のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="fe364-111">Specific activities (in a specific service) performed by all users or by specific users</span></span>

- <span data-ttu-id="fe364-112">優先度レベルは、組織内に複数のポリシーがある場合に、どのポリシーが優先されるかを指定する</span><span class="sxs-lookup"><span data-stu-id="fe364-112">A priority level that specifies which policy takes precedence in you have multiple policies in your organization</span></span>

## <a name="default-audit-log-retention-policy"></a><span data-ttu-id="fe364-113">既定の監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="fe364-113">Default audit log retention policy</span></span>

<span data-ttu-id="fe364-114">Microsoft 365 の高度な監査には、すべての組織の既定の監査ログの保持ポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fe364-114">Advanced Audit in Microsoft 365 provides a default audit log retention policy for all organizations.</span></span> <span data-ttu-id="fe364-115">このポリシーでは、Exchange、SharePoint、および Azure Active Directory の監査レコードを 1 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="fe364-115">This policy retains all Exchange, SharePoint, and Azure Active Directory audit records for one year.</span></span> <span data-ttu-id="fe364-116">この既定のポリシーは、**ワークロード** プロパティ (アクティビティが発生したサービス) の **AzureActiveDirectory**、**Exchange**、または **SharePoint** の値を含む監査レコードを保持します。</span><span class="sxs-lookup"><span data-stu-id="fe364-116">This default policy retains audit records that contain the value of **AzureActiveDirectory**, **Exchange**, or **SharePoint** for the **Workload** property (which is the service in which the activity occurred).</span></span> <span data-ttu-id="fe364-117">既定のポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="fe364-117">The default policy can't be modified.</span></span> <span data-ttu-id="fe364-118">既定のポリシーに含まれている各ワークロードのレコード種類の一覧については、この記事の「[詳細情報](#more-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe364-118">See the [More information](#more-information) section in this article for a list of record types for each workload that are included in the default policy.</span></span>

> [!NOTE]
> <span data-ttu-id="fe364-119">既定の監査ログの保持ポリシーは、Office 365 または Microsoft 365 E5 ライセンスが割り当てられているユーザー、または Microsoft 365 E5 コンプライアンス アドオン ライセンスを持つユーザーが実行したアクティビティの監査レコードにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-119">The default audit log retention policy only applies to audit records for activity performed by users who are assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance add-on license.</span></span> <span data-ttu-id="fe364-120">組織に E5 以外のユーザーがいる場合、対応する監査レコードは 90 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-120">If you have non-E5 users in your organization, their corresponding audit records are retained for 90 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fe364-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="fe364-121">Before you begin</span></span>

- <span data-ttu-id="fe364-122">監査保持ポリシーを作成または変更するには、セキュリティ/コンプライアンス センターの組織構成の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe364-122">You have to be assigned the Organization Configuration role in the Security & Compliance Center to create or modify an audit retention policy.</span></span>

- <span data-ttu-id="fe364-123">組織では、最大 50 個の監査ログの保持ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="fe364-123">You can have a maximum of 50 audit log retention policies in your organization.</span></span>

- <span data-ttu-id="fe364-124">監査ログを 90 日以上保持するには、監査ログを生成したユーザーに Office 365 または Microsoft 365 E5 ライセンスを割り当てるか、または Microsoft 365 E5 コンプライアンス アドオン ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe364-124">To retain an audit log for longer than 90 days, the user who generated the audit log must be assigned an Office 365 or Microsoft 365 E5 license or have a Microsoft 365 E5 Compliance add-on license.</span></span>

- <span data-ttu-id="fe364-125">組織によって作成されるすべてのカスタム監査ログの保持ポリシーでは、既定の保持ポリシーが優先されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-125">All custom audit log retention policies (created by your organization) take priority of the default retention policy.</span></span> <span data-ttu-id="fe364-126">たとえば、保持期間が 1 年未満の Exchange メールボックス アクティビティに対して監査ログの保持ポリシーを作成すると、Exchange メールボックス アクティビティの監査レコードは、カスタム ポリシーで指定されている短い期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-126">For example, if you create an audit log retention policy for Exchange mailbox activity that has a retention period that's shorter than one year, audit records for Exchange mailbox activities will be retained for the shorter duration specified by the custom policy.</span></span>

## <a name="create-an-audit-log-retention-policy-in-the-security--compliance-center"></a><span data-ttu-id="fe364-127">セキュリティ/コンプライアンス センターで監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe364-127">Create an audit log retention policy in the Security & Compliance Center</span></span>

1. <span data-ttu-id="fe364-128">[https://protection.office.com](https://protection.office.com) に移動し、セキュリティ/コンプライアンス センターで組織構成の役割が割り当てられているユーザー アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe364-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with user account that's assigned the Organization Configuration role in the Security & Compliance Center.</span></span> 

2. <span data-ttu-id="fe364-129">セキュリティ/コンプライアンス センターの左側のウィンドウで、[**検索**]  >  [**監査ログの検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe364-129">In the left pane of the Security & Compliance Center, click **Search** > **Audit log search**.</span></span>

    <span data-ttu-id="fe364-130">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-130">The **Audit log search** page is displayed.</span></span>

    ![監査ログの検索ページ](../media/AuditLogRetentionPolicy1.png)

3. <span data-ttu-id="fe364-132">[**監査保持ポリシーの新規作成**] をクリックし、ポップアップ ページの次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="fe364-132">Click **New audit retention policy**, and then complete the following fields on the flyout page:</span></span>

    ![監査保持ポリシーのポップアップ ページ](../media/AuditLogRetentionPolicy2.png)

   <span data-ttu-id="fe364-134">a. </span><span class="sxs-lookup"><span data-stu-id="fe364-134">a.</span></span> <span data-ttu-id="fe364-135">**名前:** 監査ログの保持ポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="fe364-135">**Name:** The name of the audit log retention policy.</span></span> <span data-ttu-id="fe364-136">この名前は組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe364-136">This name must be unique in your organization.</span></span>
   
   <span data-ttu-id="fe364-137">b. </span><span class="sxs-lookup"><span data-stu-id="fe364-137">b.</span></span> <span data-ttu-id="fe364-138">**説明:** 省略可能ですが、レコードの種類やワークロード、ポリシーで指定されたユーザー、期間など、ポリシーに関する情報を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe364-138">**Description:** Optional, but helpful to provide information about the policy, such as the record type or workload, users specified in the policy, and the duration.</span></span>

   <span data-ttu-id="fe364-139">c.</span><span class="sxs-lookup"><span data-stu-id="fe364-139">c.</span></span> <span data-ttu-id="fe364-140">**レコードの種類:** ポリシーの適用対象となる監査レコードの種類です。</span><span class="sxs-lookup"><span data-stu-id="fe364-140">**Record types:** The audit record type the policy applies to.</span></span> <span data-ttu-id="fe364-141">複数のレコードの種類を選択した場合は、選択したレコードの種類のすべてのアクティビティにポリシーが適用されるため、アクティビティを選択できません。</span><span class="sxs-lookup"><span data-stu-id="fe364-141">If you select more than one record type, you can't select activities because the policy will apply to all activities for the selected record types.</span></span> <span data-ttu-id="fe364-142">また、このプロパティを空白のままにする場合は、[**ユーザー**] ボックスでユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe364-142">Also, if you leave this property blank, you must select a user in the **Users** box.</span></span>

   <span data-ttu-id="fe364-143">d.</span><span class="sxs-lookup"><span data-stu-id="fe364-143">d.</span></span> <span data-ttu-id="fe364-144">**アクティビティ:** このボックスを使用して、選択したレコードの種類からアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe364-144">**Activities:** Use this box to choose activities from the record type that you selected.</span></span> <span data-ttu-id="fe364-145">ポリシーを適用する特定のアクティビティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="fe364-145">You can choose specific activities to apply the policy to.</span></span> <span data-ttu-id="fe364-146">特定のアクティビティを選択しない場合は、選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-146">If you don't choose specific activities, then the policy will apply to all activities of the selected record type.</span></span>

   <span data-ttu-id="fe364-147">e. </span><span class="sxs-lookup"><span data-stu-id="fe364-147">e.</span></span> <span data-ttu-id="fe364-148">**ユーザー:** ポリシーを適用する 1 人以上のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe364-148">**Users:** Select one or more users to apply the policy to.</span></span> <span data-ttu-id="fe364-149">このボックスを空白のままにすると、ポリシーがすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-149">If you leave this box blank, then the policy will apply to all users.</span></span> <span data-ttu-id="fe364-150">**レコードの種類**を空白のままにする場合は、ユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe364-150">If you leave the **Record types** blank, then you must select a user.</span></span>

   <span data-ttu-id="fe364-151">f.</span><span class="sxs-lookup"><span data-stu-id="fe364-151">f.</span></span> <span data-ttu-id="fe364-152">**期間:** ポリシーの条件を満たす監査ログの保持期間です。</span><span class="sxs-lookup"><span data-stu-id="fe364-152">**Duration:** The amount of time to retain the audit logs that meet the criteria of the policy.</span></span>

   <span data-ttu-id="fe364-153">g. </span><span class="sxs-lookup"><span data-stu-id="fe364-153">g.</span></span> <span data-ttu-id="fe364-154">**ポリシー:** この値は、組織内の監査ログの保持ポリシーが処理される順序を決定します。</span><span class="sxs-lookup"><span data-stu-id="fe364-154">**Priority:** This value determines the order in which audit log retention policies in your organization are processed.</span></span> <span data-ttu-id="fe364-155">値が高いほど、高い優先度を示します。</span><span class="sxs-lookup"><span data-stu-id="fe364-155">A higher value indicates a higher priority.</span></span> <span data-ttu-id="fe364-156">たとえば、優先度の値が **5** のポリシーは、優先度の値が **0** のポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-156">For example, a policy with a priority value of **5** would take priority over a policy with a priority value of **0**.</span></span> <span data-ttu-id="fe364-157">前述のとおり、カスタム監査ログの保持ポリシーは、組織の既定ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-157">As previously explained, any custom audit log retention policy takes priority over the default policy for your organization.</span></span>

6. <span data-ttu-id="fe364-158">[**保存**] をクリックして新しい監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe364-158">Click **Save** to create the new audit log retention policy.</span></span> 

<span data-ttu-id="fe364-159">現時点では、保持ポリシーが正常に作成されたことを示すものはありません。</span><span class="sxs-lookup"><span data-stu-id="fe364-159">At this time, there's no indication that the retention policy was successfully created.</span></span> <span data-ttu-id="fe364-160">監査ログの保持ポリシーのプロパティの表示については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe364-160">See the next section on viewing the properties of the audit log retention policies.</span></span>

## <a name="create-an-audit-log-retention-policy-in-powershell"></a><span data-ttu-id="fe364-161">PowerShell で監査ログの保持ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fe364-161">Create an audit log retention policy in PowerShell</span></span>

<span data-ttu-id="fe364-162">セキュリティ/コンプライアンス センターの PowerShell を使用して監査ログの保持ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe364-162">You can also use Security & Compliance Center PowerShell to create audit log retention policies.</span></span> 

1. <span data-ttu-id="fe364-163">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fe364-163">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="fe364-164">次のコマンドを実行して監査ログの保持ポリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe364-164">Run the following command to create an audit log retention policy.</span></span> 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```
    
    <span data-ttu-id="fe364-165">この例では、次の設定を使用して「Microsoft Teams 監査ポリシー」という名前の監査ログの保持ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe364-165">This example creates an audit log retention policy named "Microsoft Teams Audit Policy" with these settings:</span></span>

   - <span data-ttu-id="fe364-166">ポリシーの説明。</span><span class="sxs-lookup"><span data-stu-id="fe364-166">A description of the policy.</span></span>

   - <span data-ttu-id="fe364-167">Microsoft Teams のすべてのアクティビティ (*RecordType* パラメーターで定義) を保持します。</span><span class="sxs-lookup"><span data-stu-id="fe364-167">Retains all Microsoft Teams activities (as defined by the *RecordType* parameter).</span></span>

   - <span data-ttu-id="fe364-168">Microsoft Teams 監査ログを 1 年間保持します。</span><span class="sxs-lookup"><span data-stu-id="fe364-168">Retains Microsoft Teams audit logs for one year.</span></span>

   - <span data-ttu-id="fe364-169">優先度が 100 の場合。</span><span class="sxs-lookup"><span data-stu-id="fe364-169">A priority of 100.</span></span>

<span data-ttu-id="fe364-170">監査ログの保持ポリシーを作成するもう 1 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe364-170">Here's another example of creating an audit log retention policy.</span></span> <span data-ttu-id="fe364-171">このポリシーには、ユーザー「admin@contoso.onmicrosoft.com」の 6 か月間の「ユーザー ログイン」アクティビティの監査ログが保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-171">This policy retains audit logs for the "User logged in" activity for six months for the user admin@contoso.onmicrosoft.com.</span></span>

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

<span data-ttu-id="fe364-172">詳細については、「[New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe364-172">For more information, see [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-unifiedauditlogretentionpolicy).</span></span>

## <a name="view-audit-log-retention-policies"></a><span data-ttu-id="fe364-173">監査ログの保持ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="fe364-173">View audit log retention policies</span></span>

<span data-ttu-id="fe364-174">現時点では、カスタム監査ログの保持ポリシーを表示する唯一の方法は、セキュリティ センターとコンプライアンス センターの PowerShell で **Get-UnifiedAuditRetentionPolicy** コマンドレットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="fe364-174">At this time, the only way to view custom audit log retention policies is to use the **Get-UnifiedAuditRetentionPolicy** cmdlet in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="fe364-175">組織の監査ログの保持ポリシーの設定 (前の手順で構成済み) を表示するサンプル コマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="fe364-175">Here's a sample command to display the settings (that you configured in the previous step) for the audit log retention policies in your organization.</span></span> <span data-ttu-id="fe364-176">このコマンドを実行すると、ポリシーが優先度の高い順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="fe364-176">This command sorts the policies from the highest to lowest priority.</span></span>

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> <span data-ttu-id="fe364-177">現時点では、**Get-UnifiedAuditLogRetentionPolicy** コマンドレットは、組織の既定の監査ログのポリシーを返しません。</span><span class="sxs-lookup"><span data-stu-id="fe364-177">At this time, the **Get-UnifiedAuditLogRetentionPolicy** cmdlet doesn't return the default audit log policy for your organization.</span></span>

<span data-ttu-id="fe364-178">詳細については、「[Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/get-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe364-178">For more information, see [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/get-unifiedauditlogretentionpolicy).</span></span>

## <a name="more-information"></a><span data-ttu-id="fe364-179">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fe364-179">More information</span></span>

- <span data-ttu-id="fe364-180">セキュリティ センターとコンプライアンス センターの PowerShell で**Set-UnifiedAuditLogRetentionPolicy** コマンドレットを使用して、既存の監査ログの保持ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="fe364-180">Use the **Set-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to modify an existing audit log retention policy.</span></span> <span data-ttu-id="fe364-181">詳細については、「[Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/set-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe364-181">For more information, see [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/set-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="fe364-182">セキュリティ センターとコンプライアンス センターの PowerShell で**Remove-UnifiedAuditLogRetentionPolicy** コマンドレットを使用して、監査ログの保持ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fe364-182">Use the **Remove-UnifiedAuditLogRetentionPolicy** cmdlet in Security & Compliance Center PowerShell to delete an audit log retention policy.</span></span> <span data-ttu-id="fe364-183">ポリシーが完全に削除されるまで、最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe364-183">It might take up to 30 minutes for the policy to be completely removed.</span></span> <span data-ttu-id="fe364-184">詳細については、「[Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/remove-unifiedauditlogretentionpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe364-184">For more information, see [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/remove-unifiedauditlogretentionpolicy).</span></span>

- <span data-ttu-id="fe364-185">前に説明したように、Azure Active Directory、Exchange、および SharePoint の運用に関する監査レコードは 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-185">As previously stated, audit records for operations in Azure Active Directory, Exchange, and SharePoint are retained for one year.</span></span> <span data-ttu-id="fe364-186">次の表に、既定の監査ログの保持ポリシーに含まれるすべてのレコードの種類 (これらのサービスごと) を示します。</span><span class="sxs-lookup"><span data-stu-id="fe364-186">The following table list all the record types (for each of these services) included in the default audit log retention policy.</span></span> <span data-ttu-id="fe364-187">つまり、特定のレコードの種類、動作、またはユーザーに対してカスタム監査ログの保持ポリシーが優先されない限り、このレコードの種類の動作の監査ログは 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-187">This means that audit logs for any operation with this record type are retained for one year unless a custom audit log retention policy takes precedence for a specific record type, operation, or user.</span></span> <span data-ttu-id="fe364-188">各レコードの種類の Enum 値 (監査レコード内の RecordType プロパティの値として表示される) はかっこ内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe364-188">The Enum value (which is displayed as the value for the RecordType property in an audit record) for each record type is shown in parentheses.</span></span>

   |<span data-ttu-id="fe364-189">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="fe364-189">AzureActiveDirectory</span></span> |<span data-ttu-id="fe364-190">Exchange</span><span class="sxs-lookup"><span data-stu-id="fe364-190">Exchange</span></span>  |<span data-ttu-id="fe364-191">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe364-191">SharePoint</span></span>|
   |:---------|:---------|:---------|
   |<span data-ttu-id="fe364-192">AzureActiveDirectory (8)</span><span class="sxs-lookup"><span data-stu-id="fe364-192">AzureActiveDirectory (8)</span></span>|<span data-ttu-id="fe364-193">ExchangeAdmin (1)</span><span class="sxs-lookup"><span data-stu-id="fe364-193">ExchangeAdmin (1)</span></span>|<span data-ttu-id="fe364-194">ComplianceDLPSharePoint (11)</span><span class="sxs-lookup"><span data-stu-id="fe364-194">ComplianceDLPSharePoint (11)</span></span>|
   |<span data-ttu-id="fe364-195">AzureActiveDirectoryAccountLogon (9)</span><span class="sxs-lookup"><span data-stu-id="fe364-195">AzureActiveDirectoryAccountLogon (9)</span></span>|<span data-ttu-id="fe364-196">ExchangeItem (2)</span><span class="sxs-lookup"><span data-stu-id="fe364-196">ExchangeItem (2)</span></span>|<span data-ttu-id="fe364-197">ComplianceDLPSharePointClassification (33)</span><span class="sxs-lookup"><span data-stu-id="fe364-197">ComplianceDLPSharePointClassification (33)</span></span>|
   |<span data-ttu-id="fe364-198">AzureActiveDirectoryStsLogon (15)</span><span class="sxs-lookup"><span data-stu-id="fe364-198">AzureActiveDirectoryStsLogon (15)</span></span>|<span data-ttu-id="fe364-199">Campaign (62)</span><span class="sxs-lookup"><span data-stu-id="fe364-199">Campaign (62)</span></span>|<span data-ttu-id="fe364-200">Project (35)</span><span class="sxs-lookup"><span data-stu-id="fe364-200">Project (35)</span></span>|
   ||<span data-ttu-id="fe364-201">ComplianceDLPExchange (13)</span><span class="sxs-lookup"><span data-stu-id="fe364-201">ComplianceDLPExchange (13)</span></span>|<span data-ttu-id="fe364-202">SharePoint (4)</span><span class="sxs-lookup"><span data-stu-id="fe364-202">SharePoint (4)</span></span>|
   ||<span data-ttu-id="fe364-203">ComplianceSupervisionExchange (68)</span><span class="sxs-lookup"><span data-stu-id="fe364-203">ComplianceSupervisionExchange (68)</span></span>|<span data-ttu-id="fe364-204">SharePointCommentOperation (37)</span><span class="sxs-lookup"><span data-stu-id="fe364-204">SharePointCommentOperation (37)</span></span>|
   ||<span data-ttu-id="fe364-205">CustomerKeyServiceEncryption (69)</span><span class="sxs-lookup"><span data-stu-id="fe364-205">CustomerKeyServiceEncryption (69)</span></span>|<span data-ttu-id="fe364-206">SharePointContentTypeOperation (55)</span><span class="sxs-lookup"><span data-stu-id="fe364-206">SharePointContentTypeOperation (55)</span></span>|
   ||<span data-ttu-id="fe364-207">ExchangeAggregatedOperation (19)</span><span class="sxs-lookup"><span data-stu-id="fe364-207">ExchangeAggregatedOperation (19)</span></span>|<span data-ttu-id="fe364-208">SharePointFieldOperation (56)</span><span class="sxs-lookup"><span data-stu-id="fe364-208">SharePointFieldOperation (56)</span></span>|
   ||<span data-ttu-id="fe364-209">ExchangeItemAggregated (50)</span><span class="sxs-lookup"><span data-stu-id="fe364-209">ExchangeItemAggregated (50)</span></span>|<span data-ttu-id="fe364-210">SharePointFileOperation (6)</span><span class="sxs-lookup"><span data-stu-id="fe364-210">SharePointFileOperation (6)</span></span>|
   ||<span data-ttu-id="fe364-211">ExchangeItemGroup (3)</span><span class="sxs-lookup"><span data-stu-id="fe364-211">ExchangeItemGroup (3)</span></span>|<span data-ttu-id="fe364-212">SharePointListOperation (36)</span><span class="sxs-lookup"><span data-stu-id="fe364-212">SharePointListOperation (36)</span></span>|
   ||<span data-ttu-id="fe364-213">InformationBarrierPolicyApplication (53)</span><span class="sxs-lookup"><span data-stu-id="fe364-213">InformationBarrierPolicyApplication (53)</span></span>|<span data-ttu-id="fe364-214">SharePointSharingOperation (14)</span><span class="sxs-lookup"><span data-stu-id="fe364-214">SharePointSharingOperation (14)</span></span>|
   ||||
