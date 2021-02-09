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
description: 管理者は、Microsoft 365 の脅威保護について学習し、組織で使用する方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb2866fd3e60c021ae89ffabe7149f4b415d63bc
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150714"
---
# <a name="protect-against-threats"></a><span data-ttu-id="8e870-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="8e870-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8e870-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="8e870-104">**Applies to**</span></span>
- [<span data-ttu-id="8e870-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e870-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="8e870-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="8e870-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="8e870-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e870-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8e870-108">365 用の Defender の構成をチャンクに分割するクイック Officeを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e870-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="8e870-109">Office 365 の脅威保護機能を初めから使用する場合は、どこから開始する必要があるのか分からず、最適な方法で学習する場合は、チェックリストと開始点としてこのガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e870-110">**初期推奨設定はポリシー** の種類ごとに含まれていますが、多くのオプションを使用できます。また、組織の特定のニーズに合わせて設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e870-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="8e870-111">ポリシーまたは変更がデータセンターを経由して機能するには、約 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="8e870-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e870-112">要件</span><span class="sxs-lookup"><span data-stu-id="8e870-112">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="8e870-113">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="8e870-113">Subscriptions</span></span>

<span data-ttu-id="8e870-114">脅威保護機能は、すべての Microsoft *または* Office 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには高度な機能があります。</span><span class="sxs-lookup"><span data-stu-id="8e870-114">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="8e870-115">次の表に、この記事に含まれる保護機能と、最小サブスクリプション要件を示します。</span><span class="sxs-lookup"><span data-stu-id="8e870-115">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="8e870-116">監査を有効にする指示以外にも、Office 365 Exchange Online Protection **(EOP)** の一部としてマークされているマルウェア対策、フィッシング対策、スパム対策が開始されます。 </span><span class="sxs-lookup"><span data-stu-id="8e870-116">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="8e870-117">これは、Defender for Office 365 の記事では **、(Office 365** 用 Defender) に EOP が含まれていると、EOP に基が構築されるまで、奇数に思える場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e870-117">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="8e870-118">保護の種類</span><span class="sxs-lookup"><span data-stu-id="8e870-118">Protection type</span></span>|<span data-ttu-id="8e870-119">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="8e870-119">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="8e870-120">監査ログ (レポート用)</span><span class="sxs-lookup"><span data-stu-id="8e870-120">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="8e870-121">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e870-121">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="8e870-122">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-122">Anti-malware protection</span></span>|<span data-ttu-id="8e870-123">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="8e870-123">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="8e870-124">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-124">Anti-phishing protection</span></span>|[<span data-ttu-id="8e870-125">EOP</span><span class="sxs-lookup"><span data-stu-id="8e870-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8e870-126">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-126">Anti-spam protection</span></span>|[<span data-ttu-id="8e870-127">EOP</span><span class="sxs-lookup"><span data-stu-id="8e870-127">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8e870-128">ゼロアワー自動消去 (メール用)</span><span class="sxs-lookup"><span data-stu-id="8e870-128">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="8e870-129">EOP</span><span class="sxs-lookup"><span data-stu-id="8e870-129">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8e870-130">電子メールやドキュメント内の悪意のある URL やファイルOffice (安全なリンクと安全な添付ファイル) からの保護</span><span class="sxs-lookup"><span data-stu-id="8e870-130">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|[<span data-ttu-id="8e870-131">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8e870-131">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="8e870-132">SharePoint、OneDrive、Microsoft Teams ワークロードの安全な添付ファイルを有効にする</span><span class="sxs-lookup"><span data-stu-id="8e870-132">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="8e870-133">Defender for Office 365 </span><span class="sxs-lookup"><span data-stu-id="8e870-133">Defender for Office 365 </span></span>](atp-for-spo-odb-and-teams.md)|
|<span data-ttu-id="8e870-134">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-134">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="8e870-135">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8e870-135">Defender for Office 365</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="8e870-136">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="8e870-136">Roles and permissions</span></span>

<span data-ttu-id="8e870-137">Office 365 ポリシー用に Defender を構成するには、セキュリティ/コンプライアンス センターで適切な [役割&必要があります](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="8e870-137">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="8e870-138">これらのアクションを実行できるロールについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-138">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="8e870-139">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="8e870-139">Role or role group</span></span>|<span data-ttu-id="8e870-140">詳細については、次の場所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-140">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="8e870-141">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8e870-141">global administrator</span></span>|[<span data-ttu-id="8e870-142">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="8e870-142">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="8e870-143">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8e870-143">Security Administrator</span></span>|[<span data-ttu-id="8e870-144">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8e870-144">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="8e870-145">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="8e870-145">Exchange Online Organization Management</span></span>|[<span data-ttu-id="8e870-146">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8e870-146">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="8e870-147">および</span><span class="sxs-lookup"><span data-stu-id="8e870-147">and</span></span> <p> [<span data-ttu-id="8e870-148">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e870-148">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="8e870-149">詳細については、セキュリティ/コンプライアンス [センターの「アクセス許可&参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-149">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="8e870-150">始める前に、レポートと調査の監査ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8e870-150">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="8e870-151">監査ログを早期に開始します。</span><span class="sxs-lookup"><span data-stu-id="8e870-151">Start your audit logging early.</span></span> <span data-ttu-id="8e870-152">次の特定の手順で監査を **有効** にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e870-152">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="8e870-153">監査ログは、Exchange Online を含むサブスクリプション [で使用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8e870-153">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="8e870-154">セキュリティ ダッシュボード、メール セキュリティ レポート、エクスプローラーなどの脅威 [](security-dashboard.md)保護レポートのデータを表示するには、[](threat-explorer.md)監査ログをオンにする必要 *があります*。 [](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="8e870-154">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="8e870-155">詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-155">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="8e870-156">パート 1 - マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-156">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="8e870-157">[マルウェア対策保護は、EOP](anti-malware-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8e870-157">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8e870-158">セキュリティ/ [コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシーの** \> **マルウェア対策** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-158">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-malware**.</span></span>

2. <span data-ttu-id="8e870-159">既定のポリシーを **ダブルクリックし** 、設定を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-159">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="8e870-160">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-160">Specify the following settings:</span></span>

    - <span data-ttu-id="8e870-161">[マルウェア検出 **応答] セクション** で、既定の設定 [いいえ] のままに **します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-161">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="8e870-162">[共通の **添付ファイルの種類フィルター] セクションで** 、[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-162">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="8e870-163">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-163">Click **Save**.</span></span>

<span data-ttu-id="8e870-164">マルウェア対策ポリシー オプションの詳細については、「マルウェア対策ポリシーを構成 [する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-164">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="8e870-165">パート 2 - フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-165">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="8e870-166">[フィッシング対策保護は、EOP](anti-phishing-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8e870-166">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8e870-167">高度なフィッシング対策保護は、Defender で Office [365 で利用できます](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8e870-167">Advanced anti-phishing protection is available in [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="8e870-168">次の手順では、Microsoft Defender でフィッシング対策ポリシーを Office 365 に構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e870-168">The following procedure describes how to configure an anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8e870-169">手順は、EOP でフィッシング対策ポリシーを構成する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="8e870-169">The steps are similar for configuring an anti-phishing policy in EOP.</span></span>

1. <span data-ttu-id="8e870-170">セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシー** ATP フィッシング対策 \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8e870-171">[既定 **のポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8e870-171">Click **Default policy**.</span></span>

3. <span data-ttu-id="8e870-172">[偽装 **] セクションで、[** 編集] **をクリック** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8e870-173">[保護する **ユーザーの追加] タブで** 、[保護を有効にする] *をオン* にします。</span><span class="sxs-lookup"><span data-stu-id="8e870-173">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="8e870-174">次に、組織の役員、CEO、CFO、その他の上級リーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8e870-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="8e870-175">(個々のメール アドレスを入力するか、クリックしてリストを表示できます)。</span><span class="sxs-lookup"><span data-stu-id="8e870-175">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="8e870-176">On the **Add domains to protect** tab, turn on Automatically include the **domains I own**.</span><span class="sxs-lookup"><span data-stu-id="8e870-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="8e870-177">カスタム ドメインがある場合は、ここで追加します。</span><span class="sxs-lookup"><span data-stu-id="8e870-177">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="8e870-178">[操作 **] タブで**、偽装したユーザーと偽装されたドメイン の両方のオプションのメッセージ **を検疫するを選択** します。</span><span class="sxs-lookup"><span data-stu-id="8e870-178">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="8e870-179">また、偽装安全性のヒントも有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="8e870-179">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="8e870-180">[メールボックス インテリジェンス **] タブ** で、メールボックス インテリジェンスが有効になっていることを確認し、メールボックス インテリジェンス ベースの偽装保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8e870-180">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="8e870-181">In the **If email is sent by an impersonated user** list, choose Quarantine the **message**.</span><span class="sxs-lookup"><span data-stu-id="8e870-181">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8e870-182">[信頼 **できる送信者と** ドメインの追加] タブで、追加する信頼できる送信者またはドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-182">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="8e870-183">**設定** を **確認した後、[** 設定の確認] タブに保存します。</span><span class="sxs-lookup"><span data-stu-id="8e870-183">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="8e870-184">[ **スプーフィング]** セクションで [編集 **] をクリック** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-184">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8e870-185">[ **スプーフィング フィルターの設定** ] タブで、スプーフィング対策保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e870-185">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="8e870-186">[操作 **] タブで** 、[メッセージの **検疫] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-186">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8e870-187">**変更** を **確認した後、[** 設定の確認] タブに保存します。</span><span class="sxs-lookup"><span data-stu-id="8e870-187">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="8e870-188">(If you didn't make any changes, **Cancel**.)</span><span class="sxs-lookup"><span data-stu-id="8e870-188">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="8e870-189">既定のポリシー設定ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8e870-189">Close the default policy settings page.</span></span>

<span data-ttu-id="8e870-190">フィッシング対策ポリシー オプションの詳細については [、「Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)でのフィッシング対策ポリシーの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-190">To learn more about your anti-phishing policy options, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="8e870-191">パート 3 - スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8e870-191">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="8e870-192">[スパム対策保護は、EOP](anti-spam-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8e870-192">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8e870-193">セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシーのスパム** 対策 \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-193">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8e870-194">[カスタム] **タブ** で、[カスタム設定] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8e870-194">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="8e870-195">[既定 **のスパム フィルター ポリシー] を展開し、[\*\*\*\*ポリシーの** 編集] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-195">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8e870-196">[スパム **と一括アクション** ] セクションで、しきい値を 5 または 6 に設定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-196">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="8e870-197">[許可 **リスト] セクション** で、許可された送信者とドメインを確認 (または編集) します。</span><span class="sxs-lookup"><span data-stu-id="8e870-197">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="8e870-198">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-198">Click **Save**.</span></span>

<span data-ttu-id="8e870-199">スパム対策ポリシー オプションの詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-199">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="8e870-200">パート 4 - 悪意のある URL とファイルからの保護 (Defender for Office 365 の安全なリンクと安全な添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="8e870-200">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="8e870-201">悪意のある URL やファイルからのクリック時の保護は、Microsoft [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8e870-201">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="8e870-202">これは、安全な添付ファイル[と安全なリンクの](atp-safe-attachments.md)[ポリシーを使用して](atp-safe-links.md)設定されます。</span><span class="sxs-lookup"><span data-stu-id="8e870-202">It's set up through [Safe Attachments](atp-safe-attachments.md) and [Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8e870-203">Microsoft Defender for Office 365 の安全な添付ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="8e870-203">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8e870-204">安全な添付ファイル [を設定するには](atp-safe-attachments.md)、少なくとも 1 つの安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e870-204">To set up [Safe Attachments](atp-safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="8e870-205">セキュリティ/[コンプライアンス センターで&](https://protection.office.com)管理ポリシー ATP の安全な添付ファイルを選択し、[作成] \>  \> をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-205">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="8e870-206">表示される **安全な添付ファイルの新** しいポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e870-206">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8e870-207">[名前 **] ボックスに** 「次へ」 `Block malware` と入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8e870-207">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="8e870-208">[設定 **] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e870-208">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="8e870-209">[安全な **添付ファイル] の [不明なマルウェアの応答** ] セクションで、[ブロック] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-209">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="8e870-210">[添付ファイル **のリダイレクト] セクション** で、[リダイレクトを有効にする] **オプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-210">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="8e870-211">検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-211">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="8e870-212">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-212">Click **Next**.</span></span>

3. <span data-ttu-id="8e870-213">On the **Applied to** page, click **A condition,** choose **Applied if: The recipient domain is,** click **Add,** select your domains, click **Add,** click **Done,** and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8e870-213">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="8e870-214">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8e870-214">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8e870-215">Microsoft Defender for Office 365 の安全なリンク ポリシー</span><span class="sxs-lookup"><span data-stu-id="8e870-215">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8e870-216">安全なリンク [を設定するには](atp-safe-links.md)、安全なリンクのグローバル設定を確認および編集し、少なくとも 1 つの安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8e870-216">To set up [Safe Links](atp-safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="8e870-217">セキュリティ &[コンプライアンス](https://protection.office.com)センターで、[脅威 **管理** ポリシー ATP の安全なリンク] を選択し、[グローバル設定] をクリックして、次の \>  \> 設定を構成します。 </span><span class="sxs-lookup"><span data-stu-id="8e870-217">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="8e870-218">Verify **Use Safe Links in: Office 365 applications** is turned on: Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="8e870-218">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="8e870-219">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: Toggle off ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="8e870-219">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="8e870-220">**ユーザーが元の URL への安全な** リンクをクリックさせない: この設定がオンになっていることを確認します:オンに切り ![ 替え ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="8e870-220">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="8e870-221">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-221">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="8e870-222">メインの [安全なリンク] ページに戻り、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8e870-222">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="8e870-223">表示される **安全なリンクの作成** ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e870-223">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8e870-224">[名前 **] ボックス** に名前を入力し、[次へ] `Safe Links` をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-224">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="8e870-225">[設定 **] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8e870-225">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="8e870-226">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span><span class="sxs-lookup"><span data-stu-id="8e870-226">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="8e870-227">**Microsoft Teams 内の不明な URL または悪意のある** 可能性のある URL に対するアクションを選択します。[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-227">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="8e870-228">**組織内で送信される電子メール メッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="8e870-228">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="8e870-229">**メッセージを配信する前に URL のスキャンが完了するのを待つ**</span><span class="sxs-lookup"><span data-stu-id="8e870-229">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="8e870-230">**組織内で送信される電子メール メッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="8e870-230">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="8e870-231">**ユーザーがクリックして元の URL にアクセスできない**</span><span class="sxs-lookup"><span data-stu-id="8e870-231">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="8e870-232">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-232">Click **Next**</span></span>

4. <span data-ttu-id="8e870-233">On the **Applied to** page, click **A condition,** choose **Applied if: The recipient domain is,** click **Add,** select your domains, click **Add,** click **Done,** and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8e870-233">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="8e870-234">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8e870-234">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="8e870-235">詳細については、「[安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8e870-235">To learn more, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="8e870-236">パート 5 - SharePoint、OneDrive、Microsoft Teams の安全な添付ファイルが有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8e870-236">Part 5 - Verify Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="8e870-237">SharePoint、OneDrive、Teams のようなワークロードは、コラボレーション用に構築されています。</span><span class="sxs-lookup"><span data-stu-id="8e870-237">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="8e870-238">Defender を Office 365 に使用すると、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別されたファイルをブロックおよび検出できます。</span><span class="sxs-lookup"><span data-stu-id="8e870-238">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="8e870-239">この機能の詳細については、以下を参照 [してください](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-239">You can read more about how that works [here](atp-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e870-240">**この手順を開始する前に、Microsoft 365** 環境で監査ログが既に有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-240">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="8e870-241">これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="8e870-241">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="8e870-242">詳細については、「監査ログ [検索を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-242">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="8e870-243">セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理** ポリシー ATP の安全な添付ファイルを選択し、[グローバル設定] \>  \> を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8e870-243">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="8e870-244">**[SharePoint、OneDrive、Microsoft Teams の Office 365** の Defender を有効にする] トグルが右側に表示されるのを確認します。オンに切り替え、[保存] をクリック ![ ](../../media/scc-toggle-on.png) **します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-244">Verify the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="8e870-245">組織の安全な添付ファイル ポリシーと安全なリンク ポリシーを [確認](set-up-atp-safe-attachments-policies.md) (および必要に応じて編集) [します](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-245">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

4. <span data-ttu-id="8e870-246">(推奨)全体管理者または SharePoint Online 管理者として _、DisallowInfectedFileDownload_ パラメーターを設定して **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します `$true` 。</span><span class="sxs-lookup"><span data-stu-id="8e870-246">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="8e870-247">`$true` 検出されたファイルのすべてのアクション (Delete を除く) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-247">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="8e870-248">検出されたファイルを開いたり、移動したり、コピーしたり、共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8e870-248">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="8e870-249">`$false` Delete および Download 以外のすべてのアクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8e870-249">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="8e870-250">ユーザーはリスクを受け入れて、検出されたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8e870-250">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="8e870-251">Microsoft 365 で PowerShell を使用する方法の詳細については、「PowerShell を使用して [Microsoft 365 を管理](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-251">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

5. <span data-ttu-id="8e870-252">変更がすべての Microsoft 365 データセンターに分散するために最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="8e870-252">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="8e870-253">検出されたファイルのアラートを設定する</span><span class="sxs-lookup"><span data-stu-id="8e870-253">Now set up alerts for detected files</span></span>

<span data-ttu-id="8e870-254">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるファイルとして識別された場合に通知を受け取る場合は、アラートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8e870-254">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="8e870-255">セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラートの **管理を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-255">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="8e870-256">[新 **しいアラート ポリシー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-256">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="8e870-257">通知の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-257">Specify a name for the alert.</span></span> <span data-ttu-id="8e870-258">たとえば、「ライブラリ」に「悪意のあるファイル」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8e870-258">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="8e870-259">アラートの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8e870-259">Type a description for the alert.</span></span> <span data-ttu-id="8e870-260">たとえば、SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に、管理者に通知を入力できます。</span><span class="sxs-lookup"><span data-stu-id="8e870-260">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="8e870-261">[この通知 **をいつ送信する...] セクションで** 、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8e870-261">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="8e870-262">a.</span><span class="sxs-lookup"><span data-stu-id="8e870-262">a.</span></span> <span data-ttu-id="8e870-263">[アクティビティ **] ボックスの** 一覧で、[ **ファイル内の検出されたマルウェア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-263">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="8e870-264">b.</span><span class="sxs-lookup"><span data-stu-id="8e870-264">b.</span></span> <span data-ttu-id="8e870-265">[ユーザー **] フィールドは** 空のままにします。</span><span class="sxs-lookup"><span data-stu-id="8e870-265">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="8e870-266">[この警告の送信場所 **...]** セクションで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 人または複数のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e870-266">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="8e870-267">**保存します**。</span><span class="sxs-lookup"><span data-stu-id="8e870-267">**Save**.</span></span>

<span data-ttu-id="8e870-268">アラートの詳細については、セキュリティ/コンプライアンス センターの「アクティビティアラート& [参照してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-268">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8e870-269">構成が完了したら、次のリンクを使用してワークロードの調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="8e870-269">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="8e870-270">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="8e870-270">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="8e870-271">セキュリティ/コンプライアンス センター&使用して検疫済みファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="8e870-271">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="8e870-272">SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが見つかった場合の対応方法</span><span class="sxs-lookup"><span data-stu-id="8e870-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="8e870-273">Microsoft 365 で管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="8e870-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="8e870-274">パート 6 - 構成する追加設定</span><span class="sxs-lookup"><span data-stu-id="8e870-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="8e870-275">マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護を構成するとともに、ゼロアワー自動消去を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8e870-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="8e870-276">EOP での電子メールのゼロアワー自動消去</span><span class="sxs-lookup"><span data-stu-id="8e870-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="8e870-277">[ゼロアワー自動消去](zero-hour-auto-purge.md) (ZAP) は [、EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8e870-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8e870-278">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e870-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="8e870-279">スパム対策アクションは、スパム \*\*対策ポリシーで [メッセージを迷惑メール\*\* フォルダー [に移動する] に設定されています](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="8e870-280">ユーザーは、既定の迷惑メール [設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持し、迷惑メール保護をオフにしていない。</span><span class="sxs-lookup"><span data-stu-id="8e870-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="8e870-281">詳細については、「ゼロアワー自動消去 - スパムやマルウェアに対する [保護」を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="8e870-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="8e870-282">セットアップ後のタスクと次の手順</span><span class="sxs-lookup"><span data-stu-id="8e870-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="8e870-283">脅威保護機能を構成したら、それらの機能の動作を監視してください。</span><span class="sxs-lookup"><span data-stu-id="8e870-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="8e870-284">必要に応じてポリシーを確認および修正します。</span><span class="sxs-lookup"><span data-stu-id="8e870-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="8e870-285">また、価値を高め得る新機能やサービス更新プログラムを監視します。</span><span class="sxs-lookup"><span data-stu-id="8e870-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="8e870-286">操作</span><span class="sxs-lookup"><span data-stu-id="8e870-286">What to do</span></span>|<span data-ttu-id="8e870-287">追加情報</span><span class="sxs-lookup"><span data-stu-id="8e870-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="8e870-288">レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する</span><span class="sxs-lookup"><span data-stu-id="8e870-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="8e870-289">セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8e870-289">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="8e870-290">電子メール セキュリティ レポート</span><span class="sxs-lookup"><span data-stu-id="8e870-290">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="8e870-291">Microsoft Defender for Office 365 のレポート</span><span class="sxs-lookup"><span data-stu-id="8e870-291">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md) <p> [<span data-ttu-id="8e870-292">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="8e870-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="8e870-293">必要に応じて脅威保護ポリシーを定期的に確認および修正する</span><span class="sxs-lookup"><span data-stu-id="8e870-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="8e870-294">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="8e870-294">Secure Score</span></span>](../mtp/microsoft-secure-score.md) <p> [<span data-ttu-id="8e870-295">スマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="8e870-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="8e870-296">Microsoft 365 脅威の調査と対応の機能</span><span class="sxs-lookup"><span data-stu-id="8e870-296">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="8e870-297">新機能とサービス更新プログラムを監視する</span><span class="sxs-lookup"><span data-stu-id="8e870-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="8e870-298">標準と対象指定のリリース オプション</span><span class="sxs-lookup"><span data-stu-id="8e870-298">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [<span data-ttu-id="8e870-299">Message Center</span><span class="sxs-lookup"><span data-stu-id="8e870-299">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [<span data-ttu-id="8e870-300">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="8e870-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="8e870-301">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="8e870-301">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="8e870-302">EOP および Defender for Office 365 の推奨される Standard および Strict セキュリティ構成の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e870-302">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="8e870-303">EOP と Microsoft Defender の 365 セキュリティOffice推奨設定</span><span class="sxs-lookup"><span data-stu-id="8e870-303">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)|
