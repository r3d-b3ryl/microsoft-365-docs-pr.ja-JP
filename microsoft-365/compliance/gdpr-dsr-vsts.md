---
title: GDPR および CCPA のための Azure DevOps データ サブジェクト要求
keywords: Visual Studio Team Services、VSTS、Azure DevOps ドキュメント、プライバシー、GDPR、CCPA
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 4ae98f6e396bdca0f1f1a4d6d360cf062878ba73
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073274"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="b67f9-103">GDPR および CCPA のための Azure DevOps Services データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="b67f9-103">Azure DevOps Services Data Subject Requests for the GDPR and CCPA</span></span>

<span data-ttu-id="b67f9-p101">EU [一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) では、ユーザー (この規則では*データ サブジェクト*と呼ばれる) に対して、*データ コントローラー*が収集した個人データを管理する権利が与えられます。データ コントローラー (または単に*コントローラー*) は、雇用主やその他の機関または組織です。GDPR の下では個人データは広範な定義がなされ、識別された、または識別可能な自然人に関連するあらゆるデータを指します。GDPR は、データ サブジェクトに対して、自分の個人データへの特定の権利を与えています。こうした権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、別のコントローラーに移動できるようにするための電子形式での受信などがあります。データ サブジェクトがコントローラーに個人データに関するアクションの実行を求める正式な要求は、*データ サブジェクト要求* (DSR) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people, known in the regulation as *data subjects*, to manage the personal data that's collected by a *data controller*. A data controller, or just *controller*, is an employer or other type of agency or organization. Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data. These rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request*, or DSR.</span></span>

<span data-ttu-id="b67f9-110">同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、それらの個人情報の削除、アクセスおよび受信 (移植性) の権利などの GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="b67f9-110">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR’s Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span>  <span data-ttu-id="b67f9-111">また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、“売上“ として分類された特定のデータ転送の “オプトアウト/オプトイン“ 要件を規定します。</span><span class="sxs-lookup"><span data-stu-id="b67f9-111">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and “opt-out/ opt-in” requirements for certain data transfers classified as “sales".</span></span> <span data-ttu-id="b67f9-112">「販売」は広く定義されており、有価約因に関するデータの共有を含みます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-112">Sales are broadly defined to include the sharing of data for a valuable consideration.</span></span> <span data-ttu-id="b67f9-113">CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b67f9-113">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="b67f9-114">GDPR の一般的な情報については、[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b67f9-114">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

<span data-ttu-id="b67f9-115">このガイドでは、Microsoft のツールを使用して、認証済みの (サインイン済みの) Azure DevOps Services (旧 Visual Studio Team Services) セッション中に収集された個人データをエクスポートまたは削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b67f9-115">This guide discusses how to use Microsoft tools to export or delete personal data collected during an authenticated (signed-in) session of Azure DevOps Services (formerly known as Visual Studio Team Services).</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="b67f9-116">その他のプライバシー情報</span><span class="sxs-lookup"><span data-stu-id="b67f9-116">Additional privacy information</span></span>

<span data-ttu-id="b67f9-117">[Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)、[オンライン サービス使用条件 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)、および [Microsoft の GDPR コミットメント](/legal/gdpr)の記事では、弊社のデータ処理方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="b67f9-117">The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx), and [Microsoft's GDPR Commitments](/legal/gdpr) articles describe our data processing practices.</span></span>

## <a name="personal-data-we-collect"></a><span data-ttu-id="b67f9-118">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="b67f9-118">Personal data we collect</span></span>

<span data-ttu-id="b67f9-119">Microsoft では、Azure DevOps Services の運用および向上のために、ユーザーのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="b67f9-119">Microsoft collects data from users to operate and improve Azure DevOps Services.</span></span> <span data-ttu-id="b67f9-120">Azure DevOps Services では、2 つのカテゴリのデータを収集します。つまり、顧客データとシステム生成ログです。</span><span class="sxs-lookup"><span data-stu-id="b67f9-120">Azure DevOps Services collects two categories of data — customer data and system-generated logs.</span></span> <span data-ttu-id="b67f9-121">顧客データには、サービスを運用するために Azure DevOps Services で必要とされる、特定のユーザーを識別可能なトラザクション データおよび相互作用的データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-121">Customer data includes user-identifiable transactional and interactional data that Azure DevOps Services needs to operate the service.</span></span> <span data-ttu-id="b67f9-122">システム生成ログには、各製品領域と機能について集計されたサービスの利用状況データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-122">System-generated logs include service usage data that is aggregated for each product area and feature.</span></span>

## <a name="delete-azure-devops-data"></a><span data-ttu-id="b67f9-123">Azure DevOps データの削除</span><span class="sxs-lookup"><span data-stu-id="b67f9-123">Delete Azure DevOps data</span></span>

<span data-ttu-id="b67f9-124">関連付けられた Azure DevOps Services の顧客データの削除、およびシステム生成ログで確認される個人を識別可能なデータの匿名化の最初のステップは、Azure Active Directory (AAD) の ID アカウントまたは Microsoft アカウント (MSA) を閉じることです。</span><span class="sxs-lookup"><span data-stu-id="b67f9-124">The first step to delete associated Azure DevOps Services customer data and to anonymize personally identifiable data found in system-generated logs is to close your Azure Active Directory (AAD) identity account or Microsoft Account (MSA).</span></span> <span data-ttu-id="b67f9-125">Azure DevOps Services は、完全な統合性、追跡可能性、監査ルールを用いたレコードのシステムとして信頼されています。</span><span class="sxs-lookup"><span data-stu-id="b67f9-125">Azure DevOps Services is relied upon as a system of record with strict integrity, traceability, and audit rules.</span></span> <span data-ttu-id="b67f9-126">これらの既存の義務は、GDPR の削除と保持の義務に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-126">These existing obligations affect our delete and retention obligations for GDPR.</span></span> <span data-ttu-id="b67f9-127">IDアカウントを閉じても、Azure DevOps 組織の個別 ID に関連付けられた成果物およびレコードを修正、削除、変更することはありません。</span><span class="sxs-lookup"><span data-stu-id="b67f9-127">Closing the identity account does not alter, remove, or change artifacts and records associated with the individual identity in the Azure DevOps organization.</span></span> <span data-ttu-id="b67f9-128">Azure DevOps 組織全体が削除さたときに、すべての関連付けられた個人を識別可能なデータおよびその組織で確認されるシステム生成ログが、システムから削除されることを確実にしました (Azure DevOps 組織で必要な 30 日間の倫理的な削除の期間後)。</span><span class="sxs-lookup"><span data-stu-id="b67f9-128">We have ensured that when an entire Azure DevOps organization is deleted, all associated personally identifiable data, and system-generated logs found in that organization are removed from our system (after the requisite Azure DevOps organization 30-day soft-delete period).</span></span>

## <a name="export-azure-devops-data"></a><span data-ttu-id="b67f9-129">Azure DevOps データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="b67f9-129">Export Azure DevOps data</span></span>

<span data-ttu-id="b67f9-130">コントローラーは、Azure DevOps サービスへのサインインに使用される ID プロバイダー (MSA または AAD) に応じて、2 つの方法のいずれかで、データ サブジェクトから収集された顧客データとシステム生成ログをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-130">Controllers can export customer data and system-generated logs collected from their data subjects by one of two methods, depending upon the identity provider (MSA or AAD) used to sign in to the Azure DevOps service.</span></span>

- <span data-ttu-id="b67f9-131">Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなど、Azure テナントに裏付けられたアカウントを使用して認証を行うユーザーは、「[GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)」の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b67f9-131">Users that authenticate using an account that is backed by an Azure tenant, for example, AAD account or MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>

- <span data-ttu-id="b67f9-p105">MSA ID を使用して認証を行うユーザーは、この[プライバシー要求サイト](https://www.microsoft.com/concern/privacyrequest-msa)を使用して、複数の Microsoft サービス間で MSA ID に関連付けられたアクティビティ データを表示できます。このシナリオでは、ユーザーは自分の個人データのコントローラーです。</span><span class="sxs-lookup"><span data-stu-id="b67f9-p105">Users that authenticate using an MSA identity can use this [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) to view activity data tied to their MSA identity across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

## <a name="export-or-delete-issues"></a><span data-ttu-id="b67f9-134">エクスポートまたは削除の問題</span><span class="sxs-lookup"><span data-stu-id="b67f9-134">Export or delete issues</span></span>

<span data-ttu-id="b67f9-135">AAD ID の場合、Azure Portal からデータをエクスポートまたは削除する際に問題が発生したときは、Azure Portal の **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理]** > **[他のセキュリティとコンプライアンスの要求]** > **[プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。</span><span class="sxs-lookup"><span data-stu-id="b67f9-135">For AAD identities, if you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management** > **Other Security and Compliance Request** > **Privacy Blade and GDPR Requests**.</span></span>

<span data-ttu-id="b67f9-136">MSA ID の場合、プライバシー要求サイトからデータをエクスポートする際に問題が発生したときは、[プライバシー要求サイト](https://www.microsoft.com/concern/privacyrequest-msa)にログオンし、要求 Web フォームを介して Microsoft プライバシー チームからのヘルプへの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b67f9-136">For MSA identities, if you run into issues while exporting data from the Privacy Request site, log on to the [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) and submit a request for help from the Microsoft Privacy team via the request webform.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b67f9-137">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="b67f9-137">Learn more</span></span>

<span data-ttu-id="b67f9-p106">Microsoft は、ユーザーの Azure DevOps Services データが今後も確実に例外なく保護され、公開されないことを確約します。弊社がユーザーの Azure DevOps Services データを保護する方法の詳細については、[Azure DevOps Services データ保護の概要](/vsts/articles/team-services-security-whitepaper?view=vsts)に関するホワイトペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b67f9-p106">Microsoft is committed to ensuring that your Azure DevOps Services data remains secure and private, without exception. Visit the [Azure DevOps Services data protection overview](/vsts/articles/team-services-security-whitepaper?view=vsts) whitepaper to learn more about how we protect your Azure DevOps Services data.</span></span>

## <a name="see-also"></a><span data-ttu-id="b67f9-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b67f9-140">See also</span></span>

- [<span data-ttu-id="b67f9-141">一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント</span><span class="sxs-lookup"><span data-stu-id="b67f9-141">Microsoft's GDPR commitments to customers of our generally available enterprise software products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="b67f9-142">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="b67f9-142">Microsoft Trust center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="b67f9-143">Service Trust Portal</span><span class="sxs-lookup"><span data-stu-id="b67f9-143">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="b67f9-144">Microsoft プライバシー ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="b67f9-144">Microsoft privacy dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="b67f9-145">Microsoft Privacy Response Center</span><span class="sxs-lookup"><span data-stu-id="b67f9-145">Microsoft privacy response center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="b67f9-146">GDPR のための Azure データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="b67f9-146">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
