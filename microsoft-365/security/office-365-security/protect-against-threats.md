---
title: 脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
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
ms.openlocfilehash: 2951d5725237d572d357ac3fc6cff0ac4df7e8f0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794438"
---
# <a name="protect-against-threats"></a><span data-ttu-id="8ecb9-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8ecb9-104">ここでは、365 用の Defender の構成をチャンクに分割するクイック スタート Office示します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-104">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="8ecb9-105">Office 365 の脅威保護機能を初めから使用する場合は、どこから開始する必要があるのか分からず、最適な方法で学習する場合は、チェックリストと開始点としてこのガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ecb9-106">**初期推奨設定はポリシー** の種類ごとに含まれていますが、多くのオプションを使用できます。また、組織の特定のニーズに合わせて設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="8ecb9-107">ポリシーまたは変更がデータセンターを経由して機能するには、約 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="8ecb9-108">要件</span><span class="sxs-lookup"><span data-stu-id="8ecb9-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="8ecb9-109">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="8ecb9-109">Subscriptions</span></span>

<span data-ttu-id="8ecb9-110">脅威保護機能は、すべての Microsoft *または* Office 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには高度な機能があります。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="8ecb9-111">次の表に、この記事に含まれる保護機能と、最小サブスクリプション要件を示します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="8ecb9-112">監査を有効にする指示以外にも、Office 365 Exchange Online Protection **(EOP)** の一部としてマークされているマルウェア対策、フィッシング対策、スパム対策が開始されます。 </span><span class="sxs-lookup"><span data-stu-id="8ecb9-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="8ecb9-113">これは、Defender for Office 365 の記事では **、(Office 365** 用 Defender) に EOP が含まれていると、EOP に基が構築されるまで、奇数に思える場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-113">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="8ecb9-114">保護の種類</span><span class="sxs-lookup"><span data-stu-id="8ecb9-114">Protection type</span></span>|<span data-ttu-id="8ecb9-115">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="8ecb9-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="8ecb9-116">監査ログ (レポート用)</span><span class="sxs-lookup"><span data-stu-id="8ecb9-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="8ecb9-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8ecb9-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="8ecb9-118">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-118">Anti-malware protection</span></span>|<span data-ttu-id="8ecb9-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="8ecb9-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="8ecb9-120">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-120">Anti-phishing protection</span></span>|[<span data-ttu-id="8ecb9-121">EOP</span><span class="sxs-lookup"><span data-stu-id="8ecb9-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8ecb9-122">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-122">Anti-spam protection</span></span>|[<span data-ttu-id="8ecb9-123">EOP</span><span class="sxs-lookup"><span data-stu-id="8ecb9-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8ecb9-124">ゼロアワー自動消去 (メール用)</span><span class="sxs-lookup"><span data-stu-id="8ecb9-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="8ecb9-125">EOP</span><span class="sxs-lookup"><span data-stu-id="8ecb9-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8ecb9-126">電子メールやドキュメント内の悪意のある URL やファイルOffice (安全なリンクと安全な添付ファイル) からの保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|[<span data-ttu-id="8ecb9-127">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8ecb9-127">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="8ecb9-128">SharePoint、OneDrive、Microsoft Teams のワークロードに対して ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="8ecb9-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="8ecb9-129">Defender for Office 365 </span><span class="sxs-lookup"><span data-stu-id="8ecb9-129">Defender for Office 365 </span></span>](atp-for-spo-odb-and-teams.md)|
|<span data-ttu-id="8ecb9-130">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="8ecb9-131">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8ecb9-131">Defender for Office 365</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="8ecb9-132">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="8ecb9-132">Roles and permissions</span></span>

<span data-ttu-id="8ecb9-133">Office 365 ポリシー用に Defender を構成するには、セキュリティ/コンプライアンス センターで適切な [役割&必要があります](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-133">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="8ecb9-134">これらのアクションを実行できるロールについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="8ecb9-135">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="8ecb9-135">Role or role group</span></span>|<span data-ttu-id="8ecb9-136">詳細については、次の場所を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="8ecb9-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8ecb9-137">global administrator</span></span>|[<span data-ttu-id="8ecb9-138">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="8ecb9-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="8ecb9-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8ecb9-139">Security Administrator</span></span>|[<span data-ttu-id="8ecb9-140">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ecb9-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="8ecb9-141">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="8ecb9-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="8ecb9-142">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ecb9-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="8ecb9-143">および</span><span class="sxs-lookup"><span data-stu-id="8ecb9-143">and</span></span> <p> [<span data-ttu-id="8ecb9-144">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ecb9-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="8ecb9-145">詳細については、セキュリティ/コンプライアンス [センターの「アクセス許可&参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-145">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="8ecb9-146">始める前に、レポートと調査の監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="8ecb9-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="8ecb9-147">監査ログを早期に開始します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-147">Start your audit logging early.</span></span> <span data-ttu-id="8ecb9-148">次の手順の **特定の場合** は、監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="8ecb9-149">監査ログは、Exchange Online を含むサブスクリプション [で使用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="8ecb9-150">セキュリティ ダッシュボード、メール セキュリティ レポート、エクスプローラーなどの脅威 [](security-dashboard.md)保護レポートのデータを表示するには、[](threat-explorer.md)監査ログをオンにする必要 *があります*。 [](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="8ecb9-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="8ecb9-151">詳細については、「監査ログ [検索を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="8ecb9-152">パート 1 - マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="8ecb9-153">[マルウェア対策保護は、EOP](anti-malware-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8ecb9-154">セキュリティ/ [コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシーの** \> **マルウェア対策** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-malware**.</span></span>

2. <span data-ttu-id="8ecb9-155">既定のポリシーを **ダブルクリックし** 、設定を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="8ecb9-156">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-156">Specify the following settings:</span></span>

    - <span data-ttu-id="8ecb9-157">[マルウェア検出 **応答] セクション** で、既定の設定 [いいえ] のままに **します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="8ecb9-158">[共通の **添付ファイルの種類フィルター] セクションで** 、[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="8ecb9-159">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-159">Click **Save**.</span></span>

<span data-ttu-id="8ecb9-160">マルウェア対策ポリシー オプションの詳細については、「マルウェア対策ポリシーを構成 [する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="8ecb9-161">パート 2 - フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="8ecb9-162">[フィッシング対策保護は、EOP](anti-phishing-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-162">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8ecb9-163">高度なフィッシング対策保護は、Defender で Office [365 で利用できます](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-163">Advanced anti-phishing protection is available in [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="8ecb9-164">次の手順では、Microsoft Defender でフィッシング対策ポリシーを Office 365 に構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-164">The following procedure describes how to configure an anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8ecb9-165">手順は、EOP でフィッシング対策ポリシーを構成する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-165">The steps are similar for configuring an anti-phishing policy in EOP.</span></span>

1. <span data-ttu-id="8ecb9-166">セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシー** ATP フィッシング対策 \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-166">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8ecb9-167">[既定 **のポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-167">Click **Default policy**.</span></span>

3. <span data-ttu-id="8ecb9-168">[偽装 **] セクションで、[** 編集] **をクリック** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-168">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8ecb9-169">[保護する **ユーザーの追加] タブで** 、[保護を有効にする] *をオン* にします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-169">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="8ecb9-170">次に、組織の役員、CEO、CFO、その他の上級リーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-170">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="8ecb9-171">(個々のメール アドレスを入力するか、クリックしてリストを表示できます)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-171">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="8ecb9-172">On the **Add domains to protect** tab, turn on Automatically include the **domains I own**.</span><span class="sxs-lookup"><span data-stu-id="8ecb9-172">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="8ecb9-173">カスタム ドメインがある場合は、ここで追加します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-173">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="8ecb9-174">[操作 **] タブで**、偽装したユーザーと偽装されたドメイン の両方のオプションのメッセージ **を検疫するを選択** します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-174">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="8ecb9-175">また、偽装安全性のヒントも有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-175">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="8ecb9-176">[メールボックス **インテリジェンス] タブ** で、メールボックス インテリジェンスが有効になっていることを確認し、メールボックス インテリジェンス ベースの偽装保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-176">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="8ecb9-177">In the **If email is sent by an impersonated user** list, choose Quarantine the **message**.</span><span class="sxs-lookup"><span data-stu-id="8ecb9-177">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8ecb9-178">[信頼 **できる送信者と** ドメインの追加] タブで、追加する信頼できる送信者またはドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-178">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="8ecb9-179">**設定** を **確認した後、[** 設定の確認] タブに保存します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-179">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="8ecb9-180">[ **スプーフィング]** セクションで、[編集 **] をクリック** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-180">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8ecb9-181">[ **スプーフィング フィルターの設定** ] タブで、スプーフィング対策保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-181">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="8ecb9-182">[操作 **] タブで** 、[メッセージの **検疫] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-182">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8ecb9-183">**変更** を **確認した後、[設定の** 確認] タブに保存します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-183">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="8ecb9-184">(If you didn't make any changes, **Cancel**.)</span><span class="sxs-lookup"><span data-stu-id="8ecb9-184">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="8ecb9-185">既定のポリシー設定ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-185">Close the default policy settings page.</span></span>

<span data-ttu-id="8ecb9-186">フィッシング対策ポリシー オプションの詳細については、「Microsoft Defender for Office [365](configure-atp-anti-phishing-policies.md)でのフィッシング対策ポリシーの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-186">To learn more about your anti-phishing policy options, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="8ecb9-187">パート 3 - スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8ecb9-187">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="8ecb9-188">[スパム対策保護は、EOP](anti-spam-protection.md) を含むサブスクリプションで [利用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-188">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8ecb9-189">セキュリティ/[コンプライアンス センター&、](https://protection.office.com)脅威 **管理ポリシーのスパム** 対策 \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-189">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8ecb9-190">[カスタム] **タブ** で、[カスタム設定] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-190">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="8ecb9-191">[既定 **のスパム フィルター ポリシー] を展開し、[\*\*\*\*ポリシーの** 編集] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-191">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8ecb9-192">[スパム **と一括アクション** ] セクションで、しきい値を 5 または 6 に設定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-192">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="8ecb9-193">[許可 **リスト] セクション** で、許可された送信者とドメインを確認 (または編集) します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-193">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="8ecb9-194">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-194">Click **Save**.</span></span>

<span data-ttu-id="8ecb9-195">スパム対策ポリシー オプションの詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-195">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="8ecb9-196">パート 4 - 悪意のある URL とファイルからの保護 (Defender の安全なリンクと安全な添付ファイル Office 365)</span><span class="sxs-lookup"><span data-stu-id="8ecb9-196">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="8ecb9-197">悪意のある URL やファイルからのクリック時の保護は、Microsoft [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-197">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="8ecb9-198">これは、安全な添付ファイル[と安全なリンクの](atp-safe-attachments.md)[ポリシーを使用して](atp-safe-links.md)設定されます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-198">It's set up through [Safe Attachments](atp-safe-attachments.md) and [Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8ecb9-199">Microsoft Defender for Office 365 の安全な添付ファイル ポリシー</span><span class="sxs-lookup"><span data-stu-id="8ecb9-199">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8ecb9-200">安全な添付ファイル [を設定するには](atp-safe-attachments.md)、少なくとも 1 つの安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-200">To set up [Safe Attachments](atp-safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="8ecb9-201">セキュリティ & コンプライアンス センター [で、[](https://protection.office.com)脅威 **管理** ポリシー ATP の安全な添付ファイル] を選択し、[作成] \>  \> をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-201">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="8ecb9-202">表示される **安全な添付ファイルの新しい** ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-202">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8ecb9-203">[名前 **] ボックスに** 「次へ」 `Block malware` と入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-203">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="8ecb9-204">[設定 **] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-204">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="8ecb9-205">[安全な **添付ファイル] の [不明なマルウェアの応答** ] セクションで、[ブロック] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-205">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="8ecb9-206">[添付ファイル **のリダイレクト] セクション** で、[リダイレクトを有効にする] **オプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-206">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="8ecb9-207">検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-207">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="8ecb9-208">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-208">Click **Next**.</span></span>

3. <span data-ttu-id="8ecb9-209">On the **Applied to** page, click **a condition,** choose **Applied if: The recipient domain is,** click **Add,** select your domains, click **Add,** click **Done,** and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8ecb9-209">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="8ecb9-210">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-210">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8ecb9-211">Microsoft Defender for Office 365 の安全なリンク ポリシー</span><span class="sxs-lookup"><span data-stu-id="8ecb9-211">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="8ecb9-212">安全なリンク [を設定するには](atp-safe-links.md)、安全なリンクのグローバル設定を確認および編集し、少なくとも 1 つの安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-212">To set up [Safe Links](atp-safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="8ecb9-213">セキュリティ &[コンプライアンス](https://protection.office.com)センターで、[**脅威管理** ポリシー ATP の安全なリンク] を選択し、[グローバル設定] をクリックして、次の \>  \> 設定を構成します。 </span><span class="sxs-lookup"><span data-stu-id="8ecb9-213">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="8ecb9-214">Verify **Use Safe Links in: Office 365 applications** is turned on: Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="8ecb9-214">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="8ecb9-215">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: Toggle off ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="8ecb9-215">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="8ecb9-216">**ユーザーが元の URL への安全な** リンクをクリックさせない: この設定がオンになっていることを確認します: ![ オンに切り替え ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-216">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="8ecb9-217">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-217">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="8ecb9-218">メインの [安全なリンク] ページに戻り、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-218">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="8ecb9-219">表示される **安全なリンクの作成** ポリシー ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-219">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8ecb9-220">[名前 **] ボックス** に名前を入力し、[次へ] `Safe Links` をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-220">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="8ecb9-221">[設定 **] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-221">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="8ecb9-222">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span><span class="sxs-lookup"><span data-stu-id="8ecb9-222">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="8ecb9-223">**Microsoft Teams 内の不明な URL または悪意のある** 可能性のある URL に対するアクションを選択します。[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-223">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="8ecb9-224">**組織内で送信される電子メール メッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="8ecb9-224">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="8ecb9-225">**メッセージを配信する前に URL のスキャンが完了するのを待つ**</span><span class="sxs-lookup"><span data-stu-id="8ecb9-225">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="8ecb9-226">**組織内で送信される電子メール メッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="8ecb9-226">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="8ecb9-227">**ユーザーがクリックして元の URL にアクセスできない**</span><span class="sxs-lookup"><span data-stu-id="8ecb9-227">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="8ecb9-228">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-228">Click **Next**</span></span>

4. <span data-ttu-id="8ecb9-229">On the **Applied to** page, click **a condition,** choose **Applied if: The recipient domain is,** click **Add,** select your domains, click **Add,** click **Done,** and then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8ecb9-229">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="8ecb9-230">設定を確認し、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-230">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="8ecb9-231">詳細については、「[安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-231">To learn more, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="8ecb9-232">パート 5 - SharePoint、OneDrive、Microsoft Teams の ATP がオンになっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-232">Part 5 - Verify ATP for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="8ecb9-233">SharePoint、OneDrive、Teams のようなワークロードは、コラボレーション用に構築されています。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-233">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="8ecb9-234">Defender を Office 365 に使用すると、チーム サイトやドキュメント ライブラリで悪意のあるファイルとして識別されたファイルをブロックおよび検出できます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-234">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="8ecb9-235">この機能の詳細については、以下を参照 [してください](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-235">You can read more about how that works [here](atp-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ecb9-236">**この手順を開始する前に、Microsoft 365** 環境で監査ログが既に有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-236">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="8ecb9-237">これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-237">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="8ecb9-238">詳細については、「監査ログ [検索を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-238">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="8ecb9-239">セキュリティ/[コンプライアンス センターで&](https://protection.office.com)管理ポリシー ATP の安全な添付ファイルを選択し、[グローバル設定] \>  \> を **クリックします**。 </span><span class="sxs-lookup"><span data-stu-id="8ecb9-239">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="8ecb9-240">**SharePoint、OneDrive、Microsoft Teams** の ATP を有効にするトグルが右側に表示されるのを確認します。オンに切り替え、[保存] ![ ](../../media/scc-toggle-on.png) をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-240">Verify the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/scc-toggle-on.png), and then click **Save**.</span></span>

3. <span data-ttu-id="8ecb9-241">組織の安全な添付ファイル ポリシーと安全なリンク ポリシーを [確認](set-up-atp-safe-attachments-policies.md) (および必要に応じて編集) [します](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-241">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

4. <span data-ttu-id="8ecb9-242">(推奨)全体管理者または SharePoint Online 管理者として _、DisallowInfectedFileDownload_ パラメーターを設定して **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します `$true` 。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-242">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="8ecb9-243">`$true` 検出されたファイルのすべてのアクション (Delete を除く) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-243">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="8ecb9-244">ユーザーは、検出されたファイルを開く、移動、コピー、または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-244">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="8ecb9-245">`$false` Delete および Download 以外のすべてのアクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-245">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="8ecb9-246">ユーザーはリスクを受け入れて、検出されたファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-246">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="8ecb9-247">Microsoft 365 で PowerShell を使用する方法の詳細については、「PowerShell を使用して [Microsoft 365 を管理](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-247">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

5. <span data-ttu-id="8ecb9-248">変更がすべての Microsoft 365 データセンターに分散するために最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-248">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="8ecb9-249">検出されたファイルのアラートを設定する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-249">Now set up alerts for detected files</span></span>

<span data-ttu-id="8ecb9-250">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるファイルとして識別された場合に通知を受け取る場合は、アラートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-250">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="8ecb9-251">セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラートの **管理を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-251">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="8ecb9-252">[新 **しいアラート ポリシー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-252">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="8ecb9-253">通知の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-253">Specify a name for the alert.</span></span> <span data-ttu-id="8ecb9-254">たとえば、「ライブラリ」に「悪意のあるファイル」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-254">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="8ecb9-255">アラートの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-255">Type a description for the alert.</span></span> <span data-ttu-id="8ecb9-256">たとえば、「SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが検出された場合に管理者に通知する」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-256">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="8ecb9-257">[この通知 **をいつ送信する...] セクションで** 、次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-257">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="8ecb9-258">a. </span><span class="sxs-lookup"><span data-stu-id="8ecb9-258">a.</span></span> <span data-ttu-id="8ecb9-259">[アクティビティ **] ボックスの** 一覧で、[ **ファイル内の検出されたマルウェア] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-259">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="8ecb9-260">b.</span><span class="sxs-lookup"><span data-stu-id="8ecb9-260">b.</span></span> <span data-ttu-id="8ecb9-261">[ユーザー **] フィールドは** 空のままにします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-261">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="8ecb9-262">[この警告の送信場所 **...]** セクションで、悪意のあるファイルが検出された場合に通知を受け取る必要がある 1 人または複数のグローバル管理者、セキュリティ管理者、またはセキュリティ 閲覧者を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-262">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="8ecb9-263">**保存します**。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-263">**Save**.</span></span>

<span data-ttu-id="8ecb9-264">アラートの詳細については、「セキュリティ/コンプライアンス センターでのアクティビティアラート& [参照してください](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-264">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8ecb9-265">構成が完了したら、次のリンクを使用してワークロードの調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-265">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="8ecb9-266">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="8ecb9-266">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="8ecb9-267">セキュリティ/コンプライアンス センター&使用して検疫済みファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-267">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="8ecb9-268">SharePoint Online、OneDrive、または Microsoft Teams で悪意のあるファイルが見つかった場合の対応方法</span><span class="sxs-lookup"><span data-stu-id="8ecb9-268">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="8ecb9-269">Microsoft 365 で管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-269">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="8ecb9-270">パート 6 - 構成する追加設定</span><span class="sxs-lookup"><span data-stu-id="8ecb9-270">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="8ecb9-271">マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護を構成するとともに、ゼロアワー自動消去を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-271">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="8ecb9-272">EOP での電子メールのゼロアワー自動消去</span><span class="sxs-lookup"><span data-stu-id="8ecb9-272">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="8ecb9-273">[ゼロアワー自動消去](zero-hour-auto-purge.md) (ZAP) は [、EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-273">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8ecb9-274">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-274">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="8ecb9-275">スパム対策アクションは、スパム \*\*対策ポリシーで [メッセージを迷惑メール\*\* フォルダー [に移動する] に設定されています](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-275">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="8ecb9-276">ユーザーは、既定の迷惑メール [設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持し、迷惑メール保護をオフにしていない。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-276">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="8ecb9-277">詳細については、「ゼロアワー自動消去 - スパムやマルウェアに対する [保護」を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-277">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="8ecb9-278">セットアップ後のタスクと次の手順</span><span class="sxs-lookup"><span data-stu-id="8ecb9-278">Post-setup tasks and next steps</span></span>

<span data-ttu-id="8ecb9-279">脅威保護機能を構成したら、それらの機能の動作を監視してください。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-279">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="8ecb9-280">必要に応じてポリシーを確認および修正します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-280">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="8ecb9-281">また、価値を高め得る新機能やサービス更新プログラムを監視します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-281">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="8ecb9-282">操作</span><span class="sxs-lookup"><span data-stu-id="8ecb9-282">What to do</span></span>|<span data-ttu-id="8ecb9-283">追加情報</span><span class="sxs-lookup"><span data-stu-id="8ecb9-283">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="8ecb9-284">レポートを表示して、組織の脅威保護機能がどのように機能しているのか確認する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-284">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="8ecb9-285">セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8ecb9-285">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="8ecb9-286">電子メール セキュリティ レポート</span><span class="sxs-lookup"><span data-stu-id="8ecb9-286">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="8ecb9-287">Microsoft Defender for Office 365 のレポート</span><span class="sxs-lookup"><span data-stu-id="8ecb9-287">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md) <p> [<span data-ttu-id="8ecb9-288">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="8ecb9-288">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="8ecb9-289">必要に応じて脅威保護ポリシーを定期的に確認および修正する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-289">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="8ecb9-290">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="8ecb9-290">Secure Score</span></span>](../mtp/microsoft-secure-score.md) <p> [<span data-ttu-id="8ecb9-291">スマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="8ecb9-291">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="8ecb9-292">Microsoft 365 脅威の調査と対応の機能</span><span class="sxs-lookup"><span data-stu-id="8ecb9-292">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="8ecb9-293">新機能とサービス更新プログラムを監視する</span><span class="sxs-lookup"><span data-stu-id="8ecb9-293">Watch for new features and service updates</span></span>|[<span data-ttu-id="8ecb9-294">標準リリースオプションと対象指定リリース オプション</span><span class="sxs-lookup"><span data-stu-id="8ecb9-294">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [<span data-ttu-id="8ecb9-295">Message Center</span><span class="sxs-lookup"><span data-stu-id="8ecb9-295">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [<span data-ttu-id="8ecb9-296">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="8ecb9-296">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="8ecb9-297">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="8ecb9-297">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="8ecb9-298">EOP および Defender for Office 365 の推奨される Standard および Strict セキュリティ構成の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ecb9-298">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="8ecb9-299">EOP と Microsoft Defender の 365 セキュリティOffice推奨設定</span><span class="sxs-lookup"><span data-stu-id="8ecb9-299">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)|
