---
title: 電子情報開示のキーワード クエリと検索条件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365の電子情報開示検索ツールを使用して検索できる電子メールとドキュメントのプロパティについて説明します。
ms.openlocfilehash: 09c939f7d92bf06a9eab89d8ac45fec78bd424a8
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64936645"
---
# <a name="keyword-queries-and-search-conditions-for-ediscovery"></a>電子情報開示のキーワード クエリと検索条件

この記事では、Exchange Onlineの電子メール アイテムやMicrosoft Teamsチャット会話で検索できる電子メールとドキュメントのプロパティ、および Microsoft Purview コンプライアンス ポータルの電子情報開示検索ツールを使用してSharePointサイトとOneDrive for Business サイトに保存されているドキュメントについて説明します。 これには、コンテンツ検索、Microsoft Purview 電子情報開示 (Standard)、Microsoft Purview 電子情報開示 (プレミアム) が含まれます (電子情報開示での電子情報開示検索 (プレミアム) は *コレクション* と呼ばれます)。 また、セキュリティ/コンプライアンス センター PowerShell の **\*-ComplianceSearch** コマンドレットを使用してこれらのプロパティを検索することもできます。 この記事では、次についても説明します。

- ブール検索演算子、検索条件、およびその他の検索クエリ技法を使用して、検索結果を絞り込む。
- SharePoint および OneDrive for Business で機密情報の種類およびカスタムの機密情報の種類を検索する。
- 組織外のユーザーと共有されているサイトのコンテンツを検索する

さまざまな電子情報開示検索を作成する方法の詳細な手順については、次を参照してください。

- [コンテンツ検索](content-search.md)
- [電子情報開示でコンテンツを検索する (Standard)](search-for-content-in-core-ediscovery.md)
- [電子情報開示で下書きコレクションを作成する (プレミアム)](create-draft-collection.md)

> [!NOTE]
> コンプライアンス ポータルでの電子情報開示検索と、Security & Compliance Center PowerShell の対応する **\*-ComplianceSearch** コマンドレットでは、キーワード クエリ言語 (KQL) を使用します。 詳細については、「[キーワード クエリ言語 (KQL) 構文のリファレンス](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)」を参照してください。

## <a name="searchable-email-properties"></a>検索可能なメール プロパティ

次の表に、コンプライアンス ポータルの電子情報開示検索ツールを使用するか、 **New-ComplianceSearch** または **Set-ComplianceSearch** コマンドレットを使用して検索できる電子メール メッセージのプロパティを示します。 表には、各プロパティの  _property:value_ 構文の例、およびその例で返される検索結果の説明が含まれています。 これらの  `property:value` ペアは、電子情報開示検索のキーワード ボックスに入力できます。

> [!NOTE]
> メール プロパティを検索するときは、指定されたプロパティが空のアイテムを検索することはできません。 たとえば、件名が空のメール メッセージを検索するときに **subject:""** という *プロパティと値* の組み合わせを使用した場合、結果は返されません。 これは、サイトと連絡先のプロパティの検索時にも当てはまります。

|プロパティ|プロパティの説明|例|例で返される検索結果|
|---|---|---|---|
|AttachmentNames|メール メッセージに添付されているファイルの名前。|`attachmentnames:annualreport.ppt` <p> `attachmentnames:annual*` <br/> `attachmentnames:.pptx`|annualreport.ppt という名前の添付ファイルのあるメッセージ。 2 番目の例では、ワイルドカード文字 ( * ) を使用して、添付ファイルのファイル名に "annual" という単語を含むメッセージを返します。 3　番目の例は、ファイルの拡張子が pptx のすべての添付ファイルを返します。|
|Bcc|メール メッセージの Bcc フィールド。<sup>1</sup>|`bcc:pilarp@contoso.com` <p> `bcc:pilarp` <p> `bcc:"Pilar Pinilla"`|どの例も Bcc フィールドに「Pilar Pinilla」が含まれているメッセージを返します。|
|カテゴリ|検索するカテゴリ。 カテゴリは、ユーザーが Outlook または Outlook on the web (旧称: Outlook Web App) を使用して定義できます。 値は次のいずれかです。 <ul><li>青<li>green<li>orange<li>purple<li>red<li>yellow</li></ul>|`category:"Red Category"`|元のメールボックスで「red」のカテゴリが割り当てられているメッセージ。|
|Cc|メール メッセージの Cc フィールド。<sup>1</sup>|`cc:pilarp@contoso.com` <p> `cc:"Pilar Pinilla"`|どちらの例も、Cc フィールドに "Pilar Pinilla" が指定されたメッセージ。|
|Folderid|特定のメールボックス フォルダーのフォルダー ID (GUID)。 このプロパティを使う場合は、必ず指定したフォルダーが存在するメールボックスを検索するようにします。 指定したフォルダーのみが検索されます。 フォルダー内のサブフォルダーは検索されません。 サブフォルダーを検索するには、検索するサブフォルダーの Folderid プロパティを使う必要があります。 <p> Folderid プロパティを検索し、スクリプトを使用して特定のメールボックスのフォルダー ID を取得する方法の詳細については、「 [ターゲット コレクションのコンテンツ検索を使用する」を](use-content-search-for-targeted-collections.md)参照してください。|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000` <p> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|最初の例では、指定したメールボックス フォルダー内のすべてのアイテムが返されます。 2 番目の例では、指定したメールボックス フォルダー内で garthf@contoso.com によって送信または受信されたすべてのアイテムが返されます。|
|送信元|メール メッセージの送信者。<sup>1</sup>|`from:pilarp@contoso.com` <p> `from:contoso.com`|指定されたユーザーによって送信された、または指定されたドメインから送信されたメッセージ。|
|HasAttachment|メッセージに添付ファイルがあるかどうかを示します。 値 **true** または **false** を使用します。|`from:pilar@contoso.com AND hasattachment:true`|指定したユーザーによって送信された添付ファイルを含むメッセージ。|
|Importance|送信者がメッセージを送信するときに指定できる電子メール メッセージの重要度。既定では、送信者が重要度を **high** または **low** に設定していない限り、メッセージは普通の重要度で送信されます。|`importance:high` <p> `importance:medium` <p> `importance:low`|高重要度、中重要度、または低重要度とマークされているメッセージ。|
|IsRead|メッセージが既読か未読かを示します。 値 **true** または **false** を使用します。|`isread:true` <p> `isread:false`|最初の例では、IsRead プロパティを **True** に設定されているメッセージが返されます。 2 番目の例では、IsRead プロパティが **False** に設定されているメッセージが返されます。|
|ItemClass|このプロパティは、組織が Office 365 にインポートした特定のサード パーティのデータ型を検索するときに使います。 このプロパティでは、次の構文を使います:  `itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso` <p> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|最初の例では、Subject プロパティに "contoso" という単語が含まれる Facebook アイテムが返されます。 2 番目の例では、Ann Beebe によって投稿された、"Northwind Traders" というキーワード語句を含む Twitter アイテムが返されます。 <p> ItemClass プロパティのサード パーティのデータ型に使用する値の完全な一覧については、「[コンテンツ検索を使用して、Office 365にインポートされたサード パーティのデータを検索する」を](use-content-search-to-search-third-party-data-that-was-imported.md)参照してください。|
|Kind|検索するメール メッセージの種類。 可能な値: <p>  contacts <p>  docs <p>  email <p>  externaldata <p>  faxes <p>  im <p>  journals <p>  meetings <p>  microsoftteams (Microsoft Teams のチャット、会議、通話のアイテムが返されます) <p>  notes <p>  posts <p>  rssfeeds <p>  tasks <p>  voicemail|`kind:email` <p> `kind:email OR kind:im OR kind:voicemail` <p> `kind:externaldata`|最初の例では、検索条件に一致するメール メッセージが返されます。 2 番目の例では、検索条件に一致するメール メッセージ、インスタント メッセージ、会話 (Skype for Business の会話と Microsoft Teams のチャットを含みます) ボイス メッセージが返されます。 3 番目の例は、サード パーティのデータ ソース (Twitter、Facebook、Cisco Jabber など) から Office 365 のメールボックスにインポートされたアイテムのうち、検索条件に一致して、返されたアイテムです。 詳細については、「[Office 365 でサードパーティのデータをアーカイブする](https://www.microsoft.com/?ref=go)」を参照してください。|
|Participants|メール メッセージのすべての送受信者フィールド。 すなわち、[差出人]、[宛先]、[Cc]、[Bcc] の各フィールドです。<sup>1</sup>|`participants:garthf@contoso.com` <p> `participants:contoso.com`|garthf@contoso.com が送信元または送信先のメッセージ。2 番目の例は、contoso.com ドメイン内のユーザーが送信元または送信先のすべてのメッセージを返します。|
|Received|電子メール メッセージが受信者によって受信された日付。|`received:2021-04-15` <p> `received>=2021-01-01 AND received<=2021-03-31`|2021 年 4 月 15 日に受信したメッセージ。 2 番目の例では、2021 年 1 月 1 日から 2021 年 3 月 31 日の間に受信したすべてのメッセージが返されます。|
|Recipients|メール メッセージのすべての受信者フィールド。 すなわち、[宛先]、[Cc]、[Bcc] の各フィールドです。<sup>1</sup>|`recipients:garthf@contoso.com` <p> `recipients:contoso.com`|garthf@contoso.com に送信されたメッセージ。2 番目の例では、contoso.com ドメイン内のすべての受信者に送信されたメッセージを返します。|
|Sent|送信者によって電子メール メッセージが送信された日付。|`sent:2021-07-01` <p> `sent>=2021-06-01 AND sent<=2021-07-01`|指定された日付に送信された、または指定された日付範囲内に送信されたメッセージ。|
|Size|アイテムのサイズ (バイト数)。|`size>26214400` <p> `size:1..1048567`|25 MB を超えるメッセージ。2 番目の例は 1 ～ 1,048,567 バイト (1 MB) のサイズのメッセージを返します。|
|件名|電子メール メッセージの件名行に含まれるテキスト。 <p> **注:** クエリで Subject プロパティを使用すると、検索するテキストが件名に含まれているすべてのメッセージが返されます。 つまり、完全一致のメッセージのみがクエリで返されるわけではありません。 たとえば、 `subject:"Quarterly Financials"` を検索した場合の結果には、件名が "Quarterly Financials 2018" のメッセージが含まれることになります。|`subject:"Quarterly Financials"` <p> `subject:northwind`|件名行のテキストのいずれかの箇所に "Quarterly Financials" を含むメッセージ。 2 番目の例では、件名行に「northwind」の語が含まれているすべてのメッセージを返します。|
|To|メール メッセージの To フィールド。<sup>1</sup>|`to:annb@contoso.com` <p> `to:annb ` <br/> `to:"Ann Beebe"`|いずれの例も、To: 行に "Ann Beebe" が指定されているメッセージを返します。|

> [!NOTE]
> <sup>1</sup> recipient プロパティの値には、メール アドレス (*ユーザー プリンシパル名* または UPN とも呼ばれます)、表示名、またはエイリアスを使用してユーザーを指定できます。 たとえば、ユーザー Ann Beebe を指定するために、annb@contoso.com、annb、または "Ann Beebe" を使用できます。

### <a name="recipient-expansion"></a>受信者の展開

受信者のいずれかのプロパティ (From、To、Cc、Bcc、Participants、Recipients) を検索すると、Office 365 では、Azure Active Directory (Azure AD) でユーザーを検索して、各ユーザーの ID の拡張を試みます。  ユーザーが Azure Active Directory で見つかった場合はクエリが拡張され、そのユーザーのメール アドレス (または UPN)、エイリアス、表示名、LegacyExchangeDN が含まれるようになります。 たとえば、`participants:ronnie@contoso.com` などのクエリは、`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"` に拡張されます。

受信者の拡張を防ぐには、メール アドレスの末尾にワイルドカード文字 (アスタリスク) を追加し、たとえば、短縮したドメイン名を使用します。 `participants:"ronnie@contoso*"` 必ず、二重引用符でメール アドレスを囲みます。

ただし、検索クエリで受信者の拡張を防ぐと、関連するアイテムが検索結果に返されない可能性があります。 Exchange のメール メッセージは、受信者フィールドに異なるテキスト形式で保存できます。 受信者の拡張は、異なるテキスト形式を含む可能性のあるメッセージを返して、この事実を軽減することを目的としています。 受信者の拡張を防ぐと、検索クエリが調査に関連する可能性のあるすべてのアイテムを返さない結果になる可能性があります。

> [!NOTE]
> 受信者の展開が原因で検索クエリによって返されるアイテムを確認または減らす必要がある場合は、電子情報開示 (プレミアム) の使用を検討してください。 受信者の拡張を利用してメッセージを検索し、それをレビュー セットに追加し、レビュー セットのクエリまたはフィルターを使用して結果を確認または絞り込みます。 詳細については、「[ケース用にデータを収集する](collecting-data-for-ediscovery.md)」および「[レビュー セットのデータのクエリ](review-set-search.md)」を参照してください。

## <a name="searchable-site-properties"></a>検索可能なサイト プロパティ

次の表に、Microsoft Purview コンプライアンス ポータルの電子情報開示検索ツールを使用するか、**New-ComplianceSearch** または **Set-ComplianceSearch** コマンドレットを使用して検索できるSharePointプロパティとOneDrive for Businessプロパティの一部を示します。 表には、各プロパティの  _property:value_ 構文の例、およびその例で返される検索結果の説明が含まれています。

検索可能な SharePoint プロパティの完全な一覧については、「[クロールされたプロパティと管理プロパティの概要](/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。 [**クエリ可能**] 列で **[はい]** と示されているプロパティが検索可能です。

|プロパティ|プロパティの説明|例|例で返される検索結果|
|---|---|---|---|
|Author|Office ドキュメントの作成者フィールド。ドキュメントがコピーされた場合でもこのフィールは保持されます。 たとえば、ユーザーがドキュメントを作成して別のユーザーにメールで送信し、そのユーザーがそのドキュメントを SharePoint にアップロードした場合、そのドキュメントでは引き続き元の作成者が保持されます。 このプロパティには、必ずユーザーの表示名を使用してください。|`author:"Garth Fort"`|Garth Fort によって作成されたすべてのドキュメント。|
|ContentType|Item、Document、Video など、アイテムの SharePoint コンテンツ タイプ。|`contenttype:document`|すべてのドキュメントが返されます。|
|Created|アイテムが作成された日付。|`created>=2021-06-01`|2021 年 6 月 1 日以降に作成されたすべてのアイテム。|
|CreatedBy|アイテムを作成またはアップロードした人。 このプロパティには、必ずユーザーの表示名を使用してください。|`createdby:"Garth Fort"`|Garth Fort によって作成またはアップロードされたすべてのアイテム。|
|DetectedLanguage|アイテムの言語。|`detectedlanguage:english`|すべての英語のアイテム。|
|DocumentLink|SharePoint または OneDrive for Business サイトの特定のフォルダーのパス (URL)。 このプロパティを使う場合は、必ず指定したフォルダーが存在するサイトを検索するようにします。 <p> documentlink プロパティに指定したフォルダーのサブフォルダーにあるアイテムを返すには、指定したフォルダーの URL に /\* を追加する必要があります。たとえば、 `documentlink: "https://contoso.sharepoint.com/Shared Documents/*"` <p> <br/>documentlink プロパティを検索し、スクリプトを使用して特定のサイト上のフォルダーのドキュメントリンク URL を取得する方法の詳細については、「 [ターゲット コレクションのコンテンツ検索を使用する](use-content-search-for-targeted-collections.md)」を参照してください。|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"` <p> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|最初の例では、指定した OneDrive for Business フォルダー内のすべてのアイテムが返されます。 2 番目の例では、指定したサイト フォルダー (およびすべてのサブフォルダー) に存在するドキュメントで、ファイル名に "confidential" という単語が含まれるものが返されます。|
|FileExtension|ファイルの拡張子。例: docx、one、pptx、xlsx など。|`fileextension:xlsx`|すべての Excel ファイル (Excel 2007 以降)|
|FileName|ファイルの名前。|`filename:"marketing plan"` <p> `filename:estimate`|最初の例では、タイトルに "marketing plan" と完全一致する語句が含まれるファイルが返されます。2 番目の例では、ファイル名に "estimate" という単語を含むファイルが返されます。|
|LastModifiedTime|アイテムが最後に変更された日付。|`lastmodifiedtime>=2021-05-01` <p> `lastmodifiedtime>=2021-05-01 AND lastmodifiedtime<=2021-06-01`|最初の例では、2021 年 5 月 1 日以降に変更された項目を返します。 2 番目の例では、2021 年 5 月 1 日から 2021 年 6 月 1 日の間に変更された項目が返されます。|
|ModifiedBy|アイテムを最後に変更した人。 このプロパティには、必ずユーザーの表示名を使用してください。|`modifiedby:"Garth Fort"`|Garth Fort によって最後に変更されたすべてのアイテム。|
|Path|SharePoint または OneDrive for Business サイトの特定のサイトのパス (URL)。 <p> 指定したサイトからのみアイテムを返すには、URL の末尾に末尾 `/` を追加する必要があります。たとえば、 `path: "https://contoso.sharepoint.com/sites/international/"` <p> path プロパティで指定したサイト内のフォルダーにあるアイテムを返すには、URL の末尾に追加 `/*` する必要があります。たとえば、  `path: "https://contoso.sharepoint.com/Shared Documents/*"` <p> **メモ：** このプロパティを`Path`使用してOneDrive場所を検索しても、.png、.tiff、.wav ファイルなどのメディア ファイルは検索結果に返されません。 OneDrive フォルダー内のメディア ファイルを検索するには、検索クエリで別のサイト プロパティを使用します。 <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"` <p> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|最初の例では、指定した OneDrive for Business サイト内のすべてのアイテムが返されます。 2 番目の例では、指定したサイト フォルダー (およびサイト内のフォルダー) に存在するドキュメントで、ファイル名に "confidential" という単語が含まれるものが返されます。|
|SharedWithUsersOWSUser|指定したユーザーと共有されているドキュメントで、そのユーザーの OneDrive for Business サイトの [**自分と共有**] ページに表示されるドキュメント。 これらは、組織内の他のユーザーによって指定したユーザーと明示的に共有されているドキュメントです。 SharedWithUsersOWSUser プロパティを使う検索クエリと一致するドキュメントをエクスポートすると、ドキュメントは、指定したユーザーとドキュメントを共有しているユーザーの元のコンテンツの場所からエクスポートされます。 詳細については、「[組織内で共有されているサイト コンテンツの検索](#searching-for-site-content-shared-within-your-organization)」を参照してください。|`sharedwithusersowsuser:garthf` <p> `sharedwithusersowsuser:"garthf@contoso.com"`|どちらの例でも、Garth Fort と明示的に共有されていて、Garth Fort の OneDrive for Business アカウントの [**自分と共有**] ページに表示されるすべての内部ドキュメントが返されます。|
|Site|組織内のサイトかサイトのグループの URL。|`site:"https://contoso-my.sharepoint.com"` <p> `site:"https://contoso.sharepoint.com/sites/teams"`|最初の例では、組織内のすべてのユーザー向けの OneDrive for Business のサイトからアイテムが返されます。 2 番目の例では、すべてのチーム サイトからアイテムが返されます。|
|Size|アイテムのサイズ (バイト数)。|`size>=1` <p> `size:1..10000`|最初の例では、1 バイトより大きいアイテムが返されます。2 番目の例では、1 ～ 10,000 バイトのサイズのメッセージが返されます。|
|Title|ドキュメントのタイトル。 Title プロパティは、Microsoft Office ドキュメントに 指定されているメタデータです。 ドキュメントのファイル名とは異なります。|`title:"communication plan"`|Office ドキュメントの Title メタデータ プロパティに "communication plan" という語句が含まれるすべてのドキュメント。|

## <a name="searchable-contact-properties"></a>検索可能な連絡先プロパティ

次の表に、インデックスが作成され、電子情報開示検索ツールを使用して検索できる連絡先プロパティの一覧を示します。 これらは、ユーザーのメールボックスの個人用アドレス帳内にある連絡先 (個人の連絡先とも呼ばれます) に対してユーザーが構成できるプロパティです。 連絡先を検索するには、検索対象のメールボックスを選び、キーワード クエリで 1 つまたは複数の連絡先プロパティを使います。

> [!TIP]
> スペースまたは特殊文字を含む値を検索するには、二重引用符 ("  ") で語句を囲みます。例: `businessaddress:"123 Main Street"`

|プロパティ|プロパティの説明|
|---|---|
|BusinessAddress|**会社住所** プロパティの住所。 このプロパティは連絡先のプロパティ ページでは **勤務先** 住所とも呼ばれます。|
|BusinessPhone|
            **勤務先電話** 番号プロパティの電話番号。|
|CompanyName|
            **会社** プロパティの名前。|
|Department|
            **部門** プロパティの名前。|
|DisplayName|連絡先の表示名。 これは、連絡先の **氏名** プロパティの名前です。|
|EmailAddress|連絡先のメール アドレス プロパティのアドレス。 1 つの連絡先に複数のメール アドレスを追加できます。 このプロパティを使うと、連絡先のメール アドレスのいずれかに一致する連絡先が返されます。|
|FileAs|**表題** プロパティ。 このプロパティは、ユーザーの連絡先一覧での連絡先の表示方法を指定するために使います。 たとえば、 *FirstName,LastName*  または  *LastName,FirstName* と連絡先を表示できます。|
|GivenName|
            **名** プロパティの名前。|
|HomeAddress|いずれかの **自宅** 住所プロパティの住所。|
|HomePhone|いずれかの **自宅** 電話番号プロパティの電話番号。|
|IMAddress|IM アドレス プロパティ。通常は、インスタント メッセージングに使うメール アドレスです。|
|MiddleName|
            **ミドル** ネーム プロパティの名前。|
|MobilePhone|
            **携帯** 電話番号プロパティの電話番号。|
|Nickname|
            **ニックネーム** プロパティの名前。|
|OfficeLocation|
            **オフィス** プロパティまたは **オフィスの場所** プロパティの値。|
|OtherAddress|
            **その他** 住所プロパティの値。|
|Surname|
            **姓** プロパティの名前。|
|Title|**役職** プロパティの名前。|

## <a name="searchable-sensitive-data-types"></a>検索可能な機密情報の種類

コンプライアンス ポータルの電子情報開示検索ツールを使用すると、SharePoint サイトやOneDrive for Business サイトのドキュメントに格納されている機密データ (クレジット カード番号や社会保障番号など) を検索できます。 これを行うには、`SensitiveType`プロパティと機密情報の名前 (または ID) をキーワード クエリで使います。 たとえば、クエリ `SensitiveType:"Credit Card Number"` は、クレジット カード番号が含まれているドキュメントを返します。 クエリ`SensitiveType:"U.S. Social Security Number (SSN)"` は米国の社会保障番号を含むドキュメントを返します。

検索できる機密情報の種類の一覧を表示するには、コンプライアンス ポータルで **データ分類の** \> **機密情報の種類** に移動します。 または、セキュリティ/コンプライアンス センター PowerShell で **Get-DlpSensitiveInformationType** コマンドレットを使用する方法でも機密情報の種類の一覧を表示できます。

`SensitiveType` プロパティを使用したクエリの作成の詳細については、「[サイトに保存されている機密データを検索するクエリを作成する](form-a-query-to-find-sensitive-data-stored-on-sites.md)」を参照してください。 

### <a name="limitations-for-searching-sensitive-data-types"></a>機密データ型を検索する場合の制限事項

- カスタムの機密情報の種類を検索するには、`SensitiveType`プロパティで機密情報の種類の ID を指定する必要があります。 前のセクションの組み込み機密情報の種類の例で示すように、カスタムの機密情報の種類の名前を使用すると、結果は返されません。 コンプライアンス センターの [**機密情報の種類**] ページの [**発行元**] 列 (または PowerShell の **発行元** プロパティ) を使って、組み込みの機密情報の種類とカスタムの機密情報の種類を区別できます。 組み込みの機密データ型は **発行元** プロパティの値`Microsoft Corporation`を持っています。

  組織のカスタムの機密データの種類の名前と ID を表示するには、セキュリティ/コンプライアンス センターの PowerShell で次のコマンドを実行します。

  ```powershell
  Get-DlpSensitiveInformationType | Where-Object {$_.Publisher -ne "Microsoft Corporation"} | FT Name,Id
  ```

  次に、`SensitiveType` 検索プロパティで ID を使用して、カスタムの機密データ型を含むドキュメントを返します。例えば `SensitiveType:7e13277e-6b04-3b68-94ed-1aeb9d47de37`

- 機密性のある情報の種類と `SensitiveType` 検索プロパティは、Exchange Online メールボックスに保管されている機密性の高いデータの検索には使用できません。 これには、1 対 1 のチャット メッセージ、1 対 N のグループ チャット メッセージ、Microsoft Teamsのチーム チャネル会話が含まれます。このコンテンツはすべてメールボックスに格納されるためです。 ただし、データ損失防止 (DLP) ポリシーを使用して、転送中の機密性の高いメール データを保護できます。 詳細については、「 [データ損失防止の詳細」](dlp-learn-about-dlp.md) と「 [個人データの検索と検索」](/compliance/regulatory/gdpr)を参照してください。

## <a name="search-operators"></a>検索演算子

**AND**、**OR**、**NOT** などのブール演算子は、検索クエリで特定の語を含めたり除去したりすることにより、検索をより詳細に定義するために役立ちます。 プロパティ演算子 (`>=` や `..`など)、引用符、かっこ、ワイルドカードを使用するといった他の技法も、検索クエリを調整するのに役立ちます。 検索結果を絞り込んだり、その範囲を広げたりするために使用できる演算子を次の表に示します。

|演算子|用途|説明|
|---|---|---|
|AND|keyword1 AND keyword2|指定されたすべてのキーワードまたは  `property:value` 式が含まれる項目を返します。 たとえば、 `from:"Ann Beebe" AND subject:northwind` は、Ann Beebe によって送信され、件名の行に "northwind" という単語が含まれるすべてのメッセージを返します。 <sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|Returns items that contain  *either*  `keyword2` or  `keyword3` *and*  that also contain  `keyword1`. Therefore, this example is equivalent to the query  `(keyword2 OR keyword3) AND keyword1`.  <p> クエリ `keyword1 + keyword2` ( **+** 記号の後にスペースがあります) は、**AND** 演算子を使用する場合と同じではありません。 This query would be equivalent to  `"keyword1 + keyword2"` and return items with the exact phase  `"keyword1 + keyword2"`.|
|OR|keyword1 OR keyword2|指定された 1 つ以上のキーワードや  `property:value` 式が含まれる項目を返します。 <sup>2</sup>|
|NOT|keyword1 NOT keyword2 <p> NOT from:"Ann Beebe" <p> NOT kind:im|キーワードまたは  `property:value` 式で指定されたアイテムを除外します。 2 番目の例では、Ann Beebe によって送信されたメッセージを除外します。 3 番目の例では、[会話の履歴] メールボックス フォルダーに保存されている、Skype for Business の会話などのインスタント メッセージの会話をすべて除外します。 <sup>2</sup>|
|-|keyword1 -keyword2|
            **NOT** 演算子と同じです。 このクエリは、 `keyword1` が含まれている項目のうち、`keyword2` が含まれていない項目を返します。|
|NEAR|keyword1 NEAR(n) keyword2|互いに近くにある単語を含むアイテムを返します。n は、何単語離れているかを示します。 たとえば、`best NEAR(5) worst` は、"best" の近くの 5 つの単語の中に "worst" という単語があるアイテムを返します。 数値が指定されていない場合、既定の間隔は 8 単語です。 <sup>2</sup>|
|:|property:value|`property:value` 構文内のコロン (:) は、検索するプロパティに含まれる値を指定します。 たとえば、 `recipients:garthf@contoso.com` は、garthf@contoso.com に送信されたすべてのメッセージを返します。|
|=|property=value|**:** 演算子と同じです。|
|\<|property\<value|検索対象のプロパティが指定の値より小さいことを意味します。<sup>1</sup>|
|\>|property\>value|検索対象のプロパティが指定の値より大きいことを意味します。<sup>1</sup>|
|\<=|property\<=value|検索対象のプロパティが特定の値以下であることを意味します。<sup>1</sup>|
|\>=|property\>=value|検索対象のプロパティが特定の値以上であることを意味します。<sup>1</sup>|
|..|property:value1..value2|検索対象のプロパティが value1 以上で value2 以下であることを意味します。<sup>1</sup>|
|"  "|"fair value" <p> subject:"Quarterly Financials"|キーワード クエリ ([**キーワード**] ボックスにペアを入力する`property:value`場合) では、二重引用符 (" ") を使用して、正確な語句または語句を検索します。 ただし、**件名** または **件名/タイトル**[の検索条件](#search-conditions)を使用する場合は、これらの検索条件を使用するときに引用符が自動的に追加されるため、値に二重引用符を追加しないでください。 値に引用符を追加すると、条件値に 2 組の二重引用符が追加され、検索クエリによってエラーが返されます。 |
|\*|cat\* <p> subject:set\*|キーワードまたは`property:value`クエリの単語の末尾にワイルドカード文字 (*) が配置されるプレフィックス検索 (*プレフィックスマッチング* とも呼ばれます)。 プレフィックス検索では、単語の後に 0 個以上の文字が続く語句を含む結果が返されます。 たとえば、 `title:set*` ドキュメント タイトルに "set"、"setup"、および "setting" (および "set" で始まる他の単語) を含むドキュメントを返します。 <p> **メモ：** プレフィックス検索のみを使用できます。たとえば、**cat\**_ や _* set\* *_などです。サフィックス検索 (_*\*cat**)、インフィックス検索 (**ct\***)、および部分文字列検索 (**\*cat\***) はサポートされていません。 <p> また、ピリオド( \. の追加 ) をプレフィックス検索に設定すると、返される結果が変更されます。 これは、ピリオドが停止語として扱われるためです。 たとえば、**cat\**_ と   _* cat.\*** 検索では、異なる結果が返されます。 プレフィックス検索ではピリオドを使用しないことをお勧めします。|
|(  )|(fair OR free) AND from:contoso.com <p> (IPO OR initial) AND (stock OR shares) <p> (quarterly financials)|括弧は、ブール演算子の文字列、 `property:value` アイテム、およびキーワードをグループにまとめます。たとえば、  `(quarterly financials)` は quarterly および financials の語を含むアイテムを返します。  |

> [!NOTE]
> <sup>1</sup> この演算子は、日付や数値を含むプロパティに使用します。<br/> <sup>2</sup> ブール検索演算子は、大文字である必要があります (例: **AND**)。 小文字の演算子を使うと (**and** など)、検索クエリではキーワードとして扱われます。

## <a name="search-conditions"></a>検索条件

検索クエリに条件を追加して、検索を絞り込み、さらに絞り込まれた結果のセットを返すようにできます。 各条件によって、作成された KQL 検索クエリに句が追加され、ユーザーが検索を開始するとそのクエリが実行されます。

[共通プロパティの条件](#conditions-for-common-properties)

[メール プロパティの条件](#conditions-for-mail-properties)

[ドキュメント プロパティの条件](#conditions-for-document-properties)

[条件で使用される演算子](#operators-used-with-conditions)

[条件を使用するためのガイドライン](#guidelines-for-using-conditions)

[検索クエリでの条件の使用例](#examples-of-using-conditions-in-search-queries)

### <a name="conditions-for-common-properties"></a>共通プロパティの条件 

同じ検索でメールボックスとサイトを検索する場合は、共通プロパティを使って条件を作成します。 次の表に、条件を追加する場合に使用可能なプロパティを一覧表示します。

|Condition|説明|
|---|---|
|日付|メールの場合、受信者によってメッセージが受信された日付か、送信者によってメッセージが送信された日付。 ドキュメントの場合、ドキュメントが最後に変更された日付。|
|送信者/作成者|メールの場合、メッセージの送信者。 ドキュメントの場合、Office ドキュメントから作成者フィールドに示されている人。 カンマで区切って、複数の名前を入力することができます。 2 つ以上の値は、**OR** 演算子によって論理的に結合されます。|
|サイズ (バイト単位)|メールとドキュメントのいずれの場合も、アイテムのサイズ (バイト単位)。|
|件名/タイトル|メールの場合、メッセージの件名行のテキスト。 ドキュメントの場合、ドキュメントのタイトル。 前述したように、Title プロパティは Microsoft Office ドキュメントに指定されたメタデータです。 複数のサブジェクト/タイトル値の名前をコンマで区切って入力できます。 2 つ以上の値は、**OR** 演算子によって論理的に結合されます。 <p> **注**: この検索条件を使用すると引用符が自動的に追加されるため、この条件の値に二重引用符を含めないでください。 値に引用符を追加すると、2 組の二重引用符が条件値に追加され、検索クエリによってエラーが返されます。|
|保持ラベル|電子メールとドキュメントの両方で、メッセージやドキュメントに自動的に適用または手動で適用できる保持ラベル。 保持ラベルを使用すると、レコードを宣言し、ラベルで指定された保持および削除ルールを適用することで、コンテンツのデータ ライフサイクルを管理するのに役立ちます。 保持ラベル名の一部を入力してワイルドカードを使うことも、完全なラベル名を入力することもできます。 アイテム保持ポリシーに関する詳細情報は、「[アイテム保持ポリシーおよび保持ラベルの詳細](retention.md)」をご覧ください。|

### <a name="conditions-for-mail-properties"></a>メール プロパティの条件

メールボックスまたはパブリック フォルダーを検索する場合は、メール プロパティを使用して条件を作成します。 条件で使用できるメール プロパティを次の表に一覧表示します。 これらのプロパティは、上で説明したメール プロパティのサブセットです。 利便性を考慮して、以下に説明をもう一度記載します。

|Condition|説明|
|---|---|
|メッセージの種類|検索するメッセージの種類。 これは、Kind メール プロパティと同じプロパティです。 可能な値: <ul><li>contacts</li><li>docs</li><li>email</li><li>externaldata</li><li>fax</li><li>im</li><li>journals</li><li>meetings</li><li>microsoftteams</li><li>notes</li><li>posts</li><li>rssfeeds</li><li>tasks</li><li>voicemail</li></ul>|
|Participants|メール メッセージのすべての送受信者フィールド。 すなわち、[差出人]、[宛先]、[Cc]、[Bcc] の各フィールドです。|
|Type|メール アイテムのメッセージ クラス プロパティ。 これは、ItemClass メール プロパティと同じプロパティです。 また、複数値の条件です。 複数のメッセージ クラスを選ぶには、**Ctrl** キーを押したまま、ドロップダウン リストで条件に追加する複数のメッセージ クラスをクリックします。 リストで選んだ各メッセージ クラスは、対応する検索クエリでは **OR** 演算子によって論理的に接続されます。 <p> Exchange によって使われていて **メッセージ クラス** リストで選ぶことができるメッセージ クラス (およびそれに対応するメッセージ クラス ID) のリストについては、「[アイテムの種類とメッセージ クラス](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes)」をご覧ください。|
|受信済み|メール メッセージが受信者によって受信された日付。これは、Received メール プロパティと同じプロパティです。|
|Recipients|メール メッセージのすべての受信者フィールド。 すなわち、[宛先]、[Cc]、[Bcc] の各フィールドです。|
|Sender|電子メール メッセージの差出人。|
|送信日時|送信者によって電子メール メッセージが送信された日付。 これは、Sent メール プロパティと同じプロパティです。|
|件名|電子メール メッセージの件名行に含まれるテキスト。 <p> **注**: この検索条件を使用すると引用符が自動的に追加されるため、この条件の値に二重引用符を含めないでください。 値に引用符を追加すると、2 組の二重引用符が条件値に追加され、検索クエリによってエラーが返されます。|
|To|[宛先] フィールドにある、メール メッセージの受信者。|

### <a name="conditions-for-document-properties"></a>ドキュメント プロパティの条件

SharePoint と OneDrive for Business sites サイトでドキュメントを検索する場合、ドキュメント プロパティを使用して条件を作成します。 次の表に、条件に使用できるドキュメント プロパティを示します。 これらのプロパティは、上で説明したサイト プロパティのサブセットです。 利便性を考慮して、以下に説明をもう一度記載します。

|Condition|説明|
|---|---|
|Author|Office ドキュメントの作成者フィールド。ドキュメントがコピーされた場合でもこのフィールは保持されます。 たとえば、ユーザーがドキュメントを作成して別のユーザーにメールで送信し、そのユーザーがそのドキュメントを SharePoint にアップロードした場合、そのドキュメントでは引き続き元の作成者が保持されます。|
|Title|ドキュメントのタイトル。 Title プロパティは、Office ドキュメントに 指定されているメタデータです。 ドキュメントのファイル名とは異なります。|
|作成済み|ドキュメントが作成された日付。|
|最終更新日時|ドキュメントが最後に変更された日付。|
|ファイルの種類|ファイルの拡張子。例: docx、one、pptx、xlsx など。 これは、FileExtension サイト プロパティと同じプロパティです。 <p> **メモ：** 検索クエリに **Equals** または **Equals 演算子を** 使用してファイルの種類条件を含める場合は、プレフィックス検索を使用して (ファイルの種類の末尾にワイルドカード文字 ( \* ) を含めることによって) ファイルの種類のすべてのバージョンを返すことはできません。 この場合、ワイルドカードは無視されます。 たとえば、条件 `Equals any of doc*`を含める場合は、拡張子 `.doc` が 1 つのファイルのみが返されます。 拡張子が 1 の `.docx` ファイルは返されません。 ファイルの種類のすべてのバージョンを返すには、キーワード クエリで *property:value* ペアを使用しました。たとえば、. `filetype:doc*`|

### <a name="operators-used-with-conditions"></a>条件で使用する演算子

条件を追加するときは、条件のプロパティの種類に関連した演算子を選択します。条件とともに使用される演算子を次の表で説明します。また、検索クエリで使用される同等物の一覧も表示します。

|演算子|クエリの同等物|説明|
|---|---|---|
|After|`property>date`|日付の条件を使用します。指定した日付以降に送信、受信、または変更されたアイテムを返します。|
|Before|`property<date`|日付の条件で使用されます。指定された日付の前に送信、受信、変更された項目を返します。|
|Between|`date..date`|日付条件およびサイズ条件で使用します。 日付条件で使用すると、指定された日付範囲内に送信、受信、変更された項目を返します。 サイズ条件で使用すると、サイズが指定範囲内にある項目を返します。|
|Contains any of|`(property:value) OR (property:value)`|文字列値を指定するプロパティの条件で使用されます。 1 つ以上の指定された文字列の値の任意の部分が含まれる項目を返します。|
|Doesn't contain any of|`-property:value` <p> `NOT property:value`|文字列値を指定するプロパティの条件で使用されます。指定された文字列のどの部分も含まれない項目を返します。|
|Doesn't equal any of|`-property=value` <p> `NOT property=value`|文字列値を指定するプロパティの条件で使用されます。特定の文字列が含まれない項目を返します。|
|Equals|`size=value`|指定されたサイズに等しい項目を返します。<sup>1</sup>|
|次のいずれかと等しい|`(property=value) OR (property=value)`|文字列値を指定するプロパティの条件で使用されます。 指定した 1 つ以上の文字列値と一致する項目を返します。|
|Greater|`size>value`|指定されたプロパティが指定された値より大きい項目を返します。<sup>1</sup>|
|Greater or equal|`size>=value`|指定されたプロパティが指定された値以上の項目を返します。<sup>1</sup>|
|より小さい|`size<value`|特定の値以上の項目を返します。<sup>1</sup>|
|Less or equal|`size<=value`|特定の値以上の項目を返します。<sup>1</sup>|
|Not equal|`size<>value`|指定したサイズと等しくないアイテムを返します。<sup>1</sup>|

> [!NOTE]
> <sup>1</sup> この演算子は、Size プロパティを使う条件でのみ使うことができます。

### <a name="guidelines-for-using-conditions"></a>条件を使用するためのガイドライン

検索条件を使用する際は、以下の点に留意してください。

- 条件は、**AND** 演算子によってキーワードのクエリ (キーワード ボックスで指定される) と論理的に接続されます。 これは、結果に含まれるようにするためには、その項目が、キーワードのクエリと条件の両方を満たす必要があることを意味します。 このように、条件を使用して結果を絞り込むことができます。

- 2 つ以上の固有の条件を検索クエリ (異なるプロパティを指定する条件) に追加する場合、それらの条件は **AND** 演算子によって論理的に接続されます。 これは、(キーワードのクエリに加えて) すべての条件が満たされる項目だけが返されることを意味します。

- 同じプロパティに複数の条件を追加する場合、これらの条件は、**OR** 演算子によって論理的に接続されます。 これは、キーワードのクエリおよびいずれかの条件を満たす項目が返されることを意味します。 それで、同じ条件のグループが **OR** 演算子によって互いに接続され、その後、固有の条件のセットが AND 演算子によって接続されます。

- 複数の値 (コンマまたはセミコロンによって区切られる) を単一の条件に追加する場合、その値は **OR** 演算子によって接続されます。 これは、条件のプロパティの指定された値のいずれかが項目に含まれる場合にその項目が返されることを意味します。

- **Contains** および **Equals** ロジックを持つ演算子を使用する条件は、単純な文字列検索で同様の検索結果を返します。 単純な文字列検索は、ワイルドカードを含まない条件内の文字列です)。 たとえば、 **いずれかの Equals を** 使用する条件は、いずれかを **含む** 条件と同じ項目を返します。

- キーワード ボックスおよび条件を使用して作成される検索クエリは、[**検索**] ページの、選択した検索の詳細ウィンドウに表示されます。 クエリでは、表記  `(c:c)` の右側のものはすべて、クエリに追加される条件を示します。

- 条件によって検索クエリに追加されるのはプロパティだけであり、演算子は追加されません。 詳細ウィンドウに表示されるクエリの表記  `(c:c)` の右側に演算子が表示されないのはそのためです。 KQL は、クエリの実行時に (前述の規則に従って) 論理演算子を追加します。

- ドラッグ アンド ドロップを使用して、条件を並び替えることができます。 条件のコントロールをクリックすると、上または下に移動できます。

- 前述のように、一部の条件プロパティでは、複数の値を入力できます (セミコロンで区切られます)。 各値は **OR** 演算子によって論理的に接続され、クエリ `(filetype=docx) OR (filetype=pptx) OR (filetype=xlsx)`が生成されます。 次の図は、複数の値を持つ条件の例を示しています。

    ![複数の値を持つ 1 つの条件。](../media/SearchConditions1.png)

  > [!NOTE]
  > 複数の条件を追加することはできません (同じプロパティの **[条件の追加]** をクリックします。 代わりに、前の例に示すように、条件に複数の値 (セミコロンで区切る) を指定する必要があります。

### <a name="examples-of-using-conditions-in-search-queries"></a>検索クエリでの条件の使用例

次の例は、条件を使用した検索クエリの GUI ベースのバージョン、選択した検索の詳細ウィンドウに表示される検索クエリ構文 (**Get-ComplianceSearch** コマンドレットによっても返される)、対応する KQL クエリのロジックを示しています。

#### <a name="example-1"></a>例 1

この例では、クレジット カード番号を含み、2021 年 1 月 1 日より前に最後に変更されたSharePointサイトとOneDrive for Business サイトのドキュメントを返します。

**GUI**:

![検索条件の最初の例。](../media/SearchConditions2.png)

**検索クエリ構文**:

`SensitiveType:"Credit Card Number"(c:c)(lastmodifiedtime<2021-01-01)`

**検索クエリ ロジック**:

`SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2021-01-01)`

前のスクリーンショットでは、検索 UI は、キーワードクエリと条件が **AND** 演算子によって接続されていることを強調していることに注意してください。

#### <a name="example-2"></a>例 2

この例では、2021 年 4 月 1 日より前に送信または作成されたキーワード "report" を含み、電子メール メッセージの件名フィールドまたはドキュメントのタイトル プロパティに "northwind" という単語を含む電子メール アイテムまたはドキュメントを返します。 クエリは、他の検索条件に一致する Web ページを除外します。

**GUI**:

![検索条件の 2 番目の例。](../media/SearchConditions3.png)

**検索クエリ構文**:

`report(c:c)(date<2021-04-01)(subjecttitle:"northwind")(-filetype:aspx)`

**検索クエリ ロジック**:

`report AND (date<2021-04-01) AND (subjecttitle:"northwind") NOT (filetype:aspx)`

#### <a name="example-3"></a>例 3

この例では、2019 年 12 月 1 日から 2020 年 11 月 30 日の間に送信され、"phone" または "スマートフォン" で始まる単語を含むメール メッセージまたは予定表会議を返します。

**GUI**:

![検索条件の 3 番目の例。](../media/SearchConditions4.png)

**検索クエリ構文**:

`phone* OR smartphone*(c:c)(sent=2019-12-01..2020-11-30)(kind="email")(kind="meetings")`

**検索クエリ ロジック**:

`phone* OR smartphone* AND (sent=2019-12-01..2020-11-30) AND ((kind="email") OR (kind="meetings"))`

## <a name="special-characters"></a>特殊文字

一部の特殊文字は検索インデックスに含まれないため、検索できません。 これには、検索クエリの検索演算子を表す特殊文字も含まれます。 実際の検索クエリでは空白スペースに置き換えられるか、検索エラーの原因となる特殊文字の一覧を次に示します。

`+ - = : ! @ # % ^ & ; _ / ? ( ) [ ] { }`

## <a name="searching-for-site-content-shared-with-external-users"></a>外部ユーザーと共有されているサイト コンテンツの検索

コンプライアンス センターの電子情報開示検索ツールを使用して、組織外のユーザーと共有されているSharePointおよびOneDrive for Business サイトに保存されているドキュメントを検索することもできます。 これにより、組織外で共有されている重要な情報や機密情報を識別できます。 これはキーワード クエリの  `ViewableByExternalUsers` プロパティを使って行うことができます。 このプロパティは、次の共有方法のいずれかを使用して外部ユーザーと共有されているドキュメントまたはサイトを返します。

- ユーザーが認証されたユーザーとして組織にサインインする必要がある共有への招待。
- リンクを使って誰でも認証なしでリソースにアクセスできる匿名ゲスト リンク。

次に例を示します。

- クエリ  `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` は、組織外のユーザーと共有されている、クレジット カード番号を含むすべてのアイテムを返します。
- クエリ  `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` は、外部ユーザーと共有されている、組織内のすべてのチーム サイトにあるドキュメントの一覧を返します。

> [!TIP]
> `ViewableByExternalUsers:true AND ContentType:document` などの検索クエリは、検索結果に多数の .aspx ファイルを返すことがあります。 これら (または他の種類のファイル) を削除するには、特定のファイルの種類を除外する  `FileExtension` プロパティを使うことができます。例: `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`

組織外のユーザーと共有されているコンテンツとして見なされるのは何ですか? 共有への招待を送信して共有されているか、公共の場所で共有されている、組織の SharePoint と OneDrive for Business のサイト内のドキュメント。 たとえば、次のユーザー アクティビティよって、コンテンツが外部ユーザーに表示されることになります。

- ユーザーが組織外のユーザーとファイルやフォルダーを共有する。
- ユーザーが共有ファイルへのリンクを作成し、組織外のユーザーに送信する。 外部ユーザーはこのリンクからファイルを表示 (または編集) できるようになります。
- ユーザーが、共有ファイルを表示 (または編集) するための共有への招待やゲスト リンクを組織外のユーザーに送信する。

### <a name="issues-using-the-viewablebyexternalusers-property"></a>ViewableByExternalUsers プロパティを使用する際の問題

`ViewableByExternalUsers` プロパティは、ドキュメントまたはサイトが外部ユーザーと共有されているかどうかのステータスを表しますが、このプロパティが表す / 表さないものに関して、以下の注意点があります。 次のシナリオでは、プロパティの  `ViewableByExternalUsers` 値は更新されません。また、このプロパティを使用する検索クエリの結果が不正確である可能性があります。

- サイトまたは組織の外部共有をオフにするなど、共有ポリシーにおける変更。 外部アクセスが取り消されている可能性があるにもかかわらず、プロパティでは、以前に共有されたドキュメントが外部アクセス可能と示されます。
- Office 365 グループまたは Microsoft 365 セキュリティ グループへの外部ユーザーの追加や削除など、グループ メンバーシップの変更。 グループがアクセスできるアイテムのプロパティは自動的に更新されません。
- 外部ユーザーに共有招待状を送信した場合に、受信者が招待状をまだ承諾しておらず、そのためコンテンツにまだアクセスできない場合。

このシナリオでは、サイトまたはドキュメントのライブラリが再クロールされ、インデックスが再作成されるまでは、  `ViewableByExternalUsers` プロパティは現在の共有状態を表しません。

## <a name="searching-for-site-content-shared-within-your-organization"></a>組織内で共有されているサイト コンテンツの検索

上で説明したように、 `SharedWithUsersOWSUser` プロパティを使って、組織内のユーザー間で共有されているドキュメントを検索できます。 ユーザーが組織内の別のユーザーとファイル (またはフォルダー) を共有すると、ファイルを共有されたユーザーの OneDrive for Business アカウントの [**自分と共有**] ページに、共有ファイルへのリンクが表示されます。 たとえば、Sara Davis と共有されているドキュメントは、 `SharedWithUsersOWSUser:"sarad@contoso.com"` というクエリを使って検索できます。 この検索の結果をエクスポートすると、(ドキュメントを Sara と共有したユーザーのコンテンツの場所にある) 元のドキュメントがダウンロードされます。

`SharedWithUsersOWSUser` プロパティを使用した検索結果にドキュメントが返されるには、そのドキュメントが指定したユーザーと明示的に共有されている必要があります。 たとえば、ユーザーが OneDrive アカウントでドキュメントを共有している場合は、ドキュメントを任意のユーザー (組織外または組織内) と共有する、組織内のユーザーとのみ共有する、または特定のユーザーと共有するためのオプションがあります。 3 つの共有オプションを表示している OneDrive の [**共有**] ウィンドウのスクリーン ショットを次に示します。

![SharedWithUsersOWSUser プロパティを使用する検索クエリによって、特定のユーザーと共有されているファイルのみが返されます。](../media/469a4b61-68bd-4ab0-b612-ab6302973886.png)

`SharedWithUsersOWSUser` プロパティを使用する検索クエリで返されるドキュメントは、3 番目のオプション ([**特定のユーザー**] と共有) を使用して共有されているドキュメントのみです。 

## <a name="searching-for-skype-for-business-conversations"></a>Skype for Business の会話を検索

次のキーワード クエリを使用すると、特に Skype for Business の会話のコンテンツを検索できます。

```powershell
kind:im
```

上の検索クエリは、Microsoft Teams からのチャットも返します。 これを回避するには、次のキーワード クエリを使用して、検索結果に Skype for Business の会話のみを含めるようにできます。

```powershell
kind:im AND subject:conversation
```

Skype for Business の会話は 件名が "Conversation" という単語で始まるメール メッセージとして保存されるため、上のキーワード　クエリでは Microsoft Teams のチャットが除外されます。

特定の日付範囲に行われた Skype for Business の会話を検索するには、次のキーワード クエリを使用します。

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="character-limits-for-searches"></a>検索の文字制限

SharePoint サイトとOneDrive アカウントでコンテンツを検索する場合、検索クエリには 4,000 文字の制限があります。
検索クエリの合計文字数の計算方法を次に示します。

- キーワード検索クエリの文字 (ユーザー フィールドとフィルター フィールドの両方を含む) は、この制限に対してカウントされます。
- 任意の場所プロパティ内の文字 (検索対象のすべてのSharePoint サイトの URL や検索されるOneDriveの場所など) は、この制限に反してカウントされます。
- 制限に対して検索カウントを実行しているユーザーに適用されるすべての検索アクセス許可フィルター内の文字。

文字制限の詳細については、「 [電子情報開示検索の制限](limits-for-content-search.md#search-limits)」を参照してください。

> [!NOTE]
> 4,000 文字の制限は、コンテンツ検索、電子情報開示 (Standard)、電子情報開示 (プレミアム) に適用されます。

## <a name="search-tips-and-tricks"></a>検索のヒントと秘訣

- キーワード検索では大文字と小文字は区別されません。 たとえば、**cat** と **CAT** は同じ結果を返します。

- ブール演算子の **AND**、**OR**、**NOT**、および **NEAR** は、大文字でなければなりません。

- 2 つのキーワード間または　2　つの  `property:value` 式間のスペースは、**AND** を使用する場合と同じです。 たとえば、 `from:"Sara Davis" subject:reorganization` は、件名に ”reorganization” の単語が含まれる Sara Davis によって送信されたすべてのメッセージを返します。

- `property:value` 形式に一致する構文を使用します。 値では大文字と小文字が区別されず、演算子の後にスペースを設定することはできません。 スペースがある場合、目的の値はフルテキスト検索になります。 たとえば、`to: pilarp` は、pilarp に送信されたメッセージではなく、"pilarp" によるキーワード検索を行います。

- To、From、Cc、Recipients などの受信者プロパティを検索するとき、SMTP アドレス、別名、または表示名を使用して受信者を指定できます。たとえば、pilarp@contoso.com、pilarp、または "Pilar Pinilla" を使用できます。

- プレフィックス検索のみを使用できます。たとえば、**cat\**_ や _* set\* *_などです。サフィックス検索 (_*\*cat**)、インフィックス検索 (**ct\***)、および部分文字列検索 (**\*cat\***) はサポートされていません。

- 検索プロパティを検索するとき、検索値が複数の単語で構成される場合は、二重引用符 ("  ") を使用します。 たとえば、 `subject:budget Q1` は、件名行に **budget** を含み、メッセージ内またはいずれかのメッセージ プロパティ内のいずれかの場所に **Q1** を含むメッセージを返します。 `subject:"budget Q1"` を使用すると、件名行に **budget Q1** を含むすべてのメッセージが返されます。

- 特定のプロパティ値でマークされているコンテンツを検索結果から除外するには、プロパティの名前の前にマイナス記号 (-) を置きます。 たとえば、 `-from:"Sara Davis"` は、Sara Davis によって送信されたすべてのメッセージを除外します。

- メッセージの種類に基づいてアイテムをエクスポートできます。 たとえば、Skype の会話と Microsoft Teams のチャットをエクスポートするには、構文 `kind:im` を使用します。 メール メッセージだけを返すには、`kind:email` を使用します。 Microsoft Teams のチャット、会議、通話を返すには、`kind:microsoftteams` を使用します。

- 前に説明したように、サイトを検索する場合は、プロパティを使用して`path`指定したサイト内のアイテムのみを返すときに、URL の末尾に末尾`/`を追加する必要があります。 末尾 `/`を含めない場合は、同様のパス名を持つサイトのアイテムも返されます。 たとえば、使用すると `path:sites/HelloWorld` 、名前が付けられた `sites/HelloWorld_East` サイトのアイテム、または `sites/HelloWorld_West` 返されるサイトのアイテムも返されます。 HelloWorld サイトからのみアイテムを返すには、 `path:sites/HelloWorld/`.
