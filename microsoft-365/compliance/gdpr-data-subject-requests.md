---
title: GDPR および CCPA のためのデータ対象要求
description: ''
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
ms.openlocfilehash: d2f9ac660c30b815d4ac381f347e1c1aa354ce0d
ms.sourcegitcommit: 2498cd4af90c31771167a1be9f8f12a96dc6500f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41916912"
---
# <a name="data-subject-requests-and-the-gdpr-and-ccpa"></a><span data-ttu-id="34a7e-103">データ対象要求と GDPR および CCPA</span><span class="sxs-lookup"><span data-stu-id="34a7e-103">Data Subject Requests and the GDPR and CCPA</span></span>

<span data-ttu-id="34a7e-104">一般データ保護規則 (GDPR) では、欧州連合 (EU) 内の人々に商品やサービスを提供する、または EU 居住者向けのデータの収集と分析を実行する会社に対して、新しい規則を導入します。GDPR は、個人やその企業がどの場所にあるかに関係なく適用されます。</span><span class="sxs-lookup"><span data-stu-id="34a7e-104">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="34a7e-105">詳細については、「[GDPR 概要トピック](gdpr.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a7e-105">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span>

<span data-ttu-id="34a7e-106">同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-106">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  <span data-ttu-id="34a7e-107">また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、“売上“ として分類された特定のデータ転送の “オプトアウト/オプトイン“ 要件を規定します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-107">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and “opt-out/ opt-in” requirements for certain data transfers classified as “sales".</span></span> <span data-ttu-id="34a7e-108">このドキュメントは、Microsoft の製品とサービスの使用における、GDPR および CCPA に基づくデータ主体の要求 (DSR) の完了に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-108">This document guides you to information on the completion of Data Subject Requests (DSRs) under the GDPR and CCPA using Microsoft products and services.</span></span>

- [<span data-ttu-id="34a7e-109">Office 365</span><span class="sxs-lookup"><span data-stu-id="34a7e-109">Office 365</span></span>](gdpr-dsr-Office365.md)
- [<span data-ttu-id="34a7e-110">Azure</span><span class="sxs-lookup"><span data-stu-id="34a7e-110">Azure</span></span>](gdpr-dsr-Azure.md)
- [<span data-ttu-id="34a7e-111">Intune</span><span class="sxs-lookup"><span data-stu-id="34a7e-111">Intune</span></span>](gdpr-dsr-Intune.md)
- [<span data-ttu-id="34a7e-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="34a7e-112">Dynamics 365</span></span>](gdpr-dsr-Dynamics365.md)
- [<span data-ttu-id="34a7e-113">Visual Studio ファミリ</span><span class="sxs-lookup"><span data-stu-id="34a7e-113">Visual Studio Family</span></span>](gdpr-dsr-visual-studio-family.md)
- [<span data-ttu-id="34a7e-114">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="34a7e-114">Azure DevOps Services</span></span>](gdpr-dsr-vsts.md)
- [<span data-ttu-id="34a7e-115">Microsoft サポート/プロフェッショナル サービス</span><span class="sxs-lookup"><span data-stu-id="34a7e-115">Microsoft Support and Professional Services</span></span>](gdpr-dsr-prof-services.md)

## <a name="terminology"></a><span data-ttu-id="34a7e-116">用語</span><span class="sxs-lookup"><span data-stu-id="34a7e-116">Terminology</span></span>

<span data-ttu-id="34a7e-117">このドキュメントで使用されている GDPR 用語の役に立つ定義:</span><span class="sxs-lookup"><span data-stu-id="34a7e-117">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="34a7e-118">*データ コントローラー (コントローラー)*: 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-118">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="34a7e-119">*個人データ*と*データ主体*: 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。</span><span class="sxs-lookup"><span data-stu-id="34a7e-119">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="34a7e-120">*処理者*: コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。</span><span class="sxs-lookup"><span data-stu-id="34a7e-120">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="34a7e-121">*顧客データ*: ビジネス運営における日々の業務で作成および保存されるデータ。</span><span class="sxs-lookup"><span data-stu-id="34a7e-121">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dsr"></a><span data-ttu-id="34a7e-122">DSR とは?</span><span class="sxs-lookup"><span data-stu-id="34a7e-122">What is a DSR?</span></span>

<span data-ttu-id="34a7e-123">一般データ保護規則 (GDPR) は、規制においてデータ主体と呼ばれる人に、雇用主または他の種類の機関や組織 (データ コントローラーまたは単にコントローラーと呼ばれます) によって収集された個人データを管理する権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="34a7e-123">The General Data Protection Regulation (GDPR) gives rights to people (known in the regulation as data subjects) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the data controller or just controller).</span></span> <span data-ttu-id="34a7e-124">GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの変更の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。</span><span class="sxs-lookup"><span data-stu-id="34a7e-124">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller.</span></span>

<span data-ttu-id="34a7e-125">カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-125">California Consumer Privacy Act (CCPA) provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  

<span data-ttu-id="34a7e-126">管理者は、要求されたアクションを実行するか、または管理者が DSR に対応できない理由についての説明を提供することで、各 DSR を速やかに検討し、実質的な対応を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-126">As a controller, you are obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller.</span></span> <span data-ttu-id="34a7e-127">コントローラーは、特定の DSR の適切な処理について自身の法律またはコンプライアンスのアドバイザーに相談する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-127">A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.</span></span>

<span data-ttu-id="34a7e-128">DSR の完了には、組織の GDPR コンプライアンス規則に従って、いくつかのプロセスが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-128">Several processes may be involved completing a DSR, subject to your organization’s GDPR-compliance rules.</span></span>
  
- <span data-ttu-id="34a7e-129">**検出**。</span><span class="sxs-lookup"><span data-stu-id="34a7e-129">**Discovery**.</span></span> <span data-ttu-id="34a7e-130">DSR を完了するために必要なデータを特定するプロセス。</span><span class="sxs-lookup"><span data-stu-id="34a7e-130">The process of determining what data is needed to complete a DSR.</span></span>
- <span data-ttu-id="34a7e-131">**アクセス**。</span><span class="sxs-lookup"><span data-stu-id="34a7e-131">**Access**.</span></span> <span data-ttu-id="34a7e-132">検出された情報の取得とデータ主体への潜在的な伝送。</span><span class="sxs-lookup"><span data-stu-id="34a7e-132">Retrieval and potential transmission to the data subject of discovered information.</span></span>
- <span data-ttu-id="34a7e-133">**修正**。</span><span class="sxs-lookup"><span data-stu-id="34a7e-133">**Rectify**.</span></span> <span data-ttu-id="34a7e-134">変更またはその他の要求された個人データの変更を実施します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-134">Implement changes or other requested personal data changes.</span></span>
- <span data-ttu-id="34a7e-135">**制限**。</span><span class="sxs-lookup"><span data-stu-id="34a7e-135">**Restrict**.</span></span> <span data-ttu-id="34a7e-136">アクセスを制限する、または Microsoft クラウドからデータを削除することにより、個人データのアクセスまたは処理を変更します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-136">Changing the access or processing of persona data by restricting access, or removing data from the Microsoft cloud.</span></span>
- <span data-ttu-id="34a7e-137">**エクスポート**。</span><span class="sxs-lookup"><span data-stu-id="34a7e-137">**Export**.</span></span> <span data-ttu-id="34a7e-138">GDPR の「データの移植の権利」で規定されているように、「構造化された一般的に使用されているコンピューターが読み取り可能な形式」の個人データをデータ主体に提供します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-138">Providing a “structured, commonly used, machine-readable format” of personal data to the data subject, as provided by the GDPR’s “right of data portability.”</span></span>
- <span data-ttu-id="34a7e-139">**削除**。</span><span class="sxs-lookup"><span data-stu-id="34a7e-139">**Delete**.</span></span> <span data-ttu-id="34a7e-140">Microsoft クラウドから個人データを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-140">Permanent removal of personal data from the Microsoft cloud.</span></span>

## <a name="specific-dsr-considerations"></a><span data-ttu-id="34a7e-141">特定の DSR に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="34a7e-141">Specific DSR Considerations</span></span>

### <a name="insights-generated-by-microsoft-products-or-services"></a><span data-ttu-id="34a7e-142">Microsoft の製品またはサービスにより生成された分析情報</span><span class="sxs-lookup"><span data-stu-id="34a7e-142">Insights generated by Microsoft Products or Services</span></span>

<span data-ttu-id="34a7e-143">[分析情報](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)はサービス (MyAnalytics など) によって生成される場合があります。Office 365 には、分析情報を使用するユーザーと組織にこの情報を提供するオンライン サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34a7e-143">[Insights](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) may be generated by services (MyAnalytics, etc.) Office 365 includes online services that provide insights to users and organizations that use them.</span></span> <span data-ttu-id="34a7e-144">これらのサービスによって生成されたデータによって、DSR に関連する個人データが生成される場合あります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-144">Data generated by these services may produce personal data relevant to a DSR.</span></span> <span data-ttu-id="34a7e-145">サービス固有の DSR プロセスに関する詳細については、以下のリストにあるリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a7e-145">Follow the link in the list below for details regarding service-specific DSR processes.</span></span>  

### <a name="dsrs-for-system-generated-logs"></a><span data-ttu-id="34a7e-146">システム生成ログに関する DSR</span><span class="sxs-lookup"><span data-stu-id="34a7e-146">DSRs for system-generated logs</span></span>

<span data-ttu-id="34a7e-147">Microsoft によって生成されたログと関連データには、"個人データ" の GDPR 定義に基づき個人に関するものとしてみなされるデータが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-147">Logs and related data generated by Microsoft may contain data deemed personal under GDPR's definition of "personal data."</span></span> <span data-ttu-id="34a7e-148">システム生成ログのデータの制限または修正はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="34a7e-148">Restricting or rectifying data in system-generated logs is not supported.</span></span> <span data-ttu-id="34a7e-149">システム生成ログのデータは、Microsoft のクラウド内で実行された実際のアクションや診断データを構成しているため、変更すると、アクションの履歴記録が損なわれ、詐欺やセキュリティのリスクが増大します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-149">Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data; modifications would compromise the historical record of actions and increase fraud and security risks.</span></span> <span data-ttu-id="34a7e-150">Microsoft は、DSR の完了に必要となる可能性があるシステム生成ログに対するアクセス、エクスポート、削除の各機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-150">Microsoft provides the ability to access, export, and delete system-generated logs that may be necessary to complete a DSR.</span></span> <span data-ttu-id="34a7e-151">該当するデータには次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-151">Examples of such data may include:</span></span>  

- <span data-ttu-id="34a7e-152">製品およびサービスの利用状況データ (ユーザー アクティビティ ログなど)</span><span class="sxs-lookup"><span data-stu-id="34a7e-152">Product and service usage data such as user activity logs</span></span>
- <span data-ttu-id="34a7e-153">ユーザー検索要求およびクエリ データ</span><span class="sxs-lookup"><span data-stu-id="34a7e-153">User search requests and query data</span></span>
- <span data-ttu-id="34a7e-154">ユーザーまたはその他のシステムによるシステム機能および相互作用の結果として、製品およびサービスによって生成されたデータ。</span><span class="sxs-lookup"><span data-stu-id="34a7e-154">Data generated by product and services resulting from system functionality and interaction by users or other systems.</span></span>  

### <a name="yammer-and-kaizala"></a><span data-ttu-id="34a7e-155">Yammer と Kaizala</span><span class="sxs-lookup"><span data-stu-id="34a7e-155">Yammer and Kaizala</span></span>

<span data-ttu-id="34a7e-p113">ユーザー アカウントを削除した場合、Yammer と Kaizala でシステム生成されたログは削除されません。これらのアプリケーションからデータを削除する場合は、次のいずれかの資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a7e-p113">Deleting a user’s account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following resources:</span></span>

- [<span data-ttu-id="34a7e-158">Yammer Enterprise で GDPR データ主体の要求を管理する</span><span class="sxs-lookup"><span data-stu-id="34a7e-158">Manage GDPR data subject requests in Yammer Enterprise</span></span>](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [<span data-ttu-id="34a7e-159">Kaizala でユーザーの組織データをエクスポートまたは削除する</span><span class="sxs-lookup"><span data-stu-id="34a7e-159">Export or delete a user's organizational data in Kaizala</span></span>](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a><span data-ttu-id="34a7e-160">国内クラウド</span><span class="sxs-lookup"><span data-stu-id="34a7e-160">National Clouds</span></span>

<span data-ttu-id="34a7e-161">一部の国内クラウドでは、グローバル IT 管理者がシステム生成ログを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-161">In some national clouds, a global IT Administrator needs to delete system-generated logs.</span></span>

### <a name="microsoft-services"></a><span data-ttu-id="34a7e-162">Microsoft サービス</span><span class="sxs-lookup"><span data-stu-id="34a7e-162">Microsoft Services</span></span>

<span data-ttu-id="34a7e-163">お客様の組織またはユーザーが Microsoft の製品とサービスに関連するサポートを受けるために Microsoft と連携している場合、このデータの一部に個人データが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-163">If your organization or users engage with Microsoft to receive,  support related to Microsoft products and services some of this data may contain personal data.</span></span> <span data-ttu-id="34a7e-164">詳細については、「[GDPR のための Microsoft サポート/プロフェッショナル サービス データ主体の要求](gdpr-dsr-prof-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a7e-164">For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](gdpr-dsr-prof-services.md).</span></span>

### <a name="microsoft-controller-products"></a><span data-ttu-id="34a7e-165">Microsoft コントローラー製品</span><span class="sxs-lookup"><span data-stu-id="34a7e-165">Microsoft Controller Products</span></span>

<span data-ttu-id="34a7e-166">状況によっては、組織のユーザーは Microsoft がデータ コントローラーである Microsoft の製品またはサービスにアクセスすることもあります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-166">In some circumstances, your organization’s users may access Microsoft products or services for which Microsoft is the data controller.</span></span> <span data-ttu-id="34a7e-167">このような場合、ユーザーは自分自身の DSR を Microsoft に対して直接開始する必要があります。また、Microsoft はユーザーに対する要求を直接満たします。</span><span class="sxs-lookup"><span data-stu-id="34a7e-167">In those cases, your users need to initiate their own DSRs directly to Microsoft, and Microsoft fulfills the requests directly to the user.</span></span>

### <a name="third-party-products"></a><span data-ttu-id="34a7e-168">サード パーティ製品</span><span class="sxs-lookup"><span data-stu-id="34a7e-168">Third-party Products</span></span>

<span data-ttu-id="34a7e-169">Microsoft アカウント認証を介してアクセスしたサード パーティの製品とサービスの場合、すべてのデータ主体の要求は該当するサード パーティに送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a7e-169">For third-party products and services accessed through Microsoft account authentication, any data subject requests should be directed to the applicable third party.</span></span>

## <a name="data-subject-request-admin-tools"></a><span data-ttu-id="34a7e-170">データ主体の要求の管理ツール</span><span class="sxs-lookup"><span data-stu-id="34a7e-170">Data Subject Request admin tools</span></span>

- <span data-ttu-id="34a7e-171">**セキュリティ/コンプライアンス センター**: ユーザーが生成したデータは、[セキュリティ/コンプライアンス センター](https://aka.ms/stpsecurityandcompliance)を使用するか、アプリケーション内の機能を使用してエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="34a7e-171">**Security & Compliance Center**: User-generated data is exported by the [Security & Compliance Center](https://aka.ms/stpsecurityandcompliance) or in-application features.</span></span>
- <span data-ttu-id="34a7e-172">**Azure AD 管理センター**: Azure Active Directory および関連サービスからのデータ主体の削除には、[Azure AD 管理センター](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="34a7e-172">**Azure AD Admin Center**: Delete a data subject from Azure Active Directory and related services using [Azure AD Admin Center](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/UserManagementMenuBlade/Allusers/menuId/).</span></span>
- <span data-ttu-id="34a7e-173">**Microsoft データ ログのエクスポート**: システム生成のログは、テナント管理者が [Microsoft データ ログのエクスポート](https://aka.ms/MicrosoftGDPR)を使用することでエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="34a7e-173">**Microsoft Data Log Export**: System-generated logs can be exported by tenant administrators using the [Microsoft Data Log Export](https://aka.ms/MicrosoftGDPR).</span></span>

## <a name="learn-more"></a><span data-ttu-id="34a7e-174">詳細情報</span><span class="sxs-lookup"><span data-stu-id="34a7e-174">Learn more</span></span>

- [<span data-ttu-id="34a7e-175">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="34a7e-175">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
