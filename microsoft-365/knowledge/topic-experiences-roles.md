---
title: Microsoft のトピックの役割
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
description: ユーザー ロールの詳細については、「トピック」を参照してください。
ms.openlocfilehash: e2975201124045574c516aad49bc5059db969b76
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107436"
---
# <a name="microsoft-viva-topics-roles"></a>Microsoft のトピックの役割 

Microsoft 365 環境で多くのトピックを使用する場合、ユーザーは次の役割を持ちます。
-   トピック ビューアー
-   トピックの投稿者
-   ナレッジ マネージャー
-   ナレッジ管理者

## <a name="topic-viewer"></a>トピック ビューアー

トピック ビューアーとは、SharePoint のモダン サイト、SharePoint を使用した Microsoft Search、およびトピック センターで強調表示されたトピックを表示できる組織内Office.comユーザーです。 トピック ページでトピックに関する詳細を表示できます。 

トピックのハイライトとそのトピック ページをトピック ビューアーに表示するには、ユーザーは次の条件を実行する必要があります。
-   Microsoft 365 管理者[によって](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses)、多くのトピックのライセンスが割り当てられます。
-   トピックを表示できます。 このタスクは、Microsoft 365 管理センターの [多くのトピックの設定] ページのナレッジ管理者が行います。


## <a name="topic-contributors"></a>トピックの投稿者

トピックの投稿者は、トピック閲覧者のアクセス許可を持っているだけでなく、既存のトピックを編集したり、新しいトピックを作成したりできる組織内のユーザーです。 トピック ページ内の情報を手動で "キュレーション" する上で重要な役割を果たします (AI または手動で提供された情報の両方)。

トピック投稿者のアクセス許可を持つユーザーには、[トピック] ページに [編集] ボタンが表示され、トピックを更新して発行できます。

トピック投稿者は、トピック センターを通じて新しいトピックを作成して発行できます。

トピックを作成して編集するには、ユーザーは次の条件を実行する必要があります。

-   Microsoft 365 管理者[によって、](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses)多くのトピックのライセンスが割り当てられます。
-   [トピックを作成および編集するためのアクセス許可が割り当てられている](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 このタスクは、Microsoft 365 管理センターの [多くのトピックの設定] ページのナレッジ管理者が行います。

## <a name="knowledge-managers"></a>ナレッジ マネージャー

ナレッジ マネージャーは、組織内のトピックを管理するユーザーです。  トピック管理は、トピック センターの [トピックの管理] ページで行い、ナレッジ マネージャーにのみ表示されます。

[トピックの管理] ページでは、ナレッジ マネージャーは次のタスクを実行できます。
-   AI が提案するトピックを表示します。
-   トピックを確認して、有効なトピックを確認します。
-   ユーザーに表示しないトピックを削除します。

また、ナレッジ マネージャーは、既存のトピックを編集したり、新しいトピックを作成できます。

トピックを管理するには、ユーザーは次の条件を実行する必要があります。
-   Microsoft 365 管理者[によって](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses)、多くのトピックのライセンスが割り当てられます。
-   [トピックを管理するためのアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 このタスクは、Microsoft 365 管理センターの [多くのトピックの設定] ページのナレッジ管理者が行います。

ビジネスに関する全体的な知識を持つユーザーは、ナレッジ マネージャーロールの有力候補になる可能性があります。 このようなユーザーは、トピックが有効かどうか知る知識を持っているだけでなく、それらのトピックに関連する企業内のユーザーも知っている可能性があります。


## <a name="knowledge-admins"></a>ナレッジ管理者

ナレッジ管理者は、Microsoft 365 環境で多くのトピックをセットアップおよび構成する管理者です。 また、セットアップが完了した後で、[トピック] の設定も管理します。 セットアップと管理は Microsoft 365 管理センターで行われるので、ナレッジ管理者ロールは Microsoft 365 グローバル管理者または SharePoint 管理者である必要があります。
セットアップ時に、ナレッジ管理者は次の機能を持つ多くのトピックを構成できます。

-   トピックに対してクロールする SharePoint サイトを選択します。
-   トピック (トピック閲覧者) を表示できるライセンスユーザーを選択します。
-   特定から除外するトピックを選択します。
-   トピック (トピック投稿者) を作成および編集できるライセンス ユーザーを選択します。
-   トピックを管理できるライセンスユーザー (ナレッジ マネージャー) を選択します。
-   トピック センターに名前を付けます。

ナレッジ マネージャーは、組織内のすべての多くの関係者と調整して、構成方法を知る必要があります。 たとえば、新しいプロジェクトに機密情報がある場合、ナレッジ マネージャーに通知して、トピックに対して SharePoint サイトがクロールされていないか、特定のトピック名を除外する必要があります。


## <a name="see-also"></a>関連項目

