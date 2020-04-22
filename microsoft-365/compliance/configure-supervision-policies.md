---
title: 監督ポリシーを構成する
description: Office 365 の通信監督を構成する
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.openlocfilehash: 2935f6d163a954cf17e4e4ce3c357028c9763b3b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632372"
---
# <a name="configure-supervision-policies-in-office-365"></a><span data-ttu-id="f4e23-103">Office 365 で監督ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f4e23-103">Configure supervision policies in Office 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="f4e23-104">このトピックは、Microsoft 365 サブスクリプションの監督ポリシーを構成する場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-104">This topic applies to configuring supervision policies in a Microsoft 365 subscription.</span></span> <span data-ttu-id="f4e23-105">Microsoft 365 サブスクリプションの通信コンプライアンスを構成する場合は、「 [microsoft 365 で通信コンプライアンスを構成](communication-compliance-configure.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4e23-105">If you want to configure communications compliance for a Microsoft 365 subscription, see [Configure communications compliance in Microsoft 365](communication-compliance-configure.md).</span></span>

<span data-ttu-id="f4e23-106">監督ポリシーを使って、内部レビューまたは外部レビューによる調査のために従業員の通信をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-106">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="f4e23-107">監督ポリシーが組織内の通信を監視する方法の詳細については、「[Office 365 の監督ポリシー](supervision-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4e23-107">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

>[!NOTE]
><span data-ttu-id="f4e23-108">監督ポリシーによって監視されるユーザーは、Microsoft 365 E5 コンプライアンスライセンス、Advanced コンプライアンスアドオンを備えた Office 365 Enterprise E3 ライセンス、または Office 365 Enterprise E5 サブスクリプションに含まれているか、Microsoft の 365 E5 サブスクリプションに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-108">Users monitored by supervision policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription, or be included in a Microsoft 365 E5 subscription.</span></span>
><span data-ttu-id="f4e23-109">既存の E5 プランを利用しておらず、監督をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップしてください](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="f4e23-109">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="f4e23-110">組織内で監督を設定して使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-110">Follow these steps to set up and use supervision in your organization:</span></span>
  
- <span data-ttu-id="f4e23-111">**手順 1 (オプション)**: [監督用のグループを設定する](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="f4e23-111">**Step 1 (optional)**: [Set up groups for supervision](#step-1-set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="f4e23-112">監督ポリシーの使用を開始する前に、通信のレビューが必要なユーザーおよびレビューを実行するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-112">Before you start using supervision policies, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="f4e23-113">少数のユーザーから始めて監督の機能を確認する場合は、グループの設定をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-113">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="f4e23-114">**手順 2 (必須)**: [組織で監督機能を使用できるようにする](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="f4e23-114">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="f4e23-115">自分がポリシーを設定できるように、自分を監督レビューの役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-115">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="f4e23-116">この役割が割り当てられているすべてのユーザーは、セキュリティ & コンプライアンスセンターの [**監督**] ページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-116">Anyone who has this role assigned can access the **Supervision** page in the Security & Compliance Center.</span></span> <span data-ttu-id="f4e23-117">レビュー可能なメールが Exchange Online でホストされている場合、各レビュー担当者は [Exchange Online へのリモート PowerShell アクセス](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4e23-117">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f4e23-118">**手順 3 (オプション)**: [カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="f4e23-118">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="f4e23-119">監督ポリシーにカスタムの機密情報の種類またはカスタム キーワードディクショナリが必要な場合は、監督ウィザードを開始する前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-119">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="f4e23-120">**手順 4 (必須)**: [監督ポリシーを設定する](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="f4e23-120">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="f4e23-121">監督ポリシーは、セキュリティ & コンプライアンスセンターで作成します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-121">You create supervision policies in the Security & Compliance Center.</span></span> <span data-ttu-id="f4e23-122">監督ポリシーでは、組織でレビュー対象の通信を定義し、レビューを実行するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-122">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="f4e23-123">通信には、メール、Microsoft Teams の通信、およびサードパーティ製のプラットフォームの通信 (Facebook、Twitter など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-123">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.).</span></span> <span data-ttu-id="f4e23-124">組織で作成された監督ポリシーは、Microsoft 365 サブスクリプションの通信監督ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f4e23-124">Supervision policies created in organizations are not supported in communication supervision in Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="f4e23-125">**手順 5**: [通信監督ポリシーをテストする](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="f4e23-125">**Step 5 (optional)**: [Test your communication supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="f4e23-126">監督ポリシーをテストして、期待どおりに機能するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-126">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="f4e23-127">コンプライアンス戦略が標準を満たしていることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f4e23-127">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="f4e23-128">手順 1: 監督用のグループを設定する (オプション)</span><span class="sxs-lookup"><span data-stu-id="f4e23-128">Step 1: Set up groups for supervision (optional)</span></span>

 <span data-ttu-id="f4e23-129">監督ポリシーを作成するときには、通信がスキャンされるユーザーおよびレビューを実行するユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-129">When you create a supervision policy, you define who has their communications scanned and who performs reviews.</span></span> <span data-ttu-id="f4e23-130">ポリシーでは、メール アドレスを使って、個人または複数人のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-130">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="f4e23-131">設定を簡単にするために、通信をスキャンされるユーザーのグループと、それらの通信をレビューするユーザーのグループを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-131">To simplify your setup, you can create groups for people who have their communication scanned and groups for people who review those communications.</span></span> <span data-ttu-id="f4e23-132">グループを使用している場合は、複数必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-132">If you're using groups, you may need several.</span></span> <span data-ttu-id="f4e23-133">たとえば、2 つの異なるグループ間の通信を監視する場合や、監督対象ではないグループを指定する場合などです。</span><span class="sxs-lookup"><span data-stu-id="f4e23-133">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="f4e23-134">次の表を使用して、組織内のグループに通信監督ポリシーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-134">Use the following chart to help you configure groups in your organization for communication supervision policies:</span></span>

| <span data-ttu-id="f4e23-135">**ポリシー メンバー**</span><span class="sxs-lookup"><span data-stu-id="f4e23-135">**Policy Member**</span></span> | <span data-ttu-id="f4e23-136">**サポートされているグループ**</span><span class="sxs-lookup"><span data-stu-id="f4e23-136">**Supported Groups**</span></span> | <span data-ttu-id="f4e23-137">**サポートされていないグループ**</span><span class="sxs-lookup"><span data-stu-id="f4e23-137">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="f4e23-138">監督対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="f4e23-138">Supervised users</span></span> <br> <span data-ttu-id="f4e23-139">非監督対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="f4e23-139">Non-supervised users</span></span> | <span data-ttu-id="f4e23-140">配布グループ</span><span class="sxs-lookup"><span data-stu-id="f4e23-140">Distribution groups</span></span> <br> <span data-ttu-id="f4e23-141">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="f4e23-141">Microsoft 365 groups</span></span> | <span data-ttu-id="f4e23-142">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="f4e23-142">Dynamic distribution groups</span></span> |
| <span data-ttu-id="f4e23-143">レビュー担当者</span><span class="sxs-lookup"><span data-stu-id="f4e23-143">Reviewers</span></span> | <span data-ttu-id="f4e23-144">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="f4e23-144">Mail-enabled security groups</span></span>  | <span data-ttu-id="f4e23-145">配布グループ</span><span class="sxs-lookup"><span data-stu-id="f4e23-145">Distribution groups</span></span> <br> <span data-ttu-id="f4e23-146">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="f4e23-146">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="f4e23-147">監視対象ユーザーに対して Microsoft 365 グループを選択すると、そのグループに関連付けられている共有メールボックスおよび Microsoft Teams チャネルのコンテンツが監視されます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-147">When you select a Microsoft 365 group for supervised users, the policy monitors the content of the shared mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="f4e23-148">配布リストを選択すると、ポリシーは個々のユーザー メールボックスを監視します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-148">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="f4e23-149">大規模な企業組織の監督対象ユーザーを管理するには、大規模なグループ全体のユーザーすべてを監視する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-149">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="f4e23-150">PowerShell を使用して、割り当てられたグループのグローバル監督ポリシーの配布グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-150">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="f4e23-151">これにより、単一のポリシーで数千人のユーザーを監視し、新しい従業員が組織に加入する際に監督ポリシーを最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-151">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="f4e23-152">次のプロパティを使用して、グローバル監督ポリシー専用の[配布グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)を作成します。この配布グループが他の目的または他の Office 365 サービスに使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-152">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="f4e23-153">**MemberDepartRestriction = Closed**。</span><span class="sxs-lookup"><span data-stu-id="f4e23-153">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="f4e23-154">ユーザーが配布グループから自分自身を削除できないようにします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-154">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="f4e23-155">**MemberJoinRestriction = Closed**。</span><span class="sxs-lookup"><span data-stu-id="f4e23-155">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="f4e23-156">ユーザーが配布グループに自分自身を追加できないようにします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-156">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="f4e23-157">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="f4e23-157">**ModerationEnabled = True**.</span></span> <span data-ttu-id="f4e23-158">このグループに送信されるすべてのメッセージが承認の対象となり、監督ポリシー構成の外部との通信にそのグループが使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-158">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="f4e23-159">使用されていない [Exchange カスタム属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)を選択して、組織の監督ポリシーに追加されたユーザーを追跡します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-159">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="f4e23-160">定期的なスケジュールで次の PowerShell スクリプトを実行して、ユーザーを監督ポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-160">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="f4e23-161">グループの設定の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4e23-161">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="f4e23-162">配布グループを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="f4e23-162">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="f4e23-163">メールが有効なセキュリティ グループの管理</span><span class="sxs-lookup"><span data-stu-id="f4e23-163">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="f4e23-164">Microsoft 365 グループの概要</span><span class="sxs-lookup"><span data-stu-id="f4e23-164">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="f4e23-165">手順 2: 組織で監督機能を使用できるようにする (必須)</span><span class="sxs-lookup"><span data-stu-id="f4e23-165">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="f4e23-166">セキュリティ & コンプライアンスセンターで、**監督**をメニューオプションとして利用できるようにするには、監督レビュー管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-166">To make **Supervision** available as a menu option in Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="f4e23-167">そのためには、自分自身を監督レビュー役割グループのメンバーとして追加するか、役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-167">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="f4e23-168">監督レビュー役割グループにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="f4e23-168">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="f4e23-169">組織内[https://protection.office.com](https://protection.office.com)の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-169">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f4e23-170">[セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-170">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="f4e23-171">[**監督レビュー**] 役割グループを選び、編集アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-171">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="f4e23-172">[**メンバー**] セクションで、組織の通信監督を管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-172">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="f4e23-173">新しい役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="f4e23-173">Create a new role group</span></span>

1. <span data-ttu-id="f4e23-174">組織内[https://protection.office.com/permissions](https://protection.office.com/permissions)の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-174">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f4e23-175">[セキュリティ & コンプライアンスセンター] で、[**アクセス許可**] に移動し**+**、[追加] () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-175">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="f4e23-176">[**役割**] セクションで、[追加] (**+**) をクリックし、[**監督レビュー管理者**] までスクロールします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-176">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="f4e23-177">この役割を役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-177">Add this role to the role group.</span></span>

4. <span data-ttu-id="f4e23-178">[**メンバー**] セクションで、組織の通信監督を管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-178">In the **Members** section, add the people who you want to manage communication supervision for your organization.</span></span>

<span data-ttu-id="f4e23-179">役割グループとアクセス許可の詳細については、「[Permissions in the Compliance Center (コンプライアンス センターのアクセス許可)](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください。 </span><span class="sxs-lookup"><span data-stu-id="f4e23-179">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="f4e23-180">レビュー担当者のリモート PowerShell アクセスを有効にします (メールが Exchange Online でホストされている場合)</span><span class="sxs-lookup"><span data-stu-id="f4e23-180">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="f4e23-181">「[Exchange Online PowerShell へのアクセスを有効または無効にする](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)」のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="f4e23-181">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="f4e23-182">手順 3: カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う (オプション)</span><span class="sxs-lookup"><span data-stu-id="f4e23-182">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="f4e23-183">監督ポリシー ウィザードで既存のカスタム機密情報の種類またはカスタム キーワード ディクショナリから選択するには、最初にこれらのアイテムを必要に応じて作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-183">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="f4e23-184">カスタム キーワード ディクショナリ/語彙の作成 (オプション)</span><span class="sxs-lookup"><span data-stu-id="f4e23-184">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="f4e23-185">テキスト エディター (メモ帳など) を使用して、監督ポリシーで監視するキーワード用語を含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-185">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="f4e23-186">各用語が別の行にあることを確認し、**Unicode/UTF-16 (リトル エンディアン)** 形式でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-186">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="f4e23-187">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="f4e23-187">Create custom sensitive information types</span></span>

1. <span data-ttu-id="f4e23-188">新しい機密情報の種類を作成し、セキュリティ & コンプライアンスセンターでユーザー辞書を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-188">Create a new sensitive information type and add your custom dictionary in the Security & Compliance Center.</span></span> <span data-ttu-id="f4e23-189">[**分類**] \> [**機密情報タイプ**] の順に移動し、**新しい機密情報の種類ウィザード**の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f4e23-189">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="f4e23-190">ここで、以下の操作をします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-190">Here you will:</span></span>

    - <span data-ttu-id="f4e23-191">機密情報の種類の名前と説明を定義する</span><span class="sxs-lookup"><span data-stu-id="f4e23-191">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="f4e23-192">近接性、信頼度、プライマリ パターン要素を定義する</span><span class="sxs-lookup"><span data-stu-id="f4e23-192">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="f4e23-193">一致する要素の要件としてユーザー ディクショナリをインポートする</span><span class="sxs-lookup"><span data-stu-id="f4e23-193">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="f4e23-194">選択内容を確認し、機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="f4e23-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="f4e23-195">詳細については、「[カスタム機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」および「[キーワード ディクショナリの作成](create-a-keyword-dictionary.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="f4e23-195">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="f4e23-196">カスタム ディクショナリ/語彙を作成したら、[Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) コマンドレットで構成済みのキーワードを表示したり、[Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) コマンドレットを使用して用語を追加および削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-196">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="f4e23-197">手順 4: 監督ポリシーを設定する (必須)</span><span class="sxs-lookup"><span data-stu-id="f4e23-197">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="f4e23-198">組織内[https://protection.office.com](https://protection.office.com)の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-198">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f4e23-199">[セキュリティ & コンプライアンスセンター] で、[**監督**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-199">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="f4e23-200">[**作成**] を選択し、ウィザードに従ってポリシー構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-200">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="f4e23-201">ウィザードを使用して、以下の操作をします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-201">Using the wizard, you will:</span></span>

    - <span data-ttu-id="f4e23-202">ポリシーに名前と説明を付けます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-202">Give the policy a name and description.</span></span>
    - <span data-ttu-id="f4e23-203">除外するユーザーやグループの選択などを含めて、監督するユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-203">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="f4e23-204">監督ポリシーの[条件](supervision-policies.md#ConditionalSettings)を定義します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-204">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="f4e23-205">[メッセージ アドレス]、[キーワード]、[ファイルの種類]、および [サイズの一致条件] の中から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-205">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="f4e23-206">機密情報の種類を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-206">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="f4e23-207">ここで、既定およびカスタムの機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-207">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="f4e23-208">不快感を与える言語のモデルを有効にするかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-208">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="f4e23-209">これにより、メール メッセージの本文で送受信された不適切な言語が検出されます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-209">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="f4e23-210">レビューする通信の割合を定義します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-210">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="f4e23-211">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-211">Choose the reviewers for the policy.</span></span> <span data-ttu-id="f4e23-212">レビュー担当者は個々のユーザーか、[メールが有効なセキュリティ グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)です。</span><span class="sxs-lookup"><span data-stu-id="f4e23-212">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="f4e23-213">すべてのレビュー担当者は、Exchange Online でホストされているメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-213">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="f4e23-214">選択したポリシーを確認し、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-214">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="f4e23-215">手順 5: 監督ポリシーをテストする (オプション)</span><span class="sxs-lookup"><span data-stu-id="f4e23-215">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="f4e23-216">通信監督ポリシーを作成したら、定義した条件がポリシーによって適切に実施されていることを確認するためのテストの実施をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-216">After you create a communication supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="f4e23-217">監督ポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテストする](create-test-tune-dlp-policy.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-217">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="f4e23-218">以下の手順に従って、監督ポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-218">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="f4e23-219">テストするポリシーで定義されている監督対象ユーザーとしてログインしているメール クライアントまたは Microsoft Teams を開きます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-219">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="f4e23-220">監督ポリシーで定義した条件を満たすメールまたは Microsoft Teams チャットを送信します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-220">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="f4e23-221">これは、キーワード、添付ファイルのサイズ、ドメインなどです。ポリシーで構成された条件設定が厳しすぎる、または緩すぎるかどうかを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="f4e23-221">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f4e23-222">定義されたポリシーの対象となるメールはほぼリアルタイムで処理され、ポリシーの構成後すぐにテストできます。</span><span class="sxs-lookup"><span data-stu-id="f4e23-222">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="f4e23-223">Microsoft Teams のチャットは、ポリシーで完全に処理されるまでに最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4e23-223">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="f4e23-224">コミュニケーション監督ポリシーで指定されたレビュー担当者として Microsoft 365 にログインします。</span><span class="sxs-lookup"><span data-stu-id="f4e23-224">Log into Microsoft 365 as a reviewer designated in the communication supervision policy.</span></span> <span data-ttu-id="f4e23-225">[**監督**]  >  [*カスタム ポリシー*]  >  [**開く**] の順に移動して、ポリシーのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="f4e23-225">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

