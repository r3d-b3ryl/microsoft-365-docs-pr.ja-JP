---
title: Microsoft 365 Enterprise テスト環境の特権アクセスの管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: このテストラボガイドを使用して、Microsoft 365 Enterprise テスト環境で特権アクセス管理を有効にします。
ms.openlocfilehash: 27f63de138f388b0dcbc1bc896bafcb9abc9ed6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632865"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2ab79-103">Microsoft 365 Enterprise テスト環境の特権アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="2ab79-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2ab79-104">*このテストラボ ガイドは、Microsoft 365 Enterprise および Office 365 Enterprise テスト環境に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="2ab79-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2ab79-105">この記事の手順に従って、Microsoft 365 エンタープライズテスト環境のセキュリティを向上させるために、特権アクセス管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="2ab79-107">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2ab79-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2ab79-108">フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="2ab79-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2ab79-109">最低限の要件を持つ軽量な方法で特権アクセス管理を構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2ab79-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2ab79-110">シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2ab79-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="2ab79-111">権限のあるアクセス管理をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと AD DS フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2ab79-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="2ab79-112">この記事は、一般的な組織を表す環境で、特権アクセス管理をテストしてテストできるようにするためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="2ab79-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="2ab79-113">フェーズ 2: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="2ab79-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="2ab79-114">このフェーズでは、承認者グループを構成し、Microsoft 365 Enterprise テスト環境の特権アクセス管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="2ab79-115">権限のあるアクセス管理の詳細と概要については、「 [365 Office 2010 での特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab79-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="2ab79-116">次の手順に従って、組織内で特権アクセスを設定して使用します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="2ab79-117">手順 1: 承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="2ab79-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="2ab79-118">特権アクセスの使用を開始する前に、昇格されたタスクと特権タスクへのアクセスのための受信要求に対して、誰がだれに承認権限を付与するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="2ab79-119">承認者グループの一部であるユーザーは、アクセス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="2ab79-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="2ab79-120">これは、Office 365 でメールが有効なセキュリティグループを作成することによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="2ab79-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="2ab79-121">テスト環境に「特権アクセス承認者」という名前の新しいセキュリティグループを作成し、以前のテストラボガイドの手順で作成した「User 3」を追加します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="2ab79-122">手順 2: 特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="2ab79-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="2ab79-123">既定の承認者グループを使用して Office 365 で特権アクセスを明示的に有効にする必要があります。また、特権アクセス管理アクセス制御から除外する必要があるシステムアカウントのセットを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ab79-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="2ab79-124">このガイドのフェーズ3を開始する前に、必ず組織で特権アクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="2ab79-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="2ab79-125">フェーズ 3: 昇格された権限のあるタスクに承認が必要であることを確認する</span><span class="sxs-lookup"><span data-stu-id="2ab79-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="2ab79-126">このフェーズでは、特権アクセスポリシーが機能していること、および定義された昇格した権限のあるタスクを実行する承認がユーザーに必要であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2ab79-127">特権アクセスポリシーで定義されていないタスクを実行するためのテスト機能</span><span class="sxs-lookup"><span data-stu-id="2ab79-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="2ab79-128">最初に、テスト環境で全体管理者として構成されているユーザーの資格情報を使用して Exchange 管理 PowerShell に接続し、新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="2ab79-129">[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)タスクは、現在、組織の特権アクセスポリシーでは定義されていません。</span><span class="sxs-lookup"><span data-stu-id="2ab79-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="2ab79-130">ローカルコンピューターで、テスト環境のグローバル管理者アカウントを使用して、 **microsoft Corporation** > **microsoft exchange online**リモート powershell モジュールの exchange online リモート powershell モジュールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ab79-131">Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="2ab79-132">Exchange 管理 PowerShell で新しいジャーナルルールが正常に作成されたことを表示します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="2ab79-133">New-journalrule タスクの新しい特権アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2ab79-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="2ab79-134">このガイドのフェーズ2の手順1と2をまだ完了していない場合は、「権限アクセス承認者」という名前の承認者のグループを作成し、テスト環境で特権アクセスを有効にする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2ab79-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="2ab79-135">資格情報を使用して[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。テスト環境のグローバル管理者アカウントです。</span><span class="sxs-lookup"><span data-stu-id="2ab79-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ab79-136">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2ab79-137">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2ab79-138">[**ポリシーの構成**] を選択し、[**ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="2ab79-139">ドロップダウンフィールドで、次の値を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="2ab79-140">**ポリシーの種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="2ab79-140">**Policy type**: Task</span></span>

    <span data-ttu-id="2ab79-141">**ポリシースコープ**: Exchange</span><span class="sxs-lookup"><span data-stu-id="2ab79-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="2ab79-142">**ポリシー名**: 新しいジャーナルルール</span><span class="sxs-lookup"><span data-stu-id="2ab79-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="2ab79-143">**承認の種類**: 手動</span><span class="sxs-lookup"><span data-stu-id="2ab79-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="2ab79-144">**承認グループ**: 特権アクセス承認者</span><span class="sxs-lookup"><span data-stu-id="2ab79-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="2ab79-145">[**作成**] を選択し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="2ab79-146">ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ab79-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="2ab79-147">次の手順で承認の要件をテストする前に、ポリシーが完全に有効になるまでの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="2ab79-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2ab79-148">特権アクセスポリシーで定義された New-journalrule タスクのテスト承認要件</span><span class="sxs-lookup"><span data-stu-id="2ab79-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="2ab79-149">ローカルコンピューターで、テスト環境のグローバル管理者アカウントを使用して、 **microsoft Corporation** > **microsoft exchange online リモート**powershell モジュールの exchange online リモート powershell モジュールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ab79-150">Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="2ab79-151">Exchange 管理 PowerShell で "十分な権限がありません" というエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="2ab79-152">New-journalrule タスクを使用して新しいジャーナルルールを作成するためのアクセス権を要求する</span><span class="sxs-lookup"><span data-stu-id="2ab79-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="2ab79-153">テスト環境のグローバル管理者アカウントを使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ab79-154">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2ab79-155">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2ab79-156">[**新しい要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-156">Select **New request**.</span></span> <span data-ttu-id="2ab79-157">ドロップダウンフィールドで、組織に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="2ab79-158">**要求の種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="2ab79-158">**Request type**: Task</span></span>

    <span data-ttu-id="2ab79-159">**要求スコープ**: Exchange</span><span class="sxs-lookup"><span data-stu-id="2ab79-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="2ab79-160">**要求**: 新しいジャーナルルール</span><span class="sxs-lookup"><span data-stu-id="2ab79-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="2ab79-161">**期間 (時間)**: 2</span><span class="sxs-lookup"><span data-stu-id="2ab79-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="2ab79-162">**コメント**: 新しいジャーナルルールを作成するためのアクセス許可を要求する</span><span class="sxs-lookup"><span data-stu-id="2ab79-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="2ab79-163">[**保存**] を選択し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="2ab79-164">要求は、電子メールを介して承認者のグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2ab79-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="2ab79-165">新しいジャーナルルールの作成に関する特権アクセス要求を承認する</span><span class="sxs-lookup"><span data-stu-id="2ab79-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="2ab79-166">テスト環境のユーザー3の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします (テスト環境の "特権アクセス承認者" セキュリティグループのメンバー)。</span><span class="sxs-lookup"><span data-stu-id="2ab79-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="2ab79-167">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2ab79-168">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2ab79-169">保留中の要求を選択し、[**承認**] を選択して、新しいジャーナルルールを作成するためのグローバル管理者アカウントへのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="2ab79-170">承認が付与されたことを確認する通知メールは、グローバル管理者アカウント (要求元ユーザー) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2ab79-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="2ab79-171">New-journalrule タスクの特権アクセスが承認された新しいジャーナルルールを作成するテスト</span><span class="sxs-lookup"><span data-stu-id="2ab79-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="2ab79-172">ローカルコンピューターで、テスト環境のグローバル管理者アカウントを使用して、 **microsoft Corporation** > **microsoft exchange online**リモート powershell モジュールの exchange online リモート powershell モジュールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2ab79-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2ab79-173">Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="2ab79-174">Exchange 管理 PowerShell で新しいジャーナルルールが正常に作成されたことを表示します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="2ab79-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="2ab79-175">Next step</span></span>

<span data-ttu-id="2ab79-176">テスト環境でのその他の[情報保護](m365-enterprise-test-lab-guides.md#information-protection)機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ab79-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ab79-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ab79-177">See also</span></span>

[<span data-ttu-id="2ab79-178">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="2ab79-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2ab79-179">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="2ab79-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2ab79-180">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="2ab79-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
