---
title: GDPR および CCPA のためのデータ対象要求
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR、CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
description: Microsoft の製品とサービスを使用して、一般データ保護規則 (GPDR) およびカリフォルニア州消費者プライバシー法 (CCPA) に従って DSR を完了する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7342c0ae4105c05ae2e2956df51581d3afedb286
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035475"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a><span data-ttu-id="ff42d-104">データ対象要求と GDPR および CCPA</span><span class="sxs-lookup"><span data-stu-id="ff42d-104">Data Subject Requests and the GDPR and CCPA</span></span>

<span data-ttu-id="ff42d-105">一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。</span><span class="sxs-lookup"><span data-stu-id="ff42d-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="ff42d-106">詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff42d-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span>

<span data-ttu-id="ff42d-107">同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-107">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  <span data-ttu-id="ff42d-108">また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、"売上" として分類された特定のデータ転送の "オプトアウト/オプトイン" 要件を規定します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-108">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and "opt-out/ opt-in" requirements for certain data transfers classified as "sales".</span></span> <span data-ttu-id="ff42d-109">このドキュメントは、Microsoft の製品とサービスの使用における、GDPR および CCPA に基づくデータ主体の要求 (DSR) の完了に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-109">This document guides you to information on the completion of Data Subject Requests (DSRs) under the GDPR and CCPA using Microsoft products and services.</span></span>

- [<span data-ttu-id="ff42d-110">Office 365</span><span class="sxs-lookup"><span data-stu-id="ff42d-110">Office 365</span></span>](gdpr-dsr-Office365.md)
- [<span data-ttu-id="ff42d-111">Azure</span><span class="sxs-lookup"><span data-stu-id="ff42d-111">Azure</span></span>](gdpr-dsr-Azure.md)
- [<span data-ttu-id="ff42d-112">Intune</span><span class="sxs-lookup"><span data-stu-id="ff42d-112">Intune</span></span>](gdpr-dsr-Intune.md)
- [<span data-ttu-id="ff42d-113">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ff42d-113">Dynamics 365</span></span>](gdpr-dsr-Dynamics365.md)
- [<span data-ttu-id="ff42d-114">Visual Studio ファミリ</span><span class="sxs-lookup"><span data-stu-id="ff42d-114">Visual Studio Family</span></span>](gdpr-dsr-visual-studio-family.md)
- [<span data-ttu-id="ff42d-115">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="ff42d-115">Azure DevOps Services</span></span>](gdpr-dsr-vsts.md)
- [<span data-ttu-id="ff42d-116">Microsoft サポート/プロフェッショナル サービス</span><span class="sxs-lookup"><span data-stu-id="ff42d-116">Microsoft Support and Professional Services</span></span>](gdpr-dsr-prof-services.md)

## <a name="terminology"></a><span data-ttu-id="ff42d-117">用語</span><span class="sxs-lookup"><span data-stu-id="ff42d-117">Terminology</span></span>

<span data-ttu-id="ff42d-118">このドキュメントで使用されている GDPR 用語の役に立つ定義:</span><span class="sxs-lookup"><span data-stu-id="ff42d-118">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="ff42d-119">*データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-119">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="ff42d-120">*個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。</span><span class="sxs-lookup"><span data-stu-id="ff42d-120">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="ff42d-121">*処理者*: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。</span><span class="sxs-lookup"><span data-stu-id="ff42d-121">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="ff42d-122">*顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。</span><span class="sxs-lookup"><span data-stu-id="ff42d-122">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dsr"></a><span data-ttu-id="ff42d-123">DSR とは?</span><span class="sxs-lookup"><span data-stu-id="ff42d-123">What is a DSR?</span></span>

<span data-ttu-id="ff42d-124">一般データ保護規則 (GDPR) は、規制においてデータ主体と呼ばれる人に、雇用主または他の種類の機関や組織 (データ コントローラーまたは単にコントローラーと呼ばれます) によって収集された個人データを管理する権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="ff42d-124">The General Data Protection Regulation (GDPR) gives rights to people (known in the regulation as data subjects) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the data controller or just controller).</span></span> <span data-ttu-id="ff42d-125">GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの変更の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff42d-125">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller.</span></span>

<span data-ttu-id="ff42d-126">カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-126">California Consumer Privacy Act (CCPA) provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  

<span data-ttu-id="ff42d-127">管理者は、要求されたアクションを実行するか、または管理者が DSR に対応できない理由についての説明を提供することで、各 DSR を速やかに検討し、実質的な対応を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-127">As a controller, you are obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller.</span></span> <span data-ttu-id="ff42d-128">コントローラーは、特定の DSR の適切な処理について自身の法律またはコンプライアンスのアドバイザーに相談する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-128">A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.</span></span>

<span data-ttu-id="ff42d-129">DSR の完了には、組織の GDPR コンプライアンス規則に従って、いくつかのプロセスが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-129">Several processes may be involved completing a DSR, subject to your organization's GDPR-compliance rules.</span></span>
  
- <span data-ttu-id="ff42d-130">**検出**。</span><span class="sxs-lookup"><span data-stu-id="ff42d-130">**Discovery**.</span></span> <span data-ttu-id="ff42d-131">DSR を完了するために必要なデータを特定するプロセス。</span><span class="sxs-lookup"><span data-stu-id="ff42d-131">The process of determining what data is needed to complete a DSR.</span></span>
- <span data-ttu-id="ff42d-132">**アクセス**。</span><span class="sxs-lookup"><span data-stu-id="ff42d-132">**Access**.</span></span> <span data-ttu-id="ff42d-133">検出された情報の取得とデータ主体への潜在的な伝送。</span><span class="sxs-lookup"><span data-stu-id="ff42d-133">Retrieval and potential transmission to the data subject of discovered information.</span></span>
- <span data-ttu-id="ff42d-134">**修正**。</span><span class="sxs-lookup"><span data-stu-id="ff42d-134">**Rectify**.</span></span> <span data-ttu-id="ff42d-135">変更またはその他の要求された個人データの変更を実施します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-135">Implement changes or other requested personal data changes.</span></span>
- <span data-ttu-id="ff42d-136">**制限**。</span><span class="sxs-lookup"><span data-stu-id="ff42d-136">**Restrict**.</span></span> <span data-ttu-id="ff42d-137">アクセスを制限する、または Microsoft クラウドからデータを削除することにより、個人データのアクセスまたは処理を変更します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-137">Changing the access or processing of persona data by restricting access, or removing data from the Microsoft cloud.</span></span>
- <span data-ttu-id="ff42d-138">**エクスポート**。</span><span class="sxs-lookup"><span data-stu-id="ff42d-138">**Export**.</span></span> <span data-ttu-id="ff42d-139">GDPR の「データの移植の権利」で規定されているように、「構造化された一般的に使用されているコンピューターが読み取り可能な形式」の個人データをデータ主体に提供します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-139">Providing a "structured, commonly used, machine-readable format" of personal data to the data subject, as provided by the GDPR's "right of data portability."</span></span>
- <span data-ttu-id="ff42d-140">**Delete**</span><span class="sxs-lookup"><span data-stu-id="ff42d-140">**Delete**.</span></span> <span data-ttu-id="ff42d-141">Microsoft クラウドから個人データを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-141">Permanent removal of personal data from the Microsoft cloud.</span></span>

## <a name="specific-dsr-considerations"></a><span data-ttu-id="ff42d-142">特定の DSR に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ff42d-142">Specific DSR Considerations</span></span>

### <a name="insights-generated-by-microsoft-products-or-services"></a><span data-ttu-id="ff42d-143">Microsoft の製品またはサービスにより生成された分析情報</span><span class="sxs-lookup"><span data-stu-id="ff42d-143">Insights generated by Microsoft Products or Services</span></span>

<span data-ttu-id="ff42d-144">[分析情報](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)はサービス (MyAnalytics など) によって生成される場合があります。Office 365 には、分析情報を使用するユーザーと組織にこの情報を提供するオンライン サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff42d-144">[Insights](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) may be generated by services (MyAnalytics, etc.) Office 365 includes online services that provide insights to users and organizations that use them.</span></span> <span data-ttu-id="ff42d-145">これらのサービスによって生成されたデータによって、DSR に関連する個人データが生成される場合あります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-145">Data generated by these services may produce personal data relevant to a DSR.</span></span> <span data-ttu-id="ff42d-146">サービス固有の DSR プロセスに関する詳細については、以下のリストにあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff42d-146">Follow the link in the list below for details regarding service-specific DSR processes.</span></span>  

### <a name="dsrs-for-system-generated-logs"></a><span data-ttu-id="ff42d-147">システム生成ログに関する DSR</span><span class="sxs-lookup"><span data-stu-id="ff42d-147">DSRs for system-generated logs</span></span>

<span data-ttu-id="ff42d-148">Microsoft によって生成されたログと関連データには、"個人データ" の GDPR 定義に基づき個人に関するものとしてみなされるデータが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-148">Logs and related data generated by Microsoft may contain data deemed personal under GDPR's definition of "personal data."</span></span> <span data-ttu-id="ff42d-149">システム生成ログのデータの制限または修正はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ff42d-149">Restricting or rectifying data in system-generated logs is not supported.</span></span> <span data-ttu-id="ff42d-150">システム生成ログのデータは、Microsoft のクラウド内で実行された実際のアクションや診断データを構成しているため、変更すると、アクションの履歴記録が損なわれ、詐欺やセキュリティのリスクが増大します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-150">Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data; modifications would compromise the historical record of actions and increase fraud and security risks.</span></span> <span data-ttu-id="ff42d-151">Microsoft は、DSR の完了に必要となる可能性があるシステム生成ログに対するアクセス、エクスポート、削除の各機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-151">Microsoft provides the ability to access, export, and delete system-generated logs that may be necessary to complete a DSR.</span></span> <span data-ttu-id="ff42d-152">該当するデータには次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-152">Examples of such data may include:</span></span>  

- <span data-ttu-id="ff42d-153">製品およびサービスの利用状況データ (ユーザー アクティビティ ログなど)</span><span class="sxs-lookup"><span data-stu-id="ff42d-153">Product and service usage data such as user activity logs</span></span>
- <span data-ttu-id="ff42d-154">ユーザー検索要求およびクエリ データ</span><span class="sxs-lookup"><span data-stu-id="ff42d-154">User search requests and query data</span></span>
- <span data-ttu-id="ff42d-155">ユーザーまたはその他のシステムによるシステム機能および相互作用の結果として、製品およびサービスによって生成されたデータ。</span><span class="sxs-lookup"><span data-stu-id="ff42d-155">Data generated by product and services resulting from system functionality and interaction by users or other systems.</span></span>  

### <a name="yammer-and-kaizala"></a><span data-ttu-id="ff42d-156">Yammer と Kaizala</span><span class="sxs-lookup"><span data-stu-id="ff42d-156">Yammer and Kaizala</span></span>

<span data-ttu-id="ff42d-157">ユーザーのアカウントを削除しても、システムで生成された Yammer および Kaizala のログは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ff42d-157">Deleting a user's account will not remove system-generated logs for Yammer and Kaizala.</span></span> <span data-ttu-id="ff42d-158">これらのアプリケーションからデータを削除するには、次のいずれかのリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff42d-158">To remove the data from these applications, see one of the following resources:</span></span>

- [<span data-ttu-id="ff42d-159">Yammer Enterprise で GDPR データ主体の要求を管理する</span><span class="sxs-lookup"><span data-stu-id="ff42d-159">Manage GDPR data subject requests in Yammer Enterprise</span></span>](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [<span data-ttu-id="ff42d-160">Kaizala でユーザーの組織データをエクスポートまたは削除する</span><span class="sxs-lookup"><span data-stu-id="ff42d-160">Export or delete a user's organizational data in Kaizala</span></span>](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a><span data-ttu-id="ff42d-161">国内クラウド</span><span class="sxs-lookup"><span data-stu-id="ff42d-161">National Clouds</span></span>

<span data-ttu-id="ff42d-162">一部の国内クラウドでは、グローバル IT 管理者がシステム生成ログを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-162">In some national clouds, a global IT Administrator needs to delete system-generated logs.</span></span>

### <a name="microsoft-services"></a><span data-ttu-id="ff42d-163">Microsoft サービス</span><span class="sxs-lookup"><span data-stu-id="ff42d-163">Microsoft Services</span></span>

<span data-ttu-id="ff42d-164">お客様の組織またはユーザーが Microsoft の製品とサービスに関連するサポートを受けるために Microsoft と連携している場合、このデータの一部に個人データが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-164">If your organization or users engage with Microsoft to receive,  support related to Microsoft products and services some of this data may contain personal data.</span></span> <span data-ttu-id="ff42d-165">詳細については、「[GDPR のための Microsoft サポート/プロフェッショナル サービス データ主体の要求](gdpr-dsr-prof-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff42d-165">For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](gdpr-dsr-prof-services.md).</span></span>

### <a name="microsoft-controller-products"></a><span data-ttu-id="ff42d-166">Microsoft コントローラー製品</span><span class="sxs-lookup"><span data-stu-id="ff42d-166">Microsoft Controller Products</span></span>

<span data-ttu-id="ff42d-167">状況によっては、組織のユーザーは Microsoft がデータ コントローラーである Microsoft の製品またはサービスにアクセスすることもあります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-167">In some circumstances, your organization's users may access Microsoft products or services for which Microsoft is the data controller.</span></span> <span data-ttu-id="ff42d-168">このような場合、ユーザーは自分自身の DSR を Microsoft に対して直接開始する必要があります。また、Microsoft はユーザーに対する要求を直接満たします。</span><span class="sxs-lookup"><span data-stu-id="ff42d-168">In those cases, your users need to initiate their own DSRs directly to Microsoft, and Microsoft fulfills the requests directly to the user.</span></span>

### <a name="third-party-products"></a><span data-ttu-id="ff42d-169">サード パーティ製品</span><span class="sxs-lookup"><span data-stu-id="ff42d-169">Third-party Products</span></span>

<span data-ttu-id="ff42d-170">Microsoft アカウント認証を介してアクセスしたサード パーティの製品とサービスの場合、すべてのデータ主体の要求は該当するサード パーティに送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff42d-170">For third-party products and services accessed through Microsoft account authentication, any data subject requests should be directed to the applicable third party.</span></span>

## <a name="data-subject-request-admin-tools"></a><span data-ttu-id="ff42d-171">データ主体の要求の管理ツール</span><span class="sxs-lookup"><span data-stu-id="ff42d-171">Data Subject Request admin tools</span></span>

- <span data-ttu-id="ff42d-172">**セキュリティ/コンプライアンス センター**: ユーザーが生成したデータは、[セキュリティ/コンプライアンス センター](https://aka.ms/stpsecurityandcompliance)を使用するか、アプリケーション内の機能を使用してエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ff42d-172">**Security & Compliance Center**: User-generated data is exported by the [Security & Compliance Center](https://aka.ms/stpsecurityandcompliance) or in-application features.</span></span>
- <span data-ttu-id="ff42d-173">**Azure AD 管理センター**: Azure Active Directory および関連サービスからのデータ主体の削除には、[Azure AD 管理センター](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff42d-173">**Azure AD Admin Center**: Delete a data subject from Azure Active Directory and related services using [Azure AD Admin Center](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/).</span></span>
- <span data-ttu-id="ff42d-174">**Microsoft データ ログのエクスポート**: システム生成のログは、テナント管理者が [Microsoft データ ログのエクスポート](https://aka.ms/MicrosoftGDPR)を使用することでエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ff42d-174">**Microsoft Data Log Export**: System-generated logs can be exported by tenant administrators using the [Microsoft Data Log Export](https://aka.ms/MicrosoftGDPR).</span></span>

## <a name="learn-more"></a><span data-ttu-id="ff42d-175">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ff42d-175">Learn more</span></span>

- [<span data-ttu-id="ff42d-176">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="ff42d-176">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
