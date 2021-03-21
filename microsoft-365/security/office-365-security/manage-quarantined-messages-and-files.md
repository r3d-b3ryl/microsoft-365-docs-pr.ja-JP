---
title: 管理者として検疫済みメッセージとファイルを管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のすべてのユーザーの検疫済みメッセージを表示および管理する方法について学習できます。 Microsoft Defender for Office 365 の組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams で検疫済みファイルを管理することもできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fef752e8a02f7ed0dd4ed51854810a0d36d718b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926798"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="c47bb-104">EOP の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="c47bb-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c47bb-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c47bb-105">**Applies to**</span></span>
- [<span data-ttu-id="c47bb-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c47bb-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c47bb-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c47bb-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c47bb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c47bb-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c47bb-109">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="c47bb-110">詳細については [、「EOP の検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="c47bb-111">管理者は、すべてのユーザーの検疫済みメッセージのすべての種類を表示、解放、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="c47bb-112">マルウェア、高信頼フィッシング、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを管理できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="c47bb-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c47bb-113">管理者は、誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="c47bb-114">Microsoft Defender for Office 365 の組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams で検疫済みファイルを表示、ダウンロード、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="c47bb-115">検疫済みメッセージは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c47bb-116">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c47bb-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c47bb-117">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="c47bb-118">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="c47bb-119">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c47bb-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c47bb-120">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c47bb-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c47bb-121">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c47bb-122">すべてのユーザーの検疫済みメッセージに対してアクションを実行するには、組織の管理、セキュリティ管理者、または検疫管理者の役割グループのメンバー **である** <sup>\*</sup> 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="c47bb-123">すべてのユーザーの検疫済みメッセージへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c47bb-124">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c47bb-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="c47bb-125">**注**:</span><span class="sxs-lookup"><span data-stu-id="c47bb-125">**Notes**:</span></span>

  - <span data-ttu-id="c47bb-126">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c47bb-127">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c47bb-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="c47bb-128">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="c47bb-129"><sup>\*</sup>また、Exchange  Online PowerShell で検疫手順を実行するには、検疫管理者役割グループのメンバーが[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の衛生管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="c47bb-130">検疫済みメッセージは、自動的に削除される前に既定の期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="c47bb-131">スパム対策ポリシー (スパム、フィッシング、バルク メール) によって検疫されたメッセージの 30 日間。</span><span class="sxs-lookup"><span data-stu-id="c47bb-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="c47bb-132">これは既定値と最大値です。</span><span class="sxs-lookup"><span data-stu-id="c47bb-132">This is the default and maximum value.</span></span> <span data-ttu-id="c47bb-133">この値を (低く) 構成するには、「スパム対策ポリシーを構成 [する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="c47bb-134">マルウェアを含むメッセージの場合は 15 日間。</span><span class="sxs-lookup"><span data-stu-id="c47bb-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="c47bb-135">SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルによって検疫されたファイルが 365 の場合、Defender で 15 日間Officeされます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="c47bb-136">検疫からメッセージの有効期限が切れると、メッセージを回復できません。</span><span class="sxs-lookup"><span data-stu-id="c47bb-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="c47bb-137">セキュリティ コンプライアンス センターを&して、検疫済み電子メール メッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="c47bb-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="c47bb-138">検疫済みメールの表示</span><span class="sxs-lookup"><span data-stu-id="c47bb-138">View quarantined email</span></span>

1. <span data-ttu-id="c47bb-139">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="c47bb-140">[**検疫済みを表示**] が既定値の [**メール**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="c47bb-141">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="c47bb-142">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="c47bb-143">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="c47bb-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="c47bb-144">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-145">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-146">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-147">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-148">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-149">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="c47bb-150">**Expires**</span></span>
   - <span data-ttu-id="c47bb-151">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-151">**Recipient**</span></span>
   - <span data-ttu-id="c47bb-152">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-152">**Message ID**</span></span>
   - <span data-ttu-id="c47bb-153">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-153">**Policy name**</span></span>
   - <span data-ttu-id="c47bb-154">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-154">**Size**</span></span>
   - <span data-ttu-id="c47bb-155">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-155">**Direction**</span></span>

   <span data-ttu-id="c47bb-156">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="c47bb-157">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="c47bb-158">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c47bb-158">The available filters are:</span></span>

   - <span data-ttu-id="c47bb-159">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="c47bb-160">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-160">**Today**</span></span>
     - <span data-ttu-id="c47bb-161">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-161">**Next 2 days**</span></span>
     - <span data-ttu-id="c47bb-162">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-162">**Next 7 days**</span></span>
     - <span data-ttu-id="c47bb-163">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="c47bb-164">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="c47bb-165">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="c47bb-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="c47bb-166">**ポリシー**: メッセージは、メール フロー ルール (トランスポート ルールとも呼ばれる) の条件と一致しました。</span><span class="sxs-lookup"><span data-stu-id="c47bb-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="c47bb-167">**[バルク]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-167">**Bulk**</span></span>
     - <span data-ttu-id="c47bb-168">**フィッシング**: スパム フィルターの評決は、フィッシングメールまたはフィッシング対策保護がメッセージ [(ス](set-up-anti-phishing-policies.md#spoof-settings)プーフィング設定または偽装保護) を [検疫しました](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="c47bb-169">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="c47bb-169">**Malware**</span></span>
     - <span data-ttu-id="c47bb-170">**スパム**</span><span class="sxs-lookup"><span data-stu-id="c47bb-170">**Spam**</span></span>
     - <span data-ttu-id="c47bb-171">**高信頼フィッシング**</span><span class="sxs-lookup"><span data-stu-id="c47bb-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="c47bb-172">**ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="c47bb-173">**マルウェア対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="c47bb-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="c47bb-174">**安全な添付ファイル ポリシー**</span><span class="sxs-lookup"><span data-stu-id="c47bb-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="c47bb-175">**フィッシング対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="c47bb-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="c47bb-176">**ホストされているコンテンツ フィルター ポリシー** (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="c47bb-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="c47bb-177">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="c47bb-177">**Transport rule**</span></span>

   - <span data-ttu-id="c47bb-178">**電子メール受信者**: すべてのユーザーまたは送信されたメッセージのみ。</span><span class="sxs-lookup"><span data-stu-id="c47bb-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="c47bb-179">エンド ユーザーは、送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="c47bb-180">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="c47bb-181">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="c47bb-182">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="c47bb-183">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c47bb-183">Wildcards aren't supported.</span></span> <span data-ttu-id="c47bb-184">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-184">You can search by the following values:</span></span>

   - <span data-ttu-id="c47bb-185">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="c47bb-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="c47bb-186">たとえば、メッセージ [トレースを](message-trace-scc.md) 使用して、組織内のユーザーに送信されたメッセージを探し、メッセージが配信される代わりに検疫されたと判断しました。</span><span class="sxs-lookup"><span data-stu-id="c47bb-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="c47bb-187">メッセージ ID の完全な値 (角かっこ ( ) を含む場合があります) を必ず含める \<\> 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="c47bb-188">例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="c47bb-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="c47bb-189">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c47bb-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="c47bb-190">**ポリシー名**: メッセージのポリシー名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="c47bb-191">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="c47bb-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="c47bb-192">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="c47bb-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="c47bb-193">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="c47bb-194">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="c47bb-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="c47bb-195">**ポリシー名**: メッセージのクォーティ化を担当したポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="c47bb-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="c47bb-196">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="c47bb-197">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="c47bb-198">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="c47bb-198">View quarantined message details</span></span>

<span data-ttu-id="c47bb-199">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c47bb-200">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="c47bb-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="c47bb-201">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-201">**Sender address**</span></span>

- <span data-ttu-id="c47bb-202">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="c47bb-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="c47bb-203">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-203">**Subject**</span></span>

- <span data-ttu-id="c47bb-204">**検疫の理由**: メッセージがスパム、バルク、フィッシング、メールフロー ルール **(トランスポート** ルール) と一致したと識別された場合、またはマルウェアが含まれていると識別された場合に表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="c47bb-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="c47bb-205">**受信者数**</span><span class="sxs-lookup"><span data-stu-id="c47bb-205">**Recipient count**</span></span>

- <span data-ttu-id="c47bb-206">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="c47bb-207">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="c47bb-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="c47bb-208">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="c47bb-209">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="c47bb-210">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="c47bb-210">Take action on quarantined email</span></span>

<span data-ttu-id="c47bb-211">メッセージを選択した後、[詳細] フライアウト ウィンドウでメッセージを処理するためのいくつかの **オプションがあります** 。</span><span class="sxs-lookup"><span data-stu-id="c47bb-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c47bb-212">**リリース メッセージ**: 表示されるフライアウト ウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="c47bb-213">**分析のために Microsoft にメッセージを** 報告する : これは既定で選択され、誤って検疫されたメッセージを誤検知として Microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="c47bb-214">メッセージがスパム、バルク、フィッシング、またはマルウェアを含むとして検疫された場合、メッセージは Microsoft スパム分析チームにも報告されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="c47bb-215">分析によっては、サービス全体のスパム フィルター ルールが調整され、メッセージの通過が許可される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c47bb-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="c47bb-216">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="c47bb-217">**すべての受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="c47bb-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="c47bb-218">**特定の受信者にメッセージをリリースする**</span><span class="sxs-lookup"><span data-stu-id="c47bb-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="c47bb-219">**他のユーザーへのメッセージの** 解放 : 元の受信者以外のユーザーにマルウェア メッセージを解放する機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c47bb-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="c47bb-220">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="c47bb-221">メッセージのリリースに関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="c47bb-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="c47bb-222">同じ受信者に対してメッセージを 2 回以上リリースできない。</span><span class="sxs-lookup"><span data-stu-id="c47bb-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="c47bb-223">メッセージを受信していない受信者だけが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="c47bb-224">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="c47bb-225">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="c47bb-226">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="c47bb-227">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="c47bb-228">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="c47bb-229">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="c47bb-230">**検疫から削除**: 表示される警告 **で [は** い] をクリックすると、メッセージは元の受信者に送信されることなくすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="c47bb-231">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="c47bb-232">**送信メッセージ**: 表示されるフライアウト ウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="c47bb-233">**オブジェクトの種類**:**メール**(既定 **)、URL、** または **添付ファイル 。**</span><span class="sxs-lookup"><span data-stu-id="c47bb-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="c47bb-234">**送信形式**: **ネットワーク メッセージ ID** (既定では、[ネットワーク メッセージ **ID]** ボックスに対応する値を指定) **または** [ファイル] (ローカルの .eml ファイルまたは .msg ファイルを参照)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="c47bb-235">[ファイル] を **選択し** 、[ネットワーク メッセージ **ID]** を選択すると、初期値は削除されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="c47bb-236">**受信者:** メッセージの元の受信者をリース時に入力するか、[すべて選択] をクリックしてすべての受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="c47bb-237">[すべて選択] **をクリックし** 、個々の受信者を選択的に削除できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="c47bb-238">**申請の理由**: **ブロックされていない** (既定) または **ブロックされている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="c47bb-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="c47bb-239">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c47bb-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="c47bb-240">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="c47bb-241">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="c47bb-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="c47bb-242">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="c47bb-243">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c47bb-244">次のシナリオを検討してください:john@gmail.com メッセージをメッセージに送信 faith@contoso.com と john@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c47bb-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="c47bb-245">Gmail は、このメッセージを 2 つのコピーに分割し、どちらも Microsoft でフィッシング詐欺として検疫にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="c47bb-246">管理者は、これらのメッセージの両方をリリースして、admin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c47bb-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="c47bb-247">管理メールボックスに到達した最初のリリース済みメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="c47bb-248">2 番目にリリースされたメッセージは重複配信として識別され、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="c47bb-249">メッセージ ID と受信時間が同じ場合、メッセージは重複として識別されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="c47bb-250">**メッセージの** 削除 : 表示される警告 **で [は** い] をクリックすると、メッセージは元の受信者に送信されることなくすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="c47bb-251">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="c47bb-252">Microsoft Defender for Office 365 のみ: セキュリティ コンプライアンス センターを使用して&ファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="c47bb-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="c47bb-253">このセクションの検疫済みファイルの手順は、Microsoft Defender Office 365 プラン 1 およびプラン 2 サブスクライバーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="c47bb-254">Defender for Office 365 の組織では、管理者は SharePoint Online、OneDrive for Business、Microsoft Teams で検疫済みファイルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="c47bb-255">これらのファイルの保護を有効にするには [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c47bb-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="c47bb-256">検疫済みファイルの表示</span><span class="sxs-lookup"><span data-stu-id="c47bb-256">View quarantined files</span></span>

1. <span data-ttu-id="c47bb-257">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="c47bb-258">[検疫 **済みビュー] を値** ファイルに **変更します**。</span><span class="sxs-lookup"><span data-stu-id="c47bb-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="c47bb-259">使用可能な列ヘッダーをクリックすると、フィールドの並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="c47bb-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="c47bb-260">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="c47bb-261">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="c47bb-262">既定の列には、アスタリスク ( ) が付いています <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="c47bb-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="c47bb-263">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="c47bb-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-264">**場所**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-265">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-266">**ファイル URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-267">**ファイル サイズ**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-268">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-269">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c47bb-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="c47bb-270">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="c47bb-270">**Detected by**</span></span>
   - <span data-ttu-id="c47bb-271">**時間による変更**</span><span class="sxs-lookup"><span data-stu-id="c47bb-271">**Modified by time**</span></span>

4. <span data-ttu-id="c47bb-272">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c47bb-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="c47bb-273">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c47bb-273">The available filters are:</span></span>

   - <span data-ttu-id="c47bb-274">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="c47bb-275">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-275">**Today**</span></span>
     - <span data-ttu-id="c47bb-276">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-276">**Next 2 days**</span></span>
     - <span data-ttu-id="c47bb-277">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-277">**Next 7 days**</span></span>
     - <span data-ttu-id="c47bb-278">カスタムの日付/時刻範囲。</span><span class="sxs-lookup"><span data-stu-id="c47bb-278">A custom date/time range.</span></span>
   - <span data-ttu-id="c47bb-279">**受信時刻**</span><span class="sxs-lookup"><span data-stu-id="c47bb-279">**Received time**</span></span>
   - <span data-ttu-id="c47bb-280">**検疫の理由**: 使用可能な値は Malware **のみです**。</span><span class="sxs-lookup"><span data-stu-id="c47bb-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="c47bb-281">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="c47bb-281">**Policy type**</span></span>

<span data-ttu-id="c47bb-282">特定の検疫済みファイルを見つけたら、ファイルを選択して詳細を表示し、そのファイルに対してアクションを実行します (メッセージの表示、リリース、ダウンロード、削除など)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="c47bb-283">検疫済みファイルの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="c47bb-283">View quarantined file details</span></span>

<span data-ttu-id="c47bb-284">一覧でファイルを選択すると、[詳細] フライアウト ウィンドウに次のファイル **の詳細** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c47bb-285">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="c47bb-285">**File Name**</span></span>
- <span data-ttu-id="c47bb-286">**ファイル URL**: ファイルの場所を定義する URL (SharePoint Online など)。</span><span class="sxs-lookup"><span data-stu-id="c47bb-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="c47bb-287">**悪意のあるコンテンツが検出された** ファイルが検疫された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="c47bb-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="c47bb-288">**有効期限**: ファイルが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="c47bb-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="c47bb-289">**検出者**: Defender for Office 365 または Microsoft のマルウェア対策エンジン。</span><span class="sxs-lookup"><span data-stu-id="c47bb-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="c47bb-290">**[解放済み?]**</span><span class="sxs-lookup"><span data-stu-id="c47bb-290">**Released?**</span></span>
- <span data-ttu-id="c47bb-291">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="c47bb-291">**Malware Name**</span></span>
- <span data-ttu-id="c47bb-292">**ドキュメント ID**: ドキュメントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="c47bb-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="c47bb-293">**ファイル サイズ**: キロバイト (KB) で指定します。</span><span class="sxs-lookup"><span data-stu-id="c47bb-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="c47bb-294">**組織** 組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c47bb-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="c47bb-295">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="c47bb-295">**Last modified**</span></span>
- <span data-ttu-id="c47bb-296">**[変更者**] : ファイルを最後に変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="c47bb-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="c47bb-297">**Secure Hash Algorithm 256-bit (SHA-256)** の値 : このハッシュ値を使用して、他の評価ストアまたは環境内の他の場所にあるファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="c47bb-298">検疫済みファイルに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="c47bb-298">Take action on quarantined files</span></span>

<span data-ttu-id="c47bb-299">一覧でファイルを選択すると、[詳細] フライアウト ウィンドウでファイルに対して次の **操作** を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c47bb-300">**ファイルを解放** する : 分析のためにMicrosoft にレポート ファイルを選択 (既定) または選択解除し、[ファイルのリリース]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c47bb-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="c47bb-301">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="c47bb-301">**Download file**</span></span>
- <span data-ttu-id="c47bb-302">**検疫からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="c47bb-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="c47bb-303">ファイルを解放または削除しない場合、既定の検疫保持期間の有効期限が切れると、ファイルは削除されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="c47bb-304">複数の検疫済みファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="c47bb-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="c47bb-305">リストで複数の検疫済みファイル (最大 100) を選択すると、[一括操作] フライアウト ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="c47bb-306">**ファイルを解放する**</span><span class="sxs-lookup"><span data-stu-id="c47bb-306">**Release files**</span></span>
- <span data-ttu-id="c47bb-307">**ファイルの削除**: 表示される **警告で [は** い] をクリックすると、ファイルはすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="c47bb-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="c47bb-308">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して、検疫済みメッセージとファイルを表示および管理する</span><span class="sxs-lookup"><span data-stu-id="c47bb-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="c47bb-309">検疫内のメッセージとファイルを表示および管理するコマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c47bb-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="c47bb-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c47bb-310">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="c47bb-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c47bb-311">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="c47bb-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c47bb-312">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="c47bb-313">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): このコマンドレットはメッセージ専用であり、SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルからのマルウェア ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="c47bb-313">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="c47bb-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c47bb-314">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)