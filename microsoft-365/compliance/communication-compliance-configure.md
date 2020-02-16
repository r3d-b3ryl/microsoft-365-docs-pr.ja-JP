---
title: 通信のコンプライアンスを構成する
description: コミュニケーションコンプライアンスポリシーを設定して、レビューのために従業員の通信を構成します。
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
ms.openlocfilehash: 1c53eded5e50d480cdce2ccbcb61f732bc899041
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078781"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a><span data-ttu-id="0f966-103">Microsoft 365 で通信のコンプライアンスを構成する</span><span class="sxs-lookup"><span data-stu-id="0f966-103">Configure communication compliance in Microsoft 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="0f966-104">このトピックは、Microsoft 365 サブスクリプションで通信のコンプライアンスを構成する場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0f966-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="0f966-105">Office 365 サブスクリプションの監督ポリシーを構成する場合は、「 [configure 監督 For office 365](supervision-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="0f966-106">コミュニケーションコンプライアンスポリシーを使用して、内部または外部のレビューアーによる調査のために従業員の通信をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="0f966-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="0f966-107">通信コンプライアンスポリシーが組織内の通信の監視にどのように役立つかについては、「 [Microsoft 365 の通信コンプライアンスポリシー](communication-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0f966-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="0f966-108">Before you begin</span></span>

<span data-ttu-id="0f966-109">通信のコンプライアンスを開始する前に、Microsoft 365 のサブスクリプションを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-109">Before you get started with communication compliance, you should confirm your Microsoft 365 subscription.</span></span> <span data-ttu-id="0f966-110">通信コンプライアンスポリシーに含まれているユーザーは、Microsoft 365 E5 コンプライアンスライセンス、Advanced コンプライアンスアドオンを備えた Office 365 Enterprise E3 ライセンス、または Microsoft 365 E5 サブスクリプションに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-110">Users included in communication compliance policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in a Microsoft 365 E5 subscription.</span></span>

<span data-ttu-id="0f966-111">既存の Microsoft 365 Enterprise E5 プランを保有せずに insider リスク管理を試みる場合は、 [microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)を既存の Office 365 サブスクリプションに追加するか、Microsoft 365 Enterprise E5 の[試用版にサインアップ](https://www.microsoft.com/microsoft-365/enterprise)することができます。</span><span class="sxs-lookup"><span data-stu-id="0f966-111">If you don't have an existing Microsoft 365 Enterprise E5 plan and want to try insider risk management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>
  
<span data-ttu-id="0f966-112">Microsoft 365 組織の通信コンプライアンスをセットアップして使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f966-112">Complete these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="0f966-113">手順 1 (必須): 通信のコンプライアンスのためのアクセス許可を有効にする</span><span class="sxs-lookup"><span data-stu-id="0f966-113">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="0f966-114">既定では、全体管理者は通信コンプライアンス機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0f966-114">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="0f966-115">この手順で割り当てられる役割は、通信コンプライアンス機能がアクセス可能になる前に必要です。</span><span class="sxs-lookup"><span data-stu-id="0f966-115">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="0f966-116">Microsoft 365 コンプライアンスセンターのメニューオプションとして**通信のコンプライアンス**を実現するには、**監督レビュー管理者**の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-116">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="0f966-117">**スーパーバイザーレビュー管理者**、**ケース管理**、および**レビュー**の役割を持つレビュー担当者用の新しい役割グループを作成して、ポリシーが一致するメッセージを調査および修復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-117">You must create a new role group for reviewers with the **Supervisory Review Administrator**, **Case Management**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="0f966-118">新しい役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="0f966-118">Create a new role group</span></span>

1. <span data-ttu-id="0f966-119">Microsoft 365 [https://protection.office.com/permissions](https://protection.office.com/permissions)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f966-119">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="0f966-120">Microsoft Office 365 セキュリティ/コンプライアンスセンターで、[**アクセス許可**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f966-120">In the Microsoft Office 365 security and compliance center, go to **Permissions**.</span></span> <span data-ttu-id="0f966-121">Office 365 で役割を表示および管理するためのリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-121">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="0f966-122">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-122">Select **Create**.</span></span>

4. <span data-ttu-id="0f966-123">[**名前**] フィールドに、新しい役割グループにフレンドリ名を付けます。</span><span class="sxs-lookup"><span data-stu-id="0f966-123">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="0f966-124">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-124">Select **Next**.</span></span>

5. <span data-ttu-id="0f966-125">[**役割の選択**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-125">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="0f966-126">[**監督レビュー管理者**]、[**ケースの管理**]、[**レビュー**] のチェックボックスをオンにして、[**追加**と**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-126">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="0f966-127">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-127">Select **Next**.</span></span>

    ![通信コンプライアンスに必要な役割グループ](../media/communication-compliance-role-groups.png)

6. <span data-ttu-id="0f966-129">[**メンバーの選択**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-129">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="0f966-130">[ポリシーの作成] と [ポリシーの一致でメッセージを管理する] を使用するすべてのユーザーおよびグループのチェックボックスをオンにし、[**追加** **] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="0f966-130">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="0f966-131">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-131">Select **Next**.</span></span>

7. <span data-ttu-id="0f966-132">[**役割グループの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-132">Select **Create role group** to finish.</span></span>

<span data-ttu-id="0f966-133">役割グループとアクセス許可の詳細については、「[Permissions in the Compliance Center (コンプライアンス センターのアクセス許可)](../security/office-365-security/protect-against-threats.md)」を参照してください。 </span><span class="sxs-lookup"><span data-stu-id="0f966-133">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-office-365-audit-log"></a><span data-ttu-id="0f966-134">手順 2 (必須): Office 365 監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="0f966-134">Step 2 (required): Enable the Office 365 audit log</span></span>

<span data-ttu-id="0f966-135">通信のコンプライアンスでは、監査ログを使用して通知を表示し、レビュー担当者が行った修復アクションを追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-135">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="0f966-136">監査ログは、定義済みの組織ポリシーに関連付けられているすべてのアクティビティ、または通信コンプライアンスポリシーが変更されるたびに、その概要を示します。</span><span class="sxs-lookup"><span data-stu-id="0f966-136">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="0f966-137">監査を有効にするための詳細な手順については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-137">For step-by-step instructions to turn on auditing, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="0f966-138">監査を有効にすると、監査ログが準備されていて、準備が完了してから数時間で検索を実行できるというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f966-138">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="0f966-139">この操作は1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-139">You only have to do this action once.</span></span> <span data-ttu-id="0f966-140">監査ログの使用の詳細については、「 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-140">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>


## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="0f966-141">手順 3 (省略可能): 通信コンプライアンス用にグループをセットアップする</span><span class="sxs-lookup"><span data-stu-id="0f966-141">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="0f966-142">通信コンプライアンスポリシーを作成する場合は、通信をレビューしたユーザーとレビューを実行するユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="0f966-142">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="0f966-143">ポリシーでは、メール アドレスを使って、個人または複数人のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f966-143">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="0f966-144">セットアップを簡単にするために、コミュニケーションをレビューしたユーザーのためのグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f966-144">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="0f966-145">グループを使用している場合は、複数必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-145">If you're using groups, you may need several.</span></span> <span data-ttu-id="0f966-146">たとえば、2つの異なるユーザーグループ間の通信を監視する場合、または、監視されないグループを指定する場合などです。</span><span class="sxs-lookup"><span data-stu-id="0f966-146">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="0f966-147">次の表を使用して、通信コンプライアンスポリシー用に組織内のグループを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f966-147">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="0f966-148">**ポリシー メンバー**</span><span class="sxs-lookup"><span data-stu-id="0f966-148">**Policy Member**</span></span> | <span data-ttu-id="0f966-149">**サポートされているグループ**</span><span class="sxs-lookup"><span data-stu-id="0f966-149">**Supported Groups**</span></span> | <span data-ttu-id="0f966-150">**サポートされていないグループ**</span><span class="sxs-lookup"><span data-stu-id="0f966-150">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="0f966-151">監督対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="0f966-151">Supervised users</span></span> <br> <span data-ttu-id="0f966-152">非監督対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="0f966-152">Non-supervised users</span></span> | <span data-ttu-id="0f966-153">配布グループ</span><span class="sxs-lookup"><span data-stu-id="0f966-153">Distribution groups</span></span> <br> <span data-ttu-id="0f966-154">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="0f966-154">Office 365 groups</span></span> | <span data-ttu-id="0f966-155">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="0f966-155">Dynamic distribution groups</span></span> |
| <span data-ttu-id="0f966-156">レビュー担当者</span><span class="sxs-lookup"><span data-stu-id="0f966-156">Reviewers</span></span> | <span data-ttu-id="0f966-157">メールが有効なセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="0f966-157">Mail-enabled security groups</span></span>  | <span data-ttu-id="0f966-158">配布グループ</span><span class="sxs-lookup"><span data-stu-id="0f966-158">Distribution groups</span></span> <br> <span data-ttu-id="0f966-159">動的配布グループ</span><span class="sxs-lookup"><span data-stu-id="0f966-159">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="0f966-160">監督対象ユーザーの Office 365 グループを選択すると、ポリシーは共有 Office 365 メールボックスのコンテンツおよびグループに関連付けられた Microsoft Teams チャネルを監視します。</span><span class="sxs-lookup"><span data-stu-id="0f966-160">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="0f966-161">配布リストを選択すると、ポリシーは個々のユーザー メールボックスを監視します。</span><span class="sxs-lookup"><span data-stu-id="0f966-161">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="0f966-162">グループの設定の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-162">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="0f966-163">配布グループを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="0f966-163">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="0f966-164">メールが有効なセキュリティ グループの管理</span><span class="sxs-lookup"><span data-stu-id="0f966-164">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="0f966-165">Overview of Office 365 Groups (Office 365 グループの概要)</span><span class="sxs-lookup"><span data-stu-id="0f966-165">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a><span data-ttu-id="0f966-166">手順 4 (必須): 通信コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0f966-166">Step 4 (required): Create a communication compliance policy</span></span>
  
1. <span data-ttu-id="0f966-167">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f966-167">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="0f966-168">Microsoft 365 コンプライアンスセンターで、[**通信コンプライアンス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-168">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="0f966-169">[**ポリシー** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-169">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="0f966-170">[**ポリシーの作成**] を選択して、テンプレートから新しいポリシーを作成して構成するか、カスタムポリシーを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="0f966-170">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="0f966-171">ポリシーを作成するポリシーテンプレートを選択する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f966-171">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="0f966-172">ポリシー名を確認または更新します。</span><span class="sxs-lookup"><span data-stu-id="0f966-172">Confirm or update the policy name.</span></span> <span data-ttu-id="0f966-173">ポリシー名は、ポリシーの作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f966-173">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="0f966-174">除外するユーザーやグループの選択などを含めて、監督するユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-174">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="0f966-175">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-175">Choose the reviewers for the policy.</span></span> <span data-ttu-id="0f966-176">レビュー担当者は個々のユーザーか、[メールが有効なセキュリティ グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)です。</span><span class="sxs-lookup"><span data-stu-id="0f966-176">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="0f966-177">すべてのレビュー担当者は、Exchange Online でホストされているメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-177">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="0f966-178">制限された条件フィールド (通常は、ポリシーに適用する機密情報の種類またはキーワードディクショナリ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-178">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="0f966-179">ポリシーウィザードを使用してカスタムポリシーを作成する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0f966-179">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="0f966-180">ポリシーに名前と説明を付けます。</span><span class="sxs-lookup"><span data-stu-id="0f966-180">Give the policy a name and description.</span></span> <span data-ttu-id="0f966-181">ポリシー名は、ポリシーの作成後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f966-181">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="0f966-182">組織内のすべてのユーザー、特定のユーザーとグループ、または除外する他のユーザーとグループを含む、監督するユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-182">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span> -
    - <span data-ttu-id="0f966-183">ポリシーのレビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-183">Choose the reviewers for the policy.</span></span> <span data-ttu-id="0f966-184">レビュー担当者は個々のユーザーか、[メールが有効なセキュリティ グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)です。</span><span class="sxs-lookup"><span data-stu-id="0f966-184">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="0f966-185">すべてのレビュー担当者は、Exchange Online でホストされているメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-185">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="0f966-186">Exchange、Microsoft Teams、Skype for Business など、スキャンする通信チャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-186">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="0f966-187">また、Microsoft 365 でコネクタを構成した場合は、サードパーティのソースをスキャンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0f966-187">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="0f966-188">受信、送信、内部通信など、監視する通信方向を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-188">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="0f966-189">通信コンプライアンスポリシーの[条件](communication-compliance-feature-reference.md#ConditionalSettings)を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f966-189">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="0f966-190">[メッセージ アドレス]、[キーワード]、[ファイルの種類]、および [サイズの一致条件] の中から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0f966-190">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="0f966-191">機密情報の種類を含めるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-191">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="0f966-192">この手順では、既定およびカスタムの機密情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0f966-192">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="0f966-193">コミュニケーションコンプライアンスポリシーウィザードで、既存のカスタムの機密情報の種類またはカスタムキーワードディクショナリから選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-193">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="0f966-194">これらの項目は、必要に応じてウィザードを実行する前に作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f966-194">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="0f966-195">コミュニケーションコンプライアンスポリシーウィザードから、新しい機密情報の種類を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f966-195">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="0f966-196">不快な言語の分類子を有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-196">Choose if you'd like to enable the offensive language classifier.</span></span> <span data-ttu-id="0f966-197">この分類子は、電子メールメッセージの本文で送信または受信された不適切な言語を検出します。</span><span class="sxs-lookup"><span data-stu-id="0f966-197">This  classifier detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="0f966-198">レビューする通信の割合を定義します。</span><span class="sxs-lookup"><span data-stu-id="0f966-198">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="0f966-199">選択したポリシーを確認し、ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f966-199">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="0f966-200">テンプレートを使用する場合は [**ポリシーの作成**] を選択し、カスタムポリシーウィザードを使用する場合は [**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-200">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="0f966-201">[**ポリシーが作成**されました] ページが表示され、ポリシーがアクティブ化され、どの通信が取得されるかについてのガイドラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f966-201">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-5-optional-create-employee-notice-templates"></a><span data-ttu-id="0f966-202">手順 5 (省略可能): 従業員の通知テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="0f966-202">Step 5 (optional): Create employee notice templates</span></span>

<span data-ttu-id="0f966-203">関連付けられた従業員にアラーム通知を送信してポリシーの警告に応答するオプションを使用する場合は、組織内に少なくとも1つの通知テンプレートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-203">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="0f966-204">通知テンプレートフィールドは、通知修復プロセスの一環として送信される前に編集でき、コミュニケーションコンプライアンスポリシーごとにカスタマイズされた通知テンプレートを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f966-204">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="0f966-205">Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com)組織の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f966-205">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="0f966-206">Microsoft 365 コンプライアンスセンターで、[通信の**コンプライアンス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f966-206">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="0f966-207">[**通知テンプレート**] タブを選択してから、[**通知テンプレートの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f966-207">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="0f966-208">[**通知テンプレートの変更**] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="0f966-208">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="0f966-209">通知テンプレート名 (必須)</span><span class="sxs-lookup"><span data-stu-id="0f966-209">Notice template name (required)</span></span>
    - <span data-ttu-id="0f966-210">送信元 (必須)</span><span class="sxs-lookup"><span data-stu-id="0f966-210">Send from (required)</span></span>
    - <span data-ttu-id="0f966-211">Cc および Bcc (省略可能)</span><span class="sxs-lookup"><span data-stu-id="0f966-211">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="0f966-212">件名 (必須)</span><span class="sxs-lookup"><span data-stu-id="0f966-212">Subject (required)</span></span>
    - <span data-ttu-id="0f966-213">メッセージ本文 (必須)</span><span class="sxs-lookup"><span data-stu-id="0f966-213">Message body (required)</span></span>

5. <span data-ttu-id="0f966-214">[**保存**] を選択して、通知テンプレートを作成して保存します。</span><span class="sxs-lookup"><span data-stu-id="0f966-214">Select **Save** to create and save the notice template.</span></span>

## <a name="step-6-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="0f966-215">手順 6 (オプション): 通信コンプライアンスポリシーをテストする</span><span class="sxs-lookup"><span data-stu-id="0f966-215">Step 6 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="0f966-216">通信コンプライアンスポリシーを作成した後、それをテストして、定義した条件がポリシーによって適切に適用されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f966-216">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="0f966-217">また、通信コンプライアンスポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテスト](create-test-tune-dlp-policy.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f966-217">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="0f966-218">テストする通信が取得されるように、ポリシーの時間をアクティブにする必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-218">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="0f966-219">コミュニケーションコンプライアンスポリシーをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f966-219">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="0f966-220">テストするポリシーで定義された、監視対象のユーザーとしてサインインした状態で、電子メールクライアントまたは Microsoft Teams を開きます。</span><span class="sxs-lookup"><span data-stu-id="0f966-220">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="0f966-221">コミュニケーションコンプライアンスポリシーで定義した条件を満たすメールまたは Microsoft Teams のチャットを送信します。</span><span class="sxs-lookup"><span data-stu-id="0f966-221">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="0f966-222">このテストには、キーワード、添付ファイルのサイズ、ドメインなどを指定できます。ポリシーに構成された条件設定が制限を超えているか、厳しすぎるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f966-222">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f966-223">すべてのソースチャネルでの通信は、ポリシー内で完全に処理されるまでに最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f966-223">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="0f966-224">コミュニケーションコンプライアンスポリシーで指定されたレビュー担当者として Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f966-224">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="0f966-225">[**通信コンプライアンス** > **アラート**に移動して、ポリシーのアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="0f966-225">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="0f966-226">修復コントロールを使用してアラートを修復し、アラートが適切に解決されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f966-226">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
