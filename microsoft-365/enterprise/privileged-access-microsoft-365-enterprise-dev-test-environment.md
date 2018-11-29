---
title: Microsoft 365 Enterprise テスト環境の特権アクセスの管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: アクセス権限の管理を有効にするのに Microsoft 365 エンタープライズ テスト環境に対応するこのテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869007"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e1863-103">Microsoft 365 Enterprise テスト環境の特権アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="e1863-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e1863-104">この資料の手順についてで Microsoft 365 エンタープライズ テスト環境でセキュリティを強化するのにはアクセス権限の管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e1863-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e1863-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e1863-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="e1863-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e1863-108">最小要件で軽量な方法でアクセス権限の管理を構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="e1863-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e1863-109">シミュレートされた企業内のアクセス権限の管理を構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="e1863-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1863-p101">アクセス権限管理のテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。ここで提供されている、オプションとしてテストすることができるように権限のアクセス管理と一般的な組織を表す環境で実験します。</span><span class="sxs-lookup"><span data-stu-id="e1863-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="e1863-112">フェーズ 2: アクセス権限の管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="e1863-p102">このフェーズでは、承認者グループの構成し、Microsoft 365 エンタープライズ テスト環境のアクセス権限の管理を有効にします。詳細および特権の概要の管理にアクセス、 [Office 365 にアクセス権限の管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1863-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="e1863-115">設定し、Office 365 の組織内のアクセス権限を使用してこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e1863-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="e1863-116">手順 1: 承認者のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="e1863-p103">特権アクセスの使用を開始する前に、管理者特権、特権を持つタスクにアクセスするための着信方向の要求の承認権限を持ってことを確認します。承認者グループの一部になっているユーザーはアクセス権の要求を承認することになります。これは、Office 365 のメールが有効なセキュリティ グループを作成することによって有効になります。テスト環境で「特権を持つアクセスの承認」をという名前の新しいセキュリティ グループを作成し、、追加の"3" 以前のテスト ラボ ガイドの手順で作成済みのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e1863-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="e1863-121">手順 2: アクセス権限を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e1863-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="e1863-p104">アクセス権限を明示的にオンにする Office 365 の既定の承認者グループとアクセス権限の管理アクセスの制御から除外することがシステム アカウントのセットを含む必要があります。このガイドの第 3 段階を開始する前に Office 365 の組織内のアクセス権限を有効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1863-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="e1863-124">フェーズ 3: は、承認が昇格した特権と特権を持つタスクに必要であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1863-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="e1863-125">このフェーズでは、アクセス権限ポリシーが機能して、そのユーザーが管理者特権、特権の定義済みのタスクを実行するために承認を必要とするを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1863-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="e1863-126">特権のアクセス ポリシーで定義されていないタスクを実行する機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="e1863-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="e1863-p105">まず、テスト環境でグローバル ・ アドミニストレーターとして構成されたユーザーの資格情報を持つ Exchange 管理 PowerShell に接続し、新しいジャーナル ルールを作成しようとしてください。[新規 JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)タスクは、組織の管理者のアクセス ポリシーで現在定義されていません。</span><span class="sxs-lookup"><span data-stu-id="e1863-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="e1863-129">ローカル コンピューターを開き、サインインを Exchange オンライン リモート PowerShell モジュールでは、**米国 Microsoft Corporation** > **Microsoft Exchange Online リモート PowerShell モジュール**のグローバル管理を使用するが、テスト環境を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e1863-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="e1863-130">Exchange 管理 Powershell では、組織の新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="e1863-131">ジャーナル ルールの新規作成されたこと正常に Exchange 管理 PowerShell を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1863-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="e1863-132">新規 JournalRule タスク用の新しいアクセス権限ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="e1863-133">手順 1 と 2 からは、このガイドの第 2 フェーズが完了していない場合、は、「特権のアクセスの承認」という名前の承認者のグループを作成して、テスト環境でのアクセス権限有効にする手順を必ず次にあります。</span><span class="sxs-lookup"><span data-stu-id="e1863-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="e1863-134">テスト環境のグローバル管理者アカウントに資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)に署名します。</span><span class="sxs-lookup"><span data-stu-id="e1863-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="e1863-135">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="e1863-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e1863-136">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1863-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e1863-137">**ポリシーを構成する**を選択し、[**ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1863-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="e1863-138">ドロップ ダウン フィールドから選択または次の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e1863-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="e1863-139">**ポリシーの種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="e1863-139">**Policy type**: Task</span></span>

    <span data-ttu-id="e1863-140">**ポリシーのスコープ**: Exchange</span><span class="sxs-lookup"><span data-stu-id="e1863-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="e1863-141">**ポリシー名**: 新しいジャーナル ルール</span><span class="sxs-lookup"><span data-stu-id="e1863-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="e1863-142">**承認タイプ**: 手動</span><span class="sxs-lookup"><span data-stu-id="e1863-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="e1863-143">**承認グループ**: アクセスの権限を持つ承認者</span><span class="sxs-lookup"><span data-stu-id="e1863-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="e1863-p106">**作成**し、[**閉じる**を選択します。ポリシーを完全に構成し、有効にするのには数分かかる場合があります。承認要件を次の手順でテストする前に完全に有効にするポリシーの時間を確保することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1863-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="e1863-147">特権のアクセス ポリシーで定義されている新しい JournalRule タスクの承認要件をテストします。</span><span class="sxs-lookup"><span data-stu-id="e1863-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="e1863-148">ローカル コンピューターを開き、サインインを Exchange オンライン リモート PowerShell モジュールでは、**米国 Microsoft Corporation** > テスト用アカウントの**Microsoft Exchange Online リモート PowerShell モジュール**を使用してグローバル管理者を使用して環境です。</span><span class="sxs-lookup"><span data-stu-id="e1863-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="e1863-149">Exchange 管理 Powershell では、組織の新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="e1863-150">Exchange 管理 PowerShell の"「アクセス許可不十分です。 のエラーをを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1863-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="e1863-151">新規 JournalRule タスクを使用して、新しいジャーナル ルールを作成するアクセス権の要求</span><span class="sxs-lookup"><span data-stu-id="e1863-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="e1863-152">テスト環境のグローバル管理者アカウントを使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e1863-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="e1863-153">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="e1863-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e1863-154">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1863-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e1863-p107">**新しい要求**を選択します。ドロップ ダウン フィールドから、組織の適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1863-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="e1863-157">**要求の種類**: タスク</span><span class="sxs-lookup"><span data-stu-id="e1863-157">**Request type**: Task</span></span>

    <span data-ttu-id="e1863-158">**要求スコープ**: Exchange</span><span class="sxs-lookup"><span data-stu-id="e1863-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="e1863-159">**要求**: 新しいジャーナル ルール</span><span class="sxs-lookup"><span data-stu-id="e1863-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="e1863-160">**期間 (時間)**: 2</span><span class="sxs-lookup"><span data-stu-id="e1863-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="e1863-161">**コメント**: 新しいジャーナル ルールを作成するアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="e1863-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="e1863-p108">**保存**し、**閉じる**を選択します。要求は、電子メールでの承認者のグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e1863-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="e1863-164">新しいジャーナル ルールを作成するためのアクセス権限の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="e1863-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="e1863-165">ユーザー 3 のテスト環境 (テスト環境で"特権を持つアクセスを承認者] セキュリティ グループのメンバー) の資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e1863-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="e1863-166">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="e1863-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e1863-167">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1863-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e1863-p109">保留中の要求を選択し、[新しい仕訳ルールを作成するのにはグローバル管理者アカウントへのアクセスを許可する**承認**を選択します。承認が与えられていることを確認通知メールは、グローバル管理者アカウント (要求元のユーザー) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e1863-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="e1863-170">新規 JournalRule タスクの承認のアクセス権限を持つ新しいジャーナル ルールを作成するテスト</span><span class="sxs-lookup"><span data-stu-id="e1863-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="e1863-171">ローカル コンピューターを開き、サインインを Exchange オンライン リモート PowerShell モジュールでは、**米国 Microsoft Corporation** > **Microsoft Exchange Online リモート PowerShell モジュール**のグローバル管理を使用するが、テスト環境を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e1863-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="e1863-172">Exchange 管理 Powershell では、組織の新しいジャーナル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e1863-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="e1863-173">ジャーナル ルールの新規作成されたこと正常に Exchange 管理 PowerShell を表示します。</span><span class="sxs-lookup"><span data-stu-id="e1863-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1863-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1863-174">Next step</span></span>

<span data-ttu-id="e1863-175">追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1863-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1863-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1863-176">See also</span></span>

[<span data-ttu-id="e1863-177">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e1863-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e1863-178">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="e1863-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e1863-179">Microsoft 365 Enterprise のドキュメントとリソース</span><span class="sxs-lookup"><span data-stu-id="e1863-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)