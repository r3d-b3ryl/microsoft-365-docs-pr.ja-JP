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
description: これで、Microsoft Teams のチャットとチャネルに DLP ポリシーを適用できます。 動作の詳細については、この記事を参照してください。
ms.openlocfilehash: 3d55c447b2e808af2ac35f04b67a002304e3e9eb
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709539"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="013f4-104">データ損失防止と Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="013f4-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="013f4-105">データ損失防止機能は、Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 Information Protection and Governance、または Office 365 Advanced Compliance のライセンスを持つユーザー向け Microsoft Teams チャットおよびチャネル メッセージに追加されました。</span><span class="sxs-lookup"><span data-stu-id="013f4-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="013f4-106">Office 365 および Microsoft 365 E3 には、SharePoint Online、OneDrive、Exchange Online の DLP 保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="013f4-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="013f4-107">これには、Teams が SharePoint Online と OneDrive を使用してファイルを共有するために Teams を通じて共有されるファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="013f4-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="013f4-108">Teams チャットでの DLP 保護のサポートには E5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="013f4-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="013f4-109">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="013f4-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="013f4-110">Teams の DLP は、ユーザーが Exchange Online にあるメールボックスを持っている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="013f4-110">DLP for Teams is only supported when the user has a mailbox that is in Exchange Online</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="013f4-111">Microsoft Teams の DLP の概要</span><span class="sxs-lookup"><span data-stu-id="013f4-111">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="013f4-112">最近では [、データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、プライベート チャネル メッセージを含む Microsoft Teams チャットとチャネル **メッセージが含まれます**。</span><span class="sxs-lookup"><span data-stu-id="013f4-112">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span>


<span data-ttu-id="013f4-113">組織に DLP がある場合は、Microsoft Teams チャネルまたはチャット セッションでユーザーが機密情報を共有するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="013f4-113">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="013f4-114">この保護のしくみの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="013f4-114">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="013f4-115">**例 1: メッセージ内の機密情報を保護する**。</span><span class="sxs-lookup"><span data-stu-id="013f4-115">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="013f4-116">Teams のチャットまたはチャネル内の機密情報をゲスト (外部ユーザー) と共有しようとしたとします。</span><span class="sxs-lookup"><span data-stu-id="013f4-116">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="013f4-117">これを防止するために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="013f4-117">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="013f4-118">これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。</span><span class="sxs-lookup"><span data-stu-id="013f4-118">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="013f4-119">Microsoft Teams の DLP は、次の条件を持つ Microsoft Teams ユーザーと共有すると、機密コンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="013f4-119">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="013f4-120">- [チームとチャネル](https://docs.microsoft.com/MicrosoftTeams/guest-access) でのゲスト アクセスまたは</span><span class="sxs-lookup"><span data-stu-id="013f4-120">- [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="013f4-121">- [会議およびチャット](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。</span><span class="sxs-lookup"><span data-stu-id="013f4-121">- [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="013f4-122">外部チャット セッションの DLP は、送信者と受信者の両方が Teams Only モードで [、Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)ネイティブ フェデレーションを使用している場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="013f4-122">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="013f4-123">Teams の DLP は、Skype for Business またはネイティブ以外のフェデレーション チャット セッションとの相互運用のメッセージをブロックしません。 [](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)</span><span class="sxs-lookup"><span data-stu-id="013f4-123">DLP for Teams does not block messages in [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="013f4-124">**例 2: ドキュメント内の機密情報を保護する**。</span><span class="sxs-lookup"><span data-stu-id="013f4-124">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="013f4-125">Microsoft Teams チャネルまたはチャットで、誰かがゲストとドキュメントを共有しようとして、ドキュメントに機密情報が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="013f4-125">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="013f4-126">これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。</span><span class="sxs-lookup"><span data-stu-id="013f4-126">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="013f4-127">この場合、保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f4-127">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="013f4-128">(これは、Microsoft Teams に表示される SharePoint 用 DLP の例であり、そのため、ユーザーには Office 365 DLP (Office 365 E3 に含まれる) のライセンスが必要ですが、ユーザーに Office 365 Advanced Compliance のライセンスを与える必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="013f4-128">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="013f4-129">ポリシー ヒントは、ユーザーの教育に役立ちます</span><span class="sxs-lookup"><span data-stu-id="013f4-129">Policy tips help educate users</span></span>

<span data-ttu-id="013f4-130">[Exchange、Outlook、Web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)上の Outlook、SharePoint [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、および[Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーと競合するとポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="013f4-130">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="013f4-131">ポリシー ヒントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="013f4-131">Here's an example of a policy tip:</span></span>

![Teams でのブロックされたメッセージ通知](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="013f4-133">この場合、送信者は Microsoft Teams チャネルで社会保障番号を共有しようとした。</span><span class="sxs-lookup"><span data-stu-id="013f4-133">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="013f4-134">[ **操作方法] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="013f4-134">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="013f4-135">この場合、送信者はポリシーを上書きするか、ポリシーを確認して解決することを管理者に通知できます。</span><span class="sxs-lookup"><span data-stu-id="013f4-135">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![ブロックされたメッセージを解決するオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="013f4-137">組織では、ユーザーに DLP ポリシーの上書きを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="013f4-137">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="013f4-138">また、DLP ポリシーを構成するときに、既定のポリシー ヒントを使用するか、組織の [ポリシー](#to-customize-policy-tips) ヒントをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="013f4-138">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="013f4-139">この例に戻り、送信者が Teams チャネルで社会保障番号を共有しました。受信者が確認した情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="013f4-139">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="013f4-141">**[What's this?** ][](data-loss-prevention-policies.md)リンクは DLP ポリシーに関する記事を開きます。これは、メッセージがブロックされた理由を説明するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="013f4-141">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="013f4-142">ポリシー ヒントをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="013f4-142">To customize policy tips</span></span>

<span data-ttu-id="013f4-143">このタスクを実行するには、DLP ポリシーを編集するアクセス許可を持つ役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f4-143">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="013f4-144">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="013f4-144">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="013f4-145">セキュリティ & コンプライアンス センター ( ) に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="013f4-145">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="013f4-146">データ **損失防止ポリシーを選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-146">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="013f4-147">ポリシーを選択し、[ポリシー設定] **の横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-147">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="013f4-148">新しいルールを作成するか、ポリシーの既存のルールを編集します。</span><span class="sxs-lookup"><span data-stu-id="013f4-148">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![ポリシーのルールの編集](../media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="013f4-150">[ユーザー通知 **] タブで** 、[メール **テキストの** カスタマイズ] または [ポリシー ヒント テキスト オプションのカスタマイズ] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="013f4-150">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="013f4-151">![ユーザー通知とポリシー ヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-151">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="013f4-152">電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-152">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="013f4-153">[ポリシー設定 **] タブで、[** 保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-153">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="013f4-154">変更がデータ センターを経由してユーザー アカウントに同期されるのに約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="013f4-154">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="013f4-155">既存の DLP ポリシーに場所として Microsoft Teams を追加する</span><span class="sxs-lookup"><span data-stu-id="013f4-155">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="013f4-156">このタスクを実行するには、DLP ポリシーを編集するアクセス許可を持つ役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f4-156">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="013f4-157">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="013f4-157">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="013f4-158">セキュリティ & コンプライアンス センター ( ) に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="013f4-158">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="013f4-159">データ **損失防止ポリシーを選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-159">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="013f4-160">ポリシーを選択し、[場所] の下の値 **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-160">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="013f4-161">Teams のチャット **メッセージとチャネル メッセージが表示** される場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="013f4-161">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="013f4-162">If you don't, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="013f4-162">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="013f4-163">![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-163">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="013f4-164">[状態 **] 列** で、Teams チャットおよびチャネル メッセージの **ポリシーを有効にします**。</span><span class="sxs-lookup"><span data-stu-id="013f4-164">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="013f4-165">![Teams のチャットとチャネルの DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-165">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="013f4-166">すべてのアカウントの既定の設定を維持するか、含めるか除外するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="013f4-166">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="013f4-167">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="013f4-167">Click **Save**.</span></span>

<span data-ttu-id="013f4-168">変更がデータ センターを経由してユーザー アカウントに同期されるのに約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="013f4-168">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="013f4-169">Microsoft Teams の新しい DLP ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="013f4-169">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="013f4-170">このタスクを実行するには、DLP ポリシーを編集するアクセス許可を持つ役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f4-170">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="013f4-171">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="013f4-171">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="013f4-172">セキュリティ & コンプライアンス センター ( ) に移動し [https://protection.office.com](https://protection.office.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="013f4-172">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="013f4-173">データ **損失防止ポリシーを**  >  **選択**  >  **し、ポリシーを作成します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-173">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="013f4-174">テンプレートを選択 [し](data-loss-prevention-policies.md#dlp-policy-templates)、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-174">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="013f4-175">この例では、米国の個人を特定できる情報データ テンプレートを選択しました。</span><span class="sxs-lookup"><span data-stu-id="013f4-175">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="013f4-176">![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-176">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="013f4-177">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span><span class="sxs-lookup"><span data-stu-id="013f4-177">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="013f4-178">[場所 **の選択**] タブで、すべての場所の既定の設定を維持するか、[特定の場所を選択する] を選択して 、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-178">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="013f4-179">特定の場所を選択した場合は、DLP ポリシーで場所を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-179">If you chose specific locations, select them for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="013f4-180">![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-180">![DLP policy locations](../media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="013f4-181">機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams のチャットおよびチャネル メッセージと共にオンになっていることを確認 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-181">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

<br/>

6. <span data-ttu-id="013f4-182">[ポリシー **設定]** タブの[保護するコンテンツの種類のカスタマイズ] で、既定の簡単な設定を維持するか、[詳細設定を使用] を選択して 、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-182">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="013f4-183">詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="013f4-183">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="013f4-184">(このヘルプについては、「簡単な設定と詳細設定 [」を参照してください](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings))。</span><span class="sxs-lookup"><span data-stu-id="013f4-184">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="013f4-185">[ポリシー **設定] タブ** の[機密情報が検出された場合の操作] で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="013f4-185">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="013f4-186">(ここでは、既定のポリシー ヒントと電子メール[](use-notifications-and-policy-tips.md)通知を保持するか、カスタマイズすることができます)。</span><span class="sxs-lookup"><span data-stu-id="013f4-186">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="013f4-187">![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-187">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="013f4-188">設定の確認または編集が完了したら、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-188">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="013f4-189">On the **Policy settings** tab, under Do you want on the policy or test things **out first?** choose whether to turn the policy on, [test it first,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)or keep it turned off for now, and then choose **Next**.</span><span class="sxs-lookup"><span data-stu-id="013f4-189">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="013f4-190">![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-190">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="013f4-191">[設定 **の確認] タブで** 、新しいポリシーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="013f4-191">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="013f4-192">[編集 **] を選択** して変更します。</span><span class="sxs-lookup"><span data-stu-id="013f4-192">Choose **Edit** to make changes.</span></span> <span data-ttu-id="013f4-193">完了したら、[作成] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="013f4-193">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="013f4-194">新しいポリシーがデータ センターを経由して動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="013f4-194">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="013f4-195">機密ドキュメントへの外部アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="013f4-195">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="013f4-196">機密情報を含む SharePoint ドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="013f4-196">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="013f4-197">DLP スキャンまでドキュメントを保護し、新しいファイルを既定で機密としてマークすることで、ドキュメントを共有しても安全だと [マークできます。](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="013f4-197">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span></span>
- <span data-ttu-id="013f4-198">推奨される DLP ポリシー構造</span><span class="sxs-lookup"><span data-stu-id="013f4-198">Recommended DLP policy structure</span></span>
    - <span data-ttu-id="013f4-199">**条件**</span><span class="sxs-lookup"><span data-stu-id="013f4-199">**Conditions**</span></span>
        - <span data-ttu-id="013f4-200">コンテンツには、次の機密情報の種類が含まれる: [適用されるすべて選択]</span><span class="sxs-lookup"><span data-stu-id="013f4-200">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        - <span data-ttu-id="013f4-201">Microsoft 365 から組織外のユーザーとコンテンツを共有する</span><span class="sxs-lookup"><span data-stu-id="013f4-201">Content is shared from Microsoft 365 with people outside my organization</span></span>
        <br/><span data-ttu-id="013f4-202">![機密コンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-202">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span><br/>


    - <span data-ttu-id="013f4-203">**アクション**</span><span class="sxs-lookup"><span data-stu-id="013f4-203">**Actions**</span></span>
        - <span data-ttu-id="013f4-204">外部ユーザーのコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="013f4-204">Restrict access to the content for external users</span></span>
        - <span data-ttu-id="013f4-205">電子メールとポリシー ヒントを使用してユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="013f4-205">Notify users with email and policy tips</span></span>
        - <span data-ttu-id="013f4-206">インシデント レポートを管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="013f4-206">Send incident reports to the Administrator</span></span>    
        <br/>![機密コンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)<br/>

<span data-ttu-id="013f4-208">機密情報を含む SharePoint のドキュメントを外部ゲストと共有しようとするときに動作している DLP ポリシー:</span><span class="sxs-lookup"><span data-stu-id="013f4-208">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>
<br/><span data-ttu-id="013f4-209">![外部共有のブロック](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-209">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span><br/>


<span data-ttu-id="013f4-210">ゲストが外部ブロックを使用して Teams でドキュメントを開く際に有効な DLP ポリシー:</span><span class="sxs-lookup"><span data-stu-id="013f4-210">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>
<br/><span data-ttu-id="013f4-211">![外部アクセスのブロック](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="013f4-211">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span><br/>

## <a name="related-articles"></a><span data-ttu-id="013f4-212">関連記事</span><span class="sxs-lookup"><span data-stu-id="013f4-212">Related articles</span></span>

[<span data-ttu-id="013f4-213">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="013f4-213">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="013f4-214">メール通知を送信して、DLP ポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="013f4-214">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
