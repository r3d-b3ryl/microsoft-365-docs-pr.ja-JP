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
description: 管理者は、Exchange Online Protection (EOP) のすべてのユーザーの検疫済みメッセージを表示および管理する方法について学習できます。 Office 365 用 Microsoft Defender を使用している組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams で検疫済みファイルを管理することもできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a91f53f8efe4fa6944f0debff472da87b7f17e0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167493"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="24a09-104">EOP の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="24a09-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="24a09-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="24a09-105">**Applies to**</span></span>
- [<span data-ttu-id="24a09-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="24a09-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="24a09-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="24a09-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="24a09-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24a09-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="24a09-109">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="24a09-110">詳細については [、「EOP での検疫済み電子メール メッセージ」を参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="24a09-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="24a09-111">管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、解放、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="24a09-112">マルウェア、信頼度の高いフィッシング詐欺、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="24a09-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="24a09-113">管理者は、誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="24a09-114">Office 365 用 Microsoft Defender を使用している組織の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams の検疫済みファイルを表示、ダウンロード、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="24a09-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="24a09-115">検疫済みメッセージは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="24a09-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="24a09-116">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="24a09-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="24a09-117">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="24a09-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="24a09-118">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="24a09-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="24a09-119">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a09-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="24a09-120">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a09-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="24a09-121">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="24a09-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="24a09-122">すべてのユーザーの検疫済みメッセージに対してアクションを実行するには、組織の管理、セキュリティ管理者、または検疫管理者の役割グループのメンバー **である** <sup>\*</sup> 必要があります。</span><span class="sxs-lookup"><span data-stu-id="24a09-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="24a09-123">すべてのユーザーの検疫済みメッセージに読み取り専用でアクセスするには、グローバル閲覧者役割グループまたはセキュリティ閲覧者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="24a09-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="24a09-124">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a09-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="24a09-125">**注**:</span><span class="sxs-lookup"><span data-stu-id="24a09-125">**Notes**:</span></span>

  - <span data-ttu-id="24a09-126">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="24a09-127">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a09-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="24a09-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="24a09-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="24a09-129"><sup>\*</sup>また、検疫管理者役割グループのメンバーは、Exchange Online PowerShell で検疫手順を実行するために [、Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **Hygiene Management** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="24a09-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="24a09-130">検疫済みメッセージは、自動的に削除される前の既定の期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="24a09-131">スパム対策ポリシー (スパム、フィッシング、バルク メール) によって検疫されたメッセージの場合は 30 日間。</span><span class="sxs-lookup"><span data-stu-id="24a09-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="24a09-132">これは既定値と最大値です。</span><span class="sxs-lookup"><span data-stu-id="24a09-132">This is the default and maximum value.</span></span> <span data-ttu-id="24a09-133">この値を (低く) 構成するには、「スパム対策ポリシーを構成 [する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="24a09-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="24a09-134">マルウェアを含むメッセージの場合は 15 日間。</span><span class="sxs-lookup"><span data-stu-id="24a09-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="24a09-135">365 用 Defender の SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルによって検疫されたファイルOffice 15 日間。</span><span class="sxs-lookup"><span data-stu-id="24a09-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="24a09-136">検疫からメッセージの有効期限が切れると、メッセージを回復できません。</span><span class="sxs-lookup"><span data-stu-id="24a09-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="24a09-137">セキュリティ/コンプライアンス センター&使用して検疫済み電子メール メッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="24a09-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="24a09-138">検疫済みメールを表示する</span><span class="sxs-lookup"><span data-stu-id="24a09-138">View quarantined email</span></span>

1. <span data-ttu-id="24a09-139">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24a09-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="24a09-140">[**検疫済みを表示**] が既定値の [**メール**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24a09-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="24a09-141">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="24a09-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="24a09-142">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="24a09-143">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="24a09-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="24a09-144">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-145">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-146">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-147">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-148">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-149">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="24a09-150">**Expires**</span></span>
   - <span data-ttu-id="24a09-151">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="24a09-151">**Recipient**</span></span>
   - <span data-ttu-id="24a09-152">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="24a09-152">**Message ID**</span></span>
   - <span data-ttu-id="24a09-153">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="24a09-153">**Policy name**</span></span>
   - <span data-ttu-id="24a09-154">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="24a09-154">**Size**</span></span>
   - <span data-ttu-id="24a09-155">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="24a09-155">**Direction**</span></span>

   <span data-ttu-id="24a09-156">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="24a09-157">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="24a09-158">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24a09-158">The available filters are:</span></span>

   - <span data-ttu-id="24a09-159">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="24a09-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="24a09-160">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="24a09-160">**Today**</span></span>
     - <span data-ttu-id="24a09-161">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="24a09-161">**Next 2 days**</span></span>
     - <span data-ttu-id="24a09-162">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="24a09-162">**Next 7 days**</span></span>
     - <span data-ttu-id="24a09-163">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="24a09-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="24a09-164">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="24a09-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="24a09-165">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="24a09-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="24a09-166">**ポリシー**: メッセージがメール フロー ルール (トランスポート ルールとも呼ばれる) の条件と一致しました。</span><span class="sxs-lookup"><span data-stu-id="24a09-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="24a09-167">**バルク**</span><span class="sxs-lookup"><span data-stu-id="24a09-167">**Bulk**</span></span>
     - <span data-ttu-id="24a09-168">**フィッシング**: スパム フィルターの判別は、メッセージを検疫したフィッシングメールまたはフィッシング対策保護 ([ス](set-up-anti-phishing-policies.md#spoof-settings)プーフィング設定または偽装保護)[でした](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="24a09-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="24a09-169">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="24a09-169">**Malware**</span></span>
     - <span data-ttu-id="24a09-170">**スパム**</span><span class="sxs-lookup"><span data-stu-id="24a09-170">**Spam**</span></span>
     - <span data-ttu-id="24a09-171">**信頼度の高いフィッシング**</span><span class="sxs-lookup"><span data-stu-id="24a09-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="24a09-172">**ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="24a09-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="24a09-173">**マルウェア対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="24a09-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="24a09-174">**安全な添付ファイル ポリシー**</span><span class="sxs-lookup"><span data-stu-id="24a09-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="24a09-175">**フィッシング対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="24a09-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="24a09-176">**ホストされているコンテンツ フィルター ポリシー** (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="24a09-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="24a09-177">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="24a09-177">**Transport rule**</span></span>

   - <span data-ttu-id="24a09-178">**電子メールの** 受信者 : すべてのユーザーまたは送信されたメッセージのみ。</span><span class="sxs-lookup"><span data-stu-id="24a09-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="24a09-179">エンド ユーザーは、送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="24a09-180">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="24a09-181">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="24a09-182">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="24a09-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="24a09-183">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="24a09-183">Wildcards aren't supported.</span></span> <span data-ttu-id="24a09-184">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-184">You can search by the following values:</span></span>

   - <span data-ttu-id="24a09-185">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="24a09-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="24a09-186">たとえば、メッセージ追跡を[](message-trace-scc.md)使用して組織内のユーザーに送信されたメッセージを探し、メッセージが配信されるのではなく検疫されたと判断したとします。</span><span class="sxs-lookup"><span data-stu-id="24a09-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="24a09-187">必ず完全なメッセージ ID 値を含める必要があります。この値には、角かっこ ( ) が含まれる場合があります \<\> 。</span><span class="sxs-lookup"><span data-stu-id="24a09-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="24a09-188">例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="24a09-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="24a09-189">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="24a09-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="24a09-190">**ポリシー名**: メッセージのポリシー名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="24a09-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="24a09-191">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="24a09-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="24a09-192">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="24a09-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="24a09-193">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="24a09-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="24a09-194">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="24a09-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="24a09-195">**ポリシー名**: メッセージの確認を担当したポリシーの名前。</span><span class="sxs-lookup"><span data-stu-id="24a09-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="24a09-196">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="24a09-197">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="24a09-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="24a09-198">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="24a09-198">View quarantined message details</span></span>

<span data-ttu-id="24a09-199">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="24a09-200">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="24a09-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="24a09-201">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="24a09-201">**Sender address**</span></span>

- <span data-ttu-id="24a09-202">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="24a09-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="24a09-203">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="24a09-203">**Subject**</span></span>

- <span data-ttu-id="24a09-204">**検疫の理由**: メッセージがスパム、バルク、**フィッシング**、メール フロー ルール **(** トランスポート ルール) と一致した、またはマルウェアを含むとして識別された場合に表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="24a09-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="24a09-205">**受信者数**</span><span class="sxs-lookup"><span data-stu-id="24a09-205">**Recipient count**</span></span>

- <span data-ttu-id="24a09-206">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24a09-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="24a09-207">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="24a09-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="24a09-208">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="24a09-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="24a09-209">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="24a09-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="24a09-210">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="24a09-210">Take action on quarantined email</span></span>

<span data-ttu-id="24a09-211">メッセージを選択した後、[詳細] フライアウト ウィンドウのメッセージに対して行う操作には、 **いくつかのオプションがあります** 。</span><span class="sxs-lookup"><span data-stu-id="24a09-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="24a09-212">**メッセージを** 解放する : 表示されるフライアウト ウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24a09-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="24a09-213">**分析のために Microsoft に** メッセージを報告する : これは既定で選択され、誤って検疫されたメッセージを誤検知として Microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="24a09-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="24a09-214">メッセージがスパム、バルク、フィッシング、またはマルウェアを含むとして検疫された場合、メッセージは Microsoft スパム分析チームにも報告されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="24a09-215">分析によっては、メッセージを許可するためにサービス全体のスパム フィルター ルールが調整される場合があります。</span><span class="sxs-lookup"><span data-stu-id="24a09-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="24a09-216">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24a09-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="24a09-217">**すべての受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="24a09-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="24a09-218">**特定の受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="24a09-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="24a09-219">**他のユーザーに** メッセージを解放する : 元の受信者以外のユーザーへのマルウェア メッセージの解放はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="24a09-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="24a09-220">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="24a09-221">メッセージの解放に関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="24a09-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="24a09-222">同じ受信者に対してメッセージを 2 回以上解放できない。</span><span class="sxs-lookup"><span data-stu-id="24a09-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="24a09-223">メッセージを受信していない受信者だけが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="24a09-224">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="24a09-225">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="24a09-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="24a09-226">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24a09-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="24a09-227">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24a09-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="24a09-228">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="24a09-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="24a09-229">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="24a09-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="24a09-230">**検疫から削除**: 表示される警告で **[は** い] をクリックすると、メッセージは元の受信者に送信されることなく直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="24a09-231">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="24a09-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="24a09-232">**メッセージの** 送信 : 表示されるフライアウト ウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="24a09-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="24a09-233">**オブジェクトの種類**: **電子メール** (既定 **)、URL、** または **添付ファイル**。</span><span class="sxs-lookup"><span data-stu-id="24a09-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="24a09-234">**送信形式**: **ネットワーク メッセージ ID** (既定では、[ネットワーク メッセージ **ID]** ボックスに対応する値が表示されます)、または **[ファイル** ] (ローカルの .eml または .msg ファイルを参照) です。</span><span class="sxs-lookup"><span data-stu-id="24a09-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="24a09-235">[ファイル] を **選択し** 、[ネットワーク メッセージ **ID]** を選択すると、初期値は表示されません。</span><span class="sxs-lookup"><span data-stu-id="24a09-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="24a09-236">**[受信者]:** メッセージの元の受信者 1 人をリースで入力するか、[すべて選択] をクリックしてすべての受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="24a09-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="24a09-237">[すべて選択] **をクリックし** 、個々の受信者を選択的に削除できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="24a09-238">**送信の理由**: **ブロックされていない (既定** ) または **ブロックされている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="24a09-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="24a09-239">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="24a09-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="24a09-240">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="24a09-241">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="24a09-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="24a09-242">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="24a09-243">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="24a09-244">次のシナリオについて考えます。john@gmail.comメッセージを送信してfaith@contoso.com送信john@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="24a09-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="24a09-245">Gmail は、このメッセージを 2 つのコピーに分割し、どちらも Microsoft でフィッシングとして検疫にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="24a09-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="24a09-246">管理者は、これらの両方のメッセージを解放してadmin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="24a09-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="24a09-247">管理者メールボックスに到達した最初のリリース 済みメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="24a09-248">2 番目にリリースされたメッセージは重複配信として識別され、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="24a09-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="24a09-249">メッセージ ID と受信時間が同じ場合、メッセージは重複として識別されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="24a09-250">**Delete messages**: After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span><span class="sxs-lookup"><span data-stu-id="24a09-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="24a09-251">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="24a09-252">Microsoft Defender for Office 365 のみ: セキュリティ センター コンプライアンス センター&使用して検疫済みファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="24a09-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="24a09-253">このセクションの検疫済みファイルの手順は、Office 365 プラン 1 およびプラン 2 サブスクライバー向け Microsoft Defender でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="24a09-254">Defender for Office 365 を使用している組織では、管理者は SharePoint Online、OneDrive for Business、および Microsoft Teams で検疫済みファイルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="24a09-255">これらのファイルの保護を有効にするには [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)の安全な添付ファイルを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a09-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="24a09-256">検疫済みファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="24a09-256">View quarantined files</span></span>

1. <span data-ttu-id="24a09-257">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="24a09-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="24a09-258">[ **検疫済みビュー] を** 値ファイルに変更 **します**。</span><span class="sxs-lookup"><span data-stu-id="24a09-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="24a09-259">使用可能な列見出しをクリックすると、フィールドを並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="24a09-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="24a09-260">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="24a09-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="24a09-261">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="24a09-262">既定の列には、アスタリスク ( ) が付いています <sup>\*</sup> 。</span><span class="sxs-lookup"><span data-stu-id="24a09-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="24a09-263">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="24a09-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-264">**場所**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-265">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-266">**ファイル URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-267">**ファイル サイズ**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-268">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-269">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="24a09-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="24a09-270">**検出者**</span><span class="sxs-lookup"><span data-stu-id="24a09-270">**Detected by**</span></span>
   - <span data-ttu-id="24a09-271">**時間別に変更**</span><span class="sxs-lookup"><span data-stu-id="24a09-271">**Modified by time**</span></span>

4. <span data-ttu-id="24a09-272">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24a09-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="24a09-273">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24a09-273">The available filters are:</span></span>

   - <span data-ttu-id="24a09-274">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="24a09-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="24a09-275">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="24a09-275">**Today**</span></span>
     - <span data-ttu-id="24a09-276">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="24a09-276">**Next 2 days**</span></span>
     - <span data-ttu-id="24a09-277">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="24a09-277">**Next 7 days**</span></span>
     - <span data-ttu-id="24a09-278">ユーザー設定の日付/時刻範囲。</span><span class="sxs-lookup"><span data-stu-id="24a09-278">A custom date/time range.</span></span>
   - <span data-ttu-id="24a09-279">**受信時刻**</span><span class="sxs-lookup"><span data-stu-id="24a09-279">**Received time**</span></span>
   - <span data-ttu-id="24a09-280">**検疫の理由**: 利用可能な唯一の値は **マルウェアです**。</span><span class="sxs-lookup"><span data-stu-id="24a09-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="24a09-281">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="24a09-281">**Policy type**</span></span>

<span data-ttu-id="24a09-282">特定の検疫済みファイルを見つけたら、ファイルを選択してファイルの詳細を表示し、そのファイルに対してアクションを実行します (メッセージの表示、解放、ダウンロード、削除など)。</span><span class="sxs-lookup"><span data-stu-id="24a09-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="24a09-283">検疫済みファイルの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="24a09-283">View quarantined file details</span></span>

<span data-ttu-id="24a09-284">一覧でファイルを選択すると、[詳細] フライアウト ウィンドウに次の **ファイルの詳細** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="24a09-285">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="24a09-285">**File Name**</span></span>
- <span data-ttu-id="24a09-286">**ファイル URL**: ファイルの場所を定義する URL (SharePoint Online など)。</span><span class="sxs-lookup"><span data-stu-id="24a09-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="24a09-287">**悪意のあるコンテンツが検出された場合** ファイルが検疫された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="24a09-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="24a09-288">**有効期限**: ファイルが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="24a09-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="24a09-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span><span class="sxs-lookup"><span data-stu-id="24a09-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="24a09-290">**[解放済み?]**</span><span class="sxs-lookup"><span data-stu-id="24a09-290">**Released?**</span></span>
- <span data-ttu-id="24a09-291">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="24a09-291">**Malware Name**</span></span>
- <span data-ttu-id="24a09-292">**ドキュメント ID**: ドキュメントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="24a09-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="24a09-293">**ファイル サイズ**: キロバイト (KB) 単位。</span><span class="sxs-lookup"><span data-stu-id="24a09-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="24a09-294">**組織** 組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="24a09-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="24a09-295">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="24a09-295">**Last modified**</span></span>
- <span data-ttu-id="24a09-296">**Modified By**: ファイルを最後に変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="24a09-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="24a09-297">**セキュア ハッシュ アルゴリズム 256 ビット (SHA-256)** 値 : このハッシュ値を使用して、環境内の他の評価ストアまたは他の場所にあるファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="24a09-298">検疫済みファイルに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="24a09-298">Take action on quarantined files</span></span>

<span data-ttu-id="24a09-299">一覧でファイルを選択すると、[詳細] フライアウト ウィンドウでファイルに対して次の **操作** を実行できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="24a09-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis,** and then click **Release files**.</span><span class="sxs-lookup"><span data-stu-id="24a09-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="24a09-301">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="24a09-301">**Download file**</span></span>
- <span data-ttu-id="24a09-302">**検疫からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="24a09-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="24a09-303">ファイルを解放または削除しない場合、既定の検疫の保持期間が経過すると、ファイルは削除されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="24a09-304">複数の検疫済みファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="24a09-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="24a09-305">リスト内の複数の検疫済みファイル (最大 100)を選択すると、[一括操作] フライアウト ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="24a09-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="24a09-306">**ファイルを解放する**</span><span class="sxs-lookup"><span data-stu-id="24a09-306">**Release files**</span></span>
- <span data-ttu-id="24a09-307">**ファイルを** 削除する : 表示される警告 **で [は** い] をクリックすると、ファイルはすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="24a09-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="24a09-308">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して検疫済みメッセージとファイルを表示および管理する</span><span class="sxs-lookup"><span data-stu-id="24a09-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="24a09-309">検疫内のメッセージとファイルを表示および管理するコマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24a09-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="24a09-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="24a09-310">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="24a09-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="24a09-311">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="24a09-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="24a09-312">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="24a09-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): このコマンドレットはメッセージ専用であり、SharePoint、OneDrive、および Microsoft Teams の安全な添付ファイルからのマルウェア ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="24a09-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="24a09-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="24a09-314">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
