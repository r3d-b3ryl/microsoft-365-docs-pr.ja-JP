---
title: SaaS アプリに推奨される Microsoft Cloud App Security ポリシー - Microsoft 365 Enterprise |Microsoft Docs
description: Microsoft Cloud App Security との統合に推奨されるポリシーについて説明します。
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
ms.openlocfilehash: e9a52ca8cd46c0e9f590da7df94ee6d4c30289f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063292"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a><span data-ttu-id="173e1-103">SaaS アプリに推奨される Microsoft Cloud App Security ポリシー</span><span class="sxs-lookup"><span data-stu-id="173e1-103">Recommended Microsoft Cloud App Security policies for SaaS apps</span></span>
<span data-ttu-id="173e1-104">Microsoft Cloud App Security は、Azure AD 条件付きアクセス ポリシーを基に構築され、ダウンロード、アップロード、コピー、貼り付け、印刷のブロックなど、SaaS アプリによる詳細なアクションをリアルタイムで監視および制御できます。</span><span class="sxs-lookup"><span data-stu-id="173e1-104">Microsoft Cloud App Security builds on Azure AD conditional access policies to enable real-time monitoring and control of granular actions with SaaS apps, such as blocking downloads, uploads, copy and paste, and printing.</span></span> <span data-ttu-id="173e1-105">この機能は、企業リソースが管理されていないデバイスやゲスト ユーザーからアクセスされる場合など、固有のリスクを伴うセッションにセキュリティを追加します。</span><span class="sxs-lookup"><span data-stu-id="173e1-105">This feature adds security to sessions that carry inherent risk, such as when corporate resources are accessed from unmanaged devices or by guest users.</span></span> 

<span data-ttu-id="173e1-106">Microsoft Cloud App Security は、Microsoft Information Protection とネイティブに統合され、機密情報の種類と機密ラベルに基づいて機密データを検索し、適切なアクションを実行するためのリアルタイムコンテンツ検査を提供します。</span><span class="sxs-lookup"><span data-stu-id="173e1-106">Microsoft Cloud App Security also integrates natively with Microsoft Information Protection, providing real-time content inspection to find sensitive data based on sensitive information types and sensitivity labels and to take appropriate action.</span></span> 

<span data-ttu-id="173e1-107">このガイダンスには、次のシナリオに関する推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="173e1-107">This guidance includes recommendations for these scenarios:</span></span>
- <span data-ttu-id="173e1-108">SaaS アプリを IT 管理に取り込む</span><span class="sxs-lookup"><span data-stu-id="173e1-108">Bring SaaS apps into IT management</span></span>
- <span data-ttu-id="173e1-109">特定の SaaS アプリの保護を調整する</span><span class="sxs-lookup"><span data-stu-id="173e1-109">Tune protection for specific SaaS apps</span></span>
- <span data-ttu-id="173e1-110">データ保護規制に準拠するためにデータ損失防止 (DLP) を構成する</span><span class="sxs-lookup"><span data-stu-id="173e1-110">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

## <a name="bring-saas-apps-into-it-management"></a><span data-ttu-id="173e1-111">SaaS アプリを IT 管理に取り込む</span><span class="sxs-lookup"><span data-stu-id="173e1-111">Bring SaaS apps into IT management</span></span>

<span data-ttu-id="173e1-112">Microsoft Cloud App Security を使用して SaaS アプリを管理する最初の手順は、これらのアプリを検出し、それらを Azure アプリのテナントADです。</span><span class="sxs-lookup"><span data-stu-id="173e1-112">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="173e1-113">検出に関するヘルプが必要な場合は、「 [ネットワーク内の SaaS アプリを検出して管理する」を参照してください](https://docs.microsoft.com/cloud-app-security/tutorial-shadow-it)。</span><span class="sxs-lookup"><span data-stu-id="173e1-113">If you need help with discovery, see [Discover and manage SaaS apps in your network](https://docs.microsoft.com/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="173e1-114">アプリを検出した後、これらのアプリを [Azure ADテナントに追加します](https://docs.microsoft.com/azure/active-directory/manage-apps/add-application-portal)。</span><span class="sxs-lookup"><span data-stu-id="173e1-114">After you've discovered apps, [add these to your Azure AD tenant](https://docs.microsoft.com/azure/active-directory/manage-apps/add-application-portal).</span></span>  

<span data-ttu-id="173e1-115">これらを管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="173e1-115">You can begin to manage these by doing the following:</span></span>
1. <span data-ttu-id="173e1-116">まず、Azure ADで、新しい条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。</span><span class="sxs-lookup"><span data-stu-id="173e1-116">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="173e1-117">これにより、要求が Cloud App Security にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="173e1-117">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="173e1-118">1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="173e1-118">You can create one policy and add all SaaS apps to this policy.</span></span>
1. <span data-ttu-id="173e1-119">次に、Cloud App Security でセッション ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="173e1-119">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="173e1-120">適用するコントロールごとに 1 つのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="173e1-120">Create one policy for each control you want to apply.</span></span> 

<span data-ttu-id="173e1-121">SaaS アプリへのアクセス許可は、通常、アプリへのアクセスに関するビジネス上の必要性に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="173e1-121">Permissions to SaaS apps are typically based on business need for access to the app.</span></span> <span data-ttu-id="173e1-122">これらのアクセス許可は、非常に動的な場合があります。</span><span class="sxs-lookup"><span data-stu-id="173e1-122">These permissions can be highly dynamic.</span></span> <span data-ttu-id="173e1-123">Cloud App Security ポリシーを使用すると、ベースライン保護、機密性の高い保護、または厳しく規制された保護に関連付けられた Azure AD グループにユーザーが割り当てられているかどうかに関係なく、アプリ データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="173e1-123">Using Cloud App Security policies ensures protection to app data, regardless of whether users are assigned to an Azure AD group associated with baseline, sensitive, or highly regulated protection.</span></span>

<span data-ttu-id="173e1-124">SaaS アプリのコレクション全体のデータを保護するために、次の図は、必要な Azure AD 条件付きアクセス ポリシーと、Cloud App Security で作成できる推奨ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="173e1-124">To protect data across your collection of SaaS apps, the following diagram illustrates the necessary Azure AD conditional access policy plus suggested policies you can create in Cloud App Security.</span></span> <span data-ttu-id="173e1-125">この例では、Cloud App Security で作成されたポリシーは、管理しているすべての SaaS アプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="173e1-125">In this example, the policies created in Cloud App Security apply to all SaaS apps you are managing.</span></span> <span data-ttu-id="173e1-126">これらは、デバイスが管理されるかどうか、およびファイルに既に適用されている感度ラベルに基づいて適切なコントロールを適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="173e1-126">These are designed to apply appropriate controls based on whether devices are managed as well as sensitivity labels that are already applied to files.</span></span> 

<br>

![Cloud App Security で SaaS アプリを管理するためのポリシー](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

<span data-ttu-id="173e1-128">次の表に、Azure サーバーで作成する必要がある新しい条件付きアクセス AD。</span><span class="sxs-lookup"><span data-stu-id="173e1-128">The following table lists the new conditional access policy you must create in Azure AD.</span></span>

|<span data-ttu-id="173e1-129">保護レベル</span><span class="sxs-lookup"><span data-stu-id="173e1-129">Protection level</span></span>|<span data-ttu-id="173e1-130">ポリシー</span><span class="sxs-lookup"><span data-stu-id="173e1-130">Policy</span></span>|<span data-ttu-id="173e1-131">詳細情報</span><span class="sxs-lookup"><span data-stu-id="173e1-131">More information</span></span>|
|---|---|---|
|<span data-ttu-id="173e1-132">すべての保護レベル</span><span class="sxs-lookup"><span data-stu-id="173e1-132">All protection levels</span></span> | [<span data-ttu-id="173e1-133">Cloud App Security で条件付きアクセス アプリ制御を使用する</span><span class="sxs-lookup"><span data-stu-id="173e1-133">Use Conditional Access App Control in Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad) |<span data-ttu-id="173e1-134">これにより、IdP (Azure AD) が Cloud App Security で動作するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="173e1-134">This configures your IdP (Azure AD) to work with Cloud App Security.</span></span> |

<span data-ttu-id="173e1-135">次の表に、すべての SaaS アプリを保護するために作成できる上記のポリシー例を示します。</span><span class="sxs-lookup"><span data-stu-id="173e1-135">This next table lists the example policies illustrated above that you can create to protect all SaaS apps.</span></span> <span data-ttu-id="173e1-136">ビジネス、セキュリティ、コンプライアンスの目的を評価し、環境に対して最も適切な保護を提供するポリシーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="173e1-136">Be sure to evaluate your own business, security, and compliance objectives and then create policies that provide the most appropriate protection for your environment.</span></span> 

|<span data-ttu-id="173e1-137">保護レベル</span><span class="sxs-lookup"><span data-stu-id="173e1-137">Protection level</span></span>|<span data-ttu-id="173e1-138">ポリシー</span><span class="sxs-lookup"><span data-stu-id="173e1-138">Policy</span></span>|
|---|---|
|<span data-ttu-id="173e1-139">基準</span><span class="sxs-lookup"><span data-stu-id="173e1-139">Baseline</span></span> | <span data-ttu-id="173e1-140">管理されていないデバイスからのトラフィックを監視する</span><span class="sxs-lookup"><span data-stu-id="173e1-140">Monitor traffic from unmanaged devices</span></span><br><br><span data-ttu-id="173e1-141">管理されていないデバイスからのファイルダウンロードに保護を追加する</span><span class="sxs-lookup"><span data-stu-id="173e1-141">Add protection to file downloads from unmanaged devices</span></span> | 
|<span data-ttu-id="173e1-142">機密</span><span class="sxs-lookup"><span data-stu-id="173e1-142">Sensitive</span></span>  | <span data-ttu-id="173e1-143">機密または非管理対象デバイスから分類されたラベルが付いたファイルのダウンロードをブロックする (これにより、ブラウザーへのアクセスのみ可能)</span><span class="sxs-lookup"><span data-stu-id="173e1-143">Block download of files labeled with sensitive or classified from unmanaged devices (this provides browser only access)</span></span>  | 
| <span data-ttu-id="173e1-144">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="173e1-144">Highly regulated</span></span> | <span data-ttu-id="173e1-145">すべてのデバイスから分類されたラベルが付いたファイルのダウンロードをブロックする (これにより、ブラウザーへのアクセスのみ可能)</span><span class="sxs-lookup"><span data-stu-id="173e1-145">Block download of files labeled with classified from all devices (this provides browser only access)</span></span>  |   
|  |   |  

<span data-ttu-id="173e1-146">条件付きアクセス アプリ制御の設定に関するエンドツーエンドの手順については、「Deploy Conditional Access App Control for featured apps」 [を参照してください](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)。</span><span class="sxs-lookup"><span data-stu-id="173e1-146">For end-to-end instructions for setting up Conditional Access App Control, see [Deploy Conditional Access App Control for featured apps](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).</span></span> <span data-ttu-id="173e1-147">この記事では、Azure アプリで必要な条件付きアクセス ポリシーを作成し、SaaS ADテストするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="173e1-147">This article walks you through the process of creating the necessary conditional access policy in Azure AD and testing your SaaS apps.</span></span>




<span data-ttu-id="173e1-148">詳細については、「Microsoft Cloud App Security 条件付きアクセス アプリコントロールを使用してアプリを [保護する」を参照してください](https://docs.microsoft.com/cloud-app-security/proxy-intro-aad)。</span><span class="sxs-lookup"><span data-stu-id="173e1-148">For more information, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-intro-aad).</span></span> 


## <a name="tune-protection-for-specific-saas-apps"></a><span data-ttu-id="173e1-149">特定の SaaS アプリの保護を調整する</span><span class="sxs-lookup"><span data-stu-id="173e1-149">Tune protection for specific SaaS apps</span></span>
<span data-ttu-id="173e1-150">環境内の特定の SaaS アプリに追加の監視とコントロールを適用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="173e1-150">You might want to apply additional monitoring and controls to specific SaaS apps in your environment.</span></span> <span data-ttu-id="173e1-151">Cloud App Security を使用すると、これを実現できます。</span><span class="sxs-lookup"><span data-stu-id="173e1-151">Cloud App Security allows you to accomplish this.</span></span> <span data-ttu-id="173e1-152">たとえば、Box のようなアプリが環境で多用されている場合は、追加のコントロールを適用する方が理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="173e1-152">For example, if an app like Box is used heavily in your environment, it makes sense to apply additional controls.</span></span> <span data-ttu-id="173e1-153">または、法務部門または財務部門が機密ビジネス データに特定の SaaS アプリを使用している場合は、これらのアプリに対する追加の保護をターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="173e1-153">Or, if your legal or finance department is using a specific SaaS app for sensitive business data, you can target extra protection to these apps.</span></span> 

<span data-ttu-id="173e1-154">たとえば、次の種類の組み込みの異常検出ポリシー テンプレートを使用して Box 環境を保護できます。</span><span class="sxs-lookup"><span data-stu-id="173e1-154">For example, you can protect your Box environment with these types of built-in anomaly detection policy templates:</span></span>
- <span data-ttu-id="173e1-155">匿名 IP アドレスからのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="173e1-155">Activity from anonymous IP addresses</span></span>
- <span data-ttu-id="173e1-156">ほとんどアクセスがない国からのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="173e1-156">Activity from infrequent country</span></span>
- <span data-ttu-id="173e1-157">疑わしい IP アドレスからのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="173e1-157">Activity from suspicious IP addresses</span></span>
- <span data-ttu-id="173e1-158">不可能な移動</span><span class="sxs-lookup"><span data-stu-id="173e1-158">Impossible travel</span></span>
- <span data-ttu-id="173e1-159">終了したユーザーが実行するアクティビティ (IdP として AAD が必要)</span><span class="sxs-lookup"><span data-stu-id="173e1-159">Activity performed by terminated user (requires AAD as IdP)</span></span>
- <span data-ttu-id="173e1-160">マルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="173e1-160">Malware detection</span></span>
- <span data-ttu-id="173e1-161">複数回のログイン試行の失敗</span><span class="sxs-lookup"><span data-stu-id="173e1-161">Multiple failed login attempts</span></span>
- <span data-ttu-id="173e1-162">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="173e1-162">Ransomware activity</span></span>
- <span data-ttu-id="173e1-163">危険な Oauth アプリ</span><span class="sxs-lookup"><span data-stu-id="173e1-163">Risky Oauth App</span></span>
- <span data-ttu-id="173e1-164">通常と異なるファイル共有アクティビティ</span><span class="sxs-lookup"><span data-stu-id="173e1-164">Unusual file share activity</span></span>

<span data-ttu-id="173e1-165">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="173e1-165">These are examples.</span></span> <span data-ttu-id="173e1-166">追加のポリシー テンプレートは、定期的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="173e1-166">Additional policy templates are added on a regular basis.</span></span> <span data-ttu-id="173e1-167">特定のアプリに追加の保護を適用する方法の例については、「接続されているアプリの保護 [」を参照してください](https://docs.microsoft.com/cloud-app-security/protect-connected-apps)。</span><span class="sxs-lookup"><span data-stu-id="173e1-167">For examples of how to apply additional protection to specific apps, see [Protecting connected apps](https://docs.microsoft.com/cloud-app-security/protect-connected-apps).</span></span> 

<span data-ttu-id="173e1-168">[Cloud App Security が Box](https://docs.microsoft.com/cloud-app-security/protect-box) 環境の保護に役立つ方法は、Box や他のアプリのビジネス データを機密データで保護するのに役立つコントロールの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="173e1-168">[How Cloud App Security helps protect your Box environment](https://docs.microsoft.com/cloud-app-security/protect-box) demonstrates the types of controls that can help you protect your business data in Box and other apps with sensitive data.</span></span>


## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a><span data-ttu-id="173e1-169">データ保護規制に準拠するためにデータ損失防止 (DLP) を構成する</span><span class="sxs-lookup"><span data-stu-id="173e1-169">Configure data loss prevention (DLP) to help comply with data protection regulations</span></span>

<span data-ttu-id="173e1-170">Cloud App Security は、コンプライアンス規制に対する保護を構成するための貴重なツールです。</span><span class="sxs-lookup"><span data-stu-id="173e1-170">Cloud App Security can be a valuable tool for configuring protection for compliance regulations.</span></span> <span data-ttu-id="173e1-171">この場合、規制が適用される特定のデータを検索する特定のポリシーを作成し、適切なアクションを実行するために各ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="173e1-171">In this case, you create specific policies to look for specific data that a regulation applies to and configure each policy to take appropriate action.</span></span> 

<span data-ttu-id="173e1-172">次の図と表に、一般データ保護規則 (GDPR) に準拠するように構成できるポリシーのいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="173e1-172">The following illustration and table provide several examples of policies that can be configured to help comply with  the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="173e1-173">これらの例では、ポリシーは特定のデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="173e1-173">In these examples, policies look for specific data.</span></span> <span data-ttu-id="173e1-174">データの感度に基づいて、各ポリシーは適切なアクションを実行するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="173e1-174">Based on the sensitivity of the data, each policy is configured to take appropriate action.</span></span> 

![データ損失防止のための Cloud App Security ポリシーの例](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|<span data-ttu-id="173e1-176">保護レベル</span><span class="sxs-lookup"><span data-stu-id="173e1-176">Protection level</span></span>|<span data-ttu-id="173e1-177">ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="173e1-177">Example policies</span></span>|
|:---------------|:-------|
| <span data-ttu-id="173e1-178">基準</span><span class="sxs-lookup"><span data-stu-id="173e1-178">Baseline</span></span> |<span data-ttu-id="173e1-179">この機密情報の種類を含むファイル ("クレジット カード番号") が組織外で共有されている場合の警告</span><span class="sxs-lookup"><span data-stu-id="173e1-179">Alert when files containing this sensitive information type ("Credit Card Number") are shared outside the organization</span></span> <br><br><span data-ttu-id="173e1-180">管理されていないデバイスへのこの機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="173e1-180">Block downloads of files containing this sensitive information type (”Credit card number") to unmanaged devices</span></span>|
| <span data-ttu-id="173e1-181">機密</span><span class="sxs-lookup"><span data-stu-id="173e1-181">Sensitive</span></span>  | <span data-ttu-id="173e1-182">この機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードを管理対象デバイスに保護する</span><span class="sxs-lookup"><span data-stu-id="173e1-182">Protect downloads of files containing this sensitive information type ("Credit card number") to managed devices</span></span> <br><br><span data-ttu-id="173e1-183">管理されていないデバイスへのこの機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="173e1-183">Block downloads of files containing this sensitive information type ("Credit card number") to unmanaged devices</span></span> <br><br><span data-ttu-id="173e1-184">これらのラベルがオンのファイルが OneDrive for Business または Box にアップロードされた場合の警告 (顧客データ、人事: 給与データ、人事、従業員データ)</span><span class="sxs-lookup"><span data-stu-id="173e1-184">Alert when a file with on of these labels is uploaded to OneDrive for Business or Box (Customer data, Human Resources: Salary Data,Human Resources, Employee data)</span></span>|
| <span data-ttu-id="173e1-185">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="173e1-185">Highly regulated</span></span> |<span data-ttu-id="173e1-186">このラベルを持つファイル ("高度に分類された") が管理対象デバイスにダウンロードされる場合の警告</span><span class="sxs-lookup"><span data-stu-id="173e1-186">Alert when files with this label ("Highly classified") are downloaded to managed devices</span></span> <p><span data-ttu-id="173e1-187">管理されていないデバイスへのこのラベル ("高度に分類された") を持つファイルのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="173e1-187">Block downloads of files with this label ("Highly classified") to unmanaged devices</span></span> |
| | |



## <a name="next-steps"></a><span data-ttu-id="173e1-188">次の手順</span><span class="sxs-lookup"><span data-stu-id="173e1-188">Next steps</span></span>

<span data-ttu-id="173e1-189">クラウド アプリ セキュリティの使用の詳細については [、「Microsoft Cloud App Security」のドキュメントを参照してください](https://docs.microsoft.com//cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="173e1-189">For more information about using Cloud App Security, see [Microsoft Cloud App Security documentation](https://docs.microsoft.com//cloud-app-security/).</span></span> 