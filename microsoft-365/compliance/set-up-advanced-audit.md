---
title: '[高度な監査] を [Microsoft 365'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: この記事では、ユーザー アカウントが侵害された場合に法医学調査を実行したり、他のセキュリティ関連のインシデントを調査したりするために高度な監査を設定する方法について説明します。
ms.openlocfilehash: 825dadee5260a263d005eb3a37f280381f9425a2
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339228"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="32446-103">[高度な監査] を [Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32446-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="32446-104">組織に高度な監査をサポートするサブスクリプションとエンド ユーザー ライセンスがある場合は、次の手順を実行して、Advanced Audit の追加機能を設定して使用します。</span><span class="sxs-lookup"><span data-stu-id="32446-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![高度な監査を設定するためのワークフロー](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a><span data-ttu-id="32446-106">手順 1: ユーザーの高度な監査を設定する</span><span class="sxs-lookup"><span data-stu-id="32446-106">Step 1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="32446-107">MailItemsAccessed や Send などの重要なイベントをログに記録する機能などの高度な監査機能を使用するには、ユーザーに適切な E5 ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="32446-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="32446-108">さらに、それらのユーザーに対して高度な監査アプリ/サービス プランを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32446-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="32446-109">高度な監査アプリがユーザーに割り当てられていることを確認するには、ユーザーごとに次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32446-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="32446-110">[Microsoft 365 管理センター](https://admin.microsoft.com/Adminportal)で、**[ユーザー]** > **[アクティブなユーザー]** の順に移動し、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="32446-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="32446-111">ユーザー プロパティのポップアップ ページで、**[ライセンスとアプリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32446-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="32446-112">[ライセンス **] セクション** で、ユーザーに E5 ライセンスが割り当てられているか、適切なアドオン ライセンスが割り当てられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="32446-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="32446-113">高度な監査をサポートするライセンスの一覧については、「 [高度な監査ライセンス要件」を参照してください](auditing-solutions-overview.md#advanced-audit-1)。</span><span class="sxs-lookup"><span data-stu-id="32446-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="32446-114">**[アプリ]** セクションを展開して、**[Microsoft 365 高度な監査]** チェック ボックスが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="32446-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="32446-115">チェック ボックスが選択されていない場合は、チェック ボックスをオンにして、[変更の保存] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="32446-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="32446-116">MailItemsAccessed と Send の監査レコードのログ記録は、24 時間以内に開始されます。</span><span class="sxs-lookup"><span data-stu-id="32446-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="32446-117">手順 3 を実行して、他の 2 つの高度な監査の重要なイベントである SearchQueryInitiatedExchange と SearchQueryInitiatedSharePoint のログ記録を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32446-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="32446-118">グループ ベースのライセンスを使用してユーザーのグループにライセンスを割り当てている組織では、グループに対する Microsoft 365 Advanced Auditing のライセンス割り当てをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32446-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="32446-119">変更を保存したら、Microsoft 365 Advanced Auditing がグループに対してオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="32446-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="32446-120">その後、グループに対するライセンス割り当てをもう一度オンにします。</span><span class="sxs-lookup"><span data-stu-id="32446-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="32446-121">グループ ベースのライセンスの手順については、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32446-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="32446-122">また、ユーザー メールボックスまたは共有メールボックスにログオンしているメールボックスアクションをカスタマイズした場合、Microsoft によってリリースされた新しい重要なイベントは、それらのメールボックスで自動的に監査されません。</span><span class="sxs-lookup"><span data-stu-id="32446-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="32446-123">ログオンの種類ごとに監査されるメールボックス操作の変更については、 「[メールボックスの監査を管理する](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)」の「既定でログに記録されるメールボックスの操作を変更または復元する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32446-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="32446-124">手順 2: 重要なイベントを有効にする</span><span class="sxs-lookup"><span data-stu-id="32446-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="32446-125">ユーザーが Exchange Online と SharePoint Online で検索を実行するときに、2 つの重要なイベント (SearchQueryInitiatedExchange と SearchQueryInitiatedSharePoint) をログに記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32446-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="32446-126">これらの 2 つのイベントをユーザーに対して監査するには、PowerShell で次のコマンド (ユーザーごとに)[をExchange Onlineします](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="32446-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="32446-127">複数地域環境では、ユーザーのメールボックスがあるフォレストで前の **Set-Mailbox** コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32446-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="32446-128">ユーザーのメールボックスの場所を特定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="32446-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="32446-129">検索クエリの監査を有効にするコマンドが以前は、ユーザーのメールボックスが存在するフォレストとは異なるフォレストで実行されている場合は、実行してユーザーのメールボックスから SearchQueryInitiated 値を削除し、ユーザーのメールボックスがあるフォレスト内のユーザーのメールボックスに追加する必要があります。 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`</span><span class="sxs-lookup"><span data-stu-id="32446-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="32446-130">手順 3: 監査保持ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="32446-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="32446-131">Exchange、SharePoint、および Azure AD の監査記録を 1 年間保持する既定のポリシーに加えて、組織のセキュリティ運用チーム、IT チーム、およびコンプライアンス チームの要件に合わせて、監査ログの保持ポリシーを追加で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="32446-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="32446-132">詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32446-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="32446-133">手順 4: 重要なイベントを検索する</span><span class="sxs-lookup"><span data-stu-id="32446-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="32446-134">組織に対して高度な監査が設定されたので、捜査を行う際に重要なイベントや他のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="32446-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="32446-135">手順 1 と手順 2 を完了すると、侵害されたアカウントや他の種類のセキュリティまたはコンプライアンス調査の法医学調査中に、監査ログで重要なイベントや他のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="32446-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="32446-136">MailItemsAccessed 重要なイベントを使用して侵害されたユーザー アカウントの forensics 調査を実行する方法の詳細については、「高度な監査を使用して侵害されたアカウントを調査する」を参照 [してください](mailitemsaccessed-forensics-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="32446-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
