---
title: コンテンツを自動的に保持または削除するアイテム保持ポリシーを作成して構成する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーを使用すると、コンテンツを保持するか、コンテンツを削除するか、またはその両方かを積極的に決定できます。コンテンツを保持してから削除する、組織全体または特定の場所またはユーザーに単一のポリシーを適用する、すべてのコンテンツまたは特定の条件を満たすコンテンツにポリシーを適用する、などです。
ms.openlocfilehash: 52383e3dc2ab1bf8706d5fcdb8408e9294db3b50
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268352"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="c0b62-103">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="c0b62-103">Create and configure retention policies</span></span>

><span data-ttu-id="c0b62-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="c0b62-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c0b62-105">アイテム保持ポリシーを使用して、コンテンツを保持するか、コンテンツを削除するか、またはその両方を行う (コンテンツを保持した後に削除する) かを事前に決定すします。</span><span class="sxs-lookup"><span data-stu-id="c0b62-105">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="c0b62-106">アイテム保持ポリシーの仕組みについては、「[アイテム保持ポリシーの詳細](retention-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-106">For information about how retention policies work, see [Learn about retention policies](retention-policies.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c0b62-107">はじめに</span><span class="sxs-lookup"><span data-stu-id="c0b62-107">Before you begin</span></span>

<span data-ttu-id="c0b62-108">アイテム保持ポリシーを作成して管理するコンプライアンス チームのメンバーには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)へのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-108">Members of your compliance team who will create and manage retention policies need permissions to the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="c0b62-109">既定により、テナント管理者はこの場所にアクセスでき、コンプライアンス責任者やその他のユーザーにテナント管理者のすべての権限を与えることなくアクセスできます。これを行うには、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)の [**権限**] ページに移動し、[**コンプライアンス管理者**] の管理者役割を編集して、その役割グループにメンバーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0b62-109">By default, your tenant admin has access to this location and can give compliance officers and other people access without giving them all the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/), edit the **Compliance administrator** admin role, and add members to that role group.</span></span> 

<span data-ttu-id="c0b62-110">これらのアクセス許可は、アイテム保持ポリシーを作成して適用するためにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-110">These permissions are required only to create and apply a retention policy.</span></span> <span data-ttu-id="c0b62-111">アイテム保持ポリシーを構成するユーザーは、コンテンツへのアクセスを必要としません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-111">The person configuring the retention policy doesn't require access to the content.</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="c0b62-112">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="c0b62-112">Create and configure a retention policy</span></span>

1. <span data-ttu-id="c0b62-113">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)から、[**ポリシー**] > [**保持**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-113">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="c0b62-114">[**新しいアイテム保持ポリシー**] を選択するか、既存のアイテム保持ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-114">Select **New retention policy** or edit an exiting retention policy.</span></span>

3. <span data-ttu-id="c0b62-115">[**設定**] では、最初にコンテンツを保持および削除するための構成オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-115">For **Settings**, first specify the configuration options for retaining and deleting content.</span></span> <span data-ttu-id="c0b62-116">削除せずにコンテンツを保持するだけのアイテム保持ポリシーを作成し、指定した期間が経過した後に保持してから削除するか、指定した期間が経過した後にコンテンツを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="c0b62-116">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="c0b62-117">詳細については、このページの「[コンテンツを保持および削除するための設定](#settings-for-retaining-and-deleting-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-117">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page:</span></span>
    
    <span data-ttu-id="c0b62-118">次に、アイテム保持ポリシーをすべてのコンテンツに適用するか、特定の条件を満たすコンテンツに適用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-118">Then, decide whether the retention policy should apply to all content, or content that meets specific conditions.</span></span> <span data-ttu-id="c0b62-119">これらの高度な保持設定の詳細については、このページの「[特定の条件を満たすコンテンツを特定するための詳細設定](#advanced-settings-to-identify-content-that-meets-specific-conditions)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-119">For more information about these advanced retention settings, see [Advanced settings to identify content that meets specific conditions](#advanced-settings-to-identify-content-that-meets-specific-conditions) on this page.</span></span> 

4. <span data-ttu-id="c0b62-120">[**場所の選択**] ページで、アイテム保持ポリシーを組織全体でサポートされているすべての場所に適用するか、場所を指定するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-120">For the **Choose locations** page, select whether the retention policy should apply to all supported locations across your organization, or you want to specify the locations.</span></span> <span data-ttu-id="c0b62-121">特定の場所を選択した場合は、対象と除外を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-121">If you choose specific locations, you can also specify includes and excludes.</span></span> 
    
    <span data-ttu-id="c0b62-122">Microsoft Teams の場合:</span><span class="sxs-lookup"><span data-stu-id="c0b62-122">For Microsoft Teams:</span></span> 
    - <span data-ttu-id="c0b62-123">Teams のチャネル メッセージまたは Teams のチャットを削除または保持する場合は、特定の場所を選択するオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-123">You must select the option to choose specific locations if you want to delete or retain Teams channel messages or Team chats.</span></span> <span data-ttu-id="c0b62-124">これらのオプションのいずれかを場所として選択すると、この Teams データを含むアイテム保持ポリシーにその他の場所を含めることができないため、その他の場所は自動的に除外されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-124">When you select either of these options as locations, the other locations are automatically excluded because a retention policy that includes this Teams data can't include other locations.</span></span> 
    - <span data-ttu-id="c0b62-125">**Teams のチャネル メッセージ**の場合、標準チャネルからのメッセージが含まれますが、[プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels)は含まれません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-125">Note that for **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="c0b62-126">プライベート チームからのメッセージは、**Teams のチャット**の場所を選択すると、グループ チャットとしてユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-126">Messages from private channels are included for users as group chats when you select the **Teams chats** location.</span></span>
    
    <span data-ttu-id="c0b62-127">組織または特定の場所のアイテム保持ポリシーを選択する方法の詳細については、このページの「[アイテム保持ポリシーを組織全体または特定の場所に適用する](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-127">For more information about choosing between a retention policy for the organization or for specific locations, see [Applying a retention policy to an entire organization or specific locations](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) on this page.</span></span>
    
    <span data-ttu-id="c0b62-128">**Office 365 グループ**および **Skype for Business** に固有の情報については、次のセクション、「[Microsoft 365 グループの構成情報](#configuration-information-for-microsoft-365-groups)」および「[Skype for Business の構成情報](#configuration-information-for-skype-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-128">For information specific to **Office 365 groups** and **Skype for Business**, see the following sections, [Configuration information for Microsoft 365 groups](#configuration-information-for-microsoft-365-groups) and [Configuration information for Skype for Business](#configuration-information-for-skype-for-business).</span></span>

5. <span data-ttu-id="c0b62-129">ウィザードを完了して、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-129">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="c0b62-130">アイテム保持ポリシーが複数ある場合は、「[保持の原則、すなわち優先順位について](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-130">When you have more than one retention policy, see [The principles of retention, or what takes precedence?](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="c0b62-131">Microsoft 365 グループの構成情報</span><span class="sxs-lookup"><span data-stu-id="c0b62-131">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="c0b62-132">Microsoft 365 グループ (以前の Office 365 グループ) のコンテンツを保持または削除するには、アイテム保持ポリシーの場所を選択するときに **Office 365 グループ**の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-132">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), select the **Office 365 groups** location when you choose locations for your retention policy.</span></span> <span data-ttu-id="c0b62-133">Microsoft 365 グループには Exchange メールボックスがありますが、**Exchange メール**の場所全体が含まれるアイテム保持ポリシーには、Microsoft 365 グループのメールボックスのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-133">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="c0b62-134">また、最初は **Exchange メール**の場所でグループ メールボックスを含めるか除外するかを指定できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では「RemoteGroupMailbox」を選択できないことを示すエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-134">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="c0b62-135">Microsoft 365 グループに適用されるアイテム保持ポリシーには、グループ メールボックスおよびサイトの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-135">A retention policy applied to an Microsoft 365 group includes both the group mailbox and site.</span></span> <span data-ttu-id="c0b62-136">Microsoft 365 グループに適用されるアイテム保持ポリシーは、Microsoft Teams を含む Microsoft 365 グループによって作成されたリソースを保護します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-136">A retention policy applied to a Microsoft 365 group protects the resources created by a Microsoft 365 group, which includes Microsoft Teams.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="c0b62-137">Skype for Business の構成情報</span><span class="sxs-lookup"><span data-stu-id="c0b62-137">Configuration information for Skype for Business</span></span>

<span data-ttu-id="c0b62-138">Exchange メールとは異なり Skype の場所の状態をオンに切り替えてすべてのユーザーを含めることはできませんが、そのロケーションをオンにしてから、会話を保持するユーザーを手動で選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-138">Unlike Exchange email, you can't toggle the status of the Skype location on to include all users, but when you turn on that location, you then manually choose the users whose conversations you want to retain:</span></span>

![アイテム保持ポリシーの Skype の場所を選択する](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="c0b62-140">[**ユーザーの選択**] を選択すると、列ヘッダーの [**名前**] ボックスを選択して、すべてのユーザーをすばやく含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-140">When you select **Choose users**, you can quickly include all users by selecting the **Name** box in the column header.</span></span> <span data-ttu-id="c0b62-141">ただし、各ユーザーはポリシーの特定のインクルージョンとしてカウントされることを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-141">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="c0b62-142">したがって、1,000 人を超えるユーザーを含める場合は、前のセクションで述べた制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-142">Therefore, if you include over 1,000 users, the limits noted in the previous section apply.</span></span> <span data-ttu-id="c0b62-143">ここですべての Skype ユーザーを選択することは、組織全体のポリシーに規定ですべての Skype ユーザーを含めることができた場合と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-143">Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![Skype ユーザーの選択ページ](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="c0b62-p111">Outlook のフォルダー **[会話履歴]** は、Skype のアーカイブには作用しない機能です。**[会話履歴]** はエンド ユーザーが無効にできますが、Skype のアーカイブの場合はユーザーがアクセスできない (電子情報開示には使用できる) 非表示フォルダーに Skype の会話のコピーが保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-p111">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>


## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="c0b62-147">コンテンツを保持および削除するための設定</span><span class="sxs-lookup"><span data-stu-id="c0b62-147">Settings for retaining and deleting content</span></span>

<span data-ttu-id="c0b62-148">アイテム保持ポリシーでコンテンツを保持および削除するための設定を選択すると、アイテム保持ポリシーは、指定された期間、次のいずれかの構成になります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-148">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="c0b62-149">保持のみ</span><span class="sxs-lookup"><span data-stu-id="c0b62-149">Retain-only</span></span>
- <span data-ttu-id="c0b62-150">保持してから削除</span><span class="sxs-lookup"><span data-stu-id="c0b62-150">Retain and then delete</span></span>
- <span data-ttu-id="c0b62-151">削除のみ</span><span class="sxs-lookup"><span data-stu-id="c0b62-151">Delete-only</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="c0b62-152">コンテンツを特定の期間保持する</span><span class="sxs-lookup"><span data-stu-id="c0b62-152">Retaining content for a specific period of time</span></span>

<span data-ttu-id="c0b62-153">アイテム保持ポリシーを構成するときは、コンテンツを無期限に、または特定の日数、月数、または年数の間保持することを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-153">When you configure a retention policy, you choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="c0b62-154">コンテンツが保持される期間は、アイテム保持ポリシーが適用された時点からではなくコンテンツの経過時間から計算されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-154">The duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied.</span></span> <span data-ttu-id="c0b62-155">経過時間は、コンテンツが作成された日時に基づく場合と、(OneDrive および SharePoint の場合) コンテンツが最後に変更された日時に基づく場合から選択できます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-155">You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>

<span data-ttu-id="c0b62-156">例:</span><span class="sxs-lookup"><span data-stu-id="c0b62-156">Examples:</span></span>
  
- <span data-ttu-id="c0b62-157">SharePoint: サイト コレクションのコンテンツを最後に変更してから 7 年間保持する場合に、そのサイト コレクションのドキュメントが 6 年変更されていないと、そのドキュメントが変更されなければあと 1 年間しか保持されません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-157">SharePoint: If you want to retain content in a site collection for seven years since it was last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="c0b62-158">そのドキュメントがもう一度編集された場合、ドキュメントの古さは最後に変更された日付から計算され、その後 7 年間保留にされます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-158">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="c0b62-159">Exchange: メールボックスのコンテンツを 7 年間保持する場合、あるメッセージが 6 年前に送信されているときは、あと 1 年間のみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-159">Exchange: If you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="c0b62-160">Exchange コンテンツの場合、経過時間は受信メールの受信日または送信メールの送信日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c0b62-160">For Exchange content, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="c0b62-161">最終更新日に基づいてコンテンツを保持するポリシーは、OneDrive および SharePoint のコンテンツ サイトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-161">Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="c0b62-162">保持期間の終了時にコンテンツを完全に削除するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-162">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![[アイテム保持設定] ページ](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="c0b62-164">特定の経過時間を超えた古いコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="c0b62-164">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="c0b62-165">アイテム保持ポリシーは、コンテンツを保持してから削除することも、古いコンテンツを保持せずに削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-165">A retention policy can both retain and then delete content, or delete old content without retaining it.</span></span>
  
<span data-ttu-id="c0b62-166">アイテム保持ポリシーによってコンテンツを削除する場合、アイテム保持ポリシーに指定した期間は、ポリシーが割り当てられた時点からではなく、コンテンツが作成または変更された時点から計算されることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-166">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![[削除の設定]](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="c0b62-168">たとえば、保持して 3 年間を過ぎたコンテンツを削除するアイテム保持ポリシーを作成し、それをすべての OneDrive アカウントに割り当てるとします。アカウントには、4 から 5 年前に作成されたコンテンツが数多く含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0b62-168">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago.</span></span> <span data-ttu-id="c0b62-169">このような場合、最初にアイテム保持ポリシーが割り当てられてすぐに、コンテンツの多くが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-169">In this case, a lot of content will be deleted soon after assigning the retention policy for the first time.</span></span> <span data-ttu-id="c0b62-170">このような理由から、コンテンツを削除するアイテム保持ポリシーは、コンテンツにかなりの影響を与える可能性があることを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-170">For this reason, it's important to understand that a retention policy that deletes content can have a considerable impact on your content.</span></span> 
  
<span data-ttu-id="c0b62-p116">そのため、サイト コレクションに初めてポリシーを割り当てるときには、その前に、既存のコンテンツの経過時間と、そのコンテンツにポリシーが及ぼす影響について考慮する必要があります。また、新しいポリシーを割り当てる前に、サイト所有者に連絡して、発生する可能性のある影響について評価するための時間を与えるようにしてください。アイテム保持ポリシーの作成前に設定を確認すると、この警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-p116">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.</span></span>
  
![コンテンツの削除に関する警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a><span data-ttu-id="c0b62-175">特定の条件を満たすコンテンツを特定するための詳細設定</span><span class="sxs-lookup"><span data-stu-id="c0b62-175">Advanced settings to identify content that meets specific conditions</span></span>

<span data-ttu-id="c0b62-176">アイテム保持ポリシーは、その場所に含まれるすべてのコンテンツに適用することも、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツにのみ適用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-176">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![高度なアイテム保持のオプション](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a><span data-ttu-id="c0b62-178">特定のキーワードを含むコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="c0b62-178">Identify content that contains specific keywords</span></span>

<span data-ttu-id="c0b62-179">特定の条件を満たすコンテンツにのみアイテム保持ポリシーを適用し、そのコンテンツだけを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-179">You can apply a retention policy only to content that meets specific conditions, and then take retention actions on just that content.</span></span> <span data-ttu-id="c0b62-180">利用できる条件で、特定の単語または語句を含むコンテンツにアイテム保持ポリシーを適用するようになります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-180">The conditions available support applying a retention policy to content that contains specific words or phrases.</span></span> <span data-ttu-id="c0b62-181">AND、OR、NOT などの検索演算子を使用して、クエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-181">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="c0b62-182">このような演算子の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0b62-182">For more information on these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="c0b62-183">検索可能なプロパティ (**件名:** など) の追加については間もなくサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-183">Support for adding searchable properties (for example, **subject:**) is coming soon.</span></span>
  
<span data-ttu-id="c0b62-184">クエリベースの保持では、検索インデックスを使用してコンテンツを識別します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-184">Query-based retention uses the search index to identify content.</span></span>
  
![クエリ エディター](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a><span data-ttu-id="c0b62-186">機密情報が含まれているコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="c0b62-186">Identify content that contains sensitive information</span></span>

<span data-ttu-id="c0b62-p118">アイテム保持ポリシーは、[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)が含まれているコンテンツにのみ適用できます。たとえば、納税者番号、社会保障番号、パスポート番号などの個人を特定できる情報 (PII) が含まれているコンテンツにのみ固有の保持要件を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-p118">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md). For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![機密情報の種類のページ](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="c0b62-190">注:</span><span class="sxs-lookup"><span data-stu-id="c0b62-190">Notes:</span></span>
  
- <span data-ttu-id="c0b62-191">機密情報に対応する高度な保持は、Exchange のパブリック フォルダーや Skype for Business には適用されません (これらの場所が機密情報の種類をサポートしていないため)。</span><span class="sxs-lookup"><span data-stu-id="c0b62-191">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="c0b62-192">Exchange Online はメール フロー ルール (トランスポート ルールとも呼ばれます) を使用して機密情報を特定するため、既にメールボックスに保存されているすべてのアイテムにではなく、送受信するメッセージにのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-192">Exchange Online uses mail flow rules (also known as transport rules) to identify sensitive information, so this works only on messages in transit — not on all items already stored in a mailbox.</span></span> <span data-ttu-id="c0b62-193">つまり、Exchange Online の場合、アイテム保持ポリシーは、ポリシーがメールボックスに適用された**後**に受信したメッセージに対してのみ機密情報を特定して、保持することができます </span><span class="sxs-lookup"><span data-stu-id="c0b62-193">For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox.</span></span> <span data-ttu-id="c0b62-194">前のセクションで説明したクエリ ベースの保持では、コンテンツを特定する際に検索インデックスが使用されるため、このような制限がありません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-194">Query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="c0b62-195">アイテム保持ポリシーを組織全体または特定の場所に適用する</span><span class="sxs-lookup"><span data-stu-id="c0b62-195">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="c0b62-196">アイテム保持ポリシーは、組織全体、場所全体、または特定の場所やユーザーのみに簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-196">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="c0b62-197">組織全体のポリシー</span><span class="sxs-lookup"><span data-stu-id="c0b62-197">Org-wide policy</span></span>

<span data-ttu-id="c0b62-198">アイテム保持ポリシーの強力な機能の 1 つとして、Microsoft 365 全体の場所に適用されます。これには、次の場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-198">One of the most powerful features of a retention policy is that it can apply to locations across Microsoft 365, including:</span></span>
  
- <span data-ttu-id="c0b62-199">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="c0b62-199">Exchange email</span></span>
    
- <span data-ttu-id="c0b62-200">SharePoint サイト コレクション</span><span class="sxs-lookup"><span data-stu-id="c0b62-200">SharePoint site collections</span></span>
    
- <span data-ttu-id="c0b62-201">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="c0b62-201">OneDrive accounts</span></span>
    
- <span data-ttu-id="c0b62-202">Microsoft 365 グループ (グループのメールボックス、および関連する SharePoint サイトのコンテンツに適用されます)。</span><span class="sxs-lookup"><span data-stu-id="c0b62-202">Microsoft 365 groups (applies to content in the group's mailbox and associated SharePoint site.)</span></span>
    
- <span data-ttu-id="c0b62-203">Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="c0b62-203">Exchange public folders</span></span>
    

![すべての場所のオプション](../media/retention-policies-all-locations.png)

<span data-ttu-id="c0b62-205">その他の組織全体のアイテム保持ポリシーに関する重要な機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c0b62-205">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="c0b62-206">ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-206">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="c0b62-207">Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-207">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="c0b62-208">場所全体に適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="c0b62-208">A policy that applies to entire locations</span></span>

<span data-ttu-id="c0b62-209">場所を選択すると、Exchange メールや OneDrive アカウントなど、場所全体を簡単に含めたり除外したりできます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-209">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts.</span></span> <span data-ttu-id="c0b62-210">これを行うには、その場所の [**状態**] をオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-210">To do so, toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="c0b62-211">組織全体のポリシーと同様に、場所全体の任意の組み合わせにポリシーが適用される場合、ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="c0b62-211">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include.</span></span> 

<span data-ttu-id="c0b62-212">たとえば、ポリシーにすべての Exchange メールとすべての SharePoint サイトが含まれている場合、数に関係なくすべてのサイトとメールボックスが含められます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-212">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many.</span></span> <span data-ttu-id="c0b62-213">また、Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-213">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="c0b62-214">特定の追加または除外を含むポリシー</span><span class="sxs-lookup"><span data-stu-id="c0b62-214">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="c0b62-215">特定のユーザー、特定の Microsoft 365 グループ、または特定のサイトにアイテム保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-215">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="c0b62-216">そのためには、目的の場所の [**状態**] をオンに切り替えた上で、リンクを使用して特定のユーザー、Microsoft 365 グループ、またはサイトを含めたり除外したりします。</span><span class="sxs-lookup"><span data-stu-id="c0b62-216">To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="c0b62-217">ただし、この設定を使用すると、保持ポリシーに 1,000 を超える特定の場所が含まれている場合、または除外される場合、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-217">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific locations:</span></span>
  
- <span data-ttu-id="c0b62-218">アイテム保持ポリシーの最大数:</span><span class="sxs-lookup"><span data-stu-id="c0b62-218">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="c0b62-219">1,000 個のメールボックス</span><span class="sxs-lookup"><span data-stu-id="c0b62-219">1,000 mailboxes</span></span>
    - <span data-ttu-id="c0b62-220">1,000 個の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="c0b62-220">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="c0b62-221">Teams のプライベート チャットのユーザー 1,000 人</span><span class="sxs-lookup"><span data-stu-id="c0b62-221">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="c0b62-222">100 個のサイト (OneDrive または SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c0b62-222">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="c0b62-223">テナントでサポートされるポリシーの最大数は 10,000 です。</span><span class="sxs-lookup"><span data-stu-id="c0b62-223">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="c0b62-224">これらのアイテムには、アイテム保持ポリシー、保持ラベル ポリシー、および自動適用アイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-224">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="c0b62-225">アイテム保持ポリシーがこれらの制限の影響を受ける可能性がある場合は、場所全体に適用される構成オプションを選択するか、組織全体のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-225">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations, or use an org-wide policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="c0b62-226">アイテム保持ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="c0b62-226">Updating retention policies</span></span>

<span data-ttu-id="c0b62-227">アイテム保持ポリシーを編集し、コンテンツが既にアイテム保持ポリシーの元の設定の対象となっている場合、更新された設定は、新しく特定されたコンテンツに加えて、このコンテンツに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-227">If you edit a retention policy and content is already subject to the original settings in your retention policy, your updated settings will be automatically applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="c0b62-228">通常、この更新はかなり迅速ですが、数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-228">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="c0b62-229">Microsoft 365 の場所間でのポリシーの複製が完了すると、Microsoft 365 コンプライアンス センターの保持ポリシーの状態が [**On (保留中)**] から [**オン (成功)**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-229">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a><span data-ttu-id="c0b62-230">アイテム保持ポリシーの PowerShell コマンドレットを検索する</span><span class="sxs-lookup"><span data-stu-id="c0b62-230">Find the PowerShell cmdlets for retention policies</span></span>

<span data-ttu-id="c0b62-231">アイテム保持ポリシーのコマンドレットを使用するには:</span><span class="sxs-lookup"><span data-stu-id="c0b62-231">To use the retention policies cmdlets:</span></span>
  
1. [<span data-ttu-id="c0b62-232">Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="c0b62-232">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="c0b62-233">以下の Office 365 セキュリティ センターとコンプライアンス センターのコマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="c0b62-233">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="c0b62-234">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c0b62-234">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c0b62-235">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c0b62-235">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c0b62-236">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c0b62-236">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c0b62-237">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="c0b62-237">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="c0b62-238">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c0b62-238">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)
    
    - [<span data-ttu-id="c0b62-239">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c0b62-239">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)
    
    - [<span data-ttu-id="c0b62-240">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c0b62-240">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="c0b62-241">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="c0b62-241">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="c0b62-242">PowerShell を使用してアイテム保持ポリシーをロックする</span><span class="sxs-lookup"><span data-stu-id="c0b62-242">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="c0b62-243">規制要件に準拠するために [[保持ロック](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)] を使用する必要がある場合は、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-243">You must use PowerShell if you need to need to use [Preservation Lock](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span>

1. <span data-ttu-id="c0b62-244">[Office 365 セキュリティ/コンプライアンス センター PowerShell へ接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="c0b62-244">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="c0b62-245">アイテム保持ポリシーを一覧表示し、`Get-RetentionCompliancePolicy` を実行してロックするポリシーの名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-245">List your retention policies and find the name of the policy that you want to lock by running `Get-RetentionCompliancePolicy`.</span></span>
    
    ![PowerShell のアイテム保持ポリシーの一覧](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="c0b62-247">アイテム保持ポリシーに [保持ロック] を設定するには `Set-RetentionCompliancePolicy` を実行しますが、その際に `RestrictiveRetention` パラメーターを true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0b62-247">To place a Preservation Lock on a retention policy, run `Set-RetentionCompliancePolicy` with the `RestrictiveRetention` parameter set to true.</span></span> <span data-ttu-id="c0b62-248">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-248">For example:</span></span>
    
        Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
    
    ![PowerShell の RestrictiveRetention パラメーター](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    <span data-ttu-id="c0b62-250">そのコマンドレットを実行した後、[**すべてはい**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-250">After you run that cmdlet, choose **Yes to All**:</span></span>
    
    ![PowerShell でアイテム保持ポリシーをロックすることを確認するプロンプト](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="c0b62-252">アイテム保持ポリシーに保持ロックが設定されました。</span><span class="sxs-lookup"><span data-stu-id="c0b62-252">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="c0b62-253">`Get-RetentionCompliancePolicy`を実行すると、`RestrictiveRetention`パラメーターは true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c0b62-253">If you run `Get-RetentionCompliancePolicy`, the `RestrictiveRetention` parameter is set to true.</span></span> <span data-ttu-id="c0b62-254">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c0b62-254">For example:</span></span>

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![PowerShell に表示されるすべてのパラメーターを含むロックされたポリシー](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

