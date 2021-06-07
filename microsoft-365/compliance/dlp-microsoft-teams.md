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
description: Microsoft Teamsチャネルは、データ損失防止 (DLP) ポリシーをサポートします。
ms.openlocfilehash: 6467ae7fdfc9c8636bd306efde5cb89c100e5e6c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782563"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="f23d5-103">データ損失防止と Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f23d5-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="f23d5-104">組織にデータ損失防止 (DLP) がある場合は、ユーザーが機密情報をチャネルまたはチャット セッションで共有Microsoft Teamsポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="f23d5-105">この保護のしくみの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="f23d5-106">**例 1: メッセージ内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="f23d5-107">ユーザーがチャットまたはチャネル内の機密情報をゲスト (外部ユーザー) Teams共有しようとしたとします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="f23d5-108">これを防ぐために DLP ポリシーが定義されている場合は、外部ユーザーに送信される機密情報を含むメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="f23d5-109">これは、DLP ポリシーの構成方法に従って、自動的に数秒で行われます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f23d5-110">DLP for Microsoft Teamsは、次の権限を持つユーザーと共有Microsoft Teamsコンテンツをブロックします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="f23d5-111">- [チームとチャネル](/MicrosoftTeams/guest-access) でのゲスト アクセス。または</span><span class="sxs-lookup"><span data-stu-id="f23d5-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="f23d5-112">- [会議およびチャット](/MicrosoftTeams/manage-external-access) セッションでの外部アクセス。</span><span class="sxs-lookup"><span data-stu-id="f23d5-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="f23d5-113">外部チャット セッションの DLP は、送信者と受信者の両方が Teams モードでネイティブ フェデレーションMicrosoft Teams[使用している場合にのみ機能します](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="f23d5-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="f23d5-114">ユーザーの DLP Teams、またはネイティブ以外[](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)のフェデレーション チャット セッションとの相互運用Skype for Businessメッセージをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="f23d5-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="f23d5-115">**例 2: ドキュメント内の機密情報を保護します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="f23d5-116">ユーザーがチャネルまたはチャットのゲストとドキュメントを共有しようとMicrosoft Teams機密情報が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="f23d5-117">これを防ぐために DLP ポリシーが定義されている場合、ドキュメントはそれらのユーザーに対して開かれません。</span><span class="sxs-lookup"><span data-stu-id="f23d5-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="f23d5-118">保護を適用するには、DLP ポリシーに SharePoint と OneDrive を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23d5-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="f23d5-119">これは、Microsoft Teams に表示される SharePoint の DLP の例であり、Office 365 DLP (Office 365 E3 に含まれる) のライセンスをユーザーに与える必要がありますが、Office 365 Advanced Compliance のライセンスを取得する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="f23d5-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="f23d5-120">DLP ライセンス Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f23d5-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="f23d5-121">[データ損失防止機能](dlp-learn-about-dlp.md)は、次のようなプライベート チャネル メッセージMicrosoft Teams含む、チャットメッセージやチャネル メッセージを含 **む機能が拡張** されました。</span><span class="sxs-lookup"><span data-stu-id="f23d5-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="f23d5-122">Office 365E5/A5</span><span class="sxs-lookup"><span data-stu-id="f23d5-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="f23d5-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="f23d5-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="f23d5-124">Microsoft 365 の情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="f23d5-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="f23d5-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="f23d5-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="f23d5-126">Office 365およびMicrosoft 365 E3には、オンライン、SharePoint、およびOneDriveの DLP 保護Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f23d5-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="f23d5-127">また、このファイルには、Teamsを共有TeamsオンラインとSharePointをOneDriveするファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="f23d5-128">チャットでの DLP 保護のサポートTeams E5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="f23d5-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="f23d5-129">ライセンス要件の詳細については、「[Microsoft 365 テナントレベル サービスのライセンスに関するガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23d5-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f23d5-130">DLP は、チャットスレッドまたはチャネル スレッドの実際のメッセージにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="f23d5-131">アクティビティ通知 (短いメッセージ プレビューを含み、ユーザーの通知設定に基づいて表示される)は、DLP にTeamsされません。</span><span class="sxs-lookup"><span data-stu-id="f23d5-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="f23d5-132">メッセージの一部に表示される機密情報は、DLP ポリシーが適用され、メッセージ自体の機密情報が削除された後でも、通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="f23d5-133">DLP 保護の範囲</span><span class="sxs-lookup"><span data-stu-id="f23d5-133">Scope of DLP protection</span></span>

<span data-ttu-id="f23d5-134">DLP 保護は、エンティティに対してTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="f23d5-135">ユーザー アカウント/グループ/リスト</span><span class="sxs-lookup"><span data-stu-id="f23d5-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="f23d5-136">Teamsエンティティ</span><span class="sxs-lookup"><span data-stu-id="f23d5-136">Teams Entity</span></span> |<span data-ttu-id="f23d5-137">利用可能な DLP 保護</span><span class="sxs-lookup"><span data-stu-id="f23d5-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f23d5-138">個々のユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="f23d5-138">individual user accounts</span></span>     |<span data-ttu-id="f23d5-139">1:1/n チャット</span><span class="sxs-lookup"><span data-stu-id="f23d5-139">1:1/n chats</span></span>         |<span data-ttu-id="f23d5-140">はい</span><span class="sxs-lookup"><span data-stu-id="f23d5-140">yes</span></span>         |
|     |<span data-ttu-id="f23d5-141">一般的なチャット</span><span class="sxs-lookup"><span data-stu-id="f23d5-141">general chats</span></span>         |<span data-ttu-id="f23d5-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="f23d5-142">no</span></span>         |
|     |<span data-ttu-id="f23d5-143">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="f23d5-143">private channels</span></span>         |<span data-ttu-id="f23d5-144">はい</span><span class="sxs-lookup"><span data-stu-id="f23d5-144">yes</span></span>         |
|<span data-ttu-id="f23d5-145">セキュリティ グループ/配布リスト</span><span class="sxs-lookup"><span data-stu-id="f23d5-145">security groups/distribution lists</span></span>  | <span data-ttu-id="f23d5-146">1:1/n チャット</span><span class="sxs-lookup"><span data-stu-id="f23d5-146">1:1/n chats</span></span>         |<span data-ttu-id="f23d5-147">はい</span><span class="sxs-lookup"><span data-stu-id="f23d5-147">yes</span></span>         |
|     |<span data-ttu-id="f23d5-148">一般的なチャット</span><span class="sxs-lookup"><span data-stu-id="f23d5-148">general chats</span></span>         |<span data-ttu-id="f23d5-149">いいえ</span><span class="sxs-lookup"><span data-stu-id="f23d5-149">no</span></span>         |
|     |<span data-ttu-id="f23d5-150">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="f23d5-150">private channels</span></span>         |<span data-ttu-id="f23d5-151">はい</span><span class="sxs-lookup"><span data-stu-id="f23d5-151">yes</span></span>        |
|<span data-ttu-id="f23d5-152">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="f23d5-152">Microsoft 365 group</span></span>    |<span data-ttu-id="f23d5-153">1:1/n チャット</span><span class="sxs-lookup"><span data-stu-id="f23d5-153">1:1/n chats</span></span>          |<span data-ttu-id="f23d5-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="f23d5-154">no</span></span>         |
|     |<span data-ttu-id="f23d5-155">一般的なチャット</span><span class="sxs-lookup"><span data-stu-id="f23d5-155">general chats</span></span>          |<span data-ttu-id="f23d5-156">はい</span><span class="sxs-lookup"><span data-stu-id="f23d5-156">yes</span></span>        |
|     |<span data-ttu-id="f23d5-157">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="f23d5-157">private channels</span></span>|<span data-ttu-id="f23d5-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="f23d5-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="f23d5-159">ポリシー ヒントは、ユーザーの教育に役立ちます</span><span class="sxs-lookup"><span data-stu-id="f23d5-159">Policy tips help educate users</span></span>

<span data-ttu-id="f23d5-160">web 上の[Exchange、Outlook、Outlook、SharePoint](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)サイト、および[Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)デスクトップ クライアントでの DLP の動作と同様に、アクションが DLP ポリシーでトリガーされるとポリシー ヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="f23d5-161">ポリシー ヒントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-161">Here's an example of a policy tip:</span></span>

![[ブロックされたメッセージの通知] Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="f23d5-163">ここでは、送信者がソーシャル セキュリティ番号を別のチャネルで共有Microsoft Teamsしました。</span><span class="sxs-lookup"><span data-stu-id="f23d5-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="f23d5-164">[ **実行できる操作] リンクは** 、送信者が問題を解決するためのオプションを提供するダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="f23d5-165">送信者はポリシーを上書きするか、管理者に確認と解決を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![ブロックされたメッセージを解決するためのオプション](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="f23d5-167">組織では、ユーザーに DLP ポリシーの上書きを許可できます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="f23d5-168">DLP ポリシーを構成する場合は、既定のポリシー ヒントを使用するか、組織の [ポリシー ヒント](#to-customize-policy-tips) をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="f23d5-169">この例に戻り、送信者がユーザー チャネルで社会保障番号を共有Teams、受信者が見た情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f23d5-170">![ブロックされたメッセージ](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="f23d5-171">ポリシーのヒントをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f23d5-171">To customize policy tips</span></span>

<span data-ttu-id="f23d5-172">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23d5-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="f23d5-173">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23d5-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="f23d5-174">コンプライアンス センター ( ) に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="f23d5-175">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="f23d5-176">ポリシーを選択し、[ポリシー設定] の **横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="f23d5-177">新しいルールを作成するか、ポリシーの既存のルールを編集します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-178">![ポリシーのルールの編集](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="f23d5-179">[ユーザー通知 **] タブで** 、[メール テキストの **カスタマイズ** ] または [ポリシー ヒントのテキスト **オプションのカスタマイズ] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-180">![ユーザー通知とポリシーヒントをカスタマイズする](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="f23d5-181">電子メール通知やポリシー ヒントに使用するテキストを指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="f23d5-182">[ポリシー設定 **] タブで** 、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="f23d5-183">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="f23d5-184">Microsoft Teams を場所として既存の DLP ポリシーに追加する</span><span class="sxs-lookup"><span data-stu-id="f23d5-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="f23d5-185">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23d5-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="f23d5-186">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23d5-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="f23d5-187">コンプライアンス センター ( ) に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="f23d5-188">[**データ損失防止ポリシー] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="f23d5-189">ポリシーを選択し、[場所] の下の値 **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="f23d5-190">チャットメッセージと **Teamsメッセージが表示される** 場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="f23d5-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="f23d5-191">編集しない場合は、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-192">![既存のポリシーの場所](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="f23d5-193">[状態 **] 列** で、チャットメッセージとチャネル メッセージのTeams **をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-194">![チャットとチャネルTeams DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="f23d5-195">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="f23d5-196">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-196">You can specify:</span></span>

    1. <span data-ttu-id="f23d5-197">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="f23d5-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="f23d5-198">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="f23d5-199">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="f23d5-200">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-200">Click **Save**.</span></span>

<span data-ttu-id="f23d5-201">変更がデータ センターを通じて動作し、ユーザー アカウントに同期するために約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="f23d5-202">Microsoft Teams の新しい DLP ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="f23d5-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="f23d5-203">このタスクを実行するには、DLP ポリシーを編集する権限を持つロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23d5-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="f23d5-204">詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23d5-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="f23d5-205">コンプライアンス センター ( ) に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="f23d5-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="f23d5-206">[**データ損失防止ポリシー] +**  >    >  **[ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="f23d5-207">テンプレートを選択 [し、[](data-loss-prevention-policies.md#dlp-policy-templates)次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="f23d5-208">この例では、米国の個人を特定できる情報データ テンプレートを選択しました。</span><span class="sxs-lookup"><span data-stu-id="f23d5-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-209">![DLP ポリシーのプライバシー テンプレート](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="f23d5-210">[ポリシー **に名前を付け** ] タブで、ポリシーの名前と説明を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="f23d5-211">[場所 **の選択] タブ** で、すべてのアカウントの既定の設定を維持するか、[特定の場所を選択する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="f23d5-212">次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-212">You can specify:</span></span>

    1. <span data-ttu-id="f23d5-213">最大 1000 個の個別アカウントを含めるか除外する</span><span class="sxs-lookup"><span data-stu-id="f23d5-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="f23d5-214">配布リストとセキュリティ グループを含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="f23d5-215">**これはパブリック プレビュー機能です。**</span><span class="sxs-lookup"><span data-stu-id="f23d5-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP ポリシーの場所](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="f23d5-217">機密情報を含むドキュメントが Teams で不適切に共有されない場合は **、SharePoint** サイトと **OneDrive** アカウントが Teams チャットメッセージとチャネル メッセージと共にオン **になっていることを** 確認します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="f23d5-218">[ポリシー設定 **] タブ** の[保護するコンテンツの種類をカスタマイズする] で、既定の単純な設定を保持するか、[詳細設定を使用する] を選択して、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="f23d5-219">詳細設定を選択した場合は、ポリシーのルールを作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="f23d5-220">このヘルプについては、「簡易設定と [詳細設定」を参照してください](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。</span><span class="sxs-lookup"><span data-stu-id="f23d5-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="f23d5-221">[ポリシー **設定] タブ** の **[機密情報** が検出された場合の操作] で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="f23d5-222">ここでは、既定のポリシー ヒントと電子メール[](use-notifications-and-policy-tips.md)通知を保持するか、カスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-223">![ヒントと通知を含む DLP ポリシー設定](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="f23d5-224">設定の確認または編集が完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="f23d5-225">[ポリシーの **設定**] タブの [ポリシーを有効にするか、最初にテストするのかを選択しますか **?]** で、ポリシーを有効 [](dlp-overview-plan-for-dlp.md#policy-deployment)にするか、最初にテストするか、今のところオフにしておき、[次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f23d5-226">![ポリシーを有効にするかどうかを指定する](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="f23d5-227">[設定 **の確認] タブ** で、新しいポリシーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="f23d5-228">[編集 **] を** 選択して変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="f23d5-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="f23d5-229">完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f23d5-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="f23d5-230">新しいポリシーがデータセンター経由で動作し、ユーザー アカウントと同期するには、約 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="f23d5-231">機密文書への外部アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="f23d5-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="f23d5-232">機密情報をSharePoint含むドキュメントに、既定で SharePoint または Teams から外部ゲストがアクセスできないことを確認するには、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="f23d5-233">新しいファイルを既定で機密性の高いファイルとしてマークすることで、DLP スキャンが行い、共有が安全とマークされるまで、ドキュメントが [確実に保護されます](/sharepoint/sensitive-by-default)。</span><span class="sxs-lookup"><span data-stu-id="f23d5-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="f23d5-234">推奨される DLP ポリシー構造</span><span class="sxs-lookup"><span data-stu-id="f23d5-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="f23d5-235">**条件**</span><span class="sxs-lookup"><span data-stu-id="f23d5-235">**Conditions**</span></span>
        - <span data-ttu-id="f23d5-236">コンテンツには、次の機密情報の種類が含まれる。 [適用するすべて選択]</span><span class="sxs-lookup"><span data-stu-id="f23d5-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="f23d5-237">組織外のユーザー Microsoft 365からコンテンツを共有する</span><span class="sxs-lookup"><span data-stu-id="f23d5-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="f23d5-238">![機密性の高いコンテンツの外部共有を検出する DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="f23d5-239">**Actions**</span><span class="sxs-lookup"><span data-stu-id="f23d5-239">**Actions**</span></span>
        - <span data-ttu-id="f23d5-240">外部ユーザーのコンテンツへのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="f23d5-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="f23d5-241">メールおよびポリシー ヒントでユーザーに通知する</span><span class="sxs-lookup"><span data-stu-id="f23d5-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="f23d5-242">インシデント レポートを管理者に送信する</span><span class="sxs-lookup"><span data-stu-id="f23d5-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="f23d5-243">![機密性の高いコンテンツの外部共有をブロックする DLP アクション](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="f23d5-244">機密情報を含むドキュメントを外部ゲストと共有SharePoint DLP ポリシーが動作します。</span><span class="sxs-lookup"><span data-stu-id="f23d5-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f23d5-245">![外部共有がブロックされている](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="f23d5-246">ゲストが外部ブロックを使用してドキュメントを開Teams DLP ポリシーが有効です。</span><span class="sxs-lookup"><span data-stu-id="f23d5-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f23d5-247">![外部アクセスがブロックされている](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="f23d5-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="f23d5-248">関連資料</span><span class="sxs-lookup"><span data-stu-id="f23d5-248">Related articles</span></span>

- [<span data-ttu-id="f23d5-249">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="f23d5-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="f23d5-250">メール通知を送信して、DLP ポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="f23d5-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
