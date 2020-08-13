---
title: 脅威から保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft 365 の脅威保護について学習し、組織での使用方法を構成することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c2786ebda18b5730e1cbe93316f0d6cc319f6a9
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656633"
---
# <a name="protect-against-threats"></a><span data-ttu-id="05098-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="05098-103">Protect against threats</span></span>

<span data-ttu-id="05098-104">Microsoft 365 には、さまざまな脅威保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05098-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="05098-105">ここでは、組織に対して脅威保護機能がセットアップされていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。</span><span class="sxs-lookup"><span data-stu-id="05098-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="05098-106">Office 365 の脅威保護機能を初めて使用する場合や、どこから始めるべきかがわからない場合は、次のガイドを出発点としてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="05098-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05098-107">**ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。</span><span class="sxs-lookup"><span data-stu-id="05098-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="05098-108">使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="05098-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="05098-109">要件</span><span class="sxs-lookup"><span data-stu-id="05098-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="05098-110">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="05098-110">Subscriptions</span></span>

<span data-ttu-id="05098-111">脅威保護機能は、すべての Microsoft 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには、より高度な機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05098-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="05098-112">次の表に、この記事に含まれる保護機能を最小限のサブスクリプション要件と共に示します。</span><span class="sxs-lookup"><span data-stu-id="05098-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

****

|<span data-ttu-id="05098-113">保護の種類</span><span class="sxs-lookup"><span data-stu-id="05098-113">Protection type</span></span>|<span data-ttu-id="05098-114">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="05098-114">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="05098-115">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-115">Anti-malware protection</span></span>|<span data-ttu-id="05098-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="05098-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="05098-117">メールおよび Office ドキュメント内の悪意のある URL およびファイルからの保護</span><span class="sxs-lookup"><span data-stu-id="05098-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="05098-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="05098-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="05098-119">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-119">Anti-phishing protection</span></span>|[<span data-ttu-id="05098-120">EOP</span><span class="sxs-lookup"><span data-stu-id="05098-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="05098-121">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="05098-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="05098-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="05098-123">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-123">Anti-spam protection</span></span>|[<span data-ttu-id="05098-124">EOP</span><span class="sxs-lookup"><span data-stu-id="05098-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="05098-125">ゼロ時間自動削除 (電子メール用)</span><span class="sxs-lookup"><span data-stu-id="05098-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="05098-126">EOP</span><span class="sxs-lookup"><span data-stu-id="05098-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="05098-127">監査ログ (これはレポート目的で使用されます)</span><span class="sxs-lookup"><span data-stu-id="05098-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="05098-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="05098-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="05098-129">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="05098-129">Roles and permissions</span></span>

<span data-ttu-id="05098-130">[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)でポリシーを構成するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="05098-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="05098-131">次の表にいくつかの例があります:</span><span class="sxs-lookup"><span data-stu-id="05098-131">The following table includes some examples:</span></span>

****

|<span data-ttu-id="05098-132">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="05098-132">Role or role group</span></span>|<span data-ttu-id="05098-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="05098-133">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="05098-134">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="05098-134">global administrator</span></span>|[<span data-ttu-id="05098-135">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="05098-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="05098-136">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="05098-136">Security Administrator</span></span>|[<span data-ttu-id="05098-137">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="05098-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="05098-138">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="05098-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="05098-139">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="05098-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="05098-140">および</span><span class="sxs-lookup"><span data-stu-id="05098-140">and</span></span><br> [<span data-ttu-id="05098-141">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="05098-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="05098-142">詳細については、「 [Security &amp; コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="05098-143">パート 1-マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="05098-144">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="05098-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="05098-145">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**の  >  **マルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="05098-146">[**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="05098-147">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-147">Specify the following settings:</span></span>

    - <span data-ttu-id="05098-148">[**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="05098-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="05098-149">[**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="05098-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-150">Click **Save**.</span></span>

<span data-ttu-id="05098-151">マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="05098-152">パート 2-悪意のある Url およびファイルからの保護</span><span class="sxs-lookup"><span data-stu-id="05098-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="05098-153">悪意のある Url やファイルからのクリック時の保護は、 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) を含むサブスクリプションで利用でき、Atp の[安全な添付ファイル](atp-safe-attachments.md)と[atp の安全なリンク](atp-safe-links.md)ポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="05098-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="05098-154">ATP の安全な添付ファイルポリシー</span><span class="sxs-lookup"><span data-stu-id="05098-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="05098-155">[Atp の安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの Atp の安全な添付ファイルポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05098-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="05098-156">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP 安全添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="05098-157">[ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="05098-158">[**電子メールの添付ファイルを保護**する] セクションで、プラス記号 () をクリックし **+** ます。</span><span class="sxs-lookup"><span data-stu-id="05098-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="05098-159">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-159">Specify the following settings:</span></span>

   - <span data-ttu-id="05098-160">[**名前**] ボックスに「」と入力 `Block malware` します。</span><span class="sxs-lookup"><span data-stu-id="05098-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="05098-161">[応答] セクションで、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="05098-162">[**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="05098-163">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="05098-164">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="05098-165">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-165">Click **Save**.</span></span>

6. <span data-ttu-id="05098-166">(**推奨の追加手順**)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行して、Microsoft 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。</span><span class="sxs-lookup"><span data-stu-id="05098-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="05098-167">(これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。</span><span class="sxs-lookup"><span data-stu-id="05098-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="05098-168">詳細については、「 [office 365 の atp の安全な添付ファイルのポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」および「 [SharePoint、OneDrive、Microsoft Teams 用の office 365 ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="05098-169">ATP の安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="05098-169">ATP Safe Links policies</span></span>

<span data-ttu-id="05098-170">[ATP の安全なリンク](atp-safe-links.md)を設定するには、既定のポリシーを確認して編集し、特定のユーザーのポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="05098-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="05098-171">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP セーフリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="05098-172">[**既定**のポリシー] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="05098-173">[**安全なリンクの使用**] セクションで、[ **Microsoft 365 Apps for enterprise]、[Office for IOS**、および Android] のオプションを選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="05098-174">[**特定の受信者に適用されるポリシー** ] セクションで、プラス記号 () をクリックし **+** ます。</span><span class="sxs-lookup"><span data-stu-id="05098-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="05098-175">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-175">Specify the following settings:</span></span>

   - <span data-ttu-id="05098-176">[**名前**] ボックスに、などの名前を入力し `Safe Links` ます。</span><span class="sxs-lookup"><span data-stu-id="05098-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="05098-177">**[アクションの選択**] セクションで、[**オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="05098-178">次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-178">Select these options:</span></span>

     - <span data-ttu-id="05098-179">**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="05098-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="05098-180">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="05098-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="05098-181">**ユーザーが元の URL への安全なリンクをクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="05098-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="05098-182">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="05098-183">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="05098-184">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-184">Click **Save**.</span></span>

<span data-ttu-id="05098-185">詳細については、「[Office 365 ATP の安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="05098-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="05098-186">パート 3-フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="05098-187">[フィッシング対策]</span><span class="sxs-lookup"><span data-stu-id="05098-187">[Anti-phishing]</span></span>

<span data-ttu-id="05098-188">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="05098-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="05098-189">高度なフィッシング対策を[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="05098-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="05098-190">次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05098-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="05098-191">この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。</span><span class="sxs-lookup"><span data-stu-id="05098-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="05098-192">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**  >  **ポリシー**  >  **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="05098-193">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="05098-194">[**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="05098-195">[**保護するユーザーの追加**] タブで、[保護] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="05098-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="05098-196">次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="05098-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="05098-197">(個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)</span><span class="sxs-lookup"><span data-stu-id="05098-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="05098-198">[**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。</span><span class="sxs-lookup"><span data-stu-id="05098-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="05098-199">カスタムドメインがある場合は、それらも追加します。</span><span class="sxs-lookup"><span data-stu-id="05098-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="05098-200">[**操作**] タブで、[**偽装**されたユーザーと**偽装ドメイン**の両方の**メッセージを検疫**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="05098-201">さらに、[偽装の安全性に関するヒント] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="05098-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="05098-202">[**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05098-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="05098-203">さらに、メールボックスインテリジェンスベースの偽装保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="05098-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="05098-204">[偽装され**たユーザーがメールを送信した場合**] で、[**メッセージを検疫**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="05098-205">[**信頼できる差出人とドメインの追加**] タブで、追加する信頼できる送信者またはドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="05098-206">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="05098-207">[**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="05098-208">[**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05098-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="05098-209">[ **Actions** ] タブで、[**メッセージを検疫する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="05098-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="05098-210">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="05098-211">(変更を行っていない場合は、[**キャンセル**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="05098-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="05098-212">[既定のポリシー設定] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="05098-212">Close the default policy settings page.</span></span>

<span data-ttu-id="05098-213">フィッシング対策ポリシーのオプションの詳細については、「 [ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="05098-214">パート 4-スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="05098-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="05098-215">[スパム対策保護](anti-spam-protection.md)は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="05098-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="05098-216">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**脅威管理**ポリシーのスパム対策] を選択し  >  **Policy**  >  **Anti-spam**ます。</span><span class="sxs-lookup"><span data-stu-id="05098-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="05098-217">[**カスタム**] タブで、[**カスタム設定**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="05098-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="05098-218">[**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="05098-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="05098-219">[**スパムと一括操作**] セクションで、しきい値を5または6に設定します。</span><span class="sxs-lookup"><span data-stu-id="05098-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="05098-220">[**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="05098-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="05098-221">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05098-221">Click **Save**.</span></span>

<span data-ttu-id="05098-222">スパム対策ポリシーオプションの詳細については、「 [CONFIGURE EOP」の「スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="05098-223">パート 5-構成する追加の設定</span><span class="sxs-lookup"><span data-stu-id="05098-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="05098-224">マルウェア、悪意のある Url、ファイル、フィッシング、スパムからの保護を構成するだけでなく、ゼロ時間の自動削除と監査ログの設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05098-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="05098-225">電子メールのゼロ時間自動削除</span><span class="sxs-lookup"><span data-stu-id="05098-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="05098-226">[ゼロ時間自動削除](zero-hour-auto-purge.md)(ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="05098-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="05098-227">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="05098-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="05098-228">スパム[対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="05098-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="05098-229">ユーザーが既定の[迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="05098-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="05098-230">詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="05098-231">レポートおよび調査の監査ログ</span><span class="sxs-lookup"><span data-stu-id="05098-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="05098-232">監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="05098-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="05098-233">[セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](threat-explorer.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05098-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="05098-234">詳細については、「[監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05098-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="05098-235">セットアップ後のタスク</span><span class="sxs-lookup"><span data-stu-id="05098-235">Post-setup tasks</span></span>

<span data-ttu-id="05098-236">脅威保護機能を構成した後は、それらの機能がどのように動作しているかを監視し、必要に応じてポリシーを確認して変更し、新しい機能とサービスの更新について確認してください。</span><span class="sxs-lookup"><span data-stu-id="05098-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

****

|<span data-ttu-id="05098-237">行うこと</span><span class="sxs-lookup"><span data-stu-id="05098-237">What to do</span></span>|<span data-ttu-id="05098-238">追加情報</span><span class="sxs-lookup"><span data-stu-id="05098-238">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="05098-239">レポートを表示して、組織の脅威保護機能がどのように機能するかを確認する</span><span class="sxs-lookup"><span data-stu-id="05098-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="05098-240">セキュリティダッシュボード</span><span class="sxs-lookup"><span data-stu-id="05098-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="05098-241">電子メールセキュリティレポート</span><span class="sxs-lookup"><span data-stu-id="05098-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="05098-242">Office 365 ATP のレポート</span><span class="sxs-lookup"><span data-stu-id="05098-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="05098-243">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="05098-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="05098-244">必要に応じて脅威保護ポリシーを定期的にレビューし、改訂する</span><span class="sxs-lookup"><span data-stu-id="05098-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="05098-245">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="05098-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="05098-246">スマートレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="05098-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="05098-247">Microsoft 365 脅威の調査と応答機能</span><span class="sxs-lookup"><span data-stu-id="05098-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="05098-248">新機能とサービス更新を見る</span><span class="sxs-lookup"><span data-stu-id="05098-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="05098-249">標準および対象のリリースオプション</span><span class="sxs-lookup"><span data-stu-id="05098-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="05098-250">Message Center</span><span class="sxs-lookup"><span data-stu-id="05098-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="05098-251">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="05098-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="05098-252">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="05098-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
