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
description: 管理者は、Microsoft 365 の脅威保護について学習し、組織での使用方法を構成することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 624646461efe7131b2479e003b23a9e659e0a779
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326557"
---
# <a name="protect-against-threats"></a><span data-ttu-id="53035-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="53035-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="53035-104">Advanced Threat Protection の構成をチャンクに分割するクイックスタートガイドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="53035-104">Here's a quick-start guide that breaks the configuration of Advanced Threat Protection into chunks.</span></span> <span data-ttu-id="53035-105">Office 365 の脅威保護機能に慣れておらず、どこから始めるかがわからない場合や、 *実行*するのが最適な場合は、このガイドをチェックリストと開始点として使用します。</span><span class="sxs-lookup"><span data-stu-id="53035-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53035-106">**ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。</span><span class="sxs-lookup"><span data-stu-id="53035-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="53035-107">使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="53035-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="53035-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="53035-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="53035-109">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="53035-109">Subscriptions</span></span>

<span data-ttu-id="53035-110">脅威保護機能は、Microsoft または Office 365 の *すべて* のサブスクリプションに含まれています。ただし、一部のサブスクリプションには、高度な機能があります。</span><span class="sxs-lookup"><span data-stu-id="53035-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="53035-111">以下の表に、この記事に含まれる保護機能と最小のサブスクリプション要件を示します。</span><span class="sxs-lookup"><span data-stu-id="53035-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="53035-112">監査を有効にする *方法* 以外に、「Office 365 Exchange Online Protection (**EOP**) の一部としてマークされているマルウェア対策、フィッシング対策、およびスパム対策を開始することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="53035-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="53035-113">高度な脅威保護 (ATP) を含み、EOP を使用していることがわかっている場合は、Advanced Threat Protection (**ATP**) を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="53035-113">This can seem odd in an Advanced Threat Protection article, until you remember Advanced Threat Protection (**ATP**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="53035-114">保護の種類</span><span class="sxs-lookup"><span data-stu-id="53035-114">Protection type</span></span>|<span data-ttu-id="53035-115">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="53035-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="53035-116">監査ログ (レポート用)</span><span class="sxs-lookup"><span data-stu-id="53035-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="53035-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="53035-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="53035-118">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-118">Anti-malware protection</span></span>|<span data-ttu-id="53035-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span><span class="sxs-lookup"><span data-stu-id="53035-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="53035-120">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-120">Anti-phishing protection</span></span>|[<span data-ttu-id="53035-121">EOP</span><span class="sxs-lookup"><span data-stu-id="53035-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="53035-122">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-122">Anti-spam protection</span></span>|[<span data-ttu-id="53035-123">EOP</span><span class="sxs-lookup"><span data-stu-id="53035-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="53035-124">ゼロ時間自動削除 (電子メール用)</span><span class="sxs-lookup"><span data-stu-id="53035-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="53035-125">EOP</span><span class="sxs-lookup"><span data-stu-id="53035-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="53035-126">電子メールおよび Office ドキュメント内の悪意のある Url やファイルからの保護 (安全なリンクと安全な添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="53035-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|<span data-ttu-id="53035-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span><span class="sxs-lookup"><span data-stu-id="53035-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span></span>|
|<span data-ttu-id="53035-128">SharePoint、OneDrive、Microsoft Teams のワークロードに対して ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="53035-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="53035-129">ATP</span><span class="sxs-lookup"><span data-stu-id="53035-129">ATP</span></span>](atp-for-spo-odb-and-teams.md)|
|<span data-ttu-id="53035-130">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="53035-131">ATP</span><span class="sxs-lookup"><span data-stu-id="53035-131">ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="53035-132">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="53035-132">Roles and permissions</span></span>

<span data-ttu-id="53035-133">ATP ポリシーを構成するには、 [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)で適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="53035-133">To configure ATP policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="53035-134">これらの操作を実行できる役割については、以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="53035-135">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="53035-135">Role or role group</span></span>|<span data-ttu-id="53035-136">詳細情報</span><span class="sxs-lookup"><span data-stu-id="53035-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="53035-137">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="53035-137">global administrator</span></span>|[<span data-ttu-id="53035-138">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="53035-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="53035-139">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="53035-139">Security Administrator</span></span>|[<span data-ttu-id="53035-140">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="53035-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="53035-141">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="53035-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="53035-142">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="53035-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="53035-143">および</span><span class="sxs-lookup"><span data-stu-id="53035-143">and</span></span><br> [<span data-ttu-id="53035-144">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="53035-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="53035-145">詳細については、「 [Security &amp; コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-145">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="53035-146">開始する前に、レポートと調査の監査ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="53035-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="53035-147">事前に監査ログを開始します。</span><span class="sxs-lookup"><span data-stu-id="53035-147">Start your audit logging early.</span></span> <span data-ttu-id="53035-148">次の手順の **一部については、** 監査が必要になります。</span><span class="sxs-lookup"><span data-stu-id="53035-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="53035-149">監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="53035-150">[セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](threat-explorer.md)などの脅威保護レポートのデータを表示するためには、監査ログを*オンに*する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53035-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="53035-151">詳細については、「 [監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="53035-152">パート 1-マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="53035-153">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="53035-154">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**の  >  **マルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="53035-155">[ **既定** のポリシー] をダブルクリックし、[ **設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="53035-156">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="53035-156">Specify the following settings:</span></span>

    - <span data-ttu-id="53035-157">[ **マルウェア検出の応答** ] セクションで、既定の設定の [ **いいえ**] をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="53035-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="53035-158">[ **一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="53035-159">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-159">Click **Save**.</span></span>

<span data-ttu-id="53035-160">マルウェア対策ポリシーオプションの詳細については、「 [マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="53035-161">パート 2-フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="53035-162">[フィッシング対策]</span><span class="sxs-lookup"><span data-stu-id="53035-162">[Anti-phishing]</span></span>

<span data-ttu-id="53035-163">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-163">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="53035-164">高度なフィッシング対策を [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-164">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="53035-165">次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53035-165">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="53035-166">この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。</span><span class="sxs-lookup"><span data-stu-id="53035-166">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="53035-167">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-167">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="53035-168">[ **既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-168">Click **Default policy**.</span></span>

3. <span data-ttu-id="53035-169">[ **偽装** ] セクションで、[ **編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="53035-169">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="53035-170">[ **保護するユーザーの追加** ] タブで、 *[* 保護] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="53035-170">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="53035-171">次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="53035-171">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="53035-172">(個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)</span><span class="sxs-lookup"><span data-stu-id="53035-172">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="53035-173">[ **保護するドメインの追加** ] タブで、 **自分が所有しているドメインを自動的**に有効にします。</span><span class="sxs-lookup"><span data-stu-id="53035-173">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="53035-174">カスタムドメインがある場合は、ここで追加します。</span><span class="sxs-lookup"><span data-stu-id="53035-174">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="53035-175">[**操作**] タブで、[**偽装**されたユーザーと**偽装ドメイン**の両方の**メッセージを検疫**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-175">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="53035-176">また、偽装の安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="53035-176">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="53035-177">[ **メールボックスインテリジェンス** ] タブで、メールボックスインテリジェンスが有効になっていることを確認し、メールボックスインテリジェンスに基づく偽装保護をオンにします。</span><span class="sxs-lookup"><span data-stu-id="53035-177">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="53035-178">[偽装され **たユーザーがメールを送信した場合** ] で、[ **メッセージを検疫**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-178">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="53035-179">[ **信頼できる差出人とドメインの追加** ] タブで、追加する信頼できる送信者またはドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="53035-179">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="53035-180">設定を確認した後、[**設定の確認**] タブに**保存**します。</span><span class="sxs-lookup"><span data-stu-id="53035-180">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="53035-181">[ **スプーフィング** ] セクションで、[ **編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="53035-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="53035-182">[ **スプーフィングフィルターの設定** ] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53035-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="53035-183">[ **Actions** ] タブで、[ **メッセージを検疫する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-183">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="53035-184">変更内容を確認した後、[**設定の確認**] タブに**保存**します。</span><span class="sxs-lookup"><span data-stu-id="53035-184">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="53035-185">(変更を行っていない場合は、 **キャンセル**します)。</span><span class="sxs-lookup"><span data-stu-id="53035-185">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="53035-186">[既定のポリシー設定] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="53035-186">Close the default policy settings page.</span></span>

<span data-ttu-id="53035-187">フィッシング対策ポリシーのオプションの詳細については、「 [ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-187">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="53035-188">パート 3-スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="53035-188">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="53035-189">[スパム対策保護](anti-spam-protection.md) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-189">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="53035-190">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**ポリシーのスパム対策] を選択し  >  **Policy**  >  **Anti-spam**ます。</span><span class="sxs-lookup"><span data-stu-id="53035-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="53035-191">[ **カスタム** ] タブで、[ユーザー設定] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="53035-191">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="53035-192">[ **既定のスパムフィルターポリシー**] を展開し、[ **ポリシーの編集**] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="53035-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="53035-193">[ **スパムと一括操作** ] セクションで、しきい値を5または6に設定します。</span><span class="sxs-lookup"><span data-stu-id="53035-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="53035-194">[ **許可するリスト** ] セクションで、許可された送信者とドメインを確認 (または編集) します。</span><span class="sxs-lookup"><span data-stu-id="53035-194">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="53035-195">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-195">Click **Save**.</span></span>

<span data-ttu-id="53035-196">スパム対策ポリシーオプションの詳細については、「 [CONFIGURE EOP」の「スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-196">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-office-365-atp"></a><span data-ttu-id="53035-197">パート 4-悪意のある Url およびファイルからの保護 (Office 365 ATP の安全なリンクと安全な添付ファイル)</span><span class="sxs-lookup"><span data-stu-id="53035-197">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Office 365 ATP)</span></span>

<span data-ttu-id="53035-198">[Office 365 Advanced Threat protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) を含むサブスクリプションで、悪意のある url やファイルからのクリック時保護を利用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-198">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span></span> <span data-ttu-id="53035-199">これは、安全な [添付ファイル](atp-safe-attachments.md) と [安全なリンク](atp-safe-links.md) のポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="53035-199">It's set up through [Safe Attachments](atp-safe-attachments.md) and [Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-office-365-atp"></a><span data-ttu-id="53035-200">Office 365 の [安全な添付ファイルのポリシーの分析</span><span class="sxs-lookup"><span data-stu-id="53035-200">Safe Attachments policies in Office 365 ATP</span></span>

<span data-ttu-id="53035-201">[安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの安全なリンクポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="53035-201">To set up [Safe Attachments](atp-safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="53035-202">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP 安全添付ファイル**] を選択し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-202">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="53035-203">表示される **新しい安全な添付ファイルポリシー** ウィザードで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="53035-203">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="53035-204">[ **名前** ] ボックスに「 `Block malware` 」と入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-204">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="53035-205">[ **設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="53035-205">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="53035-206">[ **安全な添付ファイルの不明なマルウェアの応答** ] セクションで、[ **ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-206">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="53035-207">[ **添付ファイルのリダイレクト** ] セクションで、[ **リダイレクトを有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-207">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="53035-208">組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定して、検出されたファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="53035-208">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="53035-209">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-209">Click **Next**.</span></span>

3. <span data-ttu-id="53035-210">[ **適用先** ] ページで、[ **条件の追加**] をクリックし、[次の場合は適用] を選択し **ます。受信者のドメインが**である場合は、[ **追加**] をクリックし、ドメインまたはドメインを選択し、[ **追加**] **をクリックし**、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-210">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="53035-211">設定内容を確認し、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-211">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-office-365-atp"></a><span data-ttu-id="53035-212">Office 365 の「安全なリンク」ポリシーの ATP</span><span class="sxs-lookup"><span data-stu-id="53035-212">Safe Links policies in Office 365 ATP</span></span>

<span data-ttu-id="53035-213">[安全なリンク](atp-safe-links.md)を設定するには、安全なリンクのためのグローバル設定を確認して編集し、少なくとも1つの安全なリンクポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="53035-213">To set up [Safe Links](atp-safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="53035-214">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP セーフリンク**] を選択し、[**グローバル設定**] をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="53035-214">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="53035-215">**「安全なリンクの使用」** を確認してください。 Office 365 アプリケーションはオンになっています。オン ![ に ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) します。</span><span class="sxs-lookup"><span data-stu-id="53035-215">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>
   - <span data-ttu-id="53035-216">**ユーザーが [安全なリンク] をクリックしたときに追跡しない**: この設定をオフにして、ユーザーのクリックを追跡します: ![ トグルオフ ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="53035-216">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="53035-217">**ユーザーが安全なリンクをクリックして元の URL に移動できないようにする**: この設定がオンになっていることを確認します。オン ![ にし ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ます。</span><span class="sxs-lookup"><span data-stu-id="53035-217">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="53035-218">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-218">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="53035-219">[信頼できるメインリンク] ページに戻り、[ **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-219">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="53035-220">[ **安全なリンクの作成] ポリシー** ウィザードが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="53035-220">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="53035-221">[ **名前** ] ボックスに、などの名前を入力し、 `Safe Links` [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-221">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="53035-222">[ **設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="53035-222">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="53035-223">[**メッセージ内の不明な悪意のある url に対するアクション** **: 選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-223">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="53035-224">**Microsoft Teams 内の不明または悪意のある url に対するアクションを選択**します。 **[選択] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="53035-224">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="53035-225">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="53035-225">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="53035-226">**メッセージを配信する前に URL スキャンが完了するまで待機する**</span><span class="sxs-lookup"><span data-stu-id="53035-226">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="53035-227">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="53035-227">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="53035-228">**ユーザーが元の URL にクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="53035-228">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="53035-229">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-229">Click **Next**</span></span>

4. <span data-ttu-id="53035-230">[ **適用先** ] ページで、[ **条件の追加**] をクリックし、[次の場合は適用] を選択し **ます。受信者のドメインが**である場合は、[ **追加**] をクリックし、ドメインまたはドメインを選択し、[ **追加**] **をクリックし**、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-230">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="53035-231">設定内容を確認し、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-231">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="53035-232">詳細については、「 [安全なリンクポリシーをセットアップ](set-up-atp-safe-links-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-232">To learn more, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="53035-233">パート 5-SharePoint、OneDrive、Microsoft Teams の ATP が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="53035-233">Part 5 - Verify ATP for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="53035-234">SharePoint、OneDrive、Teams などのワークロードは、共同作業のために構築されています。</span><span class="sxs-lookup"><span data-stu-id="53035-234">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="53035-235">ATP を使用すると、チームサイトやドキュメントライブラリで悪意のあるファイルが検出された場合に、そのファイルをブロックおよび検出することができます。</span><span class="sxs-lookup"><span data-stu-id="53035-235">Using ATP helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="53035-236">この機能の詳細については、 [こちら](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-236">You can read more about how that works [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53035-237">**この手順を開始する前に、Microsoft 365 環境の監査ログが既に有効になっていることを確認して**ください。</span><span class="sxs-lookup"><span data-stu-id="53035-237">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="53035-238">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="53035-238">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="53035-239">詳細については、「 [監査ログの検索を有効または無効にする](../../compliance/turn-audit-log-search-on-or-off.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-239">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="53035-240">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP 安全添付ファイル**] を選択し、[**グローバル設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-240">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="53035-241">[ **SharePoint、OneDrive、および Microsoft Teams の ATP をオン** にする] のオン/オフを確認し、[オン] をクリックして、 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53035-241">Verify the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png), and then click **Save**.</span></span>

3. <span data-ttu-id="53035-242">組織の [安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md) と [安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="53035-242">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

4. <span data-ttu-id="53035-243">勧めグローバル管理者または SharePoint Online 管理者として、 _DisallowInfectedFileDownload_パラメーターをに設定して**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行し `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="53035-243">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="53035-244">`$true` 検出されたファイルのすべてのアクション (削除を除く) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="53035-244">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="53035-245">ユーザーは、検出されたファイルを開いたり、移動、コピー、または共有したりできません。</span><span class="sxs-lookup"><span data-stu-id="53035-245">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="53035-246">`$false` 削除とダウンロード以外のすべてのアクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="53035-246">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="53035-247">ユーザーは、リスクを容認し、検出されたファイルをダウンロードすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="53035-247">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="53035-248">Microsoft 365 での PowerShell の使用の詳細については、「 [Manage microsoft 365 With powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-248">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

5. <span data-ttu-id="53035-249">変更がすべての Microsoft 365 データセンターに蔓延するまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="53035-249">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="53035-250">検出されたファイルの通知を設定する</span><span class="sxs-lookup"><span data-stu-id="53035-250">Now set up alerts for detected files</span></span>

<span data-ttu-id="53035-251">SharePoint Online、OneDrive for Business、または Microsoft Teams のファイルが悪意のあるものとして識別された場合に通知を受け取るには、警告を設定します。</span><span class="sxs-lookup"><span data-stu-id="53035-251">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="53035-252">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、 **[通知の**管理] を選択し \> **Manage alerts**ます。</span><span class="sxs-lookup"><span data-stu-id="53035-252">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="53035-253">[ **新しい通知ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-253">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="53035-254">通知の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="53035-254">Specify a name for the alert.</span></span> <span data-ttu-id="53035-255">たとえば、ライブラリに悪意のあるファイルを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="53035-255">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="53035-256">通知の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="53035-256">Type a description for the alert.</span></span> <span data-ttu-id="53035-257">たとえば、SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出されたときに管理者に通知を入力できます。</span><span class="sxs-lookup"><span data-stu-id="53035-257">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="53035-258">[ **この通知を送信するタイミング** ] セクションで、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="53035-258">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="53035-259">a. </span><span class="sxs-lookup"><span data-stu-id="53035-259">a.</span></span> <span data-ttu-id="53035-260">[ **アクティビティ** ] リストで、[ **検出されたマルウェア (ファイル内**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-260">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="53035-261">b. </span><span class="sxs-lookup"><span data-stu-id="53035-261">b.</span></span> <span data-ttu-id="53035-262">[ **ユーザー** ] フィールドは空のままにします。</span><span class="sxs-lookup"><span data-stu-id="53035-262">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="53035-263">[ **この通知を送信する** ユーザー...] セクションで、悪意のあるファイルが検出されたときに通知を受信する必要がある1つ以上のグローバル管理者、セキュリティ管理者、またはセキュリティ閲覧者を選択します。</span><span class="sxs-lookup"><span data-stu-id="53035-263">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="53035-264">**保存**します。</span><span class="sxs-lookup"><span data-stu-id="53035-264">**Save**.</span></span>

<span data-ttu-id="53035-265">通知の詳細については、「 [セキュリティ & コンプライアンスセンターでアクティビティ警告を作成](../../compliance/create-activity-alerts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-265">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53035-266">構成が完了したら、次のリンクを使用してワークロード調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="53035-266">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="53035-267">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="53035-267">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="53035-268">セキュリティ & コンプライアンスセンターを使用して検疫されたファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="53035-268">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="53035-269">SharePoint Online、OneDrive、Microsoft Teams で悪意のあるファイルが検出された場合の対処方法</span><span class="sxs-lookup"><span data-stu-id="53035-269">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="53035-270">Microsoft 365 で管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="53035-270">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="53035-271">パート 6-構成する追加設定</span><span class="sxs-lookup"><span data-stu-id="53035-271">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="53035-272">マルウェア、悪意のある Url、ファイル、フィッシング、スパムからの保護の構成に加えて、ゼロ時間の自動削除を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53035-272">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="53035-273">EOP の電子メールのゼロ時間自動削除</span><span class="sxs-lookup"><span data-stu-id="53035-273">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="53035-274">[ゼロ時間自動削除](zero-hour-auto-purge.md) (ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="53035-274">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="53035-275">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="53035-275">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="53035-276">スパム[対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="53035-276">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="53035-277">ユーザーが既定の [迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="53035-277">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="53035-278">詳細については、「 [スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53035-278">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="53035-279">セットアップ後のタスクと次の手順</span><span class="sxs-lookup"><span data-stu-id="53035-279">Post-setup tasks and next steps</span></span>

<span data-ttu-id="53035-280">脅威保護機能を構成した後、これらの機能がどのように動作するかを必ず監視してください。</span><span class="sxs-lookup"><span data-stu-id="53035-280">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="53035-281">必要な操作を実行できるように、ポリシーを確認し、改訂します。</span><span class="sxs-lookup"><span data-stu-id="53035-281">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="53035-282">また、価値を追加できる新機能とサービス更新をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="53035-282">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="53035-283">操作</span><span class="sxs-lookup"><span data-stu-id="53035-283">What to do</span></span>|<span data-ttu-id="53035-284">追加情報</span><span class="sxs-lookup"><span data-stu-id="53035-284">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="53035-285">レポートを表示して、組織の脅威保護機能がどのように機能するかを確認する</span><span class="sxs-lookup"><span data-stu-id="53035-285">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="53035-286">セキュリティダッシュボード</span><span class="sxs-lookup"><span data-stu-id="53035-286">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="53035-287">電子メールセキュリティレポート</span><span class="sxs-lookup"><span data-stu-id="53035-287">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="53035-288">Office 365 ATP のレポート</span><span class="sxs-lookup"><span data-stu-id="53035-288">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="53035-289">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="53035-289">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="53035-290">必要に応じて脅威保護ポリシーを定期的にレビューし、改訂する</span><span class="sxs-lookup"><span data-stu-id="53035-290">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="53035-291">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="53035-291">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="53035-292">スマートレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="53035-292">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="53035-293">Microsoft 365 脅威の調査と応答機能</span><span class="sxs-lookup"><span data-stu-id="53035-293">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="53035-294">新機能とサービス更新を見る</span><span class="sxs-lookup"><span data-stu-id="53035-294">Watch for new features and service updates</span></span>|[<span data-ttu-id="53035-295">標準および対象のリリースオプション</span><span class="sxs-lookup"><span data-stu-id="53035-295">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="53035-296">Message Center</span><span class="sxs-lookup"><span data-stu-id="53035-296">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="53035-297">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="53035-297">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="53035-298">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="53035-298">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="53035-299">EOP および ATP の推奨される標準および厳密なセキュリティ構成の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="53035-299">Learn the details about recommended Standard and Strict security configurations for EOP and ATP</span></span>|[<span data-ttu-id="53035-300">EOP および Office 365 の ATP セキュリティに関する推奨設定</span><span class="sxs-lookup"><span data-stu-id="53035-300">Recommended settings for EOP and Office 365 ATP security</span></span>](recommended-settings-for-eop-and-office365-atp.md)|
