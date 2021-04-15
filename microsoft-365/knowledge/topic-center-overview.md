---
title: Microsoft Viva Topics のトピック センターの概要
description: Microsoft Viva Topics のトピック センターについて説明します。
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 01b3310f5f822f3f6f38bf4d9e727d41fe2b179b
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760112"
---
# <a name="topic-center-overview-in-microsoft-viva-topics"></a>Microsoft Viva Topics のトピック センターの概要


Microsoft Viva Topics では、トピック センターは、組織の知識の中心として機能する最新の SharePoint サイトです。 Microsoft 365 管理 [センターの Viva Topics](set-up-topic-experiences.md) セットアップ中に作成されます。

トピック センターには、ライセンスを取得したユーザー全員が、接続先のトピックを表示できる Topics Web パーツを含む既定のホーム ページがあります。 

トピックを表示できるライセンスを持つすべてのユーザーがトピック センターにアクセスできる一方で、ナレッジ マネージャーは [トピックの管理] ページを使用してトピック **を管理** することもできます。 [ **トピックの管理]** タブは、[トピックの管理] アクセス許可を持つユーザーにのみ表示されます。 

## <a name="where-is-my-topic-center"></a>トピック センターの場所

トピック センターは、Viva Topics のセットアップ中に作成されます。 セットアップが完了すると、管理者は [トピック センターの管理] ページで URL [を検索できます](./topic-experiences-administration.md#to-access-topics-management-settings)。


1. Microsoft 365 管理センターで、[設定] を選択し、[組織の設定]**を選択します**。
2. [サービス] **タブで** 、[トピック エクスペリエンス] **を選択します**。

    ![ユーザーをナレッジに接続する](../media/admin-org-knowledge-options-completed.png) </br>

3. [トピック センター **] タブを選択** します。[ **サイト アドレス]** の下に、トピック センターへのリンクがあります。

    ![ナレッジ ネットワーク設定](../media/knowledge-network-settings-topic-center.png) </br>



## <a name="home-page"></a>ホーム ページ

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LAhZ]  

</br>


トピック センターのホーム ページでは、接続している組織のトピックを確認できます。

- 推奨される接続 - [これらのトピックに関して一覧表示しました] の下に **トピックが表示されます。私たちはそれを正しいと思いましたか?** これらは、トピックへの接続が AI を介して提案されているトピックです。 たとえば、関連するファイルまたはサイトの作成者である可能性があります。 トピックの関連人物としてリストを表示する必要がある場合は、確認を求めるメッセージが表示されます。

   ![推奨される接続](../media/knowledge-management/my-topics.png) </br>
 
- 確認済み接続 - トピック ページにピン留めされているトピック、またはトピックへの推奨される接続を確認したトピックです。 推奨される接続を確認すると、トピックが [推奨] セクションから [確認済み] セクションに移動します。
 
   ![確認済みトピック](../media/knowledge-management/my-topics-confirmed.png) </br>

ユーザーがトピックへの接続を確認すると、ユーザーはトピック ページを編集して接続を管理できます。 たとえば、トピックへの接続に関する詳細を提供できます。


## <a name="manage-topics-page"></a>[トピックの管理] ページ

トピック センターの [ **トピックの管理]** セクションで作業するには、ナレッジ マネージャーの役割に必要な必要なトピックの管理権限が必要です。 管理者は、ナレッジ管理のセットアップ中にこれらの[](set-up-topic-experiences.md)アクセス許可をユーザーに割り当て[](topic-experiences-knowledge-rules.md)、または Microsoft 365 管理センターを通じて管理者が後で新しいユーザーを追加できます。

[トピックの管理] ページで、トピック ダッシュボードには、指定したソースの場所から識別された、アクセス権を持つすべてのトピックが表示されます。 各トピックには、トピックが検出された日付が表示されます。 [トピックの管理] アクセス許可が割り当てられたユーザーは、未確認のトピックを確認し、次の項目を選択できます。
- トピックを確認する: トピックに関連するファイルとページにアクセスできるユーザーにトピックを強調表示し、関連するトピック カードとトピック ページを表示できます。
- トピックを発行する: トピック情報を編集して、最初に特定されたトピックの品質を向上し、トピックへのビュー アクセス権を持つすべてのユーザーにトピックを強調表示します。 
- トピックを拒否する: トピックをユーザーが使用できません。 トピックは [拒否] タブ **に移動** され、必要に応じて後で確認できます。 

> [!Note] 
> 「 [トピックの管理」ページ](manage-topics.md) のトピック管理トピックの詳細については、「トピックの管理」を参照してください。

## <a name="create-or-edit-a-topic"></a>トピックを作成または編集する

[トピックの作成と編集] 権限がある場合は、次の方法を実行できます。

- [既存のトピックを編集](edit-a-topic.md)する : 検出によって作成された既存のトピック ページを変更できます。
- [新しいトピックを作成](create-a-topic.md)する: 検出によって見つからなかったトピック、または AI ツールがトピックを作成するのに十分な証拠を見つけなかった場合に、新しいトピックを作成できます。


## <a name="see-also"></a>関連項目

[トピック センターでトピックを管理する](manage-topics.md)

