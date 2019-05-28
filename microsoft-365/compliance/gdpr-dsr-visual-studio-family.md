---
title: GDPR に関する Visual Studio ファミリ データ主体要求
description: GDPR に関する Visual Studio ファミリ データ主体要求
keywords: Visual Studio、Visual Studio Code、Visual Studio for Mac、Visual Studio ドキュメント、プライバシー、GDPR
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 744935cb41e1521970e6fac05493129eaaf7910d
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431548"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="92207-104">GDPR に関する Visual Studio ファミリ データ主体要求</span><span class="sxs-lookup"><span data-stu-id="92207-104">Visual Studio Family Data Subject Requests for the GDPR</span></span>

<span data-ttu-id="92207-p101">EU の[一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、ユーザー (規則では_データ主体_と呼ばれる) に対して個人データを管理する権利を与えています。個人データは、GDPR の下で特定されたまたは特定可能な自然人に関するあらゆるデータとして広く定義されています。GDPR は、個人データに対するデータ主体固有の権利を与えています。これらの権利には、個人データのコピーの取得、その修正の要求、その処理の制限、その削除、またはその電子形式での受信が含まれます。データ主体からデータ コントローラー (個人データを制御する雇用主、その他の種類の代理人、または組織) にデータ主体の個人データに対するアクションの実行を求める正式な要求は、_データ主体要求_ (DSR) と呼ばれます。GDPR に関する一般情報については、「[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as _data subjects_) to manage their personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format. A formal request by a data subject to a data controller (an employer or other type of agency or organization that has control over personal data) to take an action on that data subject's personal data is called a _data subject request_ or DSR. For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="products-covered-by-this-guide"></a><span data-ttu-id="92207-110">このガイドの対象製品</span><span class="sxs-lookup"><span data-stu-id="92207-110">Products covered by this guide</span></span>

<span data-ttu-id="92207-p102">このガイドでは、Microsoft ツールを使用して、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能の認証済み (サインイン済み) セッション使用時に収集された個人データをエクスポートまたは削除する方法について説明します。また、Visual Studio 開発者コミュニティ、NuGet.org、および ASP.NET Web サイトの使用時に収集された個人データに対するデータ主体要求の発行方法についても説明します。これらの製品を使用すれば、Microsoft 以外のツールと拡張機能の使用が可能になりますが、Microsoft はこれらのツールと拡張機能のデータ プロセッサまたはコントローラーではありません。これらのツールまたは拡張機能については、それぞれのプロバイダーに問い合わせて個人データと収集に関するポリシーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92207-p102">This guide discusses how to use Microsoft tools to export or delete personal data collected during authenticated (signed-in) session usage of Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. This guide also covers how to make data subject requests for personal data collected when using Visual Studio Developer Community, NuGet.org, and the ASP.NET website. These products may enable use of non-Microsoft tools and extensions, and Microsoft is not a data processor or controller for these tools and extensions. Users should contact the tool or extension provider to understand the personal data and collection policies for these tools and extensions.</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="92207-115">その他のプライバシー情報</span><span class="sxs-lookup"><span data-stu-id="92207-115">Additional privacy information</span></span>

<span data-ttu-id="92207-116">製品に付属しているマイクロソフト ソフトウェア ライセンス条項、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?LinkId=660726)、および [Microsoft の GDPR コミットメント](https://docs.microsoft.com/legal/gdpr)にデータ処理慣行が記載されています。</span><span class="sxs-lookup"><span data-stu-id="92207-116">The Microsoft Software License Terms accompanying the products, the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=660726), and [Microsoft's GDPR Commitments](https://docs.microsoft.com/legal/gdpr) describe our data processing practices.</span></span>

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a><span data-ttu-id="92207-117">Visual Studio、Visual Studio for Mac、および Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="92207-117">Visual Studio, Visual Studio for Mac, and Visual Studio Code</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="92207-118">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="92207-118">Personal data we collect</span></span>

<span data-ttu-id="92207-p103">GDPR に基づくデータ プロセッサとして、Microsoft は、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能に対するエクスペリエンスを提供し、これらを改善するために必要なデータをユーザーから収集します。データは、顧客データとシステム生成ログという 2 つのカテゴリに分けられます。顧客データには、これらの製品が提供しているサービスを実行するために必要なユーザーを特定できるトランザクション データと相互作用データが含まれます。たとえば、ユーザーにローミング設定などの個人的なエクスペリエンスを提供するには、ユーザー アカウント情報と設定データを収集する必要があります。システム生成ログは、問題を特定してトラブルシューティングし、弊社の製品やサービスを向上させるために使用される、利用状況データまたは診断データで、ユーザー名などのエンドユーザーに関する特定可能な情報が含まれている場合もあります。システム生成ログは、少なくとも 18 か月間保持されます。例として、システム生成ログは、次のサンプルで示すように、製品使用の日ごとに集計され、使用日、使用された製品 ("Visual Studio 2017" など)、実行されたアクション ("vs/core/packagecostsummary/solutionload" など)、およびアクションの実行回数が記録されます。</span><span class="sxs-lookup"><span data-stu-id="92207-p103">As a data processor under the GDPR, Microsoft collects the data we need from users to provide experiences for and improve Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. There are two categories of data: customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that these products need to perform the service they provide. For example, to provide users with personalized experiences such as roaming settings, we need to collect user account information and settings data. System-generated logs are usage or diagnostic data that are used to help identify and troubleshoot problems and improve our products and services, and may also contain identifiable information about end users, such as a user name. System-generated logs are retained for no more than 18 months. As an example, system-generated logs are aggregated for each day of product usage and include the usage date, the product used (for example, "Visual Studio 2017"), the action you took (for example, "vs/core/packagecostsummary/solutionload"), and the number of times the action was taken, as shown in this sample:</span></span>

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

<span data-ttu-id="92207-126">詳細については、「[Visual Studio によって収集されるシステム生成ログ](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-126">For more information, see [System-generated logs collected by Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection).</span></span>

<span data-ttu-id="92207-p104">認証済みの ID に関連付けられた個人データのみが DSR で処理されます。そのため、たとえば、Visual Studio Code はサインインをサポートしていないため、そこからのシステム生成ログは認証済みの ID に関連付けられず、処理されません。ただし、Visual Studio Code に対する一部の Microsoft 拡張機能が認証済みのデータを提供するため、このデータは DSR で処理されます。詳細については、「[GDPR と Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)」を参照してください。一般に、Visual Studio 2013 以前のデータは保存されませんが、後述するように、特定の拡張機能とコンポーネントが、認証済みの ID に関連付けられたデータを提供する場合があるため、DSR で処理されます。</span><span class="sxs-lookup"><span data-stu-id="92207-p104">Only personal data that is attached to authenticated identities can be serviced by a DSR. So, for example, because Visual Studio Code does not support sign-in, system-generated logs from it are not attached to an authenticated identity and cannot be serviced. However, some Microsoft extensions for Visual Studio Code may provide authenticated data, and this data can be serviced by a DSR. For more information, see [GDPR and Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). In general, we do not store data for Visual Studio 2013 and earlier; however, certain extensions and components may provide data attached to authenticated identities and can be serviced by a DSR as outlined below.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="92207-132">ユーザーによる個人データの管理方法</span><span class="sxs-lookup"><span data-stu-id="92207-132">How users can control personal data</span></span>

<span data-ttu-id="92207-133">Visual Studio 2015 以降、Visual Studio for Mac、および Visual Studio Code は、ユーザーがデータ収集を停止したり、コントローラーが既に収集されたデータをエクスポートまたは削除したりするための以下の手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="92207-133">Visual Studio 2015 and later, Visual Studio for Mac, and Visual Studio Code provide the following means for your users to stop data collection, and for you as controller to export, or delete data that has already been gathered.</span></span>

#### <a name="in-app-settings"></a><span data-ttu-id="92207-134">アプリ内設定</span><span class="sxs-lookup"><span data-stu-id="92207-134">In-app settings</span></span>

<span data-ttu-id="92207-p105">ユーザーは、これらの製品のプライバシー設定を管理できます。詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-p105">Users can control the privacy settings for these products. For more information, see the following</span></span>

- <span data-ttu-id="92207-137">[Visual Studio でプライバシー設定を管理する方法](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program)</span><span class="sxs-lookup"><span data-stu-id="92207-137">[How to manage privacy settings in Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="92207-138">[Visual Studio for Mac でプライバシー設定を管理する方法](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program)</span><span class="sxs-lookup"><span data-stu-id="92207-138">[How to manage privacy settings in Visual Studio for Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="92207-139">[Visual Studio Code でテレメトリ レポート機能を無効にする方法](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)</span><span class="sxs-lookup"><span data-stu-id="92207-139">[How to disable telemetry reporting in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).</span></span>

#### <a name="exporting-or-deleting-data"></a><span data-ttu-id="92207-140">データのエクスポートまたは削除</span><span class="sxs-lookup"><span data-stu-id="92207-140">Exporting or deleting data</span></span>

<span data-ttu-id="92207-p106">コントローラーは、Visual Studio ファミリ製品または Microsoft 拡張機能が登録された方法に応じて、2 つの方法のどちらかでデータ主体から収集された顧客データとシステム生成ログを管理できます。両方の方法を使用しなければならない場合もあります。両方の方法を使用すれば、コントローラーは、その方法によって管理されているアクティビティ履歴のコピーをダウンロードすることができます。AAD または MSA アカウントを閉鎖すると、関連する Visual Studio 顧客データが削除され、これらの製品に関するシステム生成ログ内の個人を特定できるデータが匿名化されます。匿名化されたシステム生成ログは少なくとも 18 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="92207-p106">Controllers can manage customer data and system-generated logs collected from their data subjects by one of two methods, depending upon how their Visual Studio Family product or Microsoft extensions were registered. In some cases, both methods must be used. Both methods allow Controllers to download a copy of their activity history managed by that method. Closure of an AAD or MSA account deletes associated Visual Studio customer data, and anonymizes personally identifiable data in system-generated logs pertaining to these products. Anonymized system-generated logs are retained for no more than 18 months.</span></span>

- <span data-ttu-id="92207-146">Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなどの Azure テナントにより裏付けられるアカウントを使用して、Visual Studio ファミリ製品を登録したユーザーは、「[GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)」の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="92207-146">Users that have registered a Visual Studio Family product by using an account that is backed by an Azure tenant[](gdpr-dsr-azure.md)for example, AAD account or  MSA account associated with an Azure subscriptioncan follow the instructions in Azure Data Subject Requests for the GDPR.</span></span>
- <span data-ttu-id="92207-p107">Microsoft アカウント (MSA) を使用した複数のアカウントなどの Azure テナントによって裏付けられたアカウントを使用せずに Visual Studio ファミリ製品を登録したユーザーは、Microsoft アカウント経由で使用可能な [Ｗeb ベースの Microsoft Privacy Response Center](https://aka.ms/userprivacysite) を使用して、複数の Microsoft サービス 全体で Microsoft アカウントに紐づけられたアクティビティ データを表示、管理、および削除できます。このシナリオでは、ユーザーは自分の個人データのコントローラーです。</span><span class="sxs-lookup"><span data-stu-id="92207-p107">Users that have registered a Visual Studio Family product without an account that is backed by an Azure tenant[](https://aka.ms/userprivacysite)for example many accounts using a Microsoft Account (MSA)can use the web-based Microsoft Privacy Response Center available through their Microsoft account to view, control, and delete activity data tied to their Microsoft account across multiple Microsoft services. In this scenario, the user is a controller for their own personal data.</span></span>

> [!NOTE]
> <span data-ttu-id="92207-149">MSA アカウント所有者がアカウントを削除すると、アカウントが Azure テナントによって裏付けされているかどうかに関係なく、これらの製品に関するすべての個人を特定できるデータが削除され、システム生成ログが匿名化されます。</span><span class="sxs-lookup"><span data-stu-id="92207-149">When an MSA account holder deletes their account, all their personally identifiable data pertaining to these products is deleted, whether the account is backed by an Azure tenant or not, and system-generated logs are anonymized.</span></span>

<span data-ttu-id="92207-p108">Visual Studio 2013 では、収集されたデータが匿名化されます。Visual Studio 2012 以前のリリースでは、データが受信時に即座に削除されます。どちらの場合も、後で表示、エクスポート、または削除するものはありません。</span><span class="sxs-lookup"><span data-stu-id="92207-p108">For Visual Studio 2013, the data we collect is anonymized. For Visual Studio 2012 and prior releases, we immediately delete the data upon receipt. In both cases, there is nothing to view, export, or delete at a later time.</span></span>

## <a name="visual-studio-developer-community"></a><span data-ttu-id="92207-153">Visual Studio 開発者コミュニティ</span><span class="sxs-lookup"><span data-stu-id="92207-153">Visual Studio Developer Community</span></span>

<span data-ttu-id="92207-p109">[開発者コミュニティ](https://developercommunity.visualstudio.com) Web サイト経由の[一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 要求がサポートされています。フィードバック データを表示、エクスポート、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="92207-p109">We support [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) requests through the [Developer Community](https://developercommunity.visualstudio.com) website. You can View, Export, or Delete your feedback data.</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="92207-156">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="92207-156">Personal data we collect</span></span>

<span data-ttu-id="92207-p110">Microsoft は、Visual Studio ファミリ製品を使用して報告された問題を再現してトラブルシューティングするためのデータを収集します。このデータには、個人データとパブリック フィードバックが含まれます。個人データには、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92207-p110">Microsoft collects data to help us reproduce and troubleshoot issues you report with Visual Studio Family products. This data includes personal data and public feedback. Personal data includes:</span></span>

- <span data-ttu-id="92207-160">[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="92207-160">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="92207-161">ユーザー設定と通知</span><span class="sxs-lookup"><span data-stu-id="92207-161">Preferences and notifications;</span></span>
- <span data-ttu-id="92207-162">[Visual Studio で問題を報告する](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイルとシステム生成ログ</span><span class="sxs-lookup"><span data-stu-id="92207-162">Attachments and system-generated logs you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com);</span></span>
- <span data-ttu-id="92207-163">投票</span><span class="sxs-lookup"><span data-stu-id="92207-163">Your votes.</span></span>

<span data-ttu-id="92207-164">パブリック フィードバックには、問題、コメント、および解決策が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92207-164">Public feedback includes: reported problems, comments, and solutions.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="92207-165">ユーザーによる個人データの管理方法</span><span class="sxs-lookup"><span data-stu-id="92207-165">How users can control personal data</span></span>

#### <a name="view"></a><span data-ttu-id="92207-166">表示</span><span class="sxs-lookup"><span data-stu-id="92207-166">View</span></span>

<span data-ttu-id="92207-167">フィードバック関連データを表示するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92207-167">To View your feedback-related data, follow these steps:</span></span>

1. <span data-ttu-id="92207-168">[開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="92207-168">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="92207-169">右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="92207-169">From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="92207-170">**[プロファイル]**、**[通知]**、**[アクティビティ]**、および **[添付ファイル]** タブのいずれかをクリックして、フィードバック システムに送信されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="92207-170">Click on any of the **Profile**, **Notifications**, **Activity**, and **Attachments** tabs to view the data submitted to the feedback systems.</span></span>
   1. <span data-ttu-id="92207-171">**プロファイル**は、[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイルを意味し、ユーザー名、電子メール アドレス、自己紹介などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92207-171">**Profile** refers to your [Developer Community](https://developercommunity.visualstudio.com) profile, including user name, email address, about, etc.</span></span>
   2. <span data-ttu-id="92207-172">\*\*通知は、受信する電子メール通知の管理方法です。</span><span class="sxs-lookup"><span data-stu-id="92207-172">Notifications is how you control the email notifications you receive.</span></span>
   3. <span data-ttu-id="92207-173">**アクティビティ**は、アクティブだったフィードバック項目 (投稿済み、コメント済みなど) と実行されたアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="92207-173">**Activity** will give you the feedback items you have been active on (posted, commented, etc.), and the activities performed.</span></span>
   4. <span data-ttu-id="92207-174">**添付ファイル**は、`FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM` のような形式の添付ファイル履歴のリストです。</span><span class="sxs-lookup"><span data-stu-id="92207-174">**Attachments** is a list of your attachment history in a format like `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.</span></span>

#### <a name="export"></a><span data-ttu-id="92207-175">エクスポート</span><span class="sxs-lookup"><span data-stu-id="92207-175">Export</span></span>

<span data-ttu-id="92207-p112">DSR の一部として、フィードバック データをエクスポートすることができます。次のデータを含む 1 つ以上の .zip アーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="92207-p112">You can export your feedback data as part of DSR. We will create one or more .zip archives that will include:</span></span>

- <span data-ttu-id="92207-178">[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="92207-178">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="92207-179">ユーザー設定と通知設定</span><span class="sxs-lookup"><span data-stu-id="92207-179">Preferences and notification settings;</span></span>
- <span data-ttu-id="92207-180">[Visual Studio で問題を報告する](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイル</span><span class="sxs-lookup"><span data-stu-id="92207-180">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>

> [!NOTE]
> <span data-ttu-id="92207-181">入力されたパブリック フィードバック (コメント、解決策、および報告済みの問題) がアーカイブから除外されます。</span><span class="sxs-lookup"><span data-stu-id="92207-181">We will exclude the following public feedback you have provided from your archive: comments, solutions, reported problems.</span></span>

<span data-ttu-id="92207-182">エクスポートを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92207-182">To start an Export, follow these steps:</span></span>

1. <span data-ttu-id="92207-183">[開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="92207-183">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="92207-184">右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="92207-184">From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="92207-185">**[プライバシー]** タブをクリックしてから、**[アーカイブの作成]** をクリックし、データのエクスポートを要求します。</span><span class="sxs-lookup"><span data-stu-id="92207-185">Click the **Privacy** tab, and then click **Create an archive** to request exporting your data.</span></span>
3. <span data-ttu-id="92207-p114">**[アーカイブ状態]** が、データの準備中であることを示すように更新されます。データが使用可能になるまでの時間の長さは、エクスポートする必要があるデータ量に依存します。</span><span class="sxs-lookup"><span data-stu-id="92207-p114">The **Archive Status** will update to show that we are preparing the data. The length of time before the data is available depends on the amount of data we need to export.</span></span>
4. <span data-ttu-id="92207-188">データの準備ができると、電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="92207-188">Once the data is ready, we will send you an email.</span></span>
5. <span data-ttu-id="92207-189">電子メール内の **[アーカイブのダウンロード]** をクリックするか、[プライバシー] タブに戻ってデータをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="92207-189">Click **Download Archive** in the email, or go back to the Privacy tab to download your data.</span></span>

> [!NOTE]
> - <span data-ttu-id="92207-190">[通知] タブで通知を受信しないように選択した場合は、電子メールが送信されません。</span><span class="sxs-lookup"><span data-stu-id="92207-190">We will not send email if you chose not to receive notifications in the Notifications tab.</span></span>
> - <span data-ttu-id="92207-191">再度エクスポートを要求すると、古いアーカイブが削除され、新しいアーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="92207-191">If you request Export again, we will remove your old archive and create a new one.</span></span>

#### <a name="delete"></a><span data-ttu-id="92207-192">削除</span><span class="sxs-lookup"><span data-stu-id="92207-192">Delete</span></span>

<span data-ttu-id="92207-193">削除すると、[開発者コミュニティ](https://developercommunity.visualstudio.com)から次の情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="92207-193">Deleting will remove the following information about you from [Developer Community](https://developercommunity.visualstudio.com):</span></span>

- <span data-ttu-id="92207-194">プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="92207-194">Profile information;</span></span>
- <span data-ttu-id="92207-195">ユーザー設定と通知設定</span><span class="sxs-lookup"><span data-stu-id="92207-195">Preferences and notification settings;</span></span>
- <span data-ttu-id="92207-196">[Visual Studio で問題を報告する](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイル</span><span class="sxs-lookup"><span data-stu-id="92207-196">Attachments you provided by [reporting a problem in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>
- <span data-ttu-id="92207-197">投票</span><span class="sxs-lookup"><span data-stu-id="92207-197">Your votes</span></span>

> [!NOTE]
> <span data-ttu-id="92207-198">公開情報 (コメント、解決策、報告済みの問題) は削除されずに、匿名化されます。</span><span class="sxs-lookup"><span data-stu-id="92207-198">We will not delete, but will anonymize, the following public information: your comments, your solutions, problems that you reported.</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="92207-199">AAD または MSA アカウントを削除すると、[開発者コミュニティ](https://developercommunity.visualstudio.com)の削除プロセスがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="92207-199">Delete of an AAD or MSA account triggers the Delete process for [Developer Community](https://developercommunity.visualstudio.com).</span></span>

<span data-ttu-id="92207-200">削除を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="92207-200">To initiate a Delete, follow these steps:</span></span>

1. <span data-ttu-id="92207-p115">[開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="92207-p115">Sign into [Developer Community](https://developercommunity.visualstudio.com). From the top right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="92207-203">**[プライバシー]** タブをクリックしてから、**[データとアカウントの削除]** をクリックし、データの削除を開始します。</span><span class="sxs-lookup"><span data-stu-id="92207-203">Click the **Privacy** tab, and then click **Delete your data and account** to start deleting your data.</span></span>
3. <span data-ttu-id="92207-204">確認画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="92207-204">A confirmation screen will appear.</span></span>
4. <span data-ttu-id="92207-205">ボックスに "delete" と入力してから、**[マイ アカウントの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92207-205">Type "delete" in the box, and then click **Delete my account**.</span></span>

<span data-ttu-id="92207-206">**[マイ アカウントの削除]** をクリックすると:</span><span class="sxs-lookup"><span data-stu-id="92207-206">Once you click **Delete my account:**</span></span>

- <span data-ttu-id="92207-207">サインアウトされます。</span><span class="sxs-lookup"><span data-stu-id="92207-207">We will sign you out.</span></span>
- <span data-ttu-id="92207-208">[開発者コミュニティ](https://developercommunity.visualstudio.com) アカウント、個人データ、および添付ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="92207-208">We will delete your [Developer Community](https://developercommunity.visualstudio.com) account, your personal data, and attachments.</span></span>
- <span data-ttu-id="92207-p116">パブリック フィードバックが匿名化されます。パブリック フィードバックは、開発者コミュニティでは使用可能なままで、匿名ユーザーから報告されたかのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="92207-p116">We will anonymize your public feedback. Your public feedback will remain available on Developer Community, and will be indicated as reported by an Anonymous user.</span></span>
- <span data-ttu-id="92207-211">アカウントを削除しても、電子メールは送信されません。これは、システム内に存在しなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="92207-211">We won't email you after we delete your account, because you will no longer be present in the system.</span></span>
- <span data-ttu-id="92207-212">新しい問題を報告するか、[開発者コミュニティ](https://developercommunity.visualstudio.com)にログインすると、新しいユーザーとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="92207-212">If you report a new problem or log into [Developer Community](https://developercommunity.visualstudio.com), you will be identified as a new user.</span></span>
- <span data-ttu-id="92207-213">[開発者コミュニティ](https://developercommunity.visualstudio.com)からアカウントを削除しても、他の Microsoft サービスからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="92207-213">If you delete your account from [Developer Community](https://developercommunity.visualstudio.com), we will not delete it from other Microsoft services.</span></span>

## <a name="xamarin-forums-and-bugzilla"></a><span data-ttu-id="92207-214">Xamarin フォーラムと Bugzilla</span><span class="sxs-lookup"><span data-stu-id="92207-214">Xamarin Forums and Bugzilla</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="92207-215">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="92207-215">Personal Data We Collect</span></span>

<span data-ttu-id="92207-p117">[Xamarin フォーラム](https://forums.xamarin.com) ユーザー コミュニティと [Xamarin Bugzilla](https://bugzilla.xamarin.com/) バグ報告 Web サイト経由で、Microsoft は、Microsoft の製品とサービスで発生した可能性のある問題の再現とトラブルシューティングを支援するために提供されたデータを収集します。このデータには、個人データとパブリック フィードバックが含まれます。Microsoft が収集する個人データは、ユーザー アカウント データ (Xamarin フォーラムまたは Bugzilla アカウントに関連付けられたユーザー名や電子メール アドレスなど) で、収集するパブリック フィードバックには、Xamarin フォーラムや Xamarin Bugzilla バグ報告 Web サイト経由で提供されたバグ、問題、コメント、および解決策が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92207-p117">Through the [Xamarin Forums](https://forums.xamarin.com) user community and [Xamarin Bugzilla](https://bugzilla.xamarin.com/) bug reporting websites, Microsoft collects data you provide to help us reproduce and troubleshoot issues you may have with Microsoft products and services. This data includes personal data and public feedback. The personal data we collect is user account data (for example, user names and email addresses associated with your Xamarin Forums or Bugzilla accounts), and the public feedback we collect includes bugs, problems, comments, and solutions you provide via the Xamarin Forums or Xamarin Bugzilla bug reporting website.</span></span>

### <a name="how-you-can-control-your-data"></a><span data-ttu-id="92207-219">データの管理方法</span><span class="sxs-lookup"><span data-stu-id="92207-219">How You Can Control Your Data</span></span>

#### <a name="xamarin-forums"></a><span data-ttu-id="92207-220">Xamarin フォーラム</span><span class="sxs-lookup"><span data-stu-id="92207-220">Xamarin Forums</span></span>

##### <a name="view"></a><span data-ttu-id="92207-221">表示</span><span class="sxs-lookup"><span data-stu-id="92207-221">View</span></span>

<span data-ttu-id="92207-p118">アクティブな Xamarin フォーラム アカウントを持っているユーザーは、Xamarin フォーラム アカウント ページから個人データとパブリック フィードバック (投稿済みのスレッドと投稿のすべてなど) を表示できます。ユーザーは、アカウント ページ経由で個人データを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="92207-p118">Users with active Xamarin Forums accounts may view their personal data and public feedback (for example, all of their posted threads and posts) from their Xamarin Forums account page. Users may also edit their personal data through their account page.</span></span>

##### <a name="export"></a><span data-ttu-id="92207-224">エクスポート</span><span class="sxs-lookup"><span data-stu-id="92207-224">Export</span></span>

<span data-ttu-id="92207-p119">Xamarin フォーラムは、サードパーティの Vanilla フォーラムでホストされます。公開データのエクスポートを要求するには、ユーザーが forums@xamarin.com (Xamarin チームによって監視される) に問い合わせる必要があります。その後で、Vanilla フォーラムを直接操作してこの要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="92207-p119">Xamarin Forums are hosted by a third party, Vanilla Forums. To request export of your public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then work directly with Vanilla Forums to process this request.</span></span>

##### <a name="delete"></a><span data-ttu-id="92207-228">削除する</span><span class="sxs-lookup"><span data-stu-id="92207-228">Delete</span></span>

<span data-ttu-id="92207-p120">Xamarin Forumは、サードパーティの Vanilla Forums によりホストされています。個人データと公開データの削除を依頼するには、forums@xamarin.com (Xamarin チームによってモニターされています) にお問い合わせください。その後に、ユーザーからの個人データ削除依頼を手動で処理いたします。</span><span class="sxs-lookup"><span data-stu-id="92207-p120">Xamarin Forums are hosted by a third party, Vanilla Forums. To request deletion of your personal and public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then manually service the user's personal data deletion request.</span></span>

#### <a name="bugzilla-for-xamarin"></a><span data-ttu-id="92207-232">Xamarin 用の Bugzilla</span><span class="sxs-lookup"><span data-stu-id="92207-232">Bugzilla for Xamarin</span></span>

##### <a name="view"></a><span data-ttu-id="92207-233">表示</span><span class="sxs-lookup"><span data-stu-id="92207-233">View</span></span>

<span data-ttu-id="92207-234">アクティブな Xamarin Bugzilla アカウントを持っているユーザーは、Xamarin Bugzilla ホーム ページ上の適切なリンクをクリックすることにより、報告されたすべてのバグとバグに追加されたすべてのコメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="92207-234">Users with active Xamarin Bugzilla accounts can view all bugs they've reported and all comments they've added to bugs by clicking the appropriate links on the Xamarin Bugzilla home page.</span></span>

##### <a name="export"></a><span data-ttu-id="92207-235">エクスポート</span><span class="sxs-lookup"><span data-stu-id="92207-235">Export</span></span>

<span data-ttu-id="92207-236">個人データのエクスポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="92207-236">Exporting of personal data is not supported.</span></span>

##### <a name="delete"></a><span data-ttu-id="92207-237">削除</span><span class="sxs-lookup"><span data-stu-id="92207-237">Delete</span></span>

<span data-ttu-id="92207-p121">Xamarin の Bugzilla バグ報告 Web サイトとの接続に使用される個人データの削除を要求するには、[[ユーザー設定] ページ](https://bugzilla.xamarin.com/userprefs.cgi)に移動して、**[アカウントの削除] タブ**を選択することにより、Xamarin Bugzilla アカウントを閉鎖できます。Bugzilla パスワードを入力して、自分のアカウントが完全に削除されることの認識を確認するボックスをオンにします。ユーザーが Xamarin Bugzilla に投稿したパブリック フィードバック (バグ、問題、コメント、解決策など) は、削除要求が受信されても削除されません。代わりに、パブリック フィードバックは、削除要求の送信者によって作成されたパブリック フィードバックに関連付けられた名前と電子メール アドレスを削除することにより、匿名化されます。</span><span class="sxs-lookup"><span data-stu-id="92207-p121">To request deletion of personal data used in connection with Xamarin's Bugzilla bug reporting website, users can close their Xamarin Bugzilla account by going to the [user preferences page](https://bugzilla.xamarin.com/userprefs.cgi) and choosing the **Close Account tab**. Enter your Bugzilla password and check the box confirming that you understand that this will permanently delete your account. Public feedback (for example, bugs, problems, comments, and solutions) that users have posted to the Xamarin Bugzilla will not be deleted after receipt of a delete request. Public feedback will instead be anonymized by removing the name and email address associated with any public feedback created by the user submitting the delete request.</span></span>

## <a name="nuget"></a><span data-ttu-id="92207-241">NuGet</span><span class="sxs-lookup"><span data-stu-id="92207-241">NuGet</span></span>

<span data-ttu-id="92207-242">NuGet.org の DSR の詳細については、「[NuGet ユーザー データ要求](https://docs.microsoft.com/nuget/policies/data-requests)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-242">For more information on DSR for NuGet.org, see [NuGet User Data Requests](https://docs.microsoft.com/nuget/policies/data-requests).</span></span>

## <a name="aspnet"></a><span data-ttu-id="92207-243">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="92207-243">ASP.NET</span></span>

<span data-ttu-id="92207-244">ASP.NET Web サイトの DSR については、「[ASP.NET Web サイトと GDPR データ主体要求の処理](https://www.asp.net/gdpr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-244">For information on DSR for the ASP.NET website, see [The ASP.NET Website and GDPR Data Subject Request processing](https://www.asp.net/gdpr).</span></span>

## <a name="iisnet"></a><span data-ttu-id="92207-245">IIS.NET</span><span class="sxs-lookup"><span data-stu-id="92207-245">IIS.NET</span></span>

<span data-ttu-id="92207-246">IIS.NET Web サイトの DSR については、「[IIS.NET Web サイトと GDPR データ主体要求の処理](https://www.iis.net/gdpr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-246">For information on DSR for the IIS.NET website, see [The IIS.NET Website and GDPR Data Subject Request processing](https://www.iis.net/gdpr).</span></span>

## <a name="other-visual-studio-family-services"></a><span data-ttu-id="92207-247">その他の Visual Studio ファミリ サービス</span><span class="sxs-lookup"><span data-stu-id="92207-247">Other Visual Studio Family Services</span></span>

### <a name="surveymonkey"></a><span data-ttu-id="92207-248">SurveyMonkey</span><span class="sxs-lookup"><span data-stu-id="92207-248">SurveyMonkey</span></span>

<span data-ttu-id="92207-p122">SurveyMonkey 経由でこれらの製品に関するフィードバックの提供をお願いすることがあります。このデータは 28 日以内に削除されます。これらの製品に関するデータ主体要求を処理するときに、アンケートの回答が認証されていれば、それらをエクスポートに含め、データ主体要求を削除します。</span><span class="sxs-lookup"><span data-stu-id="92207-p122">From time to time, we invite customers to provide feedback on these products via SurveyMonkey. This data is deleted within 28 days. When servicing data subject requests for these products, if we have authenticated survey responses we include them in export and delete data subject requests.</span></span>

### <a name="uservoice"></a><span data-ttu-id="92207-252">UserVoice</span><span class="sxs-lookup"><span data-stu-id="92207-252">UserVoice</span></span>

<span data-ttu-id="92207-p123">これらの製品の UserVoice.com サイトで製品に関する提案の提供をお願いしています。これらのサイトは UserVoice によって個別に運営されており、データ主体要求は UserVoice によって管理されています。</span><span class="sxs-lookup"><span data-stu-id="92207-p123">We invite customers to provide product suggestions at UserVoice.com sites for these products. These sites are independently operated by UserVoice, and data subject requests are managed by UserVoice.</span></span>

- [https://visualstudio.uservoice.com/](https://visualstudio.uservoice.com/)
- [https://aspnet.uservoice.com/](https://aspnet.uservoice.com/)
- [https://xamarin.uservoice.com/](https://xamarin.uservoice.com/)

<span data-ttu-id="92207-255">このデータに対するデータ主体要求については、「[データをエクスポートする方法](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data)」または「[データを削除する方法](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92207-255">For data subject requests on this data, see the UserVoice guidance on [how to export your data](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data) or on [how to delete your data](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information).</span></span>

## <a name="learn-more"></a><span data-ttu-id="92207-256">詳細情報</span><span class="sxs-lookup"><span data-stu-id="92207-256">Learn more</span></span>

- [<span data-ttu-id="92207-257">一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント</span><span class="sxs-lookup"><span data-stu-id="92207-257">Microsoft's GDPR Commitments to Customers of our Generally Available Enterprise Software Products</span></span>](https://docs.microsoft.com/legal/gdpr)
- [<span data-ttu-id="92207-258">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="92207-258">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [<span data-ttu-id="92207-259">Service Trust Portal</span><span class="sxs-lookup"><span data-stu-id="92207-259">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="92207-260">Microsoft プライバシー ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="92207-260">Microsoft Privacy Dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="92207-261">Microsoft Privacy Response Center</span><span class="sxs-lookup"><span data-stu-id="92207-261">Microsoft Privacy Response Center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="92207-262">GDPR のための Azure データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="92207-262">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
