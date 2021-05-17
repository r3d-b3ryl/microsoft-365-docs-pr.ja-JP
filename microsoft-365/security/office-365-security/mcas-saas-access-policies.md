---
title: SaaS Microsoft Cloud App Security推奨されるポリシー - Microsoft 365 Enterprise |Microsoft Docs
description: ユーザーとの統合に推奨されるポリシーについてMicrosoft Cloud App Security。
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 414d6ae0586078551c737e45763ea665d5eec4e6
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939556"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a><span data-ttu-id="06bd5-103">SaaS Microsoft Cloud App Security推奨されるポリシー</span><span class="sxs-lookup"><span data-stu-id="06bd5-103">Recommended Microsoft Cloud App Security policies for SaaS apps</span></span>
<span data-ttu-id="06bd5-104">Microsoft Cloud App Security Azure AD 条件付きアクセス ポリシーを基にして、ダウンロード、アップロード、コピー、貼り付け、印刷のブロックなど、SaaS アプリによる詳細なアクションをリアルタイムで監視および制御できます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-104">Microsoft Cloud App Security builds on Azure AD conditional access policies to enable real-time monitoring and control of granular actions with SaaS apps, such as blocking downloads, uploads, copy and paste, and printing.</span></span> <span data-ttu-id="06bd5-105">この機能は、企業リソースが管理されていないデバイスやゲスト ユーザーからアクセスされる場合など、固有のリスクを伴うセッションにセキュリティを追加します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-105">This feature adds security to sessions that carry inherent risk, such as when corporate resources are accessed from unmanaged devices or by guest users.</span></span>

<span data-ttu-id="06bd5-106">Microsoft Cloud App Security Microsoft Information Protection とネイティブに統合し、機密情報の種類と機密ラベルに基づいて機密データを検索し、適切なアクションを実行するためのリアルタイムコンテンツ検査を提供します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-106">Microsoft Cloud App Security also integrates natively with Microsoft Information Protection, providing real-time content inspection to find sensitive data based on sensitive information types and sensitivity labels and to take appropriate action.</span></span>

<span data-ttu-id="06bd5-107">このガイダンスには、次のシナリオに関する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06bd5-107">This guidance includes recommendations for these scenarios:</span></span>

- <span data-ttu-id="06bd5-108">SaaS アプリを IT 管理に取り込む</span><span class="sxs-lookup"><span data-stu-id="06bd5-108">Bring SaaS apps into IT management</span></span>
- <span data-ttu-id="06bd5-109">特定の SaaS アプリの保護を調整する</span><span class="sxs-lookup"><span data-stu-id="06bd5-109">Tune protection for specific SaaS apps</span></span>
- <span data-ttu-id="06bd5-110">データ保護規制に準拠するためにデータ損失防止 (DLP) を構成する</span><span class="sxs-lookup"><span data-stu-id="06bd5-110">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

## <a name="bring-saas-apps-into-it-management"></a><span data-ttu-id="06bd5-111">SaaS アプリを IT 管理に取り込む</span><span class="sxs-lookup"><span data-stu-id="06bd5-111">Bring SaaS apps into IT management</span></span>

<span data-ttu-id="06bd5-112">SaaS アプリをMicrosoft Cloud App Securityする最初の手順は、これらのアプリを検出し、それらを Azure AD テナントにADです。</span><span class="sxs-lookup"><span data-stu-id="06bd5-112">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="06bd5-113">検出に関するヘルプが必要な場合は、「 [ネットワーク内の SaaS アプリを検出して管理する」を参照してください](/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="06bd5-113">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="06bd5-114">アプリを検出した後、これらのアプリを [Azure ADテナントに追加します](/azure/active-directory/manage-apps/add-application-portal)。</span><span class="sxs-lookup"><span data-stu-id="06bd5-114">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="06bd5-115">これらを管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-115">You can begin to manage these by doing the following:</span></span>

1. <span data-ttu-id="06bd5-116">まず、Azure ADで、新しい条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-116">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="06bd5-117">これにより、要求がサーバーにリダイレクトCloud App Security。</span><span class="sxs-lookup"><span data-stu-id="06bd5-117">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="06bd5-118">1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-118">You can create one policy and add all SaaS apps to this policy.</span></span>
1. <span data-ttu-id="06bd5-119">次に、[セッション ポリシー Cloud App Security作成します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-119">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="06bd5-120">適用するコントロールごとに 1 つのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-120">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="06bd5-121">SaaS アプリへのアクセス許可は、通常、アプリへのアクセスに関するビジネス上の必要性に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="06bd5-121">Permissions to SaaS apps are typically based on business need for access to the app.</span></span> <span data-ttu-id="06bd5-122">これらのアクセス許可は、非常に動的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="06bd5-122">These permissions can be highly dynamic.</span></span> <span data-ttu-id="06bd5-123">ポリシー Cloud App Securityを使用すると、ベースライン保護、機密性の高い保護、または高度に規制された保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかに関係なく、アプリ データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-123">Using Cloud App Security policies ensures protection to app data, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="06bd5-124">SaaS アプリのコレクション全体のデータを保護するために、次の図は、必要な Azure AD 条件付きアクセス ポリシーと、Cloud App Security で作成できる推奨ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="06bd5-124">To protect data across your collection of SaaS apps, the following diagram illustrates the necessary Azure AD conditional access policy plus suggested policies you can create in Cloud App Security.</span></span> <span data-ttu-id="06bd5-125">この例では、管理しているすべての SaaS アプリCloud App Securityポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-125">In this example, the policies created in Cloud App Security apply to all SaaS apps you are managing.</span></span> <span data-ttu-id="06bd5-126">これらは、デバイスが管理されるかどうか、およびファイルに既に適用されている感度ラベルに基づいて適切なコントロールを適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="06bd5-126">These are designed to apply appropriate controls based on whether devices are managed as well as sensitivity labels that are already applied to files.</span></span>

![アプリ内の SaaS アプリを管理するためのCloud App Security](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

<span data-ttu-id="06bd5-128">次の表に、Azure サーバーで作成する必要がある新しい条件付きアクセス AD。</span><span class="sxs-lookup"><span data-stu-id="06bd5-128">The following table lists the new conditional access policy you must create in Azure AD.</span></span>

|<span data-ttu-id="06bd5-129">保護レベル</span><span class="sxs-lookup"><span data-stu-id="06bd5-129">Protection level</span></span>|<span data-ttu-id="06bd5-130">ポリシー</span><span class="sxs-lookup"><span data-stu-id="06bd5-130">Policy</span></span>|<span data-ttu-id="06bd5-131">詳細情報</span><span class="sxs-lookup"><span data-stu-id="06bd5-131">More information</span></span>|
|---|---|---|
|<span data-ttu-id="06bd5-132">すべての保護レベル</span><span class="sxs-lookup"><span data-stu-id="06bd5-132">All protection levels</span></span>|[<span data-ttu-id="06bd5-133">サーバーで条件付きアクセス アプリ制御を使用Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="06bd5-133">Use Conditional Access App Control in Cloud App Security</span></span>](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|<span data-ttu-id="06bd5-134">これにより、IdP (Azure AD) を構成して、Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="06bd5-134">This configures your IdP (Azure AD) to work with Cloud App Security.</span></span>|
||||

<span data-ttu-id="06bd5-135">次の表に、すべての SaaS アプリを保護するために作成できる上記のポリシー例を示します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-135">This next table lists the example policies illustrated above that you can create to protect all SaaS apps.</span></span> <span data-ttu-id="06bd5-136">ビジネス、セキュリティ、コンプライアンスの目的を評価し、環境に対して最も適切な保護を提供するポリシーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="06bd5-136">Be sure to evaluate your own business, security, and compliance objectives and then create policies that provide the most appropriate protection for your environment.</span></span>

|<span data-ttu-id="06bd5-137">保護レベル</span><span class="sxs-lookup"><span data-stu-id="06bd5-137">Protection level</span></span>|<span data-ttu-id="06bd5-138">ポリシー</span><span class="sxs-lookup"><span data-stu-id="06bd5-138">Policy</span></span>|
|---|---|
|<span data-ttu-id="06bd5-139">基準</span><span class="sxs-lookup"><span data-stu-id="06bd5-139">Baseline</span></span>|<span data-ttu-id="06bd5-140">管理されていないデバイスからのトラフィックを監視する</span><span class="sxs-lookup"><span data-stu-id="06bd5-140">Monitor traffic from unmanaged devices</span></span> <p> <span data-ttu-id="06bd5-141">管理されていないデバイスからのファイルダウンロードに保護を追加する</span><span class="sxs-lookup"><span data-stu-id="06bd5-141">Add protection to file downloads from unmanaged devices</span></span>|
|<span data-ttu-id="06bd5-142">機密</span><span class="sxs-lookup"><span data-stu-id="06bd5-142">Sensitive</span></span>|<span data-ttu-id="06bd5-143">機密または非管理対象デバイスから分類されたラベルが付いたファイルのダウンロードをブロックする (これにより、ブラウザーへのアクセスのみ可能)</span><span class="sxs-lookup"><span data-stu-id="06bd5-143">Block download of files labeled with sensitive or classified from unmanaged devices (this provides browser only access)</span></span>|
|<span data-ttu-id="06bd5-144">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="06bd5-144">Highly regulated</span></span>|<span data-ttu-id="06bd5-145">すべてのデバイスから分類されたラベルが付いたファイルのダウンロードをブロックする (これにより、ブラウザーへのアクセスのみ可能)</span><span class="sxs-lookup"><span data-stu-id="06bd5-145">Block download of files labeled with classified from all devices (this provides browser only access)</span></span>|
|||

<span data-ttu-id="06bd5-146">条件付きアクセス アプリ制御の設定に関するエンドツーエンドの手順については、「Deploy Conditional Access App Control for featured apps」 [を参照してください](/cloud-app-security/proxy-deployment-aad)。</span><span class="sxs-lookup"><span data-stu-id="06bd5-146">For end-to-end instructions for setting up Conditional Access App Control, see [Deploy Conditional Access App Control for featured apps](/cloud-app-security/proxy-deployment-aad).</span></span> <span data-ttu-id="06bd5-147">この記事では、Azure アプリで必要な条件付きアクセス ポリシーを作成し、SaaS ADテストするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-147">This article walks you through the process of creating the necessary conditional access policy in Azure AD and testing your SaaS apps.</span></span>

<span data-ttu-id="06bd5-148">詳細については、「条件付きアクセス[アプリ制御を使用してアプリMicrosoft Cloud App Security保護する」を参照してください](/cloud-app-security/proxy-intro-aad)。</span><span class="sxs-lookup"><span data-stu-id="06bd5-148">For more information, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span>

## <a name="tune-protection-for-specific-saas-apps"></a><span data-ttu-id="06bd5-149">特定の SaaS アプリの保護を調整する</span><span class="sxs-lookup"><span data-stu-id="06bd5-149">Tune protection for specific SaaS apps</span></span>

<span data-ttu-id="06bd5-150">環境内の特定の SaaS アプリに追加の監視とコントロールを適用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="06bd5-150">You might want to apply additional monitoring and controls to specific SaaS apps in your environment.</span></span> <span data-ttu-id="06bd5-151">Cloud App Securityを実行できます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-151">Cloud App Security allows you to accomplish this.</span></span> <span data-ttu-id="06bd5-152">たとえば、Box のようなアプリが環境で多用されている場合は、追加のコントロールを適用する方が理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="06bd5-152">For example, if an app like Box is used heavily in your environment, it makes sense to apply additional controls.</span></span> <span data-ttu-id="06bd5-153">または、法務部門または財務部門が機密ビジネス データに特定の SaaS アプリを使用している場合は、これらのアプリに対する追加の保護をターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-153">Or, if your legal or finance department is using a specific SaaS app for sensitive business data, you can target extra protection to these apps.</span></span>

<span data-ttu-id="06bd5-154">たとえば、次の種類の組み込みの異常検出ポリシー テンプレートを使用して Box 環境を保護できます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-154">For example, you can protect your Box environment with these types of built-in anomaly detection policy templates:</span></span>

- <span data-ttu-id="06bd5-155">匿名 IP アドレスからのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="06bd5-155">Activity from anonymous IP addresses</span></span>
- <span data-ttu-id="06bd5-156">ほとんどアクセスがない国からのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="06bd5-156">Activity from infrequent country</span></span>
- <span data-ttu-id="06bd5-157">疑わしい IP アドレスからのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="06bd5-157">Activity from suspicious IP addresses</span></span>
- <span data-ttu-id="06bd5-158">不可能な移動</span><span class="sxs-lookup"><span data-stu-id="06bd5-158">Impossible travel</span></span>
- <span data-ttu-id="06bd5-159">終了したユーザーが実行するアクティビティ (IdP として AAD が必要)</span><span class="sxs-lookup"><span data-stu-id="06bd5-159">Activity performed by terminated user (requires AAD as IdP)</span></span>
- <span data-ttu-id="06bd5-160">マルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="06bd5-160">Malware detection</span></span>
- <span data-ttu-id="06bd5-161">複数回のログイン試行の失敗</span><span class="sxs-lookup"><span data-stu-id="06bd5-161">Multiple failed login attempts</span></span>
- <span data-ttu-id="06bd5-162">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="06bd5-162">Ransomware activity</span></span>
- <span data-ttu-id="06bd5-163">危険な Oauth アプリ</span><span class="sxs-lookup"><span data-stu-id="06bd5-163">Risky Oauth App</span></span>
- <span data-ttu-id="06bd5-164">通常と異なるファイル共有アクティビティ</span><span class="sxs-lookup"><span data-stu-id="06bd5-164">Unusual file share activity</span></span>

<span data-ttu-id="06bd5-165">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-165">These are examples.</span></span> <span data-ttu-id="06bd5-166">追加のポリシー テンプレートは、定期的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-166">Additional policy templates are added on a regular basis.</span></span> <span data-ttu-id="06bd5-167">特定のアプリに追加の保護を適用する方法の例については、「接続されているアプリの保護 [」を参照してください](/cloud-app-security/protect-connected-apps)。</span><span class="sxs-lookup"><span data-stu-id="06bd5-167">For examples of how to apply additional protection to specific apps, see [Protecting connected apps](/cloud-app-security/protect-connected-apps).</span></span>

<span data-ttu-id="06bd5-168">[Box Cloud App Security保護](/cloud-app-security/protect-box)に役立つ方法は、Box や他のアプリで機密データを使用してビジネス データを保護するのに役立つコントロールの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="06bd5-168">[How Cloud App Security helps protect your Box environment](/cloud-app-security/protect-box) demonstrates the types of controls that can help you protect your business data in Box and other apps with sensitive data.</span></span>

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a><span data-ttu-id="06bd5-169">データ保護規制に準拠するためにデータ損失防止 (DLP) を構成する</span><span class="sxs-lookup"><span data-stu-id="06bd5-169">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

<span data-ttu-id="06bd5-170">Cloud App Security規制に対する保護を構成するための貴重なツールになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="06bd5-170">Cloud App Security can be a valuable tool for configuring protection for compliance regulations.</span></span> <span data-ttu-id="06bd5-171">この場合、規制が適用される特定のデータを検索する特定のポリシーを作成し、適切なアクションを実行するために各ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-171">In this case, you create specific policies to look for specific data that a regulation applies to and configure each policy to take appropriate action.</span></span>

<span data-ttu-id="06bd5-172">次の図と表に、一般データ保護規則 (GDPR) に準拠するように構成できるポリシーのいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-172">The following illustration and table provide several examples of policies that can be configured to help comply with  the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="06bd5-173">これらの例では、ポリシーは特定のデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="06bd5-173">In these examples, policies look for specific data.</span></span> <span data-ttu-id="06bd5-174">データの感度に基づいて、各ポリシーは適切なアクションを実行するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="06bd5-174">Based on the sensitivity of the data, each policy is configured to take appropriate action.</span></span>

![データCloud App Security防止のポリシーの例](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|<span data-ttu-id="06bd5-176&quot;>保護レベル</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;06bd5-176&quot;>Protection level</span></span>|<span data-ttu-id=&quot;06bd5-177&quot;>ポリシーの例</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;06bd5-177&quot;>Example policies</span></span>|
|---|---|
|<span data-ttu-id=&quot;06bd5-178&quot;>基準</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;06bd5-178&quot;>Baseline</span></span>|<span data-ttu-id=&quot;06bd5-179&quot;>この機密情報の種類を含むファイル (&quot;クレジット カード番号") が組織外で共有されている場合の警告</span><span class="sxs-lookup"><span data-stu-id="06bd5-179">Alert when files containing this sensitive information type ("Credit Card Number") are shared outside the organization</span></span> <p> <span data-ttu-id="06bd5-180">>この機密情報の種類 ("クレジット カード番号") を含むファイルの管理されていないデバイスへのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="06bd5-180">>Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span>|
|<span data-ttu-id="06bd5-181">機密</span><span class="sxs-lookup"><span data-stu-id="06bd5-181">Sensitive</span></span>|<span data-ttu-id="06bd5-182">この機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードを管理対象デバイスに保護する</span><span class="sxs-lookup"><span data-stu-id="06bd5-182">Protect downloads of files containing this sensitive information type ("Credit card number") to managed devices</span></span> <p> <span data-ttu-id="06bd5-183">管理されていないデバイスへのこの機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="06bd5-183">Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span> <p> <span data-ttu-id="06bd5-184">これらのラベルがオンのファイルが OneDrive for Business または Box にアップロードされると警告する (顧客データ、人事: 給与データ、人事、従業員データ)</span><span class="sxs-lookup"><span data-stu-id="06bd5-184">Alert when a file with on of these labels is uploaded to OneDrive for Business or Box (Customer data, Human Resources: Salary Data,Human Resources, Employee data)</span></span>|
|<span data-ttu-id="06bd5-185">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="06bd5-185">Highly regulated</span></span>|<span data-ttu-id="06bd5-186">このラベルを持つファイル ("高度に分類された") が管理対象デバイスにダウンロードされる場合の警告</span><span class="sxs-lookup"><span data-stu-id="06bd5-186">Alert when files with this label ("Highly classified") are downloaded to managed devices</span></span> <p> <span data-ttu-id="06bd5-187">管理されていないデバイスへのこのラベル ("高度に分類された") を持つファイルのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="06bd5-187">Block downloads of files with this label ("Highly classified") to unmanaged devices</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="06bd5-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="06bd5-188">Next steps</span></span>

<span data-ttu-id="06bd5-189">ドキュメントの使用の詳細については、「Cloud App Security」[をMicrosoft Cloud App Securityしてください](//cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="06bd5-189">For more information about using Cloud App Security, see [Microsoft Cloud App Security documentation](//cloud-app-security/).</span></span>
