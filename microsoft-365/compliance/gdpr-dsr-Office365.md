---
title: GDPR および CCPA に基づく Office 365 データ対象要求
description: GDPR および CCPA に基づくユーザーの権利と、DSR への対応で企業が Office 365 を使用してデータを検索および処理する方法について説明します。
keywords: Office 365、DSR、Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR、CCPA
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00ad2290a252ad014e9b364d9aa5ce59f94c6516
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817646"
---
# <a name="office-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のための Office 365 データ対象要求

## <a name="introduction-to-dsrs"></a>DSR について

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR. The controller is obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller. A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.

同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。 また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、"売上" として分類された特定のデータ転送の "オプトアウト/オプトイン" 要件を規定します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。

このガイドでは、DSR に対応するために個人データや個人情報を検索して処理を行えるように Office 365 製品、サービス、管理ツールを使用する方法について説明します。 具体的には、Microsoft のクラウドに保存されている個人データや個人情報の検索、アクセス、および操作方法について説明します。 このガイドに記載されているプロセスの概要を次に示します。

- **検出:** 検索および検出ツールを使用して、DSR の対象である可能性がある顧客データを簡単に検索します。 可能性のある応答ドキュメントが収集されると、以下の手順に示す 1 つ以上の DSR アクションを実行して、要求に応答できます。 または、DSR への応答に関する組織のガイドラインを要求が満たしていないと判断する場合もあります。
- **アクセス:** Microsoft クラウドにある個人データを取り出し、要求がある場合は、データ主体が利用できるコピーを作成します。
- **修正:** 必要に応じて、個人データを変更したり、要求された他の操作を個人データに対して実行したりします。
- **制限:** さまざまな Microsoft クラウド サービスのライセンスを削除するか、可能な場合は該当するサービスを無効にすることで、個人データの処理を制限します。 また、データを Microsoft クラウドから削除してオンプレミスまたは別の場所で保持することもできます。
- **削除:** Microsoft クラウドに格納されていた個人データを完全に削除します。
- **エクスポート/受信 (移植性):** 個人データまたは個人情報の電子コピー (コンピューターで読み取り可能な形式) をデータ主体に提供します。 CCPA における個人情報とは、識別された人、または識別可能な人に関するあらゆる情報のことです。 個人の私的、公的、または職業上の役割による区別はありません。 "個人情報" と定義された用語は、GDPR における "個人データ" とほぼ同義です。 ただし、CCPA では家族データおよび世帯データも含まれます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。

### <a name="terminology"></a>用語

このガイドに関連する GDPR の用語の定義を以下に示します。

- **管理者:** 単独または他者と共同で、個人データの処理に関する目的と手段を決定する自然人や法人、公的機関、団体、その他の組織。そのような処理の目的と手段が EU 法もしくは加盟国の法律によって決定される場合、コントローラーまたはその指名に関する具体的な基準が EU 法または加盟国の法律によって提供される場合があります。
- **個人データおよびデータ主体:** 特定されたまたは特定可能な自然人 ('データ主体') に関するあらゆる情報。特定可能な自然人とは、その者の名前、ID 番号、位置データ、オンライン ID、または当該自然人に固有の 1 つ以上の特に身体的、生理学的、遺伝的、心理的、経済的、文化的、社会的な識別情報などの要素を参照することにより、直接または間接的に特定することができる者のことです。
- **処理者:** 管理者に代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。
- **顧客データ:** これは、顧客または顧客の代理がエンタープライズ サービスの使用を通じて Microsoft に提供する、テキスト、音声、ビデオ、画像ファイル、およびソフトウェアを含むすべてのデータのことです。 顧客データには次の両方が含まれます: (1) 特定を可能にするエンド ユーザーの情報 (例: Azure Active Directory でのユーザー名と連絡先情報)、および (2) 特定のサービスでお客様がアップロードまたは作成する顧客コンテンツ (例: Word または Excel ドキュメント、または Exchange Online メールのテキスト内の顧客コンテンツ、SharePoint Online サイトに追加された、または OneDrive for Business アカウントに保存された顧客コンテンツ)。
- **システム生成ログ:** Microsoft がエンタープライズ サービスをユーザーに提供するうえで役立つ、Microsoft により生成されるログおよび関連データ。 システム生成ログには主に固有 ID などの仮名化データが含まれています。固有 ID とは一般的に、それ自体は特定の個人を識別しないものの、エンタープライズ サービスをユーザーに提供するために使われるシステム生成番号です。 また、ユーザー名などの、特定を可能にするエンド ユーザーの情報がシステム生成ログに含まれることもあります。

### <a name="how-to-use-this-guide"></a>このガイドの使用方法

ユース ケースに関連する情報が簡単に見つかるように、このガイドは 4 つの部分に分かれています。

- **[パート 1: 顧客データについての DSR への対応](#part-1-responding-to-dsrs-for-customer-data):** *顧客データ*は、日常の業務において Office 365 で生成および格納されるデータです。 データを作成できる最も一般的な Office 365 アプリケーションには、Word、Excel、PowerPoint、Outlook、OneNote などがあります。 また、Office 365 には SharePoint Online、Teams、Forms などのアプリケーションも含まれているため、他のユーザーとの連携を強化できます。 このガイドのパート 1 では、Office 365 オンライン サービスでのデータ作成と保存に使用される Office 365 アプリケーションからデータを検出、アクセス、修正、制限、削除、およびエクスポートする方法について説明します。 ここでは、Microsoft がお客様組織のデータ処理者としての役割を務めるため、テナント管理者に DSR 機能を公開している製品とサービスを扱います。
- **[パート 2: Office 365 で生成されたインサイトに関する DSR への対応](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365):** Office 365 は、Delve、MyAnalytics、Workplace Analytics などのサービスを通じて特定のインサイトを提供します。 これらのインサイトが生成される方法と、そのようなインサイトに関連する DSR に対応する方法については、このガイドのパート 2 で説明します。
- **[パート 3: システム生成ログに対する DSR への対応](#part-3-responding-to-dsrs-for-system-generated-logs):** Office 365 エンタープライズ サービスを使用すると、Microsoft によってオンライン サービス機能の使用状況やパフォーマンスを記録するサービス ログなどの情報が生成されます。 サービスで生成されたデータのほとんどには、Microsoft によって生成された仮の識別子が含まれています。そのため、このドキュメントでは通常このカテゴリを、*システム生成ログ*と呼びます。 追加の情報を使用せずにこのデータを特定のデータ主体への属性を特定できませんが、一部は GDPR の「個人データ」の定義に基づいて、個人データと見なされる可能性があります。 このガイドのパート 3 では、システム生成ログのアクセス方法、削除方法、およびエクスポート方法について説明します。
- **[パート 4: DSR に役立つその他のリソース](#part-4-additional-resources-to-assist-you-with-dsrs):** このガイドのパート 4 では、特定の Office 365 製品とサービスが使用されるときに Microsoft がデータ管理者となる、限定的なシナリオを示します。

>[!NOTE]
>In most cases, when users in your organization use Microsoft Office 365 products and services, you are the data controller and Microsoft is the processor. As a data controller, you are responsible for responding to the data subject directly. To assist you with this, Parts 1-3 of this guide detail the technical capabilities available to your organization to respond to a DSR request. In some limited scenarios, however, Microsoft will be the data controller when people use certain Office 365 products and services. In these cases, the information in Part 4 provides guidance on how data subjects can submit DSR requests to Microsoft.

### <a name="office-365-national-clouds"></a>Office 365 国別クラウド

The Microsoft Office 365 services are also available in the following national cloud environments: [Office 365 Germany](https://docs.microsoft.com/microsoft-365/admin/admin-overview/learn-about-office-365-germany), [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china), and [Office 365 US Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans). Most of the guidance for managing data subject requests described in this document applies to these national cloud environments. However, due to the isolated nature of these environments, there are some exceptions. Where notable for a given subsection, these exceptions are called out in a corresponding note.

### <a name="hybrid-deployments"></a>ハイブリッド展開

Your organization may consist of Microsoft offerings that are a combination of cloud-based services and on-premises server products. In general, a hybrid deployment is typically the sharing of user accounts (identity management) and resources (such as mailboxes, web sites, and data) that exist in the cloud and on-premises. Common hybrid scenarios include:

- Exchange ハイブリッド展開。この展開では、オンプレミス メールボックスを使用するユーザーと Excnahge Online メールボックスを使用するユーザーが混在しています。
- SharePoint ハイブリッド展開。この展開では、サイトおよびファイル サーバーがオンプレミスにあり、OneDrive for Business アカウントが Office 365 にあります。
- Azure Activity Directory と同期するオンプレミスの ID 管理システム (Active Directory)。これは、Office 365 の基盤となるディレクトリ サービスです。

When responding to a DSR request, you may have to determine if data that's responsive to a DSR request is in the Microsoft cloud or in your on-premise organization, and then take the appropriate steps to respond to that request. The Office 365 Data Subject Request Guide (this guide) provides guidance for responding to cloud-based data. For guidance for data in your on-premises organization, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>パート 1: 顧客データについての DSR への対応

顧客データについての DSR に対応するためのガイダンスは、次の 4 つのセクションに分かれています。

- [コンテンツ検索の電子情報開示ツールを使用した DSR への対応](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [アプリ内機能を使用した DSR への対応](#using-in-app-functionality-to-respond-to-dsrs)
- [DSR 訂正要求への対応](#responding-to-dsr-rectification-requests)
- [DSR 制限要求への対応](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>顧客データの DSR の対象となる可能性のある Office 365 アプリケーションを特定する方法

個人情報の検索場所や検索対象を判断するために、組織内のユーザーが Office 365 でのデータ作成や保存に使用できる Office 365 アプリケーションを特定することが役立ちます。 これを知ることで、DSR の範囲内にある Office 365 アプリケーションが絞り込まれ、DSR に関連する個人データの検索方法とアクセス方法の判断に役立ちます。 具体的には、コンテンツ検索ツールを使用できるかどうか、またはデータが作成されたアプリケーションのアプリ内機能を使用する必要があるかどうかということです。

A quick way to identify the Office 365 applications that people in your organization are using to create Customer Data is to determine which applications are included in your organization's Microsoft 365 for business subscription. To do this, you can access user accounts in the Office 365 admin portal and look at the product licensing information. See [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>コンテンツ検索の電子情報開示ツールを使用した DSR への対応

When looking for personal data within the larger set of data your organization creates and stores using in Office 365, you may want to first consider which applications people have most likely used to author the data you're looking for. Microsoft estimates that over 90% of an organization's data that is stored in Office 365 is authored in Word, Excel, PowerPoint, OneNote, and Outlook. Documents authored in these Office applications, even if purchased through Microsoft 365 Apps for enterprise or an Office perpetual license, are most likely stored on a SharePoint Online site, in a user's OneDrive for Business account, or in a user's Exchange Online mailbox. That means you can use the Content Search eDiscovery tool to search (and perform other DSR-related actions) across SharePoint Online sites, OneDrive for Business accounts, and Exchange Online mailboxes (including the sites and mailboxes associated with Microsoft 365 Groups, Microsoft Teams, EDU Assignments) to find documents and mailbox items that may be relevant to the DSR you're investigating. You can also use the Content Search tool to discover Customer Data authored in other Office 365 applications.

次の表に、「顧客が作成したコンテンツ」の作成にユーザーが使用する Office 365 アプリケーションのリストを示します。これらのアプリケーションはコンテンツ検索を使用した検出が可能です。 DSR ガイドのこのセクションでは、これらの Office 365 アプリケーションを使用して作成されたデータの検出、アクセス、エクスポート、および削除方法について説明します。

***表 1: コンテンツ検索を使用して顧客データを検索できるアプリケーション***

| | |
| :---: | :---:|
![カレンダー アイコン](../media/O365-DSR-Doc-Final_image3.png) <br> カレンダー | ![SharePoint アイコン](../media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Excel アイコン](../media/o365-excel-64x64.png) <br> Excel | ![Skype for Business アイコン](../media/o365-skypeforbusiness-64x64.png) <br> Skype for Business |
| ![Office Lens アイコン](../media/o365-lens-64x64.png) <br> Office Lens | ![タスク アイコン](../media/O365-DSR-Doc-Final_image8.png) <br> タスク |
| ![OneDrive アイコン](../media/o365-OneDrive-64x64.png) <br> OneDrive for Business |![Teams アイコン](../media/o365-teams-64x64.png) <br> Teams |
| ![OneNote アイコン](../media/o365-onenote-64x64.png) <br> OneNote| ![To do アイコン](../media/o365-todo-64x64.png) <br> やるべきこと |
| ![Outlook アイコン](../media/o365-outlook-64x64.png) <br> Outlook/Exchange | ![ビデオ アイコン](../media/O365-DSR-Doc-Final_image14.png) <br> ビデオ |
| ![People アイコン](../media/O365-DSR-Doc-Final_image15.png) <br> People | ![Visio アイコン](../media/o365-visio-64x64.png) <br> Visio |
| ![PowerPoint アイコン](../media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Word アイコン](../media/o365-word-64x64.png) <br> Word
||

>[!NOTE]
>The Content Search eDiscovery tool is not available in [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china). This means you won't able to use this tool to search for and export Customer Data in the Office 365 applications shown in Table 1. However, you can use the In-Place eDiscovery tool in Exchange Online to search for content in user mailboxes. You can also use the eDiscovery Center in SharePoint Online to search for content in SharePoint sites and OneDrive accounts. Alternatively, you can ask a document owner to help you find and make changes or deletions to content or export it if necessary. For more information, see:</br><br> * [インプレース電子情報開示検索を作成する](https://docs.microsoft.com/exchange/create-in-place-ediscovery-search-exchange-2013-help)<br> * [SharePoint Online の電子情報開示センターをセットアップする](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>コンテンツ検索を使用した個人データの検索

DSR に対応するための最初のステップは、DSR の対象となる個人データを見つけることです。 ここでは、Office 365 の電子情報開示ツールを使用して個人データを検索 (Office 365 内にあるすべての組織データで) するか、データが作成されたネイティブ アプリケーションへ直接移動します。 当該の個人データの検索と確認を行うこの最初のステップは、データ主体の要求を承認または却下するための組織の要件を DSR が満たしているかどうかを判断するために役立ちます。 たとえば、当該の個人データを検索および確認した後に、これを行うことで他人の権利と自由に悪影響を及ぼす可能性があったり、組織が正当な営業上の利益を維持している業務記録に個人データが含まれているために、要求が組織の要件を満たしていないと判断する可能性があったりします。

As previously stated, Microsoft estimates that over 90% of an organization's data is created with Office applications, such as Word and Excel. This means that you can use the Content Search in the Security & Compliance Center to search for most DSR-related data.

This guide assumes that you or the person searching for personal data that may be responsive to a DSR request is familiar with or has experience using the Content Search tool in the Security & Compliance Center. For general guidance on using Content Search, see [Content Search in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search). Be sure that the person running the searches has been assigned the necessary permissions in the Security & Compliance Center. This person should be added as a member of the eDiscovery Manager role group in the Security & Compliance Center; see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions). Consider adding other people in your organization who are involved in investigating DSRs to the eDiscovery Manager role group, so they can perform the necessary actions in the Content Search tool such as previewing and exporting search results. However, unless you set up compliance boundaries (as described [here](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)) be aware that an eDiscovery Manager can search all content locations in your organization, including ones that may not be related to a DSR investigation.

データが見つかったら、データ主体の要求に対応するために特定の操作を実行できます。

>[!NOTE]
>Office 365 Germany では、セキュリティ/コンプライアンス センターは https://protection.office.de にあります。

#### <a name="searching-content-locations"></a>コンテンツの場所の検索

コンテンツ検索ツールを使用すると、次の種類のコンテンツの場所を検索できます。

- Exchange Online メールボックス。 これには Microsoft 365 グループと Microsoft Teams に関連付けられたメールボックスが含まれます
- Exchange Online のパブリック フォルダー
- SharePoint Online サイト。 これには Microsoft 365 グループと Microsoft Teams に関連付けられたサイトが含まれます
- OneDrive for Business アカウント

>[!NOTE]
>This guide assumes that all data that might be relevant to a DSR investigation is stored in Office 365; in other words, stored in the Microsoft cloud. Data stored on a user's local computer or on-premises on your organization's file servers is outside the scope of a DSR investigation for data stored in Office 365. For guidance about responding to DSR requests for data in on-premises organizations, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

#### <a name="tips-for-searching-content-locations"></a>コンテンツの場所を検索するためのヒント

- まず、組織内のすべてのコンテンツの場所 (1 回の検索で検索できる場所) を検索して、検索クエリと一致する項目が含まれているコンテンツの場所を素早く特定します。 その後、関連項目を含む特定の場所に検索範囲を絞り込んで検索を再実行できます。
- Use search statistics to identify the top locations that contain items that match your search query. See [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).
- DSR の対象ユーザーが最近行ったファイルとフォルダーのアクティビティについて、監査ログを検索します。 監査ログの検索を実行すると、ユーザーが最近操作したリソースの名前と場所を含む監査レコードの一覧が返されます。 この情報を使用してコンテンツ検索クエリを作成できる場合があります。 「[セキュリティ/コンプライアンス センターで監査ログを検索する](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)」を参照してください。

#### <a name="building-search-queries-to-find-personal-data"></a>検索クエリを作成し個人データを見つける

ほとんどの場合、調査する DSR には、個人データを検索するためのキーワード検索クエリで使用できる識別子が含まれています。 検索クエリで使用して個人データを検索できる一般的な識別子の一部を次に示します。

- メール アドレスまたはエイリアス
- 電話番号
- 郵送先住所
- 従業員の ID 番号
- 国民識別番号または EU 加盟国の社会保障番号

ほとんどの場合、調査する DSR には識別子と、検索クエリで使用できる要求の対象となる個人データに関するその他の詳細が含まれています。

電子メール アドレスや従業員 ID に限定して検索すると、多くの場合で多数の結果が返されます。 DSR に最も関連するコンテンツを返すように検索範囲を絞り込むには、検索クエリに条件を追加します。 条件を追加すると、キーワードと検索条件は **AND** ブール演算子によって論理的に結合されます。 つまり、キーワードと条件の*両方*に一致する項目のみが検索結果として返されます。

The following table lists some conditions you can use to narrow the scope of a search. The table also lists the values that you can use for each condition to search for specific document types and mailbox items.

***表 2: 条件を使用した検索範囲の絞り込み***

||||
| :--- | :--- |:--- |
|**条件**|**説明** |**条件値の例**|
| ファイルの種類 | ドキュメントまたはファイルの拡張子。 Office 365 アプリケーションで作成された Office ドキュメントとファイルを検索する場合は、この条件を使用します。 この条件は、SharePoint Online サイトと OneDrive for Business アカウントにあるドキュメントを検索する場合にも使用します。<br/>対応するドキュメントのプロパティはファイルの種類です。 <br/>検索可能なファイル拡張子の完全なリストについては、「SharePoint での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類」(https://technet.microsoft.com/library/jj219530.aspx)) を参照してください。|&nbsp;&bull;&nbsp;&nbsp;csv – コンマ区切り値 (CSV) ファイルを検索。Excel ファイルは CSV 形式で保存できます。CSV ファイルは簡単に Excel にインポートできます<br><br>&bull;&nbsp;&nbsp;docx – Word ファイルを検索 <br><br>&bull;&nbsp;&nbsp;mpp – Project ファイルを検索<br/><br>&bull;&nbsp;&nbsp;one – OneNote ファイルを検索 <br><br>&bull;&nbsp;&nbsp;pdf – PDF 形式で保存されたファイルを検索 <br><br>&bull;&nbsp;&nbsp;pptx – PowerPoint ファイルを検索 <br><br>&bull;&nbsp;&nbsp;xlxs – Excel ファイルを検索 <br><br>&bull;&nbsp;&nbsp;vsd – Visio ファイルを検索 <br><br>&bull;&nbsp;&nbsp;wmv – Windows Media ビデオ ファイルを検索 <br>|
| メッセージの種類 | 検索するメール メッセージの種類。 検索する電子メールメッセージの種類。連絡先 (People)、会議 (予定表) タスク、または Skype for Business の会話をメールボックスで検索するには、この条件を使用します。 対応する電子メールのプロパティは "*種類*" です。|&bull;&nbsp;&nbsp;*contacts – メールボックスの [個人用の連絡先] リスト (People) を検索 <br><br>&bull;&nbsp;&nbsp;* email - メール メッセージを検索 <br><br>&bull;&nbsp;&nbsp;*im - Skype for Business の会話を検索 <br><br>&bull;&nbsp;&nbsp;* meetings - 予定や会議出席依頼 (予定表) を検索 <br><br>&bull;&nbsp;&nbsp;*tasks – [マイ タスク] リスト (タスク) を検索。この値を使用すると、Microsoft To Do で作成されたタスクも返されます。<br>|
| コンプライアンス タグ |The label assigned to an email message or a document. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. Use this condition to search for items that have been automatically or manually assigned a label.<br/>This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information. See the "Using Content Search to find all content with a specific label applied to it" section in [Overview of labels in Office 365.](https://docs.microsoft.com/microsoft-365/compliance/labels)|compliancetag="personal data"|
||||

There are many more email and document properties and search conditions that you can use to build more complex search queries. See the following sections in the [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions) help topic for more information.

- [検索可能なメール プロパティ](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [検索可能なサイト (ドキュメント) のプロパティ](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [検索条件](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>SharePoint リスト、ディスカッション、およびフォーム内の個人データを検索する

In addition to searching for personal data in documents, you can also use Content Search to search for other types of data that's created by using native SharePoint Online apps. This includes data created by using SharePoint lists, discussions, and forms. When you run a Content Search and search SharePoint Online sites (or OneDrive for Business accounts) data from lists, discussions, and forms that match the search criteria will be returned in the search results.

##### <a name="examples-of-search-queries"></a>検索クエリの例

次に、キーワードと条件を使用して DSR に対応する個人データを検索する検索クエリの例を示します。 例では、クエリの 2 つのバージョンを示します。1 つはキーワード構文 (条件は [キーワード] ボックスに含まれています)、もう 1 つは条件を使用する GUI ベースのクエリのバージョンを示しています。

##### <a name="example-1"></a>例 1

この例では、指定したメール アドレスを含む SharePoint Online サイトおよび OneDrive for Business アカウントにある Excel ファイルが返されます。 メール アドレスがファイルのメタデータに含まれる場合にも、ファイルが返されることがあります。

***キーワード構文***

```Query
pilar@contoso.com AND filetype="xlxs"
```

***GUI***

![キーワード ダイアログ](../media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>例 2

この例では、指定した従業員 ID または生年月日を含む SharePoint Online サイトおよび OneDrive for Business アカウントにある Excel または Word ファイルが返されます。

(98765 OR "01-20-1990") AND (filetype="xlxs" OR filetype="docx")

***GUI***

![キーワード ダイアログ](../media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>例 3

この例では、指定された ID 番号 (フランスの社会保障番号 (INSEE)) を含む電子メール メッセージが返されます。

```Query
"1600330345678 97" AND kind="email"
```

***GUI***

![キーワード ダイアログ](../media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>部分的にインデックスが作成されたアイテムをコンテンツ検索で使用する

部分的にインデックスが作成されたアイテム (*インデックス未作成のアイテム*とも呼ばれます) とは、なんらかの理由で検索用にインデックスが作成されなかった Exchange Online メールボックスのアイテムと SharePoint Online および OneDrive for Business サイトのドキュメントのことです。コンテンツ検索を使用して検索できないコンテンツであることを意味します。 ほとんどの電子メール メッセージとサイト ドキュメントは [Office 365 のインデックス作成の制限](https://docs.microsoft.com/microsoft-365/compliance/limits-for-content-search)の範囲内に収まるため、正常にインデックスが作成されます。 電子メール メッセージやファイルが検索用にインデックス作成されない理由には、次が含まれます。

- ファイルの種類が[認識できないか、インデックス作成でサポートされていない](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)。 ファイルの種類がインデックス作成でサポートされている場合でも、特定のファイルでインデックス作成のエラーが発生することがあります
- 電子メール メッセージに画像ファイルなど、有効なハンドラがない添付ファイルがある (これは電子メール アイテムのインデックス作成が部分的になる最も一般的な原因です)
- 電子メール メッセージに添付されたファイルが大きすぎるか、添付ファイルが多すぎる

We recommend that you learn more about partially indexed items so that you can work with them when responding to DSR requests. For more information, see:

- [Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)
- [Office 365 の電子情報開示で部分的にインデックスが作成されたアイテムを調査する](https://docs.microsoft.com/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery)
- [インデックス未作成のアイテムをエクスポートする](export-search-results.md)

#### <a name="tips-for-working-with-partially-indexed-items"></a>部分的にインデックスが作成されたアイテムの使用のヒント

It's possible that data responsive to a DSR investigation may be in a partially indexed item. Here's some suggestions for working with partially indexed items:

- 検索を実行すると、推定される部分的にインデックスが作成されたアイテムの数が検索の統計に表示されます。 この推定には、SharePoint Online と OneDrive for Business の部分的にインデックスが作成されたアイテムは含まれていません。 コンテンツ検索のレポートをエクスポートして、部分的にインデックスが作成されたアイテムに関する情報を取得します。 **Unindexed Items.csv** レポートには、インデックス未作成のアイテムに関する情報が含まれます。これには、アイテムの場所、アイテムが SharePoint Online または OneDrive for Business にある場合の URL、件名 (メッセージの場合) またはドキュメントの名前などが含まれます。 詳細については、「[コンテンツ検索レポートのエクスポート](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)」を参照してください。

- コンテンツ検索の結果で返される、部分的にインデックスが作成されたアイテムの統計とリストは、すべて、検索されたコンテンツの場所の部分的なアイテムです。

- 潜在的に DSR 調査に対応する、部分的にインデックスが作成されたアイテムを検索するには、次のいずれかを実行します。

##### <a name="export-all-partially-indexed-items"></a>部分的にインデックスが作成されたアイテムをすべてエクスポートする

コンテンツ検索の結果と部分的にインデックスが作成されたアイテムの両方を、検索したコンテンツの場所からエクスポートします。 部分的にインデックスが作成されたアイテムのみをエクスポートすることもできます。 それらをネイティブのアプリケーションで開いて、コンテンツを確認します。 このオプションは、SharePoint Online および OneDrive for Business からアイテムをエクスポートする場合に使用する必要があります。 「[セキュリティ/コンプライアンス センターからコンテンツ検索の結果をエクスポートする方法](export-search-results.md)」を参照してください。

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>部分的にインデックスが作成されたアイテムの特定のセットをメールボックスからエクスポートする

部分的にインデックスが作成されたメールボックス アイテムを検索からすべてエクスポートする代わりに、コンテンツ検索を再実行し、部分的にインデックスが作成されたアイテムの特定のリストを検索して、そのアイテムをエクスポートします。 この操作は、メールボックスのアイテムに対してのみ行うことができます。 詳細については、「[Office 365 の対象指定コンテンツ検索のための CSV ファイルを準備する](https://docs.microsoft.com/microsoft-365/compliance/csv-file-for-an-id-list-content-search)」を参照してください。

### <a name="next-steps"></a>次の手順

DSR に関連する個人データを見つけたら、そのデータを見つけるために使用した具体的なコンテンツ検索を保持してください。 多くの場合、DSR 対応プロセスの他の手順 ([個人データのコピーの取得](#providing-a-copy-of-personal-data)、[エクスポート](#exporting-personal-data)、[完全な削除など](#deleting-personal-data)) を完了するためにこの検索を再使用することになります。

### <a name="additional-considerations-for-selected-applications"></a>アプリケーションの選択に関する追加の考慮事項

ここからの各セクションでは、次に示す Office 365 アプリケーションでデータを検索する際に注意が必要な事項について説明します。

- [Office Lens](#office-lens)
- [OneDrive for Business および SharePoint エクスペリエンスの設定](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [Microsoft Teams for Education](#microsoft-teams-for-education)
- [Microsoft To Do](#microsoft-to-do)
- [Skype for Business](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

Office Lens (iOS、Android、および Windows を実行しているデバイスでサポートされるカメラ アプリ) を使用すると、ホワイトボード、紙の書類、名刺など、テキストが含まれているものの写真を撮影できます。 Office Lens では、光学式文字認識テクノロジを使用して画像内のテキストを抽出し、そのテキストを Office ドキュメント (Word、PowerPoint、OneNote など) や PDF ファイルに保存します。 ユーザーは、画像から抽出したテキストが含まれているファイルを Office 365 の自分の OneDrive for Business アカウントにアップロードできます。 つまり、Office Lens の画像から作成されたファイル内のデータは、コンテンツ検索ツールを使用して検索、アクセス、削除、およびエクスポートできるということです。 Office Lens の詳細については、以下をご覧ください。

- [Office Lens for iOS](https://support.microsoft.com/ja-JP/office/microsoft-office-lens-for-ios-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Office Lens for Android](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Office Lens for Windows](https://support.microsoft.com/ja-JP/office/office-lens-for-windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>OneDrive for Business および SharePoint エクスペリエンスの設定

In addition to user-created files stored in OneDrive for Business accounts and SharePoint Online sites, these services store information about the user that is used to enable various experiences. Users still in your organization can access much of this information by using in-product functionality. The following information provides guidance on how to access, view, and export OneDrive for Business and SharePoint Online application data.

##### <a name="sharepoint-user-profiles"></a>SharePoint ユーザー プロファイル

ユーザーの Delve プロファイルにより、ユーザーは SharePoint Online ユーザー プロファイルに保存されるプロパティを保守管理できます。このプロパティには、誕生日、携帯電話番号 (およびその他の連絡先情報)、自己紹介、プロジェクト、技能と専門知識、学歴、興味の対象、趣味などがあります。

###### <a name="end-users"></a>エンド ユーザー

End users can discover, access, and rectify SharePoint Online user profile data using the Delve profile experience. See [View and update your profile in Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba) for more details.

ユーザーが別の方法で自分の SharePoint プロファイル データにアクセスするには、自分の OneDrive for Business アカウントの [**プロフィールの編集**] ページに移動します。このページにアクセスするには、OneDrive for Business アカウントの URL で **EditProfile.aspx** パスに移動します。 たとえば、<strong>user1@contoso.com</strong> というユーザーの OneDrive for Business アカウントは次の場所になります。

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

[プロフィールの編集] ページの URL は次のようになります。

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

Azure Active Directory から取得されるプロパティは、SharePoint Online では変更できません。 ただし、ユーザーは Office 365 のヘッダーで自分の**写真**を選択して [**マイ アカウント**] を選択することで、[**アカウント**] ページに移動できます。 ユーザーがこの場所でプロパティを変更するには、ユーザー プロファイル プロパティの検出、アクセス、または修正のために管理者の協力が必要になることがあります。

###### <a name="admins"></a>管理者

管理者は、SharePoint Online 管理センターでプロファイルのプロパティへアクセスして修正できます。 **SharePoint Online 管理センター**で [**ユーザー プロファイル**] タブをクリックします。[**ユーザー プロファイルの管理**] をクリックし、ユーザー名を入力して [**検索**] をクリックします。 管理者は、任意のユーザーを右クリックして、[**個人用プロファイルの編集**] を選択できます。 Azure Active Directory から取得されるプロパティは、SharePoint Online では変更できません。

An admin can export all User Profile properties for a user by using the **Export-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See  [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

ユーザー プロファイルの詳細については、「[SharePoint Online 管理センターでユーザー プロファイルを管理する](https://docs.microsoft.com/sharepoint/manage-user-profiles)」を参照してください。

##### <a name="user-information-list-on-sharepoint-online-sites"></a>SharePoint Online サイトのユーザー情報リスト

ユーザーの SharePoint ユーザー プロファイルの一部は、ユーザーが参照したサイトまたはアクセス許可を持つすべてのサイトの [ユーザー情報] リストに同期されます。 これは、SharePoint Online エクスペリエンス (ドキュメント ライブラリの [ユーザー] 列など) でユーザーの基本情報 (ドキュメントの作成者名など) を表示するために使用されます。 [ユーザー情報] リストのデータは、SharePoint ユーザー プロファイルに保存された情報と一致し、ソースが変更されると自動的に修正されます。 削除されたユーザーの場合、このデータは SharePoint の列フィールドの参照整合性のために、そのユーザーが操作したサイトに残されます。 

Admins can control which properties are replicable inside the SharePoint admin center. To do this:

1. **SharePoint Online 管理センター**に移動して、**[ユーザー プロファイル]** タブをクリックします。
2. **[ユーザー プロパティの管理]** をクリックして、プロパティのリストを確認します。
3. 任意のプロパティを右クリックして **[編集]** を選択し、各種の設定を調整します。
4. [**ポリシー設定**] の "replicable" プロパティでは、プロパティが [ユーザー情報] リストに表示されるかどうかを制御します。 すべてのプロパティがこの調整をサポートしているわけではありません。

An admin can export all User information properties for a user on a given site by using the **Export-SPOUserInfo** cmdlet in SharePoint Online PowerShell. See [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>OneDrive for Business エクスペリエンスの設定

A user's OneDrive for Business experience stores information to help the user find and navigate content of interest to them. Most of this information can be accessed by end users using in-product features. An admin can export the information using a [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands.

設定の詳細、設定の保存方法、設定のエクスポート方法については、「[OneDrive for Business エクスペリエンス設定のエクスポート](https://docs.microsoft.com/sharepoint/export-odfb-lists)」を参照してください。

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>OneDrive for Business および SharePoint Online の検索

The in-app search experience in OneDrive for Business and SharePoint Online stores a user's search queries for 30 days to increase relevance of search results. An admin can export search queries for a user by using the **Export-SPOQueryLogs** cmdlet in SharePoint Online PowerShell. See [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams for Education

Microsoft Teams for Education offers two additional collaboration features that teachers and students can use that creates and stores personal data: Assignments and OneNote Class Notebook. You can use Content Search to discover data in both.

##### <a name="assignments"></a>Assignments

Students files associated with an Assignment are stored in a document library in the corresponding Teams SharePoint Online site. IT admins can use the Content Search tool to search for student files that are related to assignments. For example, an admin could search all SharePoint Online sites in the organization and use the student's name and class or assignment name in the search query to find data relevant to a DSR.

There's other data related to Assignments that isn't stored in the class team SharePoint Online site, which means it's not discoverable with Content Search. This includes:

- 教師が課題の一部として生徒に割り当てたファイル
- 学生の成績と教師からのフィードバック
- 各学生が課題用に提出したドキュメントのリスト
- 課題のメタデータ

この種のデータの場合、IT 管理者またはデータ所有者 (教師など) が、クラス チームの [課題] に移動して DSR に関連するデータを検索することが必要になる場合があります。

##### <a name="onenote-class-notebook"></a>OneNote Class Notebook

The OneNote Class Notebook is stored in the class team SharePoint Online site. Every student in a class has a private notebook that's shared with the teacher. There's also a content library where a teacher can share documents with students, and a collaboration space for all students in the class. Data related to these capabilities is discoverable with Content Search.

ここでは、Class Notebook の検索に固有のガイダンスを示します。

1. 次の検索条件を使用して、コンテンツ検索を実行します。

   - すべての SharePoint Online サイトを検索する

   - 検索キーワードとしてクラス チームの名前を含める (例: "9C Biology")

2. 検索結果をプレビューして、Class Notebook に対応するアイテムを見つけます。
3. Select that item, and then copy the folder path that's displayed in the details pane. This is the root folder for the Class Notebook.
4. Edit the search that you created in step 1 and replace the class name in the keyword query with the folder path of the Class Notebook and precede the folder path with the **path** site property; for example, **path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/"**. Be sure to include the quotation marks and the trailing forward slash.
5. 検索条件を追加し、[ファイルの種類] 条件を選択して、ファイルの種類の値として使用します。 これにより、すべての OneNote ファイルが検索結果で返されます。 その結果としてのキーワードの構文は、次のようになります。[](#building-search-queries-to-find-personal-data)

    ```Query
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  コンテンツ検索を再実行します。 検索結果には、クラス チームの Class Notebook のすべての OneNote ファイルが含まれるようになります。

#### <a name="microsoft-to-do"></a>Microsoft To Do

Microsoft To Do のタスク (別名 *To Do*、*やるべきことリスト*に保存) は、ユーザーの Exchange Online メールボックスにタスクとして保存されます。 つまり、コンテンツ検索ツールを使用して、To Do を検索、アクセス、削除、およびエクスポートできます。 詳細については「[Microsoft To Do のセットアップ](https://support.microsoft.com/ja-JP/office/set-up-microsoft-to-do-490c1a8c-2333-4952-8125-841afadb9620)」を参照してください。

#### <a name="skype-for-business"></a>Skype for Business

ここでは、Skype for Business の個人データへのアクセス方法、表示方法、およびエクスポート方法に関する追加情報を示します。

- Files attached to a meeting are retained in the actual meeting for 180 days and then become inaccessible. These files can be accessed by meeting participants by joining the meeting from the meeting request and then viewing or downloading the attached file. See the "Use the attachments in the meeting" section in [Preload attachments for a Skype for Business meeting](https://support.microsoft.com/ja-JP/office/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).
- Conversations in Skype for Business are retained in the Conversation History folder in user mailboxes. You can use Content Search to search mailboxes for data in Skype conversations.
- A data subject can export their contacts in Skype for Business. To do this, they would right-click a contact group in Skype for Business and click **Copy**. Then they can paste the list of email addresses into a text or Word document.
- If the Exchange Online mailbox of a meeting participant is placed on Litigation Hold or assigned to an Office 365 retention policy, files attached to a meeting are retained in the participants mailbox. You can use Content Search to search for those files in the participant's mailbox if the retention period for the file has not expired. For more information about retaining files, see [Retaining large files attached to a Skype for Business meeting](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting).

## <a name="providing-a-copy-of-personal-data"></a>個人データのコピーを提供する

After you've found personal data that is potentially responsive to a DSR, it's up to you and your organization to decide which data to provide the data subject. For example, you can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions that you've deemed appropriate to share. For each of these responses to an access request, you'll have to retrieve a copy of the document or other item that contains the responsive data.

データ主体にコピーを提供する際には、別のデータ主体に関する個人情報などの機密情報を削除または編集することが必要になる場合があります。

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>コンテンツ検索を使用して個人データのコピーを取得する

コンテンツ検索ツールを使用して、検索の実行後に見つかったドキュメントまたはメールボックス アイテムのコピーを取得する方法は 2 つあります。

- Preview the search results and then download a copy of the document or item. This is a good way to download a few items or files.
- 検索結果をエクスポートして、検索で返されたすべてのアイテムのコピーをダウンロードする。 この方法は複雑になりますが、DSR に対応する多数のアイテムをダウンロードする場合に適しています。 また、検索結果のエクスポートには役立つレポートも含まれています。 こうしたレポートは、各アイテムに関する追加情報を取得するために使用できます。 **Results.csv** レポートは、エクスポートしたアイテムに関する多数の情報を含んでいるため役立ちます (たとえば、電子メール メッセージのメールボックスや、SharePoint Online および OneDrive for Business のサイトにあるドキュメントまたはリストの URL など)。 この情報は、DSR 調査プロセスでアイテムの所有者と連絡を取る必要がある場合、その所有者の特定に役立ちます。 検索結果のエクスポート時に含まれるレポートの詳細については、「[コンテンツ検索レポートのエクスポート](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report)」を参照してください。

#### <a name="preview-and-download-items"></a>アイテムのプレビューとダウンロード

新しい検索を実行した後または既存の検索を開いた後で、検索クエリと一致した各アイテムをプレビューして、調査中の DSR に関連しているかどうかを確認できます。 プレビューには、検索結果で返された SharePoint リストや Web ページも含まれます。 さらに、データ主体に元のファイルを提供する必要がある場合は、そのファイルをダウンロードすることもできます。 どちらの場合も、データ主体の要求に応えるスクリーンショットを作成して情報を取得できます。

一部の種類のアイテムはプレビューできません。 プレビューがサポートされていないアイテムまたはファイルの種類の場合は、個別のアイテムをローカル コンピューターやマップ済みのネットワーク ドライブなどのネットワークの場所にダウンロードするという方法があります。 プレビューを行えるのは、[サポート対象のファイルの種類](https://docs.microsoft.com/microsoft-365/compliance/content-search)のみです。

アイテムをプレビューしてダウンロードするには:

1. セキュリティ/コンプライアンス センターで、[コンテンツ検索] を開きます。
2. 結果が表示されていない場合は、**[結果のプレビュー]** をクリックします。
3. アイテムをクリックして表示します。
4. Click **Download original file** to download the item to your local computer. You'll also have to download items that can't be previewed.

検索結果のプレビューの詳細については、「[検索結果のプレビュー](https://docs.microsoft.com/microsoft-365/compliance/content-search)」を参照してください。

#### <a name="export-and-download-items"></a>アイテムのエクスポートとダウンロード

You can also export the results of a content search to get a copy of email messages, documents, lists, and web pages containing the personal data, though this method is more involved than previewing items. See the next section for details about [exporting the results of a Content Search](#export-and-download-content-using-content-search).

## <a name="exporting-personal-data"></a>個人データのエクスポート

The "right of data portability" allows a data subject to request an electronic copy of personal data that's in a "structured, commonly used, machine-readable format", and to request that your organization transmit these electronic files to another data controller. Microsoft supports this right in two ways:

- ネイティブのコンピューターが読み取り可能な一般的に使用されている電子形式でデータを保存する Office 365 アプリケーションを提供しています。 Office ファイル形式の詳細については、「[Office ファイル形式 - テクニカル ドキュメント](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx)」を参照してください。
- ネイティブのファイル形式、または別のアプリケーションに簡単にインポートできる形式 (CSV、TXT、JSON など) で組織がデータをエクスポートできるようにしています。

DSR エクスポート要求を満たすために、ネイティブのファイル形式で Office ドキュメントをエクスポートすることと、別の Office 365 アプリケーションからデータをエクスポートすることができます。

### <a name="export-and-download-content-using-content-search"></a>コンテンツ検索を使用したコンテンツのエクスポートとダウンロード

When you export the results of a Content Search, email items can be downloaded as PST files or as individual messages (.msg files). When you export documents and lists from SharePoint Online and OneDrive for Business sites, copies in the native file formats are exported. For example, SharePoint lists are exported as CSV files and Web pages are exported as .aspx or html files.

>[!NOTE]
>コンテンツ検索を使用してユーザーのメールボックスからメールボックス アイテムをエクスポートするには、ユーザー (アイテムのエクスポート元メールボックスの所有者) に、Exchange Online プラン 2 ライセンスが割り当てられている必要があります。 

アイテムをエクスポートおよびダウンロードするには:

1. セキュリティ/コンプライアンス センターで、[コンテンツ検索] を開きます。
2. [検索] ポップアップ ページで [![ダウンロード アイコン](../media/o365-dsr_image21.png)] [**詳細**] をクリックし、 [**結果のエクスポート**] をクリックします。 レポートをエクスポートすることもできます。
3. Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.
4. セキュリティ/コンプライアンス センターのコンテンツ検索ページに戻って、**[エクスポート]** タブをクリックします。
5. **[最新の情報に更新]** をクリックして、ページを更新します。
6. [**名前**] 列で、作成したエクスポート ジョブをクリックします。 エクスポート ジョブの名前は、コンテンツ検索の名前に "**\_Export**" が付加されたものになります。
7. [エクスポート] ポップアップ ページの [**エクスポート キー**] で、[**クリップボードにコピー**] をクリックします。 このキーは手順 10 で検索結果をダウンロードするときに使用します
8. ポップアップ ページの上部で、[![ダウンロード アイコン](../media/o365-dsr_image21.png)] [**結果のダウンロード**] をクリックします。
9. **Microsoft Office 365 電子情報開示エクスポート ツール**をインストールするように求めるダイアログが表示されたら、**[インストール]** をクリックします。
10. **電子情報開示エクスポート ツール**で、手順 7 でコピーしたエクスポート キーを該当するボックスに貼り付けます。
11. **[参照]** をクリックして、検索結果のファイルをダウンロードする場所を指定します。
12. **[開始]** をクリックして、検索結果をコンピューターにダウンロードします。

When the export process is complete, you can access the files in the location on your local computer where they were downloaded. Results of a content search are downloaded to a folder named after the Content Search. Documents from sites are copied to a subfolder named **SharePoint**. Mailbox items are copied to subfolder named **Exchange**.

手順ごとの詳細な説明については、「[セキュリティ/コンプライアンス センターの検索結果をエクスポートする](export-search-results.md)」を参照してください。

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online および OneDrive for Business からドキュメントとリストをダウンロードする

Another way to export data from SharePoint Online and OneDrive for Business is to download documents and lists directly from a SharePoint Online site or a OneDrive for Business account. You would have to get assigned the permissions to access a site, and then go to the site and download the contents. See:

- [OneDrive や SharePoint からファイルとフォルダーをダウンロードする](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [SharePoint リストを Excel にエクスポートする](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

For some DSR export requests, you may want to allow the data subject to download content themselves. This enables the data subject to go to a SharePoint Online site or shared folder and click **Sync** to sync all contents in the document library or selected folders. See:

- [次世代の OneDrive 同期クライアントを使用して SharePoint ファイルを同期する](https://docs.microsoft.com/sharepoint/let-users-use-new-onedrive-sync-client)
- [次世代の OneDrive 同期クライアントを使用して SharePoint ファイルを同期する](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>個人データの削除

組織のサポート データからの個人データの削除による「削除する権利」は GDPR における主要な保護の 1 つです。 個人データの削除には、ドキュメントやファイル全体の削除、またはドキュメント内やファイル内の特定のデータの削除 (操作と手順は、このガイドの「修正」セクションで説明したものと同様です) が含まれます。

DSR に対応する個人データの削除の調査または準備を実行する際には、いくつかの重要な事項を理解しておく必要があります。ここでは、Office 365 でのデータの削除 (および保持) がどのように動作するかについて説明します。

- **論理的な削除と物理的な削除:** Office 365 のサービス (Exchange Online、SharePoint Online、OneDrive for Business など) では、*論理的な削除*と*物理的な削除*という概念があります。これらの概念は、削除済みアイテムの回復性 (通常は期限付き) に関係しています。Microsoft のクラウドから完全に削除されると回復の可能性がなくなります。 このコンテキストでは、論理的に削除されたアイテムは、物理的に削除されるまでの一定期間、ユーザーや管理者が回復できます。 アイテムが物理的に削除されると、完全な削除のマークが付けられ、対応する Office 365 サービスによる処理が行われると消去されます。 次に、メールボックス内およびサイト内のアイテムに対して論理的な削除と物理的な削除がどのように作用するかについて説明します (データ所有者と管理者のどちらがアイテムを削除したかは関係ありません)。

    - **メールボックス:** アイテムが [削除済みアイテム] フォルダーから削除されたとき、またはユーザーが **Shift + Delete** キーを押してアイテムを削除したときに、アイテムは論理的に削除されます。 アイテムが論理的に削除されると、そのアイテムはメールボックス内の [回復可能なアイテム] フォルダーに移動されます。 この段階では、削除されたアイテムの保持期間が経過するまで、ユーザーによるアイテムの回復が可能です (Office 365 の場合、削除されたアイテムの保持期間は 14 日間ですが、管理者が 30 日間にまで延長できます)。 保持期間が経過すると、アイテムは物理的に削除され、非表示フォルダー (*[Purges]* フォルダー) に移動されます。 このアイテムは、次回のメールボックスの処理時に Office 365 から完全に削除 (消去) されます (メールボックスは 7 日ごとに処理されます)。

    - **SharePoint Online サイトと OneDrive for Business サイト**: ファイルやドキュメントは削除時に、サイトのごみ箱に移動されます (*第 1 段階のごみ箱*とも呼ばれ、Windows のごみ箱と同様のものです)。 このアイテムは、ごみ箱内に 93 日間 (Office 365 のサイトに対する削除済みアイテムの保持期間) 維持されます。 その期間が経過すると、アイテムは自動的にサイト コレクションのごみ箱 (*第 2 段階のごみ箱*とも呼ばれます) に移動されます (適切なアクセス許可を持つユーザーや管理者は、第 1 段階のごみ箱からアイテムを削除することもできます)。 この段階で、アイテムは論理的に削除されます。このアイテムは、サイト コレクション管理者 (SharePoint Online の場合) またはユーザーや管理者 (OneDrive for Business の場合) が回復できます。 アイテムが第 2 段階のごみ箱から削除されると (手動または自動による削除)、そのアイテムは物理的に削除されたことになり、ユーザーや IT 管理者はアクセスできなくなります。第 1 段階のごみ箱と第 2 段階のごみ箱ともに、保持期間は 93 日間です。これは、第 2 段階のごみ箱の保持はアイテムが最初に削除されたときに開始されることを意味します。 このため、両方のごみ箱で合計の最大保持期間が 93 日になるということです。

>[!NOTE]
>論理的または物理的にアイテムが削除される処理を理解することは、削除要求に対応するときに GDPR 要件を満たすようにデータを削除する方法の判断に役立ちます。

- **訴訟ホールドと保持ポリシー:** Office 365 では、メールボックスとサイトに対して「ホールド」を実施できます。 簡単に言うと、メールボックスやサイトがホールド状態の場合は、アイテムの保持期間が経過するかホールドが削除されるまで、一切のものが完全に削除 (物理的に削除) されなくなることを意味します。 これは、DSR への対応で顧客コンテンツを削除するというコンテキストで重要な点です。ホールド状態のコンテンツの場所からアイテムが物理的に削除されても、そのアイテムが Office 365 から完全に削除されることはありません。 つまり、IT 管理者によって回復される可能性があることを意味します。DSR への対応で Office 365 のデータを完全に削除して回復不可能にするという要件またはポリシーが組織にある場合は、メールボックスまたはサイトからホールドを削除して、Office 365 のデータを完全に削除する必要があります。 ほとんどの場合、組織が DSR に対応する際のガイドラインには、特定の DSR 削除要求と訴訟ホールドのどちらが優先されるかを判断するためのプロセスがあります。 アイテムの削除のためにホールドを削除した場合、そのホールドはアイテムの削除後に再実施できます。

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online および OneDrive for Business のドキュメントを削除する

SharePoint Online サイトまたは OneDrive for Business アカウントにある削除対象のドキュメントを見つけたら (このガイドの「検出」セクションにあるガイダンスを参照)、データ プライバシー責任者または IT 管理者は、サイトにアクセスしてドキュメントを削除するために必要なアクセス許可を割り当てる必要があります。 また、必要に応じて、ドキュメントの所有者にドキュメントを削除するように指示することもできます。

ここでは、サイトからドキュメントを削除する際の手順の概要を示します。

1. サイトに移動して、ドキュメントを検索します。
2. Delete the document. When you delete a document from a site, it's sent to the first-stage Recycle Bin.
3. Go to the first-stage Recycle Bin (the site Recycle Bin) and delete the same document you deleted in the previous step. The document is sent to the second-stage Recycle Bin. **At this point, the document is soft-deleted**.
4. Go to the second-stage Recycle Bin (which is the site collection Recycle Bin) and delete the same document that you deleted from the first-stage Recycle Bin. **At this point, the document is hard-deleted.**

>[!IMPORTANT]
>You can't delete a document that is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a DSR delete request takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted.

詳細な手順については、次のトピックを参照してください。

- [SharePoint ドキュメント ライブラリからファイル、フォルダー、またはリンクを削除する](https://support.microsoft.com/ja-JP/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)
- [SharePoint サイトのごみ箱のアイテムを削除または空にする](https://support.microsoft.com/ja-JP/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e)
- [サイト コレクションのごみ箱からアイテムを削除する](https://support.microsoft.com/ja-JP/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653)
- [元のユーザーのデータにアクセスしてバックアップを作成する](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data) (「元従業員の OneDrive for Business ドキュメントにアクセスしてバックアップを作成する」のセクション)
- [OneDrive for Business のファイルまたはフォルダーを削除する](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [SharePoint のリストを削除する](https://support.microsoft.com/ja-JP/office/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d)
- [SharePoint Online のリスト アイテムを削除する](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>SharePoint サイトの削除

You may determine that the best way to respond to a DSR delete request is to delete an entire SharePoint site, which will delete all that data located in the site. You can do this by running cmdlets in SharePoint Online PowerShell.

- [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) コマンドレットは、サイトを削除して SharePoint Online のごみ箱に移動 (論理的に削除) する場合に使用します。
- [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) コマンドレットは、サイトを完全に削除 (物理的に削除) する場合に使用します。

電子情報開示ホールドが実施されているサイトや保持ポリシーが割り当てられているサイトは削除できません。 サイトでの電子情報開示ホールドの適用を解除するか保持ポリシーを削除してからでないと、そのサイトのは削除できません。

### <a name="deleting-a-onedrive-for-business-site"></a>OneDrive for Business サイトの削除

Similarly, you may determine to delete a user's OneDrive for Business site in response to a DSR deletion request. If you delete the user's Office 365 account, their OneDrive for Business site is retained (and restorable) for 30 days. After 30 days, it's moved to the SharePoint Online Recycle Bin (soft-deleted), and then after 93 days, it's permanently deleted (hard-deleted). To accelerate this process, you can use the [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) cmdlet to move the OneDrive for Business site to the Recycle Bin and then use the [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) cmdlet to permanently delete it. As with sites in SharePoint Online, you can't delete a user's OneDrive for Business site if it was assigned to an eDiscovery hold or a retention policy before the user's account was deleted.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>OneDrive for Business および SharePoint Online エクスペリエンスの設定の削除

ビジネス アカウントと SharePoint Online サイトの OneDrive for Business に保存されているユーザーが作成したファイルに加えて、これらのサービスは、さまざまなエクスペリエンスを有効にするために使用するユーザーに関する情報を保存します。 これらは、以前このドキュメントで文書化されています。 OneDrive for Business および SharePoint Online のアプリケーション データへのアクセス、表示、エクスポートの方法に関する情報については、[コンテンツ検索の電子情報開示ツールを使用して DSRに対応する](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) の下にある、[選択したアプリケーションの追加の考慮事項](#additional-considerations-for-selected-applications) セクションを参照してください。

#### <a name="deleting-a-sharepoint-user-profile"></a>SharePoint ユーザー プロファイルの削除

The SharePoint user profile will be permanently deleted 30 days after the user account is deleted in Azure Active Directory. However, you can hard-delete the user account, which will remove the SharePoint user profile. For more information, see the [Deleting a user section in this guide](#deleting-a-user).

An admin can expedite the deletion of the User Profile for a user by using the **Remove-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). This requires the user to be at least soft-deleted in Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>SharePoint Online サイトのユーザー情報リストの削除

For users that have left the organization, this data remains in the sites they interacted with for referential integrity of SharePoint column fields. An admin can delete all User information properties for a user on a given site by using the **Remove-SPOUserInfo** command in SharePoint Online PowerShell. See [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) for information about running this PowerShell cmdlet.

既定では、このコマンドはユーザーの表示名や削除されたプロパティ (電話番号、電子メール アドレス、技能と専門知識、その他の SharePoint Online ユーザー プロファイルからコピーされたプロパティ) を保持します。 管理者は **RedactUser** パラメーターを使用して、[ユーザー情報] リスト内のユーザーに代替の表示名を指定できます。 これは、ユーザー エクスペリエンスの複数のパーツに影響し、サイト内のファイルの履歴を調べるときに情報が損失します。

Finally, the redaction capability will not remove all metadata or content referencing a user from documents. The way to achieve redaction of file content and metadata is described in the [Making changes to content in OneDrive for Business and SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) section in this guide. This method consists of downloading, deleting, and then uploading a redacted copy of the file.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>OneDrive for Business エクスペリエンスの設定の削除

The recommended way to delete all OneDrive for Business experience settings and information is to remove the user's OneDrive for Business site, after reassigning any retained files to other users. An admin can delete these lists using [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands. See [Deleting OneDrive for Business experience settings](https://docs.microsoft.com/sharepoint/delete-odfb-lists) for more information about the settings, how they are stored, and how to delete them.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>OneDrive for Business および SharePoint Online の検索クエリ

OneDrive for Business および SharePoint Online の検索エクスペリエンスで作成したユーザーの検索クエリは、ユーザーがクエリを作成してから 30 日経過後に自動的に削除されます。

### <a name="deleting-items-in-exchange-online-mailboxes"></a>Exchange Online メールボックス内のアイテムの削除

DSR 削除要求に応えるために、Exchange Online メールボックス内のアイテムの削除が必要になることがあります。 IT 管理者がメールボックス内のアイテムを削除する方法には 2 つあり、対象のアイテムを論理的に削除するか物理的に削除するかによって異なります。 SharePoint Online または OneDrive for Business のサイトにあるドキュメントと同様に、ホールド状態のメールボックス内のアイテムを Office 365 から完全に削除することはできません。 アイテムを削除する前に、ホールドを削除する必要があります。 前述したように、メールボックスのホールドと DSR 削除要求のどちらが優先されるかを判断する必要があります。

#### <a name="soft-delete-mailbox-items"></a>メールボックス アイテムの論理的な削除

コンテンツ検索の処理機能を使用すると、コンテンツ検索で返されたアイテムの論理的な削除を実行できます。 前述したように、論理的に削除されたアイテムは、メールボックス内の [回復可能なアイテム] フォルダーに移動されます。

ここでは、このプロセスの簡単な概要を示します。

1. ユーザーのメールボックスから削除するアイテムを検索するには、コンテンツ検索を作成して実行します。 削除するアイテムのみを検索結果で取得するには、検索を再実行して検索結果を絞り込む必要がある場合があります。
2. Office 365 PowerShell で **New-ComplianceSearchAction** **-Purge** コマンドを使用して、前の手順で作成したコンテンツ検索によって返されたアイテムを論理的に削除します。

詳細な手順については、「[組織でのメール メッセージの検索と削除](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)」を参照してください。

#### <a name="hard-delete-mailbox-items"></a>メールボックス アイテムの物理的な削除

If you have to hard-delete mailbox items in response to the DSR deletion request, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. If you use this method, consider using Content Search to develop and refine a search query so that only the items that are to be deleted are returned in the search. Then you can use that query syntax when you run the **Search-Mailbox -DeleteContent** command.

詳細な手順については、「[メッセージを検索して削除する](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx)」を参照してください。

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>ホールド状態のメールボックス アイテムの物理的な削除

As previously explained, if you hard-delete items in a mailbox on hold, items are not removed from the mailbox. They are moved to a hidden folder in the Recoverable Items folder (the **Purges** folder) and will remain there until the hold duration for the item expires or until the hold is removed from the mailbox. If either of those things happen, the items will be purged from Office 365 the next time that the mailbox is processed.

Your organization might determine that items being permanently deleted when the hold duration expires meets the requirements for a DSR deletion request. However, if you determine that mailbox items must be immediately purged from Office 365, you would have to remove the hold from the mailbox and then hard-deleted the items from the mailbox. For detailed instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](https://docs.microsoft.com/microsoft-365/compliance/delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold).

>[!NOTE]
>DSR 削除要求に応えるために、前のトピックの手順に従ってメールボックス アイテムを物理的に削除する場合は、メールボックスがホールド状態にある間に該当するアイテムを論理的に削除して、そのアイテムを回復可能なアイテム フォルダーに移動しておく必要があります。

## <a name="deleting-a-user"></a>ユーザーの削除

In addition to deleting personal data in response to a DSR deletion request, a data subject's "right to be forgotten" may also be fulfilled by deleting their user account. Here are some reasons that you might want to delete a user:

- データ主体が組織から退職した (または退職手続き中である)。
- The data subject has requested that you delete system-generated logs that have been collected about them. Examples of data in system-generated logs include Office 365 app and service usage data, information about search requests performed by the data subject, and data generated by product and services as a product of system functionality and interaction by users or other systems. For more information, see [Part 3: Responding to DSRs for system-generated Logs](#part-3-responding-to-dsrs-for-system-generated-logs) in this guide.
- データ主体による Office 365 のデータのアクセスや処理を完全に防止する (セクション「[DSR 制限要求への対応](#responding-to-dsr-restriction-requests)」で説明する方法による一時的なアクセスを制限とは対照的)。

ユーザー アカウントを削除すると、次のようになります。

- ユーザーは Office 365 にサインインできなくなるか、組織の Microsoft リソース (OneDrive for Business アカウント、SharePoint Online サイト、Exchange Online メールボックスなど) のいずれにもアクセスできなくなります。
- ユーザー アカウントに関連付けられた個人データ (電子メール アドレス、エイリアス、電話番号、郵送先住所など) が削除されます
- 一部の Office 365 アプリでは、ユーザーに関する情報が削除されます。 たとえば、Microsoft Flow では、削除されたユーザーは共有フローの所有者の一覧から削除されます。
- データ主体に関するシステム生成ログは、サービスのセキュリティや安定性を損なう可能性のあるデータを除き、ユーザー アカウントが削除されてから 30 日後に削除されます。 詳細については、「[システム生成ログの削除](#deleting-system-generated-logs)」セクションを参照してください。

>[!IMPORTANT]
>After you delete a user account, that person will lose the ability to sign in to Office 365 and the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. That person would also be unable to initiate any DSR requests through Microsoft directly in instances where Microsoft is the data controller. For more information, see the [Product and services authenticated with an Org ID for which Microsoft is a data controller](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller) section in Part 4 of this guide.

>[!NOTE]
>In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, you can [submit a request](https://go.microsoft.com/fwlink/?linkid=874544). In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.

個人データの削除に関する前述のセクションでは、データの論理的な削除と物理的な削除について説明しましたが、ユーザー アカウントを削除する場合にも、論理的な削除と物理的な削除の状態が存在します。

- (管理センターまたは Azure portal でユーザーを削除することにより) ユーザー アカウントが最初に削除されたときは、そのユーザー アカウントは論理的に削除され、Azure のごみ箱に 30 日間移動されます。 この時点では、ユーザー アカウントの復元が可能です。
- If you permanently deleted the user account, the user account is hard-deleted and removed from the Recycle Bin in Azure. At this point, the user account can't be restored, and any data associated with the user account will be permanently removed from the Microsoft cloud. Hard-deleting an account deletes system-generated logs about the data subject, except for data that may compromise the security or stability of the service.

ここでは、組織からユーザーを削除する場合の手順の概要を示します。

1. 管理センターまたは Azure portal に移動して、ユーザーを見つけます。

2. Delete the user. When you initially delete the user, the user's account is sent to the Recycle Bin. At this point, the user is soft-deleted. The account is retained in the soft-deleted for 30 days, which allows you to restore the account. After 30 days, the account is automatically hard-deleted. For specific instructions, see [Delete users from Azure AD](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<br><br> ユーザーア カウントは管理センターでも削除できます。 詳細については、「[組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

3. ユーザー アカウントが物理的に削除されるまで 30 日間待機できない場合は、手動による物理的な削除が可能です。 この操作を Azure portal で実行する場合は、最近削除されたユーザーのリストに移動して、そのユーザーを完全に削除します。 ユーザーはこの時点で物理的に削除されます。 手順については、「[最近削除されたユーザーを完全に削除する方法](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore)」を参照してください。

Office 365 管理ポータルでは、ユーザーの物理的な削除は実行できません。

>[!NOTE]
>In Office 365 operated by 21Vianet (China), you can't permanently delete a user as previously described. To permanently delete a user, you can submit a request via the Office 365 admin portal at this [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Go to **Commerce** and then select **Subscription** -> **Privacy** ->  **GDPR** and enter the required information.

### <a name="removing-exchange-online-data"></a>Exchange Online データの削除

ユーザーを削除する際には、ユーザーの Exchange Online メールボックスで何が起こるかについて理解しておく必要があります。 ユーザー アカウントの物理的な削除後に (前述の手順 3 の段階で)、削除されたユーザーのメールボックスが Office 365 から自動的に消去されるわけではありません。 ユーザー アカウントの物理的な削除後、メールボックスが Office 365 から完全に削除されるまでに最大 60 日かかります。 ユーザー アカウント削除後のメールボックスのライフサイクルおよびその間のメールボックス データの状態について以下に説明します。

- **1 日から 30 日** — 倫理削除されたユーザー アカウントを復元することで、メールボックスを完全に回復できます。
- **31 日から 60 日** — ユーザー アカウントが物理削除されてから 30 日間は、組織の管理者がメールボックス内のデータを回復し、そのデータを別のメールボックスにインポートできます。 これにより組織は、メールボックス データを必要に応じて回復できるようになります。
- **61 日から 90 日**-管理者は、メールボックス内のデータを回復できません。 メールボックス データには永久削除のマークが付けられますが、Office 365 からメールボックス データが消去されるまでにはさらに最大で 30 日かかります。

このメールボックスのライフサイクルが、DSR の削除要求に対応するための組織の要件を満たしていないと判断した場合は、ユーザー アカウントの物理的な削除*後*に [Microsoft サポート に問い合わせ](https://support.microsoft.com/)、メールボックス データを完全に削除するためのプロセスを手動で開始するように要求してください。 メールボックス データを完全に削除するためのこのプロセスはライフサイクルが 61 日経過すると自動的に開始されるため、ライフサイクルのこの時点以降では、Microsoft に連絡する必要はありません。

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>アプリ内機能を使用した DSR への対応

While most Customer Data is authored and produced using the applications described in the previous section, Office 365 also offers many other applications that customers can use to produce and store Customer Data. However, Content Search doesn't currently have the ability to find data authored in these other Office 365 applications. To find data generated by these applications, you or the data owner must use in-product functionality or features to find data that may be relevant to a DSR. The following table lists these Office 365 applications. Click the application icon to go the section in this guide that describes how to respond to DSR requests for data authored in the application.

***表 3: 顧客データの検索にアプリ内の機能を使用できるアプリケーション***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Access アイコン](../media/o365-access-64x64.png) <br> [Access](#access) | ![Office アイコン](../media/O365-DSR-Doc_image22.png) <br> [Office 365<br> のビジネス アプリ](#business-apps-for-office-365) | ![Office アイコン](../media/O365-DSR-Doc_image22.png) <br> [Education](#education)|
| ![Flow アイコン](../media/o365-flow-64x64.png) <br> [Flow](#flow) | ![Forms アイコン](../media/o365-forms-64x64.png) <br> [Forms](#forms) |![Kaizala アイコン](../media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Planner アイコン](../media/o365-planner-64x64.png) <br> [Planner](#planner) |![PowerApps アイコン](../media/o365-powerapps-64x64.png) <br> [Power Apps](#powerapps) |![Power BI アイコン](../media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Project アイコン](../media/o365-project-64x64.png) <br> [Project](#project-online) |![Publisher アイコン](../media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Stream アイコン](../media/o365-stream-64x64.png) <br> [Stream](#stream) |![Sway アイコン](../media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Whiteboard アイコン](../media/O365-DSR-Doc_image36.png) <br> [Whiteboard](#whiteboard) |
|![Yammer アイコン](../media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

次の各セクションでは、Microsoft Access のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

##### <a name="discover"></a>検索

There are several ways that you can search for records in an Access database that might be responsive to a DSR request. For a DSR investigation, you can search for records that related to the data subject or search for records that contain specific data. For example, you could either search or go to a record that corresponds to the data subject. Or you can search for records that contain specific data, such as personal data about the data subject. For more information, see:

- [Access データベース内でレコードを検索する](https://support.microsoft.com/ja-JP/office/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [単純な選択クエリを作成する](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Access

After you find the records or fields that are relevant to the DSR request, you can take a screenshot of the data or export it to an Excel file, Word file, or a text file. You can also create and print a report based on a record source, or a select query that you created to find the data. See:

- [Access のレポートの概要](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [Excel にデータをエクスポートする](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [Word 文書にデータをエクスポートする](https://support.microsoft.com/ja-JP/office/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [テキスト ファイルにデータをエクスポートする](https://support.microsoft.com/ja-JP/office/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>エクスポート

前述のとおり、Access データベースからデータはさまざまなファイル形式でエクスポートできます。 選択するエクスポート ファイル形式は、データ主体からの特定の DSR エクスポート要求に基づいて決定されることがあります。 Access データを異なるファイル形式でエクスポートする方法を説明するトピックの一覧については、「[インポートおよびエクスポート](https://support.microsoft.com/ja-JP/office/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f)」を参照してください。

##### <a name="delete"></a>削除

レコード全体または 1 つのフィールドだけを Access データベースから削除できます。 Access データベースからレコードを削除する最も簡単な方法は、データシート ビューでテーブルを開き、削除するレコード (行) またはフィールドのデータだけを選択して、[削除] をクリックする方法です。 また、データ検索用に作成した選択クエリを、削除クエリに変換することもできます。 以下の情報を参照してください。

- [データベースから 1 つまたは複数のレコードを削除する](https://support.office.com/article/ways-to-add-edit-and-delete-records-5e90a80c-106d-4c55-996e-07d7200980ce)
- [削除クエリ作成し、実行する](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>Office 365 のビジネス アプリ

このセクションでは、次の Office 365 の各ビジネス アプリでアプリ内機能を使用して DSR 要求に対応する方法を説明します。

- [Bookings](#bookings)
- [Listings](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings

次の各セクションでは、Microsoft Bookings のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。 この説明は、スタンドアロンの Bookings アプリと、ビジネス センターからアクセスする Bookings の両方に適用されます。

Microsoft Bookings allows administrators and users or staff, with a Bookings license in their organization, to set up booking pages so customers can schedule and make changes to appointments, receive confirmation emails, updates, cancellation, and reminders email. Business owners and their staff can also book events on behalf of their customers with Bookings. 

顧客、管理者、またはスタッフが作成するデータの種類を以下に示します。

- **顧客、パートナー、または友人の連絡先情報** - このデータには、名前、電話番号、メール アドレス、住所、メモが含まれます。

    - Web、iOS、および Android の Bookings クライアントを使用して、すべてのユーザーの連絡先を手動で作成できます。
    
    - C1 のモバイル デバイスから iOS または Android の Bookings クライアントを使用して、すべてのユーザーの連絡先を Bookings にインポートできます。
    
    - 顧客に代わってユーザーが予約を作成するか、または顧客がオーナーの予約ページから予約を作成するかどうかにか関わらず、予約ワークフローで予約を作成する時点で、予約するユーザーの連絡先も自動的に作成されます。

- **Bookings イベント** - これらは、事業主や事業主が指定したスタッフと顧客との間の会議で、事業主または顧客が、事業主の公開予約ページを使用して作成します。 このデータには、名前、住所、メール アドレス、電話番号、および事業主が予約時にユーザーから収集した情報が含まれています。

- **メールの確認 / 取り消し / 更新** - これらは、特定の予約イベントに関して、システムが作成、送信するメール メッセージです。 これらのメッセーには、関連サービスを提供するスタッフの個人情報が含まれます。また事業主や顧客が予約時に入力した顧客の個人情報も含まれます。

顧客コンテンツはすべて、組織の Bookings をホストする Exchange Online メールボックスに保存されます。 このコンテンツは、ビジネス オーナーまたは顧客がサービス内でアクティブである間は常に保存されます。ただし、事業主または顧客がデータの削除を明示的に依頼する場合、またはサービスの利用を終了する場合を除きます。 このコンテンツを削除するには、製品内 UI またはコマンドレットを使用するか、該当する予約メールボックスを削除します。 削除アクションが開始されると、事業主が設定した期間内にデータが削除されます。 

顧客がサービスの利用を終了することにした場合、顧客コンテンツは 90 日後に削除されます。 ユーザー アカウントの削除後にメールボックスの内容が削除されるタイミングについての詳細は、「[Exchange Online データの削除](#removing-exchange-online-data)」を参照してください。

#### <a name="end-user-identifiable-information"></a>エンドユーザーを特定できる情報

End user Identifiable Information (EUII) includes personal and contact information about the staff that gets scheduled in Bookings. It's added to the Staff details pages when the business owner sets up Bookings and makes updates after the setup. It contains staff member's name, initials, email address, and phone number. This data is stored in the Exchange Online mailbox that hosts Bookings.

This data is retained for as long as the staff member is active in the service unless it's explicitly deleted the business owner or an admin using the in-app UI or by deleting the relevant booking mailbox. When the admin initiates the deletion of staff's details, or if the staff member leaves the service, their details are deleted in accordance with the Exchange Online mailbox's content retention policies set by the business owner or admin.

##### <a name="discoveraccess"></a>検出/アクセス

Bookings では、次の種類のデータが収集および保存されます。

- **ビジネス プロファイル情報:** Bookings を使用するビジネスに関する顧客コンテンツは、Bookings のビジネス情報フォーム経由で収集され、顧客が Bookings とビジネス センターを併用している場合にはビジネス センター ビジネス プロファイルと同期されます。 このデータに関連付けられている唯一の EUII は、C1 のメールアドレスです。 このアドレスに、新しい予約通知と更新のメールが送信されます。
- **顧客の連絡先:** このコンテンツは、Bookings Web、iOS、Android のクライアントで手動で作成することも、モバイル デバイスからインポートすることもできます。 連絡先は、セルフ サービス予約ページを使用する場合にも自動的に作成されます。 これらには、EUII が含まれ、Bookings メールボックスに保存されます。
- **スタッフの詳細情報:** 顧客コンテンツには、Bookings Web、iOS、または Android クライアントから作成されたサービスを提供する資格を持つスタッフに関するデータが含まれます。 スタッフの詳細情報には、名前、メール アドレス、電話番号が含まれます。
- **予約イベント:** これらは、ビジネスが Web クライアントまたは Android/iOS アプリを使用して作成したか、もしくは公開されている予約ページ (または Facebook ページ) から顧客が作成した、顧客の会議および関連する顧客コンテンツです。 これらのイベントには、名前、住所、メール アドレス、電話番号、予約の詳細が含まれています。
- **会議出席依頼、メールの確認 / 取り消し / 更新 / リマインダー:** これらは、特定の予約イベントに関して、システムが送信するメール メッセージです。 これらには、スタッフのデーダ、および予約時に入力された顧客データが含まれます。

##### <a name="export"></a>エクスポート

To export data corresponding to the business owner, staff and customers, you can use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>削除

DSR 削除要求に対応して削除できる Bookings データを次に示します。

- **ビジネス プロファイル情報と連絡先:** Bookings メールボックスは管理センターで削除できます。 削除したあと、30 日間はメールボックスを復元できます。 30 日後、ユーザー アカウントとメールボックスは完全に削除され、回復不可能になります。 ユーザー アカウントを削除する方法の詳細は、[ユーザーを削除する](#deleting-a-user)セクションを参照してください。
- **スタッフの詳細情報:** スタッフを Bookings ダッシュ ボードから削除できます。 スタッフを完全に削除するには、スタッフの Office 365 アカウントを削除します。
- **予約イベント:** Bookings カレンダーから予約イベントを削除できます。これにより、顧客の情報が削除されます。
- **会議出席依頼、メールの確認 / 取り消し / 更新 / リマインダー:** Bookings カレンダーからこれらの情報を削除できます。これにより、顧客の情報が削除されます。

Business owners and admins can also delete their customer's data by using the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

Additionally, you can delete business owner and staff data, you can delete the corresponding user account. See the section  [Deleting a user](#deleting-a-user).

#### <a name="listings"></a>Listings

次の各セクションでは、Microsoft Listings のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

##### <a name="discover"></a>検索

Listings オーナーは、各自のビジネスを Google、Bing、Yelp、および Facebook に接続して、評価とレビューを集計して確認できます。 Listings で収集および保存されるデータの種類を次に示します。

- Google のレビューと評価
- Bing のレビューと評価
- Yelp のレビューと評価
- Facebook のレビューと評価

##### <a name="access"></a>Access
Listings オーナーは、Listings ダッシュボードにサインインしてレビューと評価を確認できます。

##### <a name="export"></a>エクスポート

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>削除

If a Listings owner would like to delete their Listings information, they can disconnect from the provider on the Listings page. After they disconnect, their Listings information will be deleted.

#### <a name="connections"></a>接続

次の各セクションでは、Microsoft Connections のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

##### <a name="discover"></a>検索

Connections で収集および保存されるデータの種類を次に示します。 

- 顧客/連絡先は、Web クライアントまたはモバイル アプリ (iOS、Android) を使用してビジネスにより作成されるか、または取引先担当者にマーケティング キャンペーン メールを送信するときにアプリを使用して作成されます。 顧客データには、名前、住所、メール アドレス、税 ID 番号が含めることができます。 連絡先は、すべてのビジネス センター アプリで共有されます。
- 顧客は Connections の新規登録ページで登録し、各自の個人データを保存できます。
- キャンペーン メールからのリンク

##### <a name="access"></a>Access

Connections オーナーは、Connections ダッシュボードにサインインし、送信済みのキャンペーン メールを確認できます。

##### <a name="export"></a>エクスポート

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>削除

After a Connections owner sends an email campaign, they can't delete the campaign. If there are any draft campaigns they want to delete, they can sign in to the Connections dashboard and delete the draft campaigns.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

次の各セクションでは、Outlook Customer Manager のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

##### <a name="discover"></a>検索

Outlook Customer Manager は、Outlook Customer Manager のオーナーおよび顧客と取引先担当者の両方のユーザー情報を収集および保存します。

- Owner data. This includes name, address, and email address. Documents and files that an owner shares with a customer are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.
- Customer and business contact data. Customer data can include name, address, and email address. Customer and contact data is created by the business in Outlook or Outlook web app. Contacts are shared across Business center. Documents and files that a customer shares with a business are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.

また Outlook Customer Manager は、顧客に関するアクティビティとインサイトを Exchange に保存します。

##### <a name="access"></a>Access

Outlook Customer Manager オーナーは、Outlook または Outlook Web App にサインインし、Outlook Customer Manager ダッシュ ボードに移動して、顧客とのこれまでのやりとりを確認できます。

##### <a name="export"></a>エクスポート

To export business owner and customer data, use the Outlook Customer Manager privacy portal. For details. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>削除

To delete customer data, use the Outlook Customer Manager privacy portal. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

#### <a name="invoicing"></a>Invoicing

次の各セクションでは、Microsoft Invoicing のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

##### <a name="discover"></a>検索

Invoicing で収集および保存されるデータの種類を次に示します。

- **連絡先:** これらは、顧客 / 取引先に請求書または見積書が作成されるときに、ビジネスによって作成されます。 連絡先は、ビジネス センター間で共有されます。 顧客データには、名前、住所、メール アドレス、納税者番号が含まれます。
- **請求書:** 債務と課税額の両方が記載されており、作成されて顧客に送信されます。
- **見積書:** ビジネスは、お客様に見積書も送信できます。 見積もりが受理されると、請求書に変換されます。 見積もりは、顧客によって受理されたあと、請求書に変換されます。 見積書の記録は、請求書に変換されたあとは保存されません。

##### <a name="access"></a>Access

ユーザーは各自のビジネス センターの Invoicing ダッシュボードに移動して、作成した請求書の下書きや、顧客に送信された請求書を確認できます。

##### <a name="export"></a>エクスポート

To export customer invoicing data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>削除

After an invoice is created and sent, it can't be deleted due to accounting laws. The Invoicing owner can request that Microsoft delete some or all their information from Office 365.

Alternatively, you can delete the invoicing owner's user account in Office 365. See the section [Deleting a user](#deleting-a-user).

### <a name="education"></a>教育

このセクションでは、次の Microsoft Education アプリのアプリ内機能を使用して DSR 要求に対応する方法を説明します。

- Assignments
- Class Notebook

#### <a name="assignments"></a>Assignments

次の各セクションでは、Assignments のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

##### <a name="discoveraccess"></a>検出/アクセス

Assignments stores information that is generated both by teachers and students. Some of this information is store in SharePoint and some is stored in a non-SharePoint location.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>SharePoint に保存されている Assignments データの検索

Students files associated with a Submission for Assignment are stored in a document library (named **Student Work**) and files associated with Assignments that are created by teachers and (accessible by students) are stored in a different document library (named **Class Files**). Both document libraries are in the corresponding Class Team SharePoint site.

管理者は、セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、([学生の作業] および [クラス ファイル] ライブラリ内にある) 課題提出に関連する学生のファイルや課題関連のファイルを検索できます。 たとえば、管理者は組織内のすべての SharePoint サイトを検索し、検索クエリに、学生の名前とクラスまたは課題の名前を使用して DSR 要求に関連するデータを検索できます。

同様に、管理者は教師が学生に配布するファイルの課題に関連する教師ファイルを検索できます。 たとえば、管理者は組織内のすべての SharePoint サイトを検索し、検索クエリに、教師の名前とクラスまたは課題の名前を使用して DSR に関連するデータを検索できます。

詳細については、以下を参照してください。

- [課題の管理ドキュメント](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-admin-documentation)
- このガイドの [コンテンツ検索の電子情報開示ツールを使用した DSR への対応](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>SharePoint に保存されない Assignments データの検索

次の種類の Assignments データはクラス チームの SharePoint サイトには保存されないため、コンテンツ検索では検出できません。 このデータには次が含まれます。

- 学生の成績と教師からのフィードバック
- 各学生が課題用に提出したドキュメントのリスト
- 課題の詳細情報 (提出期限など)

To find data, an admin or a teacher would have to go into the Assignment in the Class Team site to find data that may be relevant to a DSR request. An admin can add themselves as an owner to the class and view all the assignments for that class team.

学生がクラスに在籍しなくなった場合でも、学生のデータはクラスに残り、「登録なし」としてマークされる場合があります。 この場合、DSR 要求を提出する学生は、以前に登録していたクラスのリストを管理者に提出する必要があります。

##### <a name="export"></a>エクスポート

PowerShell スクリプトを使用して登録した学生のすべてのクラスにおいて、特定の学生の Assignments データをエクスポートできます。その学生のクラスのリストを取得し、PowerShell スクリプトを使用してデータをエクスポートします。 参照:

- [チームの割り当てを構成する](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [特定の学生のクラスのリストを取得する](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Assignments から学生と教師のデータをエクスポートする](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-export)

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can also use the Assignment export script to export submissions data for all assignments that a teacher has access to.

##### <a name="delete"></a>削除

PowerShell スクリプトを使用して登録した学生のすべてのクラスにおいて、特定の学生の Assignments データを削除できます。その学生のクラスのリストを取得し、PowerShell スクリプトを使用してデータを削除します。 この操作は、その学生をクラスから削除する前に行う必要があります。 参照:

- [チームの割り当てを構成する](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [特定の学生のクラスのリストを取得する](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Assignments から学生のデータを削除する](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-delete)

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can't use the Assignments deletion script to delete teacher data because all Assignments are shared across the Class Team site. As an alternative, an admin would have to add themselves to the Class Team site and then delete a specific Assignment.

#### <a name="class-notebook"></a>Class Notebook

Class Notebook でコンテンツを検索する方法については、このガイドの上の方に説明があります。 「[OneNote Class Notebook](#onenote-class-notebook)」セクションを参照してください。 コンテンツ検索ツールを使用して、Class Notebook からデータをエクスポートすることもできます。 また、管理者またはデータ主体が Class Notebook からデータをエクスポートするという方法もあります。 「[Class Notebook のコピーを保存する](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec)」を参照してください。

### <a name="flow"></a>Flow

次の各セクションでは、Microsoft Flow のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検出

People can use Flow to perform data-related tasks such as synchronizing files between applications, copying files from one Office 365 service to another, and collecting data from one Office 365 app and storing it in another. For example, a user could set up a Flow to save Outlook email attachments to their OneDrive for Business account. In this example, you could use the Content Search tool to search the user's mailbox for the email message that contained the attachment or search their OneDrive for Business account for the file. This is an example where data handled by Flow might be discoverable in the Office 365 services connected by a Flow workflow.

Additionally, people can use Flow to copy or upload files from Office 365 to an external service, such as Dropbox. In these cases, a DSR request concerning the data in an external service would have to be submitted to the external service, who is processing the data in this type of scenario.

管理者が DSR 要求を受理した場合、管理者はユーザーのフローの所有者として自分自身を追加できます。 これにより、管理者はフロー定義および実行履歴のエクスポートやフローのアクセス許可の再割り当ての実行などの機能を実行できるようになります。 詳細については、「[管理センターでフローを管理する](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/)」を参照してください。

管理者が自分自身を Flow の所有者として追加できるようにするには、次のアクセス許可があるアカウントが必要になります。

- Flow/PowerApps プラン 2 ライセンス (有料版または試用版)

- [全体管理者\](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

    または

- [Azure Active Directory 全体管理者](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

これらの権限がある場合、管理者は Flow 管理センターを使用して、組織内のすべての Flow にアクセスできます。

フローの所有者として自分を追加するには:

1. <https://admin.flow.microsoft.com> に移動します。
2. Office 365 の資格情報でサインインします。
3. [**環境**] ページで、アクセスするフローの環境をクリックします。 組織には既定の環境があります。
4. On the page for the environment that you selected, click **Resources**, and then click **Flows.** A list of all flows in the environment is displayed.
5. 自分をメンバーとして追加するフローの **[詳細の表示]** をクリックします。
6. **[所有者]** で、**[共有の管理]** をクリックします。
7. **[共有]** ポップアップで、自分をメンバーとして追加して、その変更を保存します。

自分を所有者にしたら、[**Flow**] \> [**自分のフロー**] \> **[** チームのフロー] に移動してフローにアクセスします。 ここでは、実行履歴のダウンロードやフローのエクスポートを実行できます。 以下の情報を参照してください。

- [フロー実行履歴のダウンロード](https://flow.microsoft.com/blog/download-history-recurrence/)
- [パッケージによる複数の環境におよぶフローのエクスポートおよびインポート](https://flow.microsoft.com/blog/import-export-bap-packages/)

#### <a name="access"></a>Access

ユーザーは、自分のフローの定義と実行履歴にアクセスできます。

- **フロー定義:** ユーザーはフローの定義をエクスポートできます (Flow パッケージ (JSON 形式の Zip ファイル) としてエクスポートされます)。 「[パッケージによる複数の環境におよぶフローのエクスポートおよびインポート](https://flow.microsoft.com/blog/import-export-bap-packages/)」を参照してください。
- **フロー実行履歴 :** ユーザーは自分の各フローの実行履歴をダウンロードできます。 フロー実行履歴は CSV ファイルとしてダウンロードされ、フィルター処理や検索のために Excel で開くことができます。 ユーザーは、複数のフローの実行履歴をダウンロードすることもできます。 「[フロー実行履歴のダウンロード](https://flow.microsoft.com/blog/download-history-recurrence/)」を参照してください。

#### <a name="delete"></a>削除

管理者は、Flow 管理センターで、自分自身をユーザーのフローの所有者として追加できます。 ユーザーが組織を退職して Office 365 のアカウントが削除された場合、そのユーザーのみが所有者であるフローは保持されます。 これにより、組織はより簡単にフローを新しい所有者に引き継がせることができ、共有されたビジネス プロセスに使用されているフローがある場合は、フローを原因とした業務の中断を防ぎます。 管理者は、そのユーザーが所有していたフローを削除するのか、それとも新しい所有者に再割り当てるのかを判断し、そのアクションを実行する必要があります。

共有フローについては、ユーザーが組織から削除されたときに、そのユーザーの名前が所有者のリストから削除されます。

#### <a name="export"></a>エクスポート

An admin can export the definition and run history of a user's flows. To do this, an admin must add themselves as an owner of the user's flow in the Flow admin center

- **フロー定義:** 管理者はフローの所有者として自分自身を追加してから、[**Flow**] \> [**自分のフロー**] \> [**チームのフロー**] に移動すると、フロー定義をエクスポートできます (Flow パッケージ ( JSON 形式の Zip ファイル) としてエクスポートされます)。 「[パッケージによる複数の環境におよぶフローのエクスポートおよびインポート](https://flow.microsoft.com/blog/import-export-bap-packages/)」を参照してください。

- **フロー実行履歴:** 同様に、フロー実行履歴をエクスポートするには、管理者はフローの所有者として自分自身を追加する必要があります。 フロー実行履歴は、CSV ファイルとしてダウンロードされるため、フィルター処理や検索のために Excel を使用できます。 また、複数のフローの実行履歴をダウンロードすることもできます (所有権がある場合)。 「[フロー実行履歴のダウンロード](https://flow.microsoft.com/blog/download-history-recurrence/)」を参照してください。

#### <a name="connections-and-custom-connectors-in-flow"></a>Flow の接続およびカスタム コネクタ

接続するには、ユーザーは API、SaaS アプリケーションおよび独自開発されたシステムへの接続のための資格情報を提供する必要があります。 これらの接続は、接続を確立したユーザーが所有し、製品内で[管理](https://docs.microsoft.com/flow/add-manage-connections)できます。 フローの再割り当ての完了後は、管理者は PowerShell コマンドレットを使用して、ユーザー データの削除の一環として、これらの接続の一覧表示と削除を実行できます。

カスタム コネクタにより、組織は既定のコネクタが利用できないシステムに接続することで Flow の機能を拡張できます。 カスタム コネクタの作成者は、そのコネクタを組織内の別のユーザーと[共有](https://docs.microsoft.com/flow/register-custom-api)できます。 DSR 削除要求の受理後、管理者は業務の中断を避けるために、該当するコネクタの所有権を再割り当てすることを検討してください。 このプロセスを促進するために、管理者は PowerShell コマンドレットを使用して、カスタム コネクタの一覧表示、再割り当てまたは削除を実行できます。

### <a name="forms"></a>フォーム

次の各セクションでは、Microsoft Forms のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検出

Forms users can go to <https://forms.office.com> and select **My forms** to see the Forms they've created. They can also select **Shared with me** to view Forms others have shared via a link. If there are many Forms to sort through, users can use the in-product search bar to search for Forms by title or author. To determine whether Microsoft Forms is a place where personal data responsive to your DSR is likely to reside, you can ask the Data Subject to search his or her **Shared with me** list to determine which users ("Forms owners") have sent Forms to the Data Subject. You can then ask the forms owners to select **Share** in the top navigation bar and send you a link to a specific form so you can view it and further determine whether it is material to your DSR.

#### <a name="access"></a>Access

関連するフォームが見つかると、[**回答**] タブをクリックしてフォームへの応答にアクセスできます。[クイズの結果の確認方法](https://support.microsoft.com/ja-JP/office/check-and-share-your-quiz-results-c4a9b45c-d62f-4eb7-b5db-ad81892c7c07)や[フォームの結果の確認方法](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)をご覧ください。 Excel で回答結果を確認するには、[**回答**] タブを選択して、[**Excel で開く**] をクリックします。 データ主体にフォームのコピーを送信する場合は、アプリケーション内でリッチ テキスト形式で表示される関連する質問と回答のスクリーンショットを作成することも、結果の Excel コピーをデータ主体に送信することもできます。 Excel を使用しているときに、アンケート結果の一部のみをデータ主体と共有する場合は、結果を共有する前に、特定の行や列を削除したり残りのセクションを編集したりできます。 また、**[共有] \> [複製のためのリンクを取得]** ([テンプレートとして共有] の下) に移動して、データ主体にフォーム全体の複製を提供することもできます。

#### <a name="delete"></a>削除

Any survey, quiz, questionnaire, or poll can be permanently deleted by its owner. If you would like to honor a DSR "forget me" and delete a form in its entirety, find the Form in the list of forms, select the series of dots (ellipsis) in the upper right corner of the form preview window, and then click **Delete**. Once a Form is deleted, it can't be retrieved. For information, see [Delete a Form](https://support.microsoft.com/ja-JP/office/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0).

#### <a name="export"></a>エクスポート

フォームの質問と回答を Excel ファイルにエクスポートするには、フォームを開いて **[回答]** タブを選択し、**[Excel で開く]** を選択します。

### <a name="kaizala"></a>Kaizala

次の各セクションでは、Microsoft Kaizala のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検出

A user's organizational data, which is data that is shared in organizational groups, can be accessed by an admin from the Kaizala management portal. Organizational data is retained for a duration of time determined by your organization's retention policies. In addition to user data, Kaizala servers also store the following types of organizational data:

- 組織のグループに所属するメンバーのリスト
- 組織グループのメッセージ データ (組織グループ間で共有されるメッセージと応答)
- 組織内のユーザーのリスト
- 組織内のすべてのユーザーについて取得された製品とサービスの利用状況データ。
- 組織により作成された Kaizala アクション
- Kaizala コネクタ データ

A user's consumer data can be accessed by the data subject using the Kaizala mobile app for consumer data. Consumer data includes the following types of data:

- Kaizala のプライベート グループに属するデータ (Kaizala サーバーに 90 日間保存)
- ユーザーのプロファイル情報とユーザーの連絡先
- ユーザーと同じグループに所属するメンバーのリスト
- グループ間で共有されるグループのメッセージと応答
- ユーザーの連絡先リスト (Kaizala サービスに保存)
- Kaizala でユーザーが実行したトランザクション (インドの Kaizala ユーザーのみに適用)
- ユーザーの製品およびサービスの利用状況データ

#### <a name="access"></a>Access

Kaizala users can go to their mobile device to see Kaizala content they've created on their device. To determine whether Kaizala mobile apps is a place where personal data responsive to a DSR is likely to reside, you can ask the data subject to search their Kaizala app for the requested information.

#### <a name="export"></a>エクスポート

When users in your organization use Kaizala, consumer data is generated, and organizational data may be generated if the user participates in an organization group. Admins can export a user's organizational data from the Kaizala management portal. Kaizala consumer users can export their private data from the Kaizala mobile app. In both cases, note that product and service usage data is also export when an admin or user exports Kaizala data. For details, see:

- [Kaizala でユーザーの組織データをエクスポートまたは削除する](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Kaizala モバイル アプリでデータをエクスポートまたは削除する](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

#### <a name="delete"></a>削除

A Kaizala admin can remove a Kaizala user's account in the Kaizala management portal. After a user account is deleted, the user is removed from all groups that belong to your organization and organizational data is deleted from their device. 

To remove all private data from the user's mobile device, the Kaizala user can delete their Kaizala account. After the account is deleted, all related Kaizala content including, chats, photos, and other data will be deleted from the device.

詳細については、以下を参照してください。

- [Kaizala でユーザーの組織データをエクスポートまたは削除する](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Kaizala モバイル アプリでデータをエクスポートまたは削除する](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

### <a name="planner"></a>Planner

次の各セクションでは、Microsoft Planner のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検索

Planner の計画は、Microsoft 365 グループに関連付けられ、Microsoft 365 グループのファイルはグループに関連付けられた SharePoint Online サイトに保存されます。 そのため、Planner のファイルはコンテンツ検索を使用して、Microsoft 365 グループのサイトを検索することで見つけることができます。 これを実行するには、Microsoft 365 グループの URL が必要になります。 Microsoft 365 グループに関する情報の取得に関するヒントについては、ヘルプ トピック「Office 365 のコンテンツ検索」の「[Microsoft Teams および Microsoft 365 グループの検索](https://docs.microsoft.com/microsoft-365/compliance/content-search)」を参照してください。これは、対応する SharePoint Online サイト内の Planner ファイルを検索する際に役立ちます。

#### <a name="access"></a>Access

前述のように、SharePoint Online サイト、およびプランに関連付けられているメールボックスを検索できます。 プレビューで表示したり、データへのアクセスに関連する検索結果をダウンロードできます。

#### <a name="delete"></a>削除

You can manually delete a user's personally information by either giving yourself permissions to access the plans the user is part of or signing in as the user to make the changes. See [Delete user data in Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f).

#### <a name="export"></a>エクスポート

You can use a PowerShell script to export a user's data from Planner. When you export the data, a separate JSON file is export for each plan that the user is a part of. See [Export user data from Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08).

### <a name="power-bi"></a>Power BI

次の各セクションでは、Microsoft Power BI のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検索
You can search for content in the different workspaces in Power BI, including dashboards, reports, workbooks, and datasets. Each type of workspace contains a search field that you can use to search that workspace. See [Searching, finding, and sorting content in Power BI service](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Access

Power BI のレポートから、ダッシュボード、レポートおよびビジュアルを印刷して、物理的なコピーを作成できます。 レポート全体を印刷することはできず、一度に印刷できるのは 1 ページのみです。 これを実行するには、レポートに移動し、検索フィールドを使用して特定のデータを見つけ、そのページを印刷します。 詳細については、「[Power BI サービスからの印刷](https://docs.microsoft.com/power-bi/service-print)」を参照してください。

#### <a name="delete"></a>削除

ダッシュボード、レポート、およびブックを削除する場合は、「[Power BI サービスのほとんどすべてのものを削除する](https://docs.microsoft.com/power-bi/service-delete)」を参照してください。

Deleting a dashboard, report, or workbook doesn't delete the underlying dataset. Because Power BI relies on a live connection to the underlying source data to be complete and accurate, deleting personal data must be done there. (For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.)

データの削除後に、Power BI の[スケジュールされたデータ更新](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh)機能を利用することで、Power BI に保存されたデータセットを更新できます。その後、削除したデータは、そのデータを利用していた Power BI レポートまたはダッシュボードに反映されなくなります。 GDPR 要件に準拠できるようにするために、適切な周期で確実にデータを更新するポリシーの実施が必要になります。

#### <a name="export"></a>エクスポート

データ ポータビリティ要求への対応を促進するために、Power BI のダッシュボードとレポートをエクスポートできます。

- You can export the underlying data for dashboards and reports to a static Excel file. See the video in [Printing from Power BI service](https://docs.microsoft.com/power-bi/service-print). Using Excel, you can then edit the personal data to be included in the portability request, and save it in a commonly used, machine-readable format such as .csv or .xml.
- You can export (download) a report from the Power BI service in Office 365 to a .pbix file if it was originally published using Power BI Desktop. You can then import this file to Power BI Desktop and publish (export) it to the Power BI service of another organization. See [Export a report from Power BI service to Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

次のセクションでは、Microsoft PowerApps のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、削除を実行する方法について説明します。 ここでは、管理者がビジネスの中断を抑えて、アプリと依存リソースを新しい所有者に移行する方法の概要手順を示します。

#### <a name="discover"></a>検索

PowerApps は、組織内で共有および使用できるアプリを作成するためのサービスです。 アプリの作成および実行プロセスの一環として、ユーザーは複数の種類のリソースとデータを PowerApps サービスに保存することになります。このデータとリソースには、アプリ、環境、カスタム コネクタ、およびアクセス許可が含まれます。

PowerApps に関連する DSR 要求を支援するために、[PowerApps 管理センター](https://admin.powerapps.com/)および[PowerApps 管理 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804)で公開されている管理操作を利用できます。 こうしたツールにアクセスするには、次のアクセス許可があるアカウントが必要になります。

- 有料版の PowerApps プラン 2 ライセンスまたは PowerApps プラン 2 試用版ライセンス。 30 日間の試用版ライセンスは、[ここから](https://web.powerapps.com/trial)サインアップできます。
- [全体管理者](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)または
- [Azure Active Directory 全体管理者](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

個人データの検索の詳細については、「[データ主体の権利 (DSR) による PowerApps 顧客データに対する要求への対応](https://go.microsoft.com/fwlink/?linkid=871880)」を参照してください。

PowerApps サービスには、Common Data Service for Apps も含まれています。これにより、ユーザーは Common Data Service データベース内の標準およびカスタムのエンティティにデータを保存できます。 こうしたエンティティに保存されたデータは、[PowerApps メーカー ポータル](https://web.powerapps.com)で表示できます。また、製品内の検索機能 [[高度な検索](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)] を使用してエンティティ内の特定のデータを検索できます。 Common Data Service 内の個人データの検出に関する詳細については、「[データ主体の権利 (DSR) による Common Data Service for Apps の顧客データに対する要求への応答](https://go.microsoft.com/fwlink/?linkid=871881)」を参照してください。

#### <a name="access"></a>Access

管理者は、アプリと関連リソース (フロー、接続、およびカスタム コネクタを含む) にアクセスして実行する権限を自分自身に割り当てることができます。これには、[PowerApps 管理センター](https://admin.powerapps.com/)または [PowerApps 管理 PowerShell コマンドレット](https://go.microsoft.com/fwlink/?linkid=871804)を使用します。

After you have access to the user's app, you can use a web browser to open the app. After you open an app, you can take a screenshot of the data. See [Use PowerApps in a web browser](https://docs.microsoft.com/powerapps/run-app-browser).

#### <a name="delete"></a>削除

PowerApps を使用すると、ユーザーは組織の日常業務にとって重要な部分になる基幹業務アプリケーションを作成できるようになるため、ユーザーが組織を退職して Office 365 アカウントが削除されたときに、管理者は、そのユーザーが所有していたアプリを削除するか、単に新しい所有者に再割り当てするかを判断する必要があります。 これにより、組織はより簡単にアプリを新しい所有者に引き継がせることができ、共有されたビジネス プロセスに使用されているアプリがある場合は、アプリを原因とした業務の中断を防ぎます。

アプリのような共有データについては、そのユーザーの共有データを完全に削除するか、またはデータを自分自身または組織内の別のユーザーに再割り当てして保持するかを管理者が判断する必要があります。 詳細については、「[データ主体の権利 (DSR) による PowerApps 顧客データの削除要求への応答](https://go.microsoft.com/fwlink/?linkid=871883)」を参照してください。

Any data that was stored by a user in an entity in a Common Data Service For Apps database will also need to be reviewed and (if desired) deleted by an admin using the in-product capabilities. See [Delete Common Data Service user personal data](https://go.microsoft.com/fwlink/?linkid=871886).

#### <a name="export"></a>エクスポート

Admins have the ability to export personal data stored for a user within the PowerApps service using the [PowerApps Admin Center](https://admin.powerapps.com/) and [PowerApps Admin PowerShell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804). See [Export PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871883).

You can also use the in-product search capabilities of [Advanced Find](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) to search for a user's personal data in any entity. For details about exporting personal data in the Common Data Service, see [Export Common Data Service personal data](https://go.microsoft.com/fwlink/?linkid=871889).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>PowerApps の接続およびカスタム コネクタ

接続するには、ユーザーは API、SaaS アプリケーションおよび独自開発されたシステムへの接続のための資格情報を提供する必要があります。 これらの接続は、接続を確立したユーザーが所有し、製品内で[管理](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection)できます。 PowerApps の再割り当ての完了後は、管理者は PowerShell コマンドレットを使用して、ユーザー データの削除の一環として、これらの接続の一覧表示と削除を実行できます。

カスタム コネクタにより、組織は既定のコネクタが利用できないシステムに接続することで PowerApps の機能を拡張できます。 カスタム コネクタの作成者は、そのコネクタを組織内の別のユーザーと[共有](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps)できます。 DSR 削除要求の受理後、管理者は業務の中断を避けるために、該当するコネクタの所有権を再割り当てすることを検討してください。 このプロセスを促進するために、管理者は PowerShell コマンドレットを使用して、カスタム コネクタの一覧表示、再割り当てまたは削除を実行できます。

### <a name="project-online"></a>Project Online

次の各セクションでは、Microsoft Project Online のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover-and-access"></a>検出とアクセス

コンテンツ検索を使用して、Project に関連付けられている SharePoint Online サイトを検索できます (Project の最初の作成時に、関連付ける SharePoint Online サイトを作成するオプションがあります)。コンテンツ検索では、Project Online の実際のプロジェクトに含まれるデータは検索されず、関連付けられたサイトのみが検索されます。 コンテンツ検索により、プロジェクトに関するメタデータ (件名でメンションされたユーザーなど) が検索されますが、これは、DSR に関連するデータが含まれる Project を見つける (およびアクセスする) 際に役立つことがあります。

>[!TIP]
>The URL for the site collection in your organization where sites associated with Projects is **https://\<your org\>.sharepoint.com/sites/pwa**; for example, **https://contoso.sharepoint.com/pwa**. You can use this specific site collection as the location of your content search and then the name of the Project in the search query. Additionally, an IT admin can use the Site Collections page in the SharePoint admin center to get a list of PWA site collections in the organization.

#### <a name="delete"></a>削除

You can delete information about a user from your Project Online environment. See [Delete user data from Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7).

#### <a name="export"></a>エクスポート

You can a specific user's content from your Project Online environment. This data is exported to multiple files in the JSON format. For step-by instructions see, [Export user data from Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d). For detailed information about the files that are exported, see [Project Online export json object definitions](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7).

### <a name="publisher"></a>Publisher

次のセクションでは、Microsoft Publisher のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、削除を実行する方法について説明します。

#### <a name="discover"></a>検索

ほとんどの Office アプリケーションと同じように Publisher ファイルのテキストを検索するには、アプリ内の検索機能を使用します。 [テキストを検索して変換する](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268)を参照してください。

#### <a name="access"></a>Access

データを見つけたら、スクリーン ショットを撮るか、または Word やテキストファイルへコピーペーストし、ユーザーに提供します。 Word、PDF または XPS ファイルとしてテキストを保存することもできます。 参照:

  - [Word 文書として保存する ](https://support.microsoft.com/ja-JP/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [名前を付けて保存するか、Publisher を使用して .pdf か .xps に変換する ](https://support.microsoft.com/ja-JP/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>エクスポート

実際の Publisher ファイルをユーザーに提供するか、または前述のように、Word、PDF、XPS ファイルとして保存もできます。 参照:

  - [Word 文書として保存する ](https://support.microsoft.com/ja-JP/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [名前を付けて保存するか、Publisher を使用して .pdf か .xps に変換する ](https://support.microsoft.com/ja-JP/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>削除

文書からコンテンツを削除、ページ全体の削除、または Publisher ファイル全体を削除できます。 [ページを追加、または削除する](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08)を参照してください。

### <a name="stream"></a>Stream

次の各セクションでは、Microsoft Stream のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検索

Stream で生成またはアップロードされ、データ主体要求に関連する可能性のあるコンテンツを検出する場合は、Stream 管理者はユーザー レポートを実行し、Stream ユーザーがアップロード、作成、または投稿したビデオ、ビデオの説明、グループ、チャネル、コメントを確認します。 レポートの生成手順については、「[Microsoft Stream でユーザー データを管理する](https://docs.microsoft.com/stream/managing-user-data)」を参照してください。 レポートは HTML 形式で出力され、関連する可能性のあるビデオに移動するためのハイパーリンクが含まれています。 カスタム アクセス許可が設定されており、自分が対象ユーザーではないビデオを閲覧するには、管理者モードでビデオを閲覧します。詳細については、「[Microsoft Stream での管理機能](https://docs.microsoft.com/stream/manage-content-permissions)」を参照してください。  

#### <a name="access"></a>Access

Depending on the nature of the data subject request, a copy of the report described above can be used help satisfy a data subject request. The user report includes the Stream user's name and unique ID, a list of videos the user uploaded, a list of videos the user has access to, a list of channels the user created, a list of all the groups the user is a member of, and a list of all comments the user left on videos. The report further shows whether the user viewed each video listed in the user report. If you would like to provide the data subject with access to a video to satisfy a DSR request, you can share the video.

#### <a name="export"></a>エクスポート

Stream の「アクセス」セクションを参照してください。 

#### <a name="delete"></a>削除

To delete or edit videos or any other Stream content, a Stream admin can select view in admin mode to perform the necessary function. See [Admin capabilities in Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). If a user has left the organization and would like to have their name removed from appearing next to videos that they uploaded, you can remove their name or replace it with another. See [Managing deleted users in Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway

次の各セクションでは、Microsoft Sway のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検索

Sway を使用して作成したコンテンツ ([www.sway.com](https://sway.office.com/) にあります) を表示できるのは、作成者により Sway の表示を許可されたユーザーおよび所有者だけです。 詳細については、「[Sway のプライバシー設定](https://support.microsoft.com/ja-JP/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217)」を参照してください。 DSR に対応する個人データが Sway に存在している可能性があるかどうかを判断するには、データ主体およびデータ主体に関するコンテンツを作成した可能性の高い組織のユーザーに各々の Sway を検索するよう依頼し、データ主体の要求に対応する個人データが含まれている可能性が高い Sway を管理者と共有してもらいます。 Sway の共有方法については、記事「[Sway を共有する](https://support.microsoft.com/ja-JP/office/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998)」の「組織のアカウントから Sway を共有する」を参照してください。

#### <a name="access"></a>Access

データ主体と共有する必要のある個人データをいずれかの Sway で見つけた場合、いくつかの方法でそのデータへのアクセス権をデータ主体に提供できます。 データ主体に Sway のオンライン バージョンのコピーを提供する (上記の説明を参照)、共有したい Sway の関連部分のスクリーンショットを作成する、または Sway を印刷するか Word にダウンロードまたは PDF に変換することができます。 Sway のダウンロード方法については、下記の「エクスポート」のセクションで詳しく説明します。

#### <a name="delete"></a>削除

To learn how to delete a Sway, go to the "How do I delete my Sway?" section in [Privacy settings in Sway](https://support.microsoft.com/ja-JP/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).

#### <a name="export"></a>エクスポート

Sway をエクスポートするには、ダウンロードする Sway を開いて、右上にある連続するドット (省略記号) を選択して、**[エクスポート]** → **[Word]** または **[PDF]** を選択します。

### <a name="whiteboard"></a>Whiteboard

次の各セクションでは、Microsoft Whiteboard のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

- [Surface Hub での Whiteboard 2016](#whiteboard-2016-on-surface-hub)
- [その他すべてのプラットフォームでの Whiteboard](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Surface Hub での Whiteboard 2016

このセクションでは、Surface Hub で組み込みの Whiteboad 2016 アプリを使用して作成したデータに対する DSR 要求への対応について説明します。

##### <a name="discover"></a>検出

Whiteboard files (.wbx files) are stored in users' OneDrive for Business account. You can ask the data subject or other users if whiteboards they created may contain personal data responsive to a DSR request. They can share a whiteboard with you, or you can get a copy of it to give to the data subject.

ホワイトボードにアクセスして転送するには、以下の操作を実行します。 

1. Give yourself access to the user's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data).
2. ユーザーの OneDrive for Business アカウントで Whiteboard App Data フォルダーに移動し、転送するホワイトボードの .wbx ファイルをコピーします。
3. データ主体の OneDrive for Business アカウントへのアクセスを自分自身に許可し、Whiteboard App Data フォルダーに移動します。
4. 前の手順でコピーした .wbx ファイルを貼り付けます。

##### <a name="access"></a>Access

ホワイト ボードで DSR アクセス要求に関連する個人データを検出した場合に、データ主体にホワイトボードへのアクセスを提供する方法はいくつかあります。

- ホワイトボードの該当する部分のスクリーンショットを作成します。
- Upload a copy of the .wbx file to the data subject's OneDrive for Business account. See the previous section for steps on accessing and transferring .wbx files.
- ホワイトボードのコピーを .png ファイルとしてエクスポートします。

##### <a name="export"></a>エクスポート

ホワイトボードのコピーを取得した場合は、そのコピーをエクスポートできます。 

1. Surface Hub で Whiteboard を起動します。
2. Tap the Share button and then select Export a copy.
You can export a whiteboard to a OneNote (.one) file or to an image (.png) file.

##### <a name="delete"></a>削除

ユーザーの OneDrive for Business アカウントへのアクセスを自分自身に許可し、ホワイトボードを削除します。

1. Give yourself access to the data subject's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
2. Whiteboard App Data フォルダーに移動し、このフォルダーの内容を削除します。

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>PC、Surface Hub、およびその他のプラットフォーム用の Whiteboard

If an admin receives a DSR request for data in the new Whiteboard app, they can use Whiteboard PowerShell to add themselves (or other users) as an owner of a user's whiteboards. This enables an admin to perform actions including accessing, exporting, and deleting whiteboards. Use either the **Set-WhiteboardOwner** cmdlet to add yourself or another user as the owner of a whiteboard or use the **Invoke-TransferAllWhiteboards** cmdlet to transfer the ownership of all whiteboards for a specific user to a new owner. For information about using these cmdlets and installing the Whiteboard PowerShell module, see Microsoft Whiteboard cmdlet reference.
After you or another person has ownership of a whiteboard, see [Microsoft Whiteboard cmdlet reference](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps).

管理者または他のユーザーがホワイトボードの所有者になった後の、ホワイトボードへのアクセス、ホワイトボードのエクスポート、およびホワイトボードの削除の詳細については、「[ホワイトボードのサポート記事](https://go.microsoft.com/fwlink/?linkid=872780)」を参照してください。

### <a name="yammer"></a>Yammer

次の各セクションでは、Microsoft Yammer のアプリ内機能を使用して、個人データの検索、アクセス、エクスポート、および削除を実行する方法について説明します。

#### <a name="discover"></a>検索

Yammer 管理センターでは、Yammer 認証管理者 (全体管理者または Yammer で設定された認証管理者) が、特定のユーザーに関連するデータをエクスポートできます。 このエクスポートには、ユーザーが投稿したメッセージとファイルに加えて、ユーザーが作成したトピックとグループに関する情報も含まれます。 ユーザー固有のデータのエクスポートを実行すると、管理者には、ユーザーのアカウント アクティビティのデータが含まれる受信トレイ メッセージも送られてきます。管理者は、このデータをユーザーに提供することもできます。 詳細な手順については、「[Yammer Enterprise: プライバシー](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)」を参照してください。

ユーザー固有のエクスポートは単一のネットワークに対応しているため、ユーザーが外部の Yammer ネットワークに存在する場合、管理者は、その外部ネットワーク用とホーム ネットワーク用にデータをエクスポートする必要があります。

データ エクスポートに含まれていないデータにアクセスする場合は、ユーザーのプロファイル、設定、グループ メンバーシップ、ブックマークしたメッセージ、フォローしているユーザー、およびフォローしているトピックのスクリーンショットを作成できます。 この情報は、ユーザーまたは管理者が収集できます。 詳細については、「[Yammer Enterprise: プライバシー](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)」を参照してください。

#### <a name="access"></a>Access

You can view data in the exported files, including the full text of messages and the contents of files. You can also click links in the exported files to go directly to the posted messages and files in Yammer, and to groups, and topics the user created, messages the user liked, messages where the user is @mentioned, polls the user has voted on, and links the user has added.

ユーザーごとのデータのエクスポートには、次の情報は含まれません。

- ユーザーのプロファイル:
    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    
    - If the user has an Office 365 identity, the Yammer user profile is pulled automatically from Office 365, which gets the profile information from Azure Active Directory (AAD). Yammer users can temporarily change their profiles in Yammer, but these changes are overwritten when there is a change in AAD, so you must view and change directory data in AAD. See [Manage Yammer users across their lifecycle from Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) and [Add or change profile information for a user in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   ユーザーの設定:

- The user can view and change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.<br/>
    - ユーザーのグループ メンバーシップ、ブックマークしたメッセージ、フォローしているユーザー、およびフォローしているトピック。
    
    - The user can view this information. For information on how, see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.

#### <a name="export"></a>エクスポート

For instructions for how to export data, see [Manage GDPR data subject requests in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise). You must run a per-user export for each Yammer network the user is a member of.

Yammer にはデータ保存設定があり、ユーザーがメッセージやファイルを削除したときに、データは論理的または物理的のどちらかで削除されます。 論理的な削除に設定されている場合、ユーザーが削除したデータはエクスポートに含まれます。 Yammer のデータ保存設定が物理的な削除に設定されている場合、削除された情報は Yammer に保存されなくなり、エクスポートには含まれなくなります。

#### <a name="delete"></a>削除

Yammer allows verified admins to execute a GDPR-compliant delete via the Yammer admin center if they receive a DSR. This option is called Erase User, and it suspends the user for 14 days and then removes all their personal data, excluding files and messages. If the user is a guest user, this must be done for each external network the guest user is a member of.

>[!NOTE]
>If an admin wants to remove the files and messages of a user during the 14-day window, they will have to perform a user level export to identify the files and messages, and then decide which ones to delete either by in-product deletion or by using a PowerShell script. After the 14-day window, the admin can no longer associate the user with their files or messages.

When a user is deleted with the Erase User option, notification is sent to the Yammer Inbox of all network admins and verified admins. The Erase User option deletes the user's Yammer profile, but does not delete their Office 365 or Azure Active Directory profile.

ユーザーを削除する詳細な手順については、「[Yammer Enterprise の GDPR データ主体の要求を管理する](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)」を参照してください。

## <a name="responding-to-dsr-rectification-requests"></a>DSR 訂正要求への対応

データ主体が、Office 365 に保存されている組織のデータに存在する個人データの修正を求めた場合、担当者および組織は、その要求に応じることが適切かどうかを判断する必要があります。 要求に応じる場合、データの訂正には、ドキュメントや他の種類のアイテムに含まれている個人情報の編集、修正、または削除などの処置が伴います。 そのための最も簡単な方法は、データ/ドキュメントの所有者に依頼して、適切な Office 365 アプリケーションを使用して要求された変更を実行してもらうことです。 または、組織内の IT 管理者が、その変更を実行します。 多くの場合、IT 管理者 (または、適切な権限を持つ SharePoint Online サイト コレクション管理者などの組織内の別のユーザー) は、自分または DSR の作業担当者に、ドキュメントまたはドキュメントが保存されているコンテンツの場所へのアクセスに必要な権限を割り当てる必要があります。その上で、ドキュメントで直接変更を実行します。

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>承認された変更を実行するようにデータ所有者に要求する

The most direct way to rectify personal data is to ask the data owner to make the change. After you locate the data that is the subject of the DSR, you can provide the following information so that they can make the change.

- 変更が必要なアイテムの場所とファイル名 (ドキュメントやファイルの場合)。 対象のデータの特定は、前述の[検出プロセス](#using-content-search-to-find-personal-data)の一部です。
- データ所有者が実行する必要のある承認された変更

要求された変更が実行されたことを DSR 調査の関係者が確認する、確認プロセスの実施について検討してください。

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>変更を加える SharePoint Online サイトまたは OneDrive for Business アカウントへのアクセス権を取得する

If it's not feasible for the data owner to implement the data subject's request for rectification, an IT admin or SharePoint admin in your organization can get access to the content location and make the required changes. Or, an admin can assign you or another data privacy officer the necessary permissions.

#### <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online サイトへの管理者アクセス許可または所有者アクセス許可を割り当てて、別の担当者が対象のドキュメントにアクセスして編集できるようにする場合は、次を参照してください。

- [サイト コレクションの管理者を管理する](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators)

- [SharePoint リストまたはライブラリのアクセス許可を編集および管理する](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>OneDrive for Business

全体管理者は、Office 365 管理センターを使用して、ユーザーの OneDrive for Business アカウントにアクセスできます。

1. 全体管理者の資格情報で Office 365 にサインインします。
2. 管理センターにアクセスします。
3. **[アクティブなユーザー]** に移動して、ユーザーを選択します。
4. 詳細ウィンドウの **[OneDrive for Business の設定]** を展開して、**[ファイルにアクセスする]** をクリックします。
5. URL をクリックして、ユーザーの OneDrive for Business アカウントに移動します。

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>データに変更を加える Exchange Online メールボックスへのアクセス権を取得する

A global admin can assign themselves the permissions necessary to open and edit (or delete) items in another user's mailbox, as if they were the mailbox owner. A global admin can also assign these permissions to another user. Specifically, the global admin needs to add the **Read and manage** permission, which is the Full Access permission in Exchange Online. For details, see:

- [Office 365 の別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
- [別のユーザーのメールボックスにアクセスする](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

ユーザーのメールボックスが訴訟ホールドの状態にある場合や、アイテム保持ポリシーが適用されている場合、メールボックスのすべてのバージョンは、保持期間が経過するか、ホールドがメールボックスから削除されるまで維持されます。 つまり、DSR 訂正要求への対応でメールボックス アイテムが変更される場合でも、元の (変更を加える前の) アイテムのコピーが、ユーザーのメールボックスの [回復可能なアイテム] フォルダー内の非表示フォルダーに残されて保存されることになります。

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business と SharePoint Online のコンテンツに変更を加える

Admins or data owners can make changes to SharePoint Online documents, lists, and pages. Keep the following things in mind when making changes to SharePoint content:

- ドキュメントを更新すると、変更が含まれている新しいバージョンのドキュメントが保存されます。 ドキュメントの古いバージョンは更新されません。 これは、DSR 訂正要求の対象になっているデータが、トピックの古いバージョンに残ってしまう可能性があることを意味します。 トピックの古いバージョンは削除して、Office 365 から完全に削除できます。 このガイドの「 [SharePoint Online および OneDrive for Business のドキュメントを削除する](#deleting-documents-in-sharepoint-online-and-onedrive-for-business)」セクションを参照してください。
- データ主体のトレース (ファイルのすべてのバージョンとデータ主体が実行したアクティビティのすべての記録を含む) をすべてファイルから削除する方法で SharePoint ファイルを完全に修正するには、次の手順を実行する必要があります。

    1. ファイルのコピーをローカル コンピューターにダウンロードします。
    2. Permanently delete the file from SharePoint Online, by deleting the file, and then deleting if from the first-stage and second-stage Recycle Bin. See the [Deleting documents in SharePoint Online and OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) section in this guide.
    3. ローカル コンピューター上のドキュメントのコピーに変更を加えます。
    4. 変更したファイルを元の SharePoint Online の場所にアップロードします。

- Data in SharePoint lists can be edited. See [Add, edit, or delete list items](https://support.microsoft.com/ja-JP/office/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde).

IT 管理者は、ドキュメントに関連付けられた特定の個人的なプロパティを修正することもできます。

User information from the SharePoint User Profile or Office 365 is often associated with OneDrive for Business and SharePoint Online documents to represent that person. For example, a user's name in a Created By or Modified By People column for a document or list item. This user information can be rectified in several ways, depending on the source:

- ユーザーの所有するオンプレミスの Active Directory でユーザー プロパティを修正する。 「表示名」や「氏名 (名)」などのユーザーのプロパティをオンプレミスの AD から同期している場合は、該当するプロパティはその AD で修正する必要があります。 適切にマップされたプロパティは、Office 365 に送られてから OneDrive for Business および SharePoint Online に送られます。
- 管理センターでユーザー プロパティを修正する。 管理センターで行われたアカウント情報の変更は、OneDrive for Business および SharePoint Online のエクスペリエンスに自動的に反映されます。 詳細については、「[Azure Active Directory でユーザーのプロファイル情報を追加または変更する](https://go.microsoft.com/fwlink/?linkid=864809)」を参照してください。 Office 365 から取得されるプロパティは、SharePoint 側では変更できません。
- Rectify user properties in the SharePoint user profile experience of the SharePoint admin center. In the user profiles tab of the SharePoint admin center, admins can click **Manage user profiles**, and look up any user's properties. Then they can choose to Edit the user's properties.
- Rectify user properties in a custom source. Custom SharePoint profile properties may be syncing from a custom source via Microsoft Identity Manager (MIM) or another method.

古い情報が保持されているエクスペリエンスがある可能性があるため、これはすべてのエクスペリエンスに影響するわけではありません。 たとえば、ユーザーの名前がドキュメント内でテキストとして保持されているかもしれません。

### <a name="making-changes-to-content-in-power-bi"></a>Power BI のコンテンツに変更を加える

Power BI relies on the underlying source data used in its dashboards and reports to be complete and accurate, so correcting inaccurate or incomplete source data must be done there. For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.

After those changes are made, you can take advantage of the [scheduled data refresh](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) capabilities to update the dataset that is stored in Power BI so that the revised data is reflected in the dependent Power BI assets. To help comply with GDPR requirements, you should have policies in place to ensure that you are refreshing your data at an appropriate cadence.

### <a name="making-changes-to-content-in-yammer"></a>Yammer のコンテンツに変更を加える

For messages, a user can edit a given message to rectify any inaccuracies. They can request a list of all their messages from a Yammer verified admin, and then click a link in the file to review each message.

For files, a user can edit a given file to rectify any inaccuracies. They can request a list of all the files they posted from a Yammer verified admin, and then access the files in Yammer. Files that are exported into the Files folder can be viewed by searching for the file by number. For example, for a file named 12345678.ppx in the export, use the Search box in Yammer to search for 1235678.ppx. Or, go to <strong>https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\></strong>; for example, <strong>https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678</strong>.

ユーザーが自分のプロファイルおよび設定からアクセスできるデータについては、ユーザーが必要な変更を実行できます。

- ユーザーのプロファイル:

    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - ユーザーが Office 365 ID を持っている場合は、Yammer ユーザー プロファイルが Office 365 から自動的に採用されます。このプロファイル情報は Azure Active Directory (AAD) から取得されます。 Yammer ユーザーは自分のプロファイルを Yammer で一時的に変更できますが、こうした変更は AAD で変更があったときに上書きされるため、ディレクトリ データの表示と変更を行う最適の場所は AAD です。 ユーザーは、AAD の更新をリクエストする必要があります。 詳細については、「[Office 365 から Yammer ユーザーのライフサイクル全体を管理する](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle)」および「[Azure Active Directory でユーザーのプロファイル情報を追加または変更する](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal)」を参照してください。

- ユーザーの設定:

    - The user can change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - The user's group membership, bookmarked messages, followed users, and followed topics. The user can change this information; see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380).

## <a name="responding-to-dsr-restriction-requests"></a>DSR 制限要求への対応

次に、Office 365 のデータの処理を制限する方法を示します。

- Office 365 アプリケーションのライセンスを削除して、ユーザーがアプリケーションからデータにアクセスできないようにする
- ユーザーが OneDrive for Business アカウントにアクセスできないようにする
- Office 365 サービスによるデータの処理をオフにする
- SharePoint Online と OneDrive for Business から一時的にデータを削除してオンプレミスに保持する
- SharePoint Online サイトへのすべてのアクセスを一時的に制限する
- ユーザーが Office 365 にサインインできないようにする

組織が後になって制限の適用が必要ないと判断した場合は、制限を適用した際の手順を逆に実行 (ライセンスを再割り当てする、サービスをオンに戻す、ユーザーが Office 365 にサインインできるようにするなど) して制限を停止できます。

### <a name="removing-the-license-for-an-office-365-application"></a>Office 365 アプリケーションのライセンスを削除する

前述したように、組織の Microsoft 365 for business サブスクリプションに含まれるすべての Office 365 アプリケーションのライセンスは、既定ですべてのユーザーに割り当てられます。 DSR の対象になるデータへのアクセスを制限する必要がある場合、IT 管理者は Office 365 管理ポータルを使用して、ユーザーのアプリケーションのライセンスを一時的にオフにできます。 その後でユーザーが対象のアプリケーションを使用しようとすると、ライセンスされていない製品の通知、またはアクセス許可がなくなったことを示すメッセージが表示されます。 詳細については、「[一般法人向け Office 365 のユーザーからライセンスを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。

**注:**

- ユーザーの Yammer へのアクセスを制限するには、まず、[Yammer ユーザーに Office 365 ID を適用](https://docs.microsoft.com/yammer/configure-your-yammer-network/enforce-office-365-identity)する必要があり、その後でユーザーの Yammer ライセンスを削除します。

- Power BI Embedded を利用するシナリオの場合、コンテンツが埋め込まれている ISV (独立系ソフトウェア ベンダー) アプリケーションへのアクセスを制限できます。

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>ユーザーが自分の OneDrive for Business アカウントにアクセスできないようにする

ユーザーの SharePoint Online ライセンスを削除しても、OneDrive for Business アカウントがある場合、そのユーザーは OneDrive for Business アカウントにアクセスできてしまいます。 OneDrive for Business アカウントへのユーザーの権限を削除する必要があります。 これは、ユーザーが持つ、OneDrive for Business アカウントのサイト コレクション所有者の権限を削除することで実行できます。 具体的には、ユーザーのユーザー プロファイルで、サイト コレクション管理者 (プライマリ) およびサイト コレクション管理者のグループからユーザーを削除する必要があります。 詳細については、「[SharePoint Online 管理センターでユーザー プロファイルを管理する](https://docs.microsoft.com/sharepoint/manage-user-profiles)」の「OneDrive for Business アカウントに対する管理者の追加および削除」セクションを参照してください。

### <a name="turning-off-an-office-365-service"></a>Office 365 サービスをオフにする

データ処理の制限についての DSR 要求に対応するために、Office 365 サービスをオフにするという方法もあります。 この方法は組織全体に影響を与え、すべてのユーザーがサービスの使用やサービスのデータへのアクセスができなくなります。

The most expedient way to turn off a service is to use Office 365 PowerShell and remove the corresponding user license from all users in the organization. This will in effect restrict anyone from access data in that service. For detailed instructions, see [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and follow the procedures to disable Office 365 services for users from a single licensing plan.

>[!NOTE]
>For Yammer, in additional to removing the Yammer license from user accounts, you also must disable users' ability to sign in to Yammer with Yammer credentials (by enforcing the use of their Office 365 credentials when signing in). For detailed instructions, see [Turn off Yammer access for Microsoft 365 users](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>SharePoint Online または OneDrive for Business のサイトから一時的にデータを削除する

Another way to restrict the processing of personal data is to temporarily remove it from Office 365 in response to a DSR. When your organization determines that the restriction no longer applies, you can import the data back into Office 365.

ほとんどの Office ドキュメントは SharePoint Online または OneDrive for Business のサイトにあるため、ここでは、サイトからドキュメントを削除して、そのドキュメントを再インポートする手順の概要を示します。

1. Get a copy of the document that is the subject of the restriction request. You may have to request either access to the site or ask a global admin or a site collection administrator to provide you with a copy of the document.
2. そのドキュメントをオンプレミスの場所 (ファイル サーバーやファイル共有) や Microsoft クラウド内の Office 365 テナント以外の場所に保存します。
3. Permanently delete (purge) the original document from Office 365. This is a 3-step process:

    a.  Delete the original copy of the document. When you delete a document from a site, it's sent to the site Recycle Bin (also called the *first-stage Recycle Bin*).

    b.  Go to the site Recycle Bin and delete that copy of the document. When you delete a document from the site Recycle Bin, it's sent to the site collection Recycle Bin (also called the *second-stage Recycle Bin*). See [Delete a file, folder, or link from a SharePoint document library](https://support.microsoft.com/ja-JP/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52).

    c.  Go to the site collection Recycle Bin and delete that copy of the document, which permanently removes it from Office 365. See [Delete items from the site collection recycle bin](https://support.microsoft.com/ja-JP/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653).

4. 制限の適用が不要になったときには、オンプレミスに保存しておいたドキュメントのコピーを Office 365 のサイトに再アップロードできます。

>[!IMPORTANT]
>The preceding procedure won't work if the document is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a restriction request for a DSR takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted. Additionally, the document history for deleted documents is permanently removed.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>SharePoint Online サイトへのアクセスを一時的に制限する

SharePoint Online の管理者は、サイト コレクションをロックすることで、一時的にすべてのユーザーが SharePoint Online サイト コレクションにアクセスできないようにすることが可能です (SharePoint Online PowerShell で "**Set-SPOSite -LockState**" コマンドを使用します)。 これにより、ユーザーはサイト コレクションおよびサイトにあるコンテンツとデータにアクセスできなくなります。 その後、ユーザーがサイトにアクセスできる状態にすることが適切であると判断した場合は、管理者はサイトのロックを解除できます。 この PowerShell コマンドレットの実行の詳細については、「[Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite)」を参照してください。

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>ユーザーが Office 365 にサインインできないようにする

An IT admin can also prevent a user from signing into Office 365, which would prevent the user from accessing any Office 365 online service or processing any data stored in Office 365. See [Block a former employee's access to Office 365 data](https://docs.microsoft.com/microsoft-365/admin/add-users/remove-former-employee).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>パート 2: Office 365 で生成されたインサイトに関する DSR への対応

Microsoft の Office 365 サービスのスイートには、選択されたユーザーおよび組織にインサイトを提供するオンライン サービスが含まれています。

- Delve および MyAnalytics は、個別のユーザーにインサイトを提供します
- Workplace Analytics は、組織にインサイトを提供します。

これらのサービスについては、次の各セクションで説明します。

### <a name="delve"></a>Delve

Delve では、ユーザーは自分の Office 365 プロファイルを管理でき、自分と関係している可能性のある他のユーザーやドキュメントを検出すこともできます。 ユーザーは、自分がアクセス許可を持つドキュメントのみを表示できます。 Delve に関して役立つ一連の記事については、「[Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca)」を参照してください。

#### <a name="access-and-export"></a>アクセスとエクスポート

Admins can't access or export a users' Delve data. This means that users have to access and export Delve data themselves. Most of the data types can be accessed and exported directly from Delve, but some data types are only available through other services.

##### <a name="data-available-in-the-delve-user-interface"></a>Delve ユーザー インターフェイスで使用可能なデータ

- **プロファイル データ:** これは、Azure Active Directory の組織のグローバル アドレス リストからのプロファイル情報で、ユーザーが追加したユーザー自身に関する省略可能の情報です。 Delve のプロファイル データへのアクセスまたはエクスポートを行うには、[**自分**] \> [**プロファイルの更新**] の順にクリックします。 ユーザーは、ページからコンテンツを直接コピーすることも、スクリーンショットを作成することもできます。
- **ブログ データ:** ユーザーが公開するブログ投稿です。 ユーザーが、アクセスまたはブログ データをエクスポートするには、**ここ**をクリックして \> **すべての投稿**します。 ページから直接コンテンツをコピーするか、スクリーン ショットを撮ります。
- **最近使用したユーザー データ:** これらのユーザーは、Delve が推定する、特定の時点で最もユーザーに関係のある組織内のユーザーです。 ユーザーが、「作業中の内容が見たいユーザーをクリックする」ウィンドウの**ここ** \> **すべて表示**をクリックすると、Delve が特定の時点で最もユーザーに関係のある組織内のユーザーを表示します。

##### <a name="data-available-through-an-export-link-in-delve"></a>Delve のエクスポート リンクから使用可能なデータ

- **ユーザー リスト データ:** ユーザーが Delve で表示したユーザーです。 ホームページの左のウィンドウに **ユーザー**リストが表示されます。 ユーザーは、Delve で最後に表示したユーザーのリストをエクスポートできます。
- **お気に入りデータ:** ユーザーがお気に入りとしてマークしたボードやドキュメントです。 この**お気に入り** ページは、ユーザーがお気に入りに追加したボードやドキュメントを表示します。 ユーザーは、現在のお気に入りのボードやドキュメントのリストをエクスポートできます。
- **機能設定データ:** ユーザーが Delve を使用することで得られる Delve の構成またはアクションです。 ユーザーは、機能設定のすべてのリストをエクスポートできます。

To access or export the above data, the user can click the gear icon in the upper-right corner in Delve, and then click **Feature settings** > **Export data**. Information is exported in JSON format.

##### <a name="data-thats-available-through-other-services"></a>その他のサービスから利用可能なデータ

- **よく使われるドキュメント データ:** ユーザーに関連する可能性のあるドキュメントやメールの添付ファイルです。 Delve は、これらのドキュメントおよびメール メッセージを Office 365 でのユーザーのアクティビティや連携するユーザーに基づいて編成します。 ユーザーが Delve を開くか、**ホーム**をクリックすると、Delve が、特定の時点で最も関連のあるドキュメントや添付ファイルを表示します。 ユーザーは、ドキュメントや添付ファイルを利用できる Office 365 サービス (Office.com、SharePoint Online、OneDrive for Business、または Exchange Online のような) に移動でき、実際のドキュメントや添付ファイルにアクセス、またはエクスポートできます。
- **最近使用したドキュメントやメールの添付ファイル データ:** ユーザーが一番最後に変更したドキュメントとメールの添付ファイルです。 ユーザーが、「最近使用したドキュメントとメールの添付ファイルに戻る」ウィンドウの **ここ**をクリックし、\> **すべて表示**すると、ユーザーが一番最後に変更したドキュメントとメールの添付ファイルを Delve が表示します。 ユーザーは、ドキュメントや添付ファイルを利用できる Office 365 サービス (Office.com、SharePoint Online、OneDrive for Business、または Exchange Online のような) に移動でき、実際のドキュメントや添付ファイルにアクセス、またはエクスポートできます。
- **関連のあるユーザーからのドキュメント データ:** Delve が推定する、特定の時点で最もユーザーに関係のあるドキュメントです。 ユーザーが、「関連のあるユーザーからのドキュメントを検索する」ウィンドウの**ここ** \> **すべて表示**をクリックすると、Delve が特定の時点で最もユーザーに関係のあるドキュメントを表示します。 ユーザーが実際のドキュメントにアクセス、またはエクスポートするには、ドキュメントを公開する際に使用された Office 365 サービス (Office.com、SharePoint Online、OneDrive for Business、Exchange Online など) に移動します。

#### <a name="rectify"></a>修正

ユーザーは、次に示す Delve の情報を変更できます。

- **プロファイル情報:** ユーザーは、[**自分**] \> [**プロファイルの更新**] の順にクリックして自分の情報を更新できます。 グローバル アドレス リストの組織の設定によっては、ユーザーは、名前や役職などの自身のプロファイル情報を変更できない場合があります。
- **機能の設定:** Delve の右上隅にあるギア アイコンをクリックして、[**機能の設定**] をクリックすると \> 目的の設定を変更できます。

#### <a name="restrict"></a>制限

To restrict processing in Delve for your organization, you can turn off the Office Graph. Learn more [here](https://docs.microsoft.com/sharepoint/delve-for-office-365-admins).

#### <a name="delete"></a>削除

ユーザーは、次に示す Delve の情報を削除できます。

- **プロファイル情報:** プロファイル情報を削除するには、[**自分**] \> [**プロファイルの更新**] の順にクリックし、自由形式のテキストを削除します。 グローバル アドレス リストの組織の設定によっては、ユーザーは、名前や役職などの自身のプロファイル情報を削除できない場合があります。
- **ドキュメントとメール添付ファイル:** ドキュメントまたは添付ファイルを削除するには、ドキュメントまたは添付ファイルの保存されているサービス (SharePoint Online、OneDrive for Business、Exchange Online など) に移動して、そのサービスでドキュメントを削除する必要があります。

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics provides statistics to users to help them understand how they spend their time at work. To help your users better understand the data that is presented to them in their personal dashboard and how that data is calculated, direct your users to the [MyAnalytics personal dashboard](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard-2) help topic.

#### <a name="access-and-export"></a>アクセスとエクスポート

組織で MyAnalytics を使用している場合、すべてのユーザーに関するインサイトが Microsoft により生成されます。 MyAnalytics のすべてのインサイトは、ユーザーのメールボックスのメールと会議のヘッダーに基づきます。 ユーザーは、Office 365 アカウントにサインインしている場合に [MyAnalytics ダッシュボード](https://delve.office.com)に移動し、各自の作業時間の過ごし方に関して生成されたインサイトを確認できます。 各自の情報の永続コピーが必要な場合には、MyAnalytics インサイトのスクリーンショットを作成できます。

#### <a name="rectify"></a>修正

All insights generated by MyAnalytics are derived from the user's mail and calendar items. Therefore, there is nothing to rectify other than the source email or calendar items.

#### <a name="restrict"></a>制限

To restrict processing for a specific user, you can opt them out of MyAnalytics. To see how, see [Configure MyAnalytics user settings](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-myanalytics).

#### <a name="delete"></a>削除

All mailbox content, including MyAnalytics data, is purged when a user account is "hard-deleted" from Active Directory. For more information, see the [Deleting a user](#deleting-a-user) section in this guide.

### <a name="workplace-analytics"></a>Workplace Analytics

Workplace Analytics allows organizations to augment Office 365 data with their own business data to gain insights about organizational productivity, collaboration patterns, and employee engagement. [This article](https://docs.microsoft.com/workplace-analytics/index-orig) explains the control that your organization has over the data that Workplace Analytics processes and who has access to that data.

Workplace Analytics で DSR を支援するには、次の操作を実行します。 

1. Determine whether your organization is using Workplace Analytics. For more information, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md). If your organization is not using Workplace Analytics, there is no further action.

2. 組織が Workplace Analytics を使用している場合は、Workplace Analytics 管理者の役割が割り当てられている組織内のユーザーを調べます。 また、データ主体のメールボックスに Workplace Analytics のライセンスが付与されているかどうかも確認する必要があります。 必要に応じて、次の DSR を処理する際には、Workplace Analytics 管理者が Microsoft サポートに問い合わせるようにしてください。 

#### <a name="access-and-export"></a>アクセスとエクスポート

ユーザーが作成した Workplace Analytics インサイト レポートには、組織が Workplace Analytics のライセンスを付与したユーザーの個人データが含まれていることも、含まれていないこともあります。これは、組織が Office 365 のデータを補完するために使用した情報によって決まります。 Workplace Analytics 管理者は、該当するレポートにユーザーの個人データが含まれているかどうかを確認する必要があります。 レポートにユーザーの個人情報が含まれている場合は、そのレポートのコピーをユーザーに提供するかどうかを判断する必要があります。 Workplace Analytics では、レポートのエクスポートが可能です。 

#### <a name="rectify"></a>修正

前述したように、Workplace Analytics では、ユーザーにとって有用なレポートを生成するために、Office 365 のデータとユーザーが指定した組織のデータを組み合わせて使用します。 Office 365 のデータは、ユーザーの電子メールと予定表のアクティビティに基づいているために修正できません。 ただし、レポートの生成のために Workplace Analytics にアップロードした組織のデータは修正できます。 そのためには、ソース データを修正して、そのデータをアップロードしてからレポートを再実行することで、新しい Workplace Analytics レポートを生成する必要があります。

#### <a name="restrict"></a>制限

特定のユーザーの処理を制限するには、そのユーザーの Workplace Analytics ライセンスを削除します。

#### <a name="delete"></a>削除

If a data subject would like to be removed from a Workplace Analytics report or set of reports, you can delete the report. It is your responsibility to delete users from any organizational data that you used to generate the report, and reupload the data. All data about the user is removed when a user account is "hard-deleted" from Azure Active Directory. 

データ主体の個人データを削除するには、全体管理者が次の手順を実行できます。 

1. データ主体から Workplace Analytics ライセンスを削除します。
2. Delete the Azure Active Directory (AAD) entry for the data subject. (For more information, see [Delete a user](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).)
3. Contact support and have support open a ticket for a Data Subject Rights (DSR) user-delete request. In this ticket, identify the data subject by using their User Principal Name (UPN).
4. 会社の人事システムから人事データのコピーをエクスポート (「[データのエクスポート](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data)」を参照) し、その人事データ ファイルからデータ主体の情報を削除し、編集後の人事データ ファイルを .csv 形式で Workplace Analytics にアップロードします (「[組織データをアップロードする](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data)」を参照)。

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>パート 3: システム生成ログに対する DSR への対応

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- 製品およびサービスの利用状況データ (ユーザー アクティビティ ログなど)
- ユーザー検索要求およびクエリ データ
- ユーザーまたはその他のシステムによるシステム機能および相互作用の結果として製品およびサービスによって生成されたデータ

システム生成ログのデータを制限または修正する機能はサポートされていません。 システム生成ログのデータは、Microsoft のクラウド内で実行された実際のアクションや診断データを構成しているため、そのようなデータを変更すると、アクションの履歴記録が損なわれ、詐欺やセキュリティのリスクが増大します。

### <a name="accessing-and-exporting-system-generated-logs"></a>システム生成ログのアクセスとエクスポート

テナント管理者は、組織内で、特定のユーザーの Office 365 のサービスとアプリケーションの使用に関連付けられたシステム生成ログにアクセスできる唯一のユーザーです。 エクスポート要求に対して取得されるデータは、コンピューターが読み取り可能な形式で提供され、ユーザーがデータに関連付けられているサービスを認識できるファイルで提供されます。 上記で説明したように、取得されるデータにはサービスのセキュリティまたは安定性を損なう可能性があるデータは含まれません。

システム生成ログにアクセスしてエクスポートするには:

1. Azure ポータルにサインインし、[**すべてのサービス**] を選択します。
2. フィルターにポリシーを入力し、[**ポリシー**] を選択します。
3. **[ポリシー]** ブレードで **[ユーザー プライバシー]** を選択し、**[ユーザー要求の管理]** を選択して、**[エクスポート要求の追加]** を選択します。
4. **[データ エクスポート要求]** に次のように入力します。

    - **ユーザー**。 エクスポートを要求した Azure Active Directory ユーザーの電子メール アドレスを入力します。
    - **サブスクリプション**。 リソースの使用状況の報告とサービスの請求に使用するアカウントを選択します。 これは、Azure Storage アカウントの場所でもあります。
    - **ストレージ アカウント**。 Azure Storage (Blob) の場所を選択します。 詳細については、「Microsoft Azure Storage の概要 – Blob ストレージ」の記事を参照してください。
    - **コンテナー**。 エクスポートされたユーザー プライバシー データの保存場所として新しいコンテナーを作成するか、既存のものを選択します。

5. **[作成]** を選択します。

エクスポート要求は [**保留中**] 状態になります。 レポートの状況は [**ユーザー プライバシー**] > [**概要ブレード**] で確認できます。

>[!IMPORTANT]
>個人データは複数のシステムから取得される可能性があるので、エクスポート プロセスが完了するまでに 1 か月かかる場合があります。

### <a name="notify-about-exporting-or-deleting-issues"></a>エクスポートまたは削除に関する問題を通知する

Azure portal でデータをエクスポートまたは削除中に問題が発生した場合は、Azure ポータルの [**ヘルプとサポート**] ブレードに移動し、[**サブスクリプションの管理**] > [**他のセキュリティとコンプライアンスの要求**] > [**プライバシー ブレードと GDPR 要求**] の順に新しいチケットを送信します。

>[!NOTE]
 >Azure ポータルからデータをエクスポートする場合、いくつかのアプリケーションのシステム生成データはエクスポートされません。 これらのアプリケーションのデータをエクスポートするには、「[システム生成ログ データをエクスポートする追加の手順](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data)」をご覧ください。

次に、システム生成ログのアクセスとエクスポートについての概要を示します。

- **Azure ポータルを使用したエクスポートの要求は、要求を完了するまでにどのくらいの時間がかかりますか?**: これにはいくつかの要素が影響します。 多くの場合、1 日か 2 日で完了しますが、最大 30 日間かかる場合があります。
- **出力はどの形式ですか?**: 出力はコンピューターが読み取り可能なファイル構造 (XML、CSV、JSON など) になります。
- **Azure ポータルには、誰がアクセスしてシステム生成データに対するアクセス要求を送信できますか?:** Azure ポータルには Office 365 全体管理者がアクセスできます。
- **エクスポート結果で返されるデータは?**: 結果には、Microsoft が保存するシステム生成ログが含まれます。 エクスポートされたデータは、各種 Microsoft サービス (Office 365、Azure、Dynamics など) 全体にわたります。 結果には、サービスのセキュリティまたは安定性を損なう可能性があるデータは含まれません。
- **データは、どのようにしてユーザーに返されますか?:** データは、ユーザー組織の Azure Storage の場所にエクスポートされます。このデータをユーザーに表示する方法または返す方法は、ユーザーの組織の管理者が決めます。
- **システム生成ログ データはどのようになりますか?**: 以下は例です。データは JSON 形式です:

    ```JSON
    [{
    "DateTime": "2017-04-28T12:09:29-07:00",
    "AppName": "SharePoint",
    "Action": "OpenFile",
    "IP": "154.192.13.131",
    "DevicePlatform": "Windows 1.0.1607"
    }]
    ```

Microsoft の最も頻繁に使用されるサービスの一部 (Exchange Online、SharePoint Online、Skype for Business、Yammer、Office 365 グループなど) の製品およびサービスの利用状況データは、セキュリティ/コンプライアンス センターで Office 365 監査ログを検索することで取得することもできます。 詳細については、付録 A の「[DSR 調査で Office 365 監査ログの検索ツールを使用する](#use-the-audit-log-search-tool-in-dsr-investigations)」を参照してください。このデータにアクセスするために監査ログを検索するアクセス許可を組織内の別の担当者 (法令遵守責任者など) に割り当てることができるため、監査ログの使用は重要になります。

### <a name="deleting-system-generated-logs"></a>システム生成ログの削除

To delete system-generated logs retrieved through an access request, you must remove the user from the service and permanently delete their Azure Active Directory account. For instructions about permanently delete a user, see the [Deleting a user section](#deleting-a-user) in this guide. It's important to note that permanently deleting a user account is irreversible once initiated.

ユーザーのアカウントを完全に削除すると、ユーザーのデータは、ほぼすべての Office 365 サービスのシステム生成ログから 30 日以内に削除されます。ただし、サービスのセキュリティや安定性を損なう可能性のあるデータは削除されません。 

この 30 日間の例外の 1 つは、Exchange Online でのユーザー アカウントの完全な削除に 30 日以上かかることです。 これは、Exchange Online コンテンツの重要性と不慮のデータ損失を防止するためです。 Exchange Online は、ユーザー アカウントの完全な削除から最大 60 日間、意図的にデータを保持状態にするように設計されています。 ユーザーの Exchange Online データを 30 日の期間中に完全に削除するには、そのユーザー アカウントを Azure Active Directory で完全に削除し、その後[Microsoft サポート](https://support.microsoft.com/)に連絡して、ユーザーの Exchange Online データをスケジュールされた削除プロセスとは別に手動で削除するように依頼してください。 詳細については、このガイドで前述した「[Exchange Online データの削除](#removing-exchange-online-data)」を参照してください。

Deleting a user's account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:

- Yammer: [Yammer Enterprise の GDPR データ主体の要求を管理する](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala: [Kaizala でユーザーの組織データをエクスポートまたは削除する](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>国別クラウド

次に示す国別クラウドでシステム生成ログ データをエクスポートするには、グローバル IT 管理者は次の操作を実行する必要があります。

- **Office 365 ドイツ**: 上記の手順に従ってください。
- **Office 365 US Government**: [Office 365 管理ポータルに移動](https://portal.office365.us)し、Microsoft サポートにリクエストを送信します。
- **21Vianet が運営する Office 365 (中国)**: [21Vianet が運営する Office 365 管理ポータルに移動](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage)し、[**商業**] > [**サブスクリプション**] > [**プライバシー**] > [**GDPR**] の順に移動して、必要な情報を入力します。

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>パート 4: DSR に役立つその他のリソース

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>その他の Microsoft エンタープライズ サービスについての DSR ガイド

このガイドは、Office 365 の製品、サービス、および管理ツールの使用時に DSR に対応するための個人データの検索方法と操作方法についてのみ説明しています。 その他の Microsoft エンタープライズ サービスに関する同様のガイドについては、[Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) からアクセスできます。

### <a name="microsoft-support"></a>Microsoft サポート

"Support Data" is the data you and your users provide to Microsoft if your organization or your users engage with Microsoft to receive product support related to Office 365 or other Microsoft products and services (for example, to troubleshoot unexpected product behavior). Some of this data may contain personal data. For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>Microsoft がデータ管理者である Org ID で認証された製品とサービス

このガイドのパート 1 からパート 3 では、Microsoft がお客様組織のデータ処理者の役割を務め、そのためテナント管理者が DSR 機能を利用可能な製品とサービスを扱います。 お客様組織のユーザーは、さまざまな状況で Microsoft がデータ管理者である Microsoft 製品およびサービスに組織のユーザーがサインインするために職場または学校アカウント (「Azure Active Directory ID」または「AAD」とも呼ばれる) を使用します。 そのような製品およびサービスのすべてについて、ユーザーはデータ主体要求を Microsoft に自分で直接申し込む必要があり、Microsoft はその要求を直接ユーザーに対して履行します。 ユーザーが作成したコンテンツを格納する製品やサービスでは、設計上、製品本来の機能の一部として、ユーザーはユーザーが作成したコンテンツに対するアクセス、エクスポート、修正、および削除ができます。 これが適用されるシナリオには、次のようなものがあります。

- **オプションの接続型オンライン サービス:** Microsoft 365 Apps for enterprise では、ユーザーは特定のオプションの接続型オンライン サービスを利用できます。 これらのサービスと関連するユーザー コントロールの一覧は、[こちら](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8)に記載されています。 管理者は、エンド ユーザーがこれらのサービスを使用できるようにするかどうかを決定できます。 詳細については、「[Microsoft 365 Apps for enterprise での管理者によるコントローラー サービスの管理方法](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus)」を参照してください。 これらのオプションのサービスで個人データが処理される場合は、Microsoft がこれらのサービスのデータ管理者になります。
- **ユーザーからのフィードバック:** ユーザーが Microsoft 製品およびサービスに関するフィードバックを提供するようにしている場合、フィードバックに個人情報が含まれている場合は、Microsoft がデータ管理者になります。 Microsoft は、Microsoft によって収集されるフィードバック (Microsoft の副処理者によって管理されるフィードバックを含む) に対するデータ主体要求に応えます。ただし、Microsoft がフィードバック収集処理中に個人データを含めないようにユーザーに指示した場合を除きます。 例外事項: フィードバック収集処理中に個人情報を含めないように Microsoft がユーザーに指示していた場合、Microsoft はその指示に依拠して個人データが提供されなかったと見なします。 サードパーティのフィードバック サービス プロバイダーで別のアカウントを作成したユーザーは、それらのプロバイダーに対して DSR を直接実行する必要があります。
- **職場または学校アカウントで認証された Windows:** 組織が Windows ライセンスを購入していて、組織が提供する Windows に対して職場または学校アカウントでユーザーを認証する場合、Microsoft はデータ管理者の役割を果たします。
- **ユーザーが取得した製品またはサービス:** 認証に AAD を使用する Microsoft の製品やサービス (Office アドオンまたは Microsoft Store で入手可能なアプリケーションなど) をユーザーが個人の裁量で取得できるようにしている場合は、Microsoft がデータ管理者になる可能性があります。 そのような Microsoft の製品やサービスについては、DSR を開始するために Microsoft に直接お問い合わせいただく必要があります。

>[!IMPORTANT]
>If you delete a user as enabled via Azure Active Directory, your (former) user will lose the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. Additionally, Microsoft will no longer be able to authenticate the user in connection with a DSR request for products or services for which Microsoft is a data controller. If you wish to enable a user to initiate DSRs against such services, it is important you instruct your user to do so before you delete the user's AAD account.

### <a name="personal-accounts"></a>個人アカウント

ユーザーが Microsoft アカウント (つまり、個人アカウント) を使用して Microsoft から製品およびサービスを個人的な使用のために取得していて、Microsoft がデータ管理者である場合、該当するユーザーは [Microsoft のプライバシー ダッシュボード](https://account.microsoft.com/account/privacy)から DSR 要求を開始できます。

### <a name="third-party-products"></a>サード パーティ製品

組織または個人の裁量権があるユーザーがサード パーティから製品やサービスを取得していて、認証のために Microsoft の職場または学校アカウントを使用する場合、データ主体要求は該当するサード パーティに直接請求する必要があります。

## <a name="appendix-a-preparing-for-dsr-investigations"></a>付録 A: DSR 調査の準備

Office 365 サービスを使用した DSR 調査の実施を準備する際には、次の推奨事項について考慮してください。

- セキュリティ/コンプライアンス センターの DSR 電子情報開示ケース ツールを使用して DSR 調査を管理する
- コンテンツ検索の範囲を制限するためにコンプライアンスの境界を使用する
- DSR 調査で監査ログの検索ツールを使用する

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>DSR ケース ツールを使用して DSR 調査を管理する

We recommend that you use the DSR case tool in Security & Compliance Center to manage DSR investigations. By using the DSR case tool, you can:

- DSR 調査ごとに個別のケースを作成する。

- 組み込みの検索クエリを使用して、特定のデータ主体に関連するすべてのコンテンツについて検索する。 ケースを作成して検索を開始すると、次に示すコンテンツの場所が検索されます。

   - 組織内のすべてのメールボックス (すべての Microsoft Teams と Microsoft 365 グループに関連付けられているメールボックスを含む)
   - 組織内のすべての SharePoint サイトおよび OneDrive for Business アカウント
   - 組織内のすべての Microsoft Teams サイトと Microsoft 365 グループ サイト
   - Exchange Online のすべてのパブリック フォルダー

- 既定の検索クエリを修正して、検索結果を絞り込むために検索を再実行する。

- ケースのメンバーとして人員を追加して、ケースにアクセスできる担当者を制御する。ケースにはメンバーのみがアクセス可能です。また、そのメンバーのケースのみがセキュリティ/コンプライアンス センターの DSR ケース ページのケースのリストで自分のケースを表示できるようになります。 さらに、同一のケースのメンバーごとに異なるアクセス許可を割り当てることも可能です。 たとえば、一部のメンバーにはケースとコンテンツ検索の結果の表示のみを許可し、別のメンバーには検索の作成と検索結果のエクスポートを許可することができます。

- DSR エクスポート要求への対応で検索結果をエクスポートするためのエクスポート ジョブを作成する。 コンテンツ検索によって返されるすべてのコンテンツをエクスポートできます。 データ主体に関連する他の Office 365 データもエクスポートされます。

- DSR エクスポート要求への対応で検索結果をエクスポートするためのエクスポート ジョブを作成する。 コンテンツ検索によって返されるすべてのコンテンツをエクスポートできます。 Office ローミングサービス用にシステム生成ログをエクスポートすることもできます。

- DSR 調査プロセスが完了したときにケースを削除する。 これにより、そのケースに関連付けられたすべてのコンテンツ検索とエクスポート ジョブを削除します。

DSR ケースの使用を開始するには、「[セキュリティ/コンプライアンス センターで DSR ケース ツールを使用して GDBR データ主体要求を管理する](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool)」を参照してください。

>[!IMPORTANT]
>An eDiscovery Administrator can view and manage all DSR cases in your organization. For more information about the different roles related to eDiscovery, see [Assign eDiscovery permissions to potential case members](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>コンテンツ検索の範囲を制限するためにコンプライアンスの境界を使用する

Compliance Boundaries are implemented by using the search permissions filtering functionality in the Security & Compliance Center. Compliance Boundaries create logical search boundaries within an organization that control/limit which content locations (for example Exchange Online mailboxes and SharePoint Online sites) that an IT admin or compliance officer can search. Compliance Boundaries are useful for multi-national organizations that need to respect geographical boundaries, governmental organizations that need to separate different agencies, and business organizations that segregated into business unit or department. For all these scenarios, Compliance Boundaries can be used in DSR investigations to limit which mailboxes and sites can be searched by people involved in the investigation.

コンプライアンスの境界は、電子情報開示のケースと併用することで、調査で検索できるコンテンツの場所を特定の機関内や事業単位内に制限することができます。

次に、DSR 調査用にコンプライアンスの境界を (電子情報開示のケースと共に) 実装する方法の概要を示します。

1. コンプライアンスの境界として指定する組織内の機関を決定します。

2. Determine which user object attribute in Azure Active Directory will be used to define the compliance boundary. For example, you might choose the Country, CountryCode, or Department attribute, so that members of the admin role group that you create in the next step can only search the content locations of the users that have a specific value for that attribute. This is how you limit who can search for content in a specific agency.

>[!NOTE]
>現時点では、OneDrive for Business アカウントに属性を同期するには、OneDrive for Business に対する追加の手順を実行して、Microsoft サポートにリクエストを申し込む必要があります。

4. Create an admin role group in the Security & Compliance Center for each compliance boundary. We recommend that you create these role groups by copying the built-in eDiscovery Manager role group and then removing any roles as necessary.

5. 特定の役割グループごとに、電子情報開示マネージャーとしてメンバーを追加します。 メンバーは、DSR の調査と対応の責任者になり、通常は IT 管理者、データ プライバシー担当者、コンプライアンス マネージャー、および人事担当者で構成されます。

6. コンプライアンスの境界ごとに検索権限フィルター作成して、対応する管理者役割グループのメンバーが、その機関/コンプライアンスの境界の範囲内でのみユーザーのメールボックスおよびサイトを検索できるようにします。 検索権限フィルターにより、対応する役割グループのメンバーは、機関/コンプライアンスの境界に対応するユーザー オブジェクトの属性値を持つコンテンツの場所のみを検索できるようになります。

詳細な手順については、「[Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries)」を参照してください。

### <a name="use-the-audit-log-search-tool-in-dsr-investigations"></a>DSR 調査で監査ログの検索ツールを使用する

IT admins can use the audit log search tool in the Security & Compliance Center to identity documents, files, and other Office 365 resources that users have created, accessed, changed, or deleted. Searching for this kind activity can be useful in DSR investigations. For example, in SharePoint Online and OneDrive for Business, auditing events are logged when users perform these activities:

- ファイルにアクセスした
- ファイルを変更した
- ファイルを移動した
- ファイルをアップロードまたはダウンロードした

特定のアクティビティ、アクティビティの種類、特定のユーザーが実行したアクティビティ、およびその他の検索基準で監査ログの検索が可能です。 SharePoint Online および OneDrive for Business のアクティビティに加えて、Flow、Power BI、および Microsoft Teams でのアクティビティについても検索できます。 監査レコードは 90 日間保持されます。 そのため、90 日より以前に発生したユーザーのアクティビティは検索できません。 監査対象のアクティビティの完全なリストと監査ログの検索方法については、「[セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。

>[!TIP]
>上記の 90 日間の制限を回避して、組織の監査レコードの実行履歴を維持するには、定期的なスケジュールで (たとえば、30 日ごとに) すべてのアクティビティをエクスポートして、組織の監査レコードの継続的な記録を保持するようにします。

## <a name="appendix-b-change-log"></a>付録 B: 変更ログ

次の表に、2018 年 5 月 25 日の初回発行以降の Office 365 DSR ガイドの変更点を示します。

|日付  |セクション/アプリ |変更  |
|:---------|:---------|:---------|
|9/18/2018 | [Whiteboard](#whiteboard) |Whiteboard Preview is no longer in preview and has been released to general availability. Therefore, the section on Whiteboard Preview was renamed to "Whiteboard for PC, Surface Hub, and other platforms"; procedures to access, export, and delete data were removed from this section and replaced with a link to the Whiteboard support article.|
|2018 年 11 月 8 日 | [Workplace Analytics](#workplace-analytics) |Workplace Analytics からデータ主体を削除し、Workplace Analytics レポートからデータ主体の情報を削除する方法を示す具体的な手順を削除セクションに追加しました。|
|2018 年 11 月 12 日| すべて| 壊れたブックマークと外部トピックへのリンクを修正しました。|
|2019 年 1 月 9 日| StaffHub |[削除] セクションで、ユーザー アカウントが完全に削除された場合の動作の説明を更新しました。|
|2019/5/8| [Publisher](#publisher)|Publisher の DSR への対応に関する追加のコンテンツです。|
|2019/7/11| [MyAnalytics](#myanalytics)|すべてのユーザーが MyAnalytics アプリでデータを表示できるようになったため、管理者がセキュリティ/コンプライアンス センターの DSR ケース ツールを使用して MyAnalytics データをエクスポートする機能は削除されました。 |
|2019 年 11 月 6 日|[教育](#education)|PowerShell スクリプトを使用して特定の学生のクラスのリストを取得し、そのデータをエクスポートまたは削除する方法についての新しいトピックにリンクされています。|
|2020/1/28| すべて | ドキュメントから StaffHub を削除し、StaffHub は廃止されました。 |
||||
