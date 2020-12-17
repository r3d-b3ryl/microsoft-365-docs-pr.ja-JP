---
title: トピック エクスペリエンスの役割 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: トピック エクスペリエンスのユーザー ロールについて説明します。
ms.openlocfilehash: ed4d40aa7bb91a85e28aba7ace99edf580c427a5
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698904"
---
# <a name="topic-experiences-roles-preview"></a>トピック エクスペリエンスの役割 (プレビュー)

> [!Note] 
> この記事の内容は、Project の Private Preview 用です。 [Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)


Microsoft 365 環境でトピック エクスペリエンスを使用する場合、ユーザーは次の役割を持ちます。
-   トピック ビューアー
-   トピックの投稿者
-   ナレッジ マネージャー
-   ナレッジ管理者

## <a name="topic-viewer"></a>トピック ビューアー

トピック ビューアーは、SharePoint モダン サイトおよび SharePoint 検索で強調表示されたトピックを表示できる組織内のユーザーです。 強調表示されたトピックを選択して、トピック ページでトピックに関する詳細を表示できます。 

トピックのハイライトとそのトピック ページをトピック ビューアーに表示するには、ユーザーは次の条件を実行する必要があります。
-   [トピック エクスペリエンス のライセンスは](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 、Microsoft 365 管理者によって割り当てられます。
-   トピックを表示できます。 これは、Microsoft 365 管理センターの [トピックエクスペリエンスの設定] ページのナレッジ管理者が行います。


## <a name="topic-contributors"></a>トピックの投稿者

トピックの投稿者は、トピック閲覧者のアクセス許可を持っているだけでなく、既存のトピックを編集したり、新しいトピックを作成したりできる組織内のユーザーです。 トピック ページ内の情報を手動で "キュレーション" する上で重要な役割を果たします (AI または手動で提供された情報の両方)。

トピック投稿者のアクセス許可を持つユーザーには、[トピック] ページに [編集] ボタンが表示され、トピックを更新して発行できます。

トピック投稿者は、トピック センター サイトを使用して新しいトピックを作成して発行できます。

トピックを作成および編集するには、ユーザーは次の条件を実行する必要があります。

-   [トピック エクスペリエンス のライセンスは](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 、Microsoft 365 管理者によって割り当てられます。
-   [トピックを作成および編集するためのアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 これは、Microsoft 365 管理センターの [トピックエクスペリエンスの設定] ページのナレッジ管理者が行います。

## <a name="knowledge-managers"></a>ナレッジ マネージャー

ナレッジ マネージャーは、組織内のトピックを管理するユーザーです。  トピック管理は、トピック センターの [トピックの管理] ページで行い、ナレッジ マネージャーにのみ表示されます。

[トピックの管理] ページでは、ナレッジ マネージャーは次のタスクを実行できます。
-   AI が提案するトピックを表示します。
-   トピックを確認して、有効なトピックを確認します。
-   ユーザーに表示しないトピックを削除します。


また、ナレッジ マネージャーは、既存のトピックを編集したり、新しいトピックを作成できます。

トピックを管理するには、ユーザーは次の条件を実行する必要があります。
-   [トピック エクスペリエンス のライセンスは](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 、Microsoft 365 管理者によって割り当てられます。
-   [トピックを管理するためのアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 これは、Microsoft 365 管理センターの [トピックエクスペリエンスの設定] ページのナレッジ管理者が行います。

ビジネスに関する全体的な知識を持つユーザーは、ナレッジ マネージャーロールの有力候補になる可能性があります。 このようなユーザーは、トピックが有効かどうか知る知識を持っているだけでなく、それらのトピックに関連する企業内のユーザーも知っている可能性があります。


## <a name="knowledge-admins"></a>ナレッジ管理者

ナレッジ管理者は、Microsoft 365 環境でトピック エクスペリエンスをセットアップおよび構成する管理者です。 また、セットアップが完了した後でトピック エクスペリエンスの設定も管理します。 セットアップと管理は Microsoft 365 管理センターで行われるので、ナレッジ管理者ロールは Microsoft 365 グローバル管理者または SharePoint 管理者である必要があります。
セットアップ中に、ナレッジ管理者はトピック エクスペリエンスを構成して次の操作を実行できます。

-   トピックに対してクロールする SharePoint サイトを選択します。
-   トピック (トピック閲覧者) を表示できるライセンスユーザーを選択します。
-   特定から除外するトピックを選択します。
-   トピック (トピック投稿者) を作成および編集できるライセンスユーザーを選択します。
-   トピックを管理できるライセンスユーザー (ナレッジ マネージャー) を選択します。
-   トピック センターに名前を付けます。

ナレッジ マネージャーは、組織内のすべてのトピックエクスペリエンスの関係者と調整して、構成方法を知る必要があります。 たとえば、新しいプロジェクトに機密情報がある場合、ナレッジ マネージャーに通知して、トピックに対して SharePoint サイトがクロールされていないか、特定のトピック名を除外する必要があります。


## <a name="see-also"></a>関連項目

