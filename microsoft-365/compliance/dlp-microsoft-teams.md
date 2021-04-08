---
title: データ損失防止と Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: これで、Microsoft Teams のチャットとチャネルに DLP ポリシーを適用できます。 この記事では、その動作について詳しくは、この記事を参照してください。
ms.openlocfilehash: bd6fa1c04a57f64997d5646374007641afa0f958
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632239"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="abf36-104">データ損失防止と Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abf36-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="abf36-105">データ損失防止機能は、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 Information Protection and Governance、または Office 365 Advanced Compliance のライセンスを取得したユーザー向け Microsoft Teams チャットおよびチャネル メッセージに最近追加されました。</span><span class="sxs-lookup"><span data-stu-id="abf36-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="abf36-106">Office 365 および Microsoft 365 E3 には、SharePoint Online、OneDrive、および Exchange Online の DLP 保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="abf36-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="abf36-107">また、Teams は SharePoint Online と OneDrive を使用してファイルを共有するために Teams を介して共有されるファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="abf36-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="abf36-108">Teams チャットでの DLP 保護のサポートには、E5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="abf36-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="abf36-109">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf36-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="abf36-110">Microsoft Teams 用 DLP の概要</span><span class="sxs-lookup"><span data-stu-id="abf36-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="abf36-111">最近では [、データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、Microsoft Teams のチャット メッセージとチャネル メッセージ (プライベート チャネル メッセージを含む) **が含まれるまで拡張されました**。</span><span class="sxs-lookup"><span data-stu-id="abf36-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="abf36-112">DLP は現在、チャットスレッドまたはチャネル スレッドの実際のメッセージにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="abf36-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="abf36-113">アクティビティ通知 (短いメッセージ プレビューを含み、ユーザーの通知設定に基づいて表示される)は、現時点では Teams DLP には含まれません。</span><span class="sxs-lookup"><span data-stu-id="abf36-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="abf36-114">メッセージの一部に表示される機密情報は、DLP ポリシーが適用され、メッセージ自体の機密情報が削除された後でも、通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="abf36-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="abf36-115">組織に DLP がある場合は、Microsoft Teams チャネルまたはチャット セッションで機密情報を共有するユーザーを防止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="abf36-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="abf36-116">この保護のしくみの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="abf36-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="abf36-117">**例 1: メッセージ内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="abf36-118">Teams チャットまたはチャネル内の機密情報をゲスト (外部ユーザー) と共有しようとしたとします。</span><span class="sxs-lookup"><span data-stu-id="abf36-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="abf36-119">これを防ぐために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="abf36-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="abf36-120">これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。</span><span class="sxs-lookup"><span data-stu-id="abf36-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="abf36-121">Microsoft Teams の DLP は、次の権限を持つ Microsoft Teams ユーザーと共有すると、機密コンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="abf36-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="abf36-122">- [チームとチャネル](/MicrosoftTeams/guest-access) でのゲスト アクセス。または</span><span class="sxs-lookup"><span data-stu-id="abf36-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="abf36-123">- [会議およびチャット](/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。</span><span class="sxs-lookup"><span data-stu-id="abf36-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="abf36-124">外部チャット セッションの DLP は、送信者と受信者の両方が Teams Only モードで Microsoft Teams ネイティブ フェデレーションを使用している場合にのみ [機能します](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="abf36-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="abf36-125">TEAMS の DLP は、Skype for Business またはネイティブ以外のフェデレーション チャット セッションとの相互運用のメッセージをブロックしません。 [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="abf36-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="abf36-126">**例 2: ドキュメント内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="abf36-127">Microsoft Teams チャネルまたはチャットのゲストとドキュメントを共有しようとすると、そのドキュメントに機密情報が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="abf36-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="abf36-128">これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。</span><span class="sxs-lookup"><span data-stu-id="abf36-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="abf36-129">この場合、保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf36-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="abf36-130">(これは、Microsoft Teams に表示される SharePoint 用 DLP の例であり、Office 365 DLP (Office 365 E3 に含まれる) のライセンスをユーザーに要求しますが、Office 365 Advanced Compliance のライセンスをユーザーに要求しません)。</span><span class="sxs-lookup"><span data-stu-id="abf36-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="abf36-131">ポリシー ヒントは、ユーザーの教育に役立ちます</span><span class="sxs-lookup"><span data-stu-id="abf36-131">Policy tips help educate users</span></span>

<span data-ttu-id="abf36-132">[Exchange、Outlook、Outlook on the](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)web、SharePoint [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、[および Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーと競合するとポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="abf36-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="abf36-133">ポリシー ヒントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="abf36-133">Here's an example of a policy tip:</span></span>

![Teams のブロックされたメッセージ通知](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="abf36-135">この場合、送信者は Microsoft Teams チャネルで社会保障番号を共有しようとした。</span><span class="sxs-lookup"><span data-stu-id="abf36-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="abf36-136">[ **実行できる操作] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="abf36-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="abf36-137">この場合、送信者はポリシーを上書きするか、管理者に確認と解決を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="abf36-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![ブロックされたメッセージを解決するためのオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="abf36-139">組織では、ユーザーに DLP ポリシーの上書きを許可できます。</span><span class="sxs-lookup"><span data-stu-id="abf36-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="abf36-140">また、DLP ポリシーを構成する場合は、既定のポリシー ヒントを使用するか、組織の [ポリシー ヒント](#to-customize-policy-tips) をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="abf36-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="abf36-141">送信者が Teams チャネルで社会保障番号を共有した例に戻り、受信者が見た情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="abf36-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abf36-142">![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

<span data-ttu-id="abf36-143">**[What's this?** ][](data-loss-prevention-policies.md)リンクは DLP ポリシーに関する記事を開き、メッセージがブロックされた理由を説明するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="abf36-143">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="abf36-144">ポリシーのヒントをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="abf36-144">To customize policy tips</span></span>

<span data-ttu-id="abf36-145">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf36-145">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="abf36-146">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf36-146">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="abf36-147">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="abf36-147">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="abf36-148">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-148">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="abf36-149">ポリシーを選択し、[ポリシー設定] の **横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-149">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="abf36-150">新しいルールを作成するか、ポリシーの既存のルールを編集します。</span><span class="sxs-lookup"><span data-stu-id="abf36-150">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-151">![ポリシーのルールの編集](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-151">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="abf36-152">[ユーザー通知 **] タブで** 、[メール テキストの **カスタマイズ** ] または [ポリシー ヒントのテキスト **オプションのカスタマイズ] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="abf36-152">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-153">![ユーザー通知とポリシーヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-153">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="abf36-154">電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-154">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="abf36-155">[ポリシー設定 **] タブで** 、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-155">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="abf36-156">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="abf36-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="abf36-157">Microsoft Teams を場所として既存の DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="abf36-157">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="abf36-158">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf36-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="abf36-159">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf36-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="abf36-160">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="abf36-160">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="abf36-161">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-161">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="abf36-162">ポリシーを選択し、[場所] の下の値 **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-162">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="abf36-163">Teams のチャット **メッセージとチャネル メッセージが表示される** 場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="abf36-163">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="abf36-164">編集しない場合は、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="abf36-164">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-165">![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-165">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="abf36-166">[状態 **] 列** で、Teams チャット メッセージとチャネル メッセージの **ポリシーをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="abf36-166">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-167">![Teams のチャットとチャネルの DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-167">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="abf36-168">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-168">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="abf36-169">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abf36-169">You can specify:</span></span>

    1. <span data-ttu-id="abf36-170">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="abf36-170">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="abf36-171">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="abf36-171">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="abf36-172">**これはパブリック プレビュー機能です。**</span><span class="sxs-lookup"><span data-stu-id="abf36-172">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="abf36-173">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf36-173">Then choose **Next**.</span></span>

7. <span data-ttu-id="abf36-174">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abf36-174">Click **Save**.</span></span>

<span data-ttu-id="abf36-175">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="abf36-175">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="abf36-176">Microsoft Teams の新しい DLP ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="abf36-176">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="abf36-177">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf36-177">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="abf36-178">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf36-178">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="abf36-179">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="abf36-179">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="abf36-180">[**データ損失防止ポリシー] +**  >    >  **[ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-180">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="abf36-181">テンプレートを選択 [し、[](data-loss-prevention-policies.md#dlp-policy-templates)次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-181">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="abf36-182">この例では、米国の個人を特定できる情報データ テンプレートを選択しました。</span><span class="sxs-lookup"><span data-stu-id="abf36-182">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-183">![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-183">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="abf36-184">[ポリシー **に名前を付け** ] タブで、ポリシーの名前と説明を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-184">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="abf36-185">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-185">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="abf36-186">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="abf36-186">You can specify:</span></span>

    1. <span data-ttu-id="abf36-187">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="abf36-187">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="abf36-188">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="abf36-188">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="abf36-189">**これはパブリック プレビュー機能です。**</span><span class="sxs-lookup"><span data-stu-id="abf36-189">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="abf36-191">機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams チャットメッセージとチャネル メッセージと共にオンになっていることを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-191">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="abf36-192">[ポリシー設定 **] タブ** の[保護するコンテンツの種類をカスタマイズする] で、既定の単純な設定を保持するか、[詳細設定を使用する] を選択して、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-192">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="abf36-193">詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="abf36-193">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="abf36-194">(このヘルプについては、「簡易設定 [と詳細設定」を参照](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)してください。</span><span class="sxs-lookup"><span data-stu-id="abf36-194">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="abf36-195">[ポリシー **設定] タブ** の **[機密情報** が検出された場合の操作] で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="abf36-195">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="abf36-196">(既定のポリシー ヒントと電子メール通知を[](use-notifications-and-policy-tips.md)保持するか、カスタマイズすることもできます)。</span><span class="sxs-lookup"><span data-stu-id="abf36-196">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-197">![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-197">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="abf36-198">設定の確認または編集が完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-198">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="abf36-199">[ポリシーの **設定**] タブの [ポリシーを有効にするか、最初にテストするのかを選択しますか **?]** で、ポリシーを有効 [](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)にするか、最初にテストするか、今のところオフにしておき、[次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf36-199">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="abf36-200">![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-200">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="abf36-201">[設定 **の確認] タブ** で、新しいポリシーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="abf36-201">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="abf36-202">[編集 **] を** 選択して変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="abf36-202">Choose **Edit** to make changes.</span></span> <span data-ttu-id="abf36-203">完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="abf36-203">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="abf36-204">新しいポリシーがデータセンター経由で動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="abf36-204">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="abf36-205">機密文書への外部アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="abf36-205">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="abf36-206">機密情報を含む SharePoint ドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="abf36-206">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="abf36-207">新しいファイルを既定で機密性の高いファイルとしてマークすることで、DLP スキャンが行い、共有が安全とマークされるまで、ドキュメントが [確実に保護されます](/sharepoint/sensitive-by-default)。</span><span class="sxs-lookup"><span data-stu-id="abf36-207">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="abf36-208">推奨される DLP ポリシー構造</span><span class="sxs-lookup"><span data-stu-id="abf36-208">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="abf36-209">**条件**</span><span class="sxs-lookup"><span data-stu-id="abf36-209">**Conditions**</span></span>
        - <span data-ttu-id="abf36-210">コンテンツには、次の機密情報の種類が含まれる。 [適用されるすべて選択]</span><span class="sxs-lookup"><span data-stu-id="abf36-210">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="abf36-211">Microsoft 365 から組織外のユーザーとコンテンツを共有する</span><span class="sxs-lookup"><span data-stu-id="abf36-211">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="abf36-212">![機密性の高いコンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-212">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="abf36-213">**Actions**</span><span class="sxs-lookup"><span data-stu-id="abf36-213">**Actions**</span></span>
        - <span data-ttu-id="abf36-214">外部ユーザーのコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="abf36-214">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="abf36-215">メールおよびポリシー ヒントでユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="abf36-215">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="abf36-216">インシデント レポートを管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="abf36-216">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="abf36-217">![機密性の高いコンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-217">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="abf36-218">機密情報を含む SharePoint でドキュメントを外部ゲストと共有しようとすると、DLP ポリシーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="abf36-218">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abf36-219">![外部共有がブロックされている](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-219">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="abf36-220">ゲストが Teams でドキュメントを開き、外部ブロックを使用すると、DLP ポリシーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="abf36-220">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abf36-221">![外部アクセスがブロックされている](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="abf36-221">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="abf36-222">関連記事</span><span class="sxs-lookup"><span data-stu-id="abf36-222">Related articles</span></span>

[<span data-ttu-id="abf36-223">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="abf36-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="abf36-224">メール通知を送信して、DLP ポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="abf36-224">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
