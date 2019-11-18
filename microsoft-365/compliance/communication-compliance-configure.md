---
title: Microsoft 365 の通信コンプライアンスを構成する (プレビュー)
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
description: コミュニケーションコンプライアンスポリシーを設定して、レビューのために従業員の通信を構成します。
ms.openlocfilehash: 76b28443d2fa77967933ea61f2724a2a5ff072be
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "38686682"
---
# <a name="configure-communication-compliance-for-microsoft-365-preview"></a><span data-ttu-id="99d13-103">Microsoft 365 の通信コンプライアンスを構成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="99d13-103">Configure communication compliance for Microsoft 365 (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99d13-104">このトピックは、Microsoft 365 サブスクリプションで通信のコンプライアンスを構成する場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="99d13-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="99d13-105">Office 365 サブスクリプションの監督ポリシーを構成する場合は、「 [configure 監督 For office 365](supervision-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d13-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="99d13-106">コミュニケーションコンプライアンスポリシーを使用して、内部または外部のレビューアーによる調査のために従業員の通信をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="99d13-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="99d13-107">通信コンプライアンスポリシーが組織内の通信の監視にどのように役立つかについては、「 [Microsoft 365 の通信コンプライアンスポリシー](communication-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d13-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

> [!NOTE]
> <span data-ttu-id="99d13-108">通信コンプライアンスポリシーによって監視されるユーザーは、Microsoft 365 E5 コンプライアンスライセンス、Advanced コンプライアンスアドオンを備えた Office 365 Enterprise E3 ライセンス、または Office 365 Enterprise E5 サブスクリプションに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-108">Users monitored by communication compliance policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
> <span data-ttu-id="99d13-109">既存の Enterprise E5 プランを所有しておらず、通信のコンプライアンスを試行したい場合は、 [Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="99d13-109">If you don't have an existing Enterprise E5 plan and want to try communication compliance, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="99d13-110">Microsoft 365 組織の通信コンプライアンスをセットアップして使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99d13-110">Follow these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>
  
- <span data-ttu-id="99d13-111">**手順 1 (省略可能)**:[通信コンプライアンス用にグループをセットアップする](#step-1-set-up-groups-for-communication-compliance-optional)</span><span class="sxs-lookup"><span data-stu-id="99d13-111">**Step 1 (optional)**: [Set up groups for communication compliance](#step-1-set-up-groups-for-communication-compliance-optional)</span></span> 

    <span data-ttu-id="99d13-112">通信コンプライアンスの使用を開始する前に、コミュニケーションをレビューする必要があるユーザーとレビューを実行するユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="99d13-112">Before you start using communication compliance, determine who needs communications reviewed and who performs reviews.</span></span> <span data-ttu-id="99d13-113">通信のコンプライアンスがどのように機能するかを確認するために、少数のユーザーのみを使用して作業を開始する場合は、現時点ではグループの設定を省略できます。</span><span class="sxs-lookup"><span data-stu-id="99d13-113">If you want to get started with just a few users to see how communication compliance works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="99d13-114">**手順 2 (必須)**:[組織内で通信のコンプライアンスを実現できるようにする](#step-2-make-communication-compliance-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="99d13-114">**Step 2 (required)**: [Make communication compliance available in your organization](#step-2-make-communication-compliance-available-in-your-organization-required)</span></span>

    <span data-ttu-id="99d13-115">ポリシーをセットアップできるように、自分を**監督レビュー管理者**ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="99d13-115">Add yourself to the **Supervisory Review Administrator** role so you can set up policies.</span></span> <span data-ttu-id="99d13-116">また、**ケース管理**を割り当てて、ポリシーが一致するメッセージに対する調査と修復アクションを実行するユーザーまたはグループに役割を**レビュー**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-116">You'll also need to assign the **Case Management** and **Review** roles to people or groups that will take investigative and remediation action on messages with policy matches.</span></span> <span data-ttu-id="99d13-117">これらの役割が割り当てられているすべてのユーザーは、Microsoft 365 コンプライアンスセンターの [**通信コンプライアンス**] ページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99d13-117">Anyone who has these roles assigned can access the **Communication compliance** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="99d13-118">再表示可能な電子メールが Exchange Online でホストされている場合は、各レビュー担当者が[Exchange online へのリモート PowerShell アクセス権](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-118">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="99d13-119">**手順 3 (必須)**:[通信コンプライアンスポリシーをセットアップする](#step-3-create-a-communication-compliance-policy-required)</span><span class="sxs-lookup"><span data-stu-id="99d13-119">**Step 3 (required)**: [Set up a communication compliance policy](#step-3-create-a-communication-compliance-policy-required)</span></span>

    <span data-ttu-id="99d13-120">コミュニケーションコンプライアンスポリシーは、Microsoft 365 コンプライアンスセンターで作成します。</span><span class="sxs-lookup"><span data-stu-id="99d13-120">You create communication compliance policies in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="99d13-121">これらのポリシーでは、組織内で検討する対象となる通信を定義し、レビューを実行するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="99d13-121">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="99d13-122">通信には、電子メール、Microsoft Teams、Skype for Business、サードパーティのプラットフォーム間通信 (Facebook、Twitter など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99d13-122">Communications include email, Microsoft Teams, Skype for Business, and 3rd-party platform communications (such as Facebook, Twitter, etc.).</span></span>

- <span data-ttu-id="99d13-123">**手順 4 (省略可能)**:[従業員の通知テンプレートを作成する](#step-4-create-employee-notice-templates-optional)</span><span class="sxs-lookup"><span data-stu-id="99d13-123">**Step 4 (optional)**: [Create employee notice templates](#step-4-create-employee-notice-templates-optional)</span></span>

    <span data-ttu-id="99d13-124">カスタム通知テンプレートを作成して、ポリシー一致の修復オプションとして従業員に電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="99d13-124">Create custom notice templates to send email notifications to employees as a remediation option for policy matches.</span></span>

- <span data-ttu-id="99d13-125">**手順 5 (オプション)**:[通信コンプライアンスポリシーをテストする](#step-5-test-your-communication-compliance-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="99d13-125">**Step 5 (optional)**: [Test your communication compliance policy](#step-5-test-your-communication-compliance-policy-optional)</span></span>

    <span data-ttu-id="99d13-126">通信コンプライアンスポリシーをテストして、必要に応じて機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99d13-126">Test your communication compliance policy to make sure it functions as desired.</span></span> <span data-ttu-id="99d13-127">コンプライアンス戦略によって標準が達成されていることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="99d13-127">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a><span data-ttu-id="99d13-128">手順 1: 通信コンプライアンス用にグループをセットアップする (オプション)</span><span class="sxs-lookup"><span data-stu-id="99d13-128">Step 1: Set up groups for communication compliance (optional)</span></span>

 <span data-ttu-id="99d13-129">通信コンプライアンスポリシーを作成する場合は、通信をレビューしたユーザーとレビューを実行するユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="99d13-129">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="99d13-130">このポリシーでは、電子メールアドレスを使用して個人またはユーザーのグループを識別します。</span><span class="sxs-lookup"><span data-stu-id="99d13-130">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="99d13-131">セットアップを簡単にするために、コミュニケーションをレビューしたユーザーのためのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="99d13-131">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="99d13-132">グループを使用している場合は、複数のが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="99d13-132">If you're using groups, you may need several.</span></span> <span data-ttu-id="99d13-133">たとえば、2つの異なるユーザーグループ間の通信を監視する場合、または、監視されないグループを指定する場合などです。</span><span class="sxs-lookup"><span data-stu-id="99d13-133">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="99d13-134">次の表を使用して、通信コンプライアンスポリシー用に組織内のグループを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99d13-134">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="99d13-135">**ポリシーメンバー**</span><span class="sxs-lookup"><span data-stu-id="99d13-135">**Policy Member**</span></span> | <span data-ttu-id="99d13-136">**サポートされるグループ**</span><span class="sxs-lookup"><span data-stu-id="99d13-136">**Supported Groups**</span></span> | <span data-ttu-id="99d13-137">**サポートされないグループ**</span><span class="sxs-lookup"><span data-stu-id="99d13-137">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="99d13-138">ユーザーの監視</span><span class="sxs-lookup"><span data-stu-id="99d13-138">Supervised users</span></span> <br> <span data-ttu-id="99d13-139">非監視ユーザー</span><span class="sxs-lookup"><span data-stu-id="99d13-139">Non-supervised users</span></span> | <span data-ttu-id="99d13-140">配布グループ</span><span class="sxs-lookup"><span data-stu-id="99d13-140">Distribution groups</span></span> <br> <span data-ttu-id="99d13-141">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="99d13-141">Office 365 groups</span></span> | <span data-ttu-id="99d13-142">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="99d13-142">Dynamic distribution groups</span></span> |
| <span data-ttu-id="99d13-143">Reviewers</span><span class="sxs-lookup"><span data-stu-id="99d13-143">Reviewers</span></span> | <span data-ttu-id="99d13-144">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="99d13-144">Mail-enabled security groups</span></span>  | <span data-ttu-id="99d13-145">配布グループ</span><span class="sxs-lookup"><span data-stu-id="99d13-145">Distribution groups</span></span> <br> <span data-ttu-id="99d13-146">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="99d13-146">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="99d13-147">管理対象ユーザー用に Office 365 グループを選択すると、そのグループに関連付けられている共有 Office 365 メールボックスおよび Microsoft Teams チャネルのコンテンツが監視されます。</span><span class="sxs-lookup"><span data-stu-id="99d13-147">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="99d13-148">配布リストを選択すると、ポリシーによって個々のユーザーメールボックスが監視されます。</span><span class="sxs-lookup"><span data-stu-id="99d13-148">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="99d13-149">グループのセットアップの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d13-149">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="99d13-150">配布グループを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="99d13-150">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="99d13-151">メールが有効なセキュリティ グループの管理</span><span class="sxs-lookup"><span data-stu-id="99d13-151">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="99d13-152">Office 365 グループの概要</span><span class="sxs-lookup"><span data-stu-id="99d13-152">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a><span data-ttu-id="99d13-153">手順 2: 組織で通信のコンプライアンスを実現する (必須)</span><span class="sxs-lookup"><span data-stu-id="99d13-153">Step 2: Make communication compliance available in your organization (required)</span></span>

<span data-ttu-id="99d13-154">Microsoft 365 コンプライアンスセンターのメニューオプションとして**通信のコンプライアンス**を実現するには、監督レビュー管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-154">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the Supervisory Review Administrator role.</span></span> <span data-ttu-id="99d13-155">ポリシーが一致するメッセージを調査および修復するには、**ケースの管理**および**レビュー**の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-155">To investigate and remediate messages with policy matches, you must be assigned the **Case Management** and **Review** roles.</span></span>
  
<span data-ttu-id="99d13-156">これを行うには、自分を監督レビュー役割グループのメンバーとして追加するか、新しい役割グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="99d13-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-required-roles-to-the-supervisory-reviewer-role-group"></a><span data-ttu-id="99d13-157">必要な役割を監督レビューアー役割グループに追加する</span><span class="sxs-lookup"><span data-stu-id="99d13-157">Add required roles to the Supervisory Reviewer role group</span></span>

1. <span data-ttu-id="99d13-158">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="99d13-158">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="99d13-159">Microsoft 365 コンプライアンスセンターで、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="99d13-159">In the Microsoft 365 compliance center, go to **Permissions**.</span></span> <span data-ttu-id="99d13-160">Office 365 で役割を表示および管理するためのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-160">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="99d13-161">[**監督レビュー** ] 役割グループを選択し、[詳細] ページの [**割り当てられた役割**] セクションで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99d13-161">Select the **Supervisory Review** role group and then click **Edit** in the **Assigned roles** section of the details page.</span></span>

4. <span data-ttu-id="99d13-162">[**編集**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-162">Select **Edit**, then select **Add**.</span></span> <span data-ttu-id="99d13-163">[**ケースの管理**と**レビュー**] のチェックボックスをオンにし、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-163">Select the checkbox for **Case Management** and **Review**, then select **Add**.</span></span>

5. <span data-ttu-id="99d13-164">[**完了**] を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-164">Select **Done**, then select **Save**.</span></span>

6. <span data-ttu-id="99d13-165">[**メンバー** ] セクションで、[**編集**] を選択して、組織の通信コンプライアンスを管理するユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="99d13-165">In the **Members** section, select **Edit** to add the people who you want to manage communication compliance for your organization.</span></span>

7. <span data-ttu-id="99d13-166">[**編集**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-166">Select **Edit**, then select **Add**.</span></span> <span data-ttu-id="99d13-167">ポリシーを一致させるメッセージを管理するすべてのユーザーとグループのチェックボックスをオンにし、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-167">Select the checkbox for all the users and groups you want manage messages with policy matches, then select **Add**.</span></span>

8. <span data-ttu-id="99d13-168">[**完了**] を選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-168">Select **Done**, then select **Save**.</span></span>

9. <span data-ttu-id="99d13-169">[**閉じる**] を選択して、役割グループの詳細ページを終了します。</span><span class="sxs-lookup"><span data-stu-id="99d13-169">Select **Close** to exit the role group detail page.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="99d13-170">新しい役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="99d13-170">Create a new role group</span></span>

1. <span data-ttu-id="99d13-171">Office 365 [https://compliance.microsoft.com](https://compliance.microsoft.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="99d13-171">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="99d13-172">Microsoft 365 コンプライアンスセンターで、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="99d13-172">In the Microsoft 365 compliance center, go to **Permissions**.</span></span> <span data-ttu-id="99d13-173">Office 365 で役割を表示および管理するためのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-173">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="99d13-174">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-174">Select **Create**.</span></span>

4. <span data-ttu-id="99d13-175">[**名前**] フィールドに、新しい役割グループにフレンドリ名を付けます。</span><span class="sxs-lookup"><span data-stu-id="99d13-175">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="99d13-176">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-176">Select **Next**.</span></span>

5. <span data-ttu-id="99d13-177">[**役割の選択**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-177">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="99d13-178">[**監督レビュー管理者**]、[**ケースの管理**]、[**レビュー**] のチェックボックスをオンにして、[**追加**と**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-178">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="99d13-179">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-179">Select **Next**.</span></span>

6. <span data-ttu-id="99d13-180">[**メンバーの選択**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-180">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="99d13-181">[ポリシーの作成] と [ポリシーの一致でメッセージを管理する] を使用するすべてのユーザーおよびグループのチェックボックスをオンにし、[**追加** **] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="99d13-181">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="99d13-182">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-182">Select **Next**.</span></span>

7. <span data-ttu-id="99d13-183">[**役割グループの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-183">Select **Create role group** to finish.</span></span>

<span data-ttu-id="99d13-184">役割グループとアクセス許可の詳細については、「[コンプライアンスセンターのアクセス許可](../security/office-365-security/protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99d13-184">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-3-create-a-communication-compliance-policy-required"></a><span data-ttu-id="99d13-185">手順 3: 通信コンプライアンスポリシーを作成する (必須)</span><span class="sxs-lookup"><span data-stu-id="99d13-185">Step 3: Create a communication compliance policy (required)</span></span>
  
1. <span data-ttu-id="99d13-186">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="99d13-186">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="99d13-187">Microsoft 365 コンプライアンスセンターで、[**通信コンプライアンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-187">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="99d13-188">[**ポリシー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-188">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="99d13-189">[**ポリシーの作成**] を選択して、テンプレートから新しいポリシーを作成して構成するか、カスタムポリシーを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="99d13-189">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="99d13-190">ポリシーを作成するポリシーテンプレートを選択する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="99d13-190">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="99d13-191">ポリシー名を確認または更新します。</span><span class="sxs-lookup"><span data-stu-id="99d13-191">Confirm or update the policy name.</span></span> <span data-ttu-id="99d13-192">ポリシー名は、ポリシーの作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="99d13-192">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="99d13-193">監督するユーザーまたはグループを選択します。これには、除外するユーザーまたはグループを選択することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="99d13-193">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="99d13-194">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-194">Choose the reviewers for the policy.</span></span> <span data-ttu-id="99d13-195">レビュー担当者は、個々のユーザーまたは[メールが有効なセキュリティグループに](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)することができます。</span><span class="sxs-lookup"><span data-stu-id="99d13-195">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="99d13-196">すべての校閲者が Exchange Online でホストされたメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-196">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="99d13-197">制限された条件フィールド (通常は、ポリシーに適用する機密情報の種類またはキーワードディクショナリ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-197">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="99d13-198">ポリシーウィザードを使用してカスタムポリシーを作成する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="99d13-198">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="99d13-199">ポリシーに名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="99d13-199">Give the policy a name and description.</span></span> <span data-ttu-id="99d13-200">ポリシー名は、ポリシーの作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="99d13-200">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="99d13-201">監督するユーザーまたはグループを選択します。これには、組織内のすべてのユーザー、特定のユーザーとグループ、または除外する他のユーザーやグループを選択することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="99d13-201">Choose the users or groups to supervise, including choosing all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span> -
    - <span data-ttu-id="99d13-202">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-202">Choose the reviewers for the policy.</span></span> <span data-ttu-id="99d13-203">レビュー担当者は、個々のユーザーまたは[メールが有効なセキュリティグループに](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)することができます。</span><span class="sxs-lookup"><span data-stu-id="99d13-203">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="99d13-204">すべての校閲者が Exchange Online でホストされたメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-204">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="99d13-205">Exchange、Microsoft Teams、Skype for Business など、スキャンする通信チャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-205">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="99d13-206">また、Microsoft 365 でコネクタを構成した場合は、サードパーティのソースをスキャンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="99d13-206">You'll also choose to scan third party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="99d13-207">受信、送信、内部通信など、監視する通信方向を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-207">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="99d13-208">通信コンプライアンスポリシーの[条件](communication-compliance-feature-reference.md#ConditionalSettings)を定義します。</span><span class="sxs-lookup"><span data-stu-id="99d13-208">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="99d13-209">[メッセージアドレス]、[キーワード]、[ファイルの種類]、および [サイズの一致] の条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="99d13-209">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="99d13-210">機密情報の種類を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-210">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="99d13-211">ここでは、既定およびカスタムの機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="99d13-211">This is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="99d13-212">既存のカスタムの機密情報の種類またはカスタムのキーワードディクショナリから選択する通信コンプライアンスポリシーウィザードで、必要に応じてウィザードを実行する前にこれらのアイテムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="99d13-212">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard, you can create these items before running the wizard if needed.</span></span> <span data-ttu-id="99d13-213">必要に応じて、[通信コンプライアンスポリシーウィザード] 内から新しい機密情報の種類を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="99d13-213">If desired, you can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="99d13-214">攻撃的な言語モデルを有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-214">Choose if you'd like to enable the offensive language model.</span></span> <span data-ttu-id="99d13-215">これにより、電子メールメッセージの本文での適切でない言語が検出されます。</span><span class="sxs-lookup"><span data-stu-id="99d13-215">This detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="99d13-216">レビューする通信の割合を定義します。</span><span class="sxs-lookup"><span data-stu-id="99d13-216">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="99d13-217">ポリシーの選択を確認し、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99d13-217">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="99d13-218">テンプレートを使用する場合は [**ポリシーの作成**] を選択し、カスタムポリシーウィザードを使用する場合は [**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-218">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="99d13-219">[**ポリシーが作成**されました] ページが表示され、ポリシーがアクティブ化されて通信がキャプチャされるタイミングに関するガイドラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99d13-219">The **Your policy was created** page is displayed with guidelines on when policy will be activated and communications will be captured.</span></span>

## <a name="step-4-create-employee-notice-templates-optional"></a><span data-ttu-id="99d13-220">手順 4: 従業員の通知テンプレートを作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="99d13-220">Step 4: Create employee notice templates (optional)</span></span>

<span data-ttu-id="99d13-221">関連付けられた従業員にアラーム通知を送信してポリシーの警告に応答するオプションを使用する場合は、組織内に少なくとも1つの通知テンプレートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-221">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="99d13-222">通知テンプレートフィールドは、通知修復プロセスの一部として送信する前に編集でき、コミュニケーションコンプライアンスポリシーごとにカスタマイズされた通知テンプレートを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99d13-222">The notice template fields are editable prior to sending as part of the alert remediation process and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="99d13-223">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="99d13-223">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="99d13-224">Microsoft 365 コンプライアンスセンターで、[通信の**コンプライアンス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="99d13-224">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="99d13-225">[**通知テンプレート**] タブを選択してから、[**通知テンプレートの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99d13-225">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="99d13-226">[**通知テンプレートの変更**] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="99d13-226">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="99d13-227">通知テンプレート名 (必須)</span><span class="sxs-lookup"><span data-stu-id="99d13-227">Notice template name (required)</span></span>
    - <span data-ttu-id="99d13-228">送信元 (必須)</span><span class="sxs-lookup"><span data-stu-id="99d13-228">Send from (required)</span></span>
    - <span data-ttu-id="99d13-229">Cc および Bcc (省略可能)</span><span class="sxs-lookup"><span data-stu-id="99d13-229">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="99d13-230">件名 (必須)</span><span class="sxs-lookup"><span data-stu-id="99d13-230">Subject (required)</span></span>
    - <span data-ttu-id="99d13-231">メッセージ本文 (必須)</span><span class="sxs-lookup"><span data-stu-id="99d13-231">Message body (required)</span></span>

5. <span data-ttu-id="99d13-232">[**保存**] を選択して、通知テンプレートを作成して保存します。</span><span class="sxs-lookup"><span data-stu-id="99d13-232">Select **Save** to create and save the notice template.</span></span>

## <a name="step-5-test-your-communication-compliance-policy-optional"></a><span data-ttu-id="99d13-233">手順 5: 通信コンプライアンスポリシーをテストする (オプション)</span><span class="sxs-lookup"><span data-stu-id="99d13-233">Step 5: Test your communication compliance policy (optional)</span></span>

<span data-ttu-id="99d13-234">通信コンプライアンスポリシーを作成したら、定義した条件がポリシーによって適切に適用されているかどうかをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99d13-234">After you create a communication compliance policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="99d13-235">また、通信コンプライアンスポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテスト](create-test-tune-dlp-policy.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="99d13-235">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="99d13-236">テストする通信が取得されるように、ポリシーの時間をアクティブにする必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="99d13-236">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="99d13-237">コミュニケーションコンプライアンスポリシーをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99d13-237">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="99d13-238">テストするポリシーで定義された、監視対象のユーザーとしてログインした電子メールクライアントまたは Microsoft Teams を開きます。</span><span class="sxs-lookup"><span data-stu-id="99d13-238">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="99d13-239">コミュニケーションコンプライアンスポリシーで定義した条件を満たすメールまたは Microsoft Teams のチャットを送信します。</span><span class="sxs-lookup"><span data-stu-id="99d13-239">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="99d13-240">これには、キーワード、添付ファイルのサイズ、ドメインなどを指定できます。ポリシーに構成された条件設定が制限を超えているか、厳しすぎるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="99d13-240">This can be a keyword, attachment size, domain, etc. Make sure that you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99d13-241">すべてのソースチャネルでの通信は、ポリシー内で完全に処理されるまでに最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="99d13-241">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="99d13-242">コミュニケーションコンプライアンスポリシーで指定されたレビュー担当者として Microsoft 365 にログインします。</span><span class="sxs-lookup"><span data-stu-id="99d13-242">Log into Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="99d13-243">[**通信コンプライアンス** > **アラート**に移動して、ポリシーのアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="99d13-243">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="99d13-244">修復コントロールを使用してアラートを修復し、アラートが適切に解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99d13-244">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
