---
title: 脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、組織の脅威保護Microsoft 365、組織で使用する方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c32026ab4f33a68b1f63cb000807671839f6bad
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821285"
---
# <a name="protect-against-threats"></a><span data-ttu-id="cc045-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="cc045-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cc045-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="cc045-104">**Applies to**</span></span>
- [<span data-ttu-id="cc045-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cc045-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cc045-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="cc045-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cc045-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc045-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cc045-108">次に、Defender の構成をチャンクに分割するクイック スタート Office 365示します。</span><span class="sxs-lookup"><span data-stu-id="cc045-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="cc045-109">Office 365 の脅威保護機能を初めから使用する場合は、どこから始めるのか分からず、最善の方法で学習する場合は、チェックリストと開始点としてこのガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="cc045-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc045-110">**最初の推奨設定は** ポリシーの種類ごとに含まれていますが、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc045-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="cc045-111">ポリシーまたは変更がデータセンター経由で動作するには、約 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="cc045-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc045-112">要件</span><span class="sxs-lookup"><span data-stu-id="cc045-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="cc045-113">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="cc045-113">Subscriptions</span></span>

<span data-ttu-id="cc045-114">脅威保護機能は、すべての Microsoft *または* Office 365サブスクリプションに含まれています。ただし、一部のサブスクリプションには高度な機能があります。</span><span class="sxs-lookup"><span data-stu-id="cc045-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="cc045-115">次の表に、この記事に含まれる保護機能と最小サブスクリプション要件を示します。</span><span class="sxs-lookup"><span data-stu-id="cc045-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="cc045-116">監査を有効にする指示を超えて、手順によってマルウェア対策、フィッシング対策、スパム対策が開始され、Office 365 Exchange Online Protection (**EOP)** の一部としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="cc045-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="cc045-117">これは、(Defender **for Office 365**) に EOP が含まれているとビルドされるまで、Office 365 の Defender の記事では奇妙に思えます。</span><span class="sxs-lookup"><span data-stu-id="cc045-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

<br>

****

|<span data-ttu-id="cc045-118">保護の種類</span><span class="sxs-lookup"><span data-stu-id="cc045-118">Protection type</span></span>|<span data-ttu-id="cc045-119">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="cc045-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="cc045-120">監査ログ (レポート用)</span><span class="sxs-lookup"><span data-stu-id="cc045-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="cc045-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc045-121">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="cc045-122">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="cc045-122">Anti-malware protection</span></span>|<span data-ttu-id="cc045-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="cc045-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="cc045-124">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="cc045-124">Anti-phishing protection</span></span>|[<span data-ttu-id="cc045-125">EOP</span><span class="sxs-lookup"><span data-stu-id="cc045-125">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="cc045-126">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="cc045-126">Anti-spam protection</span></span>|[<span data-ttu-id="cc045-127">EOP</span><span class="sxs-lookup"><span data-stu-id="cc045-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="cc045-128">0 時間の自動削除 (電子メールの場合)</span><span class="sxs-lookup"><span data-stu-id="cc045-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="cc045-129">EOP</span><span class="sxs-lookup"><span data-stu-id="cc045-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="cc045-130">電子メールおよびドキュメント内の悪意のある URL とファイルOfficeからの保護 (セーフ リンクセーフ添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="cc045-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="cc045-131">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="cc045-132">ワークロードのセーフ、SharePoint、OneDriveの添付ファイルMicrosoft Teamsする</span><span class="sxs-lookup"><span data-stu-id="cc045-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="cc045-133">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-133">Microsoft Defender for Office 365</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="cc045-134">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="cc045-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="cc045-135">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-135">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="cc045-136">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="cc045-136">Roles and permissions</span></span>

<span data-ttu-id="cc045-137">Defender for Office 365 ポリシーを構成するには、セキュリティ コンプライアンス センターで適切な役割を割[り&必要があります](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="cc045-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="cc045-138">これらのアクションを実行できるロールについては、以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc045-138">Take a look at the table below for roles that can do these actions.</span></span>

<br>

****

|<span data-ttu-id="cc045-139">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="cc045-139">Role or role group</span></span>|<span data-ttu-id="cc045-140">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc045-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="cc045-141">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="cc045-141">global administrator</span></span>|[<span data-ttu-id="cc045-142">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="cc045-142">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="cc045-143">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="cc045-143">Security Administrator</span></span>|[<span data-ttu-id="cc045-144">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cc045-144">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="cc045-145">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="cc045-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="cc045-146">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cc045-146">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="cc045-147">および</span><span class="sxs-lookup"><span data-stu-id="cc045-147">and</span></span> <p> [<span data-ttu-id="cc045-148">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc045-148">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="cc045-149">詳細については、「セキュリティ コンプライアンス センターのアクセス許可 [」&参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="cc045-150">レポートと調査の監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="cc045-150">Turn on Audit logging for reporting and investigation</span></span>

- <span data-ttu-id="cc045-151">監査ログを早期に開始します。</span><span class="sxs-lookup"><span data-stu-id="cc045-151">Start your audit logging early.</span></span> <span data-ttu-id="cc045-152">次の手順の一部について **、監査を ON** にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc045-152">You'll need auditing to be **ON** for some of the following steps.</span></span> <span data-ttu-id="cc045-153">監査ログは、監査ログを含むサブスクリプション[Exchange Online。](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="cc045-153">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="cc045-154">セキュリティ ダッシュボード、電子メール セキュリティ レポート、エクスプローラーなどの脅威保護レポート [](view-email-security-reports.md)のデータを表示するには [](threat-explorer.md)、監査ログをオンにする必要 *があります*。 [](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="cc045-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="cc045-155">詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection-in-eop"></a><span data-ttu-id="cc045-156">パート 1 - EOP のマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="cc045-156">Part 1 - Anti-malware protection in EOP</span></span>

<span data-ttu-id="cc045-157">マルウェア対策の推奨設定の詳細については [、「EOP マルウェア対策ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="cc045-157">For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).</span></span>

1. <span data-ttu-id="cc045-158">を <https://security.microsoft.com/antimalwarev2> 開きます。</span><span class="sxs-lookup"><span data-stu-id="cc045-158">Open <https://security.microsoft.com/antimalwarev2>.</span></span>

2. <span data-ttu-id="cc045-159">[マルウェア対策 **] ページで** 、名前をクリックして **[既定** のポリシー] という名前のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc045-159">On the **Anti-malware** page, select the policy named **Default** policy by clicking on the name.</span></span>

3. <span data-ttu-id="cc045-160">開くポリシーの詳細フライアウトで、[保護設定の編集] を **クリック** し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-160">In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:</span></span>
   - <span data-ttu-id="cc045-161">[共通 **の添付ファイル フィルターを有効** にする] を選択して、共通の添付ファイル フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cc045-161">Select **Enable the common attachments filter** to turn on the common attachments filter.</span></span> <span data-ttu-id="cc045-162">[ファイル **の種類のカスタマイズ] を** クリックして、ファイルの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc045-162">Click **Customize file types** to add more file types.</span></span>
   - <span data-ttu-id="cc045-163">[マルウェアに **対して 0 時間自動削除を有効にする] が** 選択されている点を確認します。</span><span class="sxs-lookup"><span data-stu-id="cc045-163">Verify that **Enable zero-hour auto purge for malware** is selected.</span></span>
   - <span data-ttu-id="cc045-164">[通知] セクションの設定が **選択** されなかっているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc045-164">Verify that none of the settings in the **Notification** section are selected.</span></span>

   <span data-ttu-id="cc045-165">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-165">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="cc045-166">ポリシーの詳細ポップアップに戻り、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-166">Back on the policy details flyout, click **Close**.</span></span>

<span data-ttu-id="cc045-167">マルウェア対策ポリシーを構成する手順の詳細については、「EOP でマルウェア対策ポリシーを構成する」 [を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-167">For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a><span data-ttu-id="cc045-168">パート 2 - EOP と Defender のフィッシング対策Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-168">Part 2 - Anti-phishing protection in EOP and Defender for Office 365</span></span>

<span data-ttu-id="cc045-169">[フィッシング対策保護は、EOP](anti-phishing-protection.md) を含むサブスクリプションで [利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="cc045-169">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="cc045-170">高度なフィッシング対策保護は、Defender でセキュリティ保護[Office 365。](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="cc045-170">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="cc045-171">フィッシング対策ポリシーの推奨設定の詳細については、「Microsoft Defender for Office 365」の[「EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)フィッシング対策ポリシー設定」および「フィッシング対策ポリシー設定[」を参照してください](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="cc045-171">For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="cc045-172">次の手順では、既定のフィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc045-172">The following procedure describes how to configure the default anti-phishing policy.</span></span> <span data-ttu-id="cc045-173">設定の Defender でのみ使用可能なOffice 365は、明確にマークされます。</span><span class="sxs-lookup"><span data-stu-id="cc045-173">Settings that are only available in Defender for Office 365 are clearly marked.</span></span>

1. <span data-ttu-id="cc045-174">を <https://security.microsoft.com/antiphishing> 開きます。</span><span class="sxs-lookup"><span data-stu-id="cc045-174">Open <https://security.microsoft.com/antiphishing>.</span></span>

2. <span data-ttu-id="cc045-175">[フィッシング **対策] ページで** 、名前をクリックして **Office365 AntiPhish Default (Default)** という名前のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc045-175">On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="cc045-176">表示されるポリシーの詳細フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-176">In the policy details flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cc045-177">**[フィッシングの&保護** ] セクション: **[保護** 設定の編集] をクリックし、開く [保護設定の編集] **フライアウト** で次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-177">**Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the **Edit protection settings** flyout that opens:</span></span>
     - <span data-ttu-id="cc045-178">**フィッシングメールの** <sup>\*</sup> しきい値: **[2 - アグレッシブ**(Standard) ] または **[3 - More Aggressive** (Strict] ) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc045-178">**Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).</span></span>
     - <span data-ttu-id="cc045-179">**[偽装]** <sup>\*</sup> セクション: 次の値を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-179">**Impersonation** section<sup>\*</sup>: Configure the following values:</span></span>
       - <span data-ttu-id="cc045-180">[ユーザー **の** 保護を有効にする] を選択し、表示される [送信者の管理 **] リンク** をクリックし、組織の役員、CEO、CFO、その他の上級リーダーなど、偽装から保護するために内部および外部の送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc045-180">Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span>
       - <span data-ttu-id="cc045-181">[ **保護するドメインを有効にする**] を選択し、表示される次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-181">Select **Enable domains to protect**, and then configure the following settings that appear:</span></span>
         - <span data-ttu-id="cc045-182">[ **自分が所有するドメインを含める** ] を選択して、受け入れドメイン内の内部送信者を偽装から保護します ([自分のドメインの **表示]** をクリックして表示されます)。</span><span class="sxs-lookup"><span data-stu-id="cc045-182">Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.</span></span>
         - <span data-ttu-id="cc045-183">他のドメインの送信者を保護するには、[カスタムドメインを含める] を選択し、表示される [管理 **( nn)** カスタム ドメイン] リンクをクリックしてから、偽装から保護するために他のドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc045-183">To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.</span></span>
     - <span data-ttu-id="cc045-184">**[信頼できる送信者** とドメインの追加] セクション: [管理] <sup>\*</sup> **(nn)** 信頼できる送信者とドメインをクリックして、必要に応じて送信者と送信者ドメインの例外を偽装保護に構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-184">**Add trusted senders and domains** section <sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.</span></span>
     - <span data-ttu-id="cc045-185">メールボックス インテリジェンスの設定 <sup>\*</sup> : [メールボックス インテリジェンス **を有効にする]** と [偽装保護のインテリジェンスを有効にする **] が** 選択されています。</span><span class="sxs-lookup"><span data-stu-id="cc045-185">Mailbox intelligence settings <sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.</span></span>
     - <span data-ttu-id="cc045-186">**[スプー** フィング] セクション: **[スプーフィング インテリジェンスを有効にする] が** 選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc045-186">**Spoof** section: Verify **Enable spoof intelligence** is selected.</span></span>

     <span data-ttu-id="cc045-187">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-187">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="cc045-188">**[アクション** ] セクション: [ **アクションの編集]** をクリックし、開く [アクションの編集] フライアウト **で** 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-188">**Actions** section: Click **Edit actions** and configure the following settings in the **Edit actions** flyout that opens:</span></span>
     - <span data-ttu-id="cc045-189">**[メッセージの操作** ] セクション: 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-189">**Message actions** section: Configure the following settings:</span></span>
       - <span data-ttu-id="cc045-190">**偽装ユーザーとしてメッセージが検出された場合は、[** メッセージを検疫 <sup>\*</sup> **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-190">**If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="cc045-191">**偽装ドメインとしてメッセージが検出された場合** は、[メッセージを検疫 <sup>\*</sup> **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-191">**If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="cc045-192">**メールボックス インテリジェンスが偽装ユーザーを** 検出した場合: [メッセージを受信者の迷惑メール フォルダー (標準) に移動する] または [メッセージを検疫 <sup>\*</sup> する (厳密]) を選択します。  </span><span class="sxs-lookup"><span data-stu-id="cc045-192">**If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
       - <span data-ttu-id="cc045-193">**メッセージがスプーフィングとして検出された場合**: [メッセージを受信者の迷惑メール フォルダー **(標準** ) に移動する] または [メッセージを検疫する (Strict]) を **選択** します。</span><span class="sxs-lookup"><span data-stu-id="cc045-193">**If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
     - <span data-ttu-id="cc045-194">**[インジケーター&ヒント** : 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-194">**Safety tips & indicators** section: Configure the following settings:</span></span>
       - <span data-ttu-id="cc045-195">**[ユーザーの偽装を表示安全性のヒント:** <sup>\*</sup> 選択 (オン) します。</span><span class="sxs-lookup"><span data-stu-id="cc045-195">**Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="cc045-196">**[ドメイン偽装の表示] 安全性のヒント** <sup>\*</sup> : 選択 (オン) します。</span><span class="sxs-lookup"><span data-stu-id="cc045-196">**Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="cc045-197">**[ユーザー偽装の異常な文字を表示安全性のヒント** <sup>\*</sup> : 選択 (オン) します。</span><span class="sxs-lookup"><span data-stu-id="cc045-197">**Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="cc045-198">**スプーフィングの認証されていない** 送信者に対して表示 (?) : 選択 (オン) します。</span><span class="sxs-lookup"><span data-stu-id="cc045-198">**Show (?) for unauthenticated senders for spoof**: Select (turn on).</span></span>
       - <span data-ttu-id="cc045-199">**"via" タグを表示する**: この設定が使用可能な場合は、選択 (オン) します。</span><span class="sxs-lookup"><span data-stu-id="cc045-199">**Show "via" tag**: Select (turn on) if this setting is available.</span></span>

     <span data-ttu-id="cc045-200">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-200">When you're finished, click **Save**.</span></span>

   <span data-ttu-id="cc045-201"><sup>\*</sup>この設定は、Defender の場合にのみ使用Office 365。</span><span class="sxs-lookup"><span data-stu-id="cc045-201"><sup>\*</sup> This setting is available only in Defender for Office 365.</span></span>

4. <span data-ttu-id="cc045-202">[保存 **] をクリック** し、[閉じる] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="cc045-202">Click **Save** and then click **Close**</span></span>

<span data-ttu-id="cc045-203">フィッシング対策ポリシーを構成する詳細な手順については[、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」および「Microsoft Defender for Office 365 でフィッシング対策ポリシーを構成する[」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-203">For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection-in-eop"></a><span data-ttu-id="cc045-204">パート 3 - EOP のスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="cc045-204">Part 3 - Anti-spam protection in EOP</span></span>

<span data-ttu-id="cc045-205">スパム対策の推奨設定の詳細については、「EOP スパム対策ポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="cc045-205">For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

1. <span data-ttu-id="cc045-206">を <https://security.microsoft.com/antispam> 開きます。</span><span class="sxs-lookup"><span data-stu-id="cc045-206">Open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="cc045-207">[スパム **対策ポリシー]** ページで、名前をクリックして、リストからスパム対策受信ポリシー **(Default)** という名前のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc045-207">On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="cc045-208">表示されるポリシーの詳細フライアウトで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc045-208">In the policy details flyout that appears, do the following steps:</span></span>
   - <span data-ttu-id="cc045-209">**[迷惑メールのプロパティ&メールの一括しきい値** ] セクション: [スパムのしきい値 **とプロパティの編集] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-209">**Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**.</span></span> <span data-ttu-id="cc045-210">表示される **スパムしきい値とプロパティ の** フライアウトで、[バルクメールのしきい値] の値を 5 (Strict) または 6 (Standard) に設定します。</span><span class="sxs-lookup"><span data-stu-id="cc045-210">In the **spam threshold and properties** flyout that appears, set the **Bulk email threshold** value to 5 (Strict) or 6 (Standard).</span></span> <span data-ttu-id="cc045-211">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-211">When you're finished, click **Save**.</span></span>
   - <span data-ttu-id="cc045-212">**[許可された送信者とブロック** された送信者とドメイン] セクション: 許可されている送信者と許可されたドメインを確認または編集します。</span><span class="sxs-lookup"><span data-stu-id="cc045-212">**Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains.</span></span>

4. <span data-ttu-id="cc045-213">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-213">When you're finished, click **Close**.</span></span>

<span data-ttu-id="cc045-214">スパム対策ポリシーを構成する詳細な手順については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-214">For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="cc045-215">パート 4 - 悪意のある URL とファイルからの保護 (セーフ Defender セーフの添付ファイルOffice 365)</span><span class="sxs-lookup"><span data-stu-id="cc045-215">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="cc045-216">悪意のある URL やファイルからのクリック時の保護は、Microsoft Defender for Office 365 を[含むサブスクリプションで利用できます](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="cc045-216">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="cc045-217">[添付ファイルとリンク][セーフポリシー](safe-attachments.md)セーフ[設定](safe-links.md)されます。</span><span class="sxs-lookup"><span data-stu-id="cc045-217">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cc045-218">セーフMicrosoft Defender の添付ファイル ポリシー (Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-218">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cc045-219">添付ファイルを[セーフするには](safe-attachments.md)、リンク ポリシーを少なくとも 1 セーフ作成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-219">To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="cc045-220">セキュリティ コンプライアンス [センターで、[脅威&](https://protection.office.com)ポリシー  ATP] を選択し、[添付ファイルセーフ \>  \> 作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-220">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="cc045-221">表示される **[新しいセーフ添付** ファイル] ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-221">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cc045-222">[名前] **ボックスに** 「」と `Block malware` 入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-222">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="cc045-223">[設定]**設定** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-223">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="cc045-224">[添付ファイル **のセーフ不明なマルウェアの応答] セクションで、[** ブロック] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-224">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="cc045-225">[添付ファイル **のリダイレクト] セクション** で、[リダイレクトを有効にする **] オプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-225">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="cc045-226">検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc045-226">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="cc045-227">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-227">Click **Next**.</span></span>

3. <span data-ttu-id="cc045-228">[適用先] ページ **で**、[条件の追加]をクリックし、[適用する場合] を選択します。[受信者ドメイン] をクリックし、[追加] をクリックして、ドメインまたはドメインを選択し、[**追加**] をクリックし、[完了] をクリックし、[次へ] をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="cc045-228">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="cc045-229">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-229">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cc045-230">セーフMicrosoft Defender のリンク ポリシーをOffice 365</span><span class="sxs-lookup"><span data-stu-id="cc045-230">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cc045-231">[リンク] を[セーフするには](safe-links.md)、リンクのグローバル設定を確認および編集し、セーフリンク ポリシーを 1 つ以上作成セーフします。</span><span class="sxs-lookup"><span data-stu-id="cc045-231">To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="cc045-232">[セキュリティ &[コンプライアンス](https://protection.office.com)センター]で、[脅威管理ポリシー ATP セーフ リンク] を選択し、[グローバル設定] をクリックし、次の設定 \>  \> を構成します。 </span><span class="sxs-lookup"><span data-stu-id="cc045-232">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="cc045-233">[**次のセーフリンクを使用する: Office 365が** オンになっていることを確認する: ![ トグルオン ](../../media/scc-toggle-on.png) です。</span><span class="sxs-lookup"><span data-stu-id="cc045-233">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="cc045-234">**ユーザーが [リンク] をクリックセーフ追跡** しない : この設定をオフにすると、ユーザーのクリックを追跡できます。[オフ] ![ を切り替えます ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="cc045-234">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="cc045-235">**ユーザーが元の URL への安全なリンク** をクリックさせない : この設定がオンになっていることを確認する: ![ トグルオン ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="cc045-235">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="cc045-236">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-236">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="cc045-237">[リンク] ページのメイン セーフに戻り、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-237">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="cc045-238">表示される **[セーフリンク** の作成] ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-238">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cc045-239">[名前 **] ボックス** に名前を入力し、[次 `Safe Links` へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-239">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="cc045-240">[設定]**設定** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc045-240">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="cc045-241">**メッセージ内の不明な潜在的に悪意のある URL のアクションを選択します**。[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-241">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="cc045-242">**[オン] を選択して**、不明な URL または潜在的に悪意のある URL のMicrosoft Teamsを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-242">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="cc045-243">**組織内で送信された電子メール メッセージへの安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="cc045-243">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="cc045-244">**メッセージを配信する前に URL のスキャンが完了するのを待ちます**</span><span class="sxs-lookup"><span data-stu-id="cc045-244">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="cc045-245">**組織内で送信された電子メール メッセージへの安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="cc045-245">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="cc045-246">**ユーザーに元の URL へのクリックを許可しない**</span><span class="sxs-lookup"><span data-stu-id="cc045-246">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="cc045-247">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-247">Click **Next**</span></span>

4. <span data-ttu-id="cc045-248">[適用先] ページ **で**、[条件の追加]をクリックし、[適用する場合] を選択します。[受信者ドメイン] をクリックし、[追加] をクリックして、ドメインまたはドメインを選択し、[**追加**] をクリックし、[完了] をクリックし、[次へ] をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="cc045-248">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="cc045-249">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-249">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="cc045-250">詳細については、「[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc045-250">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="cc045-251">パート 5 - セーフ、SharePoint、OneDrive、Microsoft Teamsが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="cc045-251">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="cc045-252">ワークロード (SharePoint、OneDrive、Teamsなど) は、コラボレーションのために構築されています。</span><span class="sxs-lookup"><span data-stu-id="cc045-252">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="cc045-253">Defender を使用Office 365、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別されるファイルのブロックと検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cc045-253">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="cc045-254">その動作の詳細については、こちらを参照 [してください](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-254">You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc045-255">**この手順を開始する前に、** 監査ログがユーザー環境で既に有効になっていることをMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="cc045-255">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="cc045-256">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="cc045-256">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="cc045-257">詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-257">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="cc045-258">セキュリティ セキュリティ [コンプライアンス センター&、[](https://protection.office.com)脅威 **管理** ポリシー ATP と添付ファイル] を選択セーフ、[グローバル設定] を \>  \> **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-258">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="cc045-259">[Office 365、 SharePoint、OneDrive、および **Microsoft Teams** の Defender を有効にする] トグルが右にあるのを確認します。オンに切り替え、[ ![ 保存] を ](../../media/scc-toggle-on.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc045-259">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="cc045-260">組織の添付ファイル ポリシーとリンク ポリシーを確認[](set-up-safe-attachments-policies.md)(および、必要に応じてセーフ[セーフ](set-up-safe-links-policies.md)編集) します。</span><span class="sxs-lookup"><span data-stu-id="cc045-260">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).</span></span>

4. <span data-ttu-id="cc045-261">(推奨)グローバル管理者またはオンライン管理者 _SharePoint、DisallowInfectedFileDownload_ パラメーターをに設定して **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します `$true` 。</span><span class="sxs-lookup"><span data-stu-id="cc045-261">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="cc045-262">`$true` 検出されたファイルのすべてのアクション (削除を除く) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-262">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="cc045-263">検出されたファイルを開いたり、移動したり、コピーしたり、共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cc045-263">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="cc045-264">`$false` 削除とダウンロードを除くすべてのアクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="cc045-264">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="cc045-265">ユーザーはリスクを受け入れ、検出されたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="cc045-265">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="cc045-266">PowerShell と一緒に PowerShell を使用する方法Microsoft 365、PowerShell を使用Microsoft 365[を参照してください](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-266">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).</span></span>

5. <span data-ttu-id="cc045-267">変更がすべてのデータ センターに広がり、最大 30 Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="cc045-267">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="cc045-268">検出されたファイルのアラートを設定する</span><span class="sxs-lookup"><span data-stu-id="cc045-268">Now set up alerts for detected files</span></span>

<span data-ttu-id="cc045-269">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるファイルとして識別された場合に通知を受信するには、アラートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="cc045-269">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="cc045-270">[セキュリティ 管理 [] コンプライアンス &で、[](https://protection.office.com)アラートの管理 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-270">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="cc045-271">[新 **しいアラート ポリシー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-271">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="cc045-272">アラートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc045-272">Specify a name for the alert.</span></span> <span data-ttu-id="cc045-273">たとえば、「ライブラリ」に「悪意のあるファイル」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="cc045-273">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="cc045-274">アラートの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="cc045-274">Type a description for the alert.</span></span> <span data-ttu-id="cc045-275">たとえば、「オンライン、SharePoint、またはユーザーに悪意のあるファイルが検出された場合に管理者に通知OneDrive入力Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="cc045-275">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="cc045-276">[この **アラートをいつ送信....] セクションで** 、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="cc045-276">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="cc045-277">a.</span><span class="sxs-lookup"><span data-stu-id="cc045-277">a.</span></span> <span data-ttu-id="cc045-278">[アクティビティ] **リストで** 、[ファイル内 **の検出されたマルウェア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc045-278">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="cc045-279">b.</span><span class="sxs-lookup"><span data-stu-id="cc045-279">b.</span></span> <span data-ttu-id="cc045-280">[ユーザー] **フィールドは** 空のままにします。</span><span class="sxs-lookup"><span data-stu-id="cc045-280">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="cc045-281">[このアラート **を送信する....]** セクションで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc045-281">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="cc045-282">**保存 .**</span><span class="sxs-lookup"><span data-stu-id="cc045-282">**Save**.</span></span>

<span data-ttu-id="cc045-283">アラートの詳細については、「セキュリティ コンプライアンス センターでアクティビティアラートを作成する [&する」を参照してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-283">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cc045-284">構成が完了したら、次のリンクを使用してワークロード調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="cc045-284">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="cc045-285">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="cc045-285">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="cc045-286">セキュリティ センターを使用して、Defender の検疫済みファイルを管理Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-286">Use the security center to manage quarantined files in Defender for Office 365</span></span>](manage-quarantined-messages-and-files.md#use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365)
>- [<span data-ttu-id="cc045-287">悪意のあるファイルがオンライン、オンライン、SharePoint、またはOneDriveにMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc045-287">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="cc045-288">検疫済みメッセージとファイルを管理者として管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc045-288">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="cc045-289">パート 6 - 構成する追加の設定</span><span class="sxs-lookup"><span data-stu-id="cc045-289">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="cc045-290">マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護を構成するとともに、0 時間の自動削除を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cc045-290">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="cc045-291">EOP の電子メールの 0 時間自動削除</span><span class="sxs-lookup"><span data-stu-id="cc045-291">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="cc045-292">[ゼロ時間自動削除](zero-hour-auto-purge.md) (ZAP) は、EOP を含むサブスクリプションで [使用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="cc045-292">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="cc045-293">この保護は既定でオンになっています。ただし、保護が有効になるには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc045-293">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="cc045-294">スパムアクションは、スパム \*\*対策ポリシーの [メッセージを迷惑\*\* メール フォルダーに移動 [する] に設定されています](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-294">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="cc045-295">ユーザーは既定の迷惑メール設定 [を保持](configure-junk-email-settings-on-exo-mailboxes.md)し、迷惑メール保護を無効にしていない。</span><span class="sxs-lookup"><span data-stu-id="cc045-295">Users have kept their default [junk email settings](configure-junk-email-settings-on-exo-mailboxes.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="cc045-296">詳細については、「ゼロ時間自動削除 - スパムとマルウェアに対 [する保護」を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="cc045-296">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="cc045-297">セットアップ後のタスクと次の手順</span><span class="sxs-lookup"><span data-stu-id="cc045-297">Post-setup tasks and next steps</span></span>

<span data-ttu-id="cc045-298">脅威保護機能を構成したら、それらの機能の動作を監視してください。</span><span class="sxs-lookup"><span data-stu-id="cc045-298">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="cc045-299">必要な操作を行うポリシーを確認して修正します。</span><span class="sxs-lookup"><span data-stu-id="cc045-299">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="cc045-300">また、価値を追加できる新機能やサービス更新プログラムを監視します。</span><span class="sxs-lookup"><span data-stu-id="cc045-300">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="cc045-301">操作</span><span class="sxs-lookup"><span data-stu-id="cc045-301">What to do</span></span>|<span data-ttu-id="cc045-302">追加情報</span><span class="sxs-lookup"><span data-stu-id="cc045-302">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="cc045-303">レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する</span><span class="sxs-lookup"><span data-stu-id="cc045-303">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="cc045-304">セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="cc045-304">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="cc045-305">電子メール セキュリティ レポート</span><span class="sxs-lookup"><span data-stu-id="cc045-305">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="cc045-306">Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-306">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="cc045-307">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="cc045-307">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="cc045-308">必要に応じて、脅威保護ポリシーを定期的に確認および修正する</span><span class="sxs-lookup"><span data-stu-id="cc045-308">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="cc045-309">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="cc045-309">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="cc045-310">スマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="cc045-310">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="cc045-311">Microsoft 365の調査と対応の機能</span><span class="sxs-lookup"><span data-stu-id="cc045-311">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="cc045-312">新機能とサービス更新プログラムを監視する</span><span class="sxs-lookup"><span data-stu-id="cc045-312">Watch for new features and service updates</span></span>|[<span data-ttu-id="cc045-313">標準リリースオプションとターゲット リリース オプション</span><span class="sxs-lookup"><span data-stu-id="cc045-313">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="cc045-314">Message Center</span><span class="sxs-lookup"><span data-stu-id="cc045-314">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="cc045-315">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="cc045-315">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="cc045-316">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="cc045-316">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="cc045-317">EOP および Defender の推奨される Standard および Strict セキュリティ構成の詳細については、Office 365</span><span class="sxs-lookup"><span data-stu-id="cc045-317">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="cc045-318">EOP と Microsoft Defender のセキュリティに関するOffice 365設定</span><span class="sxs-lookup"><span data-stu-id="cc045-318">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)|
