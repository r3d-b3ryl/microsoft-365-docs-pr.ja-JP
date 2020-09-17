---
title: ナレッジ管理の概要 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex のナレッジ管理の概要。
ms.openlocfilehash: 80750ee94248b21b8ac7bd3869830a7986de34b9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949374"
---
# <a name="knowledge-management-0verview-preview"></a>ナレッジマネジメント 0verview (プレビュー)

> [!Note] 
> この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex」を参照してください。](https://aka.ms/projectcortex) 

ナレッジ管理では、microsoft AI テクノロジ、Microsoft 365、Delve、検索、およびその他のコンポーネントとサービスを使用して、Microsoft 365 環境でナレッジネットワークを構築します。 

   ![ナレッジ管理フロー](../media/content-understanding/knowledge-management-flowchart.png) </br> 

これは、Outlook、Teams、SharePoint など、毎日使用するアプリでユーザーに情報を配信することを目的としています。

たとえば、ユーザーの電子メール、SharePoint サイト、または Teams の会話に、わかりやすい用語が表示されるようにします。 ナレッジ管理は、AI を使用してこれらの **トピック**を自動的に検索して識別し、それらに関する情報 (短い説明、トピックの対象者の専門家、およびそれに関連するサイト、ファイル、ページなど) をコンパイルします。 必要に応じて、トピック情報を更新するように選択できます。 その後、ユーザーがトピックを利用できるようにすることができます。つまり、Outlook、Teams、SharePoint などのアプリに表示されるトピックのすべてのインスタンスについて、テキストが強調表示されます。 トピックの詳細については、トピックを選択して詳細を確認できます。


## <a name="topic-discovery"></a>トピックの検出

ナレッジ管理は、Microsoft AI テクノロジを使用して、Office 365 環境の **トピック** を検索します。

トピックは、意味のある、または重要な語句または用語です。 組織にとっては特定の意味があります。また、それに関連するリソースがあります。これにより、ユーザーはそれを理解し、より詳細な情報を見つけることができます。

トピックが検出されると、次のようなトピック検出によって収集された情報を含むトピック **ページ** が作成されます。

- トピックの簡単な説明。
- トピックについて精通している可能性があるユーザー。
- トピックに関連するファイル、ページ、およびサイト。


## <a name="topic-management"></a>トピック管理

トピック管理は、組織の **トピックセンター**で行われます。 トピックセンターサイトはセットアップ時に作成され、組織のためのナレッジセンターとして機能します。 ここには、環境で検出されたすべてのトピックの一覧と、これらのトピックに対して作成されたすべてのトピックページが含まれています。 

適切なアクセス許可を付与されたユーザーは、トピックセンターで次の操作を実行できます。

- テナントで検出されたトピックを確認または拒否します。
- 必要に応じて、新しいトピックを手動で作成します (たとえば、十分な情報が得られなかった場合は、それを AI で検出するため)。
- 既存のトピックページを編集します。</br>

詳細について [は、トピックセンターの「Work with topic](work-with-topics.md) 」を参照してください。  


## <a name="admin-controls"></a>管理コントロール

Microsoft 365 管理センターの管理者コントロールを使用すると、ナレッジネットワークを管理できます。 これにより、Microsoft 365 グローバルまたは SharePoint 管理者が次のことを行うことができます。

- 組織内のどのユーザーが自分のクライアントアプリまたは SharePoint 検索結果でトピックを参照できるようにするかを制御します。
- トピックを検索するためにどの SharePoint サイトをクロールするかを制御します。
- トピックとして使用しない特定の用語を除外するようにトピック検出を構成します。
- トピックセンターでトピックを確認または拒否することができるユーザーを制御します。
- トピックセンターでトピックを作成および編集できるユーザーを制御します。

詳細については [、「ナレッジネットワークの管理](manage-knowledge-network.md) 」を参照してください。 

## <a name="topic-curation"></a>トピック (curation

AI は、環境内で変更が発生したときに、トピックを改善するための提案を継続的に提供していきます。

ユーザーが毎日の作業でトピックを参照できるようにするには、それらのユーザーに対して推奨事項を提案することができます。 たとえば、ユーザーがトピックページを表示し、正しくない情報や追加が必要な情報を確認すると、そのトピックページにあるリンクによって、情報を更新する要求を送信できます。

さらに、適切なアクセス許可を持つユーザーは、トピックに関連する Teams 会話などのアイテムにタグを付けて、特定のトピックに追加することができます。




## <a name="see-also"></a>関連項目
[ナレッジ管理の設定](set-up-knowledge-network.md)</br>
[トピックセンターの概要](topic-center-overview.md)
