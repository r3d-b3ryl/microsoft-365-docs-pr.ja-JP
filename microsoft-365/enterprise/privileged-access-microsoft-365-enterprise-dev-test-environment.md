---
title: Microsoft 365 用のエンタープライズテスト環境の特権アクセス管理
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
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境の特権アクセス管理を有効にします。
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487590"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5c26d-103">Microsoft 365 用のエンタープライズテスト環境の特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="5c26d-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5c26d-104">*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*</span><span class="sxs-lookup"><span data-stu-id="5c26d-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5c26d-105">この記事では、Microsoft 365 for enterprise テスト環境のセキュリティを強化するために、特権アクセス管理を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="5c26d-106">Priviledged アクセス管理を構成するには、3つのフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c26d-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="5c26d-107">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="5c26d-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="5c26d-108">フェーズ 2: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="5c26d-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="5c26d-109">フェーズ 3: 昇格された権限のあるタスクに承認が必要であることを確認する</span><span class="sxs-lookup"><span data-stu-id="5c26d-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5c26d-111">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c26d-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5c26d-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="5c26d-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5c26d-113">最低限の要件を持つ軽量な方法で特権アクセス管理を構成する場合は、「軽量な [基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5c26d-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5c26d-114">シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5c26d-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="5c26d-115">特権アクセス管理をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメインサービスフォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c26d-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="5c26d-116">この記事はオプションとして提供されており、一般的な組織を表す環境で、特権アクセス管理をテストし、それを試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="5c26d-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="5c26d-117">フェーズ 2: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="5c26d-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="5c26d-118">このフェーズでは、承認者グループを構成し、Microsoft 365 for enterprise テスト環境の特権アクセス管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5c26d-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="5c26d-119">その他の詳細と、特権アクセス管理の概要については、「 [特権アクセス管理](../compliance/privileged-access-management-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c26d-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="5c26d-120">組織で特権アクセスを設定して使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="5c26d-121">手順 1: 承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="5c26d-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="5c26d-122">特権アクセスの使用を開始する前に、昇格されたタスクと特権タスクへのアクセスのための受信要求に対して、誰がだれに承認権限を付与するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="5c26d-123">承認者グループの一部であるすべてのユーザーは、アクセス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="5c26d-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="5c26d-124">特権アクセスを使用するには、Microsoft 365 でメールが有効なセキュリティグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c26d-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="5c26d-125">テスト環境で、新しいセキュリティグループに「権限のあるアクセス承認者」という名前を指定し、以前のテストラボガイドの手順で作成した「User 3」を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="5c26d-126">手順 2: 特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="5c26d-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="5c26d-127">既定の承認者グループを使用して Microsoft 365 で特権アクセスを明示的に有効にする必要があります。また、特権アクセス管理アクセス制御から除外する必要のあるシステムアカウントのセットが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c26d-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="5c26d-128">このガイドのフェーズ3を開始する前に、必ず組織で特権アクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="5c26d-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="5c26d-129">フェーズ 3: 昇格された権限のあるタスクに承認が必要であることを確認する</span><span class="sxs-lookup"><span data-stu-id="5c26d-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="5c26d-130">このフェーズでは、特権アクセスポリシーが機能していること、および定義された昇格した権限のあるタスクを実行するためにユーザーに承認が必要であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="5c26d-131">特権アクセスポリシーで定義されていないタスクを実行する機能をテストする</span><span class="sxs-lookup"><span data-stu-id="5c26d-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="5c26d-132">最初に、テスト環境で全体管理者として構成されているユーザーの資格情報を使用して Exchange 管理 PowerShell に接続し、新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="5c26d-133">[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule)タスクは、現在、組織の特権アクセスポリシーでは定義されていません。</span><span class="sxs-lookup"><span data-stu-id="5c26d-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="5c26d-134">ローカルコンピューターで、 **Microsoft Corporation**  >  テスト環境のグローバル管理者アカウントを使用して、microsoft Corporation の exchange online リモート powershell モジュールにサインインし、microsoft**exchange online**リモート powershell モジュールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5c26d-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="5c26d-135">Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="5c26d-136">Exchange 管理 PowerShell で新しいジャーナルルールが正常に作成されたことを表示します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="5c26d-137">New-JournalRule タスクの新しい特権アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="5c26d-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="5c26d-138">このガイドのフェーズ2の手順1と2をまだ完了していない場合は、「権限アクセス承認者」という名前の承認者グループを作成する手順に従って、テスト環境での特権アクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="5c26d-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="5c26d-139">資格情報を使用して [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。テスト環境のグローバル管理者アカウントです。</span><span class="sxs-lookup"><span data-stu-id="5c26d-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="5c26d-140">管理センターで、[**設定**  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="5c26d-141">[ **アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="5c26d-142">[ **構成ポリシー**] を選択し、[ **ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="5c26d-143">ドロップダウンフィールドで、次の値を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="5c26d-144">**ポリシーの種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="5c26d-144">**Policy type**: Task</span></span>

    <span data-ttu-id="5c26d-145">**ポリシースコープ**: 交換</span><span class="sxs-lookup"><span data-stu-id="5c26d-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="5c26d-146">**ポリシー名**: 新しいジャーナルルール</span><span class="sxs-lookup"><span data-stu-id="5c26d-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="5c26d-147">**承認の種類**: 手動</span><span class="sxs-lookup"><span data-stu-id="5c26d-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="5c26d-148">**承認グループ**: 特権アクセス承認者</span><span class="sxs-lookup"><span data-stu-id="5c26d-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="5c26d-149">[ **作成**] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="5c26d-150">ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c26d-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="5c26d-151">次の手順で承認の要件をテストする前に、ポリシーが完全に有効になるまでの時間を確保してください。</span><span class="sxs-lookup"><span data-stu-id="5c26d-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="5c26d-152">特権アクセスポリシーで定義された New-JournalRule タスクのテスト承認要件</span><span class="sxs-lookup"><span data-stu-id="5c26d-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="5c26d-153">ローカルコンピューターで、 **Microsoft Corporation**  >  テスト環境のグローバル管理者アカウントを使用して、microsoft Corporation の exchange online リモート powershell モジュールを開き、microsoft**exchange online リモート**powershell モジュールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5c26d-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="5c26d-154">Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="5c26d-155">Exchange 管理 PowerShell で "権限が不足しています" というエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="5c26d-156">New-JournalRule タスクを使用して新しいジャーナルルールを作成するためのアクセス権を要求する</span><span class="sxs-lookup"><span data-stu-id="5c26d-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="5c26d-157">テスト環境のグローバル管理者アカウントを使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5c26d-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="5c26d-158">管理センターで、[**設定**  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="5c26d-159">[ **アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="5c26d-160">[ **新しい要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-160">Select **New request**.</span></span> <span data-ttu-id="5c26d-161">ドロップダウンフィールドで、組織に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="5c26d-162">**要求の種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="5c26d-162">**Request type**: Task</span></span>

    <span data-ttu-id="5c26d-163">**要求スコープ**: 交換</span><span class="sxs-lookup"><span data-stu-id="5c26d-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="5c26d-164">**要求**: 新しいジャーナルルール</span><span class="sxs-lookup"><span data-stu-id="5c26d-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="5c26d-165">**期間 (時間)**: 2</span><span class="sxs-lookup"><span data-stu-id="5c26d-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="5c26d-166">**コメント**: 新しいジャーナルルールを作成するためのアクセス許可を要求する</span><span class="sxs-lookup"><span data-stu-id="5c26d-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="5c26d-167">[ **保存**] を選択し、[ **閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="5c26d-168">要求は、電子メールを介して承認者のグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5c26d-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="5c26d-169">新しいジャーナルルールの作成に関する特権アクセス要求を承認する</span><span class="sxs-lookup"><span data-stu-id="5c26d-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="5c26d-170">テスト環境のユーザー3の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします (テスト環境の "特権アクセス承認者" セキュリティグループのメンバー)。</span><span class="sxs-lookup"><span data-stu-id="5c26d-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="5c26d-171">管理センターで、[**設定**  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="5c26d-172">[ **アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="5c26d-173">保留中の要求を選択し、[ **承認** ] を選択して、新しいジャーナルルールを作成するためのグローバル管理者アカウントへのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="5c26d-174">グローバル管理者アカウント (要求元のユーザー) は、承認が付与されたことを確認する電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="5c26d-175">New-JournalRule タスクに対する特権アクセスが承認された新しいジャーナルルールを作成するテスト</span><span class="sxs-lookup"><span data-stu-id="5c26d-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="5c26d-176">ローカルコンピューターで、 **Microsoft Corporation**  >  テスト環境のグローバル管理者アカウントを使用して、microsoft Corporation の exchange online リモート powershell モジュールにサインインし、microsoft**exchange online**リモート powershell モジュールにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5c26d-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="5c26d-177">Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="5c26d-178">Exchange 管理 PowerShell で新しいジャーナルルールが正常に作成されたことを表示します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c26d-179">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5c26d-179">Next step</span></span>

<span data-ttu-id="5c26d-180">テスト環境でのその他の [情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c26d-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c26d-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c26d-181">See also</span></span>

[<span data-ttu-id="5c26d-182">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="5c26d-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5c26d-183">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="5c26d-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5c26d-184">エンタープライズドキュメントの Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5c26d-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
