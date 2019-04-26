---
title: GDPR のための Dynamics 365 データ対象要求
description: コントローラーが DSR 要求に応じて個人データを検索して操作できるように Microsoft 製品、サービス、管理ツールを使用する方法について説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
author: herviicban
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/10/2019
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: f5a7f347dc9b26b54cf6bc1fd3a6bdb55d46fe63
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285216"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr"></a>GDPR のための Dynamics 365 データ対象要求

EU データ保護規則 (GDPR) では、個人個人 (規則では*データ対象*と呼ばれる) に対して、雇用主やその他の会社または組織 (*データ コントローラー*または単に*コントローラー*と呼ばれる) が収集した個人データを管理する権利を与えます。個人データは、GDPR の下では、特定済みまたは特定可能な個人と関連するあらゆるデータを指す広範な概念として定義されています。GDPR は、データ対象に対して、当人の個人データに関する固有の権利を与えています。この権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、または、別のコントローラーに移動できるようにするための電子形式での受信が含まれます。当人の個人データに関する権利を行使する目的でデータ対象がコントローラーに対して行う正式な要求は、*データ対象の権利要求*、または DSR 要求と呼ばれます。<span id="_Toc510437912" class="anchor"><span id="_Toc508792504" class="anchor"></span></span>

このガイドでは、コントローラーが DSR 要求に応じて個人データを検索して操作できるように Microsoft 製品、サービス、管理ツールを使用する方法について説明します。特に、Microsoft クラウドにある個人データの検索、アクセス、処理に関する方法を扱います。このガイドで説明するプロセスの概要は次のとおりです。

1. ***検出***—検索/検出ツールを使用すると、DSR 要求の対象となる可能性がある顧客データをより簡単に見つけることができます。対応の対象となり得るドキュメントが収集されたら、後続のステップの DSR アクションを 1 つ以上実行することで要求に対応できます。場合によっては、その要求が DSR 要求への対応に関する組織のガイドラインを満たしていないと判断することもあります。

2. ***アクセス***—Microsoft クラウドにある個人データを取り出し、コピーが要求されている場合には、データ対象が利用できる形でコピーを作成します。

3. ***修正***—要求されたアクションに応じて個人データを変更したり、他の操作を実行したりします。

4.  ***制限***—さまざまなオンライン サービスのライセンスを削除するか、該当するサービスを無効にする (可能な場合) ことで、個人データの処理を制限します。また、データを Microsoft クラウドから削除して、オンプレミスまたは別の場所で保持することもできます。

5. ***削除***—Microsoft のクラウドに格納されていた個人データを完全に削除します。

6. ***エクスポート***—個人データの電子的コピー (コンピューターで読み取り可能な形式) をデータ対象に提供します。

このガイドの各セクションでは、Microsoft のクラウドにある個人データについて DSR 要求がなされた場合に、その対応としてデータ コントローラー組織が実行できる技術的な手順の概要を示します。

### <a name="gdpr-terminology"></a>GDPR 用語

このガイドに関連する用語を以下に定義します。

- <em>コントローラー</em>—単独または他者と共同で、個人データの処理に関する目的と手段を決定する個人や法人、公的機関、団体、その他の組織。そのような処理の目的と手段が ＥＵ 法もしくは構成国法によって決定される場合、コントローラーまたはその指名に関する具体的な基準が ＥＵ 法もしくは構成国法によって提供される場合があります。

- *個人データ*および<em>データ対象—</em>特定済みまたは特定可能な個人 (データ対象) と関連するあらゆる情報を指します。特定可能な個人とは、その個人の名前、ID 番号、位置データ、オンライン ID、または当該個人に固有の 1 つ以上の身体的、生理学的、遺伝的、心理的、経済的、文化的、社会的な識別情報などの要素を参照することにより、直接または間接的に特定される人物です。

- <em>プロセッサ</em>—コントローラーに代わって個人データを処理する個人や法人、公的機関、団体、その他の組織。

- *顧客データ* – エンタープライズ サービスを使用することにより、Microsoft オンライン サービスの使用条件の定義に従って、顧客またはその代理人から Microsoft に提供されるすべてのデータを指します。これにはすべてのテキスト、サウンド、ビデオ、イメージ ファイルが含まれます。

- *システム*-*生成ログ –* Microsoft がエンタープライズ サービスをユーザーに提供するうえで役立つ、Microsoft により生成されるログおよび関連データ。システム生成ログには、一意識別子など、通常それ自体では個人を特定できないものの、エンタープライズ サービスをユーザーに提供するために使用される、システム生成番号などの仮名化データが主に格納されます。システム生成ログには、ユーザー名など、エンド ユーザーに関する個人情報が格納されることもあります。  

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>管理者としての責任を果たすためのこのガイドの活用方法

このガイドは、2 つの部分に分かれており、GDPR で定められた権利を行使するデータ対象による要求に応じて、ユーザーが Microsoft クラウドのデータを検索して操作できるように Dynamics 365 製品、サービス、管理ツールを使用する方法について説明します。パート 1 では、顧客データに含まれる個人データを取り上げます。その後、パート 2 で、システム生成ログによってキャプチャされるその他の仮名化された個人データについて取り上げます。

**パート 1: 顧客データに含まれる個人データに関するデータ対象の権利 (DSR) 要求に対応する。** このガイドのパート 1 では、Dynamics 365 アプリケーション (サービスとしてのソフトウェア) から、ユーザーがオンライン サービスに提供した顧客データの一部として処理される個人情報にアクセス、修正、制限、削除、エクスポートの処理を実行する方法を説明します。

**パート 2: 仮名化データに関するデータ対象の権利要求に対応する。** Dynamics 365 エンタープライズ サービスを使用すると、サービスを提供する目的で Microsoft によりある種の情報が生成されます (このドキュメントでは*システム生成ログ*と呼びます)。これは、システム内でのアクションを特定する目的でエンド ユーザーによって残された利用履歴に限られます。この種のデータは、そのほかの情報を使用しない限り、特定のデータ対象に関連付けることはできませんが、GDPR では個人情報として定められている場合があります。このガイドのパート 2 では、Dynamics 365 によって生成されるシステム生成ログのアクセス、削除、エクスポート方法について説明します。

### <a name="preparing-for-data-subject-rights-investigations"></a>データ主体権限の調査の準備

データ主体が当人の権限を行使して要求を行う場合は、次の点を考慮してください。

- 要求の一部としてデータ対象から提供された情報を基に、その人物と役割 (従業員、顧客、仕入先など) を正確に特定します。この種の情報には、名前、従業員 ID、顧客番号、その他の ID などが考えられます。

- 要求のデータと日時を記録します (要求の完了期限は 30 日です)。

- その要求が、データ対象からの要求が承諾または拒否に関する組織の要件を満たしているかどうかを確認します。たとえば、その要求を実行することにより、組織のその他の法律上、財務上、規制上の義務に抵触しないか、および、他者の権利や自由を侵害しないかを確認する必要があります。

- 要求に関連する情報があることを確認します。

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-includced-in-customer-data"></a>第 1 部: 顧客データに含まれる個人データに関するデータ主体権限要求に対する対応

次の記事では、Dynamics 365 で処理される顧客データに含まれる個人データに関する DSR 要求に備えて対応するのに役立つ情報を説明します。重要な点として、個人データは、オンライン サービス サブスクリプションの一連のサービスに際して Microsoft によって処理される別のカテゴリのデータ (管理者データや「Microsoft のプライバシーに関する声明」で定義されているサポート データなど) に含まれている場合があります。このドキュメントでは、ユーザーが Dynamics 365 に提供した顧客データ内に存在する個人データに影響する DSR 要求の検出と管理処理に絞って説明します。

Dynamics 365 は、サービスとしてのソフトウェア (SaaS) として複数のデータ処理機能を提供するオンライン サービスです。このため、Dynamics 365 には、性質や目的などの特性が異なる、売上データ、トランザクション、財務、人事情報などの多様なデータの処理を目的としたさまざまな機能が用意されています。これらの多様性を考慮して、Dynamics 365 では、顧客データを処理するのに必要となる複数のフォーム、フィールド、スキーマ、エンド ポイント、ロジックを提供しています。各アプリケーションで DSR 要求を処理できる複数の方法にも、この多様性が反映されています。Dynamics 365 アプリケーションで、特定の DSR 要求を処理する方法が複数用意されている場合、各アプリケーションによって提供されている技術的な説明の参照先がこのガイドに記載されています。

### <a name="dynamics-365"></a>Dynamics 365
#### <a name="finding-customer-data"></a>顧客データの検索

データ対象の権利要求に対する対応の最初の段階として、要求の対象となっている顧客データを検索して特定します。

顧客データの適切な分類は、Microsoft Dynamics 365 Customer Engagement の個人データを処理する際の基盤になります。Dynamics 365 for Customer Engagement では、データ分類を基にしたアプリケーションの拡張機能を柔軟に構築できます。適切な情報分類により、情報を個人データとして特定でき、データ対象の要求に対応する際にその情報を検索して取得することが可能になります。適切な情報分類は、個人データの収集と管理に関する法律や規制の要件を遵守する上でも役立ちます。

Microsoft は、データ主体の権利要求への対応とそれに伴う顧客データへのアクセスに関して、ユーザーを支援する機能を提供します。ただし、個人データが適切に保存および分類されるようにするのは、お客様の責任です。

<span id="_Toc511225657" class="anchor"></span>***Dynamics 365 for Customer Engagement*** には、高度な検索、関連性検索、レコード検索など、レコード内の個人データをユーザーが検索するための機能が複数用意されています。いずれの機能でも、個人データを特定または検索できます。

-   [[高度な検索]](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)

-   [[関連性検索]](https://docs.microsoft.com/dynamics365/customer-engagement/basics/relevance-search-results) は、ダッシュボードを使用して後で参照するために保存することができます。

-   [[レコード検索]](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records) は、複数のレコードの種類に対して検索を実行できます。

Dynamics 365 for Marketing には、次の追加機能が用意されています。

1.  [[Power BI レポートの作成]](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) は、顧客データをフィルター処理し特定する機能です。

2.  顧客データを含む可能性のあるその他のデータ ポイントを特定するには、マーケティング実行の取引先担当者や対象についてインサイト ビューを使用します。

Dynamics 365 Customer Service Insights では、個人データのコピー要求に応じたり、個人データを削除したり、データ主体の検出要求 (DSR) の対象となる個人データを検索したりする機能を提供します。 詳細については、「[Dynamics 365 Customer Service Insights の GDPR 準拠の概要](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary)」を参照してください。

<span id="_Toc511225658" class="anchor"></span>***Dynamics 365 Finance and Operations*** には、顧客データを検索するための方法が複数用意されています。顧客データを検索するには、テナント管理者として次の操作を実行します。

-   個人データをすばやく検出する目的にかなう方法で顧客データを整理します。この目的に関しては、「[データ インベントリの分類方法](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory)」をご覧ください。

-   個人データを検索および収集するには、[[個人検索レポート]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) を使用します。

-   [[個人検索レポートの拡張]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) では、エンティティを新規に作成するか既存のエンティティを拡張することにより、個人検索レポートを拡張します。

-   検索機能とフィルター処理機能を使用して、特定の個人データを検索し、Microsoft Office エクスポート機能を使用してそのデータをエクスポートしたり、ブラウザーの拡張機能を使用して .pdf ファイルにその情報を書き込んだりできます。

-   個人データを検索してエクスポートするユーザー設定のフォームを作成します。

-   認証済み顧客が当人の個人データを確認できる外部ポータルまたは Web サイトを作成します。


***Dynamics for Business Central*** は、顧客データを検索するためのいくつかの方法を提供します。詳細については、「[データの検索、フィルター処理、および並べ替え](https://docs.microsoft.com/dynamics-nav-app/ui-enter-criteria-filters)」を参照してください。

<span id="_Toc511225660" class="anchor"></span>***Dynamics 365 for Talent*** には、特定の個人データを検索するための高度な検索機能とフィルター処理機能に加えて、ブラウザーの拡張機能を使用して .pdf ファイルにその情報をエクスポートまたは書き込むための Microsoft Office エクスポート機能が用意されています。

-   顧客データを検索および収集するには、[[個人検索レポート]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) を使用します。

-   新しいエンティティを作成するか、既存のエンティティを拡張することにより、[個人検索レポートを拡張します](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report)。

### <a name="providing-a-copy-of-customer-data"></a>顧客データのコピーの提供

***Dynamics 365 for Customer Engagement*** の顧客データは、包括的なエンティティ エクスポート機能を使用してエクスポートできます。顧客データを静的な Excel ファイルにエクスポートして、データの移植性要求を容易にできます。また、Excel を使用すると、個人データが移植性要求に含まれるように編集することができ、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式で保存できます。

さらに、Dynamics 365 for Marketing には[専用 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) が用意されており、キャプチャされた顧客とのやり取りに関するその他のレコード (個人データを含む可能性がある) を取得する拡張機能を顧客が構築できます。この API は、関連するすべての情報をバックエンド システムから読み込み、その情報を単一のポータブル ドキュメントに組み立てます。

***Dynamics 365 for Finance and Operations*** 内の顧客データは、包括的なエンティティ エクスポート機能を使用してエクスポートできます。テナントの管理者は、[*データ管理と統合エンティティ*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)を使用し、個人データを Excel や他の多くの一般的な形式に[*データ インポート/エクスポート ジョブ*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)を使用して繰り返しエクスポートするため、提供されているエンティティを利用するか、新しいエンティティを作成したり、既存のエンティティを拡張したりできます。または、多くのリストを静的な Excel ファイルにエクスポートして、データの移植性要求を容易にできます。顧客データを Excel にエクスポートすると、個人データが移植性要求に含まれるように編集することができ、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。*個人検索レポート * を使用して、個人データとして分類したデータをデータ対象に提供することも検討できます。 

***Dynamics 365 Business Central*** では、次の 2 つの機能を使用して、データ対象に顧客データのコピーを提供できます。

顧客データを Excel ファイルにエクスポートできます。その後に、Excel で顧客データが移植性要求に含まれるように編集し、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/ja-JP/dynamics365/business-central/about-export-data)」をご覧ください。

***Dynamics 365 for Talent*** では、[[個人検索レポートの拡張]](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) を使用して、データ対象の個人データのコピーに関する要求をサポートするのに必要な情報を収集できます。

### <a name="rectifying-customer-data"></a>顧客データの修正

<span id="_Toc511225663" class="anchor"></span>***Dynamics 365 for Customer Engagement*** は、不正確または不完全な顧客データを修正したり、顧客データを消去したりするための次の方法を提供します。

-   「顧客データの検索」で説明した機能を使用して顧客データを検索し、Customer Engagement フォーム内で直接データを編集します。1 行ごとの編集もできますが、複数の行を直接変更することもできます。

-   複数の Customer Engagement レコードを一括編集する場合、Microsoft Office アドインを使用して、データを Microsoft Excel にエクスポートし、変更を加え、変更されたデータを Excel から Dynamics 365 for Customer Engagement にインポートできます。

さらに、Dynamics 365 for Marketing では次の機能も実行できます。

-   1 行または複数の行を直接編集することにより、マイ データのランディング ページを更新します。

-   ページに含めることができるの最大数の編集可能な連絡先フィールドが設定された[サブスクリプション センター](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) ページを準備します。これにより、エンドユーザーは、自分の情報を最大限に更新できます。

***Dynamics 365 for Finance and Operations*** では、[*カスタマイズ ツール*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)も使用できますが、決定と実装はお客様の責任です。

<span id="_Toc511225664" class="anchor"></span>***Dynamics 365 Business Central*** では、不正確または不完全な顧客データを修正する方法が 2 つ用意されています。

Business Central の複数のレコードをすばやく一括編集する場合、[Business Central Excel アドイン](https://docs.microsoft.com/ja-JP/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)を使用して Excel にリストをエクスポートし、複数のレコードを修正してから、修正したデータを Excel から Business Central に発行することができます。詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/ja-JP/dynamics365/business-central/about-export-data)」をご覧ください。

- 対象となる個人データを含むデータ要素を手動で編集することにより、顧客カードにある顧客情報など、任意のフィールドに格納された顧客データを変更できます。詳細については、「[データの入力](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)」をご覧ください。

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>ビジネス トランザクションでのエントリの変更について
全般エントリ、顧客エントリ、税元帳エントリなどのトランザクション レコードは、エンタープライズ リソース プランニング システムの整合性に不可欠です。財務その他のトランザクションの一部をなす個人データは、財務法の遵守 (税法など)、不正行為防止 (セキュリティ監査証跡)、業界の認定資格の遵守を目的として、その状態のままで保持されます。このため、Dynamics 365 for Finance and Operations および Dynamics 365 Business Central では、このようなレコードのデータ変更を制限しています。

ビジネス トランザクション レコードに個人データを保存している場合、データ対象の要求を承諾して個人データの修正、削除、処理の制限などを実行するには、Dynamics 365 Business Central の[カスタマイズ機能](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index)を使用する以外に方法はありません。[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)データ対象からの主性要求を承諾して、修正を実行するのはお客様の責任です。

### <a name="restricting-the-processing-of-customer-data"></a>顧客データの処理の制限

データ対象から、顧客データの処理を制限する要求を受けた場合、影響を受ける顧客データをオンライン サービスから簡単に抽出し、クラウド アプリケーションによって提供される処理機能から完全に分離されている別個のコンテナー (オンプレミスのストレージ、またはデータ分離機能を備えた独立した Web サービス) に保存できます。

データ処理のブロックなど、代替メカニズムが ***Dynamics 365 Business Central*** によって提供されており、ユーザーはデータ対象の特定のレコードをブロックできます。詳細については、「[データ対象のデータ処理を制限する](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject)」をご覧ください。レコードがブロック済みとしてマークされている場合、Dynamics 365 Business Central はそのデータ対象の顧客データの処理を中断します。ブロックされたレコードを使用するトランザクションを新たに作成することはできません。たとえば、顧客か店員がブロックされている場合、その顧客に新しい請求書を作成することはできません。

### <a name="deleting-customer-data"></a>顧客データの削除

データ主体から当人の顧客データを削除するように要求された場合は、次のような方法で対処できます。

-   複数の Dynamics 365 レコードを一括編集する場合、Microsoft Office アドインを使用して、データを Microsoft Excel にエクスポートし、変更を加え、変更されたデータを Excel からそのオンライン サービスにインポートし直すことができます。

-   削除するデータを特定し、対象の顧客データを含むデータ要素を手動で削除することにより、任意のフィールドに格納されている顧客データを削除できます。たとえば、データ対象を表す連絡先レコードや個人データを含む他のレコードを物理的に削除できます。

また、Dynamics 365 Marketing では、連絡先を削除すると個人情報の操作に関するデータも同様に削除されます。カスタム フィールドやエンティティについては、ユーザーがシステムをカスタマイズして、関連するレコードからすべての顧客データが削除され、連絡先レコードとのリンクが解除されて、個人情報がすべて削除されるようにする必要があります。詳細については、「[開発者ガイド (Marketing)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide)」をご覧ください。

***Dynamics 365 for Finance and Operations*** では、[*カスタマイズ ツール*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page)を使用して顧客データを削除または変更できます。

***Dynamics 365 Business Central*** では、データ対象から顧客データに含まれている当人の個人データを削除するように要求された場合、この要求に対応する方法がいくつかあります。

-   Business Central の複数のレコードをすばやく一括編集する場合、[Business Central Excel アドイン](https://docs.microsoft.com/ja-JP/dynamics365/business-central/finance-analyze-excel#the--excel-add-in)を使用して Excel にデータをエクスポートし、複数のレコードを削除してから、その変更を Excel から Business Central に発行し直すことができます。詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/ja-JP/dynamics365/business-central/about-export-data)」をご覧ください。

-   対象の顧客データを含むデータ要素を手動で削除することにより、任意のフィールドに保存されている顧客データを削除できます。詳細については、「[データの入力](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data)」をご覧ください。

-   連絡先を削除し、Delete Canceled Interaction Log Entries バッチ ジョブを実行して、その連絡先に関するやり取りを削除するなどの方法で、顧客データを直接削除できます。

-   メモ、転記済売上、仕入請求書などの顧客データを含む[ドキュメントを削除](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents)できます。

個別レコードの一括削除または個別削除のほかに、***Dynamics 365 for Talent*** から完全に削除できるのは契約関係が終了した従業員のみであることにご注意ください。[契約関係が終了した従業員の削除についてはこの手順に従います](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data)。

### <a name="exporting-customer-data"></a>顧客データのエクスポート

データの移植性要求に対応するため、***Dynamics 365 for Customer Engagement*** の顧客データは、包括的なエンティティ エクスポート機能を使用してエクスポートできます。顧客データを静的な Excel ファイルにエクスポートして、データの移植性要求を容易にできます。また、Excel を使用すると、個人データが移植性要求に含まれるように編集することができ、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式で保存できます。

さらに、Dynamics 365 for Marketing には[専用 API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) が用意されており、キャプチャされた顧客とのやり取りに関するその他のレコード (個人データを含む可能性がある) を取得する拡張機能を顧客が構築できます。この API は、関連するすべての情報をバックエンド システムから読み込み、その情報を単一のポータブル ドキュメントに組み立てます。

<span id="_Toc511225669" class="anchor"></span>***Dynamics 365 for Finance and Operations*** には、[データ管理と統合エンティティ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity)が用意されています。これは、提供されているエンティティ、新しく作成されたエンティティ、拡張されたエンティティで、個人データを Excel や他の多くの一般的な形式に[データ インポート/エクスポート ジョブ](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job)を使用して繰り返しエクスポートできるようにするものです。または、多くのリストを静的な Excel ファイルにエクスポートして、データの移植性要求を容易にできます。このようにして顧客データを Excel にエクスポートすると、個人データが移植性要求に含まれるように編集することができ、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。

Dynamics 365 for Finance and Operations と ***Dynamics 365 for Talent*** のどちらでも、ユーザーが個人データとして分類したデータをデータ対象に提供する個人検索レポートが用意されています。 

- <span id="_Toc511225670" class="anchor"></span>***Dynamics 365 Business Central*** には、次の機能が用意されています。

- 顧客データを Excel ファイルにエクスポートできます。その後に、Excel で顧客データが移植性要求に含まれるように編集し、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/dynamics-nav-app/about-export-data)」をご覧ください。

顧客データを Excel ファイルにエクスポートできます。その後に、Excel で顧客データが移植性要求に含まれるように編集し、.csv や .xml などの、コンピューターで読み取り可能な一般的に使用されるファイル形式でそのファイルを保存できます。詳細については、「[ビジネス データを Excel にエクスポートする](https://docs.microsoft.com/ja-JP/dynamics365/business-central/about-export-data)」をご覧ください。

### <a name="microsoft-social-engagement"></a>Microsoft Social Engagement

<span id="_Toc511166412" class="anchor"></span>Microsoft Social Engagement は、顧客データやソーシャル コンテンツに含まれうる個人データを処理するので、ソーシャル ネットワークから取得した個人データを参照する際に DSR 要求を独特な方法で処理します。ソーシャル コンテンツは公開コンテンツであり、ソーシャル メディア ネットワーク (Twitter、Facebook、YouTube など)、および Microsoft Social Engagement 内で実行される顧客の検索クエリに対する応答でのデータ インデックス作成サービスやデータ集約サービスから収集されます。ソーシャル コンテンツは顧客データではありません。ソーシャル コンテンツの処理、使用、保存に関する制限については、Microsoft オンライン サービス使用条件で詳しく説明しています。

### <a name="finding-personal-data"></a>個人データの検索

データ対象の要求に対する対応の最初の段階として、要求の対象となっている個人データを検索して特定します。Microsoft Social Engagement は次のデータを保存します。

#### <a name="for-social-media-users"></a>ソーシャル メディア ユーザーの場合

- Social Engagement がソーシャル プラットフォームから取得する、ソーシャル メディア ユーザー データ (Social Engagement では*作成者*と呼ばれる)。これには、名前、ユーザー名、プロファイル画像、場所、Web サイトの他に、作成者によって提供されている場合は自己紹介も含まれることがあります。

- Social Engagement の従業員が作成者をグループ化し分類する目的で使用する作成者タグ。インフルエンサー、競合企業、ファンなどがあります。

#### <a name="for-employees"></a>従業員の場合

- 従業員名、連絡先情報、およびプロファイル画像を含み、Office 365 で管理されるユーザー プロファイル。

- 投稿アラートやトレンド アラートを作成した従業員によって提供されるメール アドレス。

- ソーシャル プラットフォーム上の他のユーザーと連携する目的で、Social Engagement 内で従業員によって認証されるソーシャル メディア アカウント (Social Engagement では*ソーシャル プロファイル*と呼ばれる)。これらのアカウントは、従業員が所有する場合と組織が所有しする場合があり、従業員がソーシャル プラットフォームにアカウントを登録するときに提供するデータが含まれます。これらのプロファイルは、ソーシャル メディア上の組織を表しており、Social Engagement アプリケーション内から組織に代わって投稿を操作するために使用されます。

- Power BI でソーシャル メディア上のチーム パフォーマンスを分析するために、ユーザーの組織が [Social Engagement コンテンツ パック](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi)を使用する場合の、Power BI でのユーザー名。

最初の段階は、要求の対象となる個人データを検索して確認することです。これは、データ対象の要求が、承諾または拒否に関する組織の要件を満たしているかどうかを確認するのに役立ちます。たとえば、個人データを検索して確認すると、その要求を処理することによって他人の権利と自由に悪影響を及ぼす恐れがあり、要求が組織の要件を満たしていないことが判明する場合があります。

#### <a name="social-media-users-authors"></a>ソーシャル メディア ユーザー (作成者)

-   個人データを検索するには、[作成者の検索と削除](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#find-and-delete-an-author)にある最初の 4 つのステップに従います。

-   ソーシャル プラットフォーム上で特定の定義済みコンテンツを検索する Social Engagement ルールを従業員が作成する場合があります。これらのルールを確実に検索するには、[Twitter](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-twitter-rule)、[Instagram](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-an-instagram-rule)、[YouTube](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/add-rules-search-topic#add-a-includetnyoutubeincludestn-youtubemd-rule) などの適切なアカウントに対するソーシャル アカウント検索ルールを確認します。

-   作成者の作成者タグを検索するには、まず [[作成者]](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/understand-filters#authors) で [[投稿をフィルター処理]](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/use-filters#add-edit-or-remove-a-filter) し、次に [[作成者タグを表示]](https://go.microsoft.com/fwlink/?linkid=864795) を選択します。

##### <a name="your-employees"></a>従業員の場合 

検索方法

-   ユーザー プロファイルを検索するには、[Office 365 管理センター](https://portal.office.com/adminportal/home)に移動します。**管理センター**で、**[ユーザー]** を選択します。**[アクティブなユーザー]** ページにあるリストから、ユーザーを検索します。  
    Social Engagement で、**[設定] \> [ユーザー管理]** の順に移動し、Office 365 から自動的に同期されている情報を表示します。

-   アラートの受信者を検索するには、「[管理者としてアラート受信者を管理する](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)」にある最初の 2 つのステップに従います。

-   従業員が入力したソーシャル プロファイル データを検索するには、**[設定] \> [ソーシャル プロファイル]** の順に移動します。(詳細については「[ソーシャル プロファイルの管理](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles)」をご覧ください)。

-   Power BI のユーザー名を検索するには、Social Engagement Power BI ダッシュボードを開き、従業員名でフィルター処理します。

### <a name="providing-a-copy-of-personal-data"></a>個人データのコピーの提供

GDPR では、要求に応じて個人データのコピーを取得する権利をデータ対象に付与しています。そのリクエストに関係する可能性のあるデータを含む顧客コンテンツを発見した場合、データ対象にコピーを提供するかどうかを決定するのは、ユーザーとその組織の責任です。

#### <a name="social-media-users-authors"></a>ソーシャル メディア ユーザー (作成者)

- 作成者の個人データをエクスポートするには、「[作成者情報のエクスポート](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information)」にあるデータを Excel ファイルにエクスポートするための手順に従います。

- 特定の作成者に追加された作成者タグを抽出するために、[作成者タグ データをエクスポート](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data)することができます。

##### <a name="your-employees"></a>従業員の場合
エクスポート方法

- ユーザー プロファイルから顧客データをエクスポートするには、[Office 365 管理センター](https://portal.office.com/adminportal/home)に移動します。**管理センター**で、**[ユーザー]** を選択します。**[アクティブなユーザー]** ページで、データをエクスポートするユーザーを検索します。対象ユーザー以外のユーザーをすべて削除してから、**[エクスポート]** を選択してデータを .csv ファイルにエクスポートします。Excel を使用すると、このファイルの情報を表示できます。

- アラートの受信者のメール アドレス (アラートに含まれる唯一の顧客データ) をエクスポートするには、「[管理者としてアラート受信者を管理する](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)」の手順に従います。それから、**[エクスポート]** を選択して、この受信者を含むアラートの Excel リストをダウンロードします。

- Power BI からユーザー名をエクスポートする場合。[[Engagement レポート]](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) に、ソーシャル メディア上のチーム パフォーマンスのレポートに含まれるユーザー名が表示されます。このデータをエクスポートするには、PowerBI ダッシュボード内のユーザーでフィルター処理するか、[[レポート]](https://docs.microsoft.com/power-bi/power-bi-report-add-filter) を選択し、[[データのエクスポート]](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data) を選択します。

### <a name="rectifying-personal-data"></a>個人データの修正

不正確または不完全な個人データを修正するには

#### <a name="social-media-users-authors"></a>ソーシャル メディア ユーザー (作成者)

-   ソーシャル プラットフォーム (Twitter、WordPress、Tumblr など) 上で変更を加えるには、データの所有者 (作成者) に確認する必要があります。ソーシャル メディア アカウント内のデータは、データ対象が所有しているので、その所有者のみがデータを変更できます。作成者がデータを変更すると、Social Engagement は修正された詳細を自動的に同期します。

-   作成者タグを修正するには、「[作成者タグの変更](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#change-author-tags)」の手順に従います。

##### <a name="your-employees"></a>従業員の場合

-   ユーザー プロファイル: ユーザー プロファイルの顧客データを変更するには、「[Office 365 でユーザー名とメール アドレスを変更する](https://support.office.com/article/change-a-user-name-and-email-address-in-office-365-fb5ac074-e203-4e1f-9843-b9d1a3e03297)」、および「[Office 365 に自分のプロファイル写真を追加する](https://support.office.com/article/add-your-profile-photo-to-office-365-2eaf93fd-b3f1-43b9-9cdc-bdcd548435b7)」をご覧ください。  
    これらの変更は、Social Engagement で自動的に同期されます。これらを検索するには、**[設定]** \> **[ユーザー管理]** の順に移動します。

-   アラートの受信者: [アラートを変更する](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#change-an-alert)ことができます。

### <a name="restricting-the-processing-of-personal-data"></a>個人データの処理の制限

#### <a name="social-media-users-authors"></a>ソーシャル メディア ユーザー (作成者)
Social Engagement で作成者の顧客データの処理を中止するには、[作成者を削除](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author)します。

こうすることにより、このデータ対象のデータや将来の投稿の処理が今後ブロックされ、この作成者に関するデータやこの作成者が作成したデータはすべて削除されます。Social Engagement は、新しい投稿を受信すると、その作成者が以前に削除されているかどうかを自動的に確認し、削除された作成者の投稿である場合はその投稿を破棄します。これは、ソーシャル プラットフォーム上のユーザー アカウントには影響しません。

##### <a name="your-employees"></a>従業員の場合

- 従業員の顧客データの処理を停止する場合、Office 365 で[その従業員のライセンスを削除](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1)できます。この処理を実行すると、ユーザー ロールやプロファイルなどの Social Engagement 関連の項目すべて、関連するすべてのユーザー定義カスタム設定、アラート、アクティビティ マップ、およびストリームが削除されます。検索トピックとソーシャル プロファイルは削除されません。ただし、管理者は削除されたユーザーのソーシャル プロファイルの所有権を継承しており、要求に応じてそれらを削除できます。

- アラート電子メール メッセージの送信を制限するには、「[管理者としてアラート受信者を管理する](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)」の手順に従って、あるメール アドレスを追加したアラートすべてからそのメール アドレスを削除します。

### <a name="deleting-personal-data"></a>個人データの削除

GDPR では、特定の状況下で、コントローラーから個人データの削除を要求する権利をデータ対象に与えています。組織からそのようなデータを削除することによる「忘れられる権利」は、GDPR の主要な保護対象です。

#### <a name="social-media-users-authors"></a>ソーシャル メディア ユーザー (作成者)

Social Engagement に含まれる、ある作成者の個人データすべてを完全に削除するには、この作成者のソーシャル プロファイルすべてを削除します。「[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors)[作成者の削除](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#delete-an-author)」をご覧ください。  
処理を実行すると、元に戻すことはできません。この処理により、Social Engagement 上のこの作成者に関するデータやこの作成者が作成したデータはすべて削除され、この作成者のデータや将来の投稿の処理が今後ブロックされます。Social Engagement は、新しい投稿を受信すると、その作成者が以前に削除されているかどうかを自動的に確認し、削除された作成者の投稿である場合はその投稿を破棄します。これは、ソーシャル プラットフォーム上のユーザー アカウントには影響しません。

作成者のタグを削除するには、「[作成者タグの削除](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#remove-author-tags)」をご覧ください。

>(注) 特定の作成者の情報を削除するように依頼された場合、最初にその作成者の ID を確認し、要求を検証することをお勧めします。ID を確認するには、その作成者のソーシャル メディア アカウントから、プライベート メッセージを送信するように要求できます。

Social Engagement は、さまざまなソーシャル プラットフォーム (Twitter、WordPress、Tumblr など) のコンプライアンス フィードを実装しており、そのソーシャル プラットフォーム上でトリガーされた投稿の削除などのシグナルに直接反応します。Social Engagement をインストールすると、この機能は自動的にアクティブになるので、ユーザーが操作する必要はありません。また、Social Engagement には、Social Engagement から得たソーシャル コンテンツ上に構築されるサービス (Dynamics 365 for Customer Engagement など) がこれらのシグナルを継承できるようにするメカニズムも用意されています。

##### <a name="your-employees"></a>従業員の場合

ある従業員の顧客データすべてを完全に削除するには、Office 365 で[その従業員のライセンスを削除](https://support.office.com/article/remove-licenses-from-users-in-office-365-for-business-9b497c85-d0a4-4735-80fa-d3565bc05bd1)できます。

-   この処理を実行すると、ユーザー ロールやプロファイルなどの Social Engagement 関連の項目すべて、関連するすべてのユーザー定義カスタム設定、アラート、アクティビティ マップ、およびストリームが削除されます。検索トピックとソーシャル プロファイルは削除されません。(管理者は削除されたユーザーのソーシャル プロファイルの所有権を継承しており、要求に応じてそれらを削除できます)。

-   これらの変更は、Social Engagement で自動的に同期されます。これらを検索するには、**[設定] \> [ユーザー管理]** の順に移動します。

-   PowerBI の Engagement レポートに含まれるその従業員のエントリは、当人の個人データが削除されると匿名化されます。

[ソーシャル プロファイルを削除](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-social-profiles#delete-a-social-profile)できます。

あるメール アドレスを追加したアラートすべてからそのメール アドレスを削除するには、「[管理者としてアラート受信者を管理する](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)」の手順に従います。[](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)

### <a name="exporting-personal-data"></a>個人データのエクスポート
データ主体に電子形式で当人の個人データを提供できます。

#### <a name="social-media-users-authors"></a>ソーシャル メディア ユーザー (作成者)

作成者の個人データをエクスポートするには、「[作成者情報のエクスポート](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/manage-authors#export-author-information)」にあるデータを Excel ファイルにエクスポートするための手順に従います。

特定の作成者に追加された作成者タグを抽出するために、[作成者タグ データをエクスポート](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/author-tags#export-author-tags-data)することができます。

##### <a name="your-employees"></a>従業員の場合
エクスポート方法

- ユーザー プロファイルから顧客データをエクスポートするには、[Office 365 管理センター](https://portal.office.com/adminportal/home)に移動します。**管理センター**で、**[ユーザー]** を選択します。**[アクティブなユーザー]** ページで、データをエクスポートするユーザーを検索します。対象ユーザー以外のユーザーをすべて削除してから、**[エクスポート]** を選択してデータを .csv ファイルにエクスポートします。Excel を使用すると、このファイルの情報を表示できます。

- アラートの受信者のメール アドレス (アラートに含まれる唯一の個人データ) をエクスポートするには、「[管理者としてアラート受信者を管理する](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/email-alerts#manage-alert-recipients-as-administrator)」の手順に従います。それから、**[エクスポート]** を選択して、この受信者を含むアラートの Excel リストをダウンロードします。

- Power BI からユーザー名をエクスポートする場合。[[Engagement レポート]](https://docs.microsoft.com/dynamics365/customer-engagement/social-engagement/get-content-pack-for-power-bi) に、ソーシャル メディア上のチーム パフォーマンスのレポートに含まれるユーザー名が表示されます。このデータをエクスポートするには、PowerBI ダッシュボード内のユーザーでフィルター処理するか、[[レポート]](https://docs.microsoft.com/power-bi/power-bi-report-add-filter) を選択し、[[データのエクスポート]](https://docs.microsoft.com/power-bi/power-bi-visualization-export-data) を選択します。

## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>第 2 部: システム生成ログに関する DSR に対する対応

Microsoft は、GDPR における「個人データ」の広範な定義の下では個人のものとみなされるシステム生成ログに対して、アクセス、エクスポート、および削除するための機能も提供しています。次に、GDPR の下で個人のものとみなされるシステム生成のログの例を示します。

-   製品およびサービスの利用状況データ (ユーザー アクティビティ ログなど)

-   ユーザー検索要求およびクエリ データ

-   ユーザーまたはその他のシステムによるシステム機能および相互作用の結果として製品およびサービスによって生成されたデータ

<span id="_Toc511045103" class="anchor"><span id="_Toc511043191" class="anchor"><span id="_Toc511041446" class="anchor"><span id="_Toc511030410" class="anchor"><span id="_Toc510769888" class="anchor"></span></span></span></span></span>システム生成ログのデータを制限または修正する機能はサポートされていない点に注意してください。システム生成ログのデータは、Microsoft のクラウド内で実行された実際のアクションや診断データの一部を構成しているため、そのようなデータを変更すると、アクションの履歴記録が損なわれたり、詐欺やセキュリティのリスクが増大したりする恐れがあります。

### <a name="accessing-and-exporting-system-generated-logs"></a>システム生成ログのアクセスとエクスポート

管理者は、特定のユーザーの Dynamics 365 サービスおよびアプリケーションの使用に関連付けられたシステム生成ログにアクセスできます。システム生成ログにアクセスしてエクスポートするには、次の操作を実行します。

1.  [[Microsoft Service Trust Portal]](https://servicetrust.microsoft.com/) に移動して、Dynamics 365 全体管理者の資格情報を使用してサインインします。

2.  ページ上部にある **[プライバシー]** ドロップダウン リストから、**[データ対象要求]** をクリックします。

3.  **[データ対象要求]** ページの **[システム生成ログ]** から、**[データ ログのエクスポート]** をクリックします。

> **[データ ログのエクスポート]** が表示されます。所属する組織によって送信されたエクスポート データ要求の一覧が表示されます。

4.  あるユーザーに関して新しい要求を作成するには、**[エクスポート データ要求を作成する]** をクリックします。

新しい要求を作成すると、その要求は **[データ ログのエクスポート]** ページの一覧に表示されます。このページから、要求の現在の状態を追跡できます。要求が完了すると、リンクをクリックしてシステム生成ログにアクセスできるようになります。このログは、要求の作成から 30 日以内に、組織で指定した Azure Storage の場所にエクスポートされます。データは、JSON や XML などの、コンピューターで読み取り可能な一般的なファイル形式で保存されます。Azure アカウントや Azure Storage の場所がない場合、Data Log Export ツールでシステム生成ログをエクスポートできるように、組織の Azure アカウントや Azure Storage の場所を作成する必要があります。

Azure では、ユーザーの組織がネイティブ JSON 形式のデータを指定の Azure Storage コンテナー[にエクスポートできるようにすることによってこれをサポートしています。「Azure Storage コンテナーの概要 – BLOB ストレージ](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)」という記事をご覧ください。

**重要**: ユーザー データをテナントからエクスポートするには、テナント管理者でなければなりません。

次の表に、システム生成ログのアクセスとエクスポートについての概要を示します。

<table>
<tbody>
<tr class="odd">
<td align="left"><strong>Microsoft データ ログのエクスポート ツールが 1 つの要求を完了するのにどのくらいの時間がかかりますか?</strong>
<td align="left">これは、いくつかの要因によって異なる場合があります。ほとんどの場合、1 ～ 2 日で完了しますが、最長で 30 日間かかる場合があります。</td>
</tr>
<tr class="odd">
<td align="left"><strong>出力はどんな形式ですか?</strong></td>
<td align="left">出力は、XML、CSV、または JSON など、コンピューターで読み取り可能な構造化されたファイルになります。</td>
</tr>
<tr class="even">
<td align="left"><strong>データ ログのエクスポート ツールはどのようなデータを返しますか?</strong></td>
<td align="left">データ ログのエクスポート ツールは、Microsoft が保存しているシステム生成ログを返します。エクスポートされたデータは、各種の Microsoft サービス (Office 365、Azure、Dynamics など) 全体にわたります。</td>
</tr>
<tr class="odd">
<td align="left"><strong>データ ログのエクスポート ツールには、誰がアクセスしてシステム生成ログに対するアクセス要求を送信できますか?</strong></td>
<td align="left">Dynamics 365 の全体管理者は、GDPR ログ マネージャー ユーティリティにアクセスできます。</td>
</tr>
<tr class="even">
<td align="left"><strong>データは、どのようにしてユーザーに返されますか?</strong></td>
<td align="left">データは、ユーザー組織の Azure ストレージの場所にエクスポートされます。このデータをユーザーに示す方法または返す方法を決定するのは、ユーザー組織の管理者の役割です。</td>
</tr>
<tr class="odd">
<td align="left"><strong>システム生成ログ内のデータはどのように表示されますか?</strong></td>
<td align="left"><p>JSON 形式のシステム生成ログ レコードの例を次に示します。</p>
<p>[{</p>
<p>  &quot;DateTime&quot;: &quot;2017-04-28T12:09:29-07:00&quot;,</p>
<p>  &quot;AppName&quot;: &quot;SharePoint&quot;,</p>
<p>  &quot;Action&quot;: &quot;OpenFile&quot;,</p>
<p>  &quot;IP&quot;: &quot;154.192.13.131&quot;,</p>
<p>  &quot;DevicePlatform&quot;: &quot;Windows 1.0.1607&quot;</p>
<p>}]</p></td>
</tr>
</tbody>
</table>

[注] 一部の機能では、セキュリティおよび監査上の理由で、個人情報の整合性を維持するため、そのような情報を含むシステム生成ログのエクスポートや削除ができません。

### <a name="deleting-system-generated-logs"></a>システム生成ログの削除
アクセス要求によって取得したシステム生成ログを削除するには、サービスからユーザーを削除して、そのユーザーの Azure Active Directory アカウントを完全に削除する必要があります。ユーザーの完全な削除の手順については、このガイドのセクション「[ユーザーの削除](https://microsoft-my.sharepoint.com/personal/kated_microsoft_com/Documents/DSR%20Guide%20v4%20-(newly%20created%20for%20O365%20only).docx#_Deleting_a_user)」を参照してください。ユーザー アカウントの完全な削除は、開始後に取り消すことができなくなる点に注してください。

ユーザー アカウントを完全に削除すると、そのユーザーのデータは、ほぼすべての Dynamics 365 サービスのシステム生成ログから 30 日以内に削除されます。

#### <a name="learn-more"></a>詳細情報

[Microsoft Trust Center](https://www.microsoft.com/ja-JP/TrustCenter/Privacy/gdpr/default.aspx)
