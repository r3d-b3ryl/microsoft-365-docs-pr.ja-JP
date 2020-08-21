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
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft 365 の脅威保護について説明し、組織での使用方法を構成できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826827"
---
# <a name="protect-against-threats"></a><span data-ttu-id="8d0d2-103">脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="8d0d2-103">Protect against threats</span></span>

<span data-ttu-id="8d0d2-104">Microsoft 365 には、さまざまな脅威保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="8d0d2-105">チェックリストとして使用できるクイック スタート ガイドを以下に示します。組織で脅威保護機能が設定されているか確認します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="8d0d2-106">Office 365 の脅威保護機能を使用したのが新しい場合、または開始する場所が不適切な場合は、次のガイダンスを出すための開始点として使用してください。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d0d2-107">**初期推奨される設定はポリシーの種類ごとに適用されています。ただし、多くのオプションを利用できます。また、組織固有のニーズに合わせて設定を調整できます**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="8d0d2-108">ポリシーまたは変更がデータセンターに通過するまで、約 30 分間の制限を行います。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="8d0d2-109">Requirements</span><span class="sxs-lookup"><span data-stu-id="8d0d2-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="8d0d2-110">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="8d0d2-110">Subscriptions</span></span>

<span data-ttu-id="8d0d2-111">脅威保護機能は、すべての Microsoft 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションにはより高度な機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="8d0d2-112">次の表は、この記事に含まれている保護機能とサブスクリプションの最小要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span>

****

|<span data-ttu-id="8d0d2-113">保護の種類</span><span class="sxs-lookup"><span data-stu-id="8d0d2-113">Protection type</span></span>|<span data-ttu-id="8d0d2-114">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="8d0d2-114">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="8d0d2-115">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-115">Anti-malware protection</span></span>|<span data-ttu-id="8d0d2-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="8d0d2-117">メールおよび Office ドキュメント内の悪意のある URL およびファイルからの保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="8d0d2-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="8d0d2-119">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-119">Anti-phishing protection</span></span>|[<span data-ttu-id="8d0d2-120">EOP</span><span class="sxs-lookup"><span data-stu-id="8d0d2-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8d0d2-121">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="8d0d2-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8d0d2-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="8d0d2-123">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-123">Anti-spam protection</span></span>|[<span data-ttu-id="8d0d2-124">EOP</span><span class="sxs-lookup"><span data-stu-id="8d0d2-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8d0d2-125">ゼロア自動消去 (メールの場合)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="8d0d2-126">EOP</span><span class="sxs-lookup"><span data-stu-id="8d0d2-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="8d0d2-127">監査ログ (これはレポート目的で使用されます)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="8d0d2-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8d0d2-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="8d0d2-129">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="8d0d2-129">Roles and permissions</span></span>

<span data-ttu-id="8d0d2-130">セキュリティ センターでポリシーを構成するには、適切な役割が割 [り当&必要があります](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="8d0d2-131">次の表にいくつかの例があります:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-131">The following table includes some examples:</span></span>

****

|<span data-ttu-id="8d0d2-132">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="8d0d2-132">Role or role group</span></span>|<span data-ttu-id="8d0d2-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8d0d2-133">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="8d0d2-134">全体管理者</span><span class="sxs-lookup"><span data-stu-id="8d0d2-134">global administrator</span></span>|[<span data-ttu-id="8d0d2-135">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="8d0d2-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="8d0d2-136">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8d0d2-136">Security Administrator</span></span>|[<span data-ttu-id="8d0d2-137">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8d0d2-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="8d0d2-138">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="8d0d2-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="8d0d2-139">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8d0d2-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="8d0d2-140">および</span><span class="sxs-lookup"><span data-stu-id="8d0d2-140">and</span></span><br> [<span data-ttu-id="8d0d2-141">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0d2-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="8d0d2-142">詳細については、セキュリティ コンプライアンス センター [の「アクセス許可」 &amp; を参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="8d0d2-143">第 1 部 - マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="8d0d2-144">[マルウェア対策保護は EOP](anti-malware-protection.md) を含むサブスクリプションで利用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8d0d2-145">セキュリティ/[コンプライアンス &で脅威](https://protection.office.com)管理**ポリシーのマルウェア**  >  **Policy**  >  **対策を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="8d0d2-146">既定のポリシーを **ダブルクリック** し、[設定] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="8d0d2-147">以下の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-147">Specify the following settings:</span></span>

    - <span data-ttu-id="8d0d2-148">[マルウェア **検出応答] セクションで、** 既定の設定を [いいえ] のまま **にします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="8d0d2-149">[共通の **添付ファイルの種類フィルター] セクション** で、[オン] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="8d0d2-150">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-150">Click **Save**.</span></span>

<span data-ttu-id="8d0d2-151">マルウェア対策ポリシー オプションの詳細については、「マルウェア対策 [ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="8d0d2-152">パート 2 - 悪意のある URL とファイルからの保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="8d0d2-153">悪意のある URL やファイルからのクリック時保護は [、Office 365 ATP (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) を含むサブスクリプションで利用できます [。ATP](atp-safe-attachments.md) の安全な添付ファイルや [ATP](atp-safe-links.md) の安全なリンクのポリシーによってセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="8d0d2-154">ATP の安全な添付ファイル機能のポリシー</span><span class="sxs-lookup"><span data-stu-id="8d0d2-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="8d0d2-155">[ATP の安全な添付ファイル機能を設定するには](atp-safe-attachments.md)、少なくとも 1 つの ATP の安全な添付ファイルに対するポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="8d0d2-156">セキュリティ/[コンプライアンス センター&で、脅](https://protection.office.com)威管理**ポリシー**  >  **Policy**  >  **ATP の安全な添付ファイルを選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="8d0d2-157">**SharePoint、OneDrive、Microsoft Teams の ATP を有効にするオプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="8d0d2-158">[メールの **添付ファイルの保護] セクションで** 、プラス記号 ( ) をクリックします **+** 。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="8d0d2-159">以下の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-159">Specify the following settings:</span></span>

   - <span data-ttu-id="8d0d2-160">[名前 **] ボックス** に、次のように入力します `Block malware` 。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="8d0d2-161">応答セクションで、ブロックを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="8d0d2-162">[リダイレクト **の添付ファイル]** セクションで 、[ **リダイレクトを有効にする] オプションを選択**し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターのメール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="8d0d2-163">In the **Applied to** section, choose The recipient **domain is**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="8d0d2-164">次に、ドメインを選び、[追加 **]、** または **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="8d0d2-165">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-165">Click **Save**.</span></span>

6. <span data-ttu-id="8d0d2-166">(**推奨される追加手順**)全体管理者または SharePoint Online 管理者は、Microsoft 365 環境に対して**DisallowInfectedFileDownload パラメーター**を*true*に設定して**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="8d0d2-167">(これにより、悪意があるとして検出されたファイルを開いたり、移動したり、コピーしたり、共有したりするのを防止できます。)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="8d0d2-168">詳細については [、「Office 365 ATP の安全な添付ファイル ポリシーを設定](set-up-atp-safe-attachments-policies.md) し [、SharePoint、OneDrive、Microsoft Teams Office 365 ATP を有効にする」を参照してください](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="8d0d2-169">ATP の安全なリンク機能のポリシー</span><span class="sxs-lookup"><span data-stu-id="8d0d2-169">ATP Safe Links policies</span></span>

<span data-ttu-id="8d0d2-170">[ATP の安全なリンクを設定するには、既定](atp-safe-links.md)のポリシーを確認および編集し、特定のユーザーに対するポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="8d0d2-171">コンプライアンス センター[から&で、脅](https://protection.office.com)威**管理ポリシー**  >  **Policy**  >  **ATP の安全なリンクを選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="8d0d2-172">[既定] ポリシーを **ダブルクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="8d0d2-173">「 **安全なリンクを使用する」セクション** で **、「Microsoft 365 Apps for enterprise、iOS および Android 用 Office」のオプション、および [保存**] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="8d0d2-174">特定の **受信者に適用するポリシー セクションで** 、プラス記号 ( ) をクリックします **+** 。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="8d0d2-175">以下の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-175">Specify the following settings:</span></span>

   - <span data-ttu-id="8d0d2-176">[名前 **] ボックス** に名前を入力 `Safe Links` します。例:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="8d0d2-177">[処理の **選択] セクションで** 、[オン] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="8d0d2-178">次のオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-178">Select these options:</span></span>

     - <span data-ttu-id="8d0d2-179">**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="8d0d2-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="8d0d2-180">**組織内で送信される電子メール メッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="8d0d2-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="8d0d2-181">**ユーザーが元の URL への安全なリンクをクリックしてクリックできない**</span><span class="sxs-lookup"><span data-stu-id="8d0d2-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="8d0d2-182">In the **Applied to** section, choose The recipient **domain is**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="8d0d2-183">次に、ドメインを選び、[追加 **]、** または **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="8d0d2-184">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-184">Click **Save**.</span></span>

<span data-ttu-id="8d0d2-185">詳細については、「[Office 365 ATP の安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="8d0d2-186">第 3 部 - フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="8d0d2-187">[フィッシング対策]</span><span class="sxs-lookup"><span data-stu-id="8d0d2-187">[Anti-phishing]</span></span>

<span data-ttu-id="8d0d2-188">[フィッシング対策は、EOP](anti-phishing-protection.md) を含むサブスクリプションで使用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8d0d2-189">ATP で高度なフィッシング対策 [保護を利用できます](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="8d0d2-190">次の手順では、ATP フィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="8d0d2-191">ステップは、フィッシング対策ポリシー (ATP なし) を構成するための手順と似ています。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="8d0d2-192">セキュリティ コンプライアンス[センターで&で、](https://protection.office.com)脅**威管理**  >  **ポリシー**  >  **ATP フィッシング対策を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8d0d2-193">[既定 **のポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="8d0d2-194">[偽装 **] セクションで、[** 編集] を **クリック**し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8d0d2-195">[保護する **ユーザーを追加します]** タブで、保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="8d0d2-196">次に、組織のボード メンバー、CEO、CFO、その他のシニア リーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="8d0d2-197">個々のメール アドレスを入力するか、クリックして一覧を表示できます)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="8d0d2-198">[ドメインの**追加] タブで、** 自動的に自分**が所有するドメインを含める。**</span><span class="sxs-lookup"><span data-stu-id="8d0d2-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="8d0d2-199">カスタム ドメインがある場合は、それらも追加します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="8d0d2-200">[アクション **] タブ**で、偽**装されたユーザーと**偽装されたドメイン**オプションの両方の\*\*\*\*メッセージを検疫するを選択**します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="8d0d2-201">さらに、偽装の安全性のヒントを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="8d0d2-202">[メールボックス **インテリジェンス] タブ** で、メールボックス インテリジェンスが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="8d0d2-203">さらに、メールボックス インテリジェンス ベース偽装保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="8d0d2-204">偽装 **されたユーザーの一覧で、[電子メールが送信される] で [** 検疫] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8d0d2-205">[ **信頼できる送信者とドメインの追加]** タブで、追加する信頼できる送信者またはドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="8d0d2-206">設定を **確認した後、[** 設定の確認] タブで [保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="8d0d2-207">**[Spoof] セクションで** **、[Edit]** をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8d0d2-208">[ス **プーフィング フィルター設定]** タブで、スプーフィング対策保護がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="8d0d2-209">[操作] タブ **で** 、[メッセージの検 **疫] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8d0d2-210">設定を **確認した後、[** 設定の確認] タブで [保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="8d0d2-211">(変更を加えなかった場合は、[キャンセル] を **クリックします**)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="8d0d2-212">既定のポリシー設定ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-212">Close the default policy settings page.</span></span>

<span data-ttu-id="8d0d2-213">フィッシング対策ポリシー オプションの詳細については [、「ATP フィッシング対策ポリシーを構成する」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="8d0d2-214">第 4 部 - スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="8d0d2-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="8d0d2-215">[EOP を含む](anti-spam-protection.md) サブスクリプションでは、スパム対策保護を利用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8d0d2-216">コンプライアンス コンプライアンス[センター&脅威管理](https://protection.office.com)**ポリシーの**  >  **Policy**  >  **スパム対策を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="8d0d2-217">[カスタム] **タブで** 、[カスタム設定 **] を有効** にします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="8d0d2-218">[ **既定のスパム フィルター ポリシーを展開し**、 **ポリシーの編集]** をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8d0d2-219">[スパムおよび **バルクアクション] セクション** でしきい値を 5 または 6 に設定します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="8d0d2-220">許可リスト **セクションで** 、許可されている送信者とドメインを確認 (および必要に応じて編集) します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="8d0d2-221">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-221">Click **Save**.</span></span>

<span data-ttu-id="8d0d2-222">スパム対策ポリシーのオプションの詳細については、「EOP でスパム対策 [ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="8d0d2-223">パート 5 - 構成する追加設定</span><span class="sxs-lookup"><span data-stu-id="8d0d2-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="8d0d2-224">マルウェア、悪意のある URL とファイル、フィッシング、スパムからの保護の構成に加えて、ゼロアリングおよび監査ログの設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="8d0d2-225">ゼロアルフパージのメールの消去</span><span class="sxs-lookup"><span data-stu-id="8d0d2-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="8d0d2-226">[ゼロアチ](zero-hour-auto-purge.md) (ZAP) は EOP を含むサブスクリプションで利用 [できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8d0d2-227">この保護は既定で有効になっています。ただし、保護が有効にするには、次の条件が満たされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="8d0d2-228">スパム対策ポリシーの [迷惑**メール] フォルダーにメッセージを移動**[するアクションが設定されています](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="8d0d2-229">ユーザーは既定の迷惑メール設定 [を保持してお](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)り、迷惑メールの保護を無効にしていません。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="8d0d2-230">詳細については、「ゼロ [アア自動消去 - スパムやマルウェアからの保護」を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="8d0d2-231">レポートと調査の監査ログ</span><span class="sxs-lookup"><span data-stu-id="8d0d2-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="8d0d2-232">監査ログは Exchange Online を含むサブスクリプションで [使用できます](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="8d0d2-233">セキュリティ ダッシュボード、電子メールのセキュリティ レポート、およびエクスプローラーなどの脅[email security reports](view-email-security-reports.md)[威保護](security-dashboard.md)レポートでデータを表示[するには](threat-explorer.md)、組織の監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="8d0d2-234">詳細については、「監査ログ検索 [を有効または無効にする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="8d0d2-235">セットアップ後の作業</span><span class="sxs-lookup"><span data-stu-id="8d0d2-235">Post-setup tasks</span></span>

<span data-ttu-id="8d0d2-236">脅威保護機能を構成したら、それらの機能がどのように動作しているかを監視し、必要に応じてポリシーを確認して変更し、新機能とサービス更新がないかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d0d2-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

****

|<span data-ttu-id="8d0d2-237">操作</span><span class="sxs-lookup"><span data-stu-id="8d0d2-237">What to do</span></span>|<span data-ttu-id="8d0d2-238">追加情報</span><span class="sxs-lookup"><span data-stu-id="8d0d2-238">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="8d0d2-239">レポートを表示して、組織に対して脅威保護機能がどのように機能しているかを確認する</span><span class="sxs-lookup"><span data-stu-id="8d0d2-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="8d0d2-240">セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8d0d2-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="8d0d2-241">電子メール セキュリティ レポート</span><span class="sxs-lookup"><span data-stu-id="8d0d2-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="8d0d2-242">365 ATP Officeレポート</span><span class="sxs-lookup"><span data-stu-id="8d0d2-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="8d0d2-243">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="8d0d2-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="8d0d2-244">必要に応じて脅威保護ポリシーを定期的に確認して変更する</span><span class="sxs-lookup"><span data-stu-id="8d0d2-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="8d0d2-245">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="8d0d2-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="8d0d2-246">スマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="8d0d2-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="8d0d2-247">Microsoft 365 脅威の調査および対応の機能</span><span class="sxs-lookup"><span data-stu-id="8d0d2-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="8d0d2-248">新機能およびサービス更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="8d0d2-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="8d0d2-249">標準および対象指定リリース オプション</span><span class="sxs-lookup"><span data-stu-id="8d0d2-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="8d0d2-250">Message Center</span><span class="sxs-lookup"><span data-stu-id="8d0d2-250">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="8d0d2-251">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="8d0d2-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="8d0d2-252">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="8d0d2-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
