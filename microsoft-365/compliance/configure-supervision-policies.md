---
title: 組織の監督ポリシーを設定する
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
description: 監督レビューポリシーを設定して、レビューのために従業員のコミュニケーションをキャプチャします。
ms.openlocfilehash: dae8969598f5a71814c1b61db83341f30c0cb9d7
ms.sourcegitcommit: 8e5b799efd3ddd0eae9dd2835c3783103817fb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "37317619"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="3f381-103">組織の監督ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="3f381-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="3f381-104">監督ポリシーを使用して、内部または外部のレビューアーによる検査のために従業員の通信をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3f381-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="3f381-105">監督ポリシーが組織内の通信を監視するのに役立つ方法の詳細については、「 [Office 365 の監督ポリシー](supervision-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f381-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f381-106">監督ポリシーによって監視されるユーザーは、Microsoft 365 E5 コンプライアンスライセンス、Advanced コンプライアンスアドオンを備えた Office 365 Enterprise E3 ライセンス、または Office 365 Enterprise E5 サブスクリプションに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
> <span data-ttu-id="3f381-107">既存の Enterprise E5 プランを所有しておらず、監督を試みる場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="3f381-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="3f381-108">Office 365 組織の監督をセットアップして使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f381-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="3f381-109">**手順 1 (オプション)**:[監督のグループをセットアップする](#step-1-set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="3f381-109">**Step 1 (optional)**: [Set up groups for Supervision](#step-1-set-up-groups-for-supervision-optional)</span></span> 

    <span data-ttu-id="3f381-110">監督の使用を開始する前に、通信をレビューする必要があるユーザーとレビューを実行するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="3f381-110">Before you start using supervision, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="3f381-111">監督がどのように機能するかを確認するために、少数のユーザーのみを使用して作業を開始する場合は、現時点ではグループの設定を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3f381-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="3f381-112">**手順 2 (必須)**:[組織で監督を利用できるようにする](#step-2-make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="3f381-112">**Step 2 (required)**: [Make supervision available in your organization](#step-2-make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="3f381-113">ポリシーをセットアップできるように、自分を監督レビュー役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f381-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="3f381-114">この役割が割り当てられているすべてのユーザーは、コンプライアンスセンターの [**監督**] ページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f381-114">Anyone who has this role assigned can access the **Supervision** page in the Compliance Center.</span></span> <span data-ttu-id="3f381-115">再表示可能な電子メールが Exchange Online でホストされている場合は、各レビュー担当者が[Exchange online へのリモート PowerShell アクセス権](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-115">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3f381-116">**手順 3 (省略可能)**:[カスタムの機密情報の種類とカスタムキーワードディクショナリを作成する](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="3f381-116">**Step 3 (optional)**: [Create custom sensitive information types and custom keyword dictionaries](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="3f381-117">監督ポリシー用のカスタムの機密情報の種類またはカスタムキーワード辞書が必要な場合は、監督のウィザードを開始する前に、それを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-117">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="3f381-118">**手順 4 (必須)**:[監督ポリシーを設定する](#step-4-set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="3f381-118">**Step 4 (required)**: [Set up a supervision policy](#step-4-set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="3f381-119">監督ポリシーは、コンプライアンスセンターで作成します。</span><span class="sxs-lookup"><span data-stu-id="3f381-119">You create supervision policies in the Compliance Center.</span></span> <span data-ttu-id="3f381-120">これらのポリシーでは、組織内で検討する対象となる通信を定義し、レビューを実行するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f381-120">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="3f381-121">コミュニケーションには、電子メールと Microsoft Teams の通信、およびサードパーティ製のプラットフォーム通信 (Facebook、Twitter など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f381-121">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="3f381-122">**手順 5 (オプション)**:[監督ポリシーをテストする](#step-5-test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="3f381-122">**Step 5 (optional)**: [Test your supervision policy](#step-5-test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="3f381-123">監督ポリシーをテストし、必要に応じて機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f381-123">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="3f381-124">コンプライアンス戦略によって標準が達成されていることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3f381-124">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-supervision-optional"></a><span data-ttu-id="3f381-125">手順 1: 監督のグループをセットアップする (オプション)</span><span class="sxs-lookup"><span data-stu-id="3f381-125">Step 1: Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="3f381-126">監督ポリシーを作成するときに、通信をレビューしたユーザーとレビューを実行するユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="3f381-126">When you create a supervision policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="3f381-127">このポリシーでは、電子メールアドレスを使用して個人またはユーザーのグループを識別します。</span><span class="sxs-lookup"><span data-stu-id="3f381-127">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="3f381-128">セットアップを簡単にするために、コミュニケーションをレビューしたユーザーのためのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3f381-128">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="3f381-129">グループを使用している場合は、複数のが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3f381-129">If you're using groups, you may need several.</span></span> <span data-ttu-id="3f381-130">たとえば、2つの異なるユーザーグループ間の通信を監視する場合、または、監視されないグループを指定する場合などです。</span><span class="sxs-lookup"><span data-stu-id="3f381-130">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="3f381-131">次の表を使用して、監督ポリシー用に組織内のグループを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f381-131">Use the following chart to help you configure groups in your organization for supervision policies:</span></span>

| <span data-ttu-id="3f381-132">**ポリシーメンバー**</span><span class="sxs-lookup"><span data-stu-id="3f381-132">**Policy Member**</span></span> | <span data-ttu-id="3f381-133">**サポートされるグループ**</span><span class="sxs-lookup"><span data-stu-id="3f381-133">**Supported Groups**</span></span> | <span data-ttu-id="3f381-134">**サポートされないグループ**</span><span class="sxs-lookup"><span data-stu-id="3f381-134">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="3f381-135">ユーザーの監視</span><span class="sxs-lookup"><span data-stu-id="3f381-135">Supervised users</span></span> <br> <span data-ttu-id="3f381-136">非監視ユーザー</span><span class="sxs-lookup"><span data-stu-id="3f381-136">Non-supervised users</span></span> | <span data-ttu-id="3f381-137">配布グループ</span><span class="sxs-lookup"><span data-stu-id="3f381-137">Distribution groups</span></span> <br> <span data-ttu-id="3f381-138">[Office 365 グループ]</span><span class="sxs-lookup"><span data-stu-id="3f381-138">Office 365 groups</span></span> | <span data-ttu-id="3f381-139">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="3f381-139">Dynamic distribution groups</span></span> |
| <span data-ttu-id="3f381-140">Reviewers</span><span class="sxs-lookup"><span data-stu-id="3f381-140">Reviewers</span></span> | <span data-ttu-id="3f381-141">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="3f381-141">Mail-enabled security groups</span></span>  | <span data-ttu-id="3f381-142">配布グループ</span><span class="sxs-lookup"><span data-stu-id="3f381-142">Distribution groups</span></span> <br> <span data-ttu-id="3f381-143">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="3f381-143">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="3f381-144">管理対象ユーザー用に Office 365 グループを選択すると、そのグループに関連付けられている共有 Office 365 メールボックスおよび Microsoft Teams チャネルのコンテンツが監視されます。</span><span class="sxs-lookup"><span data-stu-id="3f381-144">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="3f381-145">配布リストを選択すると、ポリシーによって個々のユーザーメールボックスが監視されます。</span><span class="sxs-lookup"><span data-stu-id="3f381-145">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="3f381-146">大規模なエンタープライズ組織での管理対象ユーザーを管理するには、大規模なグループのすべてのユーザーを監視する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-146">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="3f381-147">PowerShell を使用して、割り当てられたグループのグローバル監督ポリシーの配布グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f381-147">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="3f381-148">これにより、数千人のユーザーを1つのポリシーで監視し、新しい従業員が組織に参加したときに、監督ポリシーを更新したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f381-148">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="3f381-149">次のプロパティを使用して、グローバル監督ポリシー用の専用の[配布グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)を作成します。この配布グループは、他の目的や他の Office 365 サービスで使用されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3f381-149">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="3f381-150">**MemberDepartRestriction = Closed**。</span><span class="sxs-lookup"><span data-stu-id="3f381-150">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="3f381-151">ユーザーが配布グループから自分自身を削除できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3f381-151">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="3f381-152">**Memberjoinrestriction = Closed**。</span><span class="sxs-lookup"><span data-stu-id="3f381-152">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="3f381-153">ユーザーが自分を配布グループに追加できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3f381-153">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="3f381-154">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="3f381-154">**ModerationEnabled = True**.</span></span> <span data-ttu-id="3f381-155">このグループに送信されるすべてのメッセージが承認され、監督ポリシー構成外との通信にグループが使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f381-155">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. <span data-ttu-id="3f381-156">組織内の監督ポリシーに追加されたユーザーを追跡するには、未使用の[Exchange カスタム属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f381-156">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="3f381-157">次の PowerShell スクリプトを定期的なスケジュールで実行して、ユーザーを監督ポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f381-157">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```
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

<span data-ttu-id="3f381-158">グループのセットアップの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f381-158">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="3f381-159">配布グループを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="3f381-159">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="3f381-160">メールが有効なセキュリティ グループの管理</span><span class="sxs-lookup"><span data-stu-id="3f381-160">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="3f381-161">Office 365 グループの概要</span><span class="sxs-lookup"><span data-stu-id="3f381-161">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a><span data-ttu-id="3f381-162">手順 2: 組織で監督を利用できるようにする (必須)</span><span class="sxs-lookup"><span data-stu-id="3f381-162">Step 2: Make supervision available in your organization (required)</span></span>

<span data-ttu-id="3f381-163">コンプライアンスセンターで、**監督**をメニューオプションとして使用できるようにするには、監督レビュー管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-163">To make **Supervision** available as a menu option in the Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="3f381-164">これを行うには、自分を監督レビュー役割グループのメンバーとして追加するか、役割グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3f381-164">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="3f381-165">監督レビュー役割グループにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="3f381-165">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="3f381-166">Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f381-166">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3f381-167">[コンプライアンスセンター] で、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f381-167">In the Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="3f381-168">[**監督レビュー** ] 役割グループを選択し、[編集] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f381-168">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="3f381-169">[**メンバー** ] セクションで、組織の監督を管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f381-169">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="3f381-170">新しい役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="3f381-170">Create a new role group</span></span>

1. <span data-ttu-id="3f381-171">Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f381-171">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3f381-172">[コンプライアンスセンター] で、[**アクセス許可**] に移動し**+**、[追加] () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f381-172">In the Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="3f381-173">[**役割**] セクションで、[追加**+**] () をクリックし、[**監督レビュー管理者**] まで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="3f381-173">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="3f381-174">この役割を役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f381-174">Add this role to the role group.</span></span>

4. <span data-ttu-id="3f381-175">[**メンバー** ] セクションで、組織の監督を管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f381-175">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="3f381-176">役割グループとアクセス許可の詳細については、「[コンプライアンスセンターのアクセス許可](../security/office-365-security/protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f381-176">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="3f381-177">レビューアーのリモート PowerShell アクセスを有効にする (電子メールが Exchange Online でホストされている場合)</span><span class="sxs-lookup"><span data-stu-id="3f381-177">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="3f381-178">「 [Exchange Online PowerShell へのアクセスを有効または無効](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)にする」のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="3f381-178">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="3f381-179">手順 3: カスタムの機密情報の種類とカスタムのキーワードディクショナリを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="3f381-179">Step 3: Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="3f381-180">監督ポリシーウィザードで既存のカスタムの機密情報の種類またはカスタムキーワードディクショナリから選択するには、最初に、必要に応じてこれらの項目を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-180">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="3f381-181">ユーザー設定のキーワード辞書/辞書を作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="3f381-181">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="3f381-182">メモ帳などのテキストエディターを使用して、監督ポリシーで監視するキーワード用語を含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f381-182">Use a text editor (like Notepad), to create a file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="3f381-183">各用語が別々の行にあることを確認し、 **Unicode/utf-16 (リトルエンディアン)** 形式でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3f381-183">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="3f381-184">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="3f381-184">Create custom sensitive information types</span></span>

1. <span data-ttu-id="3f381-185">新しい機密情報の種類を作成し、Office 365 セキュリティ & コンプライアンスセンターでユーザー辞書を追加します。</span><span class="sxs-lookup"><span data-stu-id="3f381-185">Create a new sensitive information type and add your custom dictionary in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3f381-186">[**分類** \> **機密情報の種類**] に移動し、**新しい機密情報の種類ウィザード**の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3f381-186">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="3f381-187">ここでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f381-187">Here you will:</span></span>

    - <span data-ttu-id="3f381-188">機密情報の種類の名前と説明を定義する</span><span class="sxs-lookup"><span data-stu-id="3f381-188">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="3f381-189">近接、信頼度、およびプライマリパターン要素を定義する</span><span class="sxs-lookup"><span data-stu-id="3f381-189">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="3f381-190">ユーザー辞書を一致要素の要件としてインポートする</span><span class="sxs-lookup"><span data-stu-id="3f381-190">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="3f381-191">選択内容を確認し、機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="3f381-191">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="3f381-192">詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」および「[キーワードディクショナリを作成](create-a-keyword-dictionary.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f381-192">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="3f381-193">ユーザー辞書または辞書を作成した後、 [get-dlpkeyworddictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary)コマンドレットで構成済みのキーワードを表示したり、 [get-dlpkeyworddictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary)コマンドレットを使用して用語を追加および削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f381-193">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4-set-up-a-supervision-policy-required"></a><span data-ttu-id="3f381-194">手順 4: 監督ポリシーを設定する (必須)</span><span class="sxs-lookup"><span data-stu-id="3f381-194">Step 4: Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="3f381-195">Office 365 [https://protection.office.com](https://protection.office.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f381-195">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="3f381-196">[コンプライアンスセンター] で、[**監督**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f381-196">In the Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="3f381-197">[**作成**] を選択し、ウィザードに従ってポリシー構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f381-197">Select **Create** and follow the wizard to set up the policy configuration.</span></span> <span data-ttu-id="3f381-198">ウィザードを使用すると、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3f381-198">Using the wizard, you will:</span></span>

    - <span data-ttu-id="3f381-199">ポリシーに名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f381-199">Give the policy a name and description.</span></span>
    - <span data-ttu-id="3f381-200">監督するユーザーまたはグループを選択します。これには、除外するユーザーまたはグループを選択することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f381-200">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="3f381-201">監督ポリシー[条件](supervision-policies.md#ConditionalSettings)を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f381-201">Define the supervision policy [conditions](supervision-policies.md#ConditionalSettings).</span></span> <span data-ttu-id="3f381-202">[メッセージアドレス]、[キーワード]、[ファイルの種類]、および [サイズの一致] の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3f381-202">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="3f381-203">機密情報の種類を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f381-203">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="3f381-204">ここでは、既定およびカスタムの機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3f381-204">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="3f381-205">攻撃的な言語モデルを有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="3f381-205">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="3f381-206">これにより、電子メールメッセージの本文での適切でない言語が検出されます。</span><span class="sxs-lookup"><span data-stu-id="3f381-206">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="3f381-207">レビューする通信の割合を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f381-207">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="3f381-208">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f381-208">Choose the reviewers for the policy.</span></span> <span data-ttu-id="3f381-209">レビュー担当者は、個々のユーザーまたは[メールが有効なセキュリティグループに](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)することができます。</span><span class="sxs-lookup"><span data-stu-id="3f381-209">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="3f381-210">すべての校閲者が Exchange Online でホストされたメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-210">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="3f381-211">ポリシーの選択を確認し、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f381-211">Review your policy selections and create the policy.</span></span>

## <a name="step-5-test-your-supervision-policy-optional"></a><span data-ttu-id="3f381-212">手順 5: 監督ポリシーをテストする (オプション)</span><span class="sxs-lookup"><span data-stu-id="3f381-212">Step 5: Test your supervision policy (optional)</span></span>

<span data-ttu-id="3f381-213">監督ポリシーを作成したら、定義した条件がポリシーによって適切に適用されているかどうかをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f381-213">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="3f381-214">監督ポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテスト](create-test-tune-dlp-policy.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f381-214">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="3f381-215">監督ポリシーをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f381-215">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="3f381-216">テストするポリシーで定義された、監視対象のユーザーとしてログインした電子メールクライアントまたは Microsoft Teams を開きます。</span><span class="sxs-lookup"><span data-stu-id="3f381-216">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="3f381-217">監督ポリシーで定義した条件を満たすメールまたは Microsoft Teams のチャットを送信します。</span><span class="sxs-lookup"><span data-stu-id="3f381-217">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="3f381-218">これには、キーワード、添付ファイルのサイズ、ドメインなどを指定できます。ポリシーに構成された条件設定が制限を超えているか、厳しすぎるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3f381-218">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3f381-219">定義されたポリシーの対象となるメールは、ほぼリアルタイムで処理され、ポリシーの構成後すぐにテストできます。</span><span class="sxs-lookup"><span data-stu-id="3f381-219">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="3f381-220">Microsoft Teams でのチャットは、ポリシー内で完全に処理されるまでに最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f381-220">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="3f381-221">監督ポリシーに指定されたレビュー担当者として Office 365 テナントにログインします。</span><span class="sxs-lookup"><span data-stu-id="3f381-221">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="3f381-222">[*カスタムポリシー* > \*\*\*\* の**監視** > ] に移動して、ポリシーのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="3f381-222">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="3f381-223">PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="3f381-223">PowerShell reference</span></span>

<span data-ttu-id="3f381-224">必要に応じて、次の PowerShell コマンドレットを使用して監督ポリシーを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3f381-224">If needed, you can create and manage supervision policies with the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="3f381-225">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3f381-225">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3f381-226">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3f381-226">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3f381-227">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3f381-227">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3f381-228">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="3f381-228">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="3f381-229">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="3f381-229">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="3f381-230">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="3f381-230">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="3f381-231">SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="3f381-231">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="3f381-232">SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="3f381-232">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="3f381-233">SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="3f381-233">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
