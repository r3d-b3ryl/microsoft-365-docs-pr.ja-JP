---
title: エンタープライズ向け Microsoft 365 テスト環境の特権アクセス管理
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
description: このテスト ラボ ガイドを使用して、エンタープライズ 向け Microsoft 365 テスト環境で特権アクセス管理を有効にしてください。
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126419"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="900d0-103">エンタープライズ向け Microsoft 365 テスト環境の特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="900d0-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="900d0-104">*このテスト ラボ ガイドは、Microsoft 365 for enterprise と Office 365 Enterprise テスト環境の両方に使用できます。*</span><span class="sxs-lookup"><span data-stu-id="900d0-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="900d0-105">この記事では、エンタープライズ 向け Microsoft 365 テスト環境のセキュリティを強化するために特権アクセス管理を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="900d0-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="900d0-106">権限を持つアクセス管理を構成するには、次の 3 つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="900d0-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="900d0-107">フェーズ 1: エンタープライズ向け Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="900d0-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="900d0-108">フェーズ 2: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="900d0-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="900d0-109">フェーズ 3: 昇格されたタスクと特権を持つタスクに承認が必要な状態を確認する</span><span class="sxs-lookup"><span data-stu-id="900d0-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="900d0-111">エンタープライズ向け Microsoft 365 のテスト ラボ ガイド スタックのすべての記事のビジュアル マップについては [、Microsoft 365 enterprise テスト](../downloads/Microsoft365EnterpriseTLGStack.pdf)ラボ ガイド スタックにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="900d0-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="900d0-112">フェーズ 1: エンタープライズ向け Microsoft 365 テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="900d0-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="900d0-113">最小要件で特権アクセス管理を軽量な方法で構成する場合は、「ライトウェイト基本構成」の手順 [に従ってください](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="900d0-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="900d0-114">シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="900d0-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="900d0-115">特権アクセス管理をテストする場合、シミュレーションのエンタープライズ テスト環境は必要とされません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメイン サービス フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="900d0-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="900d0-116">ここでは、特権アクセス管理をテストし、一般的な組織を表す環境で試用できるよう、オプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="900d0-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="900d0-117">フェーズ 2: 特権アクセス管理を構成する</span><span class="sxs-lookup"><span data-stu-id="900d0-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="900d0-118">このフェーズでは、承認者グループを構成し、エンタープライズ テスト環境用に Microsoft 365 の特権アクセス管理を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="900d0-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="900d0-119">特権アクセス管理の詳細と概要については、「特権アクセス管理」 [を参照してください](../compliance/privileged-access-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="900d0-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="900d0-120">組織で特権アクセスをセットアップして使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="900d0-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="900d0-121">手順 1: 承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="900d0-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="900d0-122">特権アクセスの使用を開始する前に、管理者特権タスクおよび特権タスクへのアクセス要求を受信する承認機関を持つユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="900d0-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="900d0-123">承認者のグループに含めるすべてのユーザーは、アクセス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="900d0-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="900d0-124">特権アクセスを使用するには、Microsoft 365 でメールが有効なセキュリティ グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="900d0-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="900d0-125">テスト環境で、新しいセキュリティ グループに「Privileged Access Approvers」という名前を付け、以前のテスト ラボ ガイドの手順で作成した "User 3" を追加します。</span><span class="sxs-lookup"><span data-stu-id="900d0-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="900d0-126">手順 2: 特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="900d0-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="900d0-127">既定の承認者グループを使用して Microsoft 365 で特権アクセスを明示的に有効にし、特権アクセス管理アクセス制御から除外する一連のシステム アカウントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="900d0-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="900d0-128">このガイドのフェーズ 3 を開始する前に、組織で特権アクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="900d0-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="900d0-129">フェーズ 3: 昇格されたタスクと特権を持つタスクに承認が必要な状態を確認する</span><span class="sxs-lookup"><span data-stu-id="900d0-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="900d0-130">このフェーズでは、特権アクセス ポリシーが機能し、ユーザーが定義済みの昇格されたタスクと特権タスクを実行するために承認を必要とします。</span><span class="sxs-lookup"><span data-stu-id="900d0-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="900d0-131">特権アクセス ポリシーで定義されていないタスクを実行する機能をテストする</span><span class="sxs-lookup"><span data-stu-id="900d0-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="900d0-132">まず、テスト環境でグローバル管理者として構成されたユーザーの資格情報を使用して Exchange Management PowerShell に接続し、新しいジャーナル ルールの作成を試みる。</span><span class="sxs-lookup"><span data-stu-id="900d0-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="900d0-133">[New-JournalRule](/powershell/module/exchange/new-journalrule)タスクは、現在、組織の特権アクセス ポリシーで定義されていません。</span><span class="sxs-lookup"><span data-stu-id="900d0-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="900d0-134">ローカル コンピューターで、テスト環境のグローバル管理者アカウントを使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート PowerShell モジュールを開いて  >  サインインします。</span><span class="sxs-lookup"><span data-stu-id="900d0-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="900d0-135">Exchange Management PowerShell で、組織の新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="900d0-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="900d0-136">新しいジャーナル ルールが Exchange Management PowerShell で正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="900d0-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="900d0-137">タスクの新しい特権アクセス ポリシーをNew-JournalRuleする</span><span class="sxs-lookup"><span data-stu-id="900d0-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="900d0-138">このガイドのフェーズ 2 の手順 1 と 2 をまだ完了していない場合は、テスト環境で特権アクセスを有効にする "Privilege Access Approvers" という名前の承認者のグループを作成する手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="900d0-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="900d0-139">テスト環境のグローバル管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="900d0-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="900d0-140">In the Admin Center, go to **Settings**  >  **Security & Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="900d0-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="900d0-141">[アクセス **ポリシーと要求の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="900d0-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="900d0-142">[ポリシー **の構成] を選択し**、[ポリシーの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="900d0-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="900d0-143">ドロップダウン フィールドで、次の値を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="900d0-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="900d0-144">**ポリシーの種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="900d0-144">**Policy type**: Task</span></span>

    <span data-ttu-id="900d0-145">**ポリシースコープ**: 交換</span><span class="sxs-lookup"><span data-stu-id="900d0-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="900d0-146">**ポリシー名**: 新しいジャーナル ルール</span><span class="sxs-lookup"><span data-stu-id="900d0-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="900d0-147">**承認の種類**: 手動</span><span class="sxs-lookup"><span data-stu-id="900d0-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="900d0-148">**承認グループ**: 特権アクセス承認者</span><span class="sxs-lookup"><span data-stu-id="900d0-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="900d0-149">**[作成]** を選択してから、**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="900d0-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="900d0-150">ポリシーが完全に構成され、有効になるには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="900d0-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="900d0-151">次の手順で承認要件をテストする前に、ポリシーが完全に有効になる時間を許可してください。</span><span class="sxs-lookup"><span data-stu-id="900d0-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="900d0-152">特権アクセス ポリシーで定義New-JournalRuleタスクのテスト承認要件</span><span class="sxs-lookup"><span data-stu-id="900d0-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="900d0-153">ローカル コンピューターで、テスト環境のグローバル管理者アカウントを使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート PowerShell モジュールを開いてサインイン  >  します。</span><span class="sxs-lookup"><span data-stu-id="900d0-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="900d0-154">Exchange Management PowerShell で、組織の新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="900d0-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="900d0-155">Exchange Management PowerShell で "十分なアクセス許可が不足しています" というエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="900d0-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="900d0-156">タスクを使用して新しいジャーナル ルールを作成するアクセスNew-JournalRuleする</span><span class="sxs-lookup"><span data-stu-id="900d0-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="900d0-157">テスト環境のグローバル管理者アカウントを使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="900d0-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="900d0-158">In the Admin Center, go to **Settings**  >  **Security & Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="900d0-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="900d0-159">[アクセス **ポリシーと要求の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="900d0-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="900d0-160">[新 **しい要求] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="900d0-160">Select **New request**.</span></span> <span data-ttu-id="900d0-161">ドロップダウン フィールドから、組織に適した値を選択します。</span><span class="sxs-lookup"><span data-stu-id="900d0-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="900d0-162">**要求の種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="900d0-162">**Request type**: Task</span></span>

    <span data-ttu-id="900d0-163">**要求スコープ**: 交換</span><span class="sxs-lookup"><span data-stu-id="900d0-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="900d0-164">**要求:** 新しいジャーナル ルール</span><span class="sxs-lookup"><span data-stu-id="900d0-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="900d0-165">**期間 (時間)**: 2</span><span class="sxs-lookup"><span data-stu-id="900d0-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="900d0-166">**コメント**: 新しいジャーナル ルールを作成するためのアクセス許可を要求する</span><span class="sxs-lookup"><span data-stu-id="900d0-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="900d0-167">[保存 **] を** 選択し、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="900d0-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="900d0-168">要求は、承認者のグループに電子メールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="900d0-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="900d0-169">新しいジャーナル ルールを作成する特権アクセス要求を承認する</span><span class="sxs-lookup"><span data-stu-id="900d0-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="900d0-170">テスト環境で User 3 の資格情報を使用して [Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします (テスト環境の "Privileged Access Approvers" セキュリティ グループのメンバー)。</span><span class="sxs-lookup"><span data-stu-id="900d0-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="900d0-171">In the Admin Center, go to **Settings**  >  **Security & Privacy**  >  **Privileged access**.</span><span class="sxs-lookup"><span data-stu-id="900d0-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="900d0-172">[アクセス **ポリシーと要求の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="900d0-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="900d0-173">保留中の要求を選択し、[承認]を選択してグローバル管理者アカウントへのアクセス権を付与し、新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="900d0-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="900d0-174">グローバル管理者アカウント (要求ユーザー) は、承認が許可されたという確認メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="900d0-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="900d0-175">タスクに対して承認された特権アクセスを持つ新しいジャーナル ルールNew-JournalRuleテストする</span><span class="sxs-lookup"><span data-stu-id="900d0-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="900d0-176">ローカル コンピューターで、テスト環境のグローバル管理者アカウントを使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート PowerShell モジュールを開いて  >  サインインします。</span><span class="sxs-lookup"><span data-stu-id="900d0-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="900d0-177">Exchange Management PowerShell で、組織の新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="900d0-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="900d0-178">新しいジャーナル ルールが Exchange Management PowerShell で正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="900d0-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="900d0-179">次の手順</span><span class="sxs-lookup"><span data-stu-id="900d0-179">Next step</span></span>

<span data-ttu-id="900d0-180">テスト環境 [のその他の](m365-enterprise-test-lab-guides.md#information-protection) 情報保護機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="900d0-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="900d0-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="900d0-181">See also</span></span>

[<span data-ttu-id="900d0-182">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="900d0-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="900d0-183">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="900d0-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="900d0-184">Microsoft 365 for enterprise のドキュメント</span><span class="sxs-lookup"><span data-stu-id="900d0-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
