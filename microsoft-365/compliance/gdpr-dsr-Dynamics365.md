---
title: GDPR および CCPA のための Dynamics 365 データ対象要求
description: このガイドは、個人データを検索して操作する方法、および Dynamics 365 のお客様による DSR および CCPA 要求への対応方法について説明します。
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
hideEdit: true
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817666"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のための Dynamics 365 データ対象要求

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。  また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、"売上" として分類された特定のデータ転送の "オプトアウト/オプトイン" 要件を規定します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。

このガイドは、コントローラーが DSR 要求に応じて個人データを検索して操作できるように Microsoft 製品、サービス、管理ツールを使用する方法について説明します。 具体的には、Microsoft のクラウドに保存されている個人データや個人情報の検索、アクセス、および操作方法について説明します。 このガイドに記載されているプロセスの概要を次に示します。

- **検出:** 検索および検出ツールを使用して、DSR 要求の対象である可能性がある顧客データを簡単に検索します。 可能性のある応答ドキュメントが収集されると、以下の手順に示す 1 つ以上の DSR アクションを実行して、要求に応答できます。 または、DSR 要求への応答に関する組織のガイドラインを要求が満たしていないと判断する場合もあります。
- **アクセス:** Microsoft クラウドにある個人データを取り出し、要求がある場合は、データ主体が利用できるコピーを作成します。
- **修正:** 必要に応じて、個人データを変更したり、要求された他の操作を個人データに対して実行したりします。
- **制限** さまざまなオンライン サービスに対するライセンスを削除するか、または可能な場合は目的のサービスをオフにすることで、個人データの処理を制限します。 次のことが行えます。
- **削除:** Microsoft のクラウドに格納されていた個人データを完全に削除します。
- **エクスポート/受信 (移植性):** 個人データまたは個人情報の電子コピー (コンピューターで読み取り可能な形式) をデータ主体に提供します。 CCPA における個人情報とは、識別された人、または識別可能な人に関するあらゆる情報のことです。 個人の私的、公的、または職業上の役割による区別はありません。 "個人情報" と定義された用語は、GDPR における "個人データ" とほぼ同義です。 ただし、CCPA では家族データおよび世帯データも含まれます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。

このガイドの各セクションでは、Microsoft のクラウドにある個人データについて DSR 要求がなされた場合に、その対応としてデータ コントローラー組織が実行できる技術的な手順の概要を示します。

### <a name="gdpr-terminology"></a>GDPR 用語

このガイドに関連する用語を以下に定義します。

- **管理者:** 単独または他者と共同で、個人データの処理に関する目的と手段を決定する自然人や法人、公的機関、団体、その他の組織。そのような処理の目的と手段が EU 法もしくは加盟国の法律によって決定される場合、コントローラーまたはその指名に関する具体的な基準が EU 法または加盟国の法律によって提供される場合があります。
- **個人データおよびデータ主体:** 特定されたまたは特定可能な自然人 ('データ主体') に関するあらゆる情報。特定可能な自然人とは、その者の名前、ID 番号、位置データ、オンライン ID、または当該自然人に固有の 1 つ以上の特に身体的、生理学的、遺伝的、心理的、経済的、文化的、社会的な識別情報などの要素を参照することにより、直接または間接的に特定することができる者のことです。
- **処理者:** 管理者に代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。
- **顧客データ:** これは、顧客または顧客の代理が エンタープライズ サービスの使用を通じて Microsoft に提供する、テキスト、音声、ビデオ、画像ファイル、およびソフトウェアを含むすべてのデータのことです。 顧客データには次の両方が含まれます: (1) 特定を可能にするエンド ユーザーの情報 (例: Azure Active Directory でのユーザー名と連絡先情報)、および (2) 特定のサービスでお客様がアップロードまたは作成する顧客コンテンツ (例: Azure Storage アカウント内の顧客コンテンツ、Azure SQL データベースの顧客コンテンツ、Azure Virtual Machines でのお客様の仮想マシン イメージ)。
- **システム生成ログ:** Microsoft がエンタープライズ サービスをユーザーに提供するうえで役立つ、Microsoft により生成されるログおよび関連データ。 システム生成ログには主に固有 ID などの仮名化データが含まれています。固有 ID とは一般的に、それ自体は特定の個人を識別しないものの、エンタープライズ サービスをユーザーに提供するために使われるシステム生成番号です。 また、ユーザー名などの、特定を可能にするエンド ユーザーの情報がシステム生成ログに含まれることもあります。

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>管理者としての責任を果たすためのこのガイドの活用方法

このガイドは、2 つの部分に分かれており、GDPR で定められた権利を行使するデータ主体による要求に応じて、ユーザーが Microsoft クラウドのデータを検索して操作できるように Dynamics 365 製品、サービス、管理ツールを使用する方法について説明します。 パート 1 では、顧客データに含まれる個人データを取り上げます。その後、パート 2 で、システム生成ログによってキャプチャされるその他の仮名化された個人データについて取り上げます。

- **パート 1: 顧客データに含まれる個人データに関するデータ主体の権利 (DSR) 要求に対応する:** このガイドのパート 1 では、Dynamics 365 アプリケーション (サービスとしてのソフトウェア) から、ユーザーがオンライン サービスに提供した顧客データの一部として処理される個人情報にアクセス、修正、制限、削除、エクスポートの処理を実行する方法を説明します。
- **パート 2: 仮名化データに対するデータ主体の権利要求への対応:** Dynamics 365 Enterprise サービスを使用する場合、Microsoft は一部の情報 (このドキュメントでは*システム生成ログ*と呼びます) を生成します。この情報は、システムでのアクションを識別するためにエンドユーザーが残したフットプリントに制限されます。 追加の情報を使用せずにこのデータを特定のデータ主体への属性を特定できませんが、一部は GDPR にしたがって個人データと見なされる可能性があります。 このガイドのパート 2 では、Dynamics 365 によって生成されたシステム生成ログのアクセス方法、削除方法、およびエクスポート方法について説明します。

### <a name="preparing-for-data-subject-rights-investigations"></a>データ主体権限の調査の準備

データ主体が当人の権限を行使して要求を行う場合は、次の点を考慮してください。

- 要求の一部としてデータ主体から提供された情報を基に、その人物と役割 (従業員、顧客、仕入先など) を正確に特定します。 この種の情報には、名前、従業員 ID、顧客番号、その他の ID などが考えられます。
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- 要求に関連する情報があることを確認します。

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>第 1 部: 顧客データに含まれる個人データに関するデータ主体権限要求に対する対応

In the articles below, you'll find information to help you prepare for and respond to DSR requests for personal data included in customer data processed in Dynamics 365. It is important to note that personal data could be present in other categories of data processed by Microsoft during the course of the service of an online services subscription, such as administrator data or support data defined in the Microsoft Privacy Statement. This document is limited to assist you in the process of discovery and management of DSR requests affecting personal data present in the customer data that you have provided to Dynamics 365.

Dynamics 365 is an online service that offers multiple data processing capabilities as a software-as-a-service (SaaS). As such, Dynamics 365 offers a broad array of functionality intended to process a diverse collection of data, which could vary by nature, purpose or other specific attributes, such as sales data, transactions, financials, HR information, etc. In light of this diversity, Dynamics 365 offers multiple forms, fields, schemas, end points, and logic to process customer data, which is also reflected in the multiple ways in which DSR requests could be addressed in each application. When Dynamics 365 applications offer several ways to address specific DSR requests, we will note those in this guide by pointing to the technical descriptions offered by each application.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>顧客データの検索

データ主体の権利要求に対する対応の最初の段階として、要求の対象となっている顧客データを検索して特定します。

Classifying customer data appropriately is the cornerstone of working with personal data in Dynamics 365 Customer Engagement business applications. Dynamics 365 for Customer Engagement offers flexibility to build out an application extension around data classification. Proper classification enables you to identify information as personal data, thereby making it possible to locate and retrieve it when responding to requests from a data subject. It can also help enable compliance with legislative and regulatory requirements for collecting and managing personal data.

Microsoft provides capabilities that assist you in responding to data subject rights requests, and thereby accessing customer data. However, it is your responsibility to ensure that personal data is located and classified appropriately.

***Dynamics 365 for Customer Engagement*** には、高度な検索、レコード検索など、レコード内の個人データをユーザーが検索するための機能が複数用意されています。 いずれの機能でも、個人データを特定または検索できます。

- [[高度な検索]](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [[レコード検索]](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) は、複数のレコードの種類に対して検索を実行できます。

Dynamics 365 for Marketing には、次の追加機能が用意されています。

1. [[Power BI レポートの作成]](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) は、顧客データをフィルター処理し特定する機能です。
2. 顧客データを含む可能性のあるその他のデータ ポイントを特定するには、マーケティング実行の取引先担当者や対象についてインサイト ビューを使用します。

***Dynamics 365 Customer Service Insights*** では、[顧客データを検索する](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery)ために役立つリソースの一覧を提供しており、お客様が顧客からの GDPR 要求に対応するのに役立てていただけます。 

***Dynamics 365 for Finance and Operations*** では、顧客データを検索するためのいくつかの方法を提供します。 テナント管理者として、次のアクションを実行して顧客データを検索できます。

- 個人データをすばやく検出する目的にかなう方法で顧客データを整理します。この目的に関しては、「[データ インベントリの分類方法](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)」をご覧ください。
- 個人データを検索および収集するには、[[個人検索レポート]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) を使用します。
- [[個人検索レポートの拡張]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) では、エンティティを新規に作成するか既存のエンティティを拡張することにより、個人検索レポートを拡張します。
- 検索機能とフィルター処理機能を使用して、特定の個人データを検索し、Microsoft Office エクスポート機能を使用してそのデータをエクスポートしたり、ブラウザーの拡張機能を使用して .pdf ファイルにその情報を書き込んだりできます。
- 個人データを検索してエクスポートするユーザー設定のフォームを作成します。
- 認証済み顧客が当人の個人データを確認できる外部ポータルまたは Web サイトを作成します。

***Dynamics 365 Business Central*** は、顧客データを検索するためのいくつかの方法を提供します。 詳細については、「[データの検索、フィルター処理、並べ替え](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters)」を参照してください。

***Dynamics 365 for Talent*** には、特定の個人データを検索するための高度な検索機能とフィルター処理機能に加えて、ブラウザーの拡張機能を使用して .pdf ファイルにその情報をエクスポートまたは書き込むための Microsoft Office エクスポート機能が用意されています。

- 顧客データを検索および収集するには、[[個人検索レポート]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) を使用します。
- 新しいエンティティを作成するか、既存のエンティティを拡張することにより、[個人検索レポートを拡張します](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。

### <a name="providing-a-copy-of-customer-data"></a>顧客データのコピーの提供

***Dynamics 365 for Customer Engagement*** の顧客データは、包括的なエンティティ エクスポート機能を使用してエクスポートできます。 顧客データを静的な Excel ファイルにエクスポートして、データ移植性要求を容易にすることができます。 Excel を使用して、移植性要求に含める個人データを編集し、.csv や .xml などのコンピューターで読み取り可能な一般的に使用されるファイル形式で保存できます。 また、Dynamics 365 for Customer Engagement のレコードは、[Common Data Service Web API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview)を介してエクスポートすることもできます。

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights*** では、データ エクスポートを使用して、[顧客データのコピーを提供](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)することができます。

***Dynamics 365 for Finance and Operations*** の顧客データは、包括的なエンティティ エクスポート機能を使用してエクスポートできます。 テナントの管理者は、[*データ管理と統合エンティティ*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)を使用し、個人データを Excel や他の多くの一般的な形式に[*データ インポート/エクスポート ジョブ*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)を使用して繰り返しエクスポートするため、提供されているエンティティを利用するか、新しいエンティティを作成したり、既存のエンティティを拡張したりできます。  または、多くのリストを静的な Excel ファイルにエクスポートして、データの移植性要求を容易にできます。 顧客データを Excel にエクスポートすると、個人データが移植性要求に含まれるように編集することができ、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。 *個人検索レポート* を使用して、個人データとして分類したデータをデータ主体に提供することも検討できます。

***Dynamics 365 Business Central*** では、次の 2 つの機能を使用して、データ主体に顧客データのコピーを提供できます。

顧客データを Excel ファイルにエクスポートできます。 その後に、Excel で顧客データが移植性要求に含まれるように編集し、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。 詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/dynamics365/business-central/about-export-data)」を参照してください。

***Dynamics 365 for Talent*** では、[[個人検索レポートの拡張]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) を使用して、データ対象の個人データのコピーに関する要求をサポートするのに必要な情報を収集できます。

### <a name="rectifying-customer-data"></a>顧客データの修正

***Dynamics 365 for Customer Engagement*** は、不正確または不完全な顧客データを修正したり、顧客データを消去したりするための次の方法を提供します。

- 「顧客データの検索」で説明した機能を使用して顧客データを検索し、Customer Engagement フォーム内で直接データを編集します。 1 行ごとの編集もできますが、複数の行を直接変更することもできます。
- 複数の Customer Engagement レコードを一括編集する場合、Microsoft Office アドインを使用して、データを Microsoft Excel にエクスポートし、変更を加え、変更されたデータを Excel から Dynamics 365 for Customer Engagement にインポートできます。

さらに、Dynamics 365 for Marketing では次の機能も実行できます。

- 1 行または複数の行を直接編集することにより、マイ データのランディング ページを更新します。
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

***Dynamics 365 Customer Service Insights*** では、組織が[顧客データを修正または変更する](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary)機能も用意されています。

***Dynamics 365 for Finance and Operations*** では、[*カスタマイズ ツール*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)も使用できますが、決定と実装はお客様の責任です。

***Dynamics 365 Business Central*** では、不正確または不完全な顧客データを修正する方法が 2 つ用意されています。

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

対象となる個人データを含むデータ要素を手動で編集することにより、顧客カードにある顧客情報など、任意のフィールドに格納された顧客データを変更できます。 詳細については、「[データの入力](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)」を参照してください。

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>ビジネス トランザクションでのエントリの変更について

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>顧客データの処理の制限

データ主体から、顧客データの処理を制限する要求を受けた場合、影響を受ける顧客データをオンライン サービスから簡単に抽出し、クラウド アプリケーションによって提供される処理機能から完全に分離されている別個のコンテナー (オンプレミスのストレージ、またはデータ分離機能を備えた独立した Web サービス) に保存できます。

データ処理のブロックなどの代替メカニズムが ***Dynamics 365 Business Central*** によって提供されており、ユーザーはデータ主体の特定のレコードをブロックすることができます。 詳細については、「[データ主体のデータ処理を制限する](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)」を参照してください。 レコードがブロック済みとしてマークされている場合、Dynamics 365 Business Central はそのデータ主体の顧客データの処理を中断します。 ブロックされたレコードを使用するトランザクションを新たに作成することはできません。たとえば、顧客か店員がブロックされている場合、その顧客に新しい請求書を作成することはできません。

### <a name="deleting-customer-data"></a>顧客データの削除

データ主体から当人の顧客データを削除するように要求された場合は、次のような方法で対処できます。

- 複数の Dynamics 365 レコードを一括編集する場合、Microsoft Office アドインを使用して、データを Microsoft Excel にエクスポートし、変更を加え、変更されたデータを Excel からそのオンライン サービスにインポートし直すことができます。
- 削除するデータを特定し、対象の顧客データを含むデータ要素を手動で削除することにより、任意のフィールドに格納されている顧客データを削除できます。たとえば、データ主体を表す連絡先レコードや個人データを含む他のレコードを物理的に削除できます。

また、Dynamics 365 Marketing では、連絡先を削除すると個人情報の操作に関するデータも同様に削除されます。 カスタム フィールドやエンティティについては、ユーザーがシステムをカスタマイズして、関連するレコードからすべての顧客データが削除され、連絡先レコードとのリンクが解除されて、個人情報がすべて削除されるようにする必要があります。 詳細:「[開発者ガイド (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)」。

***Dynamics 365 Customer Service Insights*** では、組織に対して[顧客データを削除する](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete)機能も提供しています。

***Dynamics 365 for Finance and Operations*** では、[*カスタマイズ ツール*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)を使用して顧客データを削除または変更できます。

***Dynamics 365 Business Central*** では、データ主体から顧客データに含まれている当人の個人データを削除するように要求された場合、この要求に対応する方法がいくつかあります。

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- 対象の顧客データを含むデータ要素を手動で削除することにより、任意のフィールドに保存されている顧客データを削除できます。 詳細については、「[データの入力](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)」を参照してください。
- 連絡先を削除し、Delete Canceled Interaction Log Entries バッチ ジョブを実行して、その連絡先に関するやり取りを削除するなどの方法で、顧客データを直接削除できます。
- メモ、転記済売上、仕入請求書などの顧客データを含む[ドキュメントを削除](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)できます。

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>顧客データのエクスポート

データの移植性要求に対応するため、***Dynamics 365 for Customer Engagement*** の顧客データは、包括的なエンティティ エクスポート機能を使用してエクスポートできます。 顧客データを静的な Excel ファイルにエクスポートして、データ移植性要求を容易にすることができます。 Excel を使用して、移植性要求に含める個人データを編集し、.csv や .xml などのコンピューターで読み取り可能な一般的に使用されるファイル形式で保存できます。

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights*** では、Azure の管理ポータルを使用して[顧客データをエクスポート](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export)します。

***Dynamics 365 for Finance and Operations*** には、[データ管理と統合エンティティ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)が用意されています。これは、提供されているエンティティ、新しく作成されたエンティティ、拡張されたエンティティで、個人データを Excel や他の多くの一般的な形式に[データ インポート/エクスポート ジョブ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)を使用して繰り返しエクスポートできるようにするものです。  または、多くのリストを静的な Excel ファイルにエクスポートして、データの移植性要求を容易にできます。 このようにして顧客データを Excel にエクスポートすると、個人データが移植性要求に含まれるように編集することができ、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。

Dynamics 365 for Finance and Operations と ***Dynamics 365 for Talent*** のどちらでも、ユーザーが個人データとして分類したデータをデータ対象に提供する個人検索レポートが用意されています。 

***Dynamics 365 Business Central*** には、次の機能が用意されています。

- 顧客データを Excel ファイルにエクスポートできます。 その後に、Excel で顧客データが移植性要求に含まれるように編集し、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。 詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/dynamics365/business-central/about-export-data)」を参照してください。
- 顧客データを Excel ファイルにエクスポートできます。 その後に、Excel で顧客データが移植性要求に含まれるように編集し、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。 詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/dynamics365/business-central/about-export-data)」を参照してください。


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>第 2 部: システム生成ログに関する DSR に対する対応

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- 製品およびサービスの利用状況データ (ユーザー アクティビティ ログなど)
- ユーザー検索要求およびクエリ データ
- ユーザーまたはその他のシステムによるシステム機能および相互作用の結果として製品およびサービスによって生成されたデータ

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>システム生成ログのアクセスとエクスポート

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) に移動し、Dynamics 365 全体管理者の資格情報を使用してサインインします。
2. ページ上部にある **[プライバシー]** ドロップダウン リストから、**[データ対象要求]** をクリックします。
3. [**データ主体要求**] ページの [**システム生成ログ**] から、[**データ ログのエクスポート**] をクリックします。
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. あるユーザーに関して新しい要求を作成するには、**[エクスポート データ要求を作成する]** をクリックします。

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

Azure では、ユーザーの組織がネイティブ JSON 形式のデータを指定の Azure Storage コンテナーにエクスポートできるようにすることによってこれをサポートしています。詳細については、「[Azure Storage コンテナーの概要 – BLOB ストレージ](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)」という記事をご覧ください。 取得されるデータにはサービスのセキュリティおよび安定性を損なう可能性があるデータは含まれません。

> [!IMPORTANT]
> ユーザー データをテナントからエクスポートするには、テナント管理者である必要があります。

次の表に、システム生成ログのアクセスとエクスポートについての概要を示します。

| | |
|:----|:---|
| | |
|**Microsoft データ ログのエクスポート ツールが要求の処理を完了するのにはどのくらいの時間がかかりますか?**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**出力はどんな形式ですか?**| 出力は、XML、CSV、または JSON など、コンピューターで読み取り可能な構造化されたファイルになります。 |
|**データ ログのエクスポート ツールはどのようなデータを返しますか?**| データ ログのエクスポート ツールは、Microsoft が保存しているシステム生成ログを返します。 エクスポートされたデータは、各種 Microsoft サービス (Office 365、Azure、Dynamics など) 全体にわたります。 |
|***データ ログのエクスポート ツールには、誰がアクセスしてシステム生成ログに対するアクセス要求を送信できますか?**| Dynamics 365 の全体管理者は、GDPR ログ マネージャー ユーティリティにアクセスできます。 |
|**データは、どのようにしてユーザーに返されますか?**| データは、ユーザー組織の Azure ストレージの場所にエクスポートされます。このデータをユーザーに示す方法または返す方法を決定するのは、ユーザー組織の管理者の役割です。 |
|**システム生成ログ内のデータはどのように表示されますか?**| JSON 形式のシステム生成ログ レコードの例を次に示します。 <br><br> "DateTime": "2017-04-28T12:09:29-07:00"、 <br> "AppName": "SharePoint"、 <br> "Action": "OpenFile"、 <br> "IP": "154.192.13.131"、 <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>システム生成ログの削除

アクセス要求を通して取得されたシステム生成ログを削除するには、そのユーザーをサービスから削除して、Azure Active Directory アカウントを完全に削除する必要があります。 ユーザーを完全に削除する方法については、Azure データ主体の要求のトピックの「[手順 5: 削除](gdpr-dsr-azure.md#step-5-delete)」セクションを参照してください。 ユーザー アカウントを完全に削除すると、元に戻すことはできませんのでご注意ください。 ユーザーのアカウントを完全に削除すると、ユーザーのデータは、ほぼすべての Dynamics 365 サービスのシステム生成ログから 30 日以内に削除されます。ただし、サービスのセキュリティや安定性を損なう可能性のあるデータは削除されません。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
