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
ms.openlocfilehash: 9974bebef9809647e7fb87f98f9d2f505baca4f3
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126508"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="42524-103">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="42524-103">Create and configure retention policies</span></span>

><span data-ttu-id="42524-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="42524-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="42524-105">アイテム保持ポリシーを使用して、コンテンツを保持するか、コンテンツを削除するか、またはその両方を行う (コンテンツを保持した後に削除する) かを事前に決定すします。</span><span class="sxs-lookup"><span data-stu-id="42524-105">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="42524-106">アイテム保持ポリシーを使用すると、サイトまたはメールボックス レベルで、場所ごとに同じ保持設定をコンテンツに割り当てることで、これを非常に効率的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="42524-106">A retention policy lets you do this very efficiently by assigning the same retention settings for content by location, at a site or mailbox level.</span></span> <span data-ttu-id="42524-107">アイテム保持ポリシーと保持ラベルのどちらを使用するかわからない場合は、「[アイテム保持ポリシーと保持ラベル](retention.md#retention-policies-and-retention-labels)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42524-107">If you're not sure whether to use a retention policy or a retention label, see [Retention policies and retention labels](retention.md#retention-policies-and-retention-labels).</span></span>

<span data-ttu-id="42524-108">アイテム保持ポリシーと仕組みに関する詳細情報は、「[保持の詳細](retention.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42524-108">For more information about retention policies and how retention works, see [Learn about retention](retention.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="42524-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="42524-109">Before you begin</span></span>

<span data-ttu-id="42524-110">組織のグローバル管理者には、アイテム保持ポリシーを作成および編集できる完全な権限があります。</span><span class="sxs-lookup"><span data-stu-id="42524-110">The global admin for your organization has full permissions to create and edit retention policies.</span></span> <span data-ttu-id="42524-111">グローバル管理者としてサインインしていない場合は、「[アイテム保持ポリシーと保持ラベルを作成して管理するために必要なアクセス許可](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-111">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="42524-112">アイテム保持ポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="42524-112">Create and configure a retention policy</span></span>

<span data-ttu-id="42524-113">アイテム保持ポリシーは複数の場所をサポートできますが、サポートされているすべての場所を含む単一のアイテム保持ポリシーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="42524-113">Although a retention policy can support multiple locations, you can't create a single retention policy that includes all the supported locations:</span></span>
- <span data-ttu-id="42524-114">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="42524-114">Exchange email</span></span>
- <span data-ttu-id="42524-115">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="42524-115">SharePoint site</span></span>
- <span data-ttu-id="42524-116">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="42524-116">OneDrive accounts</span></span>
- <span data-ttu-id="42524-117">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="42524-117">Microsoft 365 groups</span></span>
- <span data-ttu-id="42524-118">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="42524-118">Skype for Business</span></span>
- <span data-ttu-id="42524-119">Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="42524-119">Exchange public folders</span></span>
- <span data-ttu-id="42524-120">チームのチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="42524-120">Teams channel messages</span></span>
- <span data-ttu-id="42524-121">Teams のチャット</span><span class="sxs-lookup"><span data-stu-id="42524-121">Teams chats</span></span>

<span data-ttu-id="42524-122">アイテム保持ポリシーを作成するときに Teams の場所のいずれかを選択すると、他の場所は自動的に除外されます。</span><span class="sxs-lookup"><span data-stu-id="42524-122">When you select either of the Teams locations when you create a retention policy, the other locations are automatically excluded.</span></span> <span data-ttu-id="42524-123">したがって、従うべき手順は、Teams の場所を含める必要があるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="42524-123">Therefore, the instructions to follow depend on whether you need to include the Teams locations:</span></span>

- [<span data-ttu-id="42524-124">Teams の場所のアイテム保持ポリシーの説明</span><span class="sxs-lookup"><span data-stu-id="42524-124">Instructions for a retention policy for Teams locations</span></span>](#retention-policy-for-teams-locations)
- [<span data-ttu-id="42524-125">Teams 以外の場所のアイテム保持ポリシーの説明</span><span class="sxs-lookup"><span data-stu-id="42524-125">Instructions for a retention policy for locations other than Teams</span></span>](#retention-policy-for-locations-other-than-teams)

<span data-ttu-id="42524-126">複数のアイテム保持ポリシーがあり、保持ラベルも使用する場合は、「[保持の原則、すなわち優先順位について](retention.md#the-principles-of-retention-or-what-takes-precedence)」を参照して、複数の保持設定が同じコンテンツに適用された場合の結果を理解してください。</span><span class="sxs-lookup"><span data-stu-id="42524-126">When you have more than one retention policy, and when you also use retention labels, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) to understand the outcome when multiple retention settings apply to the same content.</span></span>

### <a name="retention-policy-for-teams-locations"></a><span data-ttu-id="42524-127">Teams の場所のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="42524-127">Retention policy for Teams locations</span></span>

1. <span data-ttu-id="42524-128">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)から、[**ポリシー**] > [**保持**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-128">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="42524-129">新しいアイテム保持ポリシーを作成するには、[**新しいアイテム保持ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-129">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="42524-130">ウィザードの [**コンテンツを保持するか、削除するか、またはその両方を行うかを決定する**] ページで、コンテンツを保持および削除するための構成オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="42524-130">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="42524-131">削除せずにコンテンツを保持するだけのアイテム保持ポリシーを作成し、指定した期間が経過した後に保持してから削除するか、指定した期間が経過した後にコンテンツを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="42524-131">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="42524-132">詳細については、このページの「[コンテンツを保持および削除するための設定](#settings-for-retaining-and-deleting-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-132">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="42524-133">このオプションは Teams の場所ではサポートされていないため、[**保存期間の詳細設定を使用する**] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="42524-133">Do not select **Use advanced retention settings** because this option isn't supported for Teams locations.</span></span> 

4. <span data-ttu-id="42524-134">[**場所の選択**] ページで、[**特定の場所を選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-134">For the **Choose locations** page, select **Let me choose specific locations**.</span></span> <span data-ttu-id="42524-135">次に、Teams の場所の 1 つまたは両方を切り替えます: **Teams のチャネル メッセージ**および **Teams のチャット**。</span><span class="sxs-lookup"><span data-stu-id="42524-135">Then toggle on one or both of the locations for Teams: **Teams channel message** and **Teams chats**.</span></span>
     
    <span data-ttu-id="42524-136">**Teams のチャネル メッセージ**の場合、標準チャネルからのメッセージが含まれますが、[プライベート チャネル](https://docs.microsoft.com/microsoftteams/private-channels)は含まれません。</span><span class="sxs-lookup"><span data-stu-id="42524-136">For **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="42524-137">現在、プライベートチャネルはアイテム保持ポリシーでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42524-137">Currently, private channels aren't supported by retention policies.</span></span>
    
    <span data-ttu-id="42524-138">既定では、すべてのチームが選択されていますが、含めるチームまたは除外するチームを指定することで、これを調整できます。</span><span class="sxs-lookup"><span data-stu-id="42524-138">By default, all teams are selected, but you can refine this by specifying teams to be included, or teams to be excluded.</span></span>

5. <span data-ttu-id="42524-139">ウィザードを完了して、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="42524-139">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="42524-140">Teams のアイテム保持ポリシーの詳細については、「[Microsoft Teams のアイテム保持ポリシー](https://docs.microsoft.com/microsoftteams/retention-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-140">For more information about retention policies for Teams, see [Retention policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) from the Teams documentation.</span></span>

#### <a name="additional-retention-policy-needed-to-support-teams"></a><span data-ttu-id="42524-141">Teams をサポートするのに必要な追加のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="42524-141">Additional retention policy needed to support Teams</span></span>

<span data-ttu-id="42524-142">Teams は、単なるチャットやチャネルメッセージを送るだけのツールではありません。</span><span class="sxs-lookup"><span data-stu-id="42524-142">Teams is more than just chats and channel messages.</span></span> <span data-ttu-id="42524-143">Microsoft 365 グループ (以前の Office 365 グループ) から作成されたチームがある場合は、**Office 365 グループ**の場所を使用して、その Microsoft 365 グループを含むアイテム保持ポリシーを追加で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42524-143">If you have teams that were created from a Microsoft 365 group (formerly Office 365 group), you should additionally configure a retention policy that includes that Microsoft 365 group by using the **Office 365 groups** location.</span></span> <span data-ttu-id="42524-144">このアイテム保持ポリシーは、グループのメールボックス、サイト、およびドキュメントのコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="42524-144">This retention policy applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="42524-145">チーム サイトが Microsoft 365 グループに接続されていない場合に、Teams 内のファイルを保持および削除するためには、**SharePoint サイト**または **OneDrive アカウント**の場所を含むアイテム保持ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="42524-145">If you have team sites that aren't connected to a Microsoft 365 group, you need a retention policy that includes the **SharePoint sites** or **OneDrive accounts** locations to retain and delete files in Teams:</span></span>

- <span data-ttu-id="42524-146">チャット内で共有されるファイルは、ファイルを共有したユーザーの OneDrive アカウントに保存されます。</span><span class="sxs-lookup"><span data-stu-id="42524-146">Files that are shared in chat are stored in the OneDrive account of the user who shared the file.</span></span> 

- <span data-ttu-id="42524-147">チャネルにアップロードされたファイルは、チームの SharePoint 内に保存されます。</span><span class="sxs-lookup"><span data-stu-id="42524-147">Files that are uploaded to channels are stored in the SharePoint site for the team.</span></span>

> [!TIP]
> <span data-ttu-id="42524-148">チームの SharePoint サイトおよびチーム内のユーザーの OneDrive アカウントを選択すると、Microsoft 365 グループに接続されていない特定のチームのみのファイルにアイテム保持ポリシーを適用出来ます。</span><span class="sxs-lookup"><span data-stu-id="42524-148">You can apply a retention policy to the files of just a specific team when it's not connected to a Microsoft 365 group by selecting the SharePoint site for the team, and the OneDrive accounts of users in the Team.</span></span>

<span data-ttu-id="42524-149">Microsoft 365 グループ、SharePoint サイトや OneDrive アカウントに適用されているアイテム保持ポリシーにより、Teams のチャットやチャネル メッセージで参照されているファイルが、それらのメッセージが削除されるよりも先に削除される場合があります。</span><span class="sxs-lookup"><span data-stu-id="42524-149">It's possible that a retention policy that's applied to Microsoft 365 groups, SharePoint sites, or OneDrive accounts could delete a file that's referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="42524-150">このような場合、そのファイルは Teams のメッセージに引き続き表示されますが、ユーザーがファイルをクリックすると、"ファイルが見つかりません" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42524-150">In this scenario, the file still displays in the Teams message, but when users select the file, they get a "File not found" error.</span></span> <span data-ttu-id="42524-151">この動作はアイテム保持ポリシーに固有のものではなく、ユーザーが SharePoint または OneDrive から手動でファイルを削除した場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42524-151">This behavior isn't specific to retention policies and could also happen if a user manually deletes a file from SharePoint or OneDrive.</span></span>


### <a name="retention-policy-for-locations-other-than-teams"></a><span data-ttu-id="42524-152">Teams 以外の場所のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="42524-152">Retention policy for locations other than Teams</span></span>

1. <span data-ttu-id="42524-153">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)から、[**ポリシー**] > [**保持**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-153">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="42524-154">新しいアイテム保持ポリシーを作成するには、[**新しいアイテム保持ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-154">Select **New retention policy** to create a new retention policy.</span></span>

3. <span data-ttu-id="42524-155">ウィザードの [**コンテンツを保持するか、削除するか、またはその両方を行うかを決定する**] ページで、コンテンツを保持および削除するための構成オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="42524-155">For **Decide if you want to retain content, delete it, or both** page of the wizard, specify the configuration options for retaining and deleting content.</span></span> 
    
    <span data-ttu-id="42524-156">削除せずにコンテンツを保持するだけのアイテム保持ポリシーを作成し、指定した期間が経過した後に保持してから削除するか、指定した期間が経過した後にコンテンツを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="42524-156">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="42524-157">詳細については、このページの「[コンテンツを保持および削除するための設定](#settings-for-retaining-and-deleting-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-157">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page.</span></span>
    
    <span data-ttu-id="42524-158">次に、アイテム保持ポリシーをすべてのコンテンツに適用するか、特定の条件を満たすコンテンツに適用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="42524-158">Then, decide whether the retention policy should apply to all content, or content that meets specific conditions.</span></span> <span data-ttu-id="42524-159">これらの高度な保持設定の詳細については、このページの「[特定の条件を満たすコンテンツを特定するための詳細設定](#advanced-settings-to-identify-content-that-meets-specific-conditions)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="42524-159">For more information about these advanced retention settings, see [Advanced settings to identify content that meets specific conditions](#advanced-settings-to-identify-content-that-meets-specific-conditions) on this page.</span></span> 

4. <span data-ttu-id="42524-160">[**場所の選択**] ページで、アイテム保持ポリシーを組織全体でサポートされているすべての場所に適用するか、場所を指定するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-160">For the **Choose locations** page, select whether the retention policy should apply to all supported locations across your organization, or you want to specify the locations.</span></span> <span data-ttu-id="42524-161">特定の場所を選択した場合は、対象と除外を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="42524-161">If you choose specific locations, you can also specify includes and excludes.</span></span> 
    
    <span data-ttu-id="42524-162">組織または特定の場所のアイテム保持ポリシーを選択する方法の詳細については、このページの「[アイテム保持ポリシーを組織全体または特定の場所に適用する](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-162">For more information about choosing between a retention policy for the organization or for specific locations, see [Applying a retention policy to an entire organization or specific locations](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) on this page.</span></span>
    
    <span data-ttu-id="42524-163">場所固有の情報:</span><span class="sxs-lookup"><span data-stu-id="42524-163">Information specific to locations:</span></span>
    - [<span data-ttu-id="42524-164">Exchange メールと Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="42524-164">Exchange email and Exchange public folders</span></span>](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [<span data-ttu-id="42524-165">SharePoint サイトと OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="42524-165">SharePoint sites and OneDrive accounts</span></span>](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [<span data-ttu-id="42524-166">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="42524-166">Office 365 groups</span></span>](#configuration-information-for-microsoft-365-groups)
    - [<span data-ttu-id="42524-167">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="42524-167">Skype for Business</span></span>](#configuration-information-for-skype-for-business)

5. <span data-ttu-id="42524-168">ウィザードを完了して、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="42524-168">Complete the wizard to save your settings.</span></span>


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a><span data-ttu-id="42524-169">Exchange メールと Exchange パブリック フォルダーの構成情報</span><span class="sxs-lookup"><span data-stu-id="42524-169">Configuration information for Exchange email and Exchange public folders</span></span>

<span data-ttu-id="42524-170">**Exchange メール**の場所は、メールボックスのレベルで保持設定を適用することにより、ユーザーのメール、予定表、およびその他のメールボックス アイテムの保持をサポートします。</span><span class="sxs-lookup"><span data-stu-id="42524-170">The **Exchange email** location supports retention for users' email, calendar, and other mailbox items, by applying retention settings at the level of a mailbox.</span></span>

<span data-ttu-id="42524-171">次のメール アイテムが含まれます: メール メッセージ (下書きを含む) 、添付ファイル、タスク、予定表アイテム、終了日、メモ。</span><span class="sxs-lookup"><span data-stu-id="42524-171">The following mail items are included: Mail messages (includes drafts) with any attachments, tasks and calendar items when they have an end date, and notes.</span></span> <span data-ttu-id="42524-172">連絡先、および終了日が設定されていないタスクおよび予定表アイテムは含まれません。</span><span class="sxs-lookup"><span data-stu-id="42524-172">Contacts, and any tasks and calendar items that don't have an end date are not included.</span></span> <span data-ttu-id="42524-173">Skype や Teams の保存済みメッセージなど、メールボックスに保存されているその他のアイテムは、この場所には含まれません。</span><span class="sxs-lookup"><span data-stu-id="42524-173">Other items stored in a mailbox, such as Skype and Teams saved messages, aren't included with this location.</span></span> <span data-ttu-id="42524-174">これらのアイテムには、独自の保存場所があります。</span><span class="sxs-lookup"><span data-stu-id="42524-174">These items have their own retention locations.</span></span>

<span data-ttu-id="42524-175">Microsoft 365 グループには Exchange メールボックスがありますが、**Exchange メール**の場所全体が含まれるアイテム保持ポリシーには、Microsoft 365 グループのメールボックスのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="42524-175">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="42524-176">これらのメールボックスのコンテンツを保持するには、**Office 365 グループ**の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-176">To retain content in these mailboxes, select the **Office 365 groups** location.</span></span>

<span data-ttu-id="42524-177">**Exchange パブリック フォルダー**の場所は保持設定をすべてのパブリック フォルダーに適用し、フォルダーまたはメールボックス レベルでは適用できません。</span><span class="sxs-lookup"><span data-stu-id="42524-177">The **Exchange public folders** location applies retention settings to all public folders and can't be applied at the folder or mailbox level.</span></span>

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a><span data-ttu-id="42524-178">SharePoint サイトと OneDrive アカウントの構成情報</span><span class="sxs-lookup"><span data-stu-id="42524-178">Configuration information for SharePoint sites and OneDrive accounts</span></span>

<span data-ttu-id="42524-179">[**SharePoint サイト**] の場所を選択すると、アイテム保持ポリシーでは、SharePoint​​ コミュニケーション サイト、Office 365 グループによって接続されていないチーム サイト、クラシック サイトのドキュメントを保持および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="42524-179">When you choose the **SharePoint sites** location, the retention policy can retain and delete documents in SharePoint communication sites, team sites that aren't connected by Office 365 groups, and classic sites.</span></span> <span data-ttu-id="42524-180">Office 365 グループによって接続されているチーム サイトは、このオプションでサポートされていないため、代わりにグループのメールボックス、サイト、ファイル内のコンテンツに適用されている [**Office 365 グループ**] の場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="42524-180">Team sites connected by Office 365 groups aren't supported with this option and instead, use the **Office 365 groups** location that applies to content in the group's mailbox, site, and files.</span></span>

<span data-ttu-id="42524-181">アイテム保持ポリシーはサイト レベルで適用されますが、保持設定が適用されるのはドキュメントのみです。</span><span class="sxs-lookup"><span data-stu-id="42524-181">Although the retention policy is applied at the site level, only documents have retention settings applied to them.</span></span> <span data-ttu-id="42524-182">保持設定は、サイト内のライブラリ、リスト、およびフォルダーを含む組織構造には適用されません。</span><span class="sxs-lookup"><span data-stu-id="42524-182">Retention settings do not apply to the organizing structures that include libraries, lists, and folders within the site.</span></span> 

<span data-ttu-id="42524-183">SharePoint サイトまたは OneDrive アカウントの場所を指定する場合、サイトにアクセスするためのアクセス許可は必要ありません。また、**[場所の編集]** ページで URL を指定するときに、検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="42524-183">When you specify your locations for SharePoint sites or OneDrive accounts, you don't need permissions to access the sites and no validation is done at the time you specify the URL on the **Edit locations** page.</span></span> <span data-ttu-id="42524-184">ただし、SharePoint サイトはインデックス付けされている必要があり、ウィザードの最後に指定したサイトが存在しているか確認されます。</span><span class="sxs-lookup"><span data-stu-id="42524-184">However, the SharePoint sites must be indexed and the sites that you specify are checked that they exist at the end of the wizard.</span></span>

<span data-ttu-id="42524-185">この確認が失敗した場合は、入力した URL の検証が失敗したことを示すメッセージが表示され、検証が成功するまで、ウィザードはアイテム保持ポリシーを作成しません。</span><span class="sxs-lookup"><span data-stu-id="42524-185">If this check fails, you see a message that validation failed for the URL you entered, and the wizard won't create the retention policy until the validation check passes.</span></span> <span data-ttu-id="42524-186">このメッセージが表示されたら、ウィザードに戻って URL を変更するか、アイテム保持ポリシーからサイトを削除します。</span><span class="sxs-lookup"><span data-stu-id="42524-186">If you see this message, go back in the wizard to change the URL or remove the site from the retention policy.</span></span>

<span data-ttu-id="42524-187">含めるまたは除外する個々の OneDrive アカウントを指定できる URL の形式は次のとおりです: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="42524-187">To specify individual OneDrive accounts to include or exclude, the URL has the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>

<span data-ttu-id="42524-188">たとえば、「rsimone」のユーザー名を持つ contoso テナント内のユーザーの場合: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="42524-188">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>

<span data-ttu-id="42524-189">テナントの構文を確認し、ユーザーの URL を特定するには、「[組織内のすべてのユーザーの OneDrive URL のリストを取得する](https://docs.microsoft.com/onedrive/list-onedrive-urls)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-189">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="42524-190">Microsoft 365 グループの構成情報</span><span class="sxs-lookup"><span data-stu-id="42524-190">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="42524-191">Microsoft 365 グループ (以前の Office 365 グループ) のコンテンツを保持または削除するには、**Office 365 グループ**の場所を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42524-191">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), use the **Office 365 groups** location.</span></span> <span data-ttu-id="42524-192">Microsoft 365 グループには Exchange メールボックスがありますが、**Exchange メール**の場所全体が含まれるアイテム保持ポリシーには、Microsoft 365 グループのメールボックスのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="42524-192">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="42524-193">また、最初は **Exchange メール**の場所でグループ メールボックスを含めるか除外するかを指定できますが、アイテム保持ポリシーを保存しようとすると、Exchange の場所では「RemoteGroupMailbox」を選択できないことを示すエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="42524-193">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="42524-194">Microsoft 365 グループに適用されるアイテム保持ポリシーには、グループ メールボックスおよびサイトの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="42524-194">A retention policy applied to a Microsoft 365 group includes both the group mailbox and site.</span></span> <span data-ttu-id="42524-195">Microsoft 365 グループに適用されるアイテム保持ポリシーは、Microsoft Teams を含む Microsoft 365 グループによって作成されたリソースを保護します。</span><span class="sxs-lookup"><span data-stu-id="42524-195">A retention policy applied to a Microsoft 365 group protects the resources created by a Microsoft 365 group, which includes Microsoft Teams.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="42524-196">Skype for Business の構成情報</span><span class="sxs-lookup"><span data-stu-id="42524-196">Configuration information for Skype for Business</span></span>

<span data-ttu-id="42524-197">Exchange メールとは異なり Skype の場所の状態をオンに切り替えてすべてのユーザーを含めることはできませんが、そのロケーションをオンにしてから、会話を保持するユーザーを手動で選択できます。</span><span class="sxs-lookup"><span data-stu-id="42524-197">Unlike Exchange email, you can't toggle the status of the Skype location on to include all users, but when you turn on that location, you then manually choose the users whose conversations you want to retain:</span></span>

![アイテム保持ポリシーの Skype の場所を選択する](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="42524-199">[**ユーザーの選択**] を選択すると、列ヘッダーの [**名前**] ボックスを選択して、すべてのユーザーをすばやく含めることができます。</span><span class="sxs-lookup"><span data-stu-id="42524-199">When you select **Choose users**, you can quickly include all users by selecting the **Name** box in the column header.</span></span> <span data-ttu-id="42524-200">ただし、各ユーザーはポリシーの特定のインクルージョンとしてカウントされることを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="42524-200">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="42524-201">したがって、1,000 人を超えるユーザーを含める場合は、前のセクションで述べた制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="42524-201">Therefore, if you include over 1,000 users, the limits noted in the previous section apply.</span></span> <span data-ttu-id="42524-202">ここですべての Skype ユーザーを選択することは、組織全体のポリシーに規定ですべての Skype ユーザーを含めることができた場合と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="42524-202">Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![Skype ユーザーの選択ページ](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="42524-p121">Outlook のフォルダー **[会話履歴]** は、Skype のアーカイブには作用しない機能です。**[会話履歴]** はエンド ユーザーが無効にできますが、Skype のアーカイブの場合はユーザーがアクセスできない (電子情報開示には使用できる) 非表示フォルダーに Skype の会話のコピーが保存されます。</span><span class="sxs-lookup"><span data-stu-id="42524-p121">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving. **Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>


## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="42524-206">コンテンツを保持および削除するための設定</span><span class="sxs-lookup"><span data-stu-id="42524-206">Settings for retaining and deleting content</span></span>

<span data-ttu-id="42524-207">アイテム保持ポリシーでコンテンツを保持および削除するための設定を選択すると、アイテム保持ポリシーは、指定された期間、次のいずれかの構成になります。</span><span class="sxs-lookup"><span data-stu-id="42524-207">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="42524-208">保持のみ</span><span class="sxs-lookup"><span data-stu-id="42524-208">Retain-only</span></span>
- <span data-ttu-id="42524-209">保持してから削除</span><span class="sxs-lookup"><span data-stu-id="42524-209">Retain and then delete</span></span>
- <span data-ttu-id="42524-210">削除のみ</span><span class="sxs-lookup"><span data-stu-id="42524-210">Delete-only</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="42524-211">コンテンツを特定の期間保持する</span><span class="sxs-lookup"><span data-stu-id="42524-211">Retaining content for a specific period of time</span></span>

<span data-ttu-id="42524-212">アイテム保持ポリシーを構成するときは、コンテンツを無期限に、または特定の日数、月数、または年数の間保持することを選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-212">When you configure a retention policy, you choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="42524-213">コンテンツが保持される期間は、アイテム保持ポリシーが適用された時点からではなくコンテンツの経過時間から計算されます。</span><span class="sxs-lookup"><span data-stu-id="42524-213">The duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied.</span></span> <span data-ttu-id="42524-214">経過時間は、コンテンツが作成された日時に基づく場合と、(OneDrive および SharePoint の場合) コンテンツが最後に変更された日時に基づく場合から選択できます。</span><span class="sxs-lookup"><span data-stu-id="42524-214">You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>

<span data-ttu-id="42524-215">例:</span><span class="sxs-lookup"><span data-stu-id="42524-215">Examples:</span></span>
  
- <span data-ttu-id="42524-216">SharePoint: サイト コレクションのコンテンツを最後に変更してから 7 年間保持する場合に、そのサイト コレクションのドキュメントが 6 年変更されていないと、そのドキュメントが変更されなければあと 1 年間しか保持されません。</span><span class="sxs-lookup"><span data-stu-id="42524-216">SharePoint: If you want to retain content in a site collection for seven years since it was last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="42524-217">そのドキュメントがもう一度編集された場合、ドキュメントの古さは最後に変更された日付から計算され、その後 7 年間保留にされます。</span><span class="sxs-lookup"><span data-stu-id="42524-217">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="42524-218">Exchange: メールボックスのコンテンツを 7 年間保持する場合、あるメッセージが 6 年前に送信されているときは、あと 1 年間のみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="42524-218">Exchange: If you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="42524-219">Exchange コンテンツの場合、経過時間は受信メールの受信日または送信メールの送信日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="42524-219">For Exchange content, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="42524-220">最終更新日に基づいてコンテンツを保持するポリシーは、OneDrive および SharePoint のコンテンツ サイトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="42524-220">Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="42524-221">保持期間の終了時にコンテンツを完全に削除するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-221">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![[アイテム保持設定] ページ](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="42524-223">特定の経過時間を超えた古いコンテンツを削除する</span><span class="sxs-lookup"><span data-stu-id="42524-223">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="42524-224">アイテム保持ポリシーは、コンテンツを保持してから削除することも、古いコンテンツを保持せずに削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="42524-224">A retention policy can both retain and then delete content, or delete old content without retaining it.</span></span>
  
<span data-ttu-id="42524-225">アイテム保持ポリシーによってコンテンツを削除する場合、アイテム保持ポリシーに指定した期間は、ポリシーが割り当てられた時点からではなく、コンテンツが作成または変更された時点から計算されることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="42524-225">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![[削除の設定]](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="42524-227">たとえば、保持して 3 年間を過ぎたコンテンツを削除するアイテム保持ポリシーを作成し、それをすべての OneDrive アカウントに割り当てるとします。アカウントには、4 から 5 年前に作成されたコンテンツが数多く含まれています。</span><span class="sxs-lookup"><span data-stu-id="42524-227">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago.</span></span> <span data-ttu-id="42524-228">このような場合、最初にアイテム保持ポリシーが割り当てられてすぐに、コンテンツの多くが削除されます。</span><span class="sxs-lookup"><span data-stu-id="42524-228">In this case, a lot of content will be deleted soon after assigning the retention policy for the first time.</span></span> <span data-ttu-id="42524-229">このような理由から、コンテンツを削除するアイテム保持ポリシーは、コンテンツにかなりの影響を与える可能性があることを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="42524-229">For this reason, it's important to understand that a retention policy that deletes content can have a considerable impact on your content.</span></span> 
  
<span data-ttu-id="42524-p126">そのため、サイト コレクションに初めてポリシーを割り当てるときには、その前に、既存のコンテンツの経過時間と、そのコンテンツにポリシーが及ぼす影響について考慮する必要があります。また、新しいポリシーを割り当てる前に、サイト所有者に連絡して、発生する可能性のある影響について評価するための時間を与えるようにしてください。アイテム保持ポリシーの作成前に設定を確認すると、この警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="42524-p126">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content. You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact. Note this warning that appears when you review the settings for your retention policy just before creating it.</span></span>
  
![コンテンツの削除に関する警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a><span data-ttu-id="42524-234">特定の条件を満たすコンテンツを特定するための詳細設定</span><span class="sxs-lookup"><span data-stu-id="42524-234">Advanced settings to identify content that meets specific conditions</span></span>

<span data-ttu-id="42524-235">アイテム保持ポリシーは、その場所に含まれるすべてのコンテンツに適用することも、特定のキーワードや[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツにのみ適用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="42524-235">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![高度なアイテム保持のオプション](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a><span data-ttu-id="42524-237">特定のキーワードを含むコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="42524-237">Identify content that contains specific keywords</span></span>

<span data-ttu-id="42524-238">特定の条件を満たすコンテンツにのみアイテム保持ポリシーを適用し、そのコンテンツだけを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="42524-238">You can apply a retention policy only to content that meets specific conditions, and then take retention actions on just that content.</span></span> <span data-ttu-id="42524-239">利用できる条件で、特定の単語または語句を含むコンテンツにアイテム保持ポリシーを適用するようになります。</span><span class="sxs-lookup"><span data-stu-id="42524-239">The conditions available support applying a retention policy to content that contains specific words or phrases.</span></span> <span data-ttu-id="42524-240">AND、OR、NOT などの検索演算子を使用して、クエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="42524-240">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="42524-241">このような演算子の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42524-241">For more information on these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="42524-242">検索可能なプロパティ (**件名:** など) の追加については間もなくサポートされます。</span><span class="sxs-lookup"><span data-stu-id="42524-242">Support for adding searchable properties (for example, **subject:**) is coming soon.</span></span>
  
<span data-ttu-id="42524-243">クエリベースの保持では、検索インデックスを使用してコンテンツを識別します。</span><span class="sxs-lookup"><span data-stu-id="42524-243">Query-based retention uses the search index to identify content.</span></span>
  
![クエリ エディター](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a><span data-ttu-id="42524-245">機密情報が含まれているコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="42524-245">Identify content that contains sensitive information</span></span>

<span data-ttu-id="42524-246">[特定の種類の機密情報](what-the-sensitive-information-types-look-for.md)を含むコンテンツにのみ、アイテム保持ポリシーを適用させることができます。</span><span class="sxs-lookup"><span data-stu-id="42524-246">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span> <span data-ttu-id="42524-247">たとえば、納税者番号、社会保障番号、パスポート番号などの個人情報を含むコンテンツにのみ、固有の保持要件を適用するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="42524-247">For example, you can choose to apply unique retention requirements only to content that contains personal information, such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![機密情報の種類のページ](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="42524-249">注:</span><span class="sxs-lookup"><span data-stu-id="42524-249">Notes:</span></span>
  
- <span data-ttu-id="42524-250">機密情報に対応する高度な保持は、Exchange のパブリック フォルダーや Skype for Business には適用されません (これらの場所が機密情報の種類をサポートしていないため)。</span><span class="sxs-lookup"><span data-stu-id="42524-250">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="42524-251">Exchange Online はメール フロー ルール (トランスポート ルールとも呼ばれます) を使用して機密情報を特定するため、既にメールボックスに保存されているすべてのアイテムにではなく、送受信するメッセージにのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="42524-251">Exchange Online uses mail flow rules (also known as transport rules) to identify sensitive information, so this works only on messages in transit—not on all items already stored in a mailbox.</span></span> <span data-ttu-id="42524-252">つまり、Exchange Online の場合、アイテム保持ポリシーは、ポリシーがメールボックスに適用された**後**に受信したメッセージに対してのみ機密情報を特定して、保持することができます </span><span class="sxs-lookup"><span data-stu-id="42524-252">For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox.</span></span> <span data-ttu-id="42524-253">前のセクションで説明したクエリ ベースの保持では、コンテンツを特定する際に検索インデックスが使用されるため、このような制限がありません。</span><span class="sxs-lookup"><span data-stu-id="42524-253">Query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="42524-254">アイテム保持ポリシーを組織全体または特定の場所に適用する</span><span class="sxs-lookup"><span data-stu-id="42524-254">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="42524-255">アイテム保持ポリシーは、組織全体、場所全体、または特定の場所やユーザーのみに簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="42524-255">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="42524-256">組織全体のポリシー</span><span class="sxs-lookup"><span data-stu-id="42524-256">Org-wide policy</span></span>

<span data-ttu-id="42524-257">アイテム保持ポリシーの強力な機能の 1 つとして、Microsoft 365 全体の場所に適用されます。これには、次の場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="42524-257">One of the most powerful features of a retention policy is that it can apply to locations across Microsoft 365, including:</span></span>
  
- <span data-ttu-id="42524-258">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="42524-258">Exchange email</span></span>
    
- <span data-ttu-id="42524-259">SharePoint サイト コレクション</span><span class="sxs-lookup"><span data-stu-id="42524-259">SharePoint site collections</span></span>
    
- <span data-ttu-id="42524-260">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="42524-260">OneDrive accounts</span></span>
    
- <span data-ttu-id="42524-261">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="42524-261">Microsoft 365 groups</span></span>
    
- <span data-ttu-id="42524-262">Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="42524-262">Exchange public folders</span></span>
    

![すべての場所のオプション](../media/retention-policies-all-locations.png)

<span data-ttu-id="42524-264">その他の組織全体のアイテム保持ポリシーに関する重要な機能は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42524-264">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="42524-265">ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="42524-265">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="42524-266">Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="42524-266">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="42524-267">場所全体に適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="42524-267">A policy that applies to entire locations</span></span>

<span data-ttu-id="42524-268">場所を選択すると、Exchange メールや OneDrive アカウントなど、場所全体を簡単に含めたり除外したりできます。</span><span class="sxs-lookup"><span data-stu-id="42524-268">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts.</span></span> <span data-ttu-id="42524-269">これを行うには、その場所の [**状態**] をオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="42524-269">To do so, toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="42524-270">組織全体のポリシーと同様に、場所全体の任意の組み合わせにポリシーが適用される場合、ポリシーに含めることができるメールボックスまたはサイトの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="42524-270">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include.</span></span> 

<span data-ttu-id="42524-271">たとえば、ポリシーにすべての Exchange メールとすべての SharePoint サイトが含まれている場合、数に関係なくすべてのサイトとメールボックスが含められます。</span><span class="sxs-lookup"><span data-stu-id="42524-271">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many.</span></span> <span data-ttu-id="42524-272">また、Exchange の場合、ポリシーの適用後に作成された新しいメールボックスには、そのポリシーが自動的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="42524-272">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="42524-273">特定の追加または除外を含むポリシー</span><span class="sxs-lookup"><span data-stu-id="42524-273">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="42524-274">特定のユーザー、特定の Microsoft 365 グループ、または特定のサイトにアイテム保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="42524-274">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="42524-275">そのためには、目的の場所の [**状態**] をオンに切り替えた上で、リンクを使用して特定のユーザー、Microsoft 365 グループ、またはサイトを含めたり除外したりします。</span><span class="sxs-lookup"><span data-stu-id="42524-275">To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="42524-276">ただし、この設定を使用すると、保持ポリシーに 1,000 を超える特定の場所が含まれている場合、または除外される場合、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="42524-276">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific locations:</span></span>
  
- <span data-ttu-id="42524-277">アイテム保持ポリシーの最大数:</span><span class="sxs-lookup"><span data-stu-id="42524-277">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="42524-278">1,000 個のメールボックス</span><span class="sxs-lookup"><span data-stu-id="42524-278">1,000 mailboxes</span></span>
    - <span data-ttu-id="42524-279">1,000 個の Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="42524-279">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="42524-280">Teams のプライベート チャットのユーザー 1,000 人</span><span class="sxs-lookup"><span data-stu-id="42524-280">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="42524-281">100 個のサイト (OneDrive または SharePoint)</span><span class="sxs-lookup"><span data-stu-id="42524-281">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="42524-282">テナントでサポートされるポリシーの最大数は 10,000 です。</span><span class="sxs-lookup"><span data-stu-id="42524-282">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="42524-283">これらのアイテムには、アイテム保持ポリシー、保持ラベル ポリシー、および自動適用アイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="42524-283">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="42524-284">アイテム保持ポリシーがこれらの制限の影響を受ける可能性がある場合は、場所全体に適用される構成オプションを選択するか、組織全体のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="42524-284">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations, or use an org-wide policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="42524-285">アイテム保持ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="42524-285">Updating retention policies</span></span>

<span data-ttu-id="42524-286">アイテム保持ポリシーを編集し、コンテンツが既にアイテム保持ポリシーの元の設定の対象となっている場合、更新された設定は、新しく特定されたコンテンツに加えて、このコンテンツに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="42524-286">If you edit a retention policy and content is already subject to the original settings in your retention policy, your updated settings will be automatically applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="42524-287">通常、この更新はかなり迅速ですが、数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="42524-287">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="42524-288">Microsoft 365 の場所間でのポリシーの複製が完了すると、Microsoft 365 コンプライアンス センターの保持ポリシーの状態が [**On (保留中)**] から [**オン (成功)**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="42524-288">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="42524-289">PowerShell を使用してアイテム保持ポリシーをロックする</span><span class="sxs-lookup"><span data-stu-id="42524-289">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="42524-290">規制要件に準拠するために [[保持ロック](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)] を使用する必要がある場合は、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42524-290">You must use PowerShell if you need to use [Preservation Lock](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span>

1. <span data-ttu-id="42524-291">[セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="42524-291">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="42524-292">アイテム保持ポリシーを一覧表示し、`Get-RetentionCompliancePolicy` を実行してロックするポリシーの名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="42524-292">List your retention policies and find the name of the policy that you want to lock by running `Get-RetentionCompliancePolicy`.</span></span>
    
   ![PowerShell のアイテム保持ポリシーの一覧](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="42524-294">アイテム保持ポリシーに [保持ロック] を設定するには `Set-RetentionCompliancePolicy` を実行しますが、その際に `RestrictiveRetention` パラメーターを true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42524-294">To place a Preservation Lock on a retention policy, run `Set-RetentionCompliancePolicy` with the `RestrictiveRetention` parameter set to true.</span></span> <span data-ttu-id="42524-295">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="42524-295">For example:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
   ```
   
   ![PowerShell の RestrictiveRetention パラメーター](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
   <span data-ttu-id="42524-297">そのコマンドレットを実行した後、[**すべてはい**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="42524-297">After you run that cmdlet, choose **Yes to All**:</span></span>
    
   ![PowerShell でアイテム保持ポリシーをロックすることを確認するプロンプト](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="42524-299">アイテム保持ポリシーに保持ロックが設定されました。</span><span class="sxs-lookup"><span data-stu-id="42524-299">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="42524-300">`Get-RetentionCompliancePolicy`を実行すると、`RestrictiveRetention`パラメーターは true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="42524-300">If you run `Get-RetentionCompliancePolicy`, the `RestrictiveRetention` parameter is set to true.</span></span> <span data-ttu-id="42524-301">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="42524-301">For example:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

![PowerShell に表示されるすべてのパラメーターを含むロックされたポリシー](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

