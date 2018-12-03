---
title: GDPR のための Azure DevOps データ サブジェクト要求
keywords: Visual Studio Team Services、VSTS、Azure DevOps ドキュメント、プライバシー、GDPR
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 1200df7d9b079af4bba3edaeaa328709743ce65a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869424"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="4e1cb-103">GDPR のための Azure DevOps Services データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="4e1cb-103">Azure Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="4e1cb-p101">EU [一般データ保護規則 (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) では、ユーザー (この規則では*データ サブジェクト*と呼ばれる) に対して、*データ コントローラー*が収集した個人データを管理する権利が与えられます。データ コントローラー (または単に*コントローラー*) は、雇用主やその他の機関または組織です。GDPR の下では個人データは広範な定義がなされ、識別された、または識別可能な自然人に関連するあらゆるデータを指します。GDPR は、データ サブジェクトに対して、自分の個人データへの特定の権利を与えています。こうした権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、別のコントローラーに移動できるようにするための電子形式での受信などがあります。データ サブジェクトがコントローラーに個人データに関するアクションの実行を求める正式な要求は、*データ サブジェクト要求* (DSR) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-p101">The European Union [General Data Protection Regulation (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people, known in the regulation as *data subjects*, to manage the personal data that's collected by a *data controller*. A data controller, or just *controller*, is an employer or other type of agency or organization. Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data. These rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request*, or DSR.</span></span>

<span data-ttu-id="4e1cb-110">GDPR の一般的な情報については、[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-110">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

<span data-ttu-id="4e1cb-111">このガイドでは、Microsoft のツールを使用して、認証済みの (サインイン済みの) Azure DevOps Services (旧 Visual Studio Team Services) セッション中に収集された個人データをエクスポートまたは削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-111">This guide discusses how to use Microsoft tools to export or delete personal data collected during an authenticated (signed-in) session of Visual Studio Team Services (VSTS).</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="4e1cb-112">その他のプライバシー情報</span><span class="sxs-lookup"><span data-stu-id="4e1cb-112">Additional privacy information</span></span>

<span data-ttu-id="4e1cb-113">[Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)、[オンライン サービス使用条件 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)、および [Microsoft の GDPR コミットメント](/legal/gdpr)の記事では、弊社のデータ処理方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-113">The [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement), [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx), and [Microsoft's GDPR Commitments](/legal/gdpr) articles describe our data processing practices.</span></span>

## <a name="personal-data-we-collect"></a><span data-ttu-id="4e1cb-114">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="4e1cb-114">Personal data we collect</span></span>

<span data-ttu-id="4e1cb-p102">Microsoft は、Azure DevOps Services を運用および改善するためにユーザーからデータを収集します。Azure DevOps Services は 2 種類のデータを収集します&mdash;顧客データとシステム生成ログです。顧客データには、Azure DevOps Services がサービスを実行するために必要な、ユーザーを特定できるトランザクション データおよび対話データが含まれます。システム生成ログには、各製品の領域と機能ごとに集計されたサービス使用状況のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-p102">Microsoft collects data from users to operate and improve VSTS. VSTS collects two categories of data&mdash;customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that VSTS needs to operate the service. System-generated logs include service usage data that is aggregated for each product area and feature.</span></span>

## <a name="delete-azure-devops-data"></a><span data-ttu-id="4e1cb-119">Azure DevOps データの削除</span><span class="sxs-lookup"><span data-stu-id="4e1cb-119">Delete Azure DevOps data</span></span>

<span data-ttu-id="4e1cb-p103">関連する Azure DevOps Services の顧客データを削除し、システム生成ログ内で見つかる、個人を特定できるデータを匿名化するための最初の手順は、Azure Active Directory (AAD) の ID アカウントまたは Microsoft アカウント (MSA) を削除することです。Azure DevOps Services は、厳密な整合性、追跡可能性、および監査規則を持つレコードのシステムとして信頼されています。これらの既存の義務は、GDPR に関する弊社の削除および保持の義務に影響します。ID アカウントを削除しても、Azure DevOps 組織の個々の ID に関連付けられた成果物とレコードは、修正、削除または変更されません。Azure DevOps 組織全体が削除されたときは、その組織で見つかった個人を特定できるすべての関連データとシステム生成ログは、(Azure DevOps 組織の論理的な削除の必須期間である 30 日を経た後で) 弊社のシステムから削除されることを保証します。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-p103">The first step to delete associated VSTS customer data and to anonymize personally identifiable data found in system-generated logs is to close your Azure Active Directory (AAD) identity account or Microsoft Account (MSA). VSTS is relied upon as a system of record with strict integrity, traceability, and audit rules. These existing obligations affect our delete and retention obligations for GDPR. Closing the identity account does not alter, remove, or change artifacts and records associated with the individual identity in the VSTS account. We have ensured that when an entire VSTS account is deleted, all associated personally identifiable data and system-generated logs found in that account are removed from our system (after the requisite VSTS account 30-day soft-delete period).</span></span>

## <a name="export-azure-devops-data"></a><span data-ttu-id="4e1cb-125">Azure DevOps データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="4e1cb-125">Export Azure DevOps data</span></span>

<span data-ttu-id="4e1cb-126">コントローラーは、Azure DevOps サービスへのサインインに使用される ID プロバイダー (MSA または AAD) に応じて、2 つの方法のいずれかで、データ サブジェクトから収集された顧客データとシステム生成ログをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-126">Controllers can export customer data and system-generated logs collected from their data subjects by one of two methods, depending upon the identity provider (MSA or AAD) used to sign in to the VSTS service.</span></span>

- <span data-ttu-id="4e1cb-127">Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなど、Azure テナントに裏付けられたアカウントを使用して認証を行うユーザーは、「[GDPR のための Azure データ サブジェクト要求](../compliance/gdpr-dsr-azure.md)」の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-127">Users that authenticate using an account that is backed by an Azure tenant, for example, AAD account or MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](../compliance/gdpr-dsr-azure.md).</span></span>

- <span data-ttu-id="4e1cb-p104">MSA ID を使用して認証を行うユーザーは、この[プライバシー要求サイト](https://www.microsoft.com/concern/privacyrequest-msa)を使用して、複数の Microsoft サービス間で MSA ID に関連付けられたアクティビティ データを表示できます。このシナリオでは、ユーザーは自分の個人データのコントローラーです。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-p104">Users that authenticate using an MSA identity can use this [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) to view activity data tied to their MSA identity across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

## <a name="export-or-delete-issues"></a><span data-ttu-id="4e1cb-130">エクスポートまたは削除の問題</span><span class="sxs-lookup"><span data-stu-id="4e1cb-130">Export or delete issues</span></span>

<span data-ttu-id="4e1cb-131">AAD ID の場合、Azure Portal からデータをエクスポートまたは削除する際に問題が発生したときは、Azure Portal の **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理]** > **[他のセキュリティとコンプライアンスの要求]** > **[プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-131">For AAD identities, if you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management** > **Other Security and Compliance Request** > **Privacy Blade and GDPR Requests**.</span></span>

<span data-ttu-id="4e1cb-132">MSA ID の場合、プライバシー要求サイトからデータをエクスポートする際に問題が発生したときは、[プライバシー要求サイト](https://www.microsoft.com/concern/privacyrequest-msa)にログオンし、要求 Web フォームを介して Microsoft プライバシー チームからのヘルプへの要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-132">For MSA identities, if you run into issues while exporting data from the Privacy Request site, log on to the [Privacy Request site](https://www.microsoft.com/concern/privacyrequest-msa) and submit a request for help from the Microsoft Privacy team via the request webform.</span></span>

## <a name="learn-more"></a><span data-ttu-id="4e1cb-133">詳細の表示</span><span class="sxs-lookup"><span data-stu-id="4e1cb-133">Learn more</span></span>

<span data-ttu-id="4e1cb-p105">Microsoft は、ユーザーの Azure DevOps Services データが今後も確実に例外なく保護され、公開されないことを確約します。弊社がユーザーの Azure DevOps Services データを保護する方法の詳細については、[Azure DevOps Services データ保護の概要](/vsts/articles/team-services-security-whitepaper?view=vsts)に関するホワイトペーパーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1cb-p105">Microsoft is committed to ensuring that your VSTS data remains secure and private, without exception. Visit the [VSTS data protection overview](/vsts/articles/team-services-security-whitepaper?view=vsts) whitepaper to learn more about how we protect your VSTS data.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e1cb-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e1cb-136">See also</span></span>

- [<span data-ttu-id="4e1cb-137">一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント</span><span class="sxs-lookup"><span data-stu-id="4e1cb-137">Microsoft's GDPR commitments to customers of our generally available enterprise software products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="4e1cb-138">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="4e1cb-138">Microsoft Trust center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="4e1cb-139">Service Trust Portal</span><span class="sxs-lookup"><span data-stu-id="4e1cb-139">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="4e1cb-140">Microsoft プライバシー ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="4e1cb-140">Microsoft privacy dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="4e1cb-141">Microsoft Privacy Response Center</span><span class="sxs-lookup"><span data-stu-id="4e1cb-141">Microsoft privacy response center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="4e1cb-142">GDPR のための Azure データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="4e1cb-142">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)