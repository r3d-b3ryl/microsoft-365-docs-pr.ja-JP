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
ms.openlocfilehash: 3a7b228292952bdba3c950b8ab67501c40e99238
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917923"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="4ac3f-104">データ損失防止と Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ac3f-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="4ac3f-105">データ損失防止機能は、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 Information Protection and Governance、または Office 365 Advanced Compliance のライセンスを取得したユーザー向け Microsoft Teams チャットおよびチャネル メッセージに最近追加されました。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="4ac3f-106">Office 365 および Microsoft 365 E3 には、SharePoint Online、OneDrive、および Exchange Online の DLP 保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="4ac3f-107">また、Teams は SharePoint Online と OneDrive を使用してファイルを共有するために Teams を介して共有されるファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="4ac3f-108">Teams チャットでの DLP 保護のサポートには、E5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="4ac3f-109">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="4ac3f-110">Microsoft Teams 用 DLP の概要</span><span class="sxs-lookup"><span data-stu-id="4ac3f-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="4ac3f-111">最近では [、データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、Microsoft Teams のチャット メッセージとチャネル メッセージ (プライベート チャネル メッセージを含む) **が含まれるまで拡張されました**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span>

<span data-ttu-id="4ac3f-112">組織に DLP がある場合は、Microsoft Teams チャネルまたはチャット セッションで機密情報を共有するユーザーを防止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-112">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="4ac3f-113">この保護のしくみの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-113">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="4ac3f-114">**例 1: メッセージ内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-114">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="4ac3f-115">Teams チャットまたはチャネル内の機密情報をゲスト (外部ユーザー) と共有しようとしたとします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-115">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="4ac3f-116">これを防ぐために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-116">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="4ac3f-117">これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-117">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ac3f-118">Microsoft Teams の DLP は、次の権限を持つ Microsoft Teams ユーザーと共有すると、機密コンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-118">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="4ac3f-119">- [チームとチャネル](/MicrosoftTeams/guest-access) でのゲスト アクセス。または</span><span class="sxs-lookup"><span data-stu-id="4ac3f-119">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="4ac3f-120">- [会議およびチャット](/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-120">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="4ac3f-121">外部チャット セッションの DLP は、送信者と受信者の両方が Teams Only モードで Microsoft Teams ネイティブ フェデレーションを使用している場合にのみ [機能します](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-121">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="4ac3f-122">TEAMS の DLP は、Skype for Business またはネイティブ以外のフェデレーション チャット セッションとの相互運用のメッセージをブロックしません。 [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-122">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="4ac3f-123">**例 2: ドキュメント内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-123">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="4ac3f-124">Microsoft Teams チャネルまたはチャットのゲストとドキュメントを共有しようとすると、そのドキュメントに機密情報が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-124">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="4ac3f-125">これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-125">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="4ac3f-126">この場合、保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-126">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="4ac3f-127">(これは、Microsoft Teams に表示される SharePoint 用 DLP の例であり、Office 365 DLP (Office 365 E3 に含まれる) のライセンスをユーザーに要求しますが、Office 365 Advanced Compliance のライセンスをユーザーに要求しません)。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-127">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="4ac3f-128">ポリシー ヒントは、ユーザーの教育に役立ちます</span><span class="sxs-lookup"><span data-stu-id="4ac3f-128">Policy tips help educate users</span></span>

<span data-ttu-id="4ac3f-129">[Exchange、Outlook、Outlook on the](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)web、SharePoint [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、[および Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーと競合するとポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-129">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="4ac3f-130">ポリシー ヒントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-130">Here's an example of a policy tip:</span></span>

![Teams のブロックされたメッセージ通知](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="4ac3f-132">この場合、送信者は Microsoft Teams チャネルで社会保障番号を共有しようとした。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-132">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="4ac3f-133">[ **実行できる操作] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-133">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="4ac3f-134">この場合、送信者はポリシーを上書きするか、管理者に確認と解決を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-134">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![ブロックされたメッセージを解決するためのオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="4ac3f-136">組織では、ユーザーに DLP ポリシーの上書きを許可できます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-136">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="4ac3f-137">また、DLP ポリシーを構成する場合は、既定のポリシー ヒントを使用するか、組織の [ポリシー ヒント](#to-customize-policy-tips) をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-137">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="4ac3f-138">送信者が Teams チャネルで社会保障番号を共有した例に戻り、受信者が見た情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-138">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="4ac3f-140">**[What's this?** ][](data-loss-prevention-policies.md)リンクは DLP ポリシーに関する記事を開き、メッセージがブロックされた理由を説明するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-140">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="4ac3f-141">ポリシーのヒントをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="4ac3f-141">To customize policy tips</span></span>

<span data-ttu-id="4ac3f-142">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-142">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="4ac3f-143">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-143">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="4ac3f-144">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-144">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="4ac3f-145">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-145">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="4ac3f-146">ポリシーを選択し、[ポリシー設定] の **横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-146">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="4ac3f-147">新しいルールを作成するか、ポリシーの既存のルールを編集します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-147">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![ポリシーのルールの編集](../media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="4ac3f-149">[ユーザー通知 **] タブで** 、[メール テキストの **カスタマイズ** ] または [ポリシー ヒントのテキスト **オプションのカスタマイズ] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-149">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="4ac3f-150">![ユーザー通知とポリシーヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-150">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="4ac3f-151">電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-151">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="4ac3f-152">[ポリシー設定 **] タブで** 、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-152">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="4ac3f-153">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-153">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="4ac3f-154">Microsoft Teams を場所として既存の DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-154">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="4ac3f-155">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-155">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="4ac3f-156">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-156">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="4ac3f-157">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-157">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="4ac3f-158">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-158">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="4ac3f-159">ポリシーを選択し、[場所] の下の値 **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-159">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="4ac3f-160">Teams のチャット **メッセージとチャネル メッセージが表示される** 場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-160">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="4ac3f-161">編集しない場合は、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-161">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="4ac3f-162">![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-162">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="4ac3f-163">[状態 **] 列** で、Teams チャット メッセージとチャネル メッセージの **ポリシーをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-163">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="4ac3f-164">![Teams のチャットとチャネルの DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-164">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="4ac3f-165">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-165">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="4ac3f-166">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-166">You can specify:</span></span>
    1. <span data-ttu-id="4ac3f-167">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-167">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="4ac3f-168">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-168">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="4ac3f-169">**これはパブリック プレビュー機能です。**</span><span class="sxs-lookup"><span data-stu-id="4ac3f-169">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="4ac3f-170">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-170">Then choose **Next**.</span></span>



6. <span data-ttu-id="4ac3f-171">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-171">Click **Save**.</span></span>

<span data-ttu-id="4ac3f-172">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-172">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="4ac3f-173">Microsoft Teams の新しい DLP ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-173">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="4ac3f-174">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-174">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="4ac3f-175">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-175">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="4ac3f-176">コンプライアンス センター ( ) &に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-176">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="4ac3f-177">[**データ損失防止ポリシー] +**  >    >  **[ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-177">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="4ac3f-178">テンプレートを選択 [し、[](data-loss-prevention-policies.md#dlp-policy-templates)次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-178">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="4ac3f-179">この例では、米国の個人を特定できる情報データ テンプレートを選択しました。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-179">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="4ac3f-180">![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-180">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="4ac3f-181">[ポリシー **に名前を付け** ] タブで、ポリシーの名前と説明を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-181">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="4ac3f-182">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-182">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="4ac3f-183">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-183">You can specify:</span></span>
    1. <span data-ttu-id="4ac3f-184">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-184">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="4ac3f-185">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-185">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="4ac3f-186">**これはパブリック プレビュー機能です。**</span><span class="sxs-lookup"><span data-stu-id="4ac3f-186">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> <span data-ttu-id="4ac3f-188">機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams チャットメッセージとチャネル メッセージと共にオンになっていることを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-188">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>


6. <span data-ttu-id="4ac3f-189">[ポリシー設定 **] タブ** の[保護するコンテンツの種類をカスタマイズする] で、既定の単純な設定を保持するか、[詳細設定を使用する] を選択して、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-189">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="4ac3f-190">詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-190">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="4ac3f-191">(このヘルプについては、「簡易設定 [と詳細設定」を参照](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)してください。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-191">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="4ac3f-192">[ポリシー **設定] タブ** の **[機密情報** が検出された場合の操作] で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-192">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="4ac3f-193">(既定のポリシー ヒントと電子メール通知を[](use-notifications-and-policy-tips.md)保持するか、カスタマイズすることもできます)。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-193">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="4ac3f-194">![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-194">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="4ac3f-195">設定の確認または編集が完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-195">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="4ac3f-196">[ポリシーの **設定**] タブの [ポリシーを有効にするか、最初にテストするのかを選択しますか **?]** で、ポリシーを有効 [](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)にするか、最初にテストするか、今のところオフにしておき、[次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-196">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="4ac3f-197">![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-197">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="4ac3f-198">[設定 **の確認] タブ** で、新しいポリシーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-198">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="4ac3f-199">[編集 **] を** 選択して変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-199">Choose **Edit** to make changes.</span></span> <span data-ttu-id="4ac3f-200">完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-200">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="4ac3f-201">新しいポリシーがデータセンター経由で動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-201">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="4ac3f-202">機密文書への外部アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-202">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="4ac3f-203">機密情報を含む SharePoint ドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-203">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="4ac3f-204">新しいファイルを既定で機密性の高いファイルとしてマークすることで、DLP スキャンを実行して共有しても安全とマークされるまで、ドキュメントが [保護されます。](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-204">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default)</span></span>
- <span data-ttu-id="4ac3f-205">推奨される DLP ポリシー構造</span><span class="sxs-lookup"><span data-stu-id="4ac3f-205">Recommended DLP policy structure</span></span>
    - <span data-ttu-id="4ac3f-206">**条件**</span><span class="sxs-lookup"><span data-stu-id="4ac3f-206">**Conditions**</span></span>
        - <span data-ttu-id="4ac3f-207">コンテンツには、次の機密情報の種類が含まれる。 [適用されるすべて選択]</span><span class="sxs-lookup"><span data-stu-id="4ac3f-207">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        - <span data-ttu-id="4ac3f-208">Microsoft 365 から組織外のユーザーとコンテンツを共有する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-208">Content is shared from Microsoft 365 with people outside my organization</span></span>
        <br/><span data-ttu-id="4ac3f-209">![機密性の高いコンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-209">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span><br/>


    - <span data-ttu-id="4ac3f-210">**アクション**</span><span class="sxs-lookup"><span data-stu-id="4ac3f-210">**Actions**</span></span>
        - <span data-ttu-id="4ac3f-211">外部ユーザーのコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-211">Restrict access to the content for external users</span></span>
        - <span data-ttu-id="4ac3f-212">メールおよびポリシー ヒントでユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-212">Notify users with email and policy tips</span></span>
        - <span data-ttu-id="4ac3f-213">インシデント レポートを管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-213">Send incident reports to the Administrator</span></span>    
        <br/>![機密性の高いコンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)<br/>

<span data-ttu-id="4ac3f-215">機密情報を含む SharePoint でドキュメントを外部ゲストと共有しようとすると、DLP ポリシーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-215">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>
<br/><span data-ttu-id="4ac3f-216">![外部共有がブロックされている](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-216">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span><br/>


<span data-ttu-id="4ac3f-217">ゲストが Teams でドキュメントを開き、外部ブロックを使用すると、DLP ポリシーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ac3f-217">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>
<br/><span data-ttu-id="4ac3f-218">![外部アクセスがブロックされている](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="4ac3f-218">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span><br/>

## <a name="related-articles"></a><span data-ttu-id="4ac3f-219">関連記事</span><span class="sxs-lookup"><span data-stu-id="4ac3f-219">Related articles</span></span>

[<span data-ttu-id="4ac3f-220">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="4ac3f-220">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="4ac3f-221">メール通知を送信して、DLP ポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="4ac3f-221">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)