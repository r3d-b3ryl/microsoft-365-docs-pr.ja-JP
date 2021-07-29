---
title: ユーザーの役割Microsoft Viva トピック
ms.author: chucked
author: chuckedmonson
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
ms.openlocfilehash: e26f47e5826ac6db6c41e1b0648dd23398f51c43
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622294"
---
# <a name="roles-in-microsoft-viva-topics"></a>ユーザーの役割Microsoft Viva トピック

特定の環境で Viva Topics をMicrosoft 365、ユーザーは次の役割を果たします。

- トピック閲覧者
- トピック投稿者
- 知識マネージャー
- 知識管理者

## <a name="topic-viewer"></a>トピック閲覧者

トピック ビューアーとは、SharePoint モダン サイト、Microsoft Search Office から SharePoint.com、およびトピック センターで強調表示されたトピックを表示できる組織内のユーザーです。 トピックページでトピックの詳細を表示できます。 

トピックを強調表示し、トピック ページをトピック ビューアーに表示するには、以下を行う必要があります:

- [管理者が Viva Topics ライセンス](./set-up-topic-experiences.md#assign-licenses)を割り当Microsoft 365します。
- トピックへの閲覧権を取得する。 このタスクは、サポート技術情報の [ビバ トピックの設定] ページのナレッジ管理者Microsoft 365 管理センター。

## <a name="topic-contributors"></a>トピック共同作成者

トピック共同作成者とは、組織内でトピック閲覧者の権限を持つだけでなく、既存のトピックを編集したり、新しいトピックを作成したりできるユーザーのことです。 トピック ページ内の情報 (AI または手動で提供された両方) を手動で "キュレーション" し、品質を確保する上で重要な役割を果たします。

トピック投稿者のアクセス許可を持つユーザーには、[トピック] ページに [編集] ボタンが表示され、トピックの更新と発行が可能になります。

トピック共同作成者は、トピック センターから新しいトピックを作成して発行することもできます。

トピックを作成して編集するには、次の条件を実行する必要があります。

- [管理者が Viva Topics ライセンス](./set-up-topic-experiences.md#assign-licenses)を割り当Microsoft 365します。
- [トピックを作成および編集するためのアクセス許可を割り当てる](./topic-experiences-user-permissions.md)。 このタスクは、サポート技術情報の [ビバ トピックの設定] ページのナレッジ管理者Microsoft 365 管理センター。

## <a name="knowledge-managers"></a>知識マネージャー

知識マネージャーとは、組織内のトピックを管理するユーザーのことです。  トピック管理は、トピック センターの **[トピックの** 管理] ページで行われ、ナレッジ マネージャーにのみ表示されます。

[トピックの **管理] ページ** で、ナレッジ マネージャーは次のタスクを実行できます。

- AI が提案するトピックを表示できます。
- トピックを確認して、有効なトピックを確認します。
- ユーザーに表示しないトピックを削除します。

さらに、知識マネージャーは既存のトピックを編集したり、新しいトピックを作成することができます。

トピックを管理するには、次の情報を使用する必要があります。

- [管理者が Viva Topics ライセンス](./set-up-topic-experiences.md#assign-licenses)を割り当Microsoft 365します。
- [トピックを管理するためのアクセス許可を割り当てる](./topic-experiences-user-permissions.md))。 このタスクは、サポート技術情報の [ビバ トピックの設定] ページのナレッジ管理者Microsoft 365 管理センター。

ビジネスに関する全体的な知識が豊富なユーザーは、ナレッジ マネージャーの役割に優れた候補者になる可能性があります。 そのような人は、トピックが有効かどうか知る知識を持っているだけでなく、それらのトピックに関連する企業内の人々も知っている可能性があります。

## <a name="knowledge-admins"></a>ナレッジ管理者

ナレッジ管理者は、特定の環境でビバ トピックを設定および構成するMicrosoft 365です。 セットアップが完了した後で、ビバ トピックの設定も管理します。 ナレッジ管理者の役割では、セットアップと管理がMicrosoft 365完了SharePoint、グローバル管理者または管理者である必要Microsoft 365 管理センター。
セットアップ中に、ナレッジ管理者は次の設定を行うビバ トピックを構成できます。

- トピックをクロールする SharePoint サイトを選択できます。
- トピックを表示できるライセンス所有者を選択できます (トピック閲覧者)。
- 特定できないトピックを選択できます。
- トピックを作成して編集できるライセンス所有者 (トピック共同作成者) を選択できます。
- トピックを管理できるライセンス所有者 (知識マネージャー) を選択できます。
- トピック センターに名前を付けます。

知識マネージャーは、組織内のすべての Viva トピック関係者と協力できるようにその構成方法を理解する必要があります。 たとえば、新しいプロジェクトに機密情報がある場合は、SharePoint サイトがトピックに対してクロールされないか、特定のトピック名を除外する必要がある場合に、ナレッジ マネージャーに通知する必要があります。
