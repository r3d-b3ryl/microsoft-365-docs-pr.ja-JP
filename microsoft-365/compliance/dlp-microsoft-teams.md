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
description: これで、DLP ポリシーを他のチャットMicrosoft Teamsに適用できます。 この記事では、その動作について詳しくは、この記事を参照してください。
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572467"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="157b4-104">データ損失防止と Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="157b4-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="157b4-105">データ損失防止機能は、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 Information Protection and Governance または Office 365 Advanced Compliance のライセンスを持つユーザーの Microsoft Teams チャットおよびチャネル メッセージに最近追加されました。</span><span class="sxs-lookup"><span data-stu-id="157b4-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="157b4-106">Office 365およびMicrosoft 365 E3には、オンライン、SharePoint、およびOneDriveの DLP 保護Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="157b4-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="157b4-107">また、このファイルには、Teamsを共有TeamsオンラインとSharePointをOneDriveするファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="157b4-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="157b4-108">チャットでの DLP 保護のサポートTeams E5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="157b4-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="157b4-109">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157b4-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="157b4-110">Microsoft Teams 用 DLP の概要</span><span class="sxs-lookup"><span data-stu-id="157b4-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="157b4-111">最近では [、データ損失防止](dlp-learn-about-dlp.md)機能が拡張され、プライベート チャネル メッセージMicrosoft Teams含むチャット メッセージやチャネル メッセージ **が含まれるまで拡張されました**。</span><span class="sxs-lookup"><span data-stu-id="157b4-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="157b4-112">DLP は現在、チャットスレッドまたはチャネル スレッドの実際のメッセージにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="157b4-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="157b4-113">アクティビティ通知 (短いメッセージ プレビューを含み、ユーザーの通知設定に基づいて表示される)は、現時点では Teams DLP には含まれません。</span><span class="sxs-lookup"><span data-stu-id="157b4-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="157b4-114">メッセージの一部に表示される機密情報は、DLP ポリシーが適用され、メッセージ自体の機密情報が削除された後でも、通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="157b4-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="157b4-115">組織に DLP がある場合は、ユーザーが機密情報を共有するセキュリティ チャネルまたはチャット セッションでユーザーがMicrosoft Teamsポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="157b4-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="157b4-116">この保護のしくみの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="157b4-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="157b4-117">**例 1: メッセージ内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="157b4-118">ユーザーがチャットまたはチャネル内の機密情報をゲスト (外部ユーザー) Teams共有しようとしたとします。</span><span class="sxs-lookup"><span data-stu-id="157b4-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="157b4-119">これを防ぐために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="157b4-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="157b4-120">これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。</span><span class="sxs-lookup"><span data-stu-id="157b4-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="157b4-121">DLP for Microsoft Teamsは、次の権限を持つユーザーと共有Microsoft Teamsコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="157b4-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="157b4-122">- [チームとチャネル](/MicrosoftTeams/guest-access) でのゲスト アクセス。または</span><span class="sxs-lookup"><span data-stu-id="157b4-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="157b4-123">- [会議およびチャット](/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。</span><span class="sxs-lookup"><span data-stu-id="157b4-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="157b4-124">外部チャット セッションの DLP は、送信者と受信者の両方が Teams モードでネイティブ フェデレーションMicrosoft Teams[使用している場合にのみ機能します](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="157b4-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="157b4-125">ユーザーの DLP Teams、またはネイティブ以外[](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)のフェデレーション チャット セッションとの相互運用Skype for Businessメッセージをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="157b4-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="157b4-126">**例 2: ドキュメント内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="157b4-127">ユーザーがチャネルまたはチャットのゲストとドキュメントを共有しようとMicrosoft Teams機密情報が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="157b4-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="157b4-128">これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。</span><span class="sxs-lookup"><span data-stu-id="157b4-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="157b4-129">この場合、保護を行うには、DLP ポリシーに SharePointとOneDriveを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="157b4-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="157b4-130">(これは、Microsoft Teams に表示される SharePoint の DLP の例であり、Office 365 DLP (Office 365 E3 に含まれる) のライセンスをユーザーに要求しますが、Office 365 Advanced Compliance のライセンスを取得する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="157b4-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="157b4-131">ポリシー ヒントは、ユーザーの教育に役立ちます</span><span class="sxs-lookup"><span data-stu-id="157b4-131">Policy tips help educate users</span></span>

<span data-ttu-id="157b4-132">web 上の[Exchange、Outlook、Outlook、SharePoint](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、および[Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーと競合するとポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="157b4-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="157b4-133">ポリシー ヒントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="157b4-133">Here's an example of a policy tip:</span></span>

![[ブロックされたメッセージの通知] Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="157b4-135">この場合、送信者は、ユーザーチャネルで社会保障番号をMicrosoft Teamsしました。</span><span class="sxs-lookup"><span data-stu-id="157b4-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="157b4-136">[ **実行できる操作] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="157b4-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="157b4-137">この場合、送信者はポリシーを上書きするか、管理者に確認と解決を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="157b4-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![ブロックされたメッセージを解決するためのオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="157b4-139">組織では、ユーザーに DLP ポリシーの上書きを許可できます。</span><span class="sxs-lookup"><span data-stu-id="157b4-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="157b4-140">また、DLP ポリシーを構成する場合は、既定のポリシー ヒントを使用するか、組織の [ポリシー ヒント](#to-customize-policy-tips) をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="157b4-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="157b4-141">この例に戻り、送信者がユーザー チャネルで社会保障番号を共有Teams、受信者が見た情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="157b4-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="157b4-142">![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="157b4-143">ポリシーのヒントをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="157b4-143">To customize policy tips</span></span>

<span data-ttu-id="157b4-144">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="157b4-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="157b4-145">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157b4-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="157b4-146">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="157b4-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="157b4-147">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="157b4-148">ポリシーを選択し、[ポリシー設定] の **横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="157b4-149">新しいルールを作成するか、ポリシーの既存のルールを編集します。</span><span class="sxs-lookup"><span data-stu-id="157b4-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-150">![ポリシーのルールの編集](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="157b4-151">[ユーザー通知 **] タブで** 、[メール テキストの **カスタマイズ** ] または [ポリシー ヒントのテキスト **オプションのカスタマイズ] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="157b4-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-152">![ユーザー通知とポリシーヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="157b4-153">電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="157b4-154">[ポリシー設定 **] タブで** 、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="157b4-155">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="157b4-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="157b4-156">Microsoft Teams を場所として既存の DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="157b4-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="157b4-157">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="157b4-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="157b4-158">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157b4-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="157b4-159">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="157b4-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="157b4-160">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="157b4-161">ポリシーを選択し、[場所] の下の値 **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="157b4-162">チャットメッセージと **Teamsメッセージが表示される** 場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="157b4-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="157b4-163">編集しない場合は、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="157b4-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-164">![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="157b4-165">[状態 **] 列** で、チャットメッセージとチャネル メッセージのTeams **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="157b4-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-166">![チャットとチャネルTeams DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="157b4-167">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="157b4-168">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="157b4-168">You can specify:</span></span>

    1. <span data-ttu-id="157b4-169">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="157b4-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="157b4-170">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="157b4-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="157b4-171">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="157b4-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="157b4-172">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="157b4-172">Click **Save**.</span></span>

<span data-ttu-id="157b4-173">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="157b4-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="157b4-174">Microsoft Teams の新しい DLP ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="157b4-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="157b4-175">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="157b4-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="157b4-176">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="157b4-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="157b4-177">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="157b4-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="157b4-178">[**データ損失防止ポリシー] +**  >    >  **[ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="157b4-179">テンプレートを選択 [し、[](data-loss-prevention-policies.md#dlp-policy-templates)次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="157b4-180">この例では、米国の個人を特定できる情報データ テンプレートを選択しました。</span><span class="sxs-lookup"><span data-stu-id="157b4-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-181">![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="157b4-182">[ポリシー **に名前を付け** ] タブで、ポリシーの名前と説明を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="157b4-183">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="157b4-184">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="157b4-184">You can specify:</span></span>

    1. <span data-ttu-id="157b4-185">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="157b4-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="157b4-186">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="157b4-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="157b4-187">**これはパブリック プレビュー機能です。**</span><span class="sxs-lookup"><span data-stu-id="157b4-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="157b4-189">機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams チャットメッセージとチャネル メッセージと共にオン **になっていることを** 確認します。</span><span class="sxs-lookup"><span data-stu-id="157b4-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="157b4-190">[ポリシー設定 **] タブ** の[保護するコンテンツの種類をカスタマイズする] で、既定の単純な設定を保持するか、[詳細設定を使用する] を選択して、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="157b4-191">詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="157b4-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="157b4-192">(このヘルプについては、「簡易設定 [と詳細設定」を参照](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)してください。</span><span class="sxs-lookup"><span data-stu-id="157b4-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="157b4-193">[ポリシー **設定] タブ** の **[機密情報** が検出された場合の操作] で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="157b4-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="157b4-194">(既定のポリシー ヒントと電子メール通知を[](use-notifications-and-policy-tips.md)保持するか、カスタマイズすることもできます)。</span><span class="sxs-lookup"><span data-stu-id="157b4-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-195">![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="157b4-196">設定の確認または編集が完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="157b4-197">[ポリシーの **設定**] タブの [ポリシーを有効にするか、最初にテストするのかを選択しますか **?]** で、ポリシーを有効 [](dlp-overview-plan-for-dlp.md#policy-deployment)にするか、最初にテストするか、今のところオフにしておき、[次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="157b4-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="157b4-198">![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="157b4-199">[設定 **の確認] タブ** で、新しいポリシーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="157b4-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="157b4-200">[編集 **] を** 選択して変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="157b4-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="157b4-201">完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="157b4-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="157b4-202">新しいポリシーがデータセンター経由で動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="157b4-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="157b4-203">機密文書への外部アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="157b4-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="157b4-204">機密情報をSharePoint含むドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="157b4-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="157b4-205">新しいファイルを既定で機密性の高いファイルとしてマークすることで、DLP スキャンが行い、共有が安全とマークされるまで、ドキュメントが [確実に保護されます](/sharepoint/sensitive-by-default)。</span><span class="sxs-lookup"><span data-stu-id="157b4-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="157b4-206">推奨される DLP ポリシー構造</span><span class="sxs-lookup"><span data-stu-id="157b4-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="157b4-207">**条件**</span><span class="sxs-lookup"><span data-stu-id="157b4-207">**Conditions**</span></span>
        - <span data-ttu-id="157b4-208">コンテンツには、次の機密情報の種類が含まれる。 [適用されるすべて選択]</span><span class="sxs-lookup"><span data-stu-id="157b4-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="157b4-209">組織外のユーザー Microsoft 365からコンテンツを共有する</span><span class="sxs-lookup"><span data-stu-id="157b4-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="157b4-210">![機密性の高いコンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="157b4-211">**Actions**</span><span class="sxs-lookup"><span data-stu-id="157b4-211">**Actions**</span></span>
        - <span data-ttu-id="157b4-212">外部ユーザーのコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="157b4-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="157b4-213">メールおよびポリシー ヒントでユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="157b4-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="157b4-214">インシデント レポートを管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="157b4-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="157b4-215">![機密性の高いコンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="157b4-216">機密情報を含むドキュメントを外部ゲストと共有SharePoint DLP ポリシーが動作します。</span><span class="sxs-lookup"><span data-stu-id="157b4-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="157b4-217">![外部共有がブロックされている](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="157b4-218">ゲストが外部ブロックを使用してドキュメントを開Teams DLP ポリシーが有効です。</span><span class="sxs-lookup"><span data-stu-id="157b4-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="157b4-219">![外部アクセスがブロックされている](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="157b4-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="157b4-220">関連記事</span><span class="sxs-lookup"><span data-stu-id="157b4-220">Related articles</span></span>

[<span data-ttu-id="157b4-221">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="157b4-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="157b4-222">メール通知を送信して、DLP ポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="157b4-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
