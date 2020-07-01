---
title: 特権アクセス管理の使用を開始する
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Office 365 での特権アクセス管理の有効化と構成の詳細については、この記事を使用してください。
ms.openlocfilehash: 4bae6d311b3447534165ee803d7094e5797a9b1c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936322"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="97e1e-103">特権アクセス管理の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="97e1e-103">Get started with privileged access management</span></span>

<span data-ttu-id="97e1e-104">このトピックでは、組織で特権アクセス管理を有効にして構成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="97e1e-105">Microsoft 365 管理センターまたは Exchange 管理 PowerShell のいずれかを使用して、特権アクセスを管理および使用することができます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="97e1e-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="97e1e-106">Before you begin</span></span>

<span data-ttu-id="97e1e-107">特権アクセス管理を使い始める前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)とアドオンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="97e1e-108">特権アクセス管理にアクセスして使用するには、組織が次のいずれかのサブスクリプションまたはアドオンを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="97e1e-109">Microsoft 365 E5 サブスクリプション (有料または試用版)</span><span class="sxs-lookup"><span data-stu-id="97e1e-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="97e1e-110">Microsoft 365 E3 サブスクリプション (または Office 365 E3 サブスクリプション + Enterprise Mobility and Security E3 サブスクリプション) + Microsoft 365 E5 コンプライアンスアドオン</span><span class="sxs-lookup"><span data-stu-id="97e1e-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="97e1e-111">Microsoft 365、Office 365、Exchange、SharePoint、または OneDrive for Business のサブスクリプション + Microsoft 365 E5 Insider リスク管理アドオン</span><span class="sxs-lookup"><span data-stu-id="97e1e-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="97e1e-112">Microsoft 365 A5 サブスクリプション (有料または試用版)</span><span class="sxs-lookup"><span data-stu-id="97e1e-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="97e1e-113">Microsoft 365 A3 サブスクリプション (または Office 365 A3 サブスクリプション + Enterprise Mobility and Security A3 サブスクリプション) + Microsoft A5 コンプライアンスアドオン</span><span class="sxs-lookup"><span data-stu-id="97e1e-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="97e1e-114">任意の Microsoft 365、Office 365、Exchange、SharePoint、または OneDrive for エデュケーションサブスクリプション + Microsoft 365 A5 Insider リスク管理アドオン</span><span class="sxs-lookup"><span data-stu-id="97e1e-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="97e1e-115">Office 365 Enterprise E5 サブスクリプション (有料または試用版)</span><span class="sxs-lookup"><span data-stu-id="97e1e-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="97e1e-116">Office 365 Enterprise E3 サブスクリプション + Office 365 Advanced コンプライアンスアドオン (新しいサブスクリプションでは使用できなくなりました)。メモを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97e1e-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="97e1e-117">特権アクセス管理要求を送信および応答するユーザーには、上記のいずれかのライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="97e1e-118">Office 365 Advanced コンプライアンスは、スタンドアロンサブスクリプションとして販売されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="97e1e-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="97e1e-119">現在のサブスクリプションの有効期限が切れた場合、お客様は上記のサブスクリプションのいずれかに移行する必要があります。これには、同じまたは追加のコンプライアンス機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="97e1e-120">既存の Office 365 Enterprise E5 プランを持っておらず、特権アクセス管理を実行する場合は、 [microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)を既存の office 365 サブスクリプションに追加するか、Microsoft 365 Enterprise E5 の[試用版にサインアップ](https://www.microsoft.com/microsoft-365/enterprise)することができます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="97e1e-121">特権アクセス管理を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="97e1e-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="97e1e-122">次の手順に従って、組織内で特権アクセスを設定して使用します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="97e1e-123">手順 1: 承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="97e1e-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="97e1e-124">特権アクセスの使用を開始する前に、昇格されたタスクおよび権限のあるタスクへのアクセスを要求するための承認権限を必要とするユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="97e1e-125">承認者グループの一部であるユーザーは、アクセス要求を承認することができます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="97e1e-126">このグループを有効にするには、Office 365 でメールが有効なセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="97e1e-127">手順 2: 特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="97e1e-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="97e1e-128">特権アクセスは、既定の承認者グループを使用して Office 365 で明示的に有効にする必要があります。これには、特権アクセス管理アクセス制御から除外する一連のシステム アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="97e1e-129">手順 3: アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="97e1e-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="97e1e-130">承認ポリシーを作成すると、個々のタスクでスコープを設定する特定の承認要件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="97e1e-131">承認の種類のオプションは**自動**または**手動**です。</span><span class="sxs-lookup"><span data-stu-id="97e1e-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="97e1e-132">手順 4: 特権アクセス要求を送信/承認する</span><span class="sxs-lookup"><span data-stu-id="97e1e-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="97e1e-133">有効にすると、特権アクセスは関連付けられた承認ポリシーが定義されているすべてのタスクにて承認が必要になります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="97e1e-134">承認ポリシーに含まれるタスクの場合、タスクを実行するために必要なアクセス権限を持つには、ユーザーはアクセスを要求し、アクセスが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="97e1e-135">承認が与えられると、アクセス要求したユーザーは目的のタスクを実行でき、特権アクセスはユーザーに代わってタスクを承認および実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="97e1e-136">承認は、要求された期間 (既定の期間は 4 時間) にわたって有効で、その間依頼者は目的のタスクを複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="97e1e-137">これらのすべての実行はログに記録され、セキュリティとコンプライアンスの監査で利用されます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="97e1e-138">Exchange 管理 PowerShell を使用して特権アクセスを有効にし、構成する場合は、「[複数要素認証を使用して Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)に接続する」の手順に従って、Office 365 資格情報を使用して Exchange online powershell に接続します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="97e1e-139">Exchange Online PowerShell への接続中に特権アクセスを有効にする手順を使用して、組織で多要素認証を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97e1e-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="97e1e-140">多要素認証を使用して接続すると、要求に署名するために特権アクセスで使用される OAuth トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="97e1e-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="97e1e-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="97e1e-142">手順 1: 承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="97e1e-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="97e1e-143">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="97e1e-144">管理センターで、 **[グループ**  >  **の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="97e1e-145">[**メールが有効なセキュリティグループ**] を選択し、新しいグループの**名前**、**グループ電子メールアドレス**、および**説明**フィールドを入力します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="97e1e-146">グループを保存します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-146">Save the group.</span></span> <span data-ttu-id="97e1e-147"> グループが完全に構成され、Microsoft 365 管理センターに表示するには、数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="97e1e-148">新しい承認者のグループを選択し、[**編集**] を選択してグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="97e1e-149">グループを保存します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-149">Save the group.</span></span>

<span data-ttu-id="97e1e-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="97e1e-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="97e1e-151">手順 2: 特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="97e1e-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-152">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="97e1e-153">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="97e1e-154">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-155">[**権限のあるタスクの承認を必須**にする] コントロールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="97e1e-156">手順1で作成した承認者のグループを**既定の承認者グループ**として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="97e1e-157">**保存**して**閉じ**ます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-158">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-159">特権アクセスを有効にし、承認者のグループを割り当てるには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="97e1e-160">例:</span><span class="sxs-lookup"><span data-stu-id="97e1e-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="97e1e-161">システムアカウント機能を使用して、組織内の特定のオートメーションが特権アクセスに依存せずに機能できるようにすることができます。ただし、そのような除外を定期的に行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="97e1e-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="97e1e-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="97e1e-163">手順 3: アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="97e1e-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="97e1e-164">組織に対して最大30の特権アクセスポリシーを作成し、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-165">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="97e1e-166">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="97e1e-167">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-168">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="97e1e-169">[**ポリシーの構成**] を選択し、[**ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="97e1e-170">ドロップダウンフィールドで、組織に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="97e1e-171">**ポリシーの種類**: タスク、役割、役割グループ</span><span class="sxs-lookup"><span data-stu-id="97e1e-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="97e1e-172">**ポリシースコープ**: 交換</span><span class="sxs-lookup"><span data-stu-id="97e1e-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="97e1e-173">**ポリシー名**: 利用可能なポリシーから選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="97e1e-174">**承認の種類**: 手動または自動</span><span class="sxs-lookup"><span data-stu-id="97e1e-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="97e1e-175">**承認グループ**: 手順 1で作成した承認者グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="97e1e-176">[**作成**] を選択し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="97e1e-177">ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="97e1e-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-178">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-179">承認ポリシーを作成して定義するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="97e1e-180">例:</span><span class="sxs-lookup"><span data-stu-id="97e1e-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="97e1e-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="97e1e-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="97e1e-182">手順 4: 特権アクセス要求を送信/承認する</span><span class="sxs-lookup"><span data-stu-id="97e1e-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="97e1e-183">特権タスクを実行するための昇格認証の要求</span><span class="sxs-lookup"><span data-stu-id="97e1e-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="97e1e-184">特権アクセスの要求は、要求が送信されてから最大24時間有効です。</span><span class="sxs-lookup"><span data-stu-id="97e1e-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="97e1e-185">承認または拒否されない場合、要求は期限切れになり、アクセスは承認されません。</span><span class="sxs-lookup"><span data-stu-id="97e1e-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-186">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="97e1e-187">資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="97e1e-188">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-189">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="97e1e-190">[**新しい要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-190">Select **New request**.</span></span> <span data-ttu-id="97e1e-191">ドロップダウンフィールドで、組織に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="97e1e-192">**要求の種類**: タスク、役割、役割グループ</span><span class="sxs-lookup"><span data-stu-id="97e1e-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="97e1e-193">**要求スコープ**: 交換</span><span class="sxs-lookup"><span data-stu-id="97e1e-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="97e1e-194">**要求名**: 利用可能なポリシーから選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="97e1e-195">**期間 (時間)**: アクセスを希望する時間数。</span><span class="sxs-lookup"><span data-stu-id="97e1e-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="97e1e-196">要求可能な時間数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="97e1e-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="97e1e-197">**Comments**: アクセス要求に関連するコメントのテキストフィールド</span><span class="sxs-lookup"><span data-stu-id="97e1e-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="97e1e-198">[**保存**] を選択し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="97e1e-199">要求は、電子メールを介して承認者のグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-200">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-201">Exchange Online PowerShell で次のコマンドを実行して、承認要求を作成し、承認者のグループに送信します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="97e1e-202">例:</span><span class="sxs-lookup"><span data-stu-id="97e1e-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="97e1e-203">昇格要求の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="97e1e-203">View status of elevation requests</span></span>

<span data-ttu-id="97e1e-204">承認要求が作成されると、昇格要求の状態は、管理センターまたは Exchange 管理 PowerShell で、関連付けられている要求 ID を使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-205">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="97e1e-206">資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="97e1e-207">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-208">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="97e1e-209">[**表示**] を選択して、送信された要求を**保留**、**承認**、**拒否**、または**顧客のロックボックス**の状態でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-210">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-211">Exchange Online PowerShell で次のコマンドを実行して、特定の要求 ID の承認要求の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="97e1e-212">例:</span><span class="sxs-lookup"><span data-stu-id="97e1e-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="97e1e-213">昇格認証要求を承認する</span><span class="sxs-lookup"><span data-stu-id="97e1e-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="97e1e-214">承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知を受信し、要求 ID に関連付けられている要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="97e1e-215">アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-216">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="97e1e-217">資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="97e1e-218">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-219">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="97e1e-220">詳細を表示し、要求に対してアクションを実行するには、リストされている要求を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="97e1e-221">[**承認**] を選択して要求を承認するか、[**拒否**] を選択して要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="97e1e-222">以前に承認された要求では、 **Revoke**を選択することによってアクセスを取り消すことができます</span><span class="sxs-lookup"><span data-stu-id="97e1e-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-223">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-224">昇格認証要求を承認するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="97e1e-225">例:</span><span class="sxs-lookup"><span data-stu-id="97e1e-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="97e1e-226">昇格認証要求を拒否するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="97e1e-227">例:</span><span class="sxs-lookup"><span data-stu-id="97e1e-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="97e1e-228">Office 365 で特権アクセスポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="97e1e-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="97e1e-229">組織で不要になった場合は、特権アクセスポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-230">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="97e1e-231">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="97e1e-232">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-233">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="97e1e-234">[**構成ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="97e1e-235">削除するポリシーを選択し、[ポリシーの**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="97e1e-236">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-237">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-238">特権アクセスポリシーを削除するには、Exchange Online Powershell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="97e1e-239">Office 365 で特権アクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="97e1e-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="97e1e-240">必要に応じて、組織の特権アクセス管理を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="97e1e-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="97e1e-241">特権アクセスを無効にしても、関連付けられている承認ポリシーまたは承認グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="97e1e-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="97e1e-242">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="97e1e-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="97e1e-243">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="97e1e-244">管理センターで、[**設定**] [  >  **組織設定**の  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="97e1e-245">[**特権アクセス制御の承認を必須**にする] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="97e1e-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="97e1e-246">Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="97e1e-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="97e1e-247">特権アクセスを無効にするには、Exchange Online Powershell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="97e1e-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
