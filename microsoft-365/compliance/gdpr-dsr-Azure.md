---
title: GDPR のための Azure データ サブジェクト要求
description: ''
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: heicba
author: herviicban
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 5b546a38b5073297fb9b89a06b4302fcd9be71fb
ms.sourcegitcommit: ea1d28fc3d0b93441aaca659c843f67495c1874f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34544864"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a><span data-ttu-id="00bff-103">GDPR のための Azure データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="00bff-103">Azure Data Subject Requests for the GDPR</span></span>

## <a name="introduction-to-data-subject-requests-dsrs"></a><span data-ttu-id="00bff-104">データ主体要求 (DSR) の概要</span><span class="sxs-lookup"><span data-stu-id="00bff-104">Introduction to Data Subject Requests (DSRs)</span></span>

<span data-ttu-id="00bff-p101">EU データ保護規則 (GDPR) では、ユーザー (規則では*データ サブジェクト*と呼ばれる) に対して、雇用主やその他の会社または組織 (*データ コントローラー*または単に*コントローラー*と呼ばれる) が収集した個人データを管理する権利を与えます。GDPR の下で個人データは広範な定義がなされ、識別された、または識別可能な自然人と関連するあらゆるデータのことです。GDPR は個人データに対するデータ サブジェクト固有の権利を与えます。この権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、または、別のコントローラーに移動できるようにするための電子形式での受信が含まれます。データ サブジェクトからコントローラーに個人データへのアクション実行を求める正式な要求は、*データ サブジェクト要求* (DSR) と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p101">The EU Data Protection Regulation (GDPR) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.</span></span>

<span data-ttu-id="00bff-p102">このガイドでは、DSR への対応として個人データを見つけて処理するコントローラーのお客様を支援する目的で、Microsoft の製品、サービス、管理ツールをどのように使用できるかを説明します。特に、Microsoft クラウドにある個人データを検出、アクセス、処理する方法を示します。このガイドで説明するプロセスの概要は次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="00bff-p102">The guide discusses how to use Microsoft products, services and administrative tools to help our controller customers find and act on personal data to respond to DSRs. Specifically, this includes how to find, access, and act on personal data that reside in the Microsoft cloud. Here’s a quick overview of the processes outlined in this guide:</span></span>

- <span data-ttu-id="00bff-p103">**検出:** 検索/検出ツールを使用することで、DSR の対象となる可能性がある顧客データをより簡単に見つけます。対応の対象となる可能性のあるドキュメントが収集されたら、以下のステップの DSR アクションを 1 つまたは複数実行して要求に対応できます。あるいは、DSR 対応に関する組織のガイドラインを要求が満たしていないと判断する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p103">**Discover**—Use search and discovery tools to more easily find customer data that may be the subject of a DSR. Once potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request. Alternatively, you may determine that the request doesn't meet your organization’s guidelines for responding to DSRs.</span></span>
 - <span data-ttu-id="00bff-115">**アクセス:** Microsoft クラウドにある個人データを取り出し、要求がある場合は、データ主体が利用できるコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="00bff-115">**Access**—Retrieve personal data that resides in the Microsoft cloud and, if requested, make a copy of it that can be available to the data subject.</span></span>
- <span data-ttu-id="00bff-116">**修正:** 必要に応じて、個人データを変更したり、要求された他の操作を個人データに対して実行したりします。</span><span class="sxs-lookup"><span data-stu-id="00bff-116">**Rectify.** Make changes or implement other requested actions on the personal data.</span></span>
- <span data-ttu-id="00bff-p104">**制限:** さまざまな Azure サービスのライセンスを削除するか、可能な場合は該当するサービスを無効にすることで、個人データの処理を制限します。また、データを Microsoft クラウドから削除してオンプレミスまたは別の場所で保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p104">**Restrict**—Restrict the processing of personal data, either by removing licenses for various Azure services or turning off the desired services where possible. You can also remove data from the Microsoft cloud and retain it on-premises or at another location.</span></span>
- <span data-ttu-id="00bff-119">**削除:** Microsoft クラウドに格納されていた個人データを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="00bff-119">**Delete**—Permanently remove personal data that resided in the Microsoft cloud.</span></span>
- <span data-ttu-id="00bff-120">**エクスポート:** 個人データの電子コピー (コンピューターで読み取り可能な形式) をデータ主体に提供します。</span><span class="sxs-lookup"><span data-stu-id="00bff-120">**Export**—Provide an electronic copy (in a machine-readable format) of personal data to the data subject.</span></span>

<span data-ttu-id="00bff-121">このガイドの各セクションでは、Microsoft クラウド内の個人データに関する DSR への対応としてデータ コントローラー組織が実行できる技術的な手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="00bff-121">Each section in this guide outlines the technical procedures that a data controller organization can take to respond to a DSR for personal data in the Microsoft cloud.</span></span>

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>

## <a name="terminology"></a><span data-ttu-id="00bff-122">用語集</span><span class="sxs-lookup"><span data-stu-id="00bff-122">Terminology</span></span>

<span data-ttu-id="00bff-123">このガイドに関連する用語を以下に定義します。</span><span class="sxs-lookup"><span data-stu-id="00bff-123">The following provides definitions of terms that are relevant to this guide.</span></span>

- <span data-ttu-id="00bff-124">**管理者:** 単独または他者と共同で、個人データの処理に関する目的と手段を決定する自然人や法人、公的機関、団体、その他の組織。そのような処理の目的と手段が EU 法もしくは加盟国の法律によって決定される場合、コントローラーまたはその指名に関する具体的な基準が EU 法または加盟国の法律によって提供される場合があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-124">**Controller.** The natural or legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data; where the purposes and means of such processing are determined by Union or Member State law, the controller or the specific criteria for its nomination may be provided for by Union or Member State law.</span></span>

- <span data-ttu-id="00bff-125">**個人データおよびデータ主体:** 特定されたまたは特定可能な自然人 (「データ主体」) に関するあらゆる情報。特定可能な自然人とは、その者の名前、ID 番号、位置データ、オンライン ID、または当該自然人に固有の 1 つ以上の特に身体的、生理学的、遺伝的、心理的、経済的、文化的、社会的な識別情報などの要素を参照することにより、直接または間接的に特定することができる者のことです。</span><span class="sxs-lookup"><span data-stu-id="00bff-125">**Personal data and data subject.** Any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person.</span></span>

- <span data-ttu-id="00bff-126">**処理者:** 管理者に代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。</span><span class="sxs-lookup"><span data-stu-id="00bff-126">**Processor.** A natural or legal person, public authority, agency or other body which processes personal data on behalf of the controller.</span></span>

- <span data-ttu-id="00bff-p105">**顧客データ:** 顧客またはその代理者がエンタープライズ サービスの使用を通じて Microsoft に提供する、すべてのテキスト、音声、ビデオ、画像 ファイルを含むすべてのデータおよびソフトウェア。顧客データには次の両方が含まれます: (1) 特定を可能にするエンド ユーザーの情報 (例: Azure Active Directory でのユーザー名と連絡先情報)、および (2) 特定のサービスでお客様がアップロードまたは作成した顧客コンテンツ (例: Azure Storage アカウント内の顧客コンテンツ、Azure SQL データベースの顧客コンテンツ、Azure Virtual Machines でのお客様の仮想マシン イメージ)。</span><span class="sxs-lookup"><span data-stu-id="00bff-p105">**Customer Data**—All data, including all text, sound, video, or image files, and software, that are provided to Microsoft by, or on behalf of, a customer through use of the enterprise service. Customer Data includes both (1) identifiable information of end users (e.g., user names and contact information in Azure Active Directory) and Customer Content that a customer uploads into or creates in specific services (e.g., customer content in an Azure Storage account, customer content of an Azure SQL Database, or a customer’s virtual machine image in Azure Virtual Machines).</span></span>

- <span data-ttu-id="00bff-p106">**システム生成ログ:** Microsoft がエンタープライズ サービスをユーザーに提供するうえで役立つ、Microsoft により生成されるログおよび関連データ。システム生成ログには主に固有 ID などの仮名化データが含まれています。固有 ID とは通常、それ自体は特定の個人を識別しないものの、エンタープライズ サービスをユーザーに提供するために使われるシステム生成番号です。また、ユーザー名などの、特定を可能にするエンド ユーザーの情報がシステム生成ログに含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p106">**System-Generated Logs**—Logs and related data generated by Microsoft that help Microsoft provide enterprise services to users. System-generated logs contain primarily pseudonymized data, such as unique identifiers – typically a number generated by the system that cannot on its own identify an individual person but is used to deliver the enterprise services to users. System-generated logs may also contain identifiable information about end users, such as a user name.</span></span>

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

## <a name="how-to-use-this-guide"></a><span data-ttu-id="00bff-132">このガイドの使用方法</span><span class="sxs-lookup"><span data-stu-id="00bff-132">How to use this guide</span></span>

<span data-ttu-id="00bff-133">このガイドは次のような 2 部構成になっています。</span><span class="sxs-lookup"><span data-stu-id="00bff-133">This guide consists of two parts:</span></span>

<span data-ttu-id="00bff-p107">**第 1 部: 顧客データに関するデータ サブジェクト要求に対応する** — このガイドの第 1 部では、アプリケーションで作成されたデータにアクセスし、データを修正、制限、削除、エクスポートする方法を示します。このセクションでは、カスタマー コンテンツとエンド ユーザー個人情報の両方に対して DSR を実行する方法について詳しく述べます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p107">**Part 1: Responding to Data Subject Requests for Customer Data** — Part 1 of this guide discusses how to access, rectify, restrict, delete, and export data from applications in which you have authored data. This section details how to execute DSRs against both Customer Content and also identifiable information of end users.</span></span>

<span data-ttu-id="00bff-p108">**第 2 部: システム生成ログに関するデータ主体要求に対応する** — Microsoft のエンタープライズ サービスを利用する際、Microsoft がサービスを提供するために使われるシステム生成ログという情報が生成されます。このガイドの第 2 部では、Azure でこのような情報にアクセスし、それを削除したりエクスポートしたりする方法について述べます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p108">**Part 2: Responding to Data Subject Requests for System-Generated Logs** — When you use Microsoft’s enterprise services, Microsoft generates some information, known as System-Generated Logs, in order to provide the service. Part 2 of this guide discusses how to access, delete and export such information for Azure.</span></span>

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a><span data-ttu-id="00bff-138">Azure Active Directory および Microsoft サービス アカウントに関する DSR について</span><span class="sxs-lookup"><span data-stu-id="00bff-138">Understanding DSRs for Azure Active Directory and Microsoft Service Accounts</span></span>

<span data-ttu-id="00bff-p109">お客様企業へのサービス提供を考慮するとき、特定の Azure Active Directory (AAD) テナント内のコンテキストで常に DSR の実行について理解する必要があります。特に、DSR は特定の AAD テナントの内部で常に実行されます。あるユーザーが複数のテナントに参加する場合、要求を受け取った特定のテナントのコンテキスト内で*のみ*、その DSR が実行されることを強調することが重要です。あるお客様企業からの DSR を実行しても、隣接するお客様企業のデータは影響を**受けない**という点を理解することは重要です。</span><span class="sxs-lookup"><span data-stu-id="00bff-p109">When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.</span></span>

<span data-ttu-id="00bff-p110">また、Microsoft Service Accounts (MSA) に関しても、お客様企業に提供されるサービスのコンテキスト内で同じことが当てはまります。*ある AAD テナントに関連付けられた* MSA アカウントに対する DSR 実行では、そのテナント内のデータ**のみ**が対象となります。さらに、テナント内の MSA アカウントを扱う際には次の点を理解することが重要です:</span><span class="sxs-lookup"><span data-stu-id="00bff-p110">The same also applies for Microsoft Service Accounts (MSA) within the context of services provided to an enterprise customer: execution of a DSR against an MSA account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling MSA accounts within a tenant:</span></span>

-   <span data-ttu-id="00bff-p111">MSA ユーザーが Azure サブスクリプションを作成すると、そのサブスクリプションは AAD テナントであるかのように扱われます。その結果、DSR の範囲は上記のようにテナント内となります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p111">If an MSA user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.</span></span>

-   <span data-ttu-id="00bff-p112">MSA アカウントを介して作成された Azure サブスクリプションが削除された場合、実際の MSA アカウントには影響が**ありません**。ここでも、上記のように、Azure サブスクリプション内で実行される DSR はテナント自体の範囲に限定されます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p112">If an Azure subscription created via an MSA account is deleted, **it will not affect** the actual MSA account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.</span></span>

<span data-ttu-id="00bff-p113">**特定のテナント外部の** MSA アカウント自体に対する DSR は、カスタマー プライバシー ダッシュボードを介して実行されます。詳しくは、Windows データ サブジェクト要求ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00bff-p113">DSRs against an MSA account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.</span></span>

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a><span data-ttu-id="00bff-151">第 1 部: 顧客データに関する DSR ガイド</span><span class="sxs-lookup"><span data-stu-id="00bff-151">Part 1: DSR Guide for Customer Data</span></span>

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a><span data-ttu-id="00bff-152">顧客データに対する DSR の実行</span><span class="sxs-lookup"><span data-stu-id="00bff-152">Executing DSRs against Customer Data</span></span>

<span data-ttu-id="00bff-p114">Microsoft の特定のお客様データにアクセスし、それを削除したりエクスポートしたりするには、Azure ポータルを使用するか、特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) やユーザー インターフェイス (UI) を直接使用できます (後者は*製品内エクスペリエンス*とも呼ばれます)。このような製品内エクスペリエンスについての詳細は、各サービスの参照ドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p114">Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services’ reference documentation.</span></span>

>[!Important]  
> <span data-ttu-id="00bff-p115">製品内 DSR をサポートするサービスでは、そのサービスのアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を直接使用し、該当する CRUD (作成、読み取り、更新、削除) 操作を記述する必要があります。したがって、特定のデータ サブジェクトの要求全体を完了するには Azure ポータル内での DSR 実行に加えて特定のサービス内で DSR を実行する必要があります。詳細については、特定のサービスの参照ドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00bff-p115">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.</span></span>

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-1-discover"></a><span data-ttu-id="00bff-158">ステップ 1: 検出</span><span class="sxs-lookup"><span data-stu-id="00bff-158">Step 1: Discover</span></span>

<span data-ttu-id="00bff-159">DSR に対応する最初の手順は、要求の件名の個人データを見つけることです。</span><span class="sxs-lookup"><span data-stu-id="00bff-159">The first step in responding to a data subject rights request is to search for and identify the customer data that is the subject of the request.</span></span> <span data-ttu-id="00bff-160">この第 1 ステップ (該当する個人データの検出と確認) により、DSR の承認/拒否に関する組織の要件を DSR が満たしているかどうか判断できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-160">This first step — finding and reviewing the personal data at issue — will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR.</span></span> <span data-ttu-id="00bff-161">たとえば、該当する個人データを検出して確認した後、その要求を実行すると他者の権利や自由が侵害される恐れがあるので、その要求は組織の要件に適合しないと判断する場合があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="00bff-161">This first step—finding and reviewing the personal data at issue—will help you determine whether the data subject’s request meets your organization's requirements for honoring or declining it. For example, after finding and reviewing the personal data, you may determine the request doesn’t meet your organization’s requirements because doing so may adversely affect the rights and freedoms of others.</span></span>

<span data-ttu-id="00bff-162">データが見つかったら、データ主体の要求に対応するために特定の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-162">After you find the data, you can then perform the specific action to satisfy the request by the data subject.</span></span>

<span id="_Toc511384807" class="anchor"><span id="_Toc511163878" class="anchor"><span id="_Toc511136235" class="anchor"><span id="_Toc511125168" class="anchor"><span id="_Toc511120755" class="anchor"><span id="_Toc511122662" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="00bff-163">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00bff-163">Azure Active Directory</span></span>

<span data-ttu-id="00bff-p117">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) は、Microsoft が提供するクラウド ベースのマルチテナント ディレクトリおよびアイデンティティ管理サービスです。[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) 環境にある個人データを含むエンド ユーザー個人情報 (顧客や従業員のユーザー プロファイルなど) およびユーザー勤務先情報を見つけるには、[Azure Portal](https://portal.azure.com/) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p117">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) is Microsoft’s cloud-based, multi-tenant directory and identity management service. You can locate identifiable information of end users, such as customer and employee user profiles and user work information that contain personal data in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/).</span></span>

<span data-ttu-id="00bff-p118">特定のユーザーの個人データを検出または変更する必要がある場合には、これが特に役立ちます。また、ユーザー プロファイルや勤務先情報を追加したり変更したりすることもできます。ディレクトリのグローバル管理者であるアカウントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p118">This is particularly helpful if you want to find or change personal data for a specific user. You can also add or change user profile and work information. You must sign in with an account that’s a global admin for the directory.</span></span>

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a><span data-ttu-id="00bff-169">ユーザー プロファイルや勤務先情報を検出または表示する方法</span><span class="sxs-lookup"><span data-stu-id="00bff-169">How do I locate or view user profile and work information?</span></span>

1. <span data-ttu-id="00bff-170">ディレクトリのグローバル管理者であるアカウントを使用して [Azure Portal](https://portal.azure.com/) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="00bff-170">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

1. <span data-ttu-id="00bff-171">**[すべてのサービス]** を選択し、テキスト ボックスに「**ユーザーとグループ**」と入力して、**Enter** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-171">Select **All services**, enter **Users and groups** in the text box, and then select **Enter**.</span></span>

     ![[すべてのサービス] を選択します](media/azure-dsr_image3.png)

3. <span data-ttu-id="00bff-173">**[ユーザーとグループ]** ブレードで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-173">On the **Users and groups** blade, select **Users**.</span></span>

     ![ユーザーを選択します](media/azure-dsr_image9.png)

4.  <span data-ttu-id="00bff-175">[**ユーザーとグループ - ユーザー**] ブレードでリストからユーザーを選択し、そのユーザーのブレードの [**プロファイル**] を選択すると、ユーザー プロファイル情報が表示されます。そこに個人データが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-175">On the **Users and groups - Users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view user profile information that might contain personal data.</span></span>

    ![プロファイルを選択します](media/azure-dsr_image5.png)

5. <span data-ttu-id="00bff-177">ユーザー プロファイル情報を必要に応じて追加または変更した後、コマンド バーの **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-177">If you need to add or change user profile information, you can do so, and then, in the command bar, select **Save.**</span></span>

<!-- steps 6 and 7 not in original 
6. On the blade for the selected user, select **Work Info** to view user work information that may contain personal data.

     ![Select work info](media/azure-dsr_image11.png)

7. If you need to add or change user work information, you can do so, and then, in the command bar, select **Save.**

end of text to isolate -->

<span id="_Toc511384808" class="anchor"><span id="_Toc511163879" class="anchor"><span id="_Toc511136236" class="anchor"><span id="_Toc511125169" class="anchor"><span id="_Toc511120756" class="anchor"><span id="_Toc511122663" class="anchor"></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-178">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-178">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p119">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p119">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Access" class="anchor"><span id="_Toc508792512" class="anchor"><span id="_Ref511119401" class="anchor"><span id="_Toc511122664" class="anchor"><span id="_Toc511120757" class="anchor"><span id="_Toc511125170" class="anchor"><span id="_Toc511136237" class="anchor"><span id="_Toc511163880" class="anchor"><span id="_Toc511384809" class="anchor"><span id="_Hlk503968195" class="anchor"></span></span></span></span></span></span></span></span></span></span>

### <a name="step-2-access"></a><span data-ttu-id="00bff-181">ステップ 2: アクセス</span><span class="sxs-lookup"><span data-stu-id="00bff-181">Step 2: Access</span></span>

<span data-ttu-id="00bff-p120">DSR 対応の対象となる可能性のある個人データを含む顧客データが見つかった後、組織とその担当者はどんなデータをデータ サブジェクトに提供するかを決定します。実際のドキュメントのコピー、適切に編集したバージョン、または共有できると判断した部分のスクリーン ショットを提供できます。アクセス要求に対するこのような対応ごとに、対象のデータを含むドキュメントのコピーまたは他のアイテムを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p120">After you’ve found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.</span></span>

<span data-ttu-id="00bff-185">データ サブジェクトにコピーを提供する際には、他のデータ サブジェクトに関する個人情報や他の機密情報を削除または編集する必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="00bff-185">When providing a copy to the data subject, you may have to remove or redact personal information about other data subjects and any confidential information.</span></span>

<span data-ttu-id="00bff-186"><span id="_Using_Content_Search_1" class="anchor"></span>DSR アクセス要求への対応としてデータのコピーを取得する方法を以下で説明します。</span><span class="sxs-lookup"><span data-stu-id="00bff-186"><span id="_Using_Content_Search_1" class="anchor"></span>The following explains how to get a copy of data in response to a DSR access request.</span></span>

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="00bff-187">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00bff-187">Azure Active Directory</span></span>

<span data-ttu-id="00bff-p121"><span id="_Forms_1" class="anchor"></span>お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介して DSR アクセス要求を管理できます。DSR アクセス要求では (a) エンド ユーザーに関する個人情報、および (b) システム生成ログを含むユーザー個人データへのアクセスが扱われます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p121"><span id="_Forms_1" class="anchor"></span>Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR access requests. DSR Access requests allow for access of the personal data of the user, including: (a) identifiable information about an end-user and (b) system-generated logs.</span></span>

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-190">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-190">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p122">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p122">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-3-rectify"></a><span data-ttu-id="00bff-193">ステップ 3: 修正</span><span class="sxs-lookup"><span data-stu-id="00bff-193">Step 3: Rectify</span></span>

<span data-ttu-id="00bff-p123">組織のデータに含まれる個人データを修正するようデータ サブジェクトが依頼した場合、組織とその担当者は、要求を承認するのが適切かどうか判断する必要があります。データの修正には、ドキュメントまたは他の種類のアイテムの中の個人データを編集、変更、または削除するアクションが含まれます。Microsoft サポートおよび FastTrack データに対してこれを行う最も便利な方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="00bff-p123">If a data subject has asked you to rectify the personal data that resides in your organization’s data, you and your organization will have to determine whether it’s appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item. The most expedient way to do this for Microsoft Support and FastTrack data is provided below.</span></span>

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="00bff-197">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00bff-197">Azure Active Directory</span></span>

<span data-ttu-id="00bff-p124">お客様企業は、各 Microsoft サービスの性質に応じて、限定的な編集を含む DSR 修正要求の管理機能を利用できます。Microsoft はデータ プロセッサとして、システム生成ログの修正機能を提供しません。これはシステム生成ログが実際のアクティビティを表し、Microsoft サービス内のイベントの履歴レコードを形成するためです。Azure Active Directory に関しては、下記で説明するように、エンド ユーザーの個人情報を限定的に編集できる機能があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p124">Enterprise customers have the ability to manage DSR rectify requests, including limited editing features per the nature of a given Microsoft service. As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Azure Active Directory, limited editing features exist to rectify identifiable information about an end-user, as described further below.</span></span>

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a><span data-ttu-id="00bff-201">Azure Active Directory: 不正確または不完全な個人データの修正</span><span class="sxs-lookup"><span data-stu-id="00bff-201">Azure Active Directory: rectify/correct inaccurate or incomplete personal data</span></span>

<span data-ttu-id="00bff-p125">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) 環境で [Azure Portal](https://portal.azure.com/) を使用すると、ユーザーの氏名、役職、住所、電話番号などの個人データを含むエンド ユーザー個人情報 (顧客や従業員のユーザー プロファイルなど) やユーザーの勤務先情報を修正、更新、または削除することができます。ディレクトリのグローバル管理者であるアカウントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p125">You can correct, update, or delete identifiable information about end users, such as customer and employee user profiles and user work information that contain personal data, such as a user’s name, work title, address, or phone number, in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/). You must sign in with an account that’s a global admin for the directory.</span></span>

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a><span data-ttu-id="00bff-204">Azure Active Directory でユーザー プロファイルや勤務先情報を修正または更新する方法</span><span class="sxs-lookup"><span data-stu-id="00bff-204">How do I correct or update user profile and work information in Azure Active Directory?</span></span>

1.  <span data-ttu-id="00bff-205">ディレクトリのグローバル管理者であるアカウントを使用して [Azure Portal](https://portal.azure.com/) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="00bff-205">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2.  <span data-ttu-id="00bff-206">**[すべてのサービス]** を選択し、テキスト ボックスに「**ユーザーとグループ**」と入力して、**Enter** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-206">Select **All services**, enter **Users and groups** in the text box, and then select **Enter**.</span></span>

    ![[すべてのサービス] を選択します](media/azure-dsr_image3.png)

3.  <span data-ttu-id="00bff-208">**[ユーザーとグループ]** ブレードで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-208">On the **Users and groups** blade, select **Users**.</span></span>
         
    ![ユーザーを選択します](media/azure-dsr_image9.png)

4.  <span data-ttu-id="00bff-210">[**ユーザーとグループ - ユーザー**] ブレードでリストからユーザーを選択し、そのユーザーのブレードの [**プロファイル**] を選択すると、修正または更新が必要なユーザー プロファイル情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00bff-210">On the **Users and groups - Users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view the user profile information that needs to be corrected or updated.</span></span>

    ![プロファイルを選択します](media/azure-dsr_image5.png)

5.  <span data-ttu-id="00bff-212">情報を修正または更新した後、コマンド バーの **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-212">Correct or update the information, and then, in the command bar, select **Save.**</span></span>

6.  <span data-ttu-id="00bff-213">選択したユーザーのブレードで **[勤務先情報]** を選択すると、修正または更新が必要なユーザーの勤務先情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00bff-213">On the blade for the selected user, select **Work Info** to view user work information that needs to be corrected or updated.</span></span>

    ![勤務先情報を選択します](media/azure-dsr_image4.png)

7.  <span data-ttu-id="00bff-215">ユーザーの勤務先情報を修正または更新した後、コマンド バーの **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-215">Correct or update the user work information, and then, in the command bar, select **Save.**</span></span>

<span id="_Toc511384814" class="anchor"><span id="_Toc511163885" class="anchor"><span id="_Toc511136242" class="anchor"><span id="_Toc511125175" class="anchor"><span id="_Toc511120762" class="anchor"><span id="_Toc511122669" class="anchor"></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-216">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-216">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p126">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p126">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Gain_access_to" class="anchor"><span id="_Toc508792521" class="anchor"><span id="_Toc511122670" class="anchor"><span id="_Toc511120763" class="anchor"><span id="_Toc511125176" class="anchor"><span id="_Toc511136243" class="anchor"><span id="_Toc511163886" class="anchor"><span id="_Toc511384815" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-4-restrict"></a><span data-ttu-id="00bff-219">ステップ 4: 制限</span><span class="sxs-lookup"><span data-stu-id="00bff-219">Step 4: Restrict</span></span>

<span data-ttu-id="00bff-p127"><span id="_Delete" class="anchor"></span>個人データの処理を制限するようデータ サブジェクトから依頼されることがあります。その場合、Azure ポータルと既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) の両方を使用できます。お客様企業のテナント管理者はこれらのエクスペリエンスを利用し、データ エクスポートとデータ削除を組み合わせて、このような DSR を管理できます。お客様は (a) アカウント、(b) システム生成ログ、(c) 関連するログを含むユーザー個人データの電子的なコピーをエクスポートし、その後、Microsoft システム内に保管されているアカウントおよび関連するデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p127"><span id="_Delete" class="anchor"></span>Data subjects may request that you restrict processing of their personal data. We provide both the Azure Portal and pre-existing application programming interfaces (APIs) or user interfaces (UIs). These experiences provide the enterprise customer’s tenant administrator the capability to manage such DSRs through a combination of data export and data deletion. A customer may (1) export an electronic copy of the personal data of the user, including (a) account(s), (b) system-generated logs, and (c) associated logs, followed with (2) deletion of the account and associated data residing within Microsoft systems.</span></span>

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>

### <a name="step-5-delete"></a><span data-ttu-id="00bff-224">ステップ 5: 削除</span><span class="sxs-lookup"><span data-stu-id="00bff-224">Step 5: Delete</span></span>

<span data-ttu-id="00bff-225">組織のサポート データからの個人データの削除による「削除する権利」は GDPR における主要な保護の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="00bff-225">The “right to erasure” by the removal of personal data from an organization’s Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. For details, see Delete end user personal data.</span></span> <span data-ttu-id="00bff-226">個人データの削除には、監査ログ情報を除く、すべての個人データとシステム生成ログの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00bff-226">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span> <span data-ttu-id="00bff-227">あるユーザーが**回復可能削除** (下記を参照) されると、そのアカウントが 30 日間にわたり無効になります。</span><span class="sxs-lookup"><span data-stu-id="00bff-227">When a user is **soft deleted** (see details below), the account is disabled for 30 days.</span></span> <span data-ttu-id="00bff-228">この 30 日間に何のアクションも行われない場合、そのユーザーは**完全削除** (これも下記を参照) されます。 </span><span class="sxs-lookup"><span data-stu-id="00bff-228">If no further action is taken during this 30-day period, the user is **permanently deleted** (again, see details below).</span></span> <span data-ttu-id="00bff-229">**完全削除**された場合、そのユーザーのアカウント、個人データ、システム生成ログがその後 30 日以内に抹消されます。</span><span class="sxs-lookup"><span data-stu-id="00bff-229">Upon a **permanent delete**, the user’s account, personal data, and system-generated logs are expunged within an additional 30 days.</span></span> <span data-ttu-id="00bff-230">テナント管理者が即時に**完全削除**を発行した場合、ユーザーのアカウント、個人データ、システム生成ログがその後 30 日以内に抹消されます。</span><span class="sxs-lookup"><span data-stu-id="00bff-230">If a tenant admin immediately issues a **permanent delete**, the user’s account, personal data, and system-generated logs are expunged within 30 days of issuance.</span></span>

> [!Important]
> <span data-ttu-id="00bff-231">ユーザーをテナントから削除するには、テナント管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="00bff-231">[Important] You must be a tenant administrator to delete a user from the tenant.</span></span>

<span id="_Toc511384817" class="anchor"><span id="_Toc511163888" class="anchor"><span id="_Toc511136245" class="anchor"><span id="_Toc511125178" class="anchor"><span id="_Toc511120765" class="anchor"><span id="_Toc511122672" class="anchor"><span id="_Ref511119801" class="anchor"></span></span></span></span></span></span></span>

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a><span data-ttu-id="00bff-232">Azure Portal を介してユーザーおよび関連データを削除する</span><span class="sxs-lookup"><span data-stu-id="00bff-232">Delete a user and associated data through the Azure portal</span></span>

<span data-ttu-id="00bff-233">データ サブジェクトから削除要求を受け取った後、Azure Portal を使用してユーザーおよび関連する個人情報、さらにシステム生成ログを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="00bff-233">After you receive a delete request for a data subject, you can use the Azure portal to delete both a user and the associated personal information as well as system-generated logs.</span></span>

<span data-ttu-id="00bff-p129">このデータを削除すると、それとともにテナントからユーザーが削除されます。ユーザーは最初に回復可能な方法で削除されます。つまり、回復可能削除のマークが付いてから 30 日以内にテナント管理者がアカウントを回復することができます。30 日後は、アカウントがテナントから自動的かつ完全に削除されます。この 30 日が経過する前に、回復可能削除されたユーザーをごみ箱から手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p129">Deleting this data also means deleting the user from the tenant. Users are initially soft-deleted, which means the account can be recovered by a tenant admin within 30 days of being marked for soft-delete. After 30 days, the account is automatically, and permanently, deleted from the tenant. Prior to that 30 days, you can manually delete a soft-deleted user from the recycle bin.</span></span>

<span data-ttu-id="00bff-238">テナントからユーザーを削除する大まかな手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00bff-238">Here’s the high-level process for deleting users from your tenant.</span></span>

1.  <span data-ttu-id="00bff-239">Azure Portal に移動し、ユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="00bff-239">Go to the Azure portal and locate the user.</span></span>

2.  <span data-ttu-id="00bff-p130">ユーザーを削除します。ユーザーを最初に削除すると、そのユーザーのアカウントがごみ箱に送られます。**この時点で、ユーザーは回復可能削除された状態になります。つまり、アカウントが無効になりますが、Azure Active Directory から抹消されたわけではありません。**</span><span class="sxs-lookup"><span data-stu-id="00bff-p130">Delete the user. When you initially delete the user, the user’s account is sent to the Recycle Bin. **At this point, the user is soft deleted, meaning the account is disabled, but not expunged from Azure Active Directory.**</span></span>

3.  <span data-ttu-id="00bff-p131">最近削除されたユーザーのリストに移動して、ユーザーを永続的に削除します。**この時点でユーザーが永続的に削除されます (完全削除ともいう)。つまりアカウントが Azure Active Directory から抹消済みになります**</span><span class="sxs-lookup"><span data-stu-id="00bff-p131">Go to the Recently deleted users list and permanently delete the user. **At this point the user is permanently deleted (also known as hard deleted), meaning the account has been expunged from Azure Active Directory**</span></span>

###### <a name="to-delete-a-user-from-an-azure-tenant"></a><span data-ttu-id="00bff-245">Azure テナントからユーザーを削除するには</span><span class="sxs-lookup"><span data-stu-id="00bff-245">To delete a user from an Azure tenant</span></span>

1.  <span data-ttu-id="00bff-246">Azure Portal を開き、**Azure Active Directory** ブレードを選択して **[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-246">Open the Azure portal, select the **Azure Active Directory** blade, and then select **Users**.</span></span>

    <span data-ttu-id="00bff-247">[**ユーザー – すべてのユーザー**] ブレードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00bff-247">The **Users – All users** blade appears.</span></span>

    ![ユーザーを見つけます](media/azure-dsr_image8.png)

2.  <span data-ttu-id="00bff-249">削除するユーザーの横にあるボックスをオンにして **[ユーザーの削除]** を選択し、ユーザー削除を確認するボックスで **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-249">Check the box next to the user you want to delete, select **Delete user**, and then select **Yes** in the box asking if you want to delete the user.</span></span>

    ![ユーザー管理](media/azure-dsr_image9.png)

3.  <span data-ttu-id="00bff-251">**[表示]** ドロップダウン ボックスで、**[最近削除されたユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-251">In the **Show** drop-down box, select **Recently deleted users**.</span></span>

    ![ユーザー プロファイルを表示します](media/azure-dsr_image10.png)

4.  <span data-ttu-id="00bff-253">同じユーザーを再び選択し、**[完全に削除する]** を選択して、確認を求めるボックスで **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-253">Select the same user again, select **Delete permanently**, and then select **Yes** in the box asking if you’re sure.</span></span>

>[!Important]  
><span data-ttu-id="00bff-p132">**[はい]** をクリックすると、ユーザーおよび関連するすべてのデータとシステム生成ログが完全に削除され、この操作を元に戻せないことに注意してください。間違ってこの操作を行った場合、手動でユーザーをテナントに再び追加する必要があります。関連するデータとシステム生成ログは回復不能です。</span><span class="sxs-lookup"><span data-stu-id="00bff-p132">Be aware that by clicking **Yes** you are permanently, and irrevocably, deleting the user and all associated data and system-generated logs. If you do this by mistake, you’ll have to manually add the user back to the tenant. The associated data and system-generated logs are non-recoverable.</span></span>

   ![ユーザー勤務先情報を表示します](media/azure-dsr_image11.png)

<span id="_Export" class="anchor"><span id="_Step_6:_Export" class="anchor"><span id="_Toc511116629" class="anchor"><span id="_Toc511122673" class="anchor"><span id="_Toc511120766" class="anchor"><span id="_Toc511125179" class="anchor"><span id="_Toc511136246" class="anchor"><span id="_Toc511163889" class="anchor"><span id="_Toc508792534" class="anchor"></span></span></span></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-258">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-258">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p133">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p133">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384819" class="anchor"><span id="_Toc511163890" class="anchor"><span id="_Toc511136247" class="anchor"><span id="_Toc511125180" class="anchor"><span id="_Toc511120767" class="anchor"><span id="_Toc511122674" class="anchor"></span></span></span></span></span></span>
## <a name="step-6-export"></a><span data-ttu-id="00bff-261">ステップ 6: エクスポート</span><span class="sxs-lookup"><span data-stu-id="00bff-261">Step 6: Export</span></span>

<span data-ttu-id="00bff-262"><span id="_Power_BI_2" class="anchor"></span>「データ移植性の権利」により、データ主体は、別のデータ コントローラーに移送できる電子的な形式 (つまり構造化され、一般使用される、マシン読み取り可能かつ相互運用可能な形式) の個人データのコピーを要求できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-262"><span id="_Power_BI_2" class="anchor"></span>The “right of data portability” allows a data subject to request a copy of their personal data in an electronic format (that’s a “structured, commonly used, machine read-able and interoperable format”) that may be transmitted to another data controller. Azure supports this by enabling your organization to export the data in the native JSON format, to your specified Azure Storage Container.</span></span> <span data-ttu-id="00bff-263">Azure では、ユーザーの組織がネイティブ JSON 形式のデータを指定の Azure Storage コンテナーにエクスポートできるようにすることによってこれをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="00bff-263">Azure supports this by enabling your organization to export the data in the native JSON format, to your specified Azure Storage Container. Introduction to Microsoft Azure Storage – Blob storage article.</span></span>

><span data-ttu-id="00bff-264">[重要] ユーザー データをテナントからエクスポートするには、テナント管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="00bff-264">[Important] You must be a tenant administrator to export user data from the tenant.</span></span>

<span id="_Toc511384820" class="anchor"><span id="_Toc511163891" class="anchor"><span id="_Toc511136248" class="anchor"><span id="_Toc511125181" class="anchor"><span id="_Toc511120768" class="anchor"><span id="_Toc511122675" class="anchor"><span id="_Ref511119875" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a><span data-ttu-id="00bff-265">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00bff-265">Azure Active Directory</span></span>

<span data-ttu-id="00bff-266">顧客データに関して、お客様企業のテナント管理者はポータルと製品エクスペリエンスの両方を利用して、エンド ユーザーに関する特定可能な情報のエクスポート要求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="00bff-266">With respect to Customer Data, Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage export requests for identifiable information about an end-user.</span></span>

<span id="_Toc511384821" class="anchor"><span id="_Toc511163892" class="anchor"></span></span>
### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-267">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-267">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p135">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p135">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>

## <a name="part-2-system-generated-logs"></a><span data-ttu-id="00bff-270">第 2 部: システム生成ログ</span><span class="sxs-lookup"><span data-stu-id="00bff-270">Part 2: System-Generated Logs</span></span>

<span data-ttu-id="00bff-271">さらに、ユーザーによる Azure 使用状況に関連する特定のシステム生成ログにアクセスし、それを削除したりエクスポートしたりできます。</span><span class="sxs-lookup"><span data-stu-id="00bff-271">Microsoft also provides you with the ability to access, delete and export certain system-generated logs associated with a user’s use of Azure.</span></span>

>[!Important]
> <span data-ttu-id="00bff-p136">システム生成ログを制限または修正する機能はサポートされていない点に注意してください。システム生成ログは、Microsoft クラウド内で実行された実際のアクションと診断データを形成し、そのようなデータが変更されるとアクションの履歴記録が損なわれ、詐欺やセキュリティのリスクが増大します。</span><span class="sxs-lookup"><span data-stu-id="00bff-p136">The ability to restrict or rectify system-generated logs is not supported. System-generated logs constitute factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions, increasing fraud and security risks.</span></span>

<span id="_Toc511384823" class="anchor"><span id="_Toc511163894" class="anchor"><span id="_Toc511136252" class="anchor"><span id="_Toc511125185" class="anchor"><span id="_Toc511120772" class="anchor"><span id="_Toc511122679" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-system-generated-logs"></a><span data-ttu-id="00bff-274">システム生成ログに対する DSR の実行</span><span class="sxs-lookup"><span data-stu-id="00bff-274">Executing DSRs against System-Generated Logs</span></span>

<span data-ttu-id="00bff-p137">Azure ポータルを使用したり、特定のサービス用のプログラマティック インターフェイスまたはユーザー インターフェイスを直接使用したりすることで、特定のシステム生成ログにアクセスし、削除/エクスポートすることができます。詳細については、各サービスの参照ドキュメンテーションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p137">Microsoft provides the ability to access, delete, and export certain system-generated logs through the Azure Portal and also directly via programmatic interfaces or user interfaces for specific services. Details are described in the respective services’ reference documentation.</span></span>

>[!Important]  
> <span data-ttu-id="00bff-p138">製品内 DSR をサポートするサービスでは、そのサービスのアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を直接使用する必要があります。したがって、特定のデータ サブジェクトの要求全体を完了するには Azure ポータル内での DSR 実行に加えて製品内 DSR **を実行する必要があります。詳細については、特定のサービスの参照ドキュメントをご覧ください。**</span><span class="sxs-lookup"><span data-stu-id="00bff-p138">Services supporting in-product DSRs require direct usage of the service’s application programming interface (API) or user interface (UI). Consequently, execution of an in-product DSRs **must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services’ reference documentation for further details.**</span></span>

<span id="_Toc511384824" class="anchor"><span id="_Toc511163895" class="anchor"><span id="_Toc511136253" class="anchor"><span id="_Toc511125186" class="anchor"><span id="_Toc511120773" class="anchor"><span id="_Toc511122680" class="anchor"><span id="_Ref511119063" class="anchor"><span id="_Toc508792552" class="anchor"><span id="_Toc509825622" class="anchor"></span></span></span></span></span></span></span></span></span>

### <a name="step-1-access"></a><span data-ttu-id="00bff-279">ステップ 1: アクセス</span><span class="sxs-lookup"><span data-stu-id="00bff-279">Step 1: Access</span></span> 

<span data-ttu-id="00bff-p139">組織内で特定のユーザーによる Azure 使用状況に関連するシステム生成ログにアクセスできるのは、テナント管理者のみです。アクセス要求に関して取得されるデータはマシン読み取り可能形式で提供され、データの関連先のサービスがユーザーにわかるようなファイルで提供されます。上記のように、サービスのセキュリティを損なう可能性のあるデータは取得対象データに含まれません。</span><span class="sxs-lookup"><span data-stu-id="00bff-p139">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user’s use of Azure. The data retrieved for an access request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security of the service.</span></span>

<span id="_Toc511384825" class="anchor"><span id="_Toc511163896" class="anchor"><span id="_Toc511136254" class="anchor"><span id="_Toc511125187" class="anchor"><span id="_Toc511120774" class="anchor"><span id="_Toc511122681" class="anchor"><span id="_Toc511119129" class="anchor"></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="00bff-283">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00bff-283">Azure Active Directory</span></span>

<span data-ttu-id="00bff-284">お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介してアクセス要求を管理できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-284">With respect to Customer Data, Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage export requests for identifiable information about an end-user.</span></span> <span data-ttu-id="00bff-285">アクセス要求では (a) エンド ユーザーに関する特定可能なデータ、および (b) サービス生成ログを含むユーザーの個人データへのアクセスが扱われます。</span><span class="sxs-lookup"><span data-stu-id="00bff-285">Access requests will allow for access of the personal data of the user, including: (a) identifiable information about an end user and (b) service-generated logs.</span></span> <span data-ttu-id="00bff-286">このプロセスは、第 1 部「ステップ 2: アクセス」の Azure Active Directory セクションで説明するプロセスと同じです。</span><span class="sxs-lookup"><span data-stu-id="00bff-286">The process is identical to that described in the Azure Active Directory section of Part 1, Step 2: Access.</span></span>

<span id="_Toc511384826" class="anchor"><span id="_Toc511163897" class="anchor"><span id="_Toc511136255" class="anchor"><span id="_Toc511125188" class="anchor"><span id="_Toc511120775" class="anchor"><span id="_Toc511122682" class="anchor"><span id="_Toc511119130" class="anchor"></span></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-287">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-287">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p141">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p141">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384827" class="anchor"><span id="_Toc511163898" class="anchor"><span id="_Toc511136256" class="anchor"><span id="_Toc511125189" class="anchor"><span id="_Toc511120776" class="anchor"><span id="_Toc511122683" class="anchor"><span id="_Toc508792553" class="anchor"><span id="_Toc509825623" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-2-delete"></a><span data-ttu-id="00bff-290">ステップ 2: 削除</span><span class="sxs-lookup"><span data-stu-id="00bff-290">Step 2: Delete</span></span>

<span data-ttu-id="00bff-291">組織内で、Azure テナントの特定のユーザーに関する DSR 削除要求を実行できるのはテナント管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="00bff-291">The tenant admin is the only person within your organization who can execute a DSR delete request for a particular user within an Azure tenant.</span></span>

<span id="_Toc511384828" class="anchor"><span id="_Toc511163899" class="anchor"><span id="_Toc511136257" class="anchor"><span id="_Toc511125190" class="anchor"><span id="_Toc511120777" class="anchor"><span id="_Toc511122684" class="anchor"><span id="_Toc511119563" class="anchor"></span></span></span></span></span></span></span>
#### <a name="azure-active-directory"></a><span data-ttu-id="00bff-292">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00bff-292">Azure Active Directory</span></span>

<span data-ttu-id="00bff-p142">お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介して DSR 削除要求を管理できます。DSR 削除要求は、第 1 部、「ステップ 5: 削除」の「Azure Portal を介してユーザーおよび関連データを削除する」のセクションと同じ方法で扱われます。</span><span class="sxs-lookup"><span data-stu-id="00bff-p142">Microsoft offers both a portal and in-product experiences providing the enterprise customer’s tenant administrator the capability to manage DSR delete requests. DSR delete requests follow the same as described in the Delete a user and associated data through the Azure portal section of Part 1, Step 5: Delete.</span></span>

<span id="_Toc511384829" class="anchor"><span id="_Toc511163900" class="anchor"><span id="_Toc511136258" class="anchor"><span id="_Toc511125191" class="anchor"><span id="_Toc511120778" class="anchor"><span id="_Toc511122685" class="anchor"><span id="_Toc511119564" class="anchor"></span></span></span></span></span></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-295">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-295">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p143">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p143">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

<span id="_Toc511384830" class="anchor"><span id="_Toc511163901" class="anchor"><span id="_Toc511136259" class="anchor"><span id="_Toc511125192" class="anchor"><span id="_Toc511120779" class="anchor"><span id="_Toc511122686" class="anchor"><span id="_Toc508792554" class="anchor"><span id="_Toc509825624" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="step-3-export"></a><span data-ttu-id="00bff-298">ステップ 3: エクスポート</span><span class="sxs-lookup"><span data-stu-id="00bff-298">Step 3: Export</span></span>

<span data-ttu-id="00bff-p144">組織内で特定のユーザーによる Azure 使用状況に関連するシステム生成ログにアクセスできるのは、テナント管理者のみです。エクスポート要求に関して取得されるデータはマシン読み取り可能形式で提供され、データの関連先のサービスがユーザーにわかるようなファイルで提供されます。上記のように、サービスのセキュリティや安定性を損なう可能性のあるデータは取得対象データに含まれません。</span><span class="sxs-lookup"><span data-stu-id="00bff-p144">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user’s use of Azure. The data retrieved for an export request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security or stability of the service.</span></span>

<span id="_Toc511384831" class="anchor"><span id="_Toc511163902" class="anchor"></span></span>

#### <a name="export-system-generated-logs-using-the-azure-portal"></a><span data-ttu-id="00bff-302">Azure Portal を使用してシステム生成ログをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="00bff-302">Export system-generated logs using the Azure portal</span></span>

<span data-ttu-id="00bff-303">データ サブジェクトのエクスポート要求を受け取った後、Azure Portal を使用して、特定のユーザーに関連するシステム生成ログをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="00bff-303">After you receive an export request for a data subject, you can use the Azure portal to export system-generated logs associated with a given user.</span></span>

<span data-ttu-id="00bff-304">テナントからデータをエクスポートする大まかな手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00bff-304">Here’s the high-level process for exporting data from your tenant.</span></span>

1. <span data-ttu-id="00bff-305">Azure Portal に移動し、ユーザーに代わってエクスポート要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="00bff-305">Go to the Azure portal and create an export request on behalf of the user.</span></span>
2. <span data-ttu-id="00bff-306">データをエクスポートして、ファイルをユーザーに送ります。</span><span class="sxs-lookup"><span data-stu-id="00bff-306">Export the data and send file to user.</span></span>

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a><span data-ttu-id="00bff-307">Azure テナントからユーザーの情報をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="00bff-307">To export a user’s info from an Azure tenant</span></span>

1. <span data-ttu-id="00bff-308">Azure Portal を開き、**[すべてのサービス]** を選択し、フィルターに「*policy*」と入力して **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-308">Open the Azure portal, select **All services**, type *policy* into the filter, and then select **Policy**.</span></span>

     ![<span data-ttu-id="00bff-309">[すべてのサービス] フィルター</span><span class="sxs-lookup"><span data-stu-id="00bff-309">All services filter</span></span> ](media/azure-dsr_image12.png)

2. <span data-ttu-id="00bff-310">**[ポリシー]** ブレードで **[ユーザー プライバシー]** を選択し、**[ユーザー要求の管理]** を選択して、**[エクスポート要求の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-310">In the **Policy** blade, select **User privacy**, select **Manage User Requests**, and then select **Add export request**.</span></span>

    ![<span data-ttu-id="00bff-311">エクスポート要求を追加します</span><span class="sxs-lookup"><span data-stu-id="00bff-311">Add export request</span></span> ](media/azure-dsr_image13.png)

3. <span data-ttu-id="00bff-312">**[データ エクスポート要求]** に次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="00bff-312">Complete the **Export data request**:</span></span>

    ![新しいデータ エクスポート要求](media/azure-dsr_image14.png)

- <span data-ttu-id="00bff-p145">**ユーザー**: エクスポートを要求した Azure Active Directory ユーザーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="00bff-p145">**User.** Type the email address of the Azure Active Directory user that requested the export.</span></span>

- <span data-ttu-id="00bff-p146">**サブスクリプション**: リソース使用状況の報告とサービス料金の請求に使用するアカウントを選択します。これは Azure ストレージ アカウントの場所でもあります。</span><span class="sxs-lookup"><span data-stu-id="00bff-p146">**Subscription.** Select the account you use to report resource usage and to bill for services. This is also the location of your Azure storage account.</span></span>

- <span data-ttu-id="00bff-319">**ストレージ アカウント。**</span><span class="sxs-lookup"><span data-stu-id="00bff-319">\*\*\*\* Storage account name</span></span> <span data-ttu-id="00bff-320">Azure Storage (Blob) の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-320">Select the location of your Azure Storage (Blob).</span></span> <span data-ttu-id="00bff-321">詳細については、「[Microsoft Azure Storage の概要 – Blob ストレージ](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00bff-321">Storage account. Select the location of your Azure Storage (Blob). For more info, see the [Introduction to Microsoft Azure Storage – Blob storage](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage) article.</span></span>

- <span data-ttu-id="00bff-p148">**コンテナー**: エクスポートされたユーザー プライバシー データの保存場所として新しいコンテナーを作成するか、既存のものを選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-p148">**Container.** Create a new (or select an existing) container as the storage location for the user’s exported privacy data.</span></span>

4. <span data-ttu-id="00bff-324">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00bff-324">Select **Create**.</span></span>

<span data-ttu-id="00bff-325">エクスポート要求は [**保留中**] 状態になります。</span><span class="sxs-lookup"><span data-stu-id="00bff-325">The export request goes into **Pending** status.</span></span> <span data-ttu-id="00bff-326">レポートの状況は [**ユーザー プライバシー - 概要**] ブレードで確認できます。</span><span class="sxs-lookup"><span data-stu-id="00bff-326">The export request goes into Pending status. You can view the report status on the **User privacy - Overview** blade.</span></span>

>[!Important]  
><span data-ttu-id="00bff-327">個人データは複数のシステムから取得される可能性があるので、エクスポート プロセスが完了するまでに 1 か月かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00bff-327">Because personal data can come from multiple systems, it’s possible that the export process might take up to one month to complete.</span></span>

<span id="_Toc511384832" class="anchor"><span id="_Toc511163903" class="anchor"></span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="00bff-328">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="00bff-328">Service-Specific Interfaces</span></span>

<span data-ttu-id="00bff-p150">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="00bff-p150">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services’ reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="notify-about-exporting-or-deleting-issues"></a><span data-ttu-id="00bff-331">エクスポートまたは削除に関する問題を通知する</span><span class="sxs-lookup"><span data-stu-id="00bff-331">Notify about exporting or deleting issues</span></span>
<span data-ttu-id="00bff-332">Azure portal でデータをエクスポートまたは削除中に問題が発生した場合は、Azure ポータルの **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理] > [他のセキュリティとコンプライアンスの要求] > [プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。</span><span class="sxs-lookup"><span data-stu-id="00bff-332">If you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management > Other Security and Compliance Request > Privacy Blade and GDPR Requests**.</span></span>

## <a name="learn-more"></a><span data-ttu-id="00bff-333">詳細情報</span><span class="sxs-lookup"><span data-stu-id="00bff-333">Learn more</span></span>

- [<span data-ttu-id="00bff-334">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="00bff-334">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)