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
ms.openlocfilehash: 3381ce66433f1f4e32f0251c45601e3cb84865b6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538725"
---
# <a name="protect-against-threats"></a><span data-ttu-id="732d7-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="732d7-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="732d7-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="732d7-104">**Applies to**</span></span>
- [<span data-ttu-id="732d7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="732d7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="732d7-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="732d7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="732d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="732d7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="732d7-108">次に、Defender の構成をチャンクに分割するクイック スタート Office 365示します。</span><span class="sxs-lookup"><span data-stu-id="732d7-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="732d7-109">Office 365 の脅威保護機能を初めから使用する場合は、どこから始めるのか分からず、最善の方法で学習する場合は、チェックリストと開始点としてこのガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="732d7-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="732d7-110">**最初の推奨設定は** ポリシーの種類ごとに含まれていますが、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="732d7-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="732d7-111">ポリシーまたは変更がデータセンター経由で動作するには、約 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="732d7-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="732d7-112">要件</span><span class="sxs-lookup"><span data-stu-id="732d7-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="732d7-113">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="732d7-113">Subscriptions</span></span>

<span data-ttu-id="732d7-114">脅威保護機能は、すべての Microsoft *または* Office 365サブスクリプションに含まれています。ただし、一部のサブスクリプションには高度な機能があります。</span><span class="sxs-lookup"><span data-stu-id="732d7-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="732d7-115">次の表に、この記事に含まれる保護機能と最小サブスクリプション要件を示します。</span><span class="sxs-lookup"><span data-stu-id="732d7-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="732d7-116">監査を有効にする指示を超えて、手順によってマルウェア対策、フィッシング対策、スパム対策が開始され、Office 365 Exchange Online Protection (**EOP)** の一部としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="732d7-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="732d7-117">これは、(Defender **for Office 365**) に EOP が含まれているとビルドされるまで、Office 365 の Defender の記事では奇妙に思えます。</span><span class="sxs-lookup"><span data-stu-id="732d7-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="732d7-118">保護の種類</span><span class="sxs-lookup"><span data-stu-id="732d7-118">Protection type</span></span>|<span data-ttu-id="732d7-119">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="732d7-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="732d7-120">監査ログ (レポート用)</span><span class="sxs-lookup"><span data-stu-id="732d7-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="732d7-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="732d7-121">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="732d7-122">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="732d7-122">Anti-malware protection</span></span>|<span data-ttu-id="732d7-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="732d7-123">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="732d7-124">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="732d7-124">Anti-phishing protection</span></span>|[<span data-ttu-id="732d7-125">EOP</span><span class="sxs-lookup"><span data-stu-id="732d7-125">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="732d7-126">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="732d7-126">Anti-spam protection</span></span>|[<span data-ttu-id="732d7-127">EOP</span><span class="sxs-lookup"><span data-stu-id="732d7-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="732d7-128">0 時間の自動削除 (電子メールの場合)</span><span class="sxs-lookup"><span data-stu-id="732d7-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="732d7-129">EOP</span><span class="sxs-lookup"><span data-stu-id="732d7-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="732d7-130">電子メールおよびドキュメント内の悪意のある URL とファイルOfficeからの保護 (セーフ リンクセーフ添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="732d7-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="732d7-131">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="732d7-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="732d7-132">ワークロードのセーフ、SharePoint、OneDriveの添付ファイルMicrosoft Teamsする</span><span class="sxs-lookup"><span data-stu-id="732d7-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="732d7-133">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="732d7-133">Microsoft Defender for Office 365</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="732d7-134">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="732d7-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="732d7-135">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="732d7-135">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="732d7-136">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="732d7-136">Roles and permissions</span></span>

<span data-ttu-id="732d7-137">Defender for Office 365 ポリシーを構成するには、セキュリティ コンプライアンス センターで適切な役割を割[り&必要があります](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="732d7-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="732d7-138">これらのアクションを実行できるロールについては、以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732d7-138">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="732d7-139">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="732d7-139">Role or role group</span></span>|<span data-ttu-id="732d7-140">詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="732d7-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="732d7-141">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="732d7-141">global administrator</span></span>|[<span data-ttu-id="732d7-142">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="732d7-142">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="732d7-143">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="732d7-143">Security Administrator</span></span>|[<span data-ttu-id="732d7-144">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="732d7-144">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="732d7-145">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="732d7-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="732d7-146">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="732d7-146">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="732d7-147">および</span><span class="sxs-lookup"><span data-stu-id="732d7-147">and</span></span> <p> [<span data-ttu-id="732d7-148">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="732d7-148">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="732d7-149">詳細については、「セキュリティ コンプライアンス センターのアクセス許可 [」&参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="732d7-150">開始する前に、[レポートと調査の監査ログ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="732d7-150">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="732d7-151">監査ログを早期に開始します。</span><span class="sxs-lookup"><span data-stu-id="732d7-151">Start your audit logging early.</span></span> <span data-ttu-id="732d7-152">次の手順の特定の場合は、 **監査をオン** にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="732d7-152">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="732d7-153">監査ログは、監査ログを含むサブスクリプション[Exchange Online。](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="732d7-153">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="732d7-154">セキュリティ ダッシュボード、電子メール セキュリティ レポート、エクスプローラーなどの脅威保護レポート [](view-email-security-reports.md)のデータを表示するには [](threat-explorer.md)、監査ログをオンにする必要 *があります*。 [](security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="732d7-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="732d7-155">詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="732d7-156">パート 1 - マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="732d7-156">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="732d7-157">[マルウェア対策保護は、EOP](anti-malware-protection.md) を含むサブスクリプションで [利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="732d7-157">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="732d7-158">[セキュリティ と [コンプライアンス &] で、[](https://protection.office.com)脅威 **管理** ポリシーマルウェア \> **対策** \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-158">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-malware**.</span></span>

2. <span data-ttu-id="732d7-159">[既定のポリシー] を **ダブルクリック** し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-159">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="732d7-160">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-160">Specify the following settings:</span></span>

    - <span data-ttu-id="732d7-161">[マルウェア **検出応答] セクション** で、既定の設定を **[いいえ**] のままにします。</span><span class="sxs-lookup"><span data-stu-id="732d7-161">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="732d7-162">[共通の **添付ファイルの種類フィルター] セクションで** 、[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-162">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="732d7-163">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-163">Click **Save**.</span></span>

<span data-ttu-id="732d7-164">マルウェア対策ポリシー オプションの詳細については、「マルウェア対策ポリシーを構成 [する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-164">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="732d7-165">パート 2 - フィッシング対策の保護</span><span class="sxs-lookup"><span data-stu-id="732d7-165">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="732d7-166">[フィッシング対策保護は、EOP](anti-phishing-protection.md) を含むサブスクリプションで [利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="732d7-166">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="732d7-167">高度なフィッシング対策保護は、Defender でセキュリティ保護[Office 365。](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="732d7-167">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="732d7-168">次の手順では、Microsoft Defender でフィッシング対策ポリシーを構成する方法について説明Office 365。</span><span class="sxs-lookup"><span data-stu-id="732d7-168">The following procedure describes how to configure an anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="732d7-169">EOP でフィッシング対策ポリシーを構成する手順は似ています。</span><span class="sxs-lookup"><span data-stu-id="732d7-169">The steps are similar for configuring an anti-phishing policy in EOP.</span></span>

1. <span data-ttu-id="732d7-170">[セキュリティ [管理&コンプライアンス センター] で、[](https://protection.office.com)脅威 **管理ポリシー** \> **の** \> **フィッシング対策] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="732d7-171">[既定 **のポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-171">Click **Default policy**.</span></span>

3. <span data-ttu-id="732d7-172">[偽装 **] セクションで** 、[編集] **をクリック** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="732d7-173">[保護する **ユーザーの追加] タブで** 、[保護を有効にする] *をオン* にします。</span><span class="sxs-lookup"><span data-stu-id="732d7-173">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="732d7-174">次に、組織の役員、CEO、CFO、その他の上級リーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="732d7-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="732d7-175">(個々の電子メール アドレスを入力するか、クリックしてリストを表示できます)。</span><span class="sxs-lookup"><span data-stu-id="732d7-175">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="732d7-176">[保護する **ドメインの追加] タブ** で、[所有するドメインを自動的に含める **] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="732d7-177">カスタム ドメインがある場合は、今すぐ追加します。</span><span class="sxs-lookup"><span data-stu-id="732d7-177">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="732d7-178">[操作 **] タブで**、[偽装されたユーザーと偽装されたドメイン オプションの両方についてメッセージ **を検疫する] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="732d7-178">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="732d7-179">また、偽装の安全に関するヒントも有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="732d7-179">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="732d7-180">[メールボックス **インテリジェンス] タブ** で、メールボックス インテリジェンスが有効になっていることを確認し、メールボックス インテリジェンス ベースの偽装保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="732d7-180">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="732d7-181">[偽装 **されたユーザーから電子メール** が送信された場合] ボックスの一覧で、[メッセージの **検疫] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-181">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="732d7-182">[信頼 **できる送信者とドメインの** 追加] タブで、追加する信頼できる送信者またはドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-182">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="732d7-183">**設定** を **確認した後、[** 設定の確認] タブに保存します。</span><span class="sxs-lookup"><span data-stu-id="732d7-183">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="732d7-184">[スプー **フィング]** セクションで、[編集] **をクリック** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-184">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="732d7-185">[ス **プーフィング フィルターの設定** ] タブで、スプーフィング対策保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="732d7-185">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="732d7-186">[操作] **タブで** 、[メッセージの **検疫] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-186">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="732d7-187">**変更** を確認 **した後、[設定の** 確認] タブに保存します。</span><span class="sxs-lookup"><span data-stu-id="732d7-187">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="732d7-188">(変更を加えなかった場合は、 **キャンセル** します。)</span><span class="sxs-lookup"><span data-stu-id="732d7-188">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="732d7-189">既定のポリシー設定ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="732d7-189">Close the default policy settings page.</span></span>

<span data-ttu-id="732d7-190">フィッシング対策ポリシー オプションの詳細については[、「Microsoft Defender for microsoft Defender for Office 365」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-190">To learn more about your anti-phishing policy options, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="732d7-191">パート 3 - スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="732d7-191">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="732d7-192">[スパム対策保護は、EOP](anti-spam-protection.md) を含むサブスクリプション [で利用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="732d7-192">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="732d7-193">セキュリティ 管理 [コンプライアンス センター&で、[](https://protection.office.com)脅威 **管理** ポリシースパム \> **対策** \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-193">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="732d7-194">**[カスタム]** タブで、[カスタム] 設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="732d7-194">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="732d7-195">[既定 **のスパム フィルター ポリシー] を展開** し、[ポリシー **の編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-195">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="732d7-196">**[迷惑メールおよびバルク メールの処理**] セクションで、しきい値を 5 または 6 に設定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-196">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="732d7-197">[許可 **リスト] セクション** で、許可されている送信者とドメインを確認 (および/または編集) します。</span><span class="sxs-lookup"><span data-stu-id="732d7-197">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="732d7-198">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-198">Click **Save**.</span></span>

<span data-ttu-id="732d7-199">スパム対策ポリシー オプションの詳細については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-199">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="732d7-200">パート 4 - 悪意のある URL とファイルからの保護 (セーフ Defender セーフの添付ファイルOffice 365)</span><span class="sxs-lookup"><span data-stu-id="732d7-200">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="732d7-201">悪意のある URL やファイルからのクリック時の保護は、Microsoft Defender for Office 365 を[含むサブスクリプションで利用できます](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="732d7-201">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="732d7-202">[添付ファイルとリンク][セーフポリシー](safe-attachments.md)セーフ[設定](safe-links.md)されます。</span><span class="sxs-lookup"><span data-stu-id="732d7-202">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="732d7-203">セーフMicrosoft Defender の添付ファイル ポリシー (Office 365</span><span class="sxs-lookup"><span data-stu-id="732d7-203">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="732d7-204">添付ファイルを[セーフするには](safe-attachments.md)、リンク ポリシーを少なくとも 1 セーフ作成します。</span><span class="sxs-lookup"><span data-stu-id="732d7-204">To set up [Safe Attachments](safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="732d7-205">セキュリティ コンプライアンス [センターで、[脅威&](https://protection.office.com)ポリシー  ATP] を選択し、[添付ファイルセーフ \>  \> 作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-205">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="732d7-206">表示される **[新しいセーフ添付** ファイル] ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="732d7-206">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="732d7-207">[名前] **ボックスに** 「」と `Block malware` 入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-207">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="732d7-208">[設定]**設定** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="732d7-208">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="732d7-209">[添付ファイル **のセーフ不明なマルウェアの応答] セクションで、[** ブロック] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-209">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="732d7-210">[添付ファイル **のリダイレクト] セクション** で、[リダイレクトを有効にする **] オプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-210">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="732d7-211">検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-211">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="732d7-212">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-212">Click **Next**.</span></span>

3. <span data-ttu-id="732d7-213">[適用先] ページ **で**、[条件の追加]をクリックし、[適用する場合] を選択します。[受信者ドメイン] をクリックし、[追加] をクリックして、ドメインまたはドメインを選択し、[**追加**] をクリックし、[完了] をクリックし、[次へ] をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="732d7-213">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="732d7-214">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-214">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="732d7-215">セーフMicrosoft Defender のリンク ポリシーをOffice 365</span><span class="sxs-lookup"><span data-stu-id="732d7-215">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="732d7-216">[リンク] を[セーフするには](safe-links.md)、リンクのグローバル設定を確認および編集し、セーフリンク ポリシーを 1 つ以上作成セーフします。</span><span class="sxs-lookup"><span data-stu-id="732d7-216">To set up [Safe Links](safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="732d7-217">[セキュリティ &[コンプライアンス](https://protection.office.com)センター]で、[脅威管理ポリシー ATP セーフ リンク] を選択し、[グローバル設定] をクリックし、次の設定 \>  \> を構成します。 </span><span class="sxs-lookup"><span data-stu-id="732d7-217">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="732d7-218">[**次のセーフリンクを使用する: Office 365が** オンになっていることを確認する: ![ トグルオン ](../../media/scc-toggle-on.png) です。</span><span class="sxs-lookup"><span data-stu-id="732d7-218">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="732d7-219">**ユーザーが [リンク] をクリックセーフ追跡** しない : この設定をオフにすると、ユーザーのクリックを追跡できます。[オフ] ![ を切り替えます ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="732d7-219">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="732d7-220">**ユーザーが元の URL への安全なリンク** をクリックさせない : この設定がオンになっていることを確認する: ![ トグルオン ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="732d7-220">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="732d7-221">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-221">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="732d7-222">[リンク] ページのメイン セーフに戻り、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-222">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="732d7-223">表示される **[セーフリンク** の作成] ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="732d7-223">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="732d7-224">[名前 **] ボックス** に名前を入力し、[次 `Safe Links` へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-224">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="732d7-225">[設定]**設定** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="732d7-225">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="732d7-226">**メッセージ内の不明な潜在的に悪意のある URL のアクションを選択します**。[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-226">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="732d7-227">**[オン] を選択して**、不明な URL または潜在的に悪意のある URL のMicrosoft Teamsを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-227">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="732d7-228">**組織内で送信された電子メール メッセージへの安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="732d7-228">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="732d7-229">**メッセージを配信する前に URL のスキャンが完了するのを待ちます**</span><span class="sxs-lookup"><span data-stu-id="732d7-229">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="732d7-230">**組織内で送信された電子メール メッセージへの安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="732d7-230">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="732d7-231">**ユーザーに元の URL へのクリックを許可しない**</span><span class="sxs-lookup"><span data-stu-id="732d7-231">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="732d7-232">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-232">Click **Next**</span></span>

4. <span data-ttu-id="732d7-233">[適用先] ページ **で**、[条件の追加]をクリックし、[適用する場合] を選択します。[受信者ドメイン] をクリックし、[追加] をクリックして、ドメインまたはドメインを選択し、[**追加**] をクリックし、[完了] をクリックし、[次へ] をクリックします。  </span><span class="sxs-lookup"><span data-stu-id="732d7-233">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="732d7-234">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-234">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="732d7-235">詳細については、「[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="732d7-235">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="732d7-236">パート 5 - セーフ、SharePoint、OneDrive、Microsoft Teamsが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="732d7-236">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="732d7-237">ワークロード (SharePoint、OneDrive、Teamsなど) は、コラボレーションのために構築されています。</span><span class="sxs-lookup"><span data-stu-id="732d7-237">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="732d7-238">Defender を使用Office 365、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別されるファイルのブロックと検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="732d7-238">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="732d7-239">その動作の詳細については、こちらを参照 [してください](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-239">You can read more about how that works [here](mdo-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="732d7-240">**この手順を開始する前に、** 監査ログがユーザー環境で既に有効になっていることをMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="732d7-240">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="732d7-241">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="732d7-241">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="732d7-242">詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-242">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="732d7-243">セキュリティ セキュリティ [コンプライアンス センター&、[](https://protection.office.com)脅威 **管理** ポリシー ATP と添付ファイル] を選択セーフ、[グローバル設定] を \>  \> **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-243">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="732d7-244">[Office 365、 SharePoint、OneDrive、および **Microsoft Teams** の Defender を有効にする] トグルが右にあるのを確認します。オンに切り替え、[ ![ 保存] を ](../../media/scc-toggle-on.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="732d7-244">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="732d7-245">組織の添付ファイル ポリシーとリンク ポリシーを確認[](set-up-safe-attachments-policies.md)(および、必要に応じてセーフ[セーフ](set-up-safe-links-policies.md)編集) します。</span><span class="sxs-lookup"><span data-stu-id="732d7-245">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-safe-attachments-policies.md) and [Safe Links policies](set-up-safe-links-policies.md).</span></span>

4. <span data-ttu-id="732d7-246">(推奨)グローバル管理者またはオンライン管理者 _SharePoint、DisallowInfectedFileDownload_ パラメーターをに設定して **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します `$true` 。</span><span class="sxs-lookup"><span data-stu-id="732d7-246">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="732d7-247">`$true` 検出されたファイルのすべてのアクション (削除を除く) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-247">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="732d7-248">検出されたファイルを開いたり、移動したり、コピーしたり、共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="732d7-248">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="732d7-249">`$false` 削除とダウンロードを除くすべてのアクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="732d7-249">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="732d7-250">ユーザーはリスクを受け入れ、検出されたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="732d7-250">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="732d7-251">PowerShell と一緒に PowerShell を使用する方法Microsoft 365、PowerShell を使用Microsoft 365[を参照してください](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-251">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).</span></span>

5. <span data-ttu-id="732d7-252">変更がすべてのデータ センターに広がり、最大 30 Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="732d7-252">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="732d7-253">検出されたファイルのアラートを設定する</span><span class="sxs-lookup"><span data-stu-id="732d7-253">Now set up alerts for detected files</span></span>

<span data-ttu-id="732d7-254">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるファイルとして識別された場合に通知を受信するには、アラートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="732d7-254">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="732d7-255">[セキュリティ 管理 [] コンプライアンス &で、[](https://protection.office.com)アラートの管理 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-255">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="732d7-256">[新 **しいアラート ポリシー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-256">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="732d7-257">アラートの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-257">Specify a name for the alert.</span></span> <span data-ttu-id="732d7-258">たとえば、「ライブラリ」に「悪意のあるファイル」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="732d7-258">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="732d7-259">アラートの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="732d7-259">Type a description for the alert.</span></span> <span data-ttu-id="732d7-260">たとえば、「オンライン、SharePoint、またはユーザーに悪意のあるファイルが検出された場合に管理者に通知OneDrive入力Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="732d7-260">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="732d7-261">[この **アラートをいつ送信....] セクションで** 、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="732d7-261">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="732d7-262">a.</span><span class="sxs-lookup"><span data-stu-id="732d7-262">a.</span></span> <span data-ttu-id="732d7-263">[アクティビティ] **リストで** 、[ファイル内 **の検出されたマルウェア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="732d7-263">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="732d7-264">b.</span><span class="sxs-lookup"><span data-stu-id="732d7-264">b.</span></span> <span data-ttu-id="732d7-265">[ユーザー] **フィールドは** 空のままにします。</span><span class="sxs-lookup"><span data-stu-id="732d7-265">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="732d7-266">[このアラート **を送信する....]** セクションで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ リーダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="732d7-266">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="732d7-267">**保存 .**</span><span class="sxs-lookup"><span data-stu-id="732d7-267">**Save**.</span></span>

<span data-ttu-id="732d7-268">アラートの詳細については、「セキュリティ コンプライアンス センターでアクティビティアラートを作成する [&する」を参照してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-268">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="732d7-269">構成が完了したら、次のリンクを使用してワークロード調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="732d7-269">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="732d7-270">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="732d7-270">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="732d7-271">セキュリティ コンプライアンス センターを&検疫済みファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="732d7-271">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="732d7-272">悪意のあるファイルがオンライン、オンライン、SharePoint、またはOneDriveにMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="732d7-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="732d7-273">検疫済みメッセージとファイルを管理者として管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="732d7-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="732d7-274">パート 6 - 構成する追加の設定</span><span class="sxs-lookup"><span data-stu-id="732d7-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="732d7-275">マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護を構成するとともに、0 時間の自動削除を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="732d7-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="732d7-276">EOP の電子メールの 0 時間自動削除</span><span class="sxs-lookup"><span data-stu-id="732d7-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="732d7-277">[ゼロ時間自動削除](zero-hour-auto-purge.md) (ZAP) は、EOP を含むサブスクリプションで [使用できます](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="732d7-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="732d7-278">この保護は既定でオンになっています。ただし、保護が有効になるには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="732d7-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="732d7-279">スパムアクションは、スパム \*\*対策ポリシーの [メッセージを迷惑\*\* メール フォルダーに移動 [する] に設定されています](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="732d7-280">ユーザーは既定の迷惑メール設定 [を保持](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)し、迷惑メール保護を無効にしていない。</span><span class="sxs-lookup"><span data-stu-id="732d7-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="732d7-281">詳細については、「ゼロ時間自動削除 - スパムとマルウェアに対 [する保護」を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="732d7-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="732d7-282">セットアップ後のタスクと次の手順</span><span class="sxs-lookup"><span data-stu-id="732d7-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="732d7-283">脅威保護機能を構成したら、それらの機能の動作を監視してください。</span><span class="sxs-lookup"><span data-stu-id="732d7-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="732d7-284">必要な操作を行うポリシーを確認して修正します。</span><span class="sxs-lookup"><span data-stu-id="732d7-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="732d7-285">また、価値を追加できる新機能やサービス更新プログラムを監視します。</span><span class="sxs-lookup"><span data-stu-id="732d7-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="732d7-286">操作</span><span class="sxs-lookup"><span data-stu-id="732d7-286">What to do</span></span>|<span data-ttu-id="732d7-287">追加情報</span><span class="sxs-lookup"><span data-stu-id="732d7-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="732d7-288">レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する</span><span class="sxs-lookup"><span data-stu-id="732d7-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="732d7-289">セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="732d7-289">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="732d7-290">電子メール セキュリティ レポート</span><span class="sxs-lookup"><span data-stu-id="732d7-290">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="732d7-291">Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="732d7-291">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="732d7-292">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="732d7-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="732d7-293">必要に応じて、脅威保護ポリシーを定期的に確認および修正する</span><span class="sxs-lookup"><span data-stu-id="732d7-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="732d7-294">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="732d7-294">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="732d7-295">スマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="732d7-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="732d7-296">Microsoft 365の調査と対応の機能</span><span class="sxs-lookup"><span data-stu-id="732d7-296">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="732d7-297">新機能とサービス更新プログラムを監視する</span><span class="sxs-lookup"><span data-stu-id="732d7-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="732d7-298">標準リリースオプションとターゲット リリース オプション</span><span class="sxs-lookup"><span data-stu-id="732d7-298">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="732d7-299">Message Center</span><span class="sxs-lookup"><span data-stu-id="732d7-299">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="732d7-300">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="732d7-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="732d7-301">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="732d7-301">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="732d7-302">EOP および Defender の推奨される Standard および Strict セキュリティ構成の詳細については、Office 365</span><span class="sxs-lookup"><span data-stu-id="732d7-302">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="732d7-303">EOP と Microsoft Defender のセキュリティに関するOffice 365設定</span><span class="sxs-lookup"><span data-stu-id="732d7-303">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)|
