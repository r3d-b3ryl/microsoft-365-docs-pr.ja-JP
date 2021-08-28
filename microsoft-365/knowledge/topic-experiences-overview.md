---
title: Microsoft Viva トピックの概要
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan; lauris
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: 組織でビバ トピックを使用する方法について説明します。
ms.openlocfilehash: 902628d53f651073b1d08ce3f1915808da22b03f
ms.sourcegitcommit: d016e3bd30c0dd73c4cd3d804c0b6941b5eb3e87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2021
ms.locfileid: "58684135"
---
# <a name="microsoft-viva-topics-overview"></a>Microsoft Viva トピックの概要 

ビバ トピックでは、Microsoft AI テクノロジ、Microsoft 365、Microsoft Graph、検索、その他のコンポーネントとサービスを使用して、SharePoint モダン ページ、Microsoft Search、Search in Word、PowerPoint、Outlook、および Excel から始まる、日常的に使用する Microsoft 365 アプリのユーザーに知識を提供します。

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

<br/>

Viva Topics は、多くの企業で重要なビジネス上の問題に対処するのに役立ちます。必要なときにユーザーに情報を提供します。 たとえば、新入社員は多くの新しい情報を素早く学ばなければならず、会社情報を読んでいてもまったく知らない言葉に出会うことがあります。 たとえば、その用語が何なのか、組織内の誰が専門家なのか、その用語に関連するサイトやドキュメントがあるのかなど、詳細を調べるために、ユーザーは自分の作業を離れて、貴重な時間を費やす必要があります。

Viva トピックは、AI を使って組織内の *トピック* を自動的に検索し、特定します。 簡単な説明、トピックで作業するユーザー、それに関連するサイト、ファイル、ページなどの情報をまとめています。 知識の管理者や共同作成者は、必要に応じてトピック情報の更新を選択できます。 トピックはユーザーに公開されます。つまり、最新の SharePoint サイトのニュースやページに表示されるトピックのすべてのインスタンスについて、テキストが強調表示されます。 ユーザーは、トピックを選択すると、トピックの詳細からその内容を知ることができます。 トピックは、SharePoint Search でも検索できます。

## <a name="how-topics-are-displayed-to-users"></a>ユーザーに対するトピックの表示方法

トピックは、次の方法でユーザーに表示されます。

- [ページで強調表示](topic-experiences-overview.md#sharepoint-highlights)SharePointトピック
- 検索結果のトピック [回答](topic-experiences-overview.md#search-results)
- Office アプリケーション [での検索](topic-experiences-overview.md#office-application-search)
- [トピック センターの](topic-experiences-overview.md#topic-center) ホーム ページ

### <a name="sharepoint-highlights"></a>SharePointハイライト

SharePoint ニュースやページのコンテンツでトピックがメンションされると、そのトピックが強調表示されます。 強調表示からトピック サマリーを開くことができます。 概要のタイトルからトピックの詳細を開き、完全なトピック ページを表示します。 前述のトピックは、自動的に識別するか、ページ作成者によって直接参照されている可能性があります。 

   ![トピックのハイライトを示すスクリーンショット。](../media/knowledge-management/saturn.png) 

### <a name="search-results"></a>検索結果

検索範囲を変更[](search.md#topic-answer)して組織全体を含める場合は、SharePoint スタート ページから検索したり、Office.com で検索したり、SharePoint サイトから検索したりすると、検索結果にトピックの回答が表示されます。 トピックの回答は、結果リストのトピックに表示され、そのトピックに関連する短い情報セットを提供します。 

   ![サイト検索の検索結果を示SharePointスクリーンショット。](../media/knowledge-management/site-search-results.png) 

### <a name="office-application-search"></a>Office検索

Word、PowerPoint、Outlook、Excel などの Office アプリで検索を使用する場合は、検索ボックスを使用するか、コンテキスト メニューで [検索] を選択すると、トピックの回答が検索結果に表示されます。

   ![[検索] ボックスを使用して Word で検索を示すスクリーンショット。](../media/knowledge-management/word-search-2.png)

   ![[検索] コンテキスト メニューを使用して Word で検索を示すスクリーンショット。](../media/knowledge-management/word-search-1.png)

### <a name="topic-center"></a>トピック センター

ユーザーは、自分が接続している組織内のトピックをトピック センターのホーム [ページで確認できます](topic-center-overview.md#home-page)。

## <a name="knowledge-indexing"></a>知識のインデックス化

Viva トピックは、Microsoft の AI 技術を用いて、Microsoft 365 環境の *トピック* を特定します。

トピックとは、組織的に重要な意味を持つフレーズや用語のことです。 組織にとって特定の意味を持ち、それに関連したリソースがあり、ユーザーがその意味を理解し、それに関する詳細な情報を見つけるのに役立ちます。 組織にとって重要なトピックには、さまざまな種類があります。 当初、Microsoft の AI 技術は以下のタイプに焦点を当てています。

- プロジェクト
- イベント
- 組織
- 場所
- 製品
- クリエイティブな作業
- 専攻分野

トピックが特定され、AI が提案トピックとして十分な情報を持っていると判断すると、*トピック ページ* には、次のようにトピックのインデックス化によって収集された情報が表示されます。

- 代替名と頭字語。
- トピックの簡単な説明。
- そのトピックに関する知識が豊富と思われるユーザー。
- トピックに関連するファイル、ページ、サイト。

知識管理者は、テナント内のすべての SharePoint サイトをクロールしてトピックを探すことも、特定のサイトだけを選択することもできます。

詳細については、「トピックの検出 [とキュレーション」を参照してください](./topic-experiences-discovery-curation.md)。

## <a name="roles"></a>ロール

Microsoft 365 環境で Viva・トピックを使用する場合、ユーザーには以下のロールがあります。

- トピック ビューアー: 少なくとも *読み取り* のアクセス許可を持つ SharePoint の最新のサイトや、Microsoft Search でトピックの強調表示を表示することができるユーザー。 トピックの強調表示を選択すると、トピック ページにトピックの詳細が表示されます。 トピックを見た人は、そのトピックの有用性をフィードバックすることができます。

- 共同作成者: 既存のトピックを編集したり、新しいトピックを作成する権利を持つユーザー。 知識管理者は、Microsoft 365 管理センターの Viva トピック設定で、ユーザーに共同作成者のアクセス許可を割り当てます。 なお、すべてのトピック閲覧者にトピックの編集と作成のアクセス許可を付与することで、すべてのユーザーが閲覧したトピックに協力できるようにすることもできます。

- 知識マネージャー: トピックのライフ サイクルを通してトピックをガイドするユーザー。 ナレッジ マネージャーは、トピック センターの [トピックの管理] ページを使用して、AI が推奨するトピックを確認し、関連性がなくなったトピックを削除し、既存のトピックを編集したり、新しいトピックを作成したりします。 知識管理者は、Microsoft 365 管理センターの Viva トピック管理設定で、ユーザーに知識マネージャーのアクセス許可を割り当てます。 

- ナレッジ管理者: 管理者は、ビバ トピックをセットアップし、管理者の管理コントロールを使用して管理Microsoft 365 管理センター。 現在、Microsoft 365 グローバル管理者や SharePoint 管理者が知識管理者として活躍できます。

詳細については [、「Viva Topics roles」を参照してください](topic-experiences-roles.md)。

## <a name="topic-management"></a>トピック管理

トピック管理は、組織のトピック **センターの** [トピックの管理] ページで *行います*。 トピック センターはセットアップ中に作成され、組織の知識の中心として機能します。 

ライセンスを取得しているすべてのユーザーは、トピック センターで接続されているトピックを表示することができますが、トピックの管理権限 (ナレッジ マネージャー) を持つユーザーだけが [トピックの管理] ページを表示および **使用** できます。

知識マネージャーは、次のことができます。

- テナントで検出されたトピックを確認または削除します。
- 必要に応じて手動で新しいトピックを作成する (たとえば、AI で検出できるほど十分な情報が提供されなかった場合など)。
- 既存のトピック ページの編集。

詳細については、「トピック センターの [トピックの管理」を参照してください](manage-topics.md)。  

## <a name="admin-controls"></a>管理制御

このページの管理Microsoft 365 管理センター、ビバ トピックを管理できます。 これらにより、Microsoft 365 グローバル管理者や SharePoint サービス管理者は次のことができます。

- 組織内のどのユーザーが SharePoint の最新ページや SharePoint 検索結果でトピックを見ることができるかを制御します。
- トピックを特定するためにどの SharePoint サイトをクロールするかを制御します。
- 特定のトピックを検索対象から除外します。
- トピック センターでトピックを管理できるユーザーを制御します。
- トピックを作成し編集できるユーザーを制御します。
- トピックを閲覧できるユーザーを制御します。

管理コントロールの詳細については、「[ユーザーアクセス許可](./plan-topic-experiences.md#user-permissions)の割り当[](./topic-experiences-knowledge-rules.md)て、トピックの表示の管理、トピックの検出[の管理」を参照してください](./topic-experiences-discovery.md)。

## <a name="topic-curation-and-suggestions"></a>トピックのキュレーションと提案

AI は、お客様の環境の変化に合わせて、トピックを改善するための提案を継続的に行っていきます。 

トピックの編集や作成のアクセス許可を持つユーザーは、修正や追加の情報を必要とする場合、トピック ページを直接更新することができます。 また、AI が認識できなかった新しいトピックを追加することもできます。 これらの手動で追加されたトピックに関する十分な情報が存在し、AI がこの種類のトピックを特定できる場合は、AI からの追加の提案によって、これらの手動で追加されたトピックが強化される可能性があります。

日常業務でトピックの閲覧を許可しているユーザーには、そのトピックが自分にとって有益か質問することがあります。 システムは、これらの回答を見て、トピックの強調表示を改善したり、トピックの概要やトピックの詳細に表示する内容を決定するのに使用します。

詳細については、「トピックの検出 [とキュレーション」を参照してください](./topic-experiences-discovery-curation.md)。

## <a name="provide-us-feedback"></a>フィードバックを提供する

Microsoft では、お客様からのフィードバックを非常に真剣に受け止めています。 Viva Topics に提供するフィードバックは、トラブルシューティング、バグの修正、既存の機能の強化、および新しい機能の開発に使用されます。 

トピック ページおよびトピックの管理ページと [マイ トピック]ページから、Microsoft に直接フィードバック **を送信** できます。 ページの右下隅にあるこのボタンを探します。

   ![[フィードバック] ボタンを示すスクリーンショット。](../media/knowledge-management/feedback-icon.png)

[フィードバックを **Microsoft に送信する** ] ページで、何か好きかどうか、気に入らない場合、または提案があればお知らせします。

   ![[フィードバックを Microsoft に送信する] ページを示すスクリーンショット。](../media/knowledge-management/feedback-page.png)

フィードバックを送信する際には、電話番号、住所、個人性の高いストーリーなどの機密情報を含めないでお願いします。 代わりに、Viva Topics で発生している特定の問題や、ビバ トピックに関するエクスペリエンス全般に関する情報を提供してください。 これにより、お客様からのフィードバックに基づいてレビューとアクションを実行する際に、プライバシーを保つのに役立ちます。

お時間を頂き、ありがとうございます。 お客様の視点は、既存の機能を改善し、新しい機能を開発するのに役立ちます。

## <a name="see-also"></a>関連項目

[ビバ Microsoft Searchトピックを検索するには、次のトピックを使用します。](./search.md)
