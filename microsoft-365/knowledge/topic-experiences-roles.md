---
title: Microsoft Viva トピックのロール
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
- m365initiative-viva-topics
localization_priority: None
description: ビバ トピックのユーザー ロールについて説明します。
ms.openlocfilehash: d5b57e768a1de8bc0447492067371630b2d045f6
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453945"
---
# <a name="microsoft-viva-topics-roles"></a>Microsoft Viva トピックのロール 

Microsoft 365 環境で Viva Topics を使用する場合、ユーザーは次の役割を果たします。
-   トピック ビューアー
-   トピック投稿者
-   ナレッジ マネージャー
-   ナレッジ管理者

## <a name="topic-viewer"></a>トピック ビューアー

トピック ビューアーは組織内のユーザーで、SharePoint モダン サイト、Microsoft Search through SharePoint、およびトピック センターで強調表示されたトピックOffice.com表示できます。 トピックページでトピックの詳細を表示できます。 

トピックの強調表示とそのトピック ページをトピック ビューアーに表示するには、次の項目を使用する必要があります。
-   Microsoft 365 管理者[がビ](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses)バ トピックス ライセンスを割り当てる。
-   トピックを表示できます。 このタスクは、Microsoft 365 管理センターの [ビバ トピックの設定] ページのナレッジ管理者によって実行されます。


## <a name="topic-contributors"></a>トピック投稿者

トピック投稿者とは、トピック ビューアーのアクセス許可を持つだけでなく、既存のトピックを編集したり、新しいトピックを作成したりできる組織内のユーザーです。 トピック ページ内の情報 (AI または手動で提供された両方) を手動で "キュレーション" し、品質を確保する上で重要な役割を果たします。

トピック投稿者のアクセス許可を持つユーザーには、[トピック] ページに [編集] ボタンが表示され、トピックの更新と発行が可能になります。

トピック投稿者は、トピック センターを通じて新しいトピックを作成および発行できます。

トピックを作成して編集するには、次の条件を実行する必要があります。

-   Microsoft 365 管理者[がビ](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses)バ トピックス ライセンスを割り当てる。
-   [トピックを作成および編集するためのアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 このタスクは、Microsoft 365 管理センターの [ビバ トピックの設定] ページのナレッジ管理者によって実行されます。

## <a name="knowledge-managers"></a>ナレッジ マネージャー

ナレッジ マネージャーは、組織内のトピックを管理するユーザーです。  トピック管理は、トピック センターの [トピックの管理] ページで行われ、ナレッジ マネージャーにのみ表示されます。

[トピックの管理] ページで、ナレッジ マネージャーは次のタスクを実行できます。
-   AI が推奨するトピックを表示します。
-   トピックを確認して、有効なトピックを確認します。
-   ユーザーに表示しないトピックを削除します。

さらに、ナレッジ マネージャーは、既存のトピックを編集したり、新しいトピックを作成したりできます。

トピックを管理するには、次の情報を使用する必要があります。
-   Microsoft 365 管理者[がビ](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses)バ トピックス ライセンスを割り当てる。
-   [トピックを管理するためのアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center))。 このタスクは、Microsoft 365 管理センターの [ビバ トピックの設定] ページのナレッジ管理者によって実行されます。

ビジネスに関する全体的な知識が豊富なユーザーは、ナレッジ マネージャーの役割に優れた候補者になる可能性があります。 そのような人は、トピックが有効かどうか知る知識を持っているだけでなく、それらのトピックに関連する企業内の人々も知っている可能性があります。


## <a name="knowledge-admins"></a>ナレッジ管理者

ナレッジ管理者は、Microsoft 365 環境でビバ トピックを設定および構成する管理者です。 セットアップが完了した後で、ビバ トピックの設定も管理します。 サポート技術情報管理者の役割では、Microsoft 365 管理センターでセットアップと管理が行われるので、Microsoft 365 グローバル管理者または SharePoint 管理者である必要があります。
セットアップ中に、ナレッジ管理者は次の設定を行うビバ トピックを構成できます。

-   トピックに対してクロールする SharePoint サイトを選択します。
-   トピック (トピック ビューアー) を表示できるライセンスユーザーを選択します。
-   特定から除外するトピックを選択します。
-   トピックを作成および編集できるライセンスユーザー (トピック投稿者) を選択します。
-   トピック (ナレッジ マネージャー) を管理できるライセンスユーザーを選択します。
-   トピック センターに名前を付けます。

ナレッジ マネージャーは、組織内のすべてのビバ トピックス関係者と調整して、構成方法を知る必要があります。 たとえば、新しいプロジェクトに機密情報がある場合、ナレッジ マネージャーに通知して、SharePoint サイトがトピックに対してクロールされないか、特定のトピック名を除外する必要があります。


## <a name="see-also"></a>関連項目

